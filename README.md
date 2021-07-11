# DevOps
Course of Docker 

## PART 1 ##

* 1.1 Getting Started
  ```
    CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                     PORTS     NAMES
  0df1d65df0d9   nginx     "/docker-entrypoint.…"   29 seconds ago   Up 28 seconds              80/tcp    zealous_shaw
  126966cace6c   nginx     "/docker-entrypoint.…"   33 seconds ago   Exited (0) 6 seconds ago             mystifying_murdock
  93b8698ace39   nginx     "/docker-entrypoint.…"   35 seconds ago   Exited (0) 9 seconds ago             lucid_clarke
  ```
* 1.2 Clean up
 ```
  sudo docker ps -as
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES     SIZE

 sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    9873176a8ff5   3 weeks ago   72.7MB
 ```
Ps: The image of ubuntu is active because i was doing the rest of the part 1

* 1.3 Secret message
  ```
  step 1: sudo docker run -d -it --rm --name ubt devopsdockeruh/simple-web-service:ubuntu
  step 2: sudo docker exec -it ubt bash
  step 3: root@beb0cecad0df:/usr/src/app# tail -f ./text.log
  output : Secret message is: 'You can find the source code here: https://github.com/docker-hy'
                  2021-07-11 01:05:52 +0000 UTC
                  2021-07-11 01:05:54 +0000 UTC
                  2021-07-11 01:05:56 +0000 UTC
                  2021-07-11 01:05:58 +0000 UTC
                  2021-07-11 01:06:00 +0000 UTC
  ```
