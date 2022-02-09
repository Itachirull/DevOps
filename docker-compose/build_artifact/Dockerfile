FROM alpine:latest
RUN apk update && apk add openjdk8 maven git && mkdir /opt/artifact \
    && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git && cd boxfuse-sample-java-war-hello && mvn package \
    && mv /boxfuse-sample-java-war-hello/target/*.war /opt/artifact/hello.war && rm -rf /root/boxfuse-sample-java-war-hello \
    && apk del git maven && rm -rf /etc/ssl* && rm -rf /etc/apk/cache \
CMD ping 127.0.0.1