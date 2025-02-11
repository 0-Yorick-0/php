# php-fpm container

Docker image for php-fpm made to use with led.

## Available versions

| Tag      | Description      |
| -------- | -----------------|
| **5.6**  | PHP 5.6.40       |
| **7.0**  | PHP 7.0.33       |
| **7.1**  | PHP 7.1.33       |
| **7.2**  | PHP 7.2.34       |
| **7.3**  | PHP 7.3.31       |
| **7.4**  | PHP 7.4.24       |
| **8.0**  | PHP 8.0.11       |
| **8.1**  | PHP 8.1.0~RC3    |

## Includes

- Composer version 1.10.22 (prestaconcept)
- Composer version 2.1.8 (prestaconcept)
- Git 2.29.2 (prestaconcept)
- Make 3.82
- Wkhtmltopdf 0.12.3 (prestaconcept)

### PECL

```
AMQP
AST
APCu
Imagick
pecl_HTTP
lz4
mailparse
memcached
mongodb
maxminddb
redis
ssh2
XDebug
```

**Note** : Some extensions are not yet compatible with PHP 8.0)

XDebug is disabled by default. Set an environment variable `PHP_XDEBUG` setted to 1

## Usage

**By default, the image launch PHP-FPM in foreground**

```
docker run -it --rm ledup/php:*tag*
```

**To override command**

```
docker run -it --rm ledup/php:*tag* bash
```

**To override PHP memory limit**

```
docker run -it -e PHP_MEMORY_LIMIT=1024M --rm ledup/php:*tag* php -i | grep memory_limit
```

## Logs

Daemon output is redirected to stderr to be readable from container's log with `docker logs [container_name]`

## Misc

In this images, `composer` is wrapped to a shell function which disable XDebug on-the-fly if enabled
