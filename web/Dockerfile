FROM node:18-slim
ARG INSTALL_PATH=/opt/docker-mcsm
ARG TZ=Asia/Shanghai
ENV TZ=${TZ}
RUN apt update && apt install -y git
RUN git clone --single-branch -b master --depth 1 https://github.com/MCSManager/MCSManager-Web-Production.git $INSTALL_PATH/releases/web
RUN cd $INSTALL_PATH/releases/web && npm i --production
WORKDIR $INSTALL_PATH/releases/web
CMD node app.js