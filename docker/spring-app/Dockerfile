FROM timbru31/java-node:jdk
RUN apt update && apt upgrade -y
RUN apt install -y git maven wget
RUN git clone https://github.com/dobrosi/vaadin-microservices-demo.git
RUN cd /vaadin-microservices-demo
WORKDIR /vaadin-microservices-demo
RUN mvn package -DskipTests
RUN cp discovery-server/target/*SNAPSHOT.jar /discovery-server.jar
RUN cp config-server/target/*SNAPSHOT.jar /config-server.jar
RUN cp biz-application/target/*SNAPSHOT.jar /biz-application.jar
RUN cp news-application/target/*SNAPSHOT.jar /news-application.jar
RUN cp website-application/target/*SNAPSHOT.jar /website-application.jar
RUN cp proxy-server/target/*SNAPSHOT.jar /proxy-server.jar
RUN cp admin-application/target/*SNAPSHOT.jar /admin-application.jar