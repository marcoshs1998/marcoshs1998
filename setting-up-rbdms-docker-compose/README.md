## Run RBDMS's on docker compose up

1. Download file `docker-compose.yml` or clone this repo
2. Start default containers by docker compose-up
```
docker-compose -f "docker-compose.yml" up -d --build
```

## Start only SQLServer 2017
use `docker-compose.yml` from folder `mssql`
```
cd mssql
docker-compose -f "docker-compose.yml" up -d --build
```

## Start only MySQL
use `docker-compose.yml` from folder `mysql`
```
cd mysql
docker-compose -f "docker-compose.yml" up -d --build
```

## Start only Postgres
use `docker-compose.yml` from folder `postgres`
```
cd postgres
docker-compose -f "docker-compose.yml" up -d --build
```