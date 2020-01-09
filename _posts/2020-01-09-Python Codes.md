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

More information on Sets can be found here, on the official doc page: [https://docs.python.org/2/library/sets.html](https://docs.python.org/2/library/sets.html)

``` python
myList = [1,2,2,3,2,4,5,3,5,6]
print(myList)
```

[1, 2, 2, 3, 2, 4, 5, 3, 5, 6]

``` python
myList_uniques = set(myList)
print(myList_uniques)
```

{1, 2, 3, 4, 5, 6}

## Checking duplications on a List

We can also use Sets to check if there are duplications on our list by checking the length of the original list and the length of that list. If they are the same, no duplications exists.

``` python
len(myList) == len(myList_uniques)
```
False

If the result is 'False', then the list has duplications.


## Slicing

Slicing is a important function to apply on list in general. It is used to select parts of the list rather then the entire object.

Here is our list
``` python
myList = ['Kirk', 'Spock', 'McCoy', 'Scott', 'Uhura', 'Chekov', 'Sulu']
```

You can select a single value:
``` python
myList[0:1]
```
['Kirk']

You can also omit the zero for a cleaner code:
``` python
myList[:1]
```
['Kirk']

You can select multiple values:
``` python
myList[2:5]
```
['McCoy', 'Scott', 'Uhura']
Note that Slicing #includes# the first element (position 2) and # excludes the last element (position 5)

You can skip every other position:
``` python
myList[:7:2]
```
['Kirk', 'McCoy', 'Uhura', 'Sulu']

You can go backwards in the list:
``` python
myList[::-1]
```
['Sulu', 'Chekov', 'Uhura', 'Scott', 'McCoy', 'Spock', 'Kirk']

## Repeating a String

Personally I use a lot a #Print# statements while working on Python and sometimes I need a way to separate all the print that are being displayed.
For that, I often use print('---'), but I also don't like to keep pressing '-' until I am satisfied.

There is a handy dandy way to print LOTS of dashes:
``` python
print('-'*100')
```
----------------------------------------------------------------------------------------------------

There you go. A ton of '-'
