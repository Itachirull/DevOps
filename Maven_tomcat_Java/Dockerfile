FROM ubuntu:20.04
ENV TZ=Europe/Mocsow \
    DEBIAN_FRONTEND=noninteractive
RUN  ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
     && apt update && apt -y install default-jdk tomcat9 git maven && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git \
     && cd boxfuse-sample-java-war-hello &&  mvn package && mv target/*war /usr/lib/tomcat/webapps/ && rm -rf /boxfuse && apt clean && rm -rf /etc/apt/cache
EXPOSE 8080
WORKDIR /usr/lib/tomcat9/bin
CMD ["sh","catalina.sh","run"]
