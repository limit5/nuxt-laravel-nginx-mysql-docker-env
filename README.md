# Using Docker to Run Nuxt3 + Laravel 11 + nginx 1.27 + mysql 8.0 + php 8.3 for Fullstack Web Service

# Description
Nuxt 3.12 : run with nodejs 22@alpine3.20

Laravel 11: run with php 8.3 and tested ubuntu 24.04

MySQL 8: run with offical image: mysql-server:8.0

Nginx 1.27: run with 1.27.0-alpine3.19-slim

# Usage:

```
# clone this template
git clone https://github.com/limit5/nuxt-laravel-nginx-mysql-docker-env.git

# change directory into this project
cd nuxt-laravel-nginx-mysql-docker-env

# copy server .env file for mysql setting
cp backend/server/.env.example backend/server/.env

# modify backend/server/.env to set mysql arguments
DB_DATABASE=database
DB_USERNAME=user
DB_PASSWORD=password
DB_ROOT_PASSWORD=root

# build and run all containers
# -d for running in the background
docker compose up -d
```

## (Optional) Modify timezone

There are 4 timezone setting in this template repository

Modify the TZ as needed

The docker-compose.yml in repo root directory

```
TZ: Asia/Taipei
```

The Dockerfile in frontend folder
```
ENV TZ=Asia/Taipei
```

The Dockerfile in httpd/nginx
```
ENV TZ=Asia/Taipei
```

Modify the date.timezone as needed

The php.ini in backend folder
```
date.timezone = "Asia/Taipei"
```

# Check the result
For frontend status (Nginx + Nuxt)
```
# connect to the server
# If the server is fine it will show the Nuxt default page
http://localhost
```

For Backend status (Laravel + Mysql)
```
# check migration status
docker compose exec backend php artisan migrate
```

For Laravel status
```
# connect to web
# Laravel page will show while the server is working fine
http://localhost:8000
```