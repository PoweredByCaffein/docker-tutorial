## Docker Commands

<hr>

#### Pulling a Docker Image from Docker Hub
```
docker pull IMAGE_NAME
```
By default, this pulls the latest code from the Docker hub<br>
In order to pull a specific version of the image, we use the following command
```
docker pull IMAGE_NAME:VERSION
```

#### Running a Docker Container

Once you have pulled the Docker Image from Docker Hub, now you need to run the Docker Container, in order to do so, 
we use the following command.
<br>
In order for a container to run we need to set up various parameters like the port number, any environment variable if 
that is required.<br>For the demonstration we are doing to run the mongo container, we will setup the port and 
also the required environment variables.
<br>
Let us first look the complete command, then we will see each flag that we have used
```
docker run -d \
--name CONTAINER_NAME \
-p HOST_PORT:CONTAINER_PORT \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
mongo
```

This command will run the Docker container. Let's look at the flags we have used.
<br>
```-d ``` This starts Docker in detached mode <br>
Once you run docker with this, you can go ahead and close the terminal and the container will continue running 
in the background. With this once you close the terminal, it will close the container.

```--name``` Gives a name to the docker container<br>
By default, docker provides a random name to every docker container. This flag helps override the default name and gives
a name that makes the most sense to you.

```-p``` This flag defines the port number to use <br>
It has 2 parameters, the port on the host machine and port inside the docker container
Let us say, in my machine I want mongo on port 3001 and in my container I'm using the default port 27017 then I will use
```-p 3001:27017```

```-e``` These are the environment variables that the container uses, for each container there are different environment
variables, the details for the same can be found on Docker Hub





#### Listing the running Docker Containers
```
docker ps
// ps stands for process status
```

This command only lists the active docker containers, if you want to see all the containers then use the below command
```
docker ps -a
```

#### Remove a docker container

In order to delete or remove a docker container, we first need to find the container ID. For this use the above command
<br>Once you have the container ID, use the below command to remove the container
```
docker rm CONTAINER_ID
```

<hr>

#### Creating a Docker Network
```
docker network create DOCKER_NETWORK_NAME
```

#### Listing all the available Docker Networks
```
docker network ls
```
<hr>


