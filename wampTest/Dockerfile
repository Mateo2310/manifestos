FROM ubuntu/apache2:2.4-20.04_beta
RUN mkdir /etc/apache2/aliases
RUN mkdir /etc/apache2/Guru
RUN mkdir /etc/apache2/Guru/rewrite-rules
RUN mkdir /etc/apache2/sites-available/vhost
# COPY ./conf/aliases /etc/apache2/aliases
# COPY ./conf/rewrite-rules/ /etc/apache2/Guru/rewrite-rules
# COPY ./conf/vhost /etc/apache2/sites-available
CMD ["bash"]
RUN a2enmod rewrite
RUN a2enmod cache
RUN a2enmod expires
RUN a2enmod headers
RUN a2enmod usertrack
RUN a2enmod proxy
RUN a2enmod proxy_http
RUN a2enmod proxy_balancer
RUN a2enmod proxy_html
RUN a2enmod proxy_ajp
RUN a2enmod ssl
RUN service apache2 restart
# RUN apt update && apt upgrade
# RUN apt install openjdk-8-jdk -y

EXPOSE 8080
