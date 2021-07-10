ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk update && apk add --no-cache murmur && mkdir /data && mkdir /config

# Copy data for add-on
#COPY run.sh /
#RUN chmod a+x /run.sh

ADD mumble-server.ini /config/mumble-server.ini

VOLUME ["/data", "/config"]

EXPOSE 64738/udp
EXPOSE 64738/tcp

ENTRYPOINT ["/usr/bin/murmurd", "-fg", "-ini", "/config/mumble-server.ini"]
CMD []
