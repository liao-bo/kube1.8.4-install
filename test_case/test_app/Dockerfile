FROM ubuntu:16.04

ARG http_proxy="http://liujun162:Linux%403079@10.199.75.12:8080"
ARG https_proxy=$http_proxy

RUN echo '\
deb http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse \
deb http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse \
deb http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse \
deb http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse \
deb http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse'>/etc/apt/sources.list

RUN apt-get update && apt-get install -y python-pip --fix-missing

ADD requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

VOLUME ["/var/app"]

ADD run.sh /var/run.sh

EXPOSE 5000

CMD chmod +x /var/run.sh && /var/run.sh
