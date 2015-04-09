---
layout: post
title: Learning Scheme - car, cdr and cons
category: computer
tags: [scheme,lisp,SICP]
---

`car` is the first S-expression of this **non-empty** list. 

```scheme
(a b c)       ;car is a
((a b c) d e) ;car is (a b c)
hotdog        ;there is no car as this is an atom
```

If `l` is `(((hotdogs)) (and) (pickle) relish)`, then `(car l)` will be `((hotdogs))`, because `(car l)` is another way to ask for *the car of the list l*. And this is recursive : `(car (car l))` will be `(hotdogs)`.

`cdr` (pronounced *could-er*) is the list which holds the left part of a list after cdr. Example

```scheme
(a b c)          ;cdr is (b c)
((a b c) x y z)  ;cdr is (x y z)
(ham)            ;cdr is ()
```
Obviously, there is no answer if `cdr` is used on an atom or an empty list.

If `l` is `((b) (x y) ((c)))`, more examples:

```scheme
(car (cdr l))    ;(x y)
(cdr (cdr l))    ;(((c)))
```

The `cons` of the atom `a` and the list `l` where a is `peanut` and`l` is `(butter and jelly)` is `(peanut butter and jelly)`, it reads *cons the atom a onto the list l*. What it does is to add a s-expression to the front of a list (or it takes two arguments:the first one is any S-expression; the second one is any list). So the `cons` of `s` and `l` where `s` is `(banana and)` and `l` is `(peanut butter and jelly)` is `((banana and) peanut butter and jelly)`.


