FROM node:18-slim
ARG INSTALL_PATH=/opt/docker-mcsm
ARG TZ=Asia/Shanghai
ENV TZ=${TZ}
ENV LANG=C.utf8
ENV LC_ALL=C.utf8
ENV LANGUAGE=C.utf8
RUN apt update && apt install -y git openjdk-17-jdk
RUN git clone --single-branch -b master --depth 1 https://github.com/MCSManager/MCSManager-Daemon-Production.git $INSTALL_PATH/releases/daemon
RUN cd $INSTALL_PATH/releases/daemon && npm i --production
WORKDIR $INSTALL_PATH/releases/daemon
CMD node app.js