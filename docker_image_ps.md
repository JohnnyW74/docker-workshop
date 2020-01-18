# docker ps
## docker ps
Which containers are running?
>docker ps

Which containers have run in the past

>docker ps -a

How to delete

> docker rm *container_id*

How to clean all containers the old way

> docker rm $(docker ps -a -q)

the new Way

> docker container prune
## docker images
Which containers have i downloaded?
> docker images

How to delete

> docker rmi *image_id*

Force will delete also all containers relying on the image

> docker rmi -f *image_id*

Delete all images

> docker image prune