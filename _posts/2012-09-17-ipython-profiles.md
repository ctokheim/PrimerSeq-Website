---
layout: post
title: "IPython Profiles"
description: "IPython profiles configure on startup"
category: "Code"
tags: [Python, IPython]
tagline: "{IPython + profile = profit}"
---
{% include JB/setup %}
IPython provides extensive configuration capabilities either for your own needs or for
specific projects. A more comprehensive documentation of IPython configuration can
be found [here](http://ipython.org/ipython-doc/stable/config/overview.html). Amidst the confusing 
but power capabilities of configuration file inheritance, there is a simple but useful 
feature called a profile. Profiles can easily be created by the following command.

    $ ipython profile create my_profile_name

This command should create and print the path where the profile is setup at. To use the profile
just specify the profile as an argument for ipython.

    $ ipython --profile=my_profile_name

Why would I create profiles? Well, most importantly you can create your own startup environment.

## Startup Files 

The `profile_<name>/startup` directory allows you to place any python `.py` files or ipython `.ipy` files so they can be
executed as soon as the ipython start. For example, I could have the following python file called `test.py` in the startup directory.

{% highlight python %}
# import modules you'll use
import re
import csv

# perform calculations, advanced eh?
baz = 5 + 6

# you can read in files if you want
with open('my_data.txt') as handle:
    my_data = list(csv.reader(handle))
{% endhighlight %}

Everything in the startup files can then be used without retyping them each time
you re-enter ipython.

{% highlight python %}
In  [1]: baz
Out [1]: 11
{% endhighlight %}

The advantage of valid python code as configuartion files is that considerable logic can
be constructed in them. Notice, a simple if statement could specify platform specific
code for an ipython profile. 

{% highlight python %}
import platform

if platform.system() == 'Linux':
    foo = 1
{% endhighlight %}

## Details

You can always find where the config files will be located by using the following command.

    $ ipython locate

If you would like to change the directory of the config files then set the `IPYTHONDIR` environment
variable. Profiles are located in the `IPYTHONDIR/profile_<name>` directory. If you want
to locate a specific profile then type the following.

    $ ipython locate profile <name>

## Conclusion

Profiles are incredibly flexible and as long as you know where to drop your `.py` and `.ipy` files
they are also incredibly easy to use.
