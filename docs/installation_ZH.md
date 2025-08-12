# 安装依赖，根据系统（Ubuntu 24.04、HCE2.0）不同选择相应的脚本

## 安装docker

~~~markdown
# 安装docker
apt  install docker.io  # ubuntu 系统
yum install docker  # 欧拉系统安装

# 配置镜像加速器
vi /etc/docker/daemon.json

{
    "registry-mirrors": [ "https://51262a7168c84cfd97b7c142adbd05ca.mirror.swr.myhuaweicloud.com" ]
}

# 重启容器引擎
systemctl restart docker

执行docker info，当Registry Mirrors字段的地址为加速器的地址时，说明加速器已经配置成功。
~~~



## 启动服务

```shell
docker run -d \
  --name langflow \
  --restart unless-stopped \
  -p 7860:7860 \
  langflowai/langflow:latest
  
 # 查看容器
 docker  ps
```


# 