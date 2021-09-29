FROM ubuntu:20.04
RUN apt update && apt upgrade -y
RUN apt install default-jdk -y
RUN apt install maven -y
RUN apt install git -y
WORKDIR /var/boxfuse_src
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /var/boxfuse_src/boxfuse-sample-java-war-hello
RUN mvn package
#WORKDIR /var/boxfuse_src/boxfuse-sample-java-war-hello/target
CMD ["mvn","package"]