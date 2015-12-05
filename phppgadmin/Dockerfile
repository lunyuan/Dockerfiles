FROM debian:jessie

MAINTAINER Lun-Yuan Lee <lunyuanlee@gmail.com>

RUN apt-get update

# Install Apache
RUN apt-get install -y apache2
# Install php
RUN apt-get install -y php5 libapache2-mod-php5 php5-mcrypt

# Install phppgadmin
RUN apt-get install -y phppgadmin

RUN sed -i "s/Require local/#Require local \nRequire all granted/g" /etc/apache2/conf-enabled/phppgadmin.conf
RUN sed -i "s/\$conf\['extra_login_security'\] = true;/\$conf\['extra_login_security'\] = false;/g" /etc/phppgadmin/config.inc.php
RUN sed -i "s/\$conf\['servers'\]\[0\]\['host'\] = 'localhost';/\$conf\['servers'\]\[0\]\['host'\] = 'db';/g" /etc/phppgadmin/config.inc.php

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

