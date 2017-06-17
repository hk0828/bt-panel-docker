FROM pipill/armhf-debian:jessie

COPY install-ubuntu.sh /usr/bin/

RUN [ "cross-build-start" ]

RUN apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y iputils-ping \
  && bash /usr/bin/install-ubuntu.sh \
  && rm -rf /var/cache/apk/*

RUN mkdir -p /usr/src/www \
  && cp -a /www/* /usr/src/www/

RUN [ "cross-build-end" ]

COPY entrypoint.sh /usr/bin/

ENTRYPOINT ["entrypoint.sh"]

