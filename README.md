# JTL docker
Complete local development stack for JTL Shop 5, PHP8.1 (Xdebug) - Apache, MariaDB(10.6.0), PhpMyAdmin and mailhog using docker-compose.

Tested JTL Shop Version:
- 5.2.1

Original Repo here: https://github.com/neumanniTech/docker-jtl-shop-stack

# Installation
## Clone the Repo
First, clone this repository:

`git clone git@github.com:hreinberger/jtl-docker.git`

Next, put your JTL Shop into `shop`. You can obtain a recent shop build from here: https://build.jtl-shop.de/ 

Rename `.env.dist` to `.env`. 

Set the values for `MYSQL_ROOT_PASSWORD, MYSQL_USER, MYSQL_PASSWORD `,

Then, run:

`docker-compose up -d`

## DB Setup
The shop wants an existing DB, so you'll have to create one in PHPMyAdmin: `http://localhost:8080`

## Shop Installation

You can now visit and configure your JTL Shop on the following URL: `http://localhost`.

**Info:** The DB Host must be `jtl-db`

## Mailhog configuration
In JTLs Mail settings, set the mail method to SMTP and SMTP hostname to `mailhog` on Port 1025 with no auth

## Links
PhpMyAdmin: `http://localhost:8080`
Mailhog: `http://localhost:8888`

# How it works
To access the jtl-shop container run the following:

```bash
docker compose exec jtl-shop bash
```

Logs can be shown using 

```bash
docker compose logs jtl-shop bash
```

## htaccess issues
If you're having trouble with access to the PDPs, copy the `.htaccess` file from the `docker/web` directory to the shop directory.

# To Do
[ ] automate .htaccess setup
[ ] download and unzip shop build automatically
[ ] docker image