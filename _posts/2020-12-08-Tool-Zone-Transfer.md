Hi

This is a test post really, but i'll add a small amount of value to it. 

Here is a tool for zone transfers, nothing special, does the job nice and quickly though. 

```
#!/bin/bash

echo "####################################"
echo "#                                  #"
echo "#         ZZZZonneTranzzfer        #"
echo "#           by Ryku-01             #"
echo "#                                  #"
echo "####################################"

NETWORK="$1"
DOMAIN="$2"

[ -z ${2} ] && echo "Usage: ${0} <Network/24> <Domain>"

servers=$(nmap -p 53 ${NETWORK} --open -oG - | grep "/open" | awk '{ print $2 }')

for server in ${servers};
do
    echo "[*] zonetransfer: ${server}"
    host -l ${DOMAIN} ${server}
done
```

Enjoy!

ryku!
