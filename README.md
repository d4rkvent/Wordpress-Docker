## Wordpress-Docker
# Download and Install docker 

  [Download LInk](https://www.docker.com/)

You can use Docker Compose to easily run WordPress in an isolated environment built with Docker containers. This quick-start guide demonstrates how to use Compose to set up and run WordPress. Before starting, make sure you have Compose installed.

## Instructions 

#### Step 1 : Create two empty folders 
>database
html
docker-compose.yml


#### Step 2 : Create docker-compose.yml file
```
wordpress:
    image: wordpress
    links:
     - mariadb:mysql
    environment:
     - WORDPRESS_DB_PASSWORD=password
    ports:
     - "80:80"
    volumes:
     - ./html:/var/www/html
mariadb:
    image: mariadb:10.0.33
    environment:
     - MYSQL_ROOT_PASSWORD=password
     - MYSQL_DATABASE=wordpress
    volumes:
     - ./database:/var/lib/mysql
```
#### step 3 Run this command
         docker-compose up -d
