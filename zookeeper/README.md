# Docker搭建Zookeeper集群

该脚本使用的

~~`zookeeper`镜像为：**zookeeper:3.4**~~

`zookeeper`镜像为：**wurstmeister/zookeeper**

> 由于在使用的时候出现了点小问题，切换为和`Kafka`镜像同作者的`Zookeeper`镜像

1. 安装 `docker-compose`

   ```
   # 获取脚本
   $ curl -L https://github.com/docker/compose/releases/download/1.25.0-rc2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
   # 赋予执行权限
   $ chmod +x /usr/local/bin/docker-compose
   ```

2. 下载当前`docker-compose.yml`

```
$ wget https://raw.githubusercontent.com/JacianLiu/docker-compose/master/zookeeper/docker-compose.yml
```

3. 新建 Docker 网络

   ```
   $ docker network create --driver bridge --subnet 172.69.0.0/25 --gateway 172.69.0.1  kafka_zoo
   ```

4. 执行命令 `docker-compose up -d`