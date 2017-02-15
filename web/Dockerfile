FROM centos:6

MAINTAINER inocop

RUN rpm -ivh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
RUN rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN yum install -y httpd
RUN yum install --enablerepo=epel,remi-php56,remi -y \
                              php \
                              php-cli \
                              php-gd \
                              php-mbstring \
                              php-mysqlnd \
                              php-mysqli \
                              php-pdo \
                              php-xml

# enable .htaccess
RUN sed -i -e "s/AllowOverride None/AllowOverride All/g" /etc/httpd/conf/httpd.conf

CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
