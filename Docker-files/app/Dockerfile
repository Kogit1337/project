FROM openjdk:11 AS BUILD_IMG
LABEL "Project"="mibops"
LABEL "MAINTAINER"="MichBor"

RUN apt update && apt install maven -y
RUN git clone https://github.com/Kogit1337/project.git
RUN cd project && git checkout docker && mvn install

FROM tomcat:9-jre11 AS TOMCAT
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMG project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]

