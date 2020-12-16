FROM java:8     
MAINTAINER laolan
ENV REFRESHED_AT 2020-12-10  
ENV LANG C.UTF-8

VOLUME /tmp

WORKDIR /usr/local
RUN mkdir kun-metaca-collect-3.5.3

ADD kun-metaca-collect-3.5.3 /usr/local/kun-metaca-collect-3.5.3/

EXPOSE 9091
WORKDIR kun-metaca-collect-3.5.3
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-XX:+DisableAttachMechanism","-agentpath:bin/codelib.so","-jar","kun-metaca-collect-3.5.3-release.jar"]
