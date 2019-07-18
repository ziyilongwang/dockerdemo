from zero/centos:7.2
WORKDIR /root
ADD  Python-3.7.4.tgz  /root
RUN yum swap -y fakesystemd systemd && \
    yum clean all && rpm --rebuilddb && \
    yum install -y openssl openssl-devel 
RUN cd /root/Python-3.7.4 && ./configure --with-ssl --prefix=/usr/local/python3  && make && make install && \
     mv /usr/bin/python /usr/bin/python.bak && ln -s /usr/local/python3/bin/python3  /usr/bin/python
ONBUILD ADD . /root
