# Docker Tutorial:  Hello World

   - docker run
   - docker images
   - docker ps, docker ps -a
    
[Docker Tutorial](https://docs.docker.com/get-started/) 

## Docker concepts
Docker is a platform for developers and sysadmins to develop, deploy, and run applications with containers. 
The use of Linux containers to deploy applications is called containerization. 

## First see if Docker is installed correctly

```bash
   docker --version
```

````
Marilyns-MacBook-Pro:~ marilynwaldman$ docker --version
Docker version 18.09.0, build 4d60db4
Marilyns-MacBook-Pro:~ marilynwaldman$ 
````

## First see if Docker is installed correctly

```bash
   docker --version
```

````
Marilyns-MacBook-Pro:~ marilynwaldman$ docker --version
Docker version 18.09.0, build 4d60db4
Marilyns-MacBook-Pro:~ marilynwaldman$ 
````
    
## Images and containers
   A container is launched by running an image. An image is an executable package that includes everything needed to run an 
   application--the code, a runtime, libraries, environment variables, and 
   configuration files.
   
   A container is a runtime instance of an image--what the image becomes 
   in memory when executed (that is, an image with state, or a user process). You can see a list of your running containers with the command, docker ps, just as you would in Linux.
   
## Let's pull and run Hello-World

```bash
  docker run hello-world
```

This command pulls a docker image and runs it.

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
d1725b59e92d: Pull complete 
Digest: sha256:0add3ace90ecb4adbf7777e9aacf18357296e799f81cabc9fde470971e499788
Status: Downloaded newer image for hello-world:latest

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

Marilyns-MacBook-Pro:~ marilynwaldman$ 


````

## List the hello-world image that was downloaded to your machine:

```bash
   docker images ls
```

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              4ab4c602aa5e        3 months ago        1.84kB
Marilyns-MacBook-Pro:~ marilynwaldman$ 

````

## Find all running containers on your machine.
Notice that hello world is not running.  It started, printed 'hello world', then
stopped.

```bash
  docker ps
```

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
Marilyns-MacBook-Pro:~ marilynwaldman$ 
````

## To see all containers, use the -a (or --all) flag

```bash
   docker ps -a

```

````aidl
 docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                     PORTS               NAMES
7ab73d0dea56        hello-world         "/hello"            6 minutes ago       Exited (0) 6 minutes ago                       wizardly_khayyam
````

Notice the 'status' is 'exited'.  This means the contain.er ran and has terminated.
The system also gave the container the funny name 'quirky_gagarin.' We will learn
to give meaningful names in a later lesson.

## Run hello-world again, followed by ps -a.

```bash
   docker run hello-world;
   docker ps -a
```

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
2ace4fb3e510        hello-world         "/hello"            12 seconds ago      Exited (0) 12 seconds ago                       blissful_noether
7ab73d0dea56        hello-world         "/hello"            34 minutes ago      Exited (0) 34 minutes ago                       wizardly_khayyam
````

Notice we have two containers.  One for each time we ran hello-world.

We have no running containers however:

```bash
  docker ps
```

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
Marilyns-MacBook-Pro:~ marilynwaldman$ 
````

Check the status of the containers:

```bash
   docker ps -a
```

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
2ace4fb3e510        hello-world         "/hello"            3 minutes ago       Exited (0) 3 minutes ago                        blissful_noether
7ab73d0dea56        hello-world         "/hello"            38 minutes ago      Exited (0) 38 minutes ago                       wizardly_khayyam
Marilyns-MacBook-Pro:~ marilynwaldman$ 

````

Check what images are on your machine.

```bash
   docker images

```

```
Marilyns-MacBook-Pro:~ marilynwaldman$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              4ab4c602aa5e        3 months ago        1.84kB
Marilyns-MacBook-Pro:~ marilynwaldman$
```

### Cleanup

   - Remove containers one at a time
   
```bash
  docker ps -a
  docker rm 2ace4fb3e510
  docker rm $CONTAINER_ID
```   

```aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
2ace4fb3e510        hello-world         "/hello"            7 minutes ago       Exited (0) 7 minutes ago                        blissful_noether
7ab73d0dea56        hello-world         "/hello"            42 minutes ago      Exited (0) 42 minutes ago                       wizardly_khayyam
Marilyns-MacBook-Pro:~ marilynwaldman$ docker rm 2ace4fb3e510
2ace4fb3e510
Marilyns-MacBook-Pro:~ marilynwaldman$ docker rm 7ab73d0dea56
7ab73d0dea56
Marilyns-MacBook-Pro:~ marilynwaldman$ 
```

   - Remove the hello-world image
   
```bash
   docker -images -a
   docker rmi hello-world
```  

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker images -a
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              4ab4c602aa5e        3 months ago        1.84kB
Marilyns-MacBook-Pro:~ marilynwaldman$ docker rmi hello-world
Untagged: hello-world:latest
Untagged: hello-world@sha256:0add3ace90ecb4adbf7777e9aacf18357296e799f81cabc9fde470971e499788
Deleted: sha256:4ab4c602aa5eed5528a6620ff18a1dc4faef0e1ab3a5eddeddb410714478c67f
Deleted: sha256:428c97da766c4c13b19088a471de6b622b038f3ae8efa10ec5a37d6d31a2df0b
Marilyns-MacBook-Pro:~ marilynwaldman$ 
```` 

   - verify
```bash
   docker ps -a
   docker images
```  

````aidl
Marilyns-MacBook-Pro:~ marilynwaldman$ docker images -a
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
Marilyns-MacBook-Pro:~ marilynwaldman$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
Marilyns-MacBook-Pro:~ marilynwaldman$ 
```` 
   




