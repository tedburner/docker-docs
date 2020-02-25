#基于opjdk8创建镜像,可自行替换centos等
FROM openjdk:8-jdk-alpine
ADD mycat.tar.gz /usr/local/
VOLUME /usr/local/mycat/conf
ENV MYCAT_HOME=/usr/local/mycat
EXPOSE 8066 9066
CMD ["/usr/local/mycat/bin/mycat", "console","&"]