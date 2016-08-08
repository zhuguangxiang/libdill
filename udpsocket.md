# udpsocket(3) manual page

## NAME

udpsocket - create a UDP socket

## SYNOPSIS

```
#include <dsock.h>
int udpsocket(ipaddr *local, const ipaddr *remote);
```

## DESCRIPTION

Creates a UDP socket listening on `local` IP address. If `local` is `NULL` the socket won't listen for incoming packets. If `remote` IP address is not `NULL` it will be stored and use to send packets to when `udpsend` is invoked without a destination address or when `msend` is called on the socket.

## RETURN VALUE

Handle of the created socket. In case of error -1 is returned and `errno` is set to one of the error codes below.

## ERRORS

TODO

## EXAMPLE

```
ipaddr addr;
int rc = iplocal(&addr, NULL, 5555, 0);
int s = udpsocket(&addr, NULL);
```

## SEE ALSO

* [mrecv(3)](mrecv.html)
* [msend(3)](msend.html)
* [udprecv(3)](udprecv.html)
* [udpsend(3)](udpsend.html)

## AUTHORS

Martin Sustrik <sustrik@250bpm.com>
