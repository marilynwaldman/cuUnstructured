#Get this repo


1.  Get this repository. Either clone the repo or download it into a folder named cuSparkDocker

````
    $ git clone git@github.com:marilynwaldman/cuSparkDocker.git

        or
    Download it@github.com:marilynwaldman/cuSparkDocker.git
    $  mkdir cuSparkDocker
    $  cd cuSparkDocker
````

# cuSparkDocker

Project Jupyter and Docker have many out-of-the-box notebooks built for students in Data Science.  This is a quick start for obtaining these ready made notebooks.

Some of the choices are located at:

https://github.com/jupyter/docker-stacks

We will demonstrate how to run the all-spark-notebook.

These instruction are for MAC only, but can easily be ported to WINDOWS.

You will need the following installed to run Spark Notebooks on Docker:

1.  VirtualBox
2.  Docker and docker-machine.

## Getting Started

###Install VirtualBox

Go to the VirtualBox download page and get select the correct download for your machine type.  

[VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)

Once downloaded double-click on the .dmg file and follow the instructions.  You should get a screen stating the install was successful.

You must be running the latest VirtualBox for the docker images to run on.

##Install Docker and Docker-Machine

If this is your first time using Docker or any of the Jupyter projects, do the following to get started.  We will be installing Docker on a Virtual Machine as described here:  https://docs.docker.com/machine/get-started/.  It is recommended that if you have an old version of Docker, you update using docker-machine.

Please note the following restrictions on macs:  Docker for Mac requires macOS 10.10.3 Yosemite or newer running on a 2010 or newer Mac, with Intel’s hardware support for MMU virtualization. 

1. [Install Docker] (https://docs.docker.com/docker-for-mac/)
     From this download site select the "Stable Build" option 
2.  Once the dmg is downloaded, double-click on it and follow the instructions.  You should get a confirmation that install was successful.
3. Open a terminal window on your mac.
4. Run the following:

```
    $ docker-machine ls
    NAME   ACTIVE   DRIVER   STATE   URL   SWARM   DOCKER   ERRORS
```
5.  If you do not see this, start the docker-machine:

````
    $ docker-machine start 
    $ docker-machine ls
````
6   Create a virtual machine to run on.

````
    $ docker-machine create --driver virtualbox default


    You will see the following:

    Running pre-create checks...
    Creating machine...
    (staging) Copying /Users/ripley/.docker/machine/cache/boot2docker.iso to      

   ....

````
7.  If the script hangs at the create SSH step, you may have to reboot your machine and try steps 3-6 again.
8.  Verify you machine is running:
````
    $ docker-machine ls
    NAME      ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER   ERRORS
    default   *        virtualbox   Running   tcp://192.168.99.187:2376
````
9.  You need to connect your terminal to docker's environment:

````
   $ docker-machine env default

    export DOCKER_TLS_VERIFY="1"
    export DOCKER_HOST="tcp://172.16.62.130:2376"
    export DOCKER_CERT_PATH="/Users/<yourusername>/.docker/machine/machines/default"
    export DOCKER_MACHINE_NAME="default"
    # Run this command to configure your shell:
    # eval "$(docker-machine env default)"
````
10.  # Run this command to configure your shell:
````
      $eval "$(docker-machine env default)"
````
11.  You will need the ip address of this machine to start the Jupyter notebook.
````
    $ docker-machine ip default
     192.168.99.100  (this may be different on your machine.)
````


##  Now that Docker is running on VirtualBox we can pull an image and start a Spark Notebook

1.  You can find a list of available notebooks at this github account.  We will choose the all-spark-notebook.  It takes a while to download this, so try to do this before class.

    https://github.com/jupyter/docker-stacks

2. Follow the instructions for all-spark-notebook.  This will pull the docker image, start the container, and start the Jupyter notebook.

````
    $docker run -d -p 8888:8888 jupyter/all-spark-notebook

````    

3.  When this completes open a browser window and point to 
````
    http://192.168.99.100:8888  Note you need to use the ip address from #11 above.

````

  Jupyter should appear.

##  Upload the assignment and data files for class. These are in the cuSparkDocker directory.

1.  On the Jupyter notebook select "upload" at the top.
2.  You will be directed to your local file system.  Go to the cuSparkDocker folder and select all files that ends in ipynb.
    You can upload these one at a time or select them all at once.
3.  Follow the prompts and upload them.
4.  Upload all files that end in .txt.  These are data files we will use.



