FROM java:8     
MAINTAINER laolan
ENV REFRESHED_AT 2020-12-11  
ENV LANG C.UTF-8

VOLUME /tmp

WORKDIR /usr/local
RUN mkdir kun-job-server-deploy-4.0.0

ADD kun-job-server-deploy-4.0.0 kun-job-server-deploy-4.0.0/

EXPOSE 8185
WORKDIR kun-job-server-deploy-4.0.0
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","kun-job-server-deploy-4.0.0.jar"]
