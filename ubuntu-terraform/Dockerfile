FROM ubuntu:18.04

MAINTAINER Jashan Sidhu <sidhujashandeep05@gmail.com>

ENV TERRAFORM_VERSION="0.12.9"
ENV PROVIDER_AWS="2.30.0"

RUN apt-get update && \
    apt-get install -y \
    curl \
    ca-certificates \
    gnupg \
    groff \
    default-jre \
    jq \
    less \
    openssl \
    python \
    python-pip \
    python-dev \
    unzip \
    zip \
    bsdmainutils \
    wget \
    git \
    gnupg2 \
    rubygems && \
    pip install --upgrade pip virtualenv awscli==1.* s3cmd==2.* python-magic cfn-lint

RUN curl -fsSLO --compressed "https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    unzip "terraform_${TERRAFORM_VERSION}_linux_amd64.zip" -d /bin && \
    rm "terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    curl -fsSLO --compressed "https://releases.hashicorp.com/terraform-provider-aws/${PROVIDER_AWS}/terraform-provider-aws_${PROVIDER_AWS}_linux_amd64.zip" && \
    unzip "terraform-provider-aws_${PROVIDER_AWS}_linux_amd64.zip" -d /bin && \
    rm "terraform-provider-aws_${PROVIDER_AWS}_linux_amd64.zip"

RUN apt-get clean && \
    apt-get update
