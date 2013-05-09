---
layout: news
title: 'The Netbeans support is live!'
---

[David Festal from Serli](http://www.serli.com/) provides us with [an awesome Netbeans plugin](https://github.com/golo-lang/golo-netbeans). It is part of our `golo-lang` community organization on GitHub, and Serli makes it available under the Apache License, version 2.0.

[Netbeans](http://netbeans.org/) is a free, opensource and popular IDE that works on all major operating systems. Plus, it has a nice community sustaining it.

While the plugin had been available since the initial public release of Golo, this required either building it from source or installing it manually from a `.nbm` file.

This is now a thing from the past, as the Golo Netbeans plugin can now be downloaded from within Netbeans! David went through the required validation steps to have the plugin available for direct downloads from Netbeans, not just from the [plugins portal website](http://plugins.netbeans.org/).

### Installing the plugin

Open the plugins management interface:

![Installing the plugin](http://farm8.staticflickr.com/7285/8724440912_764d585ccf_b_d.jpg)

It may be useful to refresh the catalog to ensure that the plugin is listed.

Once the plugin has been installed, it is recommended that you restart Netbeans:

![Restart Netbeans](http://farm8.staticflickr.com/7325/8723320737_e58ed7f1d9_z_d.jpg)

### Configuring the plugin

Golo is not embedded with the plugin, so you will have to point the plugin to a Golo distribution directory:

![Setup](http://farm8.staticflickr.com/7305/8723320805_3bca3e8083_b_d.jpg)

Do not forget to specify a Java SE 7 platform. OpenJDK 7 and 8 will do just fine, too.

### Profit!

![IDE](http://farm8.staticflickr.com/7458/8723320977_59b00ab348_b_d.jpg)

The plugin does not just provide syntax highlighting. You may run Golo modules having a `main` function from the editor contextual menu. The structure view provides a quick overview of the current source file symbols, including closure definitions.

And of course, you will be haunted for errors:

![Errors](http://farm8.staticflickr.com/7368/8723407661_eaff1485f5_z_d.jpg)

### What's next?

* If you spot a bug: [report an issue](https://github.com/golo-lang/golo-netbeans/issues)
* If you have an idea for an improvement: [report an issue](https://github.com/golo-lang/golo-netbeans/issues)
* Otherwise... [fork the code!](https://github.com/golo-lang/golo-netbeans)

### Thanks David, thanks Serli!

Many thanks to David for his awesome work, and hats off to his employer [Serli](http://www.serli.com/) for allocating 
him so time to help the Golo community!
