# html-inline

inline javascript, stylesheets, and images from an html page

[![build status](https://secure.travis-ci.org/substack/html-inline.png)](http://travis-ci.org/substack/html-inline)

# example

input file:

``` html
<html>
  <head>
    <link rel="stylesheet" href="/yo.css">
  </head>
  <body>
    <img src="icon.png">
    <script src="hey.js"></script>
  </body>
</html>
```

output:

```
$ html-inline index.html
```

``` html
<html>
  <head>
    <style>body {
  background-color: cyan;
}
</style>
  </head>
  <body>
    <img src="data:image/png;base64,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">
    <script>console.log('oh hey');
</script>
  </body>
</html>
```

# usage

```
html-inline {-i INFILE -o OUTFILE -b BASEDIR}

  Read an html file from INFILE to produce OUTFILE, inlining stylesheets, script
  tags, and images relative to BASEDIR.

  -i File to read. Default: STDIN.
  -o File to write. Default: STDOUT.
  -b Directory to resolve paths from. Default: $PWD.

  --ignore-images   Don't inline images. Default: false
  --ignore-scripts  Don't inline JavaScript. Default: false
  --ignore-styles   Don't inline CSS. Default: false
  --ignore-links    Don't inline <link> tags. Default: false
  --ignore-external Skip external resources instead of throwing an error. Default: false

```

# methods

``` js
var inliner = require('html-inline')
```

## var inline = inliner(opts={})

Create a transform stream `inline` that expects html as input and produces html
with inline assets as output.

Paths to scripts, stylesheets, and images are
resolved relative to `opts.basedir`.

You can disable asset inlining by passing `true` for:

* `opts.ignoreImages`
* `opts.ignoreScripts`
* `opts.ignoreStyles`
* `opts.ignoreLinks`

# install

With [npm](https://npmjs.org), to get the command do:

```
npm install -g html-inline
```

and to get the library do:

```
npm install html-inline
```

# license

MIT
