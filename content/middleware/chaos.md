+++
title = "chaos"
description = "The *chaos* middleware allows CoreDNS to respond to TXT queries in the CH class."
weight = 4
tags = [ "middleware", "chaos" ]
categories = [ "middleware" ]
date = "2017-07-27T12:53:47.833526"
+++

This is useful for retrieving version or author information from the server.

## Syntax

~~~
chaos [VERSION] [AUTHORS...]
~~~

* **VERSION** is the version to return. Defaults to `CoreDNS-<version>`, if not set.
* **AUTHORS** is what authors to return. No default.

Note that you have to make sure that this middleware will get actual queries for the
following zones: `version.bind`, `version.server`, `authors.bind`, `hostname.bind` and
`id.server`.

## Examples

~~~
chaos CoreDNS-001 "Miek Gieben" miek@miek.nl
~~~
