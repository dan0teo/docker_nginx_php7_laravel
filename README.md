## Useful commands.
### Buid the image:
docker build -t apiimg .

### !Web application files should be placed into www folder!

### Run container from image "apiimg": 
docker run -d -p 80:80 -p 443:443 -v /FULL_PATH_TO_CURRENT_DIR/www:/var/www/app -v /FULL_PATH_TO_CURRENT_DIR/logs:/var/log/nginx  --name apisrv apiimg

### Enter into docker container:
docker exec -it apisrv bash

### Restart docker container:
docker restart apisrv

### Start docker container:
docker start apisrv

### Stop docker container:
docker stop apisrv


