Infracubator Assignments
Module:1 Docker
**Assignment 1:**
  Start an nginx container 
  => docker start nginx
  Port forward to local and check
  => docker run -p 80:80 –name ngnixContainer -d nginx
  Check logs
  => docker logs ngnixContainer
  Go inside the container
  => docker exec -it ngnixContainer /bin/bash
  Stop the container
  => docker stop ngnixContainer
  
**Assignment 2:**
Given that you have instructions to run the go-app ( in prerequisite ) 
Try to create a docker image out of it with the base image of `golang:latest`
  => 
Run a container with that image and do a curl request and make sure you are able to see the output. 
  => docker build -t goapp .
  => docker run -p 8081:8080 --name goappcontainer -d goapp
  => curl localhost:8081
Tag the docker image with v1. 
 => docker build -t goapp:v1 .
Run docker history, observe and understand the output. 
=> docker history goapp
Push the docker image to your docker hub. 
=> docker login -u singhanjali09
=> docker tag goapp singhanjali09/goapp
=> docker push singhanjali09/goapp
=> https://hub.docker.com/r/singhanjali09/goapp/tags

**Assignment 3:**

Note: - use proper names for images, containers.

