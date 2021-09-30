#FROM openjdk:8-jre-alpine
#FROM alpine:latest
#RUN apk add openjdk8


FROM alpine:latest as build

ADD https://download.java.net/java/GA/jdk17/0d483333a00540d886896bac774ff48b/35/GPL/openjdk-17_linux-x64_bin.tar.gz /opt/jdk/
RUN tar -xzvf /opt/jdk/openjdk-17_linux-x64_bin.tar.gz -C /opt/jdk/

RUN ["/opt/jdk/jdk-17/bin/jlink", "--compress=2", \
     "--module-path", "/opt/jdk/jdk-14/jmods/", \
     "--add-modules", "java.base", \
     "--output", "/jlinked"]


FROM alpine:latest
COPY --from=build /jlinked /opt/jdk/




WORKDIR /tmp
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.53/bin/apache-tomcat-9.0.53.tar.gz /tmp
RUN  tar -zxvf apache-tomcat-9.0.53.tar.gz
RUN cp -Rv /tmp/apache-tomcat-9.0.53 /usr/local/tomcat
#RUN cd /usr/local/tomcat/webapps && ls -la
EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]