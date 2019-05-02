FROM alpine:latest

MAINTAINER Jashan Sidhu <sidhujashandeep05@gmail.com>

RUN apk update

# Install base and dev packages
RUN apk add --no-cache --virtual .build-deps
RUN apk add bash

# Install git
RUN apk add git

# Install nodejs
RUN apk add nodejs

# Install yarn
RUN apk add yarn

# Install npm
RUN apk add --update nodejs nodejs-

# Install serverless
RUN npm install -g serverless

# Install Python, pip and virtualenv
RUN apk add --update \
    python \
    python-dev \
    py-pip \
    build-base \
  && pip install virtualenv \
  && rm -rf /var/cache/apk/*

# Install AWS CLI
RUN pip install awscli

CMD ["/bin/bash"]
