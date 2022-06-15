## check for tcp port ##
## need bash shell ##
(echo >/dev/tcp/{host}/{port}) &>/dev/null && echo "open" || echo "close"
(echo >/dev/udp/{host}/{port}) &>/dev/null && echo "open" || echo "close"
(echo >/dev/tcp/www.cyberciti.biz/22) &>/dev/null && echo "Open 22" || echo "Close 22"
(echo >/dev/tcp/www.cyberciti.biz/443) &>/dev/null && echo "Open 443" || echo "Close 443"

from https://www.cyberciti.biz/faq/ping-test-a-specific-port-of-machine-ip-address-using-linux-unix/

Also there:
Use nc command
The syntax is:
nc -vz {host} {port}
nc -vz 192.168.2.254 80
nc -vz www.cyberciti.biz 443

