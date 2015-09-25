---
layout: main
title: Download Golo
---

### Standalone distribution

Standalone distributions can be obtained from the Eclipse Foundation and its mirrors network.

* [Golo 3.0.0-incubation-M2](https://www.eclipse.org/downloads/download.php?file=/golo/golo-3.0.0-incubation-M2.zip)
* [Latest snapshot build](https://www.eclipse.org/downloads/download.php?file=/golo/golo-latest-snapshot.zip) (if you like the greatest and latest)

### Maven

#### Bintray, jCenter and Maven Central

Release and milestone artifacts can be obtained from [Bintray / jCenter](https://bintray.com/golo-lang/golo-lang)
as well as from [Maven Central](http://search.maven.org/).

The Golo library (runtime + compiler) artifact is:

{% highlight xml %}
<groupId>org.eclipse.golo</groupId>
<artifactId>golo</artifactId>
<version>3.0.0-incubation-M2</version>
{% endhighlight %}

The Golo Maven plugin artifact is:

{% highlight xml %}
<groupId>org.eclipse.golo</groupId>
<artifactId>golo-maven-plugin</artifactId>
<version>3.0.0-incubation-M2</version>
{% endhighlight %}

#### Snapshots at Eclipse

We publish our Maven `-SNAPSHOT` artifacts to the [Eclipse repositories](https://repo.eclipse.org/):
[https://repo.eclipse.org/content/repositories/golo-snapshots/](https://repo.eclipse.org/content/repositories/golo-snapshots/)

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

[We provide Docker images of Golo](https://registry.hub.docker.com/u/jponge/golo-lang/).
You can either use them as-is, or derive your own specialized images based on top of them.

If you want to quickly test Golo:

```console
$ docker pull jponge/golo-lang

    (...)

$ docker run --rm -t -i jponge/golo-lang /bin/bash
root@cf99d78f22a4:/# golo version --full
Golo version: 3.0.0-SNAPSHOT (build 15-03-17-09:28)
JVM version: 1.8.0_31
root@cf99d78f22a4:/#
```

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
