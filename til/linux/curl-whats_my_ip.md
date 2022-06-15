# HOWTO: Check my public address

That means, the address of my router, ie. the address under which the world sees me. This TIL piece is taken from [How to find your IP address in Linux](https://opensource.com/article/18/5/how-find-ip-address-linux).

```
$ curl ifconfig.me
188.144.0.191$ curl ident.me
188.144.0.191$ curl -4/-6 icanhazip.com
curl: option -4/-6: is unknown
curl: try 'curl --help' for more information
$ curl ipinfo.io/ip
188.144.0.191
$ curl api.ipify.org
188.144.0.191$ curl checkip.dyndns.org
<html><head><title>Current IP Check</title></head><body>Current IP Address: 188.144.0.191</body></html>
$ dig +short myip.opendns.com @resolver1.opendns.com
188.144.0.191
$ host myip.opendns.com resolver1.opendns.com
Using domain server:
Name: resolver1.opendns.com
Address: 208.67.222.222#53
Aliases: 

myip.opendns.com has address 188.144.0.191
Host myip.opendns.com not found: 3(NXDOMAIN)
Host myip.opendns.com not found: 3(NXDOMAIN)
$ curl bot.whatismyipaddress.com
188.144.0.191$ curl ipecho.net/plain
188.144.0.191$ 
```
