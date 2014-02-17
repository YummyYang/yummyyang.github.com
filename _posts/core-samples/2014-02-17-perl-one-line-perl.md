---
layout: post
category : perl
tags : [perl ]
title: one line perl
tagline: code for test
---
{% include JB/setup %}
	One line perl is a magic code, looks like it is more useful than sed.
### background
  I have a mail list. named 'mail_list'.
{% highlight r linenos %}
a@b.com; c@d.com.cn; e@edu.com ...
{% endhighlight %}

so, at first, need split by '; '
{% highlight perl linenos %}
sed 's/; /\n/g' mail_list 
| perl -ne '/.*@.*?([^\.]+)\.(com|net|org|edu|cn|hk).*/i && print "\L$1\n" ' 
| sort | uniq -c | sort -rgk1 > provider_names
{% endhighlight %}

here is the content of provider_names:
{% highlight r linenos %}
     28 163
     20 gmail
     17 yahoo
     16 hotmail
     15 126
     13 ac
     8 sina
     ...
{% endhighlight %}

and we want to know the summary of first column:
{% highlight r linenos %}
awk 'BEGIN{sum=0}{sum+=$1}END{print sum}' provider_names
{% endhighlight %}
the result is 167.

and the other name maybe like this : 'bill gates' or 'Ballmer(CEO)'
then the count will use -v:
{% highlight r linenos %}
sed 's/; /\n/g' mail_list | grep -v '@' | wc -l
{% endhighlight %}
then result will equal the result of line of mail_list.

and lsat , this code will count the same mail provider:
{% highlight perl linenos %}
sed 's/; /\n/g' mail_list  | sort | perl -pe 's/.*@(.*)/lc($1)/ei' 
| sort | less | uniq -cd | sort -rgk1 > mail_provider
{% endhighlight %}

