---
layout: news
title: 'Golo news roundup #4'
---

![Golo is everywhere.](http://farm8.staticflickr.com/7050/8689168816_9d88302181_z.jpg)

### What's new in Golo?

* JVM arrays (think `Object[]`) can now be manipulated as objects. We provide *methods* that make them look like normal objects: `get`, `set`, `length`, `equals`, `toString`, and... `iterator()`. This means that you can now uniformly iterate over an array with a `foreach`, just like you would do for a `java.util` collection. Don't you find it nicer than calling array-specific functions such as `aget`, `aset`, `alength`?

* A bunch of fixes made it to the Git `master` branch. `boolean` arguments of Java code would not be handled (woops!). We also changed the closure generated methods parameters ordering, so that closures with a variable arity can now properly capture their context. If this sounds a bit too technical then don't worry: it just means that we fixed a stupid bug.

* Daniel Petisme joins as a contributor, and his first pull-request made it into the code base: he added a `join` augmentation to `java.util.List`.

* The JNI / JNA investigations are [making progress on the pull request](https://github.com/golo-lang/golo-lang/pull/7#issuecomment-17214248) opened by Sylvain Desgrais. Why not join the discussion? We want **your** feedback!

### In the community

* We now have a `#golo-lang` IRC channel on FreeNode. Feel-free to hang out over here!

* The awesome [Ninja Squad provided us with stickers](/news/2013/04/29/viral-marketing-thanks-to-ninjasquad/) for maximal viral marketing.

* Thierry Chantier wrote about his [Golo HTTP server experiments](http://titimoby.herokuapp.com/blog/2013/04/26/golo-little-5/). Simple stuff works!

* As usual, we have *several* items from Philippe Charrière:
  - he experimented with dynamic proxies: [https://github.com/k33g/DynoGolo](https://github.com/k33g/DynoGolo)
  - he opened a new GitHub repository for his *Fast* web framework: [https://github.com/k33g/Fast20](https://github.com/k33g/Fast20)
  - he gave a lightning talk at Mix-IT 2013: [slides (in French)](https://dl.dropboxusercontent.com/u/21154141/www/GOLO_LT.pdf)

### Off next week!

The Golo main developer is on vacations next week, so expect *less* to happen on the development front.

See you soon!
