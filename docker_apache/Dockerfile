FROM centos:6.6
MAINTAINER darek@mika.email

ADD files/epel-release-latest-6.noarch.rpm /tmp
RUN rpm -ivh /tmp/epel-release-latest-6.noarch.rpm
ADD ansible /etc/ansible/
RUN yum -y update
RUN yum -y install python-dateutil ansible s3cmd crontabs httpd
RUN ansible-playbook -b /etc/ansible/provision.yml
EXPOSE 80
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]

