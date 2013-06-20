---
layout: news
title: 'Golo news roundup #6'
---

![Philippe at the Montpellier JUG](http://distilleryimage0.s3.amazonaws.com/d7e5fc0ed90b11e2a0d822000a1f9a12_7.jpg)

*(Philippe at the Montpellier JUG, instagram courtesy of Christophe Hamerling)*

This new edition of the Golo news roundup is fruitful!

### Small changes

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
a `NullPointerException`, which is not what you would expect from a sane language.

* `foreach` loops now have optional parenthesis, so you can write `foreach b in dtc() { ... }`.

* We added `fileToText` and `textToFile` predefined functions that allow for one-shot reading and
writing of text files. You can use them as follows:

      # Read from a file
      let text = fileToText("/some/file.txt", "UTF-8")
      
      # Write to a file
      textToFile("Hello, world!", "/foo/bar.txt")


### A brand new command-line interface

Golo used to have `golo`, `goloc` and `gologolo` commands. We unified those in a simpler `golo`
command that is built with [JCommander](http://jcommander.org):

    Usage: golo [options] [command] [command options]
      Options:
            --help
           Prints this message
           Default: false
      Commands:
        version      Queries the Golo version
          Usage: version [options]
            Options:
                  --full
                 Prints the full information details
                 Default: false

        compile      Compiles Golo source files
          Usage: compile [options] Golo source files (*.golo)
            Options:
                  --output
                 The compiled classes output directory
                 Default: .

        run      Runs compiled Golo code
          Usage: run [options] Program arguments
            Options:
            *     --module
                 The Golo module with a main function

        golo      Dynamically loads and runs from Golo source files
          Usage: golo [options]
            Options:
                  --args
                 Program arguments
                 Default: []
            *     --files
                 Golo source files (the last one has a main function)
                 Default: []

A significant advantage is that the interface is more uniform, and the usage of commands will make
it easier to evolve.

### Dynamic code evaluation    

We added a `gololang.EvaluationEnvironment` class for the dynamic evaluation of Golo code.

You can use it in many ways, such as for loading an anonymous module:

    let env = gololang.EvaluationEnvironment()
    let code =
    """
    function a = -> "a!"
    function b = -> "b!"
    """
    let mod = env: anonymousModule(code)
    let a = fun("a", mod)
    let b = fun("b", mod)
    println(a())
    println(b())

You can load a function in different ways, such as in:

    let env = gololang.EvaluationEnvironment()
    let code = "|a, b| -> (a + b) * 2"
    let f = env: def(code)
    println(f(10, 20))

And finally you can just run a piece of one-shot code:

    let env = gololang.EvaluationEnvironment()
    let code = """println(">>> run_map")
    println(a)
    println(b)
    """
    let values = java.util.TreeMap(): add("a", 1): add("b", 2)
    env: run(code, values)

There are more options to dynamic code evaluation than presented here, so you are invited to have
a look at the documentation.

### Templating

We added a lightweight template engine in Golo. Because a picture is worth a thousand words, here is
a self-describing example:

    let template = """
    <%@params posts %>
    <!DOCTYPE html>
    <html>
      <head>
        <title>Golo Chat</title>
      </head>
      <body>
      <form action="/" method="post">
        <input type="text" name="msg">
        <input type="submit" value="Send">
      </form>
      <div>
        <h3>Last posts</h3>
        <% foreach post in posts { %>
          <div>
            <%= post %>
          </div>
        <% } %>
      </div>
      </body>
    </html>
    """

    let tpl = gololang.TemplateEngine(): compile(template)
    println(tpl(someDataModel: posts()))

The compilation of a template gives a (compiled) Golo function to render templates.

This is a great way to embed Golo into your applications for templating purposes. Please note that
the implementation remains simple: it does **not** check for template and generated code
correctness. That being said, one can inspect compilation exceptions: they carry a list of reported
problems as well as the generated Golo code for a template.

### On the Eclipse front

Jeff Maury is still making progress with the *Golo Language Develoment Tools* (GLDT) for Eclipse.

You can get it by pointing your Eclipse update center to
[http://gldt-update-site.golo-lang.org](http://gldt-update-site.golo-lang.org)

Do not forget to help Jeff and give him feedback:
[https://github.com/golo-lang/gldt](https://github.com/golo-lang/gldt).

### That's all, folks!

As you can guess with some many changes, we are close to a new preview release. Stay tuned!

Thanks again for your interest in Golo!

-- Julien

