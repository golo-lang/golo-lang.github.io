---
layout: news
title: "Golo News Roundup #7"
---
![](http://farm3.staticflickr.com/2855/9575085125_db919fdd2d_o_d.jpg)

As you probably know from the last post, we were on holidays, and holidays are all about **not** working.

While there hasn’t been a flow of commits to Golo, we are far from having no news to share with you…

### Golo in Conferences

Golo will appear at 3 events this fall.

- Our research team has a paper accepted at [PPPJ 2013](http://pppj2013.dhbw.de) in early September. If you are interested in reading the paper, your favorite search engine is your very best friend.
- Our never-sleeping Golo Developer Advocate Philippe is going to share his passion for Golo at [Soft-Shake](http://soft-shake.ch/2013/program/sessions/13_java/2013/10/24/06-Golo.html) in late October.
- Julien got accepted for a tools in action session at (the real) [Devoxx](http://devoxx.be/dv13-julien-ponge.html?presId=3475) in mid-November.

### How about actual code?

- Dynamic objects can now support variadic argument methods. It did not work previously because of how we dispatched method handle invocations.
- Daniel Petisme relaxed the Golo parser on newlines in `case` and `match` statements, allowing liberal linebreaks and comments.
- Thierry Chantier joined as a contributor with a small new `fileExists` function (there has to be a start!).
- Philippe has been playing on several fronts recently:
  - [Champollion](https://github.com/k33g/champollion) is a small lexer / parser ported to Golo,
  - [Bozzo](https://github.com/k33g/bozzo) is a JSON parser written using Champollion,
  - [GolOO](http://goloo-framework.appspot.com) is a minimalist framework for [Google AppEngine](https://appengine.google.com).

### Leaving SourceForge

We were using a small number of services from SourceForge: file releases and forums. Recent policy changes are inherently bad, so we are leaving.

We have already [migrated to Google Groups](http://groups.google.com/group/golo-lang) *(hint: join us!)*.

Distribution releases are likely to happen through Maven Central, too. Our Maven POM has already been updated to attach the distribution assemblies as artifacts, meaning that they can be deployed to Maven repositories.

The later choice is not definite, though, so feel-free to suggest alternatives! As long as it can be automated with no efforts and that the service is solid, we will consider it.

*Until next time, happy Golo-ing!*
