# JTL docker
Complete local development stack for JTL Shop, PHP (Xdebug) - Apache, MariaDB, PhpMyAdmin and mailhog using docker-compose.

Tested JTL Shop Version:
- 5.x

Original Repo here: https://github.com/neumanniTech/docker-jtl-shop-stack

# Installation
## Clone the Repo
First, clone this repository:

`git clone git@github.com:hreinberger/jtl-docker.git`

Rename `.env.example` to `.env`. 

Set the values for `MYSQL_ROOT_PASSWORD, MYSQL_USER, MYSQL_PASSWORD, PHP_VERSION` and `JTL_VERSION` (with `JTL_VERSION` in a vX-Y-Z notation)

Then, run:
```bash
docker-compose build && docker compose up -d
```

Docker now prepares the containers and downloads JTL, so this can take a while.

## Shop Installation

You can now visit and configure your JTL Shop on the following URL: `http://localhost`.

**Info:** The DB Host must be `jtl-db`

## Mailhog configuration
In JTLs Mail settings, set the mail method to SMTP and SMTP hostname to `mailhog` on Port 1025 with no auth

## Links
PhpMyAdmin: `http://localhost:8080`
Mailhog: `http://localhost:8081`

# How it works
To access the jtl-shop container run the following:

```bash
docker compose exec jtl-shop bash
```

Logs can be shown using 

```bash
docker compose logs jtl-shop bash
```
# To Do
[x] download and unzip shop build automatically

[ ] docker image