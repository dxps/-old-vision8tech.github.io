# Notes on Isomorphic Go

## The Book

While studying [Isomorphic Go](https://www.packtpub.com/web-development/isomorphic-go) book, I got into some errors with the initial setup on _chapter 2_ and these notes captured the solutions.

In my (MacOS based) setup, `GOPATH` = `/files/dev/go`. You will see paths that refer to it.

First error:
```bash
$ go get -u github.com/uxtoolkit/cog
# github.com/uxtoolkit/cog
/files/dev/go/src/github.com/uxtoolkit/cog/uxcog.go:27:19: undefined: isokit.TemplateSet
$
```

was solved by using the new homes for `isokit` and `cog`:

```bash
$ go get -u go.isomorphicgo.org/go/isokit
$ go get -u go.isomorphicgo.org/uxtoolkit/cog
```

Second error:
```bash
$ pwd
/files/dev/go/src/github.com/EngineerKamesh/igb/igweb/client
$ gopherjs build
cannot find package "github.com/tdewolff/parse/v2" in any of:
	/usr/local/opt/go/libexec/src/github.com/tdewolff/parse/v2 (from $GOROOT)
	/files/dev/go/src/github.com/tdewolff/parse/v2 (from $GOPATH)
$
```
is due to the fact that GopherJS does not support modules yet.

It was solved by installing `github.com/tdewolff/minify` version 2.3.6 and  `github.com/tdewolff/parse` version 2.3.4:

```shell
$ pwd
/files/dev/go/src/github.com/tdewolff
$ curl -L https://github.com/tdewolff/minify/archive/v2.3.6.zip --output minify-2.3.6.zip
$ unzip minify-2.3.6.zip
$ mv minify-2.3.6 minify
```


