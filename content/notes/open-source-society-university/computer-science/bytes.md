---
title: "bytes"
date: "2022-05-30 02:28"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- bytes
---


# Unit of digital information
0 or 1, 1bit

00 01 10 11 2 bits

...

11111111 8 bits (1 byte)

KiloBytes

MegaBytes

GigaBytes

TeraBytes

PettaBytes

ExaBytes

ZettaBytes

YottaBytes

```
0 0
01 1
10 2
11 3
100 4
1000 8
10000 16
100000 32
1000000 64
10000000 128
11111111 255
```

power of two

overflow = infinite of x resource in games = negative number

```
11111111 255 FF
-1
```

7F half, nibble

unsigned example 0 to 255

signed example -127 to 128

word, double word, quad word

2 bytes, 4 bytes, 8 bytes

when dealing with multiple bytes: know the endianness
big endian and little endian

big endian: first bytes are the most significant
little endian: last bytes are the most significant

7f is 127 which is 011111111

80 is 128 and notice how that is 100000000

f is last digit in hex so the 7 becomes 8 and f goes back to 0

Since FF is 1 byte which is 8 bits

A bit is 0 or 1 so 8 bits goes from 00000001 to 11111111

Unsigned and signed mean how the first digit is used

If the first digit is 1 then negative number

If the first digit is 0 then positive number


the first 4 bytes of any file is the file signature

the file size of the file is specified somewhere in the first bytes too, but i forgot where