---
title: php apache mysql配置
category: other
---

httpd.conf:

{% highlight conf %}
LoadModule php5_module "F:/software/apm/php54/php5apache2_2.dll"
AddType application/x-httpd-php .php
PHPIniDir "F:/software/apm/php54"
# Virtual hosts
Include conf/extra/httpd-vhosts.conf
DocumentRoot "F:/PhpProject/cars"
<Directory "F:/PhpProject/cars">
{% endhighlight %}

httpd-vhosts.conf:

{% highlight conf %}
<VirtualHost *:80>
    ServerAdmin webmaster@dummy-host.macd.com
    DocumentRoot "E:/PhpProject/cars"
    ServerName 127.0.0.1
    #ServerAlias www.dummy-host.macd.com
    ErrorLog "logs/cars-error.log"
    CustomLog "logs/cars-access.log" common
</VirtualHost>
{% endhighlight %}

php.ini:

{% highlight conf %}
extension=php_mysql.dll
extension=php_mysqli.dll
extension_dir = "F:/software/apm/php54/ext"
{% endhighlight %}