# Install dependencies and choose the appropriate script based on the system (Ubuntu 24.04, HCE2.0)

## Install docker

```
# Install Docker
apt  install docker.io  # ubuntu system
yum install docker    # Euler system installation

# Configure image accelerator
vi /etc/docker/daemon.json
{
"registry-mirrors": [ " https://51262a7168c84cfd97b7c142adbd05ca.mirror.swr.myhuaweicloud.com " ]
}

# Restart the container engine
systemctl restart docker

Execute Docker info. When the address in the Registry Mirrors field is the address of the accelerator, it indicates that the accelerator has been successfully configured.
```



## Start service

```shell
docker run -d \
  --name langflow \
  --restart unless-stopped \
  -p 7860:7860 \
  langflowai/langflow:latest
  
 # View container
 docker  ps
```

# 