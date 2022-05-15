FROM python:3.7-slim-stretch

ENV COOKIE=""
ENV RUID="0"
ENV CRON="13 20 * * *"
ENV SERVER_CHAN_SENDKEY=""
ENV TZ="Asia/Shanghai"

RUN sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list \
	&& apt-get update \
	&& apt-get install -y --no-install-recommends git g++ \
	&& rm -rf /var/lib/apt/lists/* \
    && pip install --upgrade pip \
	&& git clone https://github.com/gxusb/bili-live-heart.git /app

WORKDIR /app

RUN pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

CMD [ "python", "index.py", "--fromdocker" ]
