# Docker搭建Kafka集群

⭕️ 使用本脚本之前，请先安装`Zookeeper` 集群

该脚本使用的

`Kafka`镜像为：**wurstmeister/kafka**

`Kafka-manager`镜像为：**sheepkiller/kafka-manager**

1. 安装 `docker-compose`



   ```
   # 获取脚本
   $ curl -L https://github.com/docker/compose/releases/download/1.25.0-rc2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
   # 赋予执行权限
   $chmod +x /usr/local/bin/docker-compose 
   ```

2. 下载当前`docker-compose.yml`

   ```
   wget https://raw.githubusercontent.com/JacianLiu/docker-compose/master/kafka/docker-compose.yml
   ```

3. 新建 Docker 网络

```
docker network create zoo_kafka
```

4. 执行命令 `docker-compose up -d`