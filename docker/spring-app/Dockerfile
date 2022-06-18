FROM timbru31/java-node
RUN apt update && apt upgrade -y
RUN apt install -y git maven
RUN git clone https://github.com/dobrosi/vaadin-microservices-demo.git
RUN cd /vaadin-microservices-demo
WORKDIR /vaadin-microservices-demo
RUN mvn --quiet package -Pproduction
COPY discovery-server/target/*SNAPSHOT.jar /discovery-server.jar
COPY config-server/target/*SNAPSHOT.jar /config-server.jar
COPY biz-application/target/*SNAPSHOT.jar /biz-application.jar
COPY news-application/target/*SNAPSHOT.jar /news-application.jar
COPY website-application/target/*SNAPSHOT.jar /website-application.jar
COPY proxy-server/target/*SNAPSHOT.jar /proxy-server.jar
COPY admin-application/target/*SNAPSHOT.jar /admin-application.jar