#
# MAINTAINER        Long,Zhang<392572435@qq.com>
#
# Dockerizing Mariadb: Dockerfile for building Mariadb images
#
FROM zero/centos:7.1
MAINTAINER Carson,C.J.Zeong <zcy@nicescale.com>

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
