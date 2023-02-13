FROM python:3.10.6-slim-buster

RUN mkdir /hello
WORKDIR /hello

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN pip install --upgrade pip
COPY ./dependencies.txt /hello/dependencies.txt
RUN pip install -r dependencies.txt

COPY . /hello