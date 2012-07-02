---
layout: post
title: Install PHP 5.3.7 on OS X Lion
---

First you need to install [libjpeg][1], [libpng][2] and download/extract the [Suhosin path][3]

Install command :
-----------------

{% highlight bash %}
export MACOSX_DEPLOYMENT_TARGET=10.7
export CFLAGS="-arch x86_64"
export CXXFLAGS="-arch x86_64"

cd php-5.3.7
patch -p 1 -i ../suhosin-patch-5.3.7-0.9.10.patch

./configure --prefix=/usr --mandir=/usr/share/man --infodir=/usr/share/info --sysconfdir=/private/etc --with-apxs2=/usr/sbin/apxs --enable-cli --with-config-file-path=/etc --with-libxml-dir=/usr --with-openssl=/usr --with-kerberos=/usr --with-zlib=/usr --enable-bcmath --with-bz2=/usr --enable-calendar --with-curl=/usr --enable-dba --enable-exif --enable-ftp --with-gd --with-freetype-dir=/Developer/SDKs/MacOSX10.7.sdk/usr/X11 --with-jpeg-dir=/usr/local --with-png-dir=/usr/local --enable-gd-native-ttf --with-iodbc=/usr --with-ldap=/usr --with-ldap-sasl=/usr --with-libedit=/usr --enable-mbstring --enable-mbregex --with-mysql=mysqlnd --with-mysqli=mysqlnd --without-pear --with-pdo-mysql=mysqlnd --with-mysql-sock=/var/mysql/mysql.sock --with-readline=/usr --enable-shmop --with-snmp=/usr --enable-soap --enable-sockets --enable-sqlite-utf8 --enable-sysvmsg --enable-sysvsem --enable-sysvshm --with-tidy --enable-wddx --with-xmlrpc --with-iconv-dir=/usr --with-xsl=/usr --enable-zend-multibyte --enable-zip --with-pcre-regex --with-pgsql=/usr --with-pdo-pgsql=/usr
make
sudo make install
{% endhighlight %}

Need __Intl__ ? :
---------------------------------

Install __ICU 4.6__, add _--enable-intl_ in ./configure, open __Makefile__ and add _-lstdc++_ to __EXTRA_LIBS__


[1]: http://www.ijg.org
[2]: http://www.libpng.org/pub/png/libpng.html
[3]: http://www.hardened-php.net/suhosin/download.html