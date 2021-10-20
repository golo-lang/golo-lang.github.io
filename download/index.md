---
layout: main
title: Download Golo
---

### Standalone distribution

[Get Golo 3.4.0 from GitHub](https://github.com/eclipse/golo-lang/releases/download/release%2F3.4.0/golo-3.4.0.zip).

### Maven

Release and milestone artifacts can be obtained from [Maven Central](http://search.maven.org/).

The Golo library (runtime + compiler) Maven artifact is:

{% highlight xml %}
<dependency>
  <groupId>org.eclipse.golo</groupId>
  <artifactId>golo</artifactId>
  <version>3.4.0</version>
</dependency>
{% endhighlight %}

or from Gradle:

{% highlight groovy %}
dependencies {
  implementation 'org.eclipse.golo:golo:3.4.0'
  // ...
}
{% endhighlight %}

<!-- The Golo Maven plugin artifact is:

{% highlight xml %}
<dependency>
  <groupId>org.eclipse.golo</groupId>
  <artifactId>golo-maven-plugin</artifactId>
  <version>3.4.0</version>
</dependency>
{% endhighlight %} -->

### Gradle

Check out the [Gradle Golo Plugin](https://github.com/golo-lang/gradle-golo-plugin) project by
Marcin Erdmann.

Binaries are being released to Maven Central under the `org.golo-lang` group.

### Native packages

* OSX: see the [Homebrew project](http://brew.sh/) and install the `golo` formula with `brew install golo`.
* Windows: see the [Chocolatey project](https://chocolatey.org/) and install the [golo package](https://chocolatey.org/packages/golo) with `choco install golo`.

### Source code

The canonical repository is at [https://github.com/eclipse/golo-lang](https://github.com/eclipse/golo-lang).

We also have an organization at [https://github.com/golo-lang](https://github.com/golo-lang) where interesting
projects from the wider community are invited to join.

### Editors and IDEs support

Here are the projects that we are aware of:

- [Vim](https://github.com/jponge/vim-golo) by Julien Ponge
- [Sublime Text 2](https://github.com/k33g/sublime-golo) by Philippe Charriere
- [IntelliJ IDEA (syntax highlight)](https://github.com/k33g/golo-storm) by Philippe Charriere
- [GoloIDE for Netbeans](https://github.com/golo-lang/golo-netbeans) by [Serli](http://www.serli.com/)
- [Golo Language Development Tools for Eclipse](https://github.com/golo-lang/gldt) by Jeff Maury, the
  update site for Eclipse is [http://gldt-update-site.golo-lang.org/nightly](http://gldt-update-site.golo-lang.org/nightly)
