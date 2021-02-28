FROM alpine:latest

RUN apk update && \
    apk add --no-cache \
    gcc \
    python2-dev \
    g++ \
    libffi-dev \
    openssl-dev \
    py2-pip \
    openssh \
    sshpass \
    rsync \
    tzdata

RUN pip install python-dateutil 
RUN pip install boto
RUN pip install boto3
RUN pip install botocore
RUN pip install ansible 

RUN cp /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
RUN echo "America/Sao_Paulo" > /etc/timezone
RUN apk del tzdata
