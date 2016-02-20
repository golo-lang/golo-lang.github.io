---
layout: news
title: "Golo News Roundup #10"
---

![Scenery around Lyon](https://farm9.staticflickr.com/8849/17905982216_5d080b8167_c_d.jpg)

We haven't taken time to write a roundup for the last few releases, so now is a good time to let our
community know what we are up to!

### What's on the master branch?

We haven't been idle since Golo `2.1.0` as we shifted the development towards `3.0.0` which will
require Java SE 8 as a runtime.

Here is a short recap of the upcoming changes in Golo `3.0.0`.

#### Java 8 and lambdas

[https://github.com/golo-lang/golo-lang/pull/193](https://github.com/golo-lang/golo-lang/pull/193)

Golo now adapts function references to Java 8 lambdas (_a.k.a._ [functional interfaces](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html)), as in:

{% highlight golo %}
list[1, 2, 3, 4, 5]:
  stream():
  map(|n| -> n * 10):
  reduce(0, |acc, next| -> acc + next)
{% endhighlight %}

#### Named arguments

[https://github.com/golo-lang/golo-lang/pull/250](https://github.com/golo-lang/golo-lang/pull/250)

Named arguments increase readability, and they are now coming to Golo:

{% highlight golo %}
struct Foo = {x, y}

# (...)

let f = |x, y| -> x - y
let r_1 = f(x=10, y=2)
let r_2 = f(y=10, x=2)
let foo = Foo(y="b", x="a")
{% endhighlight %}

Last but not least, named parameters work with Java APIs, too... as long as code has been compiled
with `javac -parameters`.

#### Easier adapter definition API

[https://github.com/golo-lang/golo-lang/pull/257](https://github.com/golo-lang/golo-lang/pull/257)

There is now a fluent API for those who were less comfortable with nested collections for describing adapters:

{% highlight golo %}
module sparky

import gololang.Adapters
import spark
import spark.Spark

function main = |args| {
  let sparkRouteAdapter = Adapter():
    extends("spark.Route"):
    implements("handle", |this, request, response| {
      return "Golo, world!"
    })
  let route = sparkRouteAdapter: newInstance("/hello")
  get(route)
}
{% endhighlight %}

#### Tagged unions

[https://github.com/golo-lang/golo-lang/pull/258](https://github.com/golo-lang/golo-lang/pull/258)

Also known as _sum types_, they complement `enum` and `struct` nicely:

{% highlight golo %}

# Option monad

union Option = {
  Some = {value}
  None
}

# Binary trees

union Tree = {
  Empty
  Leaf = { value }
  Node = { left, right }
}

# Cons-lists

union ConsList = {
  List = { head, tail }
  Empty
}

augment ConsList$Empty {

  function isEmpty = |this| -> true
  function head = |this| -> null
  function tail = |this| -> this
}

augment ConsList$List {
  function isEmpty = |this| -> false
}

{% endhighlight %}

Note that named arguments support is also interesting in terms of readability...

#### Function references are now boxed

[https://github.com/golo-lang/golo-lang/pull/261](https://github.com/golo-lang/golo-lang/pull/261)

Function references used to be instances of [MethodHandle](https://docs.oracle.com/javase/8/docs/api/java/lang/invoke/MethodHandle.html).

The development of named arguments proved this to be a bad abstraction, so we introduced a new
`gololang.FunctionReference` type.

The change is mostly transparent for existing code bases.

#### Proper LL(k) operators precedence

[https://github.com/golo-lang/golo-lang/pull/265](https://github.com/golo-lang/golo-lang/pull/265)

The operators precedence in Golo was wrong in many ways, and some expressions could easily mean
anything but what you expected unless you had proper parenthesis.

We got back to our textbooks and fixed this. Now operators behave just like they _should_.

#### Command-line interface subcommands

[https://github.com/golo-lang/golo-lang/pull/266](https://github.com/golo-lang/golo-lang/pull/266)

Command-line interface subcommands now take advantage of a standard Java service provider interface,
so new ones can be developed independently.

### Proposal for incubation at the Eclipse Foundation

[Our proposal is public](https://projects.eclipse.org/proposals/golo) and we have a team in place,
including mentors.

The project has yet to go through a creation review. Before that some trademark checks and domain
name transfer need to be put in place.

To be honest we expected the process to be faster, but the approaching release of Eclipse Mars is
eating lots of bandwidth for the legal staff at the foundation.

Hopefully we will be able to resolve these matters in the next few weeks and we will be able to
enter the incubator sooner rather than later.
