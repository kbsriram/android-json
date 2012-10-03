Android JSON
============

This is a standalone source for json support, extracted from the [main
Android source code](http://source.android.com/index.html).  Building
the jar file lets you run tests that use org.json methods, without
requiring the entire android framework.

Why bother with this library, when you can directly get json parsing
code from elsewhere? It is to ensure that you can use the same code
and API that android uses. For instance, Android uses an API derived
from [Douglas Crockford's org.json
implementation](http://www.json.org/java/index.html) although the two
apis have diverged since then.

Using the library
-----------------

The quickest way is to [download the
android-json.jar](https://raw.github.com/kbsriram/android-json/master/dist/android-json.jar)
and add that to your test code libraries.

Regenerating the library
------------------------

If you prefer, clone this repository, and run `ant clean dist`.

Please note that the source code compiles with warnings related to
missing serialVersionUID in a couple of serializable classes.

Please also note that one of the test cases do not pass. This appears
to be [a low-priority bug in
Android](http://source-android.frandroid.com/libcore/expectations/icebox.txt)
and described as "a low-impact bug, also present in Crockford's
implementation of org.json".

The failing test case is `org.json.ParsingTest#test64BitHexValuesw`,
and it reports the error `Large hex longs shouldn't be yield ints or
strings...`
