---
layout: post
title:  "Google Chart API"
date:   2014-07-07 15:01:00
categories: google api
---

Google makes almost every part of development tools nowadays. And this chart API is one of those pretty cool stuff. Drawing live chart with tooltips is piece of cake with this API.

It all started when I was looking for a library to draw charts on PHP. I've been using [pCharts][pchart] for some time. However, it is very difficult for me to include it in my CodeIgniter framework. Furthermore, I'm moving to Django now, so I really need to move from pCharts.

Then, I came across [Chartkick][chartkick]. It's simply mesmerizing. It's free, but rich and powerful. I just need to include one Javascript file and Google API Javascript, and then everything will be as simple as one line on the front-end. Here's an example:

{% raw %}
	{% line_chart data %}
{% endraw %}

That's it.

Pretty cool, eh?

You should really look for it. You'll be amazed by how simple drawing charts can be. Go to [Google Charts API page][gcharts] and explore it yourself!

[pchart]: http://pchart.sourceforge.net/index.php
[chartkick]: http://chartkick.com/
[gcharts]: https://developers.google.com/chart/