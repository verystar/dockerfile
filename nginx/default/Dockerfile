FROM nginx:1.21.4

LABEL maintainer="www.verystar.net"
ENV SERVER_NAME=localhost
ENV INDEX_FILE=/index.html
ENV TZ Asia/Shanghai

RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone \
    && cp -r /usr/share/nginx/html /usr/share/nginx/error \
    && rm -rf /usr/share/nginx/html/50x.html /usr/share/nginx/html/index.html

# 处理默认的配置文件
COPY nginx.conf /etc/nginx/nginx.conf
COPY nginx.vh.conf /etc/nginx/conf.d/default.conf
COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint

ENTRYPOINT ["/usr/local/bin/docker-entrypoint"]
CMD ["nginx", "-g", "daemon off;"]
