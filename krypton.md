# [The Krypton wargame](https://overthewire.org/wargames/krypton/)
host: [krypton.labs.overthewire.org](krypton.labs.overthewire.org)  
port: 2231  
username: krypton<level>  
start password: bandit0  
### login via ssh
```
ssh krypton<level>@krypton.labs.overthewire.org -p 2231
```

### level 0 -> 1
S1JZUFRPTklTR1JFQVQ= -> [decode from base64] -> KRYPTONISGREAT
**password:**  
KRYPTONISGREAT

### level 1 -> 2
YRIRY GJB CNFFJBEQ EBGGRA -> [Decode from ROT13] -> LEVEL TWO PASSWORD ROTTEN
**password:**  
ROTTEN

### level 2 -> 3
OMQEMDUEQMEK -> [Decode from Caesar Cipher(+12 shift)] -> CAESARISEASY
**password:**  
CAESARISEASY

### level 3 -> 4
Use [frequency analysis tool online](https://math.dartmouth.edu/~awilson/tools/frequency_analysis.html) to find the substitution
```shell
cd /krypton/krypton3
cat krypton4 | tr ABCDEFGHIJKLMNOPQRSTUVWXYZ BOIHGKNQVTWYURXZAJEMSLDFPC
```
**password:**  
WELL DONE THE LEVEL FOUR PASSWORD IS **BRUTE**

### level 4 -> 5
Use [Vigenere dechiper](https://www.boxentriq.com/code-breaking/vigenere-cipher) on found1  
-> key = 'frekey'  
-> krypton5 = 'CLEAR TEXT'  
**password:**  
CLEARTEXT

### level 5 -> 6
```shell
Use [Vigenere dechiper](https://www.boxentriq.com/code-breaking/vigenere-cipher) on found1  
-> key = 'keylength'  
-> krypton6 = 'RANDO M'  
```
**password:**  
RANDOM

### level 6 -> 7
```shell

```
**password:**  
