# Importing Multiple Databases

### Homestead example
When you update homestead you will have to reseed the data you had in your databases. This is the fastest way to do that from one dump.
```
for DB in `mysql -u homestead -r --silent -p -e 'show databases;' | egrep -v "_schema$|^mysql$|^sys$"`
do
  mysql -uhomestead -p $DB < homestead_backup.sql
done
```
