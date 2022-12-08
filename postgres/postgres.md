# How to create database and user

```bash
sudo -u postgres psql
postgres=# create database mydb;
postgres=# create user myuser with encrypted password 'mypass';
postgres=# grant all privileges on database mydb to myuser;
```

# Import sql
```
psql -U USER_ROLE -d DATABASE_NAME < dump.sql
```
# PG dump
```
pg_dump -d DATABASE_NAME -h localhost -p 5432 -u USER_ROLE > dump.sql 
```
