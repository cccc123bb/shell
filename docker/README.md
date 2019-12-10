
后台运行：
docker-compose up -d

修改nginx配置后，通过  
docker-compose up -d --force-recreate  重启


安装 Docker Compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version


安装Docker,Centos7。
1. 操作系统最低要求 CentoOS 7。
2. 卸载旧版本
yum remove docker \
      docker-client \
      docker-client-latest \
      docker-common \
      docker-latest \
      docker-latest-logrotate \
      docker-logrotate \
      docker-engine

3. 安装 yum-utils 
yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2

4. 设置稳定的仓库。
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo

5. 安装 Docker。
yum install docker-ce docker-ce-cli containerd.io    
