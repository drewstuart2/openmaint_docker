# openmaint_docker

OpenMaint is web based Property & Facility Management application that is fully open source. It is used for managing fixed and transferable physical assets such as buildings and furniture, along with related maintenance.

This is a fully functional OpenMAINT 2.0 solution using docker containers that employs the following customized stack:

- CMDBuild 3.1.1 core
- OpenMAINT 2.0 database dump
- Tomcat 8.5.42
- OpenJDK version 1.8.0_212
- PostgreSQL 10.7
- Debian 9.9 (stretch)

### Docker & Docker Compose

Docker is a popular tool that makes it easy to create, deploy, and run applications using containers. Containers allow developers to package and ship an application with a full stack of dependencies it needs to run on any other system, regardless of any conflicting configurations that may be present. Docker Compose is a companion tool for creating and running multi-container docker applications.

openmaint_docker was built and tested using the following Docker tools:

- Docker-Compose version 1.21.2, build a133471
- Docker version 19.03.5, build 633a0ea838
- Customized Docker Image: mrhavens/cmdbuild:app-3.1.1 (from Docker Hub)
- Customized Docker Image: mrhavens/cmdbuild:db-3.0 (from Docker Hub)

# Installation Instructions for Ubuntu 18.04 LTS

### Update APT Repository 
```
sudo apt update
```

### Install Docker
```
sudo apt -y install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
apt-cache policy docker-ce
sudo apt -y install docker-ce
```

### Install Docker Compose
```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

### Build OpenMaint & PostgreSQL Containers
```
git clone https://github.com/mrhavens/openmaint_docker.git
cd openmaint_docker
docker-compose up -d
```
