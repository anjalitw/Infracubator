Infracubator Assignments

**Module:1 Docker**

**Assignment 1:**
  1. Start an nginx container
  
    => docker start nginx
  3. Port forward to local and check

    => docker run -p 80:80 –name ngnixContainer -d nginx
  5. Check logs

    => docker logs ngnixContainer
  7. Go inside the container

    => docker exec -it ngnixContainer /bin/bash
  9. Stop the container

    => docker stop ngnixContainer
  
**Assignment 2:**
  1. Given that you have instructions to run the go-app ( in prerequisite )
  2. Try to create a docker image out of it with the base image of `golang:latest`
     
     => https://github.com/anjalitw/Infracubator/blob/main/go-app/Dockerfile
  4. Run a container with that image and do a curl request and make sure you are able to see the output. 

    => docker build -t goapp .
    => docker run -p 8081:8080 --name goappcontainer -d goapp
    => curl localhost:8081
  6. Tag the docker image with v1

    => docker build -t goapp:v1 .
  8. Run docker history, observe and understand the output.

    => docker history goapp
  10. Push the docker image to your docker hub.
     
    => docker login -u singhanjali09
    => docker tag goapp singhanjali09/goapp
    => docker push singhanjali09/goapp
   https://hub.docker.com/r/singhanjali09/goapp/tags

**Assignment 3:**
  Create multi-stage build and run dockerfile for go application
  
      stage 1: build
      stage 2: Run
https://github.com/anjalitw/Infracubator/blob/main/go-app/Dockerfile.multistage

**Assignment 4:**

    docker volume create my_volume  
    docker run -it -v my_volume:/volumeFolder --name my-container-01 ubuntu
    cd volumeFolder/
    echo "Hello" > hello.txt
    exit
    docker run -it -v my_volume:/volumeFolder --name my-container-02 ubuntu
    cd volumeFolder/
    ls -lrt
    exit

**Assignment 5:**

    docker run --name redisContainer -d redis 
    docker inspect redisContainer
    docker build -t goappnewimage .
    docker run -e REDIS_HOST=172.17.0.1 --name goappcontainer -d goappnewimage

**Assignment 6:**

    docker network create --driver bridge my_network
    docker run -it --network=my_network -d redis
    docker run -e REDIS_HOST=goappcontainer -d goappnewimage


**Assignment 7:**

  https://github.com/anjalitw/Infracubator/blob/main/go-app/docker-compose.yml
      
