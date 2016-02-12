---
layout: news
title: "Golo News Roundup #9"
---
<iframe src="//instagram.com/p/nLd9wQvpLv/embed/" width="612" height="710" frameborder="0" scrolling="no" allowtransparency="true">
</iframe>

Long time without news… we just got busy :-)

### Latest changes in Golo

The current Golo `0-preview12` snapshots have some interesting changes.

#### Nested `try/catch` fixes

The `try/catch` instruction bytecode generation has been reordered so that the following code has
correct semantics:

```golo 
function nested_try = {
  try {
    try {
      raise("a")
    } catch (ok) {
      return "ok"
    }
  } catch (failed) {
    return "failed"
  }
}
```

It properly returns `"ok"` instead of `"failed"` which is what the previous implementation would yield.

#### JSON module

The new `gololang.JSON` module provides JSON marshalling based on
[json-simple](https://code.google.com/p/json-simple/) which is a lightweight JSON Java library.

Here is some sample code to JSON-ify some data structures:

```folo
let data = map[
  ["name", "Somebody"],
  ["age", 69],
  ["friends", list[
    "Mr Bean", "John B", "Larry"
  ]]
]

let asText = JSON.stringify(data)
```

The other way around works, of course:

```golo
let data = JSON.parse(text)
println(data: get("name"))
```

#### Golodoc fixes

Philippe Charrière contributed a few fixes in the Golodoc generation.

#### New utility containers

We now have `gololang.DynamicVariable` which is a direct port of `DynamicVariable` from Scala.

We also introduced `gololang.Observable`, a nice and composable abstraction:

```golo
let foo = Observable("Foo")
foo: onChange(|v| -> println("foo = " + v))

let mapped = foo: map(|v| -> v + "!")
mapped: onChange(|v| -> println("mapped = " + v))

foo: set("69")
```

#### Pygments

Yannick Loiseau provided a Golo syntax highlighting support for Pygments.

The next release of Golo will have syntax highlighted documentation.

The Pygments maintainers haven’t merged Yannick’s pull request yet, so meanwhile one needs to install Pygments
[from his fork](https://bitbucket.org/yloiseau/pygments-main).

### Golo 1.0 release date

Golo 1.0 will be released on July 9th 2014.

This will mark the second of Golo since its first commit on July 9th 2012. At some point things need
to be marked as *“done”*, hence doing this release is important.

### Pull requests in progress

Sylvain Desgrais started working on Python-style decorators. You can already get his working code,
and follow the discussion at
<https://github.com/golo-lang/golo-lang/pull/148>

Daniel Petisme is currently working on string interpolation:
<https://github.com/golo-lang/golo-lang/pull/149>

### In the community

- Philippe Charrière is unstoppable. He is still geeking various web stacks, and he even did a talk at
     Devoxx France. Expect the video soon!

- Julien Viet and Daniel Petisme worked on a Golo / [CRaSH](http://www.crashub.org/) integration
     while at a HackerGarten.

### Until next time…

We will soon release Golo `0-preview12`, followed by `1.0` release candidates.

Stay tuned!
