FROM jdeathe/centos-ssh-mysql:centos-6
MAINTAINER darek@mika.email
ENV MYSQL_ROOT_PASSWORD=ransompassword
RUN yum -y install ansible crontabs
ADD ansible /etc/ansible/
RUN ansible-playbook -b /etc/ansible/provision.yml
EXPOSE 3306
