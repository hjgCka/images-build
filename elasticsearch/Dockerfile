FROM docker.elastic.co/elasticsearch/elasticsearch:6.2.2
MAINTAINER Hjg<computer_cka@163.com>

ARG IK_FILE
ARG XPACK_JAR_FILE

COPY ${IK_FILE} /usr/share/elasticsearch/

RUN mkdir plugins/ik && \
    unzip ${IK_FILE} && \
    mv elasticsearch/* plugins/ik && \
    rm -f ${IK_FILE} && \
    rm -f elasticsearch && \
    rm -f /usr/share/elasticsearch/plugins/x-pack/x-pack-core/${XPACK_JAR_FILE}

COPY ${XPACK_JAR_FILE} /usr/share/elasticsearch/plugins/x-pack/x-pack-core/${XPACK_JAR_FILE}
