#依赖环境
FROM tomcat:8
#设置工作目录
WORKDIR /usr/local/tomcat
#拷贝jar文件
COPY hc_depot.war ./webapps
RUN chmod 777 ./bin/*.sh 
CMD ./bin/catalina.sh run