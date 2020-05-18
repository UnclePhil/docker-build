 FROM alpine
 LABEL maintainer="ph.koenig@koenig.ph"

RUN apk --no-cache add \
        py-crypto py-yaml py-jinja2  py-paramiko py-setuptools git py2-pip perl py-simplejson rsync \
        py-httplib2 py-psycopg2 openssh sshpass py-dnspython py-netaddr openssl curl \
&& apk add --no-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/  py-netifaces py-msgpack \
&& rm -rf /var/cache/apk/* \
&&  pip install --upgrade setuptools \
&&  pip install python-keyczar boto boto3 botocore hvac python-consul \
&&  mkdir /etc/ansible/ \
&&  echo "[local]" > /etc/ansible/hosts ; echo "localhost ansible_connection=local" >> /etc/ansible/hosts \
&& mkdir /opt/ansible/ -p \
&& git clone http://github.com/ansible/ansible.git /opt/ansible/ansible
WORKDIR /opt/ansible/ansible
RUN git checkout v2.9.7 \
&& git submodule update --init

ENV PATH /opt/ansible/ansible/bin:/bin:/usr/bin:/sbin:/usr/sbin
ENV PYTHONPATH /opt/ansible/ansible/lib
ENV ANSIBLE_LIBRARY /opt/ansible/ansible/library

RUN pip install -t /opt/vault --no-deps ansible-modules-hashivault && \
       cp -r /opt/vault/ansible/* /opt/ansible/ansible/lib/ansible/ && \
       rm -rf /opt/vault \
&& pip uninstall -y cryptography \
&& mkdir /ansible 
WORKDIR /ansible
