---
layout: post
title:  "Dates are hard!"
date:   2016-02-29 22:27:37 +1100
categories: jekyll update
---

It's February 29, so lets talk about it. It is such a fun edge case when dealing with dates.

### Math with dates

Adding minutes, days or even weeks to a date is straight forward enough. In Python,
we can use `timedelta` for this.

{% highlight python %}
>>> # One week from today is:
>>> date(2016, 2, 29) + timedelta(days=7)
datetime.date(2016, 3, 7)
{% endhighlight %}

But `timedelta` does not operate in months or years. So we must use the average
lengths in days, i.e. 365.242 days per year, and 30.43683333 days per month.

{% highlight python %}
>>> # Four years from today is:
>>> date(2016, 2, 29) + timedelta(days=4*365.242)
datetime.date(2016, 3, 7)
{% endhighlight %}



Intuitively we can add 1 month to Feb 29, and most people could agree that
the result is March 29.

{% highlight python %}
>>> today = date(2016, 2, 29)
{% endhighlight %}

But there are 'edge' cases we would need to get agreement on.

What is January 30 plus 1 month?

- February 30 does not exist.
- February 29 is the last day of February _this year_, is that close enough?
- Is March 1 more appropriate substitute for February 30?
- Maybe we would prefer February 28. Maybe we are targeting the  second last day of next month.
