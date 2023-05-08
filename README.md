# Apache Config Window

[Download](https://www.apachelounge.com/download/)


## Update C:\apache24\conf\httpd.conf

```apacheconf
LoadModule rewrite_module modules/mod_rewrite.so

<IfModule dir_module>
    DirectoryIndex index.php index.html
</IfModule>

# PHP 7.4 module
# PHPIniDir "C:/php7.4"
# LoadModule php7_module "C:/php7.4/php7apache2_4.dll"
# AddType application/x-httpd-php .php

# PHP 8.1 module
# PHPIniDir "C:/php8.1"
# LoadModule php_module "C:/php8.1/php8apache2_4.dll"
# AddType application/x-httpd-php .php

# PHP 8.2 module
PHPIniDir "C:/php8.2"
LoadModule php_module "C:/php8.2/php8apache2_4.dll"
AddType application/x-httpd-php .php
LoadFile "C:/php8.2/php8ts.dll"
LoadFile "C:/php8.2/libpq.dll"

<VirtualHost custom-domain.test:80>
    DocumentRoot "C:/PROJECT_DIRECTORY"
    ServerName custom-domain.test
    DirectoryIndex index.php
    <Directory "C:/PROJECT_DIRECTORY">
        AllowOverride All
        Options Indexes FollowSymLinks
        Require all granted
    </Directory>
</VirtualHost>
```

## Run background

```sh
C:\apache24\bin\httpd.exe -k install
```
