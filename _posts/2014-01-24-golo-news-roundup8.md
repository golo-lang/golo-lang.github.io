---
layout: news
title: "Golo News Roundup #8"
---
![](http://farm6.staticflickr.com/5535/12116140074_54299743fc_z_d.jpg)

Here is the first post of 2014!

This edition welcomes 2 guest writers in which Daniel and Philippe pitch their latest Golo projects:
**Golosa Test** and **M33ki**.

### What’s new in Golo?

As you probably know, we released Golo `0-preview10` last December. This release comes with new
tools to create projects and generate documentation. It also brings better debuggers support, shell
completion and direct closure conversion for Java APIs.

More recently, Daniel brought the support of fallback methods for dynamic objects. This allows
invoking methods even on undefined properties.

Other than that, we spent a significant amount of time in rewriting a benchmarks suite with the
[OpenJDK JMH](http://openjdk.java.net/projects/code-tools/jmh/) harness.

Benchmarking applications running on an adaptive runtime like the JVM is **hard**. JMH provides the
building blocks to shield from classical traps like unwanted dead-code elimination, loop unrolling,
on-stack replacement and more. The
[HotSpot wiki](https://wikis.oracle.com/display/HotSpotInternals/Home) contains lots of technical
details on what kind of JIT compilation techniques are being used.

The `TL;DR` takeaway is that it is very easy to measure the wrong things when benchmarking on the
JVM.

With a good understanding of what HotSpot does and a tool like JMH, it is easier to get meaningful
benchmark results. We encourage you to have a look!

Let us now read what our guest writers have to say.

### Golosa Test

— By Daniel Petisme

> The world didn’t need another tesing framework. So we built yet another one. A Golo one: [Golosa Test](https://github.com/danielpetisme/golosa-test)

[Golosa Test](https://github.com/danielpetisme/golosa-test) is a behavior-driven development framework for testing mainly inspired by [Jasmine](http://pivotal.github.io/jasmine/) (a JS behavioral testing framework). Since a snippet is worth a thousand words:

```golo
module my.awesome.test

# The only import gather all the Golosa SA API
import golosa.test.$

# A test module must have a test method
function test = {

  # Define a Test suite with a description and an executable code block (ie. a lambda)
  describe("A test suite", {
    
    # A lambda can contain any executable code necessary, be careful with Golo   scoping rules
    var aList = null

    # Setting up the test fixture.
    beforeEach({
      aList = list[]
      aList: append("something")
    })

    # Defines a specification
    it("contains a specification with an expectation", {
      expect(aList: size()): toBe(1)
      expect(aList: isEmpty()): not(): toBeTrue()
    })

    # Disable a suite or a spec by prefixing it with 'x'
    xit("contains something", {
      expect("something"): toBeIn(aList)
    })

    # Tear down the test fixture to return to the original state.
    afterEach({
      aList = null
    })
  })
}
```

Do not trust this snippet, test by yourself! Go to [Golosa Test project page](https://github.com/danielpetisme/golosa-test) and give it a try…

### M33ki web framework

— By Philippe Charrière

[M33ki](https://github.com/TypeUnsafe/m33ki) is a !(not)Opinionated Web Framework (by TypeUnSafe
inc.). Of course, any resemblance to existing frameworks is purely coincidental.

M33ki Framework makes it easy to build web applications with Golo and Java. M33ki is based on a lightweight, stateless or stateful (as you want), web-friendly architecture.

Built on Golo and SparkJava (and some other libraries), M33ki provides minimal resource consumption (CPU, memory, threads) for embedded web server.

- M33ki is developer friendly: make your changes and simply hit refresh! All you need is a browser and a text editor.
- M33ki is polyglot: you can code in Golo only, or in Java and Golo.
- M33ki is asynchronous too,… only if you want (Futures, Promises ans Observers).
- M33ki is *modern*: RESTful, JSON, Websockets, EventSource (Server Sent Events), NoSQL (MongoDb, and soon Redis).
- M33ki loves JavaScript: it was designed to be the backend of single page applications.
- M33ki and M33ki apps are extensible.

Caution: [M33ki (on GitHub)](https://github.com/TypeUnsafe/m33ki) is a proof-of-concept right now.

![](https://github.com/TypeUnsafe/m33ki/raw/master/appgolo.gif)
