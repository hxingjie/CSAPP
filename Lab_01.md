# Lab_01

## Lab_01 config
install lab data: https://csapp.cs.cmu.edu/3e/labs.html

error: fatal error: bits/libc-header-start.h: No such file or directory
solution: Install 32-bit headers and libraries. Here's how you'd do this on Ubuntu.
shell: sudo apt-get install gcc-multilib

check:
```shell
make
./btest
output: Total points: 0/36
```

## Lab_01_01
使用 ~ 和 & 实现异或
原理: 德摩根定律
A ^ B = ~((~A&B) | (A&~B)) = (~((~A) & (~B))) & (~(A&B))
```c++
int bitXor(int x, int y) {
    return (~((~x) & (~y))) & (~(x&y));
}
```
```shell
make
./dlc -e bits.c
./btest
```

## Lab_01_02
求最小数
四位bit的最小数为: 1000
即 minval == 1 << 3
```c++
int tmin(void) {
    return 1<<31;
}
```
```shell
make
./btest
```

## Lab_01_03
求最最大数
四位bit的最小数为: 0111
~(0111 + 1) == 0111
1111是例外, 要特判: 1111 + 1 == 0000
```c++
int isTmax(int x) {
    return (!(x ^ (~(x+1)))) & (!!((x+1)^0));
}
```
```shell
make
./btest
```

## Lab_01_04
求解奇数位是否为1
& 可以用作取数, 需要的位置为1, 不需要的位置为0
^ 可以用作判断
x & 1010 == 1010 ? true : false
```c++
int allOddBits(int x) {
    int mask = 0xA;
    mask = (mask<<4) | mask;
    mask = (mask<<8) | mask;
    mask = (mask<<16) | mask;
    return ! ((x & mask) ^ mask);
}
```
```shell
make
./btest
```

## Lab_01_05
取相反数
A + ~A = -1, A + neg A =0
取反+1
```c++
int negate(int x) {
    return (~x) + 1;
}
```
```shell
make
./btest
```



