# Redmine on docker compose
# Redmine is latest one (4.1.1)
# Setup docker and docker compose on your linux box
# and here I am going with Ubuntu 20.04
# -> https://github.com/xxnnou/xdocker/blob/master/setup-docker-and-compose-ubuntu.txt
#
# Official Redmine Docker
# https://hub.docker.com/_/redmine
# 
docker-compose.yml
# You need to change the creditial information yaml file 
sudo mkdir -p /data/redmine/data_dir/files
sudo mkdir -p /data/redmine/data_dir/plugins
sudo mkdir -p /data/redmine/db
...
redmine:
   volumes:
      - /data/redmine/data_dir/files:/usr/src/redmine/files
      - /data/redmine/data_dir/plugins:/usr/src/redmine/plugins
db:
   volumes:
      - /data/redmine/db:/usr/src/redmine
...

docker-compose up -d
# default redmine username and password
# username: admin 
# password: admin
