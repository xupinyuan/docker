FROM openjdk:8-jdk-alpine
COPY spring-cloud-config-1.0.0-SNAPSHOT.jar app.jar
RUN sh -c 'touch app.jar'ENV JAVA_OPTS=""#Djava.security.egd
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","-Xmx1024m","-Xms1024m","app.jar"]