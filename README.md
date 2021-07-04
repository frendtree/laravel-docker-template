# Laravel Docker Template

## 概要

docker-composeでLaravel+PHP+Nginx+PostgreSQLの環境を構築するためのテンプレートです。

## 使用ソフトウェア

- PHP 8.0
- PostgreSQL 13
- Nginx 1.18

## 使用方法（例）

dockerを起動します。

```shell script
cd /path/to/laravel-docker-sample
docker-compose up -d
```

Laravelをインストールします。

```shell script
docker-compose exec app bash
rm .gitkeep
composer create-project laravel/laravel .
```

