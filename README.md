# UUCP Client - Server communication over TCP/IP Example in docker-compose

## What it this ?

Just a docker-compose to PoC a working configuration of UUCP communication over TCP/IP

Was made for some Infosec challenge.

Was a bit long to make it work after reading the doc, so it might be useful for others one days



## Usage
```
docker-compose up -d
```

You can then enter both containers using :

```
docker exec -ti uucp-client /bin/bash

```

and


```
docker exec -ti uucp-server /bin/bash
```

You may try to execute some remote command with this command (which purge any queued commands so you can instantly test if it is working)

```
rm -rf /var/spool/uucp/.Status/thames ; uux   'thames!ping 127.0.0.1' ; sleep 2 ; uulog
```

You can check debug file on both client and server with :

```
tail -f /var/log/uucp/Debug
```

If you want to allow more commands to be allowed to be executed, just edit `server/etc-uucp/Permissions` 
