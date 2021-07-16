FROM openjdk:8

COPY mvnw.sh .

COPY . .

RUN ./mvnw.sh package

EXPOSE 8080

CMD [ "java", "-jar", "./target/docker-example-1.1.3.jar" ]
