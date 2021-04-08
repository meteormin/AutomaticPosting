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
  - addtional: apache2.conf, 000-default.conf
  ```
  # apache2.conf
  User {username}
  Group {groupname}
  
  <Directory />
        Options FollowSymLinks
        AllowOverride None
        Require all denied
  </Directory>

  <Directory /usr/share>
        AllowOverride None
        Require all granted
  </Directory>

  <Directory {project-path}>
        Options FollowSymLinks
        AllowOverride All
        Require all granted
  </Directory>
  
  # 000-default.conf
  <VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port that
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin example@localhost
        DocumentRoot {project-path}

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
        <Directory {project-path}>
                Options FollowSymLinks
                AllowOverride All
                Require all granted
        </Directory>
        # For most configuration files from conf-available/, which are
        # enabled or disabled at a global level, it is possible to
        # include a line for only one particular virtual host. For example the
        # following line enables the CGI configuration for this host only
        # after it has been globally disabled with "a2disconf".
        #Include conf-available/serve-cgi-bin.conf
 </VirtualHost>

 # vim: syntax=apache ts=4 sw=4 sts=4 sr noet
 ```
mariaDB:
  - version: 15.1 Distrib 10.3.25-MariaDB
  - install: sudo apt install mariadb-server

python3-pip:
  - version: pip 20.0.2 with python3.8
  - install: sudo apt install python3-pip
  
