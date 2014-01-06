`mod_maxminddb`
=============

Apache2.4 module for MaxMindDB database integration

Overview
========

`mod_maxminddb` is an Apache 2.4 module. It uses the `libmaxminddb` library to
preform the lookups.

Requirements
============

 Please make sure apache 2.4 is installed.
`httpd -v` will show the version number.

The library [`libmaxinddb`] (https://github.com/maxmind/libmaxminddb) must be
installed to compile this module.

Install the desired `mmdb` database files either with
[`geoipupdate`](https://github.com/maxmind/geoipupdate)
or download the files [here](http://dev.maxmind.com/geoip/geoip2/geolite2/) and
install them manually.

Installation
============

    /usr/local/apache24/bin/apxs -i -a -L/usr/local/lib -I/usr/local/include -lmaxminddb -Wc,-std=gnu99 -c mod_maxminddb.c

Usage
=====

`mod_maxmindb` uses the current connection IP address for the lookup. This is
not always what you want.
[mod_remoteip](http://httpd.apache.org/docs/current/mod/mod_remoteip.html) is
useful to do this work.


