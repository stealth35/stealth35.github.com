---
layout: post
title: Speedup Symfony2 with APC
---

First you need to install [APC][1], and (if you want) [igbinary][2].
Change _apc.shm_size_ to 64M at least, if you have installed _igbinary_ switch _apc.serializer_ to _igbinary_.

Your autoload.php :
-------------------

{% highlight php %}
<?php
require __DIR__.'/../vendor/symfony/src/Symfony/Component/ClassLoader/ApcUniversalClassLoader.php';

use Symfony\Component\ClassLoader\ApcUniversalClassLoader;
use Doctrine\Common\Annotations\AnnotationRegistry;

$loader = new ApcUniversalClassLoader('sf2.apc.');
{% endhighlight %}

For more APC informations into Symfony2 you can install the [ApcProfilerBundle][3].


[1]: /2011/07/28/install-apc-on-osx-lion.html
[2]: http://pecl.php.net/package/igbinary
[3]: http://knpbundles.com/fr/stealth35/ApcProfilerBundle