#基础镜像
FROM cyourai/centos7

RUN mkdir /workspaces \
    && chmod +x /workspaces \
    && cd /workspaces \
    && wget  http://download.redis.io/releases/redis-5.0.4.tar.gz \
    && tar -xvzf redis-5.0.4.tar.gz \
    && cd redis-5.0.4 \
    && make && make install

ADD redis.conf /etc/redis.conf
EXPOSE 6379

#使用自定义conf启动
ENTRYPOINT [ "redis-server", "/etc/redis.conf" ]