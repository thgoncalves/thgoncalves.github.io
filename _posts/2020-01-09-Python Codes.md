---
layout: post
title: Top 10 useful Python snippets!
date: 2018-01-09 10:12 -500
categories: Python
excerpt_separator: <!--more-->
---

Python is a very intuitive and flexible programming language. With it, you can tackle all types of problems that might come your way. On this article, I decided to post the most common snippets I use on my work as a Data Scientist.

<!--more-->
![_config.yml]({{ site.baseurl }}/images/posts/2020-01-09-Python_Codes/Jupyter_logo.png)

## Unique values on a list

{% highlight Python %}
  x = [1,2,2,3,2,4,5,3,5,6]
  x = set(x)
  print(x)
{% endhighlight %}
