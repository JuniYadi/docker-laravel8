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
docker-compose exec node yarn install && yarn dev
docker-compose exec app php cp .env.example .env
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan migrate
```

### Install Jetstream Liveware (Manual Install)

Ref: https://jetstream.laravel.com/2.x/installation.html

```bash
docker-compose exec app composer require laravel/jetstream
docker-compose exec app php artisan jetstream:install livewire
docker-compose exec node yarn install && yarn dev
docker-compose exec app php artisan migrate
docker-compose exec app php artisan vendor:publish --tag=jetstream-views
```

### Install Sactum (API Token)

Ref: https://laravel.com/docs/8.x/sanctum

```bash
docker-compose exec app composer require laravel/sanctum
docker-compose exec app php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
docker-compose exec app php artisan migrate
```

### Generate Model or Others

```bash
docker-compose exec app php artisan make:model <ModelName> -m
```
