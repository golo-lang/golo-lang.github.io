---
layout: main
title: Download Golo
---

### Standalone distribution

Standalone distributions can be obtained [from Maven Central](http://search.maven.org/#browse|1246390074):

* [golo-0-preview7-distribution.tar.gz](http://search.maven.org/remotecontent?filepath=org/golo-lang/golo/0-preview7/golo-0-preview7-distribution.tar.gz)
* [golo-0-preview7-distribution.zip](http://search.maven.org/remotecontent?filepath=org/golo-lang/golo/0-preview7/golo-0-preview7-distribution.zip)

<span class="label label-important">Important</span>
Given that Golo is still a young project, snapshot releases more than often contain important bug
fixes and improvements:
[get the golo-0-preview8-SNAPSHOT artefacts](https://oss.sonatype.org/content/repositories/snapshots/org/golo-lang/golo/0-preview8-SNAPSHOT/).

### Maven

Maven release and snapshot artifacts can be downloaded from both Maven Central and the
[Sonatype OSS Maven Repository](https://docs.sonatype.org/display/Repository/Sonatype+OSS+Maven+Repository+Usage+Guide).

The Golo library (runtime + compiler) artifact is:

{% highlight xml %}
<groupId>org.golo-lang</groupId>
<artifactId>golo</artifactId>
<version>0-preview7</version>
{% endhighlight %}

The Maven plugin artifact is:

{% highlight xml %}
<groupId>org.golo-lang</groupId>
<artifactId>golo-maven-plugin</artifactId>
<version>0-preview7</version>
{% endhighlight %}

### Gradle

Check out the [Gradle Golo Plugin](https://github.com/golo-lang/gradle-golo-plugin) project by
Marcin Erdmann.

Binaries are being released to Maven Central under the `org.golo-lang` group.

### Native packages

RPM: see the [DevOps Incubator project](https://github.com/hgomez/devops-incubator) by Henri Gomez
and look for `golo-lang`.

### Source code

The canonical repository is at [https://github.com/golo-lang/golo-lang](https://github.com/golo-lang/golo-lang).

We also have an organization at [https://github.com/golo-lang](https://github.com/golo-lang) where interesting
projects from the wider community are invited to join.

### Editors and IDEs support

Here are the projects that we are aware of:

- [Vim](https://github.com/jponge/vim-golo) by Julien Ponge
- [Sublime Text 2](https://github.com/k33g/sublime-golo) by Philippe Charriere
- [IntelliJ IDEA (syntax highthing)](https://github.com/k33g/golo-storm) by Philippe Charriere
- [GoloIDE for Netbeans](https://github.com/golo-lang/golo-netbeans) by [Serli](http://www.serli.com/)
- [Golo Language Development Tools for Eclipse](https://github.com/golo-lang/gldt) by Jeff Maury, the
  update site for Eclipse is [http://gldt-update-site.golo-lang.org/](http://gldt-update-site.golo-lang.org/)

