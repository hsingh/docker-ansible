# Dockerfile for building Ansible image for Ubuntu 16.04 (Xenial), with as few additional software as possible.
#
# @see https://launchpad.net/~ansible/+archive/ubuntu/ansible
#
# Version  1.0
#
# pull base image
FROM python:2.7-alpine

MAINTAINER Harpreet Singh <hs@hsingh.com>

RUN echo "===> Adding handy tools..." && \
    apk add --no-cache --virtual build-dependencies python-dev libffi-dev openssl-dev build-base groff curl zip git bash && \
    echo "===> Installing Ansible & Boto..."  && \
    pip --disable-pip-version-check --no-cache-dir install boto boto3 ansible==1.9.6 awscli && \
    \
    \
    apk del build-dependencies



# default command: display Ansible version
CMD [ "ansible-playbook", "--version" ]
