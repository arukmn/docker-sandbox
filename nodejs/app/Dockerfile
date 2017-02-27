FROM ubuntu:16.04

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y git build-essential libssl-dev curl checkinstall python make gcc g++ bzip2 net-tools vim host redis-server mysql-client

# set CONST
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION v7.5.0
ENV NODE_PATH $NVM_DIR/$NODE_VERSION/lib/node_modules
ENV PATH $NVM_DIR/versions/node/$NODE_VERSION/bin:$PATH

# Install nvm with node and npm
RUN curl https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash \
    && . $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use default \
    && npm i -g pm2

# attachした時にホームディレクトの様な状態になる
RUN mkdir -p /usr/app
WORKDIR /usr/app

EXPOSE 8888

CMD ["/bin/bash"]
