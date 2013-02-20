---
layout: page
title: "Linux"
description: "Linux PrimerSeq installation guide"
tagline: "{Quick Installation Guide}"
---
{% include JB/setup %}

This installation instruction assumes you are using current versions of either
**Ubuntu** (>=12.04) or **Linux Mint** (13 Maya).

First, the [Java JRE](http://www.oracle.com/technetwork/java/javase/downloads
/java-se-jre-7-download-432155.html) **must** be installed on your computer.

You can decompress the download and install dependencies by using the below
commands from the linux terminal. The commands presuppose you have the
following.

* Default Python version of 2.7.x (standard in Ubuntu >=12.04)
* Super user access

{% highlight bash %}
$ wget https://github.com/ctokheim/PrimerSeq/archive/v1.0.1.beta.tar.gz
$ tar xvzf v1.0.1.beta.tar.gz
$ cd PrimerSeq-1.0.1.beta
$ sudo ./install.ubuntu.sh
{% endhighlight %}

You may need to confirm installation of packages downloaded by the *install.ubuntu.sh* script by pressing the "y" key.
If you are missing dependencies, you can generally install them by using *sudo
apt-get install*.

{% highlight bash %}
$ sudo apt-get install pkg-name
{% endhighlight %}

wxPython can be difficult to install so it may have to be done manually. Please follow http://wiki.wxpython.org/How%20to%20install%20wxPython

## Start PrimerSeq

Start PrimerSeq by **double clicking** the *PrimerApp.py* file in the top level directory or run through the command line.
For directions on running example data please see the [getting started](getting_started.html)
page.

{% highlight bash %}
$ ./PrimerApp.py
{%  endhighlight %}
