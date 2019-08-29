## Bsides Cymru!

In 2019 Bsides comes to Cardiff and NetSec Focus have one ticket to giveaway! If you can make it to Cardiff on the 28th September 2019 and want a free ticket I've got a little puzzle for you (or if you just want a fun challenge). 

Simply decrypt the files and let me know what they say. Hit me up on twitter @netsecfocus or join us on Mattermost and contact vcsec with your answer https://mm.netsecfocus.com/join/

## Presenting the Neu CyFun-o &trade; encryption script with AES128 encryption.

Sample files are in this repo

```bash
#!/bin/bash

: '
usage ./cyfuno.sh file file

#tidy up files - work on this later
#head -n 4 file1 > discard.txt
#tail -n +5 file1 > 1.bin
'

#create unique passwords

pass1="$(openssl rand -base64 16)"
pass2="$(openssl rand -base64 16)"

#create unique IVs
iv1="$(openssl rand -hex 8)"
iv2="$(openssl rand -hex 8)"

#echo $pass1
#echo $pass2
#echo $iv1
#echo $iv2

#encrypt files with the unique passwords and IVs
openssl enc -AES-128-CTR -S "$iv1" -pass "pass:$pass1" -in "$1" -out "$1.enc"
openssl enc -AES-128-CTR -S "$iv1" -pass "pass:$pass1" -in "$2" -out "$2.enc"
```
