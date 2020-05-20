FROM python:3.8.3-slim-buster

MAINTAINER "radial" <radial.hks@gmail.com>

RUN  echo "deb http://mirrors.aliyun.com/debian/ buster main non-free contrib" > /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian-security buster/updates main" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian-security buster/updates main" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" >> /etc/apt/sources.list \
    && apt-get update && apt-get install git -y \
    && apt-get install vim -y \
    && apt-get install ssh -y \
    # 更新pip及换源
    && pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U \
    && mkdir ~/.pip \
    && touch ~/.pip/pip.conf \
    && echo "[global]" >> ~/.pip/pip.conf \
    && echo "index-url = http://mirrors.aliyun.com/pypi/simple/" >> ~/.pip/pip.conf \
    && echo "trusted-host = mirrors.aliyun.com" >> ~/.pip/pip.conf \
    && mkdir -p /opt/app

WORKDIR /opt/app

COPY requirements.txt .

# 安装环境需要的库
RUN pip install -r requirements.txt


EXPOSE 4000

CMD ["/bin/bash"]