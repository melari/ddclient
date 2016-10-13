Forked from `3.8.2-ubuntu` to add support for multiple domains using the namecheap protocol.

`upstream` branch holds the original unpatched version of the client.

Installation
============

service ddclient stop
cp ddclient /usr/sbin/ddclient
service ddclient start

Configuration
=============
edit /etc/ddclient.conf

example configuration:

```
daemon=3600
use=web, web=dynamicdns.park-your-domain.com/getip
protocol=namecheap
ssl=yes

server=dynamicdns.park-your-domain.com
login=mydomain.com
password='abc123'
@.mydomain.com

server=dynamicdns.park-your-domain.com
login=another.com
password='abc123'
@.another.com
```


Test Configuration
==================
`sudo ddclient -daemon=0 -debug -verbose -noquiet`
