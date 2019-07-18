#
# MAINTAINER        Long,Zhang<392572435@qq.com>
#
# Dockerizing Mariadb: Dockerfile for building Mariadb images
#
FROM zero/centos:7.2
MAINTAINER zero <392572435@qq.com>

ENV DATA_DIR /var/lib/mysql

# Install Mariadb
RUN yum install -y mariadb mariadb-server && \
    yum clean all

ADD mysqld_charset.cnf /etc/my.cnf.d/

COPY scripts /scripts
RUN chmod +x /scripts/start

EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]
