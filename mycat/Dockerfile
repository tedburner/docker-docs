FROM openjdk:8

# 下载依赖
#RUN apt-get update -y & apt-get install wget -y

# Download Mycat
#RUN wget http://dl.mycat.org.cn/1.6.7.4/Mycat-server-1.6.7.4-release/Mycat-server-1.6.7.4-release-20200105164103-linux.tar.gz \
#	&& tar xvf Mycat-server-1.6.7.4-release-20200105164103-linux.tar.gz -C /usr/local/ \
#	&& rm -rf Mycat-server-1.6.7.4-release-20200105164103-linux.tar.gz

# 将宿主机压缩包拷贝进镜像
ADD mycat.tar.gz /usr/local

#容器数据卷，用于数据保存和持久化工作
VOLUME ["/usr/local/mycat/conf","/usr/local/mycat/log"]
WORKDIR /usr/local/mycat

#用来在构建镜像过程中设置环境变量
ENV MYCAT_HOME=/usr/local/mycat

#暴露出MyCat的所需端口
EXPOSE 8066 9066

#以前台进程的方式启动MyCat服务
#CMD ["sh ", "/usr/local/mycat/bin/startup_nowrap.sh"]
CMD ["/usr/local/mycat/bin/mycat", "console","&"]