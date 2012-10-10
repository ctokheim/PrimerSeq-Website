---
layout: post
title: "Jekyll-Bootstrap How-To"
description: ""
category: 
tags: [Jekyll, Jekyll-Bootstrap, Twitter Bootstrap]
tagline: "{Plz Helpz}"
---
{% include JB/setup %}

## Install 

Install git if you have not already:

    $ sudo apt-get install git

Next, grab jekyll-bootstrap from github:

    $ git clone https://github.com/plusjade/jekyll-bootstrap.git website 
    $ cd website 

Alternatively grab my website powered by jekyll-bootstrap from github:

    $ git clone https://github.com/ctokheim/website.git
    $ cd website

Install ruby:

    $ sudo apt-get install ruby

Install jekyll:

    $ sudo gem install jekyll

Install rake:

    $ sudo apt-get install rake

For python syntax highlighting you need to install pygments

    $ sudo apt-get install python-pygments

Next you have to generate the css highlighting file

    $ pygmentize -S default -f html > path/to/your/css

Make sure you include the cascading style sheet in your `_includes/themes/twitter/default.html` file.

## Usage

The files you will actually put on your website is found in the `_site` directory. Generating the
html files just requires the following command:

    $ jekyll --server --auto

When you change a file it will regenrate the files in the `_site` directory until you stop it with ^C.
Sometimes I have to stop and restart for it to regenerate the files in the `_site` directory. 

To create a page just type:

    $ rake page name="path/to/page.md"

Notice you only need to write the content and it is in markdown! If you haven't used markdown before
you can find more information [here](http://daringfireball.net/projects/markdown/). Essentially
markdown provides easier syntax for basic html markup. Other files whether they are html, pdf, php, etc ...
just get copied with out processing under the default setup.

You can also create a post by typing:

    $ rake post title="my post name"

The created markdown file will have meta information that you can provide at the top of the page:

    ---
    layout: post
    title: "Getting Rid of ^M"
    description: "Getting rid of windows ^M characters"
    category: 
    tags: [unix]
    tagline: "{the easy way}"
    ---
    {% include JB/setup %} 

Notice, the above information is for a post. A page would have a `layout: page`.

## Edit

Edit the `_includes/themes/[theme-name]/default.html` file to change your site design. It will refer
to css/js/imgs in the `assets/themes/[theme-name]` by the directive \{\{ ASSET_PATH \}\}. I recommend
any assets that are in many of your web pages be in this ASSET_PATH directory.

To change things like your name or the ASSET_PATH (see above paragraph), edit the _config.yml file.

## Tips

Copy the contents of your `_site` directory to where you host your website when you are done
editing files.

Go to [jekyllbootstrap.com](http://jekyllbootstrap.com) for more details.

Highlighting python code is as simple as inserting code in a liquid tag:

{% highlight python %}
val = True
if val:
    print "hello world!"
{% endhighlight %}
