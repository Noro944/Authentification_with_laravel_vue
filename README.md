Prerequisites

Before you start, you will need:

    One Ubuntu 18.04 server with a non-root user with sudo privileges.
    Docker installed on Ubuntu 18.04.
    Docker Compose installed on Ubuntu 18.04.


Place auth_projecct folder in your ubuntu server's user's folder
example :

 "\\wsl$\Ubuntu-18.04\home\ {user_name} \auth_projecct"

Run following codes :

docker-compose up -d

docker-compose exec app php artisan migrate

Go to http://localhost/ or http://127.0.0.1/


Connect to register page, create a user then go to login page and connect with your login and password.

In this project following technologies were used :

Laravel
Vue js
Php
Mysql
Docker
Nginx
