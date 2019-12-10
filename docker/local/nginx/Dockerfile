FROM nginx:stable-alpine

MAINTAINER xxxgit

#默认配置目录
WORKDIR /etc/nginx

RUN mkdir vhost

#创建数据目录
RUN mkdir -p /data/sites

EXPOSE 80

# the command of entrypoint
ENTRYPOINT ["nginx"]

CMD ["-g", "daemon off;"]