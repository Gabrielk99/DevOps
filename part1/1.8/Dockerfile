FROM ubuntu:18.04

WORKDIR /usr/src/app

COPY comand.sh .

RUN chmod +x comand.sh
RUN apt update
RUN yes | apt upgrade
RUN yes | apt install curl 

CMD ./comand.sh