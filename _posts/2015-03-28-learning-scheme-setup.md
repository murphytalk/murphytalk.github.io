---
layout: post
title: Learning Scheme - setup the environment
category: computer
tags: [scheme,lisp,SICP]
---

So I finally decided to read through [SICP](http://en.wikipedia.org/wiki/Structure_and_Interpretation_of_Computer_Programs), which is something maybe I should have done like 20 years earlier. The language [scheme](http://en.wikipedia.org/wiki/Scheme_%28programming_language%29) used in the book is a dialect of [Lisp](http://en.wikipedia.org/wiki/Lisp_%28programming_language%29).

It is quite often that Lisp is described as the Latin in the world of programming languages: very rarely you would have the chance to use it in your daily work, but it could become the inspiration leads to the mastering of the other programming languages. Well let's see what I can learn from this journey :)

People are recommending [DrRacket](http://en.wikipedia.org/wiki/Racket_%28programming_language%29#DrRacket_IDE) as the best IDE to learn scheme. I played it a little bit, it is truely very promising, but in order to let it to support the dialect used in SICP better, some little [tuning](http://www.neilvandyke.org/racket-sicp/) is necessary :

1. Put `#lang planet neil/sicp` as the first line in the script.
2. Choose "Determine language from source" from the bottom left dropdown list box, and then click run button (or press short-cut Ctrl-R).




