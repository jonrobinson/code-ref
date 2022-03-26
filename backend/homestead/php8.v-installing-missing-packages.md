# Installing Missing Packages

### Note
Suprisingly I did not have to update the php.ini and unsilence the extensions.

```
sudo apt-get install php8.1-curl
```

# Missing ZIP
```
sudo apt-get install php8.1-zip
```

# Missing DOM
```
sudo apt-get install php8.1-xml
```

# Missing GD
```
sudo apt-get install php8.1-gd
```

# Missing MYSQL PHP
Error: Illuminate\Database\QueryException: could not find driver (SQL: SHOW FULL TABLES WHERE table_type = 'BASE TABLE')
```
sudo apt-get install php8.1-mysql
```
