# Basic Functions

### Login
```
psql -U postgres
```

### List Databases
```
SELECT datname FROM pg_database;
```

### Create Database
```
CREATE DATABASE jons_db
```

### Displaying Databases
```
SELECT datname FROM pg_database;
```

### Sourcing from Database Dump
```
psql -U postgres -d db_name < dump_file_name.sql
```
