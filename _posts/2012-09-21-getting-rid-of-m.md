---
layout: post
title: "Getting Rid of ^M"
description: "Getting rid of windows ^M characters"
category: 
tags: [unix]
tagline: "{the easy way}"
---
{% include JB/setup %}
## Short answer

Use the `dos2unix` command. If you do not have it then first use apt-get:

    $ sudo apt-get install dos2unix

Then run `dos2unix` 

    $ dos2unix file_of_interest.txt

Note, this will automatically replace your text file with the unix equivalent.

## Long answer

The ^M (cntrl-M) is a windows carrige return. The line ending could come as a result
of writing files in a programming language, say python.

{% highlight python %}
myFile = open('my_file.txt', 'w')
myFile.write( . . . )
{% endhighlight %}

Python might interperate that it needs a windows style line returns and thus add the ^M.
To prevent this try writing in binary mode.

{% highlight python %}
myFile = open('my_file.txt', 'wb')  # note the extra 'b' in 'wb'
myFile.write( . . . )
{% endhighlight %}

As you might have guessed, any file transfered from windows to unix may have this problem.
To fix it just use `dos2unix` as described in the short answer section. However since I 
use Vim, I typically open a file and fix it by `:%!dos2unix`.
