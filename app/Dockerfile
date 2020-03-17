
FROM debian:10-slim
RUN apt update
RUN apt install -y unzip net-tools ntfs-3g apache2 php \ 
  libapache2-mod-php php-cli php-common php-mbstring php-gd \
  php-xml php-zip libapache2-mod-xsendfile php-mysql ffmpeg samba git
RUN git clone https://github.com/tobychui/ArOZ-Online-System
RUN mv ./ArOZ-Online-System/src /var/www/html/AOB && rm -rf ./ArOZ-Online-System
RUN chown -R www-data /var/www/html
RUN sed -i 's/upload_max_filesize = 2M/upload_max_filesize = 2048M/g' /etc/php/7.3/apache2/php.ini && \
  sed -i 's/post_max_size = 8M/post_max_size = 2048M/g' /etc/php/7.3/apache2/php.ini && \
  echo 'www-data ALL=(ALL:ALL) NOPASSWD:ALL' >> /etc/sudoers && \ 
  echo 'XSendFile on\nXSendFilePath /media' >> /etc/apache2/apache2.conf

CMD chmod -R 777 /etc/AOB /media && apache2ctl start && tail -f /var/log/apache2/*