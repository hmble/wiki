## Setup guide

1. Create a .env with variables for developement specified in `.env.example`

2. Run the following command in this directory `localdb`

```bash
 sudo docker compose --env-file=../.env up
```

In order to get container id you can run `sudo docker container ls` to get all the running
containers table

## Backup from docker

```bash
 sudo docker exec -it CONTAINER_ID pg_dump -U POSTGRES_USER POSTGRES_DB > dump.sql
```

### Data only backup

```bash
 sudo docker exec -it CONTAINER_ID pg_dump --column-inserts --data-only -U thor mydb > datadump.sql

```

### Import data to postgres

```bash
 sudo docker exec -i CONTAINER_ID psql -U thor -d mydb -a < datadbump.sql``
