 # Docker training 
 
A container is launched by running an image. An image is an executable package that includes everything needed to run an application--the code,
 a runtime, libraries, environment variables, and configuration files.
 
A container is a runtime instance of an image--what the image becomes in memory when executed (that is, an image with state, or a user process).
 You can see a list of your running containers with the command, docker ps,
 just as you would in Linux
 
 docker image ls : List the hello-world image that was downloaded to your machine
 docker container ls --all : List the hello-world container (spawned by the image) which exits after displaying its message. If it were still running, you would not need the --all option
 
 ## List Docker CLI commands <br/>
 ```
docker 
docker container --help 
```
## Display Docker version and info <br/>
```
docker --version 
docker version 
docker info 
```
## Execute Docker image <br/>
```
docker run hello-world 
```
## List Docker images
```
docker image ls 
```
## List Docker containers (running, all, all in quiet mode)
```
docker container ls 
docker container ls --all 
docker container ls -aq 
Invoke-WebRequest -uri "http://www.google.nl" -UseBasicParsing	 
docker container stop <Container NAME or ID> 
```
## Part 2  ##
```
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyhello" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running 
docker container stop <hash>           # Gracefully stop the specified container 
docker container kill <hash>         # Force shutdown of the specified container 
docker container rm <hash>        # Remove specified container from this machine 
docker container rm $(docker container ls -a -q)         # Remove all containers 
docker image ls -a                             # List all images on this machine 
docker image rm <image id>            # Remove specified image from this machine 
docker image rm $(docker image ls -a -q)   # Remove all images from this machine 
docker login             # Log in this CLI session using your Docker credentials 
docker tag <image> username/repository:tag  # Tag <image> for upload to registry 
docker push username/repository:tag            # Upload tagged image to registry 
docker run username/repository:tag                   # Run image from a registry 
```
<br/>

Services are really just “containers in production..

```
type NUL > docker-compose.yml  create folder in windows powershell 
```
## Part 3 ## 
A single container running in a service is called a task.
```
docker stack ls                                            # List stacks or apps 
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file 
docker service ls                 # List running services associated with an app 
docker service ps <service>                  # List tasks associated with an app 
docker inspect <task or container>                   # Inspect task or container 
docker container ls -q                                      # List container IDs 
docker stack rm <appname>                             # Tear down an application 
docker swarm leave --force      # Take down a single node swarm from the manager 
```
