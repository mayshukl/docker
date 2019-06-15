# Docker 

Docker is a continer based technology that is released on 2013 by DotCloud. It is written in GO.

#### Why Docker
- Faster Processes (like Develop, Build, Test, Deploy, update) 
- Loghtweight
- Plateform Independent(No separate setup is needed) 
- Less time to bringup a conatiner running than a sever (Useful in autohealing System )
- Its like process, It needes kerner and very less lib to run. No need for full fledged OS
#### Waht is Docker 

Docker is a container based technology. It runs on Linux kernel.


#### How does is work
- https://www.toptal.com/linux/separation-anxiety-isolating-your-system-with-linux-namespaces
- NameSpace : Every container will run as a process
- Control group : This controls the resources for a container i.e. how much memory can a container have

#### Docker Objects
- Images
- Container
- Volumne
- Network
- plugins

#### Types of Container 
 - Serverless
 - Stateless
 - Statefull
 
#### Docker Hub
This is a repository of docker images. (like maven repository)  

#### Orchestration
kubernetes , swarn

#### Images
- can be defined as app binaries, its dependencies and its metadata
- This is layred structure of changes. 

#### Continers
This is running image with one R/W lyre

#### Network
There are 3 default netrworks
- null    -> Continer will not be in any network
- host    -> Continer will use host machine network
- bridge  -> This is a private netork of docker engine. All continers will be in this network by default.

Custom network can also be created using network commands


#### To Persist Data
- container
-  Build Mounts

#### Volumne


# Docker in Use

#### Install Docker

- Download docker for MAC (https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- install docker
- install 2 tab auto complete https://docs.docker.com/compose/completion/ or https://codingbee.net/docker/get-bash-autocompletion-working-for-docker-cli-on-a-mac or https://docs.docker.com/docker-for-mac/#install-shell-completion
- Run Docker (This will start one linux vm also. Can be seen in docker preference/advanced)


#### Login to docker hub
- docker login
- docker logout
- .docker/daemon.json

#### Commands

- docker version
- docker info
- docker container run --publish 80:80 --detach --name webhost nginx
- docker container logs webhost
- docker container top webhost 
- docker container stop webhost   (This initiate SIGTERM )
- docker container stop webhost    (This initiate SIGKILL )
- docker container rm webhost
- docker container run --name mongo -detach mongo
- docker container ls
- ps aux | grep mongo
- docker container top mongo
- docker container run --publish 80:80 --name proxy -d nginx
- docker container run --publish 8080:80 --name webapp -d httpd
- docker container run --publish 3306:3306 --name mysql -e MYSQL_RANDOM_ROOT_PASSWORD=yes -d mysql
- docker container inspect nginx
- docker container stats nginx(change can be seen if you try to load localhost page)

#### Getting inside container

- docker container run -it --name proxy nginx bash
- exit to exit from bash
- docker container run -it --name ubuntu ubuntu (This will run ubuntu container. This will not have features like ubuntu IOS)
- apt update
- apt-get install curl
- (After stopping )docker container start -ai ubuntu
- docker container exec -it nginx bash 
- docker container run -it alpine sh (alpnie linux has 5 mb in size)


#### Network
- docker network create my-network
-  docker network ls
- docker container run -d --name new_nginx --network my-network nginx
- docker network inspect my-network
- docker container ls
- docker network ls
- docker network connect df9a66b8dce0 f70bdae90e8f
- docker network disconnect f70bdae90e8f df9a66b8dce0


#### DNS
- docker container exec -it my_nginx ping new_nginx  (This works beacuse both are same custom created network. To enable dns in default brifge server , it uses --link option)

#### DNS Round Robin

- docker network create dns_network
- docker network create dns_network
- docker container run -d  --net dns_network --net-alias search elasticsearch:2
- docker container run -d  --net dns_network --net-alias search elasticsearch:2
- docker container run --rm --net dns_network alpine nslookup search
- docker container run --rm --net dns_network centos curl -s search:9200


#### Images
- docker image ls
- docker pull nginx:mainline
- docker history nginx:latest
- docker inspect nginx


#### Clean host
- docker image prune      (to clean up just "dangling" images)
- docker system prune      (will clean up everything)

Docker-compone

- docker-compose up --build
- docker-compose up -d
- docker-compose down
- docker-compose ps




