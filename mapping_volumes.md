# mapping volumes

bind mounts

	docker run -d -p 127.0.0.1:8080:80 -v ~swalker/workspace/docker-workshop/tmp:/usr/share/nginx/html nginx

volumes

	docker run -d -p 127.0.0.1:8080:80 -v tmp:/usr/share/nginx/html nginx

	docker volume inspect tmp

 	docker volume prune

mention if you use docker toolbox, the directory is mapped from there

	docker-machine ssh default
	
[use volumes](https://docs.docker.com/storage/volumes/) 
[docker volume](https://docs.docker.com/engine/reference/commandline/volume_create/) 