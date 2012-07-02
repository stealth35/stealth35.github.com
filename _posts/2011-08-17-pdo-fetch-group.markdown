---
layout: post
title: Fetching groups with PDO
---

PDO offers a very usefull option in it's fetchMode : __PDO::FETCH_GROUP__ which allows you to group entries by category.

Table Example:
--------------

{% highlight html %}
test_user :
+----+-----------+----------+-------+
| id | firstname | lastname | city  |
+----+-----------+----------+-------+
|  1 | Jean      | Machin   | Paris |
|  2 | Jean      | Truc     | Nice  |
|  3 | Paul      | Bla      | Nice  |
+----+-----------+----------+-------+
{% endhighlight %}

{% highlight php %}
<?php
$result = $pdo->query("SELECT u.city, u.id, u.firstname, u.lastname FROM test_user u")
              ->fetchAll(PDO::FETCH_ASSOC | PDO::FETCH_GROUP);
?>
{% endhighlight %}

Result (in YAML) :
------------------

{% highlight yaml %}
Paris:
    - { id: 1, firstname: Jean, lastname: Machin }
Nice:
    - { id: 2, firstname: Jean, lastname: Truc }
    - { id: 3, firstname: Paul, lastname: Bla }
{% endhighlight %}

With another query :
--------------------

{% highlight mysql %}
SELECT u.firstname, u.id, u.lastname, u.city FROM test_user u
{% endhighlight %}

{% highlight yaml %}
Jean:
    - { id: 1, lastname: Machin, city: Paris }
    - { id: 2, lastname: Truc, city: Nice }
Paul:    
    - { id: 3, lastname: Bla, city: Nice }
{% endhighlight %}
