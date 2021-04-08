# Server Setting

## windows server
Anaconda:
 - version: conda 4.9.2(64-bit) with python3.8.5
 - install: https://www.anaconda.com/products/individual
Kiwoom API: 
 -install: https://www3.kiwoom.com/nkw.templateFrameSet.do?m=m1408010600
 
## ubuntu
PHP: 
 - version: 8.0.3
 - install: sudo apt install php8.0
 
Laravel/Lumen:
 - version: 8.x with php8.x
 - install: 
 ```
 # first, install composer
 php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
 php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
 php composer-setup.php
 php -r "unlink('composer-setup.php');"
 mv composer.phar /usr/local/bin/composer
 # second, install laravel/lumen
 composer create-project --prefer-dist laravel/lumen {project-name}
 ```
Apache2.4:
  - version: 2.4.41
  - install: sudo apt install apache2

mariaDB:
  - version: 15.1 Distrib 10.3.25-MariaDB
  - install: sudo apt install mariadb-server

python3-pip:
  - version: pip 20.0.2 with python3.8
  - install: sudo apt install python3-pip
  
