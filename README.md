# DevOps
Course of Docker 

## PART 1 ##

### 1.1 Getting Started
  ```
    CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                     PORTS     NAMES
  0df1d65df0d9   nginx     "/docker-entrypoint.…"   29 seconds ago   Up 28 seconds              80/tcp    zealous_shaw
  126966cace6c   nginx     "/docker-entrypoint.…"   33 seconds ago   Exited (0) 6 seconds ago             mystifying_murdock
  93b8698ace39   nginx     "/docker-entrypoint.…"   35 seconds ago   Exited (0) 9 seconds ago             lucid_clarke
  ```
### 1.2 Clean up
 ```
  sudo docker ps -as
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES     SIZE

 sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    9873176a8ff5   3 weeks ago   72.7MB
 ```
Ps: The image of ubuntu is active because i was doing the rest of the part 1

### 1.3 Secret message
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
 ### 1.4 Missing dependencies

  ```
  step 1: sudo docker run -d -it --rm --name ubt  ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
  step 2: apt update &&  apt upgrade
  step 3: apt install curl
  step 4: sudo docker attach ubt
  step 5: helsinki.fi
          Searching..
          <!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
          <html><head>
          <title>301 Moved Permanently</title>
          </head><body>
          <h1>Moved Permanently</h1>
          <p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
          </body></html>
          gabriel@gabriel-Aspir
  
  ```
   About the smart answer for this question, i just imagine that exist a way of the install all dependencies in image before execute a container.
   
  ### 1.5 Sizes of Images

  ```
  step 1: sudo docker pull devopsdocheruh/simple-web-service:alpine
  step 2: sudo docker images
          REPOSITORY                          TAG       IMAGE ID       CREATED        SIZE
          ubuntu                              latest    9873176a8ff5   3 weeks ago    72.7MB
          fav_distro                          bionic    7d0d8fa37224   3 weeks ago    63.1MB
          ubuntu                              18.04     7d0d8fa37224   3 weeks ago    63.1MB
          devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   4 months ago   83MB
          devopsdockeruh/simple-web-service   alpine    fd312adc88e0   4 months ago   15.7MB
  step 3: sudo docker tag devopsdockeruh/simple-web-service:alpine wevalp:alpine
  step 4: sudo docker container run -d -it --name web  wevalp:alpine
  step 5: sudo docker exec -it web sh
  step 6: /usr/src/app # cat text.log

          2021-07-12 14:44:53 +0000 UTC
          2021-07-12 14:44:55 +0000 UTC
          2021-07-12 14:44:57 +0000 UTC
          2021-07-12 14:44:59 +0000 UTC
          2021-07-12 14:45:01 +0000 UTC
          Secret message is: 'You can find the source code here: https://github.com/docker-hy'

   ```
   ### 1.6 Hello Docker Hub
   
   ```
    step 1: sudo docker run -it devopsdockeruh/pull_exercise
    step 2: Enter in ther docker hub web site, and search for the devospdockeruh/pull_exercise
    step 3: Give me the password: basics
            You found the correct password. Secret message is:
            "This is the secret message"
   ```
   ### 1.7 Two line Dockerfile
   
   ```
    step 1: Created a Dockerfile with two lines, using the FROM and CMD statement, the file is in the path part1/1.7
    step 2: sudo docker build . -t web-serve
    step 3: sudo docker run web-serve
    
   ```
   
