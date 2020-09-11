# Redmine on docker compose 
# 1. Setup docker and docker compose on your linux box
# - Here I am going with Ubuntu 20.04 
# https://github.com/xxnnou/xdocker/blob/master/setup-docker-and-compose-ubuntu.txt
# 
# https://hub.docker.com/_/redmine
echo 'version: '3.1'
services:
  redmine:
    image: redmine
    restart: always
    ports:
      - 8080:3000
    environment:
      REDMINE_DB_MYSQL: db
      REDMINE_DB_PASSWORD: example
      REDMINE_SECRET_KEY_BASE: supersecretkey
  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: example
      MYSQL_DATABASE: redmine' > docker-compose.yml

docker-compose up -d 
