# libHBase 

"C" APIs for HBase.

## Building libHBase
```
  mvn install
```

This will build the tarball containing the headers, shared library and the jars in the `target` directory with the following structure.

```
+---bin
+---conf
+---include
|   \---hbase
+---lib
|   \---native
\---src
    \---examples
        \---async
```

The headers can be found under `include` folder while the shared library to link against is under `lib/native`.

## Building Applications with libHBase
For examples on how to use the APIs, please take a look at [this sample source](src/examples/async/example_async.c).

As the library uses JNI, you will need to have both `libhbase` and `libjvm` shared libraries in your application's library search path. The jars required for the library can be specified through either of the environment variables `CLASSPATH` or `HBASE_LIB_DIR`. Custom JVM options, for example `-Xmx`, etc can be specified using the environment variable `LIBHBASE_OPTS`.

## Performance Testing
A performance test is included with the library which currently support sequential/random gets and puts. You can run the tests using this [shell script](bin/perftest.sh).
