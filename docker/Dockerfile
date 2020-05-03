FROM node:14

# 参照元: https://qiita.com/twu_go/items/8539bde01662c2a0a7a2

LABEL msntts.com.github.window-server-type="X11"

# ディスプレイ設定
ENV QT_X11_NO_MITSHM=1
ENV DISPLAY=host.docker.internal:0

# 日本語が使えるようにする
ENV DEBIAN_FRONTEND noninteractive
ENV LANG ja_JP.UTF-8
ENV LC_CTYPE ja_JP.UTF-8

# 実行時ユーザ
ARG DOCKER_USER=docker
ARG DOCKER_PASSWORD=docker

# electronインストール&ユーザ作成
RUN apt-get update && \
    apt-get -y install \
    libgtkextra-dev \
    libgconf2-dev \
    libnss3 \
    libasound2 \
    libxtst-dev \
    libxss1 \
    libgtk-3-0 \
    curl \
    sudo \
    locales && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    locale-gen ja_JP.UTF-8 && \
    localedef -f UTF-8 -i ja_JP ja_JP.utf8 && \
    curl -o- -L https://yarnpkg.com/install.sh | bash && \
    export PATH="$PATH:`yarn global bin`" && \
    yarn global add electron && \
    useradd -m -G sudo ${DOCKER_USER} && \
    echo ${DOCKER_USER}:${DOCKER_PASSWORD} | chpasswd

USER ${DOCKER_USER}
