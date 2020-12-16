FROM java:8 
MAINTAINER laolan
ENV REFRESHED_AT 2020-12-10  
ENV LANG C.UTF-8

VOLUME /tmp

WORKDIR /usr/local
RUN mkdir kun-dam-dqc-3.5.3

ADD kun-dam-dqc-3.5.3 /usr/local/kun-dam-dqc-3.5.3/

EXPOSE 9092
WORKDIR kun-dam-dqc-3.5.3
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-XX:+DisableAttachMechanism","-agentpath:bin/codelib.so","-jar","kun-dam-dqc-3.5.3.jar"]
