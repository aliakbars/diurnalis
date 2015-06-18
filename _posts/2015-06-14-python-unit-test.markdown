---
layout: post
title:  "Python Unit Test"
date:   2015-06-14 22:24:23
categories: python
---

Test-driven development has become more prevalent these days. People started to realize that maintainable working code is more important than writing the documentation of the code. As for me, I started to write test cases for my codes after enrolling the [Design of Computer Program class][docp] on Udacity. On the course, you can see that writing unit test can really help you to breakdown the problem you are facing and how to think modularly.

The easiest way to write a unit test in Python is by using `assert`. You just need to declare the function with its parameters and then compare it with the predicted output. You can see the example below.

{% highlight python %}
def f(x, y):
	return x + y

assert f(1, 1) == 2
{% endhighlight %}

It might look so simple, but believe me, it will help you that much in terms of solving the problems meticulously step by step.

Aside from `assert`, Python has a package module specifically designed for unit testing called [`unittest`][unittest]. The module is a actually a framework that can handle several things in terms of unit testing -- based on the site:

* test fixture: the preparation needed for testing, such as proxy database
* test case: the smallest unit of testing
* test suite: set of test cases used for integration testing, and
* test runner: a component which orchestrates the execution of the tests and provides the outcome to the user

The script for unit testing using the `unittest` module is basically consists of things like these:

{% highlight python %}
import unittest

class MyTest(unittest.TestCase):
	def setUp(self):
		# Where you define the preparation needed for testing, e.g. database

	def tearDown(self):
		# What to do after the test is completed

	def testCase1(self):
		# Test case #1

	def testCase2(self):
		# Test case #2
{% endhighlight %}

The interesting point of using the `unittest` module is that you can run the test cases arbitrarily. You can write it in a separate file, or just include it on the same file. Then, when you want to run the test, you just have to run this command from shell:

{% highlight bash %}
python -m unittest <your_test_file_name.py>
{% endhighlight %}

Believe me, it is a very good thing to write your own test cases beforehand, so that when you have to change the code, you can always check it easily whether it will work the same way or not. As I've been taught, this is the way of designing a computer program. The more test case you write, the more robust your code should be!

[docp]: https://www.udacity.com/course/viewer#!/c-cs212/l-48532737/e-48737202/m-48692640
[unittest]: https://docs.python.org/2/library/unittest.html