FROM ubuntu:20.04
ENV TZ=Europe/Mocsow \
    DEBIAN_FRONTEND=noninteractive
RUN  ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
     && apt update && apt -y install default-jdk git wget maven && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git && mkdir /opt/tomcat\
     &&  wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.58/bin/apache-tomcat-9.0.58.tar.gz && tar -xf apache-tomcat-9.0.58.tar.gz -C /opt/tomcat \
     && cd boxfuse-sample-java-war-hello &&  mvn package && mv /boxfuse-sample-java-war-hello/target/*.war /opt/tomcat/webapps/hello.war && rm -rf /boxfuse  \
     && apt clean && rm -rf /etc/apt/cache
EXPOSE 8080
WORKDIR /opt/tomcat/bin
CMD ["sh","catalina.sh","run"]
