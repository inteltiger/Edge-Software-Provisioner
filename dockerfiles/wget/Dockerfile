# Copyright (C) 2019 Intel Corporation
# SPDX-License-Identifier: BSD-3-Clause

FROM alpine:3.12

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g" /etc/apk/repositories && apk --no-cache update && \
    apk --no-cache add ca-certificates wget && \
    rm -rf /var/cache/apk/*

WORKDIR /data
