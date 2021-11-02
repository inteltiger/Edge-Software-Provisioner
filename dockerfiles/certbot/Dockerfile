# Copyright (C) 2020 Intel Corporation
# SPDX-License-Identifier: BSD-3-Clause

FROM certbot/certbot:v1.19.0
LABEL maintainer "Bryan J Rodriguez <bryan.j.rodriguez@intel.com>"

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g" /etc/apk/repositories && apk update && apk add --no-cache \
      bash \
      inotify-tools \
      tini

RUN apk add krb5 apk-tools --no-cache --repository=http://dl-cdn.alpinelinux.org/alpine/v3.14/main

COPY init /usr/local/bin/
COPY scripts/ /opt/esp/scripts/

WORKDIR /opt/esp

ENTRYPOINT ["tini", "--"]
CMD ["/usr/local/bin/init"]