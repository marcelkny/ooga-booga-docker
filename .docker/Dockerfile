# syntax=docker/dockerfile:1

FROM ubuntu:22.04
RUN echo 'APT::Install-Suggests "0";' >> /etc/apt/apt.conf.d/00-docker
RUN echo 'APT::Install-Recommends "0";' >> /etc/apt/apt.conf.d/00-docker
RUN DEBIAN_FRONTEND=noninteractive \
  apt-get update \
  && apt-get install -y python3 \
  && rm -rf /var/lib/apt/lists/*
  RUN apt-get update && apt-get install -y \
  curl

#COPY ../text-generation-webui-main/* /text-ui

#FROM python:3.10-slim-buster
VOLUME /app
WORKDIR /app

#COPY requirements.txt requirements.txt
#RUN pip3 install -r requirements.txt

COPY . .

CMD [ "./start_linux.sh"]
