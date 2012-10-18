---
layout: page
title: Hello my codes!
tagline: This site is a support for you.
---
{% include JB/setup %}


## R

In `Rdemos` remember to specify your own environment if under Linux:
    
      status: beginner 

The progress of learning is still unfinished. 
 
## Perl 

This blog contains sample codes which help learn bioinformatics and parse data.
When you don't need the samples anymore just delete the `MyBioPerl` folder.

      status: junior 

Here's a sample "list with bug".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

The progress of learning is still unfinished. 

## To-Do: Python

The progress of learning is still unfinished 
If you'd like to be added as a contributor, [please fork](http://github.com/YummyYang/MyBioPerl)!
We need to clean the codes, make them better.


