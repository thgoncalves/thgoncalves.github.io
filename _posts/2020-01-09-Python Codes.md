---
layout: post
title: Top 10 useful Python snippets!
date: 2018-01-09 10:12 -500
categories: Python
excerpt_separator: <!--more-->
---

Python is a very intuitive and flexible programming language. With it, you can tackle all types of problems that might come your way. On this article, I decided to post the most common snippets I use on my work as a Data Scientist.
<!--more-->

On this post, I'll show 10 snippets that can help you solve simple problems easier using Python and Jupyter Labs. There is no particular order here, just a collection of snippets.

Enjoy :)

![_config.yml]({{ site.baseurl }}/images/posts/2020-01-09-Python_Codes/Jupyter_logo.png)

## 1) Unique values on a list

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

## 2) Checking duplications on a List

We can also use Sets to check if there are duplications on our list by checking the length of the original list and the length of that list. If they are the same, no duplications exists.

``` python
len(myList) == len(myList_uniques)
```
False

If the result is 'False', then the list has duplications.


## 3) Slicing

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

## 4) Repeating a String

Personally I use a lot a #Print# statements while working on Python and sometimes I need a way to separate all the print that are being displayed.
For that, I often use print('---'), but I also don't like to keep pressing '-' until I am satisfied.

There is a handy dandy way to print LOTS of dashes:
``` python
print('-'*100')
```
"----------------------------------------------------------------------------------------------------"

There you go. A ton of "-"

## 5) Enumerate

Sometimes you may want to iterate over a list and you also need to get its position. We can use Enumerate for that:

There is a handy dandy way to print LOTS of dashes:
``` python
for counter, item in enumerate(myList):
    print(counter ,' - ',item)
```
0  -  Kirk

1  -  Spock

2  -  McCoy

3  -  Scott

4  -  Uhura

5  -  Chekov

6  -  Sulu

## 6) Enhancing Print function

Sometimes we want to add variables to a print statement along with some explanation text. Before Python 3, we used to write the print like this:

``` python
var1 = 50
var2 = 10
div = var1/var2

print('The division of %r by %r is %r' % (var1, var2, div))
```
The division of 50 by 10 is 5.0

But now you can also use the following syntax:
``` python
print(f'The division of {var1} by {var2} is {div}')
```

## 7) Measure execution time

It is common to have a specific code running for quite a long time. That is specially true when working with large datasets of with Neural Networks, for example.

There is a Magic Function that can be used to display the total run time a cell used: _%%time_

``` python
%%time
import time

for i in range(0,10):
    print(i, end=' ')
    time.sleep(0.5)
print('')
```
0 1 2 3 4 5 6 7 8 9

CPU times: user 11.2 ms, sys: 3.93 ms, total: 15.2 ms

Wall time: 5.03 s

The function above counts from 0 to 9 and waits 0.5 seconds on each iteration. At the end of the code, you can see the output of the %%time function displaying a Wall time of about 5 seconds

## 8) Speaking of Time

There are 3 main variation of the Magic Function _time_. Bellow I'll explain the difference between them:
1) %%time (two %)
  - This was the function used above. It calculates the total execution time for the entire cell. It will only be displayed once the cell finishes running.
  - For this function to run without errors, #it must be the first code on the cell#. Nothing can come before it.
2) %time (one %)
  - This also displays execution time but only for the code that preceeds it and not for the entire cell
  - here is an example using the same function
  
  ``` python
  import time

  for i in range(0,2):
      print(i)
      %time time.sleep(0.5)
  ```

  0
  CPU times: user 1.37 ms, sys: 1.64 ms, total: 3.01 ms</br>
  Wall time: 504 ms</br>
  1</br>
  CPU times: user 1.18 ms, sys: 249 µs, total: 1.43 ms</br>
  Wall time: 504 ms</br>

  We can see that each sleep code took about 500ms, exactly what it should've taken

3) %timeit
  - This one is a little bit different. It evaluates the code over multiple runs and depends on the code it self.
  - On the example above:
  ``` python
  %%timeit
  import time

  for i in range(0,10):
      print(i, end=' ')
      time.sleep(0.1)
  print('')
  ```
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  0 1 2 3 4 5 6 7 8 9</br>
  1.04 s ± 434 µs per loop (mean ± std. dev. of 7 runs, 1 loop each)</br>

  - On a code without a sleep function, this is what we get
  ``` python
  %%timeit
  import time

  for i in range(0,10):
      pass
  ```
  569 ns ± 2.69 ns per loop (mean ± std. dev. of 7 runs, 1000000 loops each)</br>
  - This time, the code ran for a total of 1.000.000 loops

## 9) Print on the same line

Going back to the print function, there is a few handy options that may be of help.

Print on the same line: You can define how the Print statement will end. The default value is \n (new line character).
If you force the end attribute to be, for example ' ' (space), the print will not go to the next line. Instead it will just add a space and print the next value (if inside a loop).
``` python
for i in range(0,10):
    print(i, end=' ')
```
0 1 2 3 4 5 6 7 8 9


## 10) Print with special character separation
Another attribute on the Print function is Sep. It basically adds a chosen character between prints:

``` python
print('1','2', '3', sep='-')
```
1-2-3

---

These are my 10 most used snippets. I hope those can be useful for you as they are for me.

See you later.
