Docker basic commands

## Question 1.

What is the version of Docker Server Engine running on the Host?

      docker -v
      Docker version 25.0.5, build d260a54c81efcc3f00fe67dee78c94b16c2f8692

## Question 2.

How many containers are running on this host?

      docker ps

## Question 3.

How many images are available on this host?

      docker images
      REPOSITORY                      TAG       IMAGE ID       CREATED         SIZE
      alpine                          latest    91ef0af61f39   9 months ago    7.79MB
      nginx                           alpine    c7b4f26a7d93   10 months ago   43.2MB
      nginx                           latest    39286ab8a5e1   10 months ago   188MB
      postgres                        latest    b781f3a53e61   10 months ago   432MB
      ubuntu                          latest    edbfe74c41f8   10 months ago   78MB
      redis                           latest    590b81f2fea1   10 months ago   117MB
      mysql                           latest    a82a8f162e18   10 months ago   586MB
      kodekloud/simple-webapp-mysql   latest    129dd9f67367   6 years ago     96.6MB
      kodekloud/simple-webapp         latest    c6e3cd9aae36   6 years ago     84.8MB

## Question 4.

Run a container using the redis image

NOTE: Run the container in detached mode if you don't want the container to take over your current terminal. This allows your terminal to remain free for other commands, or you can open a new terminal to run the command.
      
      docker run -d redis
      04676ede7d87361acdc11bfeaaf21e6801fbd2ac96b1aad282bb29d56c2c695f

## Question 5.

Stop the container you just created

      docker stop 04676ede7d87361acdc11bfeaaf21e6801fbd2ac96b1aad282bb29d56c2c695f
      04676ede7d87361acdc11bfeaaf21e6801fbd2ac96b1aad282bb29d56c2c695

## Question 6.

How many containers are PRESENT on the host now? Including both Running and Not Running ones

      docker ps -a
      CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS                          PORTS     NAMES
      3e7d0f793246   alpine         "/bin/sh"                About a minute ago   Exited (0) About a minute ago             youthful_feistel
      39d29a17439d   alpine         "sleep 1000"             About a minute ago   Up About a minute                         trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   About a minute ago   Up About a minute               80/tcp    nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   About a minute ago   Up About a minute               80/tcp    nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             About a minute ago   Up About a minute                         awesome_northcut
      04676ede7d87   redis          "docker-entrypoint.s…"   2 minutes ago        Exited (0) 2 minutes ago                  optimistic_satoshi

## Question 7.

What is the name of the container created using the ubuntu image?

      docker ps 
      CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS     NAMES
      39d29a17439d   alpine         "sleep 1000"             3 minutes ago   Up 3 minutes             trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   80/tcp    nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   80/tcp    nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             3 minutes ago   Up 3 minutes             awesome_northcut

## Question 8.

What is the ID of the container that uses the alpine image and is not running?

      3e7d0f793246

      docker ps -a
      CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS                     PORTS     NAMES
      3e7d0f793246   alpine         "/bin/sh"                4 minutes ago   Exited (0) 4 minutes ago             youthful_feistel
      39d29a17439d   alpine         "sleep 1000"             5 minutes ago   Up 4 minutes                         trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes               80/tcp    nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes               80/tcp    nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             5 minutes ago   Up 5 minutes                         awesome_northcut
      04676ede7d87   redis          "docker-entrypoint.s…"   6 minutes ago   Exited (0) 5 minutes ago             optimistic_satoshi

## Question 9.

What is the state of the stopped alpine container?

      Exited (0) 4 minutes ago

      docker ps -a
      CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS                     PORTS     NAMES
      3e7d0f793246   alpine         "/bin/sh"                4 minutes ago   Exited (0) 4 minutes ago             youthful_feistel
      39d29a17439d   alpine         "sleep 1000"             5 minutes ago   Up 4 minutes                         trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes               80/tcp    nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes               80/tcp    nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             5 minutes ago   Up 5 minutes                         awesome_northcut
      04676ede7d87   redis          "docker-entrypoint.s…"   6 minutes ago   Exited (0) 5 minutes ago             optimistic_satoshi

## Question 10.

Delete all containers from the Docker Host. Both Running and Not Running ones. Remember you may have to stop containers before deleting them.

      docker ps   
      CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS     NAMES
      39d29a17439d   alpine         "sleep 1000"             7 minutes ago   Up 7 minutes             trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes   80/tcp    nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes   80/tcp    nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             7 minutes ago   Up 7 minutes             awesome_northcut

      docker ps -a                                                     
      CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS                       PORTS     NAMES
      3e7d0f793246   alpine         "/bin/sh"                8 minutes ago    Exited (0) 8 minutes ago               youthful_feistel
      39d29a17439d   alpine         "sleep 1000"             8 minutes ago    Exited (137) 6 seconds ago             trusting_ganguly
      cae0cdd929aa   nginx:alpine   "/docker-entrypoint.…"   8 minutes ago    Exited (0) 16 seconds ago              nginx-2
      780d57e51312   nginx:alpine   "/docker-entrypoint.…"   8 minutes ago    Exited (0) 16 seconds ago              nginx-1
      67dc1d58d1a3   ubuntu         "sleep 1000"             8 minutes ago    Exited (137) 7 seconds ago             awesome_northcut
      04676ede7d87   redis          "docker-entrypoint.s…"   10 minutes ago   Exited (0) 9 minutes ago               optimistic_satoshi
 
      docker rm  3e7d0f793246 39d29a17439d cae0cdd929aa 780d57e51312 67dc1d58d1a3 04676ede7d87
      3e7d0f793246
      39d29a17439d
      cae0cdd929aa
      780d57e51312
      67dc1d58d1a3
      04676ede7d87

## Question 11.

Delete the ubuntu Image.

      docker rmi ubuntu                                                                       
      Untagged: ubuntu:latest
      Untagged: ubuntu@sha256:8a37d68f4f73ebf3d4efafbcf66379bf3728902a8038616808f04e34a9ab63ee
      Deleted: sha256:edbfe74c41f8a3501ce542e137cf28ea04dd03e6df8c9d66519b6ad761c2598a
      Deleted: sha256:f36fd4bb7334b7ae3321e3229d103c4a3e7c10a263379cc6a058b977edfb46de


## Question 12.

You are required to pull a docker image which will be used to run a container later. Pull the image nginx:1.14-alpine
Only pull the image, do not create a container.

      docker pull nginx:1.14-alpine
      1.14-alpine: Pulling from library/nginx
      bdf0201b3a05: Pull complete 
      3d0a573c81ed: Pull complete 
      8129faeb2eb6: Pull complete 
      3dc99f571daf: Pull complete 
      Digest: sha256:485b610fefec7ff6c463ced9623314a04ed67e3945b9c08d7e53a47f6d108dc7
      Status: Downloaded newer image for nginx:1.14-alpine
      docker.io/library/nginx:1.14-alpine


## Question 13.

Run a container with the nginx:1.14-alpine image and name it webapp

      docker run -d --name webapp nginx:1.14-alpine
      ed596390f7eae96570a4d6f9f3215ae87ab89ac2dee4ae1fa1f3c4631035ca92

## Question 13.

Cleanup: Delete all images on the host, Remove containers as necessary

      docker system prune -a

      docker images         
      REPOSITORY   TAG       IMAGE ID   CREATED   SIZE




