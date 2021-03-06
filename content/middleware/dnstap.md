+++
title = "dnstap"
description = "*dnstap* enables logging to dnstap, a flexible, structured binary log format for DNS software: http://dnstap.info."
weight = 7
tags = [ "middleware", "dnstap" ]
categories = [ "middleware" ]
date = "2017-07-27T12:53:47.834421"
+++

There is a buffer, expect at least 13 requests before the server sends its dnstap messages to the socket.

## Syntax

~~~ txt
dnstap SOCKET [full]
~~~

* **SOCKET** is the socket path supplied to the dnstap command line tool.
* `full` to include the wire-format DNS message.

## Examples

Log information about client requests and responses to */tmp/dnstap.sock*.

~~~ txt
dnstap /tmp/dnstap.sock
~~~

Log information including the wire-format DNS message about client requests and responses to */tmp/dnstap.sock*.

~~~ txt
dnstap /tmp/dnstap.sock full
~~~

## Dnstap command line tool

~~~ sh
go get github.com/dnstap/golang-dnstap
cd $GOPATH/src/github.com/dnstap/golang-dnstap/dnstap
go build
./dnstap
~~~

The following command listens on the given socket and decodes messages to stdout.

~~~ sh
dnstap -u /tmp/dnstap.sock
~~~

The following command listens on the given socket and saves message payloads to a binary dnstap-format log file.

~~~ sh
dnstap -u /tmp/dnstap.sock -w /tmp/test.dnstap
~~~
