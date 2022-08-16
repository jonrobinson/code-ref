# DB Docs

### Dumping
```
mysqldump --single-transaction --skip-add-locks --no-data -u homestead -p lauded  > lauded.sql
```

### Modify The File
Replace: `DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP`
With: `DEFAULT CURRENT_TIMESTAMP`

```
sql2dbml --mysql lauded.sql -o lauded.dbml
```
