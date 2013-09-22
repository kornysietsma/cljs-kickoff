# cljs-kickoff

A Leiningen template for minimal ClojureScript project with lein-cljsbuild
and lein-ring.

This is Korny's fork with cljs version, multiple profiles, brepl stuff - mostly taken from https://github.com/magomimmo/modern-cljs

It's intended to be as small as possible - only use Ring, ClojureScript,
lein-cljsbuild, and lein-ring. Users are free to add any other libraries as
they like.

It has complete configuration for lein-cljsbuild. The plugin compiles .cljs
files so that Ring can immediately serve them, it also is configured to
compile and include them in build.

Korny additions:
- piggieback for brepl within nrepl
- explicit clojurescript version 0.0-1889
- profiles dev only for now

planned:
- add a readme to generated project!
- prodlike and prod profiles (prodlike with brepl)
- source maps

## Usage
Install locally (as this isn't on clojars!)
```lein install```

Create project:

```bash
lein new cljs-kickoff my-project
```

Up and running (with CLJS compilation):
```bash
cd my-project
lein ring server
```

Interactive developmnt:
```bash
# Shell 1 - start server:
cd my-project
lein ring server

# Shell 2 - cljsbuild will recompile cljs whenever the files change:
cd my-project
lein cljsbuild auto
```

Package and run from jar:
```bash
cd my-project
lein ring uberjar
java -jar target/my-project-0.1.0-SNAPSHOT-standalone.jar
```

Interactive browser repl:
```lein repl
(browser-repl)
; reload the app to establish a connection (I think)
(js/alert "it's alive!")
(in-ns 'foo.bar)
```

## More resources

This project is intentionally minimal. There's plenty resources on ClojureScript
on the web. Feel free to take a look at the posts on my blog at
http://squirrel.pl/blog/tag/clojurescript/

## License

Copyright © 2012 Konrad Garus
Copyright © 2013 Korny Sietsma

Distributed under the Eclipse Public License, the same as Clojure.
