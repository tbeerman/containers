FROM centos:7

ARG TAG

WORKDIR /tmp

RUN yum install -y epel-release.noarch && \
    yum clean all && \
    rm -rf /var/cache/yum
RUN yum -y install https://repo.ius.io/ius-release-el7.rpm &&\
    yum install -y python36u-pip libaio gcc python36-devel.x86_64 openssl-devel.x86_64 mod_ssl python36-m2crypto libnsl.x86_64 && \
    yum clean all && \
    rm -rf /var/cache/yum

RUN rpm -i https://download.oracle.com/otn_software/linux/instantclient/211000/oracle-instantclient-basiclite-21.1.0.0.0-1.x86_64.rpm; \
    echo "/usr/lib/oracle/21/client64/lib" >/etc/ld.so.conf.d/oracle.conf; \
    ldconfig

CMD ["sleep", "10"]
