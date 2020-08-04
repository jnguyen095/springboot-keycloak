# springboot-keycloak

1. Spring boot & Keycloak integration
2. Deploy with docker
- Add Dockerfile with: 
 ```
 FROM openjdk:8-jdk-alpine
 RUN addgroup -S spring && adduser -S spring -G spring
 USER spring:spring
 ARG JAR_FILE=target/*.jar
 COPY ${JAR_FILE} app.jar
 ENTRYPOINT ["java","-jar","/app.jar"]
 ```
 - Build and run
 ```
 $ docker build -t springio/springboot-keycloak-docker .
 $ docker run -p 8080:8080 springio/springboot-keycloak-docker
 ``` 
 - Push to docker repositoty
 ```
 1. $> docker image -a --> to see IMAGE ID
 2. $> docker tag <IMAGE ID> nguyennhukhangvn/springbook-keycloak
 3. $> docker push nguyennhukhangvn/springbook-keycloak
 ```
