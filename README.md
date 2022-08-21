
![](./icons8-docker-480.png)


## 1.docker-search
We use this command to search for public images on Docker hub.It
will return information about the image name, description, stars, official and automated. 

docker search alpine

## 2.docker pull
We can pull images from the Docker hub
using this command.

docker pull alpine

Tags are used to identify images inside a repository.
If we don’t specify a tag Docker engine uses the :latest tag by default.

So, in the above example we pulled the latest image of alpine.

We can have multiple images under one repository,
so we can use --all-tags option to pull the images.

docker pull --all-tags alpine
## 3.docker images
We can see all the images that have been pulled by this command

docker images

So, in this case, it will show images of alpine with different tags.
## 4.docker run
Now, lets try to create a container.
we use --env option to set a mandatory environment 
variable and --detach option to run the container in the background.

docker run --env MYSQL_ROOT_PASSWORD=my-secret-pw --detach mysql

we can use --name option to assign a name to the container.Or else
Docker will randomly assign a name.



## 5.docker ps
We can list all the running containers using 
this command.

docker ps

we can also run the stopped
containers using --all option.

docker ps --all

## 6.docker stop
It is used to stop a container.
Container id or container name should 
be provided

docker stop container id/container name


## 7.docker restart
We can restart our stopped container by using this command.
We may want to use it after we reboot our machine.

docker restart f8c619becc
## 8.docker rename
Let's say we want to change the 
container name from my_container to alpine_db.We may want to change
the name to keep track of our containers more easily.

docker rename my_container alpine_db
## 9.docker exec
We access the running container alpine_db by running this command.We may want to go to alpine and 
execute alpine queries.

docker exec -it alpine_db bash

The -i and -t options are used to access the container in an interactive mode. 
Then we provide the name of the container we want to access, heree it's alpine_db.
Then we write bash to get the bash shell inside the container.
## 10. docker logs

It is used to debug our Docker containers. 
It will fetch logs from a specified container.

docker logs alpine_db

If we want to continue to stream new output, we can use the option -follow.

docker logs -follow alpine_db.
## 11. docker rm
It is used to remove a container.

docker rm alpine_db

But first we need to stop the container or else we will get an 
error response from daemon.

docker rm -f test_db
## 12. docker rmi

This command is used to remove an image provided with the image id.

docker rmi fb0e483dc3cf