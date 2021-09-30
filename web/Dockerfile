#FROM openjdk:8-jre-alpine
#FROM alpine:latest
#RUN apk add openjdk8



#FROM alpine:latest as build
#WORKDIR /opt/jdk
#ADD https://download.java.net/java/GA/jdk17/0d483333a00540d886896bac774ff48b/35/GPL/openjdk-17_linux-x64_bin.tar.gz /opt/jdk
#RUN ls -la

#RUN tar -xzvf openjdk-17_linux-x64_bin.tar.gz
#RUN ls -la
#WORKDIR /opt/jdk/jdk-17/bin
#RUN ls -la
#RUN ["jlink"]




FROM alpine:latest
#COPY --from=build /jlinked /opt/jdk/
RUN apk add openjdk8
WORKDIR /opt/jdk/
RUN ls -la

#WORKDIR /tmp
#ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.53/bin/apache-tomcat-9.0.53.tar.gz /tmp
#RUN  tar -zxvf apache-tomcat-9.0.53.tar.gz
#RUN cp -Rv /tmp/apache-tomcat-9.0.53 /usr/local/tomcat

EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]