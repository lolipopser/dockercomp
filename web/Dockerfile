#FROM alpine
#RUN wget -O /tmp/tomcat.tar.gz https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.53/bin/apache-tomcat-9.0.53.tar.gz
#RUN apk add openjdk11
FROM openjdk:8u302-jre-slim-bullseye
WORKDIR /tmp
RUN  tar -zxvf tomcat.tar.gz
RUN cp -Rv /tmp/apache-tomcat-9.0.53 /usr/local/tomcat
RUN cd /usr/local/tomcat/webapps && ls -la
EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]