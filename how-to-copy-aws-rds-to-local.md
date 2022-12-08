1. Change your database RDS instance security group to allow your machine to access it. 
    * Add your ip to the security group to acces the instance via Postgres.
2. Make a copy of the database using pg_dump
    * ```$ pg_dump -h <public dns> -U <my username> -f <name of dump file .sql> <name of my database>```
    * you will be asked for postgressql password.
    * a dump file(.sql) will be created
3. Restore that dump file to your local database.
    * but you might need to drop the database and create it first
    * ```$ psql -U <postgresql username> -d <database name> -f <dump file that you want to restore>```
    * the database is restored
4. ```pg_restore -h <host> -U <username> -c -d <database name>  <filename to be restored>```

#####ref 
1. http://stackoverflow.com/questions/31881786/how-to-pg-dump-an-rds-postgres-database
2. http://www.thegeekstuff.com/2009/01/how-to-backup-and-restore-postgres-database-using-pg_dump-and-psql/