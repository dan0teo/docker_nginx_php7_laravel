### Useful commands.
#### Buid the image:
docker build -t apiimg .

#### !Web application files should be placed into www folder!
#### !After container is running web server and php logs will be stored in logs directory!

#### Run container from image "apiimg": 
docker run -d -p 80:80 -p 443:443 -v /FULL_PATH_TO_CURRENT_DIR/www:/var/www/app -v /FULL_PATH_TO_CURRENT_DIR/logs:/var/log/nginx  --name apisrv apiimg

### If you need restart container after reboot the host machine just add --restart=always, like this:
docker run -d --restart=always -p 80:80 -p 443:443 -v /FULL_PATH_TO_CURRENT_DIR/www:/var/www/app -v /FULL_PATH_TO_CURRENT_DIR/logs:/var/log/nginx  --name apisrv apiimg

#### Enter into docker container:
docker exec -it apisrv bash

#### Restart docker container:
docker restart apisrv

#### Start docker container:
docker start apisrv

#### Stop docker container:
docker stop apisrv

#### For joining several docker containers into one network you need to:

##### 1) create network: 
docker network create --subnet 10.10.10.0/24 net
##### 2) connect containers: 
docker network connect net apisrv

docker network connect net frontsrv


