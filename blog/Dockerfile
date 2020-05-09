FROM ubuntu

MAINTAINER radial radial_hks@gmail.com



RUN apt-get update \
    && apt-get install -y nodejs \
    && apt-get install npm \
    && npm config set registry https://registry.npm.taobao.org \
    && npm install -g hexo-cli \
    && apt-get install git \
    && mkdir -p /opt/blog \
    && cd /opt/blog/ \
    && hexo init \
    && hexo generate \

EXPOSE 4000

WORKDIR  /opt/

CMD ["hexo server"]


