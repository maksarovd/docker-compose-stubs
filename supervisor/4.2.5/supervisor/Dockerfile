FROM php:8.2-fpm

USER root
RUN apt-get update && apt-get install -y supervisor python3 systemd
RUN pecl install redis && rm -rf /tmp/pear && docker-php-ext-enable redis
ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/supervisord.conf"]
