##  Signup on Github and install Git locally on your machine.
##  Install Docker
##  From your home directory clone this repo.  Open a terminal window and do the following:


````
    $ cd
    $ rm -rf cuUnstructured
    $ git clone  https://github.com/marilynwaldman/cuUnstructured.git && rm -rf cuUnstructured/.git

````




##  From the terminal window pull the spark image. This takes a long time to download

````
    $ docker pull  jupyter/all-spark-notebook

```` 


##  From the terminal window run the image and start Jupyter.  Make sure you are in your $Home directory. 

````
    $ cd
    $ docker run  -it --rm -p 8888:8888 -v $HOME/cuUnstructured:/home/jovyan --name spark jupyter/all-spark-notebook

```` 
#### It should look like this.  Copy (CNTL-C ) the token

![Screenshot](token.png)


##  Go to localhost:8888

![Screenshot](localhost.png) 

##  Paste your token into the box

![Screenshot](copypastetoken.png) 

##  Jupyter notebooks should appear.

![Screenshot](sparknotebook.png) 





