---
layout: news
title: 'Golo news roundup #3'
---

![Spring is here. Not the legacy framework of the 2000's, though.](http://farm9.staticflickr.com/8253/8675581636_fe19eb17db_z.jpg)

### Changes in Golo

* We released [Golo 0-preview2](http://golo-lang.org/download/) last week. It includes bug fixes.

* Notable changes in `0-preview2` include the new `orIfNull` and `?:` (*"elvis"*) operators to ease writing `null`-safe code.

* GitHub issues have been [filled with ideas tagged `backlog`](https://github.com/golo-lang/golo-lang/issues?labels=backlog&milestone=&page=1&state=open) to keep track of interesting enhancements and features. We invite potential contributors to have a look, as their help is welcome! Don't worry about hacking Golo, it is easier than you think and we can mentor you.

* Dealing with Java / JVM arrays from Golo is a pain. There is an open pull-request that [adds methods to arrays](https://github.com/golo-lang/golo-lang/pull/21), which hopefuly makes it easier to deal with them. In particular, the `iterator()` method allows arrays to be seamlessly used with `foreach` loops, too.

* Thierry Chantier reported problems to call methods from Java libraries that took a primitive `boolean` as a parameter. [Wooops!](https://github.com/golo-lang/golo-lang/commit/c1907540380782cccacd64102ccdeb6dee6664c7)

### In the community

* Marcin Erdmann just [released the first version of the Golo Gradle plugin](http://blog.proxerd.pl/article/gradle-golo-plugin-released). The plugin is part of the Golo organization on GitHub, and binaries are being pushed under the `org.golo-lang` group to Maven Central. Enjoy, and congratulate Marcin for his work!

* Jeff Maury has started work for the [Golo Language Development Tools in Eclipse](https://github.com/jeffmaury/gldt). Do not hesitate to give it a try and give Jeff feedback!

* Some recent geek things by our mad *Golo Developer Advocate* Philippe Charrière:
  - he updated the IntelliJ syntax highlighting and SublimeText support,
  - he created [kgolo](https://github.com/k33g/kgolo),
  - he is busy preparing a lightning talk at [Mix-IT 2013](http://www.mix-it.fr/).

* Thierry Chantier published a few blog posts on [how he has fun switching lights on and off from a RaspberryPi... and Golo](http://titimoby.herokuapp.com/blog/2013/04/21/pig-2-first-interaction/)

* Romain Lespinasse has updated his [Golo on OS X](https://github.com/rlespinasse/golo-on-osx) project.

* Daniel Petisme has started testing ideas with a set of standard augmentations for Golo, including collections and testability. Check out his [GoloSA](https://github.com/danielpetisme/golosa) project and give him feedback! He also opened a [pull-request for adding `join()` to lists](https://github.com/golo-lang/golo-lang/pull/20) which is pending acceptance of our *contributor license agreement*.

That's all folks!
