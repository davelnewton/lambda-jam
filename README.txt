There are two empty exercise projects: `robozzle` and `life` in
subdirectories of the same name. Three worked examples are in the
`worked-examples` subdirectory.

Before starting the exercises, see `INSTALL.txt`.

When doing the exercises, you can refer to the Midje user guide at
<https://github.com/marick/Midje/wiki>. If the network is down, the
selected pages in the `user-guide` directory may be helpful.

There's a copy of the Clojure 1.5 API in `clojure-api.html`. The
Clojure set API is in `clojure-set-api.html`.

=== STARTING AN EXERCISE WITH AUTOTEST

    $ cd robozzle
    $ lein repl
    nREPL server started on port 53118
    ...
    user=> (use 'midje.repl)
    Run `(doc midje)` for Midje usage.
    Run `(doc midje-repl)` for descriptions of Midje repl functions.
    nil
    user=> (autotest)
    
    ======================================================================
    Loading (robozzle.core robozzle.t-core)

    FAIL "It works end-to-end." at (core.clj:14)
    Actual result did not agree with the checking function.
            Actual result: false
        Checking function: truthy
    FAILURE: 1 check failed.  (But 1 succeeded.)
    true
    user=>

Note: `autotest` currently overlooks files that throw an error while
being loaded. So it's wise to start it before you start writing
code. Errors made *after* autotest starts are no problem. Autotest
will load them and tell you about the error:

    ======================================================================
    Loading (robozzle.core robozzle.t-core)
    LOAD FAILURE for robozzle.core
    java.lang.RuntimeException: Unable to resolve symbol: skl in this context, compiling:(robozzle/core.clj:0:0)
    The exception has been stored in #'*me, so `(pst *me)` will show the stack trace.
    FAILURE: 1 check failed. 

Each exercise has a `core.clj` file under `src` and a `t_core.clj`
file under `test`. They are set up so that you can put the facts in
either, depending on your preference.
