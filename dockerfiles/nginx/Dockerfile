# Copyright (C) 2020 Intel Corporation
# SPDX-License-Identifier: BSD-3-Clause

FROM nginx:1.21.3-alpine
LABEL maintainer "Bryan J Rodriguez <bryan.j.rodriguez@intel.com>"

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g" /etc/apk/repositories && apk update && apk add --no-cache \
      ca-certificates \
      inotify-tools \
      openssl \
      tini \
      wget \
    && update-ca-certificates

COPY init /usr/local/bin/
COPY openssl.cnf /etc/ssl

ENV CN=nginx.local \
    O=nginx \
    OU=nginx \
    C=US

EXPOSE 80
EXPOSE 443

ENTRYPOINT ["tini", "--"]
CMD ["/usr/local/bin/init"]