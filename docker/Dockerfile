ARG CENOS_VERSION=centos8.3.2011
FROM centos:${CENOS_VERSION}
ENV TZ=Asia/Shanghai
RUN dnf -y install git python3
ADD v1.2.0.tar.gz /opt/novnc/
ENV VNC_SERVER=localhost:5900
ENV LISTEN_PORT=6080
CMD /opt/novnc/noVNC-1.2.0/utils/launch.sh --vnc $VNC_SERVER --listen $LISTEN_PORT

HEALTHCHECK --interval=10s --timeout=3s CMD curl --fail http://localhost:$LISTEN_PORT/
