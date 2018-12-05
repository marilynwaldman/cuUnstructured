##  Install Github and git
##  Install Docker
##  Get this repo


````
    $ rm -rf cuUnstructured
    $ git clone  https://github.com/marilynwaldman/cuUnstructured.git && rm -rf cuUnstructured/.git

        or
    Download git@github.com:marilynwaldman/cuUnstructured.git
    $  mkdir cuUnstructured
    $  cd cuUnstructured
````




##  pull the spark image and start a Spark Notebook - this takes a long time to download

````
    docker pull  jupyter/all-spark-notebook

```` 


##  run the  image and start a Spark Notebook - this takes a long time to download

````
    docker run  -it --rm -p 8888:8888 -v /Users/marilynwaldman/cuUnstructured:/home/jovyan --name spark jupyter/all-spark-notebook

```` 


##  go to localhost:8888 and put in the token  




