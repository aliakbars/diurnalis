---
layout: post
title:  "Tests of Significance"
date:   2016-07-23 19:20:00
categories: statistics
---

> A die is rolled 100 times. The total number of spots is 368 instead of the expected 350. Can this be explained as a chance variation, or is the die loaded?

*This problem and its solution are taken from Statistics by Freedman, et al. (1998).*

To answer that question, we first need to identify some important things:

1. \\(N = 100\\)
2. \\(E[x] = \mu = 3.5\\)
3. \\(\sigma = 1.7\\)
4. \\(\bar{x} = \frac{368}{100} = 3.68\\)
5. \\(SE = SD_{\bar{x}} = \frac{\sigma}{\sqrt{N}} = \frac{1.7}{\sqrt{100}} = 0.17\\)

Note that we can directly use \\(\sigma\\) (the population variance) to compute the standard error (or in this case we will use true standard deviation of the sample mean, instead). Therefore, we can know that the \\(z\\)-statistic is

$$
z = \frac{\mathsf{observed} - \mathsf{expected}}{SE}
= \frac{\bar{x} - E[x]}{SE}
= \frac{3.68 - 3.5}{0.17}
= 1.059
$$

> z says how many SEs away an observed value is from its expected value, where the expected value is calculated using the null hypothesis.

The \\(z\\)-statistic does not seem to be that big. However, we need to verify this using the *p-value*. To get this value, we can use cumulative distribution function as follows:

$$
\int P(\bar{x}|H_0)d\bar{x} = \phi(\bar{x};E[x],\frac{\sigma^2}{N}) = P(\bar{x}<E[x]|\mu=E[x])
$$

We can use the `norm.cdf` subroutine in [SciPy](http://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.norm.html) to compute this value. The code for this calculation is as follows:

{% highlight python %}
>>> from scipy.stats import norm
>>> norm.cdf(3.68, 3.5, 0.17)
0.85515992213265712
{% endhighlight %}

This shows that we cannot reject the null hypothesis, thus deeming this result due to chance variation.

> The observed significance level is the chance of getting a test statistic as extreme as, or more extreme than, the observed one. The chance is computed on the basis that the null hypothesis is right. The smaller this chance is, the stronger the evidence against the null.