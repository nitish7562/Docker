 # Docker Documentation :
In this documentation we covers basics of `Docker` like setup, images, containers, networking, volumes, and some basic `Docker` commands for efficient containerization practices. 

![image](https://www.docker.com/wp-content/uploads/2022/12/Docker-Temporary-Image-Social-Thumbnail-1200x630-1.png)

## Table of Content

1. [What is Docker?](#what-is-docker)
2. [Why use Docker?](#why-use-docker)
3. [Key Features of Docker](#key-features-of-docker)
   
4. [Docker Architecture](#docker-architecture)
5. [Installation of Docker](#installation-of-docker)
6. [What is container?](#what-is-container)
7. [Docker Files](#docker-files)
8. [Components of Docker files](#components-of-docker-files)
9. [Docker Network and Types](#docker-network-and-types)
10. [Docker Storage](#docker-storage)
11. [docker commands](#docker-commands)
12. [Conclusion](#conclusion)
13. [Reference Link](#reference-link)

## What is Docker?

* ```Docker``` is a platform for developing, shipping, and running applications. It uses containerization technology to package software and its dependencies into standardized units called containers. These containers can run on any machine, providing consistency across environments and simplifying the deployment process for developers and system administrators.
* ```Docker``` is an open source software program or a service to manage containers, it enables us to create, run and execute softwares virtually without installing any other operating system. In short docker is an ecosystem where we can create and run containers.
* ```Docker``` is a service which contains containers . it is derived for developers to develop, to run and execute applications. There is no need to install multiple operating systems. Also, docker is very flexible to work.

## Why use Docker?

### Clean & Separate:

*Run each app in its own space, like having separate rooms for different tasks. This keeps things organized and avoids conflicts.*

### Move Anywhere:

*Imagine our apps in portable boxes. Docker lets move our apps easily between different computers or cloud services, like packing boxes for a move.*

### Runs Fast & Lean:

*Containers are lightweight, like carrying a backpack instead of a suitcase. They start up quicker and use fewer resources.*

### Always the Same:

*Build our app recipe once with Docker. No matter where i run it, I get the same results, avoiding setup headaches.*

### Share and Colaborate:

*Easily share our apps with others. They can run them without needing the same setup you have, like sharing a recipe with friends.*

## Key Features of Docker:

### Containerization:

* Containerization in ```Docker``` is like packing our software and all its stuff into a virtual box, called a container. It keeps everything tidy and separate from the rest of our computer, so our programs run smoothly without messing with each other. It's like having a mini world for each application.

### Portability:

* `Docker` containers can run on any machine that supports Docker, Making it easy to deploy application across various platforms, from development to production. 

### Efficiency:

* `Docker` uses resourcess more eficiently than traditional virtual machines, as containers share the host system's kernel and do not require a full opearating system.

### Scalability:

* `Docker` makes it easy to scale applications by quickly deploying additional containers to handle increased demand.

### Modularity:

* `Docker` promotes a modular approach to software development, where applications are broken down into smaller. Manageable components that can be developed, tested, and deployed independently.

 ### Developer Productivity:

* With the help of `docker`, Developer can build, test, and deploy applications more quicly and reliablly, thanks to the ability to create lightweight, reproducible development enviroments.

## Docker Architecture

*Docker uses Client-Server architecture, which involves the 3 main components that are Docker Client, Docker Host, and Docker Registry. The Docker client communicates with the Docker daemon, which takes care of the building, running, and distributing the Docker containers. The Docker client and daemon can run on the same system or connect a client to a remote Docker daemon. They communicate using REST APIs, over UNIX sockets or a network interface.*

![image](https://k21academy.com/wp-content/uploads/2021/04/image-16-1.png)

**Docker Client :**
* With the help of the docker client, the docker users can interact with the docker. The docker command uses the Docker API. The Docker client can communicate with multiple daemons. When a docker client runs any docker command on the docker terminal then the terminal sends instructions to the daemon.
* The main objective of the docker client is to provide a way to direct the pull of images from the docker registry and run them on the docker host.
  
***Commands used by Client :***

I. `docker build` command is used to create a Docker image from a Dockerfile and a context. 
```bash
$ docker build
```
II. The `docker pull` command is used by a client to download an image from a Docker registry (such as Docker Hub) to their local system.
```bash
$ docker pull
```
III. `docker run` command is used to start a new container from a Docker image. 
```bash
$ docker run
```

**Docker Host :**
* A Docker host is a type of machine that is responsible for running more than one container.
* It contains the Docker daemon, Images, Containers, Networks, and Storage.

**Docker daemon :**
* Docker daemon runs on the host O/S.
* It is responsible for running containers to manage docker services. and it also can communicate with other daemon.

**Docker Registry :** 
* Docker registry manages and stores the docker images.

***types of Registries.***
* Public Registry: It can be accessed by anyone and anywhere.
* Private Registry: It is used to share the image with the interpries.

## Installation of Docker

#### Step 1. Check if the system up-to-date using following command :
```bash
$ sudo apt-get update
```
#### Step 2. After update system Now you can Install Docker using the following command:
```bash
$ sudo apt install docker.io
```
* You’ll then get a prompt asking you to choose between y/n - choose y
```bash
Do you want to continue? [Y/n] y
```
#### Step 3. Install all the dependency package using this command:
```bash
$  sudo snap install docker
```
#### Step 4. check the version of Docker :
```bash
$ docker version

nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ docker --version
Docker version 26.0.2, build 3c863ff
```

#### Step 5. Verify Installation of docker :
* You can verify Docker is running correctly by running a test container.
```bash
$ sudo docker run hello-world

nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker run hello-world
[sudo] password for nitishkumar: 

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```
* Great! Now You have successfully installed docker.

#### Step 6. Start the service of docker :
```bash
$ sudo systemctl start docker
```

#### step 7. Check the status of docker service :
```bash
$ sudo systemctl status docker

nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Wed 2024-06-05 14:16:59 IST; 36s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 76257 (dockerd)
      Tasks: 15
     Memory: 33.0M
        CPU: 312ms
     CGroup: /system.slice/docker.service
             └─76257 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Jun 05 14:16:58 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:58.737531911+05:30" level=info msg="Starting up"
Jun 05 14:16:58 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:58.738055253+05:30" level=info msg="detected 127.0.0.53 >
Jun 05 14:16:58 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:58.792383693+05:30" level=info msg="[graphdriver] using >
Jun 05 14:16:58 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:58.801313890+05:30" level=info msg="Loading containers: >
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:59.301724837+05:30" level=info msg="Default bridge (dock>
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:59.392264254+05:30" level=info msg="Loading containers: >
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:59.419422861+05:30" level=info msg="Docker daemon" commi>
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:59.419606032+05:30" level=info msg="Daemon has completed>
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 dockerd[76257]: time="2024-06-05T14:16:59.438630812+05:30" level=info msg="API listen on /run/d>
Jun 05 14:16:59 nitishkumar-IdeaPad-3-15ITL6 systemd[1]: Started Docker Application Container Engine.
```
<br>

## What is container?
* A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.
* A Docker container is a lightweight, standalone, executable package that includes everything needed to run a piece of software: code, runtime, system tools, libraries, and settings. It is built from a Docker image and can run consistently on any system that has Docker installed.
![image](https://www.docker.com/wp-content/uploads/2021/11/docker-containerized-appliction-blue-border_2.png)
  
## Docker Files
*A Dockerfile is a text file that contains a series of instructions to build a Docker image. It specifies the base image, installs necessary software, copies files, and sets up the environment and commands needed to run the application. It automates the image creation process.*

![image](https://media.geeksforgeeks.org/wp-content/uploads/20230406105935/dockerfile-2.png)

## Components of Docker files 

**FROM** : Specifies the base image to use for the Docker image. Every Dockerfile must start with a `FROM` instruction.

**RUN** : It contains commands to be executed while creating image. It will create layers in image.

**COPY** : It is used to Copies files or directories from the host system into the Docker image.

**ADD** : It is similar to `COPY` command but also supports URL sources and extracting tar archives.

**WORKDIR** : It is used to set a working directory for container.

**CMD** : It Provides the default command to run when the container starts. Only one CMD instruction can be used.

**ENTRPOINT** : Configures a container that will run as an executable. It is similar to CMD but allows you to pass additional arguments to the executable.

**ENV** : It is used to Sets environment variables in the container.

**expose** : It is used to export ports such as `8080` for tomcat, `80` for nginx etc.

**ARG** : Defines variables. It is used to define build-time variable.

## Docker Network and Types 

*The Docker network is a virtual network created by Docker to enable communication between Docker containers. If two containers are running on the same host they can communicate with each other without the need for ports to be exposed to the host machine*

![image](https://media.geeksforgeeks.org/wp-content/uploads/20190915142620/docker_networks2.png)

**Types :**
1. `bridge:` If you build a container without specifying the kind of driver, the container will only be created in the bridge network, which is the default network.

2. `host:` Containers will not have any IP address they will be directly created in the system network which will remove isolation between the docker host and containers.

3. `none:` IP addresses won’t be assigned to containers. These containments are not accessible to us from the outside or from any other container.

4. `overlay:` overlay network will enable the connection between multiple Docker demons and make different Docker swarm services communicate with each other.

* By default, Docker provides two network drivers for you, the bridge and the overlay drivers.
```bash
$ docker network ls
```

```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ docker network ls
NETWORK ID     NAME      DRIVER    SCOPE
332f09da8fef   bridge    bridge    local
134d7dca47e4   host      host      local
3ccbbad91e95   none      null      local
```

![image](https://media.geeksforgeeks.org/wp-content/uploads/20230419172809/Docker-network-1.webp)

## Docker Storage
* Docker storage refers to how data is stored and managed in Docker containers. It includes various mechanisms to persist data generated and used by containers.
* Containers don’t write data permanently to any storage location. Docker storage must be configured if you would like your container to store data permanently. The data doesn’t prevail when the container is deleted (using the remove command); this happens because when the container is deleted, the writable layer is also deleted. If the data is stored outside the container you can use it even if the container no longer exists.

   ![image](https://static.javatpoint.com/blog/images/what-is-docker-volume.png)

### Types :
##### 1. Docker Volume :
* `Docker Volume` is the most commonly used technology for the permanent storage of container data.
* `Docker volume` is managed by Docker itself and has a dedicated filesystem on the host, and doesn't depend upon the filesystem structure on the host.
* It ia an explicitly managed via the Docker command line and can be created alone or during container initialization.

|**Command**|**Description**|
| - | - |
|docker volume create|Create a volume|
|docker volume inspect|Display detailed information on one or more volumes|
|docker volume Is|List volumes|
|docker volume prune|Remove all unused local volumes|
|docker volume rm|Remove one or more volumes|

##### 2. Docker Bind Mounts : 
* Docker Bind Mounts is a mechanism provided by Docker to store container data on localhost, but the directory or file mounted using bind mounts can be accessed by non-Docker processes as well and it relies on the host machine’s filesystem having a specific directory structure available because it uses absolute path for binding.
  
* Docker bind mount is the second permanent storage option but with more limited options than Docker volume.

* It can’t be managed via Docker CLI and is totally dependent on the availability of the filesystem of the host.
  
**Command :**
```bash
$ docker container run -v /host-path:/container-path image-name
```

##### 3. tmpfs Mounts :
* When using Docker in Linux, you can also create storage volume for containers using tmpfs mount. But contrary to bind mounts and volumes, this type of mount is temporary and persists on host memory.

* tmpfs is a third storage option that is not permanent like Docker volume or bind mount.

* The data is written directly on to the host’s memory and deleted when the container is stopped.

**Command :**
```bash
$ docker run -d --name tmptest --mount type=tmpfs,destination=/app nginx:latest
```

## docker commands
**Some of the most commonly used docker commands are**

1. Check docker version
```bash
$ docker --version
```
```bash
$ nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ docker --version
Docker version 26.0.2, build 3c863ff
```

2. Lists docker images on the host machine.
```bash
$ docker images
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    d2c94e258dcb   13 months ago   13.3kB
```

3. To find out an images in docker hub
 ```bash
$ docker search (Image name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ docker search httpd
NAME                             DESCRIPTION                                     STARS     OFFICIAL
httpd                            The Apache HTTP Server Project                  4723      [OK]
paketobuildpacks/httpd                                                           0         
vulhub/httpd                                                                     0         
jitesoft/httpd                   Apache httpd on Alpine linux.                   0         
openquantumsafe/httpd            Demo of post-quantum cryptography in Apache …   12        
wodby/httpd                                                                      0         
dockette/httpdump                                                                0         
betterweb/httpd                                                                  0         
dockette/apache                  Apache / HTTPD                                  1         
centos/httpd-24-centos7          Platform for running Apache httpd 2.4 or bui…   46        
manageiq/httpd                   Container with httpd, built on CentOS for Ma…   1         
centos/httpd-24-centos8                                                          3         
dockerpinata/httpd                                                               1         
httpdocker/kubia                                                                 0         
httpdss/archerysec               ArcherySec repository                           0         
19022021/httpd-connection_test   This httpd image will test the connectivity …   0         
centos/httpd                                                                     36        
e2eteam/httpd                                                                    0         
manasip/httpd                                                                    0         
publici/httpd                    httpd:latest                                    1         
patrickha/httpd-err                                                              0         
solsson/httpd-openidc            mod_auth_openidc on official httpd image, ve…   2         
futdryt/httpd                                                                    0         
amd64/httpd                      The Apache HTTP Server Project                  1         
signiant/httpd                   httpd (apache2) base container with a custom…   0  
```
4. Check the container on the machine
```bash
$ sudo docker ps
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker ps
[sudo] password for nitishkumar: 
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
02dca9c9d6db   httpd     "httpd-foreground"   8 seconds ago   Up 7 seconds   80/tcp    apache
```

5. Pull image from docker hub
```bash
$ sudo docker pull (image name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker pull httpd
Using default tag: latest
latest: Pulling from library/httpd
09f376ebb190: Pull complete 
dab55b4abfc3: Pull complete 
4f4fb700ef54: Pull complete 
1a6d0283f224: Pull complete 
1abf9110528c: Pull complete 
7bacb8f85f3a: Pull complete 
Digest: sha256:43c7661a3243c04b0955c81ac994ea13a1d8a1e53c15023a7b3cd5e8bb25de3c
Status: Downloaded newer image for httpd:latest
docker.io/library/httpd:latest
```

6. push/downloads image from docker hub
```bash
sudo docker push (image name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker pull httpd
Using default tag: latest
latest: Pulling from library/httpd
Digest: sha256:43c7661a3243c04b0955c81ac994ea13a1d8a1e53c15023a7b3cd5e8bb25de3c
Status: Image is up to date for httpd:latest
docker.io/library/httpd:latest
```
7. Create the container
```bash
$ sudo docker run -itd --name (container name) (Image name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker run -itd --name apache httpd
02dca9c9d6db28e5dc11f99e7297db8adf0f4f8074358ee9ddc8723409748cac
```

8. Start the container
```bash
$ sudo docker start (container name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker start apache
apache
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$
```

9. Stop the container
```bash
$ sudo docker stop (container name)
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ sudo docker stop apache
apache
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ 
```

10. How to enter in the container
```bash
$ sudo docker exec -it (container name) bash
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$  sudo docker exec -it apache bash 
root@02dca9c9d6db:/usr/local/apache2# ls
bin  build  cgi-bin  conf  error  htdocs  icons  include  logs	modules
root@02dca9c9d6db:/usr/local/apache2# 
```

11. Remove the container
```bash
$ sudo docker stop (container name)
```
```bash
$ sudo docker rm (container name)
```

12. Removes an image from the host machine.
```bash
$ sudo docker rmi (image name)
```

## Conclusion

* `Docker` is a powerful tool that has revolutionized the way we develop, deploy, and manage applications. By allowing developers to package applications and their dependencies into containers, `Docker` ensures that software runs consistently across different environments, from development to production. This eliminates many of the issues related to environment differences, making the development process more efficient and reliable.

* `Docker` simplifies the complexities of application deployment and management, making it an invaluable tool for modern software development. Its ability to create consistent environments, combined with the flexibility and efficiency of containers, makes Docker a cornerstone of DevOps practices and cloud-native development.

## Reference Link
* https://docs.docker.com/get-docker/

## Thank You!



 
  



