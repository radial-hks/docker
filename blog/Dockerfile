FROM node:buster-slim

MAINTAINER "radial" <radial_hks@gmail.com>

RUN npm config set registry https://registry.npm.taobao.org \
    && echo "deb http://mirrors.aliyun.com/debian wheezy main contrib non-free" > /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian wheezy main contrib non-free" >> /etc/apt/sources.list  \
    && echo "deb http://mirrors.aliyun.com/debian wheezy-updates main contrib non-free" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian wheezy-updates main contrib non-free" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian-security wheezy/updates main contrib non-free" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian-security wheezy/updates main contrib non-free" >> /etc/apt/sources.list \
    && apt-get update \
    && npm install -g hexo-cli \
    && apt-get install git \
    && mkdir -p /opt/blog \
    && cd /opt/ \
    && hexo init blog \
    && cd blog \
    && hexo generate \


EXPOSE 4000

WORKDIR  /opt/

CMD ["hexo server"]