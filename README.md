# dev-docker
Development environment for web applications (PHP, Node.js)

***This package contains:***

PHP-FPM: 7.3\
PostgreSQL: 11.1\
MySQL: 5.6\
Nginx: Latest

***Bash user for php-fpm container:***\
user: dev\
example: sudo docker-compose exec --user=dev php-fpm bash

***Notes***
- The PHP-FPM contains: Node.js, NPM, Composer 
