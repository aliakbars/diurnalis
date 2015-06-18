---
layout: post
title:  "I Just Can't Stop Learning - Flask"
date:   2014-12-03 18:50:21
categories: python flask
---

It seems like my mind keeps pushing me to learn something new. I haven't even done learning Ruby on Rails yet, but I've been attracted to learn Python Flask now. Since I now Python better than Ruby, I just can't resist to at least deploy a "Hello, World!" project to Heroku. You can find it [here][flask.ali].

[Flask][flask] is defined as a microframework. As written on their site, a minimal Flask application can be written in just a very few lines:

{% highlight python %}

from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello World!'

if __name__ == '__main__':
    app.run()

{% endhighlight %}

See? That's much easier than writing a [Django][django] app.

However, since Flask is really simple, the codes can easily be spaghetti. Furthermore, Flask does not come with Cross-Site Request Forgery (CSRF) protection. It is stated clearly on their page:

> Why does Flask not do that for you? The ideal place for this to happen is the form validation framework, which does not exist in Flask.

So, I guess it is better to use Flask just as it is intended to in the very first place: simple web app. Nevertheless, when you have to deal with forms or complex algorithm, then Django will come in handy.

[flask.ali]: http://flask.aliakbars.com
[flask]: http://flask.pocoo.org/docs/0.10/
[django]:https://www.djangoproject.com/