---
layout: post
title: Install APC on Mac OS X Lion
---

First you need to [install PEAR][1], Xcode (and the Command Line Tools) and autoconf (ex : via Brew)

{% highlight bash %}
curl -O http://freefr.dl.sourceforge.net/project/pcre/pcre/8.02/pcre-8.02.tar.gz
tar xvf pcre-8.02.tar.gz
sudo cp pcre-8.02/pcre*.h /usr/include
sudo cp pcre-8.02/pcre.h.generic /usr/include/pcre.h
rm -r pcre-8.02*

export MACOSX_DEPLOYMENT_TARGET=10.7
export CFLAGS="-arch x86_64"
export CXXFLAGS="-arch x86_64"

sudo pecl install apc
{% endhighlight %}

[1]: /2011/07/27/install-pear-on-osx-lion.html