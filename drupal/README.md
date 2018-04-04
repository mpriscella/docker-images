# Drupal

Example docker-compose.yml:

```
version: '3'
services:
  mysql:
    image: mysql:latest
    environment:
      - MYSQL_ROOT_PASSWORD=root
      - MYSQL_DATABASE=drupal
      - MYSQL_USER=drupal
      - MYSQL_PASSWORD=drupal
  drupal:
    image: mpriscella/drupal:8.5.1
    ports:
      - '8080:80'
    volumes:
      - ./modules:/var/www/html/modules
    depends_on:
      - mysql
```
