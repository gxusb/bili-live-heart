# README
This is a Dockerfile for the [Docker](  http://docker.io ) project.

[docker images](https://hub.docker.com/r/gxggxl/bili-live-heart)

# Running
docker-compose.yml
```yml
version: "3"
services:
  bili-live-heart:
    image: gxggxl/bili-live-heart
    container_name: bili-live-heart
    deploy:
      resources:
        limits:
          cpus: '0.2'
          memory: 128M
    env_file: ./env.list
    tty: true
    restart: always
```
env.lsit
```
# B站cookie
COOKIE=""
# 需要自动打卡主播uid
RUID=0
# Cron 表达式
CRON="11 20 * * *"
# Server酱sendkey，选填
SERVER_CHAN_SENDKEY=""
```
command:
```bash
docker-compose -f docker-compose.yml up -d
```
```bash
#创建目录bili-live-heart 并下载 docker-compose.yml env.list
mkdir /root/bili-live-heart && cd /root/bili-live-heart && wget https://git.gxggxl.workers.dev/https://raw.githubusercontent.com/gxusb/bili-live-heart/master/docker/docker-compose.yml && wget https://git.gxggxl.workers.dev/https://raw.githubusercontent.com/gxusb/bili-live-heart/master/docker/env.list
```
