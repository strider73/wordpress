# wordpress
https://github.com/docker/awesome-compose/tree/master/wordpress-mysql
WordPress with MySQL
This example defines one of the basic setups for WordPress. More details on how this works can be found on the official WordPress image page.

Project structure:

.
├── compose.yaml
└── README.md
compose.yaml

services:
  db:
    # We use a mariadb image which supports both amd64 & arm64 architecture
    image: mariadb:10.6.4-focal
    # If you really want to use MySQL, uncomment the following line
    #image: mysql:8.0.27
    ...
  wordpress:
    image: wordpress:latest
    ports:
      - 80:80
    restart: always
    ...
When deploying this setup, docker compose maps the WordPress container port 80 to port 80 of the host as specified in the compose file.

ℹ️ INFO
For compatibility purpose between AMD64 and ARM64 architecture, we use a MariaDB as database instead of MySQL.
You still can use the MySQL image by uncommenting the following line in the Compose file
#image: mysql:8.0.27

Deploy with docker compose
$ docker compose up -d
Creating network "wordpress-mysql_default" with the default driver
Creating volume "wordpress-mysql_db_data" with default driver
...
Creating wordpress-mysql_db_1        ... done
Creating wordpress-mysql_wordpress_1 ... done