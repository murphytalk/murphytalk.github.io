---
layout: post
title: Learning Scheme - null and eq
category: computer
tags: [scheme,lisp]
---

`'()` or `(quote ())` represents an empty or null list. The following returns true (i.e. `'t`) . Note `null?` only works for lists.

```scheme
(null? (quote()))
```

Similarly, `atom?` is the notation to check if the given parameter is an atom or not. It is defined in scheme as:

```scheme
(define atom? 
  (lambda (x)
    (and (not (pair? x))(not(null? x)))))
``` 

Note it should be defined like below in Common List:

```lisp
(defun atom? (x) (not (listp x)))
```
a1 and a2 are the same atom where a1 is Harry and a2 is Harry. The following returns true:

```scheme
(eq? a1 a2)
```
Note it is `e	q` in Common Lisp.

Both of the parameters must be *non-numeric* atoms.

