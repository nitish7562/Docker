 # DOCKER DOCUMENTATION  

In this documentation we covers basics of `Docker` like setup, images, containers, networking, volumes, security, and advanced concepts for efficient containerization practices. 

![image](https://github.com/nitish7562/Docker/assets/110687449/b4201e99-f0f2-4bc5-844f-cc19c620ce5f)

<br>

# What is Docker?

* ```Docker``` is a platform for developing, shipping, and running applications. It uses containerization technology to package software and its dependencies into standardized units called containers. These containers can run on any machine, providing consistency across environments and simplifying the deployment process for developers and system administrators.
* ```Docker``` is an open source software program or a service to manage containers, it enables us to create, run and execute softwares virtually without installing any other operating system. In short docker is an ecosystem where we can create and run containers.
* ```Docker``` is a service which contains containers . it is derived for developers to develop, to run and execute applications. There is no need to install multiple operating systems. Also, docker is very flexible to work.

<br> 

# Why use Docker?

### Clean & Separate:

Run each app in its own space, like having separate rooms for different tasks. This keeps things organized and avoids conflicts.

### Move Anywhere:

Imagine our apps in portable boxes. Docker lets move our apps easily between different computers or cloud services, like packing boxes for a move.

### Runs Fast & Lean:

Containers are lightweight, like carrying a backpack instead of a suitcase. They start up quicker and use fewer resources.

### Always the Same:

 Build our app recipe once with Docker. No matter where i run it, I get the same results, avoiding setup headaches.

### Share and Colaborate:

Easily share our apps with others. They can run them without needing the same setup you have, like sharing a recipe with friends.

<br>

# Key Features of Docker:

### Containerization:

> Containerization in ```Docker``` is like packing our software and all its stuff into a virtual box, called a container. It keeps everything tidy and separate from the rest of our computer, so our programs run smoothly without messing with each other. It's like having a mini world for each application.

<br>

### Portability:

> `Docker` containers can run on any machine that supports Docker, Making it easy to deploy application across various platforms, from development to production. 

<br>

### Efficiency:

> `Docker` uses resourcess more eficiently than traditional virtual machines, as containers share the host system's kernel and do not require a full opearating system.

<br>

### Scalability:

> `Docker` makes it easy to scale applications by quickly deploying additional containers to handle increased demand.

<br>

### Modularity:

> `Docker` promotes a modular approach to software development, where applications are broken down into smaller. Manageable components that can be developed, tested, and deployed independently.

<br>

 ### Developer Productivity:

> With the help of `docker`, Developer can build, test, and deploy applications more quicly and reliablly, thanks to the ability to create lightweight, reproducible development enviroments.

<br>

# Docker Architecture

* Docker uses Client-Server architecture, which involves the 3 main components that are Docker Client, Docker Host, and Docker Registry. The Docker client communicates with the Docker daemon, which takes care of the building, running, and distributing the Docker containers. The Docker client and daemon can run on the same system or connect a client to a remote Docker daemon. They communicate using REST APIs, over UNIX sockets or a network interface.

<br>

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
<br>

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

<br>

# Installation of Docker

![image](https://i.ytimg.com/vi/TDLKQWsrSyk/maxresdefault.jpg)

<br>

Step 1. Check if the system up-to-date using following command :
```bash
$ sudo apt-get update
```
Step 2. After update system Now you can Install Docker using the following command:
```bash
$ sudo apt install docker.io
```
* You’ll then get a prompt asking you to choose between y/n - choose y
```bash
Do you want to continue? [Y/n] y
```
Step 3. Install all the dependency package using this command:
```bash
$  sudo snap install docker
```
Step 4. check the version of Docker :
```bash
$ docker version
```
Step 5. Verify Installation of docker :
* You can verify Docker is running correctly by running a test container.
```bash
$ sudo docker run hello-world
```
> After running its look like: 
```bash
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

  
   
    




 
  



