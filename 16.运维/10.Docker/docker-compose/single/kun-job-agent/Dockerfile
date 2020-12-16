# （这串数字是我已经创建好一个ubuntu镜像的镜像id，在这里作为tomcat的基础镜像
FROM java:8     
MAINTAINER laolan
# （这个环境变量用来表名该镜像模板的最后更新时间）
ENV REFRESHED_AT 2020-12-11  
#  Tomcat 编码 和 docker 环境一致
ENV LANG C.UTF-8

VOLUME /tmp

#切换镜像目录，进入/usr目录
WORKDIR /usr/local
#在/usr/下创建tomcat目录，用来存放tomcat
RUN mkdir kun-job-agent-4.0.0

#将宿主机的tomcat目录下的文件拷至镜像的/usr/tomcat目录下
ADD kun-job-agent-4.0.0 kun-job-agent-4.0.0/

WORKDIR kun-job-agent-4.0.0/sbin
RUN ["./create.sh", "agent@dam", "11.11.11.5:5672", "dam", "bmsoft@123"]

#公开端口
WORKDIR ../
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-Dfile.encoding=UTF-8","-jar","kun-job-agent-4.0.0.jar","config/agent@docker/*.xml"]
