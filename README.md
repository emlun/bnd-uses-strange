bnd-uses-strange
================

Strange behaviour of BND in Gradle < 1.7

Building
--------

With [Gradle][gradle] installed, run

    gradle assemble


Gradle < 1.7
------------

When the project is built as an OSGi bundle using Gradle 1.6, the manifest contains the following instruction in the Export-Package header:

    Export-Package: com.acme.impl;uses:="com.acme.api";version="1.0"

Despite the fact that the package org.apache.commons.el is only ever used inside a function, which should not affect other bundles importing the com.acme.el package, unless I've misunderstood how the uses directive works.


Gradle 1.7
----------
[Gradle 1.7 uses bnd 2.1.0][releasenotes], instead of bnd 1.50.0 which is used by earlier Gradle distributions. This problem does not occur when using Gradle 1.7.

[gradle]: http://www.gradle.org/
[releasenotes]: http://www.gradle.org/docs/1.7-rc-1/release-notes#bnd-library-used-by-osgi-plugin-updated
