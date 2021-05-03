# docker-jtl-shop-stack
Complete local development stack for JTL Shop, PHP7.4 (Xdebug) - Apache, MariaDB(10.6.0), PhpMyAdmin using docker-compose.

Tested JTL Shop Version:
- 5.0.1

# Installation
First, clone this repository:

`$ git clone https://github.com/neumanniTech/docker-jtl-shop-stack.git`

Next, put your JTL Shop into `shop`.

Rename `.env.dist` to `.env`. 

Set the values for `MYSQL_ROOT_PASSWORD, MYSQL_USER, MYSQL_PASSWORD `,

Then, run:

`$ docker-compose up`

You are done, you can visit your JTL Shop on the following URL: `http://localhost` . 

**Info:** The DB Host must be `jtl-db`

PhpMyAdmin: `http://localhost:8080`




