FROM alpine:3.14.2
ARG ALPINE_REPO=mirrors.aliyun.com

RUN set -x \
    && sed -i "s/dl-cdn.alpinelinux.org/$ALPINE_REPO/g" /etc/apk/repositories \
    && apk add --update --no-cache python3 git bash procps curl
ENV TZ=Asia/Shanghai
ADD v1.2.0.tar.gz /opt/novnc/
ENV VNC_SERVER=localhost:5900
ENV LISTEN_PORT=6080
CMD /opt/novnc/noVNC-1.2.0/utils/launch.sh --vnc $VNC_SERVER --listen $LISTEN_PORT

HEALTHCHECK --interval=10s --timeout=3s CMD curl --fail http://localhost:$LISTEN_PORT/
