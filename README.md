# spilserver


### What the heck is that ?

Well, if you don't know why your are here, please go away...

Deal with it


### build and publish
```
docker images ls

docker build -t spil_server_image -f ./docker/prod-image/Dockerfile .

docker tag spil_server_image:latest laurentpaprika/spilserver:latest

docker push laurentpaprika/spilserver:latest


```
### Brutal clean of all dockers

```
docker rm -f $(docker ps -a -q)

docker rmi -f $(docker images -a -q)

docker volume rm $(docker volume ls -q)

docker network rm $(docker network ls | tail -n+2 | awk '{if($2 !~ /bridge|none|host/){ print $1 }}')
```
