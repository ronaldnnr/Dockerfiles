FROM ubuntu:20.04

RUN echo "#### Running update and upgrade ####" && \
  apt-get update -y && apt-get upgrade -y && \
  \
  echo "#### Installing ssh tools ####" && \
  apt-get install -y sshpass openssh-client && \
  \
  echo "#### Installing ansible ####" && \
  apt-get install -y ansible && \
  \
  echo "#### Adding hosts ####"        && \
  mkdir -p /etc/ansible                              && \
  echo 'localhost' > /etc/ansible/hosts && \
  \
  echo "#### Installing GNUPG ####" && \
  apt-get install -y gnupg gnupg1 gnupg2 && \
  \
  echo "#### Running autoremove and clean ####" && \
  apt-get autoremove && \
  apt-get autoclean

CMD [ "ansible-playbook", "--version" ]
