---
layout: post
title: Top 10 useful Python snippets!
date: 2018-01-09 10:12 -500
categories: Python
excerpt_separator: <!--more-->
---

Python is a very intuitive and flexible programming language. With it, you can tackle all types of problems that might come your way. On this article, I decided to post the most common snippets I use on my work as a Data Scientist.
<!--more-->

On this post, I'll show 10 snippets that can help you solve simple problems easier using Python and Jupyter Labs.

![_config.yml]({{ site.baseurl }}/images/posts/2020-01-09-Python_Codes/Jupyter_logo.png)

## Unique values on a list

Sometime we just want unique values from a list. There is a simple way to do that and it is using SET. On Python Sets.

Sets are just like Lists and Tuples, with the difference that they cannot have multiple occurrences of the same element and store unordered values.

More information on Sets can be found here, on the official doc page: https://docs.python.org/2/library/sets.html

```python
x = [1,2,2,3,2,4,5,3,5,6]
print(x)
```

    [1, 2, 2, 3, 2, 4, 5, 3, 5, 6]



```python
x = set(x)
print(x)
```

    {1, 2, 3, 4, 5, 6}
