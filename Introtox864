Task 1 Description and Objectives

firrst I began by ssh into attack box
```ssh tryhackme@10.10.30.43 ```
used password <reismyfavl33t>

Task 2 Introduction

used ls to list directories, found introduction and used commands below tochange drectory and execute the intro file
```cd introduction```
```./intro```
I then used this commands uses the radar2 framework which opened the binary into debugging mode
```r2 -d intro```
next command is used to ask r2 to analyze the program using this command
```aa``
I then set the language to the AT&T with this command
```e asm.syntax=att```
next I ran command afl to list the functions
```afl```
next command is for print disassembly function
```pdf @main```
Read material about the columns

Task 3 If Statements

read material about the if statements
practiced various jump instructions with commands below
```cmpq source2, source1```
```testq source2, source1```

Task 4 If Statements Continued

exited current program
```cd ..```
```ls```
```cd if-statements```
Once in the right lcoation, I started r2 with following command
```r2 -d if1```
```aaa``    command to analyze program
```afl```  to list functions
```pdf @main```  used to print disassembly functions
used the following commands below to set the breakpoints for jge and jmp by using the hex
```db 0x560a3283d612```
```db 0x560a3283d618```
ran command below to execute progrm and stop at the breakpoints
```dc```
message indicates breakpoint hit
Typed next command to receive the values of the registers
```dr```
to find the position of var_4h, i ran command below
```px @rbp-0x4```
used ds command to move to the next set of instructions
```ds```
```pdf @main``` to look at disassembly
ran command below
```px @rbp-0x8```   running var_8h
ran ```ds```  this incremented by five
ran ```@rbp-0x8```  once more to see the change
answered the questions
$99-$3=96
variable $0 = 0
$100-$99=1
the & is used to change the value of var_8h

Task 5 Loops

``` cd loops``` changed driectory
```r2 -d loop1``` start disassembly with loop1
analyzed everything, list functions, and disassembled main

```aaa```
```afl```
```pdf @main```
set breakpoint here   ```db 0x564b3b87b619```
```dc```  shows breakpoint here 
pdf @main
```ds```   move to next instruction
```pdf @main```
ran command ```dr```  to check registers
started to disassemble and check the memory
ran command again ```px @rbp-0xc```
ran various ```ds``` and ```pdf @main```  i was finally back on the correct addl instruction, this proves the loop
answers

value $9-$4=5
$0xa=0
addl $2 is before the compl instructions, thus is answer 2
movl $0,   the %eax is the end, thus answer is 0

Task 6 Crackme1
commands below>>>>  first exited and changed to crckme folder using ```ls, cd```

```r2 -d crackme1```
```aaa```
```afl```
```pdf @main```

tried many break ponts rinse and repeat with ds to move along the instruction set.
pdf @main to view in between each one

set my breakpoint to the first fail   
```db 0x565064ad88c9```

[0x7fa0e061d090]> db 0x565064ad88c9
[0x7fa0e061d090]> 
[0x7fa0e061d090]> dc
enter your password
this is hard
Wrong Password
[0x7fa0e030fe06]> dc
child exited with status 255

==> Process finished

[0x7fa0e061d090]> db 0x565064ad88c9
Cannot open '/proc/1540/maps': No such file or directory
Cannot open '/proc/1540/maps': No such file or directory
Breakpoint already set at this address.
Cannot set breakpoint at '0x565064ad88c9'
[0x7fa0e061d090]> dc
Cannot continue, run ood?
[0x7fa0e030fe06]> yes
Usage: y[ptxy] [len] [[@]addr]   # See wd? for memcpy, same as 'yf'.
| y               show yank buffer information (srcoff len bytes)
| y 16            copy 16 bytes into clipboard
| y 16 0x200      copy 16 bytes into clipboard from 0x200
| y 16 @ 0x200    copy 16 bytes into clipboard from 0x200
| y!              open cfg.editor to edit the clipboard
| y*              print in r2 commands whats been yanked
| yj              print in JSON commands whats been yanked
| yz [len]        copy nul-terminated string (up to blocksize) into clipboard
| yp              print contents of clipboard
| yq              print contents of clipboard in hexpairs
| yx              print contents of clipboard in hexadecimal
| ys              print contents of clipboard as string
| yt 64 0x200     copy 64 bytes from current seek to 0x200
| ytf file        dump the clipboard to given file
| yf 64 0x200     copy file 64 bytes from 0x200 from file
| yfa file copy   copy all bytes from file (opens w/ io)
| yfx 10203040    yank from hexpairs (same as ywx)
| yw hello world  yank from string
| ywx 10203040    yank from hexpairs (same as yfx)
| yy 0x3344       paste clipboard
[0x7fa0e030fe06]> dc
Cannot continue, run ood?
[0x7fa0e061d090]> no
|ERROR| Invalid command 'no' (0x6e)
[0x7fa0e061d090]> dc
Cannot continue, run ood?
[0x7fa0e030fe06]> dc
Cannot continue, run ood?
[0x7fa0e061d090]> dc
Cannot continue, run ood?
[0x7fa0e030fe06]> ood
Process with PID 1546 started...
File dbg:///home/tryhackme/crackme/crackme1  reopened in read-write mode
= attach 1546 1546
ptrace (PT_ATTACH): Operation not permitted
Unable to find filedescriptor 3
Unable to find filedescriptor 3
ptrace (PT_ATTACH): Operation not permitted
1546
not sure what ood did but permission not allowed

after many hours..............................   I saw the decimals which reminded me of ip's
255.255.255.0.  this locked up the program
0.0.0.0    code below>>>

           0x565064ad88d0      ff             invalid
..
|           0x565064ad88d5      ff             invalid
..
|           0x565064ad88da      ff             invalid
..
|           ; CODE XREF from main (0x565064ad888e)
|           0x565064ad88de      ff             invalid
..
|           0x565064ad88e3      ff             invalid
..
|           0x565064ad88e5      ff             invalid
..
|           0x565064ad88e9      ff             invalid
..
|           0x565064ad88eb      ff             invalid                 ; 0x565064ad89d8 ; str.You_ve_got_the_correct_password                                                                 
..
|           0x565064ad88f2      ff             invalid
..
|           0x565064ad88f7      ff             invalid
..
|           ; CODE XREF from main (0x565064ad88c7)
|           0x565064ad88fc      ff             invalid
..
|           0x565064ad8900      ff             invalid
..
|           0x565064ad8909      ff             invalid
..
|           0x565064ad890b      ff             invalid
..
|           0x565064ad8910      ff             invalid
|           0x565064ad8911      ff             invalid
[0x7fc52c62b090]> dc
locked my shell started over

```r2 -d crackme1```
```aaa```
```afl```
```pdf @main```
code in the begining was very familiar especially the 127
0x7f02c0f63090]> pdf @main
/ (fcn) main 280
|   int main (int argc, char **argv, char **envp);
|           ; var int32_t var_54h @ rbp-0x54
|           ; var int32_t var_50h @ rbp-0x50
|           ; var int32_t var_4ch @ rbp-0x4c
|           ; var int32_t var_48h @ rbp-0x48
|           ; var int32_t var_40h @ rbp-0x40
|           ; var int32_t var_38h @ rbp-0x38
|           ; var int32_t var_30h @ rbp-0x30
|           ; var int32_t var_28h @ rbp-0x28
|           ; var int32_t var_12h @ rbp-0x12
|           ; var int32_t var_8h @ rbp-0x8
|           ; arg int32_t arg_40h @ rbp+0x40
|           ; DATA XREF from entry0 (0x55dc0560370d)
|           0x55dc056037fa      55             pushq %rbp
|           0x55dc056037fb      4889e5         movq %rsp, %rbp
|           0x55dc056037fe      4883ec60       subq $0x60, %rsp        ; '`'
|           0x55dc05603802      64488b042528.  movq %fs:0x28, %rax     ; [0x28:8]=-1 ; '(' ; 40
|           0x55dc0560380b      488945f8       movq %rax, var_8h
|           0x55dc0560380f      31c0           xorl %eax, %eax
|           0x55dc05603811      488d3d900100.  leaq str.enter_your_password, %rdi ; 0x55dc056039a8 ; "enter your password"
|           0x55dc05603818      e863feffff     callq sym.imp.puts      ; int puts(const char *s)
|           0x55dc0560381d      488d45ee       leaq var_12h, %rax
|           0x55dc05603821      4889c6         movq %rax, %rsi
|           0x55dc05603824      488d3d910100.  leaq 0x55dc056039bc, %rdi ; "%s"
|           0x55dc0560382b      b800000000     movl $0, %eax
|           0x55dc05603830      e89bfeffff     callq sym.imp.__isoc99_scanf ; int scanf(const char *format)
|           0x55dc05603835      c745ac000000.  movl $0, var_54h
|           0x55dc0560383c      488d057c0100.  leaq 0x55dc056039bf, %rax ; "127"
|           0x55dc05603843      488945c0       movq %rax, var_40h
|           0x55dc05603847      488d05750100.  leaq str.01., %rax      ; 0x55dc056039c3 ; u"01.\u7257\u6e6f\u2067\u6150\u7373\u6f77\u6472\u5900\u756f\u7627\u2065\u6f67\u2074\u6874\u2065\u6f63\u7272\u6365\u2074\u6170\u7373\u6f77\u6472\u0100\u031b\u3c3b"                                
|           0x55dc0560384e      488945c8       movq %rax, var_38h
|           0x55dc05603852      488d056a0100.  leaq str.01., %rax      ; 0x55dc056039c3 ; u"01.\u7257\u6e6f\u2067\u6150\u7373\u6f77\u6472\u5900\u756f\u7627\u2065\u6f67\u2074\u6874\u2065\u6f63\u7272\u6365\u2074\u6170\u7373\u6f77\u6472\u0100\u031b\u3c3b"                                
|           0x55dc05603859      488945d0       movq %rax, var_30h
|           0x55dc0560385d      488d05610100.  leaq 0x55dc056039c5, %rax ; u"1.\u7257\u6e6f\u2067\u6150\u7373\u6f77\u6472\u5900\u756f\u7627\u2065\u6f67\u2074\u6874\u2065\u6f63\u7272\u6365\u2074\u6170\u7373\u6f77\u6472\u0100\u031b\u3c3b"                        


pdf @main showed 127,0,0,1 in the lines

set breakpoint to JLE which is password input>>>
[0x7f02c0f63090]> db 0x55dc05603890
[0x7f02c0f63090]> dc
enter your password
127.0.0.1
hit breakpoint at: 55dc05603890
[0x55dc05603890]> 

tried that as password and bingo   127.0.0.1

Task7 crackme2

exited binary 1 and entered binary crackme2

```exit```
```ls```
```r2 -d crackme2```
```aaa```
```afl```
```pdf @main```

set brekpoint to 0x559094cf3899 which is wrong password

tried password tryhackme failed

after many hours i thought outside the box,    >>>>

code below
```0x560fa32e5980  415e 415f c390 662e 0f1f 8400 0000 0000  A^A_..f.........                                                                     0x560fa32e5990  f3c3 0000 4883 ec08 4883 c408 c300 0000  ....H...H.......  ; sym.__libc_csu_fini  ; sym._fini  ; [15] -r-x section size 9 name0x560fa32e59a0  0100 0200 0000 0000 656e 7465 7220 796f  ........enter yo  ; obj._IO_stdin_used  ; [16] -r-- section size 88 named .rodata  ; 0x560fa32e59b0  7572 2070 6173 7377 6f72 6400 2573 0031  ur password.%s.1                                                                     0x560fa32e59c0  3237 0030 0031 002e 0057 726f 6e67 2050  27.0.1...Wrong P  ; str.01.  ; str.Password                                          0x560fa32e59d0  6173 7377 6f72 6400 596f 7527 7665 2067  assword.You've g  ; str.You_ve_got_the_correct_password                              0x560fa32e59e0  6f74 2074 6865 2063 6f72 7265 6374 2070  ot the correct p                                                                     0x560fa32e59f0  6173 7377 6f72 6400 011b 033b 3c00 0000  assword....;<...  ; loc.__GNU_EH_FRAME_HDR  ; [17] -r-- section size 60 named .eh_fra[0x560fa32e56f0]> q
Do you want to quit? (Y/n) y
Do you want to kill the process? (Y/n) 
tryhackme@ip-10-10-30-43:~/crackme$ cd /home/tryhackme
tryhackme@ip-10-10-30-43:~$ ls
crackme  if-statement  install-files  introduction  loops  radare2
tryhackme@ip-10-10-30-43:~$ cd install-files/
tryhackme@ip-10-10-30-43:~/install-files$ ls
secret.txt
tryhackme@ip-10-10-30-43:~/install-files$ cat secret.txt 
vs3curepwd

tried password   vs3curepwd failed

transposed secret like a mirror>>> dwperuc3sv

correct password   dwperuc3sv





























