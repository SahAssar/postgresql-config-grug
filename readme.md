### TODO: migrations

adapted from old madefrom solution:

```sh
# TODO: make sure different errors are handled in different ways here (no db, no migration table, incorrect user, no rows)
# TODO: automatically run `CREATE TABLE migration_done (version integer);` as part of setting up repo
# TODO: client & server githook to validate filenames in the db folder (they should always match \d*-.*.sql)
# TODO: server githook to validate branch names
export OLD_DB_VERSION=`sudo -u postgres psql $branch -t -c 'SELECT version FROM migration_done ORDER BY version DESC LIMIT 1;' || true`
for version in $(ls db | sort -h | sed -r -e 's/^([0-9]*)-.*.sql$/\1/g' -e '/^$/d'); do if [ -z $OLD_DB_VERSION ] || [ $version -gt $OLD_DB_VERSION ]; then sudo -u postgres psql -v ON_ERROR_STOP=1 -1 $branch -f db/$version-*.sql -c "INSERT INTO migration_done VALUES ($version);"; fi; done
sudo -u postgres psql -v ON_ERROR_STOP=1 -1 $branch -c 'VACUUM ANALYZE;'
```