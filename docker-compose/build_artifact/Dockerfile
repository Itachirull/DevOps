FROM alpine:latest
RUN apk update && apk add openjdk8 maven git && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git && cd boxfuse-sample-java-war-hello && mvn package \
    && mv /boxfuse-sample-java-war-hello/target/*.war /opt/hello.war