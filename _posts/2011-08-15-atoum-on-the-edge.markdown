---
layout: post
title: atoum on the edge
---

[atoum][1] is a new great unit testing framework, is simple and elegant.
Distribute in a phar archive you can easily insert it in your project.

[![atoum logo](http://downloads.atoum.org/images/logo.png)](http://blog.mageekbox.net/?tag/Atoum)

A simple way to make the phar form github's source and test it :

{% highlight bash %}
git clone git://github.com/mageekguy/atoum.git
php -dphar.readonly=0 atoum/scripts/phar/generator.php -d ./
php mageekguy.atoum.phar -d atoum/tests/units
{% endhighlight %}

_* atoum image by [mageekguy][3]_

[1]: https://github.com/mageekguy/atoum
[2]: http://blog.mageekbox.net/?tag/Atoum
[3]: http://blog.mageekbox.net