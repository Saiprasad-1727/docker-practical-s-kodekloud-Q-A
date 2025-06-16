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

      ocker images
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
