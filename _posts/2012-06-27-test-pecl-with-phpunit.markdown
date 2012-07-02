---
layout: post
title: Test PECL with PHPUnit
---

{% highlight xml %}
<phpunit
    backupGlobals="false"
    colors="true"
    processIsolation="true"
>
    <testsuites>
        <testsuite name="PHP PECL">
            <directory suffix=".phpt">./tests/</directory>
        </testsuite>
    </testsuites>
</phpunit>
{% endhighlight %}