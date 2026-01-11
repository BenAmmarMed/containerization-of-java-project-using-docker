FROM  maven:3.9.9-eclipse-temurin-21-jammy AS BUILDER_IMAGE
LABEL "project"="vprofile-project"
LABEL "Author"="Ben Ammar"
WORKDIR /app

COPY ./pom.xml /app/
RUN mvn dependency:go-offline
COPY ./src /app/src
RUN mvn clean package -DskipTests

FROM tomcat:10.1-jdk21
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILDER_IMAGE /app/target/*.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080 
CMD ["catalina.sh", "run"]

