#依赖环境
FROM openjdk:8-jdk-alpine
#设置变量
ENV DOCKERIZE_VERSION v0.6.1
#下载插件
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz
#拷贝jar文件
COPY spring-cloud-admin-1.0.0-SNAPSHOT.jar app.jar
#执行命令  -timeout 超时多久运行jar   -wait 等待http地址访问成功运行jar   wait 也可以是tcp://xxxx 
ENTRYPOINT ["dockerize", "-timeout", "5m", "-wait", "http://192.168.1.5:8888/application/dev/master", "java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "app.jar"]
