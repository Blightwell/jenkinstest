django-ribbit
=============

Ribbit - A Twitter Clone made using Django

A live demo of the app can be found at http://vast-earth-7154.herokuapp.com/

***

To set the application locally, first clone the repo

```  
https://gitlab.com/Choapinus/t1_arqsist.git
(original: git clone https://github.com/gnarula/django-ribbit.git)
```

Build the image with docker

```
docker build -t my_image_name .
```
  
With the image created, start the container and bind the ports

```
docker run -d -p 8080:8080 --name my_container_name my_image_name
```