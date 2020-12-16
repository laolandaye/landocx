FROM java:8     
MAINTAINER laolan
ENV REFRESHED_AT 2020-12-11  
ENV LANG C.UTF-8

VOLUME /tmp

WORKDIR /usr/local

RUN mkdir datax
RUN mkdir kun-dpexec-server-3.5.3

ADD datax datax/
ADD kun-dpexec-server-3.5.3 kun-dpexec-server-3.5.3/

EXPOSE 8818
WORKDIR kun-dpexec-server-3.5.3
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-XX:+DisableAttachMechanism","-agentpath:bin/codelib.so","-jar","kun-dpexec-server-3.5.3.jar"]
