FROM centos

RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*

RUN yum install initscripts httpd -y
ADD Configs/httpd.conf /etc/httpd/conf/
ADD Website/webapp.html /var/www/html/index.html

CMD /usr/sbin/httpd -DFOREGROUND

EXPOSE 80
