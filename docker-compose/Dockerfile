FROM alpine:latest
RUN apk update && apk add openjdk8 maven git && export PATH=${PATH}:${JAVA_HOME}/bin\
    && mkdir /opt/tomcat && wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.16/bin/apache-tomcat-10.0.16.tar.gz \
    && tar xvzf apache-tomcat-10.0.16.tar.gz --strip-components 1 --directory /opt/tomcat && rm -rf apache-tomcat-10.0.16.tar.gz \
    && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /opt/ && cd /opt/boxfuse-sample-java-war-hello && mvn package \
    && mv /boxfuse-sample-java-war-hello/target/*.war /opt/tomcat/webapps/hello.war && rm -rf /root/boxfuse-sample-java-war-hello
    && rm -rf /etc/apk/cache