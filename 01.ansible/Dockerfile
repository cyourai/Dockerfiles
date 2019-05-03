FROM cyourai/centos7
MAINTAINER cyourai <cyourai@sina.com>
RUN yum -y update && \
    yum clean all && \
    yum -y install epel-release && \
    yum -y install PyYAML python-jinja2 python-httplib2 python-keyczar python-paramiko python-setuptools git python-pip
RUN mkdir /etc/ansible/
RUN echo '[local]\nlocalhost\n' > /etc/ansible/hosts
RUN mkdir -p /workspaces/ansible/
RUN git clone http://github.com/ansible/ansible.git /workspaces/ansible
WORKDIR /workspaces/ansible
RUN git submodule update --init
ENV PATH /workspaces/ansible/bin:/bin:/usr/bin:/sbin:/usr/sbin
ENV PYTHONPATH /workspaces/ansible/lib
ENV ANSIBLE_LIBRARY /workspaces/ansible/library