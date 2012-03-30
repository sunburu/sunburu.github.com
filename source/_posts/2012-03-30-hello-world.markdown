---
layout: post
title: "Hello World"
date: 2012-03-30 16:11
comments: true
categories: 
---

前言 ： 第一次用 otcopress, 先学习一下常用的markdown语法吧。

## 几种用Octopress 贴贴HelloWorld的代码

### Backtick Code Blocks

Syntax

    ``` [language] [title] [url] [link text]
    code snippet
    ```

Example (plain)

    ```
    $ sudo make me a sandwich
    ```
    
```
$ sudo make me a sandwich
```

### Gist Embedding

Syntax

		{% gist gist_id [filename] %}
    
Example

{% gist 996818 %}

### Include Code Snippets

Syntax

	{% include_code [title] [lang:language] path/to/file %}
    
Example 1

This includes a file from >source/downloads/code/test.js .

    {% include_code hello.c %}
    
{% include_code hello.c %}

Example 2

    {% include_code Add a title here hello.c %}

{% include_code hello.c %}

Example 3 (Force Highlighting)

    {% include_code test.coffee lang:coffeescript %}
    
{% include_code hello.c lang:c %}

### Inline Code Blocks

Syntax

    {% codeblock [title] [lang:language] [url] [link text] %}
    code snippet
    {% endcodeblock %}
    
Example 1

    {% codeblock %}
    Awesome code snippet
    {% endcodeblock %}

{% codeblock %}
Awesome code snippet
{% endcodeblock %}

Example 2

    {% codeblock lang:shell %}
    ls -a
    {% endcodeblock %}
    
{% codeblock lang:shell %}
ls -a
{% endcodeblock %}

Example 3

    {% codeblock Time to be Awesome - awesome.rb %}
    puts "Awesome!" unless lame
    {% endcodeblock %}
    
{% codeblock Time to be Awesome - awesome.rb %}
puts "Awesome!" unless lame
{% endcodeblock %}

Example 4 (Force Highlighting)

    {% codeblock Javascript Array Syntax lang:js http://j.mp/pPUUmW MDN Documentation %}
    var arr1 = new Array(arrayLength);
    var arr2 = new Array(element0, element1, ..., elementN);
    {% endcodeblock %}
    
{% codeblock Javascript Array Syntax lang:js http://j.mp/pPUUmW MDN Documentation %}
var arr1 = new Array(arrayLength);
var arr2 = new Array(element0, element1, ..., elementN);
{% endcodeblock %}

he last argument >link_text is optional. You may want to link to a source for download file, or documentation on some other site.

