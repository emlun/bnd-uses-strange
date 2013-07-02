bnd-uses-strange
================

Strange behaviour of BND in Gradle

This project contains a single Java source file. When building the project as an OSGi bundle using Gradle, the manifest contains the following instruction:

Export-Package: com.acme.el;uses:="org.apache.commons.el";version="1.0"

Despite the fact that the package org.apache.commons.el is only ever used inside a function, which should not affect other bundles importing the com.acme.el package, unless I've misunderstood how the uses directive works.
