---
layout: main
title: Download Golo
---

### Standalone distribution

Standalone distributions can be obtained [from Maven Central](http://search.maven.org/#browse|1246390074):

* [golo-1.1.0-distribution.tar.gz](http://search.maven.org/remotecontent?filepath=org/golo-lang/golo/1.1.0/golo-1.1.0-distribution.tar.gz)
* [golo-1.1.0-distribution.zip](http://search.maven.org/remotecontent?filepath=org/golo-lang/golo/1.1.0/golo-1.1.0-distribution.zip)

<span class="label label-important">Important</span>
Given that Golo is still a young project, snapshot releases more than often contain important bug
fixes and improvements:
[get the snapshot artefacts](https://oss.sonatype.org/content/repositories/snapshots/org/golo-lang/golo/).

### Maven

Maven release and snapshot artifacts can be downloaded from both Maven Central and the
[Sonatype OSS Maven Repository](https://docs.sonatype.org/display/Repository/Sonatype+OSS+Maven+Repository+Usage+Guide).

The Golo library (runtime + compiler) artifact is:

{% highlight xml %}
<groupId>org.golo-lang</groupId>
<artifactId>golo</artifactId>
<version>1.1.0</version>
{% endhighlight %}

The Maven plugin artifact is:

{% highlight xml %}
<groupId>org.golo-lang</groupId>
<artifactId>golo-maven-plugin</artifactId>
<version>1.1.0</version>
{% endhighlight %}

### Gradle

Check out the [Gradle Golo Plugin](https://github.com/golo-lang/gradle-golo-plugin) project by
Marcin Erdmann.

Binaries are being released to Maven Central under the `org.golo-lang` group.

### Native packages

* RPM: see the [DevOps Incubator project](https://github.com/hgomez/devops-incubator) by Henri Gomez
and look for `golo-lang`.
* OSX: see the [Homebrew project](http://brew.sh/) and install the `golo` formula with `brew install golo`.
* Windows: see the [Chocolatey project](https://chocolatey.org/) and install the [golo package](https://chocolatey.org/packages/golo) with `choco install golo`.

### Docker

[Docker](http://docker.com/) is on top of the hype, and so do we!

[We provide images](https://registry.hub.docker.com/u/jponge/golo-lang/) based on Ubuntu 14.04 and Java SE 8: `docker pull jponge/golo-lang`

You can either use them as-is, or derive your own specialized images based on top of them.

### Source code

The canonical repository is at [https://github.com/golo-lang/golo-lang](https://github.com/golo-lang/golo-lang).

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
