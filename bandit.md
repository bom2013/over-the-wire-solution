# [The Bandit wargame](https://overthewire.org/wargames/bandit/)
host: [bandit.labs.overthewire.org](bandit.labs.overthewire.org)  
port: 2220  
username: bandit<level>  
start password: bandit0  
### login via ssh
```
ssh bandit<level>@bandit.labs.overthewire.org -p 2220
```
### level 0 -> 1
```shell
cat readme
```
password:  
boJ9jbbUNNfktd78OOpsqOltutMc3MY1

### level 1 -> 2
```shell
cat ./-
```
password:  
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

### level 2 -> 3
```shell
cat "spaces in this filename"
```
password:  
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

### level 3 -> 4
```shell
cat ./inhere/.hidden
```
password:  
pIwrPrtPN36QITSp3EQaw936yaFoFgAB


### level 4 -> 5
```shell
file ./-file*
cat ./-file07
```
password:  
koReBOKuIDDepwhWk7jZC0RTdopnAYKh

### level 5 -> 6
```shell
file ./ -size 1033c
cat ./maybehere07/.file2
```
password:  
DXjZPULLxYr17uwoI01bNLQbtFemEgo7

### level 6 -> 7
```shell
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
password:  
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

### level 7 -> 8
```shell
grep 'millionth' data.txt
```
password:  
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

### level 8 -> 9
```shell
sort data.txt | uniq -u 
```
password:  
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

### level 9 -> 10
```shell
strings data.txt | grep '=' 
```
password:  
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

### level 10 -> 11
```shell
base64 -d data.txt 
```
password:  
IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

### level 11 -> 12
```shell
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' 
```
password:  
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

### level 12 -> 13
```shell
mkdir /tmp/benshlom
xxd -r data.txt > /tmp/benshlom/data.txt
cd /tmp/benshlom
zcat data.txt | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
cd -
rm -r /tmp/benshlom
```
password:  
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

### level 13 -> 14
```shell
ssh -i sshkey.private bandit14@localhost
cat /etc/bandit_pass/bandit14
```
password:  
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

### level 14 -> 15
```shell
telnet localhost 30000
```
password:  
BfMYroe26WYalil77FoDi9qh59eK5xNr

### level 15 -> 16
```shell
openssl s_client -connect localhost:30001
```
password:  
cluFn7wTiGryunymYOu4RcffSxQluehd

### level 16 -> 17
```shell
nmap -p 31000-32000 -sV localhost
echo cluFn7wTiGryunymYOu4RcffSxQluehd | openssl s_client -quiet -connect localhost:31790
password:  
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
touch /tmp/key.key
nano /tmp/key.key
cd /tmp
chmod 600 key.key
ssh -i key.key bandit17@localhost
```

### level 17 -> 18
```shell
diff passwords.new passwords.old
<Now login using the password>
```
password:  
kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

### level 18 -> 19
```shell
ssh -T bandit18@localhost
cat readme
```
password:  
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

### level 19 -> 20
```shell
./bandit20-do cat /etc/bandit_pass/bandit20
```
password:  
GbKksEFF4yrVs6il55v6gwY5aVje5f0j

### level 20 -> 21
```shell
tmux
Ctrl+b c
```
#### Shell 1:
```shell
nc -l 1234 < /etc/bandit_pass/bandit20
```
#### Shell 2:
```shell
./suconnect 1234
```

password:  
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr

### level 21 -> 22
```shell
cd /etc/cron.d
cat cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
password: 
Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI 

### level 22 -> 23
```shell
cd /etc/cron.d
cat cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
cat /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
```
password:  
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n

### level 23 -> 24
```shell
 
```
password:  

### level 24 -> 25
```shell
 
```
password:  

### level 25 -> 26
```shell
 
```
password:  

### level 26 -> 27
```shell
 
```
password:  

### level 27 -> 28
```shell
 
```
password:  

### level 28 -> 29
```shell
 
```
password:  

### level 29 -> 30
```shell
 
```
password:  

### level 30 -> 31
```shell
 
```
password:  

### level 31 -> 32
```shell
 
```
password:  

### level 32 -> 33
```shell
 
```
password:  

