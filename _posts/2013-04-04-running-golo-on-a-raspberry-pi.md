---
layout: news
title: 'Running Golo on a Raspberry Pi'
---

The latest *cool* thing to have for a conference talk demo is a [Raspberry Pi](http://www.raspberrypi.org/).
It is indeed funnier to show that your demo works on a cheap device of the size of a credit card, than say, a dumb server
*in the cloud*.

![A Raspberry Pi](http://farm9.staticflickr.com/8527/8571661508_4264ba0dda_c_d.jpg)

More seriously we at [DynaMid](http://dynamid.citi-lab.fr) are very interested in such devices for our research
needs. The JVM works there, so having our [programming language Golo](http://golo-lang.org/) running fine on a
[Raspberry Pi](http://www.raspberrypi.org/) is important beyond being just cool.

Getting [Golo](http://golo-lang.org/) to work on a [Raspberry Pi](http://www.raspberrypi.org/) is quite simple
as we will see in this article.

### Operating system

We recommend [ArchLinux for ARM](http://archlinuxarm.org).

The nice thing with the [ArchLinux image for Raspberry Pi](http://archlinuxarm.org/platforms/armv6/raspberry-pi)
is that it boots `OpenSSH` *by default* with a `root/root` login.

You don't have to mess with a screen display, a keyboard and a mouse. Huge win!

We suggest that you update your fresh ArchLinux as soon as you managed to boot it:

    pacman -Syu

### Java

Get a JDK8 test version from [http://jdk8.java.net/fxarmpreview/](http://jdk8.java.net/fxarmpreview/).
It has JavaFX, too.

Extract it to a nice place such as `/opt/jdk1.8.0/`.
Once this is done, it is a good idea to modify you `~/.bash_profile` to have `JAVA_HOME` and the JDK
binaries added to your path:

    [root@alarmpi ~]# cat .bash_profile
    export JAVA_HOME=/opt/jdk1.8.0
    export PATH=$PATH:$JAVA_HOME/bin

All good! Now with a shell you can check that Java works:

    [root@alarmpi ~]# java -version
    java version "1.8.0-ea"
    Java(TM) SE Runtime Environment (build 1.8.0-ea-b36e)
    Java HotSpot(TM) Client VM (build 25.0-b04, mixed mode)

### Golo

Download a fresh version of Golo from SourceForge (change the version according to the latest Golo release):

    [root@alarmpi ~]# wget -O golo-0-preview1-distribution.tar.gz http://sourceforge.net/projects/golo-lang/files/0-preview1/golo-0-preview1-distribution.tar.gz/download
    (...)
    [root@alarmpi ~]# tar zxvf golo-0-preview1-distribution.tar.gz
    (...)
    [root@alarmpi ~]# cd golo-0-preview1
    [root@alarmpi golo-0-preview1]#

The scripts in `bin/` have JVM-specific tuning flags that are good on a desktop or server, but much less on a Raspberry Pi.
You will thus need to modifiy all the `bin/golo*` scripts to remove them.

Here is a diff for `bin/gologolo`, and you can apply the same trivial changes to all of them.

{% highlight diff %}
--- gologolo.orig	2013-04-04 10:24:51.910110064 +0100
+++ gologolo	2013-04-04 10:26:13.420116024 +0100
@@ -97,7 +97,7 @@
   [ -n "$REPO" ] && REPO=`cygpath --path --windows "$REPO"`
 fi

-exec "$JAVACMD" $JAVA_OPTS -server -Xms1024M -Xmx1024M -XX:-TieredCompilation \
+exec "$JAVACMD" $JAVA_OPTS \
   -classpath "$CLASSPATH" \
   -Dapp.name="gologolo" \
   -Dapp.pid="$$" \
{% endhighlight %}

You may leave `-XX:-TieredCompilation` if you like. The memory settings are obviously too high for such a device, and the
`server` mode is not available on ARMv6.

You should now be all set, and the following should work:

    [root@alarmpi golo-0-preview1]# bin/gologolo samples/helloworld.golo
    Hello world!

### Conclusion

If it runs Java, it runs Golo!

Looking forward to discovering what kind of experiments you will make using Golo on such cheap and fun devices!
