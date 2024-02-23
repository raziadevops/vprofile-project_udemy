FROM openjdk:17-jdk-slim AS BUILD_IMAGE
RUN apt update && \
    apt install git -y && \
    apt install maven -y && \
    git clone https://github.com/raziadevops/vprofile-project_udemy.git && \
    cd vprofile-project_udemy && \ 
    git checkout docker && \ 
    mvn install


FROM tomcat:9-jre17
LABEL "project"="vprofile_containerization"
LABEL "author"="udemy"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project_udemy/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]