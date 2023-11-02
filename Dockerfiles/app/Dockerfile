FROM openjdk:8 AS IMAGE
RUN apt update && apt install maven -y
RUN git clone -b docker https://github.com/divzraj/devprojects.git
RUN cd devprojects && mvn install


FROM tomcat:9-jre11
LABEL "proj"="mine"
LABEL "type"="docker"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=IMAGE devprojects/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]