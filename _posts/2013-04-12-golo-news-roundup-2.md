---
layout: news
title: 'Golo news roundup #2'
---

![We have stairs, too](http://farm9.staticflickr.com/8528/8641498887_4fc69b671a_z.jpg)

### Changes in Golo

We have yet to release a `0-preview2` version, but meanwhile you can build Golo yourself from the Git `master` branch.

* Golo had to have `break` and `continue` statements which are very helpful when used wisely in imperative programming. In each case they operate at the inner-most loop level. Java offers `break` to labels, which is a `goto` in disguise. Golo does not support this.

* There were bugs with the capture of references in nested closure structures. If you had encountered weird behaviors with variables not being captured then the current `master` branch shall definitely have it fixed.

* Sylvain Desgrais [opened a pull request with investigations around native code integration](https://github.com/golo-lang/golo-lang/pull/7). His first experiment is around a new `native` keyword that would help with JNI. Join the discussion on the pull request, as we need to think about JNI versus [JNA](https://github.com/twall/jna) that could maybe be a better option.

* The `pimp` keyword has been changed to `augment` so as to accomodate cultural diversity around the world. We initially chose `pimp` in reference to its clean roots in French, which are anything but offending. Anyway, some people in the world prefer songs with *beeps* and *blanks* on the `f***` word, so switching to `augment` will definitely make them happy. If you had Golo code with the `pimp` keyword you are invited to migrate to `augment`, but the parser still understands `pimp`.

* Our GitHub repository is now [integrated with Travis-CI](https://travis-ci.org/golo-lang/golo-lang) for continuous integration. Any code push or pull request will be checked against OpenJDK 7 and Oracle JDK 7. Travis-CI is an awesome project!

### In the community

* [Golo made the news in the Java Source Oracle blog](https://blogs.oracle.com/java/entry/golo_a_lightweight_dynamic_language), which happens to be one of the most popular Oracle blog.

* David Festal [posted the Netbeans plugin](http://plugins.netbeans.org/plugin/48098/golo-netbeans-module). You can download it from there, but it still needs signature to be available directly from within Netbeans. The latest versions of Netbeans still require Java 6 compatibility, so David will need to tweak the plugin for that.

* Julien Viet [opensourced a Vertx / Golo integration](https://github.com/vietj/vertx-golo). This looks very promising!

* Daniel Petisme [opensourced a Golo plugin for Jenkins](https://github.com/danielpetisme/golo-plugin). Thanks Daniel!

* Jeff Maury [is investigating a Golo plugin for Eclipse](https://sourceforge.net/p/golo-lang/discussion/users/thread/4051ba57/). Eclipse is definitely a popular IDE, so having both Netbeans and Eclipse IDE integration would be awesome for the adoption of Golo. IntelliJ IDEA support already exists in the form of syntax highlighting thanks to Philippe Charriere.

* Philippe Charriere [posted a DropBox link with a TextMate / ChocolatApp bundle](https://t.co/zPYg8JoZx5). While it needs further work, it is a very good start in those editors.

* Philippe Charriere [experimented with a script / class loading tool called JGolo](https://github.com/k33g/jgolo). It clearly shows how easy it is to embed Golo.

* Yannick Loiseau [posted a very good article (in French) to explain functional programming terminology](http://yloiseau.net/articles/functionnal/). Lambda, closures, partial application, currying... they are all explained in simple terms with examples in Python, OCaml, JavaScript... and Golo!

Stay tuned for more Golo news! Feel-free to share interesting news that we could have missed.
