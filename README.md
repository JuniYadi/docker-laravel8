# Docker Backend

## Start Docker

```
docker-compose up -d
```

## Stop Docker

```
docker-compose down
```

## MySQL Database

- Agar file Database tidak hilang, docker akan membuat folder data, sehingga ketika di stop, data tidak hilang

## Laravel Install

### First Command

```
docker-compose exec app composer install
docker-compose exec app php cp .env.example .env
docker-compose exec app php artisan key:generate
```

### Generate Model or Others

```
docker-compose exec app php artisan make:model Files -m
```
