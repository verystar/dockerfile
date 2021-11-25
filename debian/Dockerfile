FROM debian:10.10

LABEL maintainer="www.verystar.net"
ENV TZ=Asia/Shanghai

RUN apt-get update && apt-get install -y --no-install-recommends \
        ca-certificates \
        procps \
        iputils-ping \
        curl \
        wget \
	&& rm -rf /var/lib/apt/lists/* \
    && cp /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo "${TZ}" > /etc/timezone
