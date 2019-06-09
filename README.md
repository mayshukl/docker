# docker
This is Docker Repo

# Topiccs
#### History
Docker is released on 2013 by DotCloud
#### Why Docker
- Faster Processes (like Develop, Build, Test, Deploy, update) 
- Loghtweight
- Plateform Independent(No seprate setup is needed) 
- Less time to bringup a conatiner running than a sever (Useful in autohealing System )
- Its like process, It needes kerner and very less lib to run. No need for full fledged OS
#### Waht is Docker 
Docker is a container based technology. It runs on Linux kernel.
#### How does is work
- NameSpace : Every container will run as a process
- Control group : This controls the resources for a container
#### Types of Container 
 - Serverless
 - Stateless
 - Statefull
#### Docker Hub
#### Orchestration


# Docker in Use

#### Install Docker
- Download docker for MAC (https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- install docker
- install 2 tab auto complete https://docs.docker.com/compose/completion/ or https://codingbee.net/docker/get-bash-autocompletion-working-for-docker-cli-on-a-mac or https://docs.docker.com/docker-for-mac/#install-shell-completion
- Run Docker (This will start one linux vm also. Can be seen in docker preference/advanced)


#### Commands

- docker version
- docker info
- docker container run --publish 80:80 --detach --name webhost nginx
- docker container logs webhost
- docker container top webhost 
- docker container stop webhost
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





