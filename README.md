# Docker-based PHP+Apache/NGINX+MySQL+PHPMyAdmin stack

[![Build Status](https://github.com/shashikanth171/Docker4-PHP-Apache-NGINX-MySQL-PHPMyAdmin/workflows/Run%20tests/badge.svg)](https://github.com/shashikanth171/Docker4-PHP-Apache-NGINX-MySQL-PHPMyAdmin/actions)

## Introduction

Add your PHP application to the `app/` folder and if the project root fopr `apache`/`nginx` is different from `app/` change the path in `docker-compose.yml`

Default port is set to 8001. If needed, change it in .env file along with the Project name and Base URL.

Add Base URL to your hosts file and point it to localhost. Change the base URL in the following command and run it as root on linux based systems. 

`echo "127.0.0.1 my_php_app.local" >> /etc/hosts`

Run `make` to start the containers.

Use http://{PROJECT_BASE_URL}:8001/ to open the project in browser. 
Open http://{PROJECT_BASE_URL}:8001/php_info.php to test is php is working.

Run `make stop` to stop the containers.
Run `make prune` to delete the containers. This might delete all the data from DB too. Use with caution.
Run `make shell` to access shell of php container.

## Stack

The stack consist of the following containers:

| Container       | Versions           | Image                              |
|-----------------|--------------------|------------------------------------|
| [Nginx]         | 1.23               | [wodby/nginx]                      |
| [Apache]        | 2.4                | [wodby/apache]                     |
| [PHP]           | 7.0                | [webdevops/php-apache-dev:7.0]                 |
| [MariaDB]       | 10                 | [wodby/mariadb]                    |
| phpMyAdmin      | latest             | [phpmyadmin/phpmyadmin]            |
| Traefik         | latest             | [_/traefik]                        |
 

## License

This project is licensed under the MIT open source license.

[_/traefik]: https://hub.docker.com/_/traefik
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[selenium/standalone-chrome]: https://hub.docker.com/r/selenium/standalone-chrome
[wodby/apache]: https://github.com/wodby/apache
[wodby/mariadb]: https://github.com/wodby/mariadb
