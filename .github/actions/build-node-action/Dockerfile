FROM centos:centos6
LABEL maintainer="joe@rstudio.com"

RUN sed -e "s|^mirrorlist=|#mirrorlist=|g" -e "s|^#baseurl=http://mirror.centos.org/centos/\$releasever|baseurl=https://mirrors.tuna.tsinghua.edu.cn/centos-vault/6.10|g" -i.bak /etc/yum.repos.d/CentOS-*.repo
RUN cat /etc/yum.repos.d/*.repo
RUN yum -y install centos-release-scl
RUN yum -y install python27
RUN yum -y install devtoolset-7
RUN yum -y install git
RUN yum -y install xz

COPY make-node.sh /make-node.sh

ENTRYPOINT [ "/make-node.sh" ]
