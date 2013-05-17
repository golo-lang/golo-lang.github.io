---
layout: news
title: "Now available: Golo 0-preview4"
---

![](http://farm9.staticflickr.com/8399/8609710983_0593451e63_z_d.jpg)

Golo `0-preview4` is now available!

You might ask why the previous release was `0-preview2` while we directly announce `0-preview3`...

Well, the embarassing story is that a Git merge of an upstream branch had been forgotten while the Maven artifacts had already been released, meaning that there was no way back. Mistakes happen, hence we have the rare chance of having 2 successive releases in a single day!

### What's new in Golo?

* Multi-line strings can now be defined. They are delimited between `"""`.
* Local functions can now be called from augmentations from the same module.
* JVM arrays can now be manipulated as objects with methods such as `get(index)` or `length()` instead of predefined functions (e.g., `aget(array, index)` and `alength(array)`).
* JVM arrays now work in `foreach` loops, because they provide an `iterator()` method.
* The compiler no longer blocks on non-terminated source code. *(woops)*
* Some refactorings in the standard augmentations, including a `join()` method on lists contributed by Daniel Pétisme.
* Closures with a variable number of arguments were broken when context was captured.
* Philippe Charrière contributed a new `readln` function.
* ...and many small fixes there and there.

We are particularly proud to have 3 new contributors: Dan Allen, Daniel Petisme and our famous developer advocate Philippe Charrière!

### In the community

* The Golo Netbeans plugin developed by David Festal at Serli is now available directly from Netbeans.
* The Eclipse tooling by Jeff Maury is making good progress, [see the forum discussion](https://sourceforge.net/p/golo-lang/discussion/users/thread/4051ba57/).

### Links

* [Try Golo on Google AppEngine](http://golo-console.appspot.com/)
* [Download a preview release of Golo](/download/)
* [Read the Golo programming language guide](/documentation/next/)
* [Fork the project on GitHub](https://github.com/golo-lang/golo-lang)
