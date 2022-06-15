# JDeveloper - specify JVM for IDE

Here we go again... find the correct shell script or configuration file and change one line there... This time it's `$JDEVELOPER_PRODUCT_HOME/<version>/product.conf`. There just find `SetJavaHome` directive (it will be one of the first) and alter per your wish:

```
#
# By default, the product launcher will search for a JDK to use, and if none
# can be found, it will ask for the location of a JDK and store its location
# in this file. If a particular JDK should be used instead, uncomment the
# line below and set the path to your preferred JDK.
#
SetJavaHome /opt/jvm/jdk1.8.0_251
```

BTW, if you are curious, where is the `$JDEVELOPER_PRODUCT_HOME` located, it's _always_ `$HOME/.jdeveloper` and you can't change it (as far as I know). I was able to get rid off system directory and move elsewhere, but this `product.conf` is still here... but I don't care as it is not that much. 
