---
layout: page
title: "Python"
description: "Python code snippets"
tagline: "{code snippets}"
---
{% include JB/setup %}

The "I can read my own code" programming language

## 1. Default functions

{% highlight python %}
# functional programing `functions`
# 'lambda' -> anonymous functions
lambda x: x + 1            # function object
myFunc = lambda x: x + 1   # assign function a name
print 'myFunc(3):', myFunc(3), '\n'
 
# 'map' change each element w/o a for loop
my_iterable = range(10)
my_iterable_plus_one = map(lambda x: x + 1, my_iterable)
print my_iterable, '->', my_iterable_plus_one, '\n'
 
# 'filter' remove elements that don't meet a criteria
print my_iterable, '->', filter(lambda x: x>5, my_iterable), '\n'  # keep elements greater than 5
 
# 'zip' pair each element with the same index in a second list
print my_iterable, '+', my_iterable_plus_one, '->', zip(my_iterable, my_iterable_plus_one)
{% endhighlight %}

myFunc(3): 4 

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9] -> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9] -> [6, 7, 8, 9] 

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9] + [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] -> [(0, 1), (1, 2), (2, 3), (3, 4), (4, 5), (5, 6), (6, 7), (7, 8), (8, 9), (9, 10)]

## 2. Basic python syntax

### 2.1 Generators

{% highlight python %}
def my_generator(my_list):
    for element in my_list:
        # make some arbitrary logic
        if element > 3 and element < 7:
            yield element
 
# iterate by using the generator
for i in my_generator(range(10)):
    print i
{% endhighlight %}
4

5

6

### 2.2 Repeating elements

{% highlight python %}
# repeat elements of a list
x = [0, 0, 0, 0, 0, 0, 0, 0]  # i hate typing long lists
y = [0] * 8  # much easier
print x, y
 
shout = 'shout'
print shout + '!', shout + '!' * 10
{% endhighlight %}
\[0, 0, 0, 0, 0, 0, 0, 0\] \[0, 0, 0, 0, 0, 0, 0, 0\]

shout! shout!!!!!!!!!!

## 3. Standard Modules

### 3.1 Argparse

Simple example of adding a cumstom validating action:

{% highlight python %}
import argparse


class ValidateInput(argparse.Action):
    def __call__(self, parser, namespace, values, option_string=None):
        error = True  # always think there is an error
       
        # if error print help and exit
        if error:
            parser.print_help()
            parser.exit(status=1,
                message='\n' + '#'*40 + '\nhey dummy your date did not work.\ncheck out the parameter usage above\n' + '#'*40 + '\n')
        
        # set value if no error, you could probably make the value a time
        # object using strptime 
        setattr(namespace, self.dest, values)  # set the value


parser = argparse.ArgumentParser()
parser.add_argument('-t', action=ValidateInput, help='testing')
args = parser.parse_args()
{% endhighlight %}
