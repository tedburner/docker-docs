构建镜像

```bash
sudo docker build -t mycat:1.6.7.4 .
```

如果使用前，请先将需要挂载的配置文件，放在宿主机需要挂载的目录下。配置文件可以使用仓库中conf下的配置文件，这些配置文件，是mycat自带的。

启动mycat

```bash
sudo docker run -d --name mycat \
-p 8066:8066 -p 9066:9066 \
-v /home/fvad/mycat/conf/:/usr/local/mycat/conf/ \
-v /home/fvad/mycat/logs/:/usr/local/mycat/logs/ \
mycat:1.6.7.4
```

