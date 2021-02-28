FROM node:10-alpine

# Install "libraries", "Software's"
RUN apk update && \
    apk add --no-cache bash \
    git \
    curl \
    vim \
    autoconf \
    automake \
    gcc \
    libpng-dev\
    g++ \
    libc6-compat \
    libjpeg-turbo-dev \    
    make \
    nasm

RUN curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version 1.12.3 && \
  ln -sf $HOME/.yarn/bin/yarn /usr/local/bin/yarn && \
  ln -sf $HOME/.yarn/bin/yarnpkg /usr/local/bin/yarnpkg    

ARG DIR

WORKDIR ${DIR}

EXPOSE 8080

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
CMD [ "yarn", "dev"]
