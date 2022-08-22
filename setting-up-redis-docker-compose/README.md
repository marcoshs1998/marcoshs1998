## Run REDIS on docker compose up

1. Download file `docker-compose.yml`
2. Start default containers by docker compose-up
```
docker-compose -f "docker-compose.yml" up -d --build
```

## Redis Password

If you must set a password to redis server, add a new environment:
```
command: redis-server --save 20 1 --loglevel warning --requirepass YOUR_PASSWORD_HERE
```