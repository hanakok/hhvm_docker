FROM hhvm/hhvm
RUN apt-get update

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
      && php -r "if (hash_file('SHA384', 'composer-setup.php') === trim(file_get_contents('https://composer.github.io/installer.sig'))) { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
      && php composer-setup.php --version=1.8.0 \
      && php -r "unlink('composer-setup.php');" \
      && mv composer.phar /usr/sbin/composer
