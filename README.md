# Docker_Start_Up

## Installing

1.Docker Documentation

  https://docs.docker.com/

2.Get Docker CE for Ubuntu

  https://docs.docker.com/install/linux/docker-ce/ubuntu/

3.Post-installation steps for Linux

  https://docs.docker.com/install/linux/linux-postinstall/ 

4.User Guide 

  https://docs.docker.com/get-started/
  

## Ops with Container

1.Define a container with Dockerfile, requirements.txt & \_\_coding files\_\_

2.Build the app
    
    docker build --tag=__tagname__ .
    
    docker image ls
    
3.Run the app

  mapping your machine’s port 4000 to the container’s published port 80 using -p

    docker run -p 4000:80 __tagname__
    
    curl http://localhost:4000
    
  run the app in the background
    
    docker run -d -p 4000:80 __tagname__
    
    docker container ls
    
    docker container stop __CONTAINER ID__
    
 4.Share the image
 
    docker login
    
    docker tag image username/repository:tag
    
    docker push username/repository:tag
    
    docker run -p 4000:80 username/repository:tag
    
  5.stop and remove containers
    
    docker container rm __CONTAINER ID__
    
    docker container rm -f __CONTAINER ID__
    
    docker stop $(docker ps -q)
    
    docker rm $(docker ps -aq)
    
    docker stop $(docker ps -q) & docker rm $(docker ps -aq)
  
## Ops with Services

  1.Create .yml file
  
  2.Run your new load-balanced app
      
      docker swarm init
      
      docker stack deploy -c __.yml __app_name__
      
      docker service ls
      
      docker stack services __app_name__
      
      docker service ps __task_name__
      
      docker container ls -q
      
      docker stack ps
   
   3.Scale the app, change the .yml file
   
      docker stack deploy -c __.yml __app_name__
      
   4.Take down the app and the swarm
   
      docker stack rm __app_name__
      
      docker swarm leave --force
