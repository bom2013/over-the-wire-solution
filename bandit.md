# [The Bandit wargame](https://overthewire.org/wargames/bandit/)
host: [bandit.labs.overthewire.org](bandit.labs.overthewire.org)  
port: 2220  
username: bandit<level>  
start password: bandit0  
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
 
```
password:  


### level 16 -> 17
```shell
 
```
password:  


### level 17 -> 18
```shell
 
```
password:  


### level 18 -> 19
```shell
 
```
password:  


### level 19 -> 20
```shell
 
```
password:  

### level 20 -> 21
```shell
 
```
password:  

### level 21 -> 22
```shell
 
```
password:  

### level 22 -> 23
```shell
 
```
password:  

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

