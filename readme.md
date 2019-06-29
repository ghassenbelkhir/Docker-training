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
docker <br/>
docker container --help <br/>
```
<br/>
## Display Docker version and info <br/>
```
docker --version <br/>
docker version <br/>
docker info <br/>
```
<br/>
## Execute Docker image <br/>
```
docker run hello-world <br/>
<br/>
```
## List Docker images <br/>
```
docker image ls <br/>
```
## List Docker containers (running, all, all in quiet mode)
```
docker container ls <br/>
docker container ls --all <br/>
docker container ls -aq <br/>
<br/>
Invoke-WebRequest -uri "http://www.google.nl" -UseBasicParsing	 <br/>
docker container stop <Container NAME or ID> <br/>
<br/>
## Part 2  ##
docker build -t friendlyhello .  # Create image using this directory's Dockerfile<br/>
docker run -p 4000:80 friendlyhello  # Run "friendlyhello" mapping port 4000 to 80<br/>
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode<br/>
docker container ls                                # List all running containers<br/>
docker container ls -a             # List all containers, even those not running <br/>
docker container stop <hash>           # Gracefully stop the specified container <br/>
docker container kill <hash>         # Force shutdown of the specified container <br/>
docker container rm <hash>        # Remove specified container from this machine <br/>
docker container rm $(docker container ls -a -q)         # Remove all containers <br/>
docker image ls -a                             # List all images on this machine <br/>
docker image rm <image id>            # Remove specified image from this machine <br/>
docker image rm $(docker image ls -a -q)   # Remove all images from this machine <br/>
docker login             # Log in this CLI session using your Docker credentials <br/>
docker tag <image> username/repository:tag  # Tag <image> for upload to registry <br/>
docker push username/repository:tag            # Upload tagged image to registry <br/>
docker run username/repository:tag                   # Run image from a registry <br/>
```
<br/>
Services are really just “containers in production..<br/>
<br/>
```
// type NUL > docker-compose.yml  create folder in windows powershell <br/>
```
## Part 3 ## <br/>
A single container running in a service is called a task. <br/> 
<br/>
```
docker stack ls                                            # List stacks or apps <br/>
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file <br/>
docker service ls                 # List running services associated with an app <br/>
docker service ps <service>                  # List tasks associated with an app <br/>
docker inspect <task or container>                   # Inspect task or container <br/>
docker container ls -q                                      # List container IDs <br/>
docker stack rm <appname>                             # Tear down an application <br/>
docker swarm leave --force      # Take down a single node swarm from the manager <br/>
```
