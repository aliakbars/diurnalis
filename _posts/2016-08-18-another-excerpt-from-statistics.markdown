---
layout: post
title:  "Another Excerpt from Statistics by Freedman, et al."
date:   2016-08-18 08:15:00
categories: statistics
---

> Charles Tart ran an experiment at the University of California, Davis, to demonstrate ESP. Tart used a machine called the "Aquarius." The Aquarius has an electronic random number generator, and 4 "targets." Using its random number generator, the machine picks one of the 4 targets at random; it does not indicate which. Then, the subject guesses which target was chosen, by pushing a button. Finally, the machine lights up the target it picked, ringing a bell if the subject guessed right. The machine keeps track of the number of trials and the number of correct guesses. Tar selected 15 subjects who were thought to be clairvoyant. Each of the subjects made 500 guesses on the Aquarius, for a total of 15 x 500 = 7,500 guesses. Out of this total, 2,006 were right. Can this be explained as a chance variation?

Important things to note:

1. \\(N = 7500\\)
2. \\(p = \frac{1}{4}\\)
3. \\(\mathbb{E}[x] = p \times N = \frac{1}{4} \times 7500 = 1875\\)
4. \\(\bar{x} = 2006\\)
5. \\(SE = \sqrt{N} \times \sqrt{p \times (1-p)} = \sqrt{7500} \times \sqrt{1/4 \times 3/4} = 37.5\\)

Therefore, we can calculate the \\(z\\)-statistics as follows:

$$
z = \frac{\bar{x}-\mathbb{E}[x]}{SE}
= \frac{2006 - 1875}{37.5}
= 3.49
$$

The observed value of 2,006 is 3.49 SEs above the expected value. And \\(P\\) is rather small:

![p-value](/assets/pvalue.png)

It's only \\(2 \times 10^{-4}\\)!

> The surplus of correct guesses is hard to explain away as a chance variation.

But, are they really clairvoyants? Well, not really.

> The random number generator may not be very good, or the machine may be giving the subject some subtle clues as to which target it picked.

![p-values](http://imgs.xkcd.com/comics/p_values.png)