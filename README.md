# httpmime
Ensures basic mime types are installed in golang's mime package

If you use the [golang mime package](https://golang.org/pkg/mime/) you may be using an incomplete set of data.

By default, golang comes with a very small internal table mapping extentions (e.g. `.html`) to mime types (.e.g `text/html`).

On Windows this table is supplemented via the registry. On other systems, this table is supplemented by searching through the `/etc` directory looking for a mime type file.

The problem is many unix-like systems don't have this file installed.  In particular, [alpine linux](https://alpinelinux.org) does not have any of these files installed by default.

This package will check to see if the mime package has loaded data, and if not, will add all basic mime types so it works correctly.  The mime data comes the same data set that [Apache's httpd webserver](https://svn.apache.org/repos/asf/httpd/httpd/trunk/docs/conf/mime.types) uses, and is in the public domain.


