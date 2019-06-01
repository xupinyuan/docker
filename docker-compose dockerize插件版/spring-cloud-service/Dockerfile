FROM openjdk:8-jdk-alpine

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

COPY spring-cloud-service-1.0.0-SNAPSHOT.jar app.jar

ENTRYPOINT ["dockerize", "-timeout", "5m", "-wait", "http://192.168.1.5:8888/application/dev/master", "java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "app.jar"]
