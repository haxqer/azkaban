FROM openjdk:8-stretch

LABEL maintainer="haxqer <haxqer666@gmail.com>" version="3.75.2"

ARG AZKABAN_VERSION=3.75.2

ENV AZKABAN_USER=azkaban \
    AZKABAN_GROUP=azkaban \
    AZKABAN_HOME=/var/azkaban

RUN mkdir -p ${AZKABAN_HOME} \
&& export CONTAINER_USER=$AZKABAN_USER \
&& export CONTAINER_GROUP=$AZKABAN_GROUP \
&& groupadd -r $AZKABAN_GROUP && useradd -r -g $AZKABAN_GROUP $AZKABAN_USER \
&& chown -R $AZKABAN_USER:$AZKABAN_GROUP ${AZKABAN_HOME}/ \
&& curl -o /tmp/azkaban.tar.gz https://github.com/haxqer/azkaban/releases/download/${AZKABAN_VERSION}/azkaban-solo-server.tar.gz -L \
&& tar xzf /tmp/azkaban.tar.gz -C ${AZKABAN_HOME}/ --strip-components 1 \
&& rm -f /tmp/azkaban.tar.gz

VOLUME $AZKABAN_HOME
USER $AZKABAN_USER
WORKDIR $AZKABAN_HOME
EXPOSE 8081
ENTRYPOINT ["/var/azkaban/bin/internal/internal-start-solo-server.sh"]
