##  Install Github and git
##  Install Docker
##  From your home directory get this repo


````
    $ cd
    $ rm -rf cuUnstructured
    $ git clone  https://github.com/marilynwaldman/cuUnstructured.git && rm -rf cuUnstructured/.git

````




##  Pull the spark image and start a Spark Notebook - this takes a long time to download

````
    docker pull  jupyter/all-spark-notebook

```` 


##  Run the image and start Jupyter - this takes a long time to download

````
    docker run  -it --rm -p 8888:8888 -v $HOME/cuUnstructured:/home/jovyan --name spark jupyter/all-spark-notebook

```` 
#### It should look like this - copy (CNTL-C ) the token

![Screenshot](token.png)


##  Go to localhost:8888

![Screenshot](localhost.png) 

##  Paste your token into the box

![Screenshot](copypastetoken.png) 

##  Jupyter notebooks should appear.

![Screenshot](sparknotebook.png) 





