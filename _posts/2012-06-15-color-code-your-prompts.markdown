---
layout: post
title:  "Color code your prompts"
date:   2012-06-30 23:59:59 +1100
categories: jekyll update
---

Having access to too many different servers opens the door for its own set of problems. If you're not careful you can accidentally bring up a command prompt window where you have SSHed into a production environment and start causing havoc unintentionally.

For this problem I have color coded the prompts on the different servers I work with. This way I can instantly see where I'm at when I bring up a terminal window. It's mighty handy, really.

My most used ones look something like this.

<img src="{{ site.url }}/assets/color-code-your-prompts.png">

Just add one of these to your `.bashprofile`/`.bashlogin`/`.bashrc` (whichever exists, or any if none exist):

{% highlight shell %}
# for friendly cyan
PS1=\\\[\\e\]0\;\\w\\a\\\]\\n\\\[\\e\[36m\\\]\\u@\\h\ \[\\\[\\e\[37m\\\]\\w\\\[\\e\[36m\\\]\]\\\[\\e\[0m\\\]\\n\\t\ \\\$\
# for watchout yellow
PS1=\\\[\\e\]0\;\\w\\a\\\]\\n\\\[\\e\[33m\\\]\\u@\\h\ \[\\\[\\e\[37m\\\]\\w\\\[\\e\[33m\\\]\]\\\[\\e\[0m\\\]\\n\\t\ \\\$\
# for careful now red
PS1=\\\[\\e\]0\;\\w\\a\\\]\\n\\\[\\e\[31m\\\]\\u@\\h\ \[\\\[\\e\[37m\\\]\\w\\\[\\e\[31m\\\]\]\\\[\\e\[0m\\\]\\n\\t\ \\\$\
{% endhighlight %}

___Note:___ _each of the above lines end in "\ " (backslash, space)._ 
