---
layout: page
title: "PHP"
description: "PHP code snippets"
tagline: "{code snippets}"
---
{% include JB/setup %}

## SQL Implode

I always found it obnoxious to write a long SQL insert statement in PHP. Typically I would write
out each of the field names and there values something like this

{% highlight php %}
// preprocess and sanitize
$name = "John";
$email = "john@example.com";
$msg = "Hello World!!!";

// make SQL statement
sql = "
        INSERT INTO `table` (`name`, `email`, `msg`)
        VALUES ('$name', '$email', '$msg')
";
{% endhighlight %}

A much better way to craft these SQL statements is done by using the PHP implode function.

{% highlight php %}
// preprocess and sanitize
$data = arrray(
    "name"  => "John",
    "email" => "john@example.com",
    "msg"   => "Hello World!!!"
);

// fields and values will adjust to what ever is in $data
$fields_sql = '`' . implode("`, `", array_keys($data)) . '`';
$values_sql = "'" . implode("', '", $data) . "'";

// More flexible method for creating SQL statement
sql = "
    INSERT INTO `table` ($fields_sql)
    VALUES ($values_sql)
    ";
{% endhighlight %}



