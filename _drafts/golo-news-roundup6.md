---
layout: news
title: 'Golo news roundup #6'
---

![Philippe at the Montpellier JUG](http://distilleryimage0.s3.amazonaws.com/d7e5fc0ed90b11e2a0d822000a1f9a12_7.jpg)

*(Philippe at the Montpellier JUG, instagram courtesy of Christophe Hamerling)*

### What's new in Golo?

**... a lot! :-)**

#### Small changes

* The Golo Jar now comes with proper OSGi meta-data. We made limited tests with it inside an OSGi
container and it seems to be working fine. The bundle configuration exports all Golo packages, so it
should run fine as a library. Note that we do not expose any OSGi service.

* We made another round of bug fixes regarding function parameters and closure reference capture. We
now enforce parameters to be constant references, so any attempt to re-assign a parameter will yield
an error. In short: a function parameter is a `let`, and captured references are, too. We also
improved the related compilation error reporting along the way.

* Boolean expressions are now partially evaluated, which is what any sound language should be doing
anyway. This means that expressions such as `(false and null: plop())` will properly return `false`
instead of evaluating the right expression. In this case this would also throw
a `NullPointerException`, which is not what you would expect.

