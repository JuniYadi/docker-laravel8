# Docker Laravel 8

Running Laravel 8 in Docker Without [Laravel Sail](https://laravel.com/docs/8.x/sail)

For Laravel < 8, you can change PHP Version:

- PHP 8 => **juniyadi/php-composer:8.0**
- PHP 7.4 => **juniyadi/php-composer:7.4**

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

### Web Access

- Laravel => http://localhost
- Mailhogs => http://localhost:8025
