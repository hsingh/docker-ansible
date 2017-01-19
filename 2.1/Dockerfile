# Dockerfile for building Ansible image for Ubuntu 16.04 (Xenial), with as few additional software as possible.
#
# @see https://launchpad.net/~ansible/+archive/ubuntu/ansible
#
# Version  1.0
#
# pull base image
FROM python:2.7

MAINTAINER Harpreet Singh <hs@hsingh.com>

RUN echo "===> Installing Ansible & Boto..."  && \
    pip --disable-pip-version-check --no-cache-dir install boto boto3 ansible==2.1.4.0 awscli && \
    \
    \
    echo "===> Adding handy tools..."  && \
    apt-get update && \
    apt-get install -y --no-install-recommends curl git zip unzip sshpass openssh-client groff && \
    mkdir -p /etc/ansible && \
    echo "localhost              ansible_connection=local ansible_python_interpreter=python" > /etc/ansible/hosts

# default command: display Ansible version
CMD [ "ansible-playbook", "--version" ]
