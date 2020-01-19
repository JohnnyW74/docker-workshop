# docker pull/run
First we have to pull an image
>docker pull alpine

Lets take a look what we are pulling(downloading):
[Alpine Image](https://hub.docker.com/_/alpine/) 

Every Image has a tag. Default is "latest". Be carfeule if you want to rely on in productional environment.

>docker run alpine

Why does nothing happens?

> docker run alpine echo "hello world"

Now interactive

> docker run -ti alpine

What do you see inside an container? What do you see outside an container?

Are Containers persistent?
> docker run -ti alpine
> touch hugo
> ls -l
> exit
> docker run -ti alpine
> ls -l

[weiter](https://github.com/JohnnyW74/docker-workshop/blob/master/docker_image_ps.md) 