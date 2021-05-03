# docker-jtl-shop-stack
Complete local development stack for JTL Shop 5.0.1, PHP7.4 (Xdebug) - Apache, MariaDB(10.6.0), PhpMyAdmin using docker-compose.

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

# How it works
To access the jtl-shop container run the following:

```bash
> $ docker container ls
CONTAINER ID   IMAGE                     COMMAND                  CREATED             STATUS             PORTS                                            NAMES
9f435f1d4fc5   jtl-5-0-1                 "docker-php-entrypoi…"   3 minutes ago       Up 6 seconds       0.0.0.0:80->80/tcp                               docker-jtl-shop-stack_jtl-shop_1
dbf75c5b6f63   phpmyadmin:5.1.0-apache   "/docker-entrypoint.…"   3 minutes ago       Up 7 seconds       0.0.0.0:8080->80/tcp                             docker-jtl-shop-stack_phpmyadmin_1

# Use the first 3 characters of the container id and run
> $ docker exec -it 9f4 bash
```



