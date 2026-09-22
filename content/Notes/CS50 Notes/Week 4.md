---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
RGB color convention uses  8 bit =1 byte numbers (from $0$ to $2^{8}-1=255$)
using hexadecimal (base-16) that number 8bit number is a 2hex number.

a canvas of memory would from 0 to F to 10 to 1F to ......FFFFFFFF

to know which base system we use and that we use the hexadecimal system we prefix every number with as 0x.
so we have 0x0,0x1,...,0xF,0x10,...,0x1F,...$

integers are four bytes, (octet) 

the & gets the address of a variable 

%p to prints the address 

the asterisks uses:

```
int *p = &n;
printf("%d\n",*p);
```
"pronounced int star p"
* after a data type we have an * which means that p in this case is an address of that data type 
*  the asterisks before the pointer also indicates the "go" for the value that the pointer is pointing to which in this case is n it is called dereferencing 

for pointers we have 64bits of memory equivalent of 8 bytes (octets)

a string s is a pointer that holds the address of an array starting from the beginning, s represents the beginning and /0 represents the end

valgrind gives u a summary for memory leaks or any other mistakes that perhaps u wouldn't notice . it is done by valgrind ./programme

## What I've learnt in the exercises

I've learnt how to use different data structures like uint16_t uint8_t which are 16 and 8 bytes
I've trained more on manipulating files including .daw .jpg and bitmaps
I've learnt new functions to apply and use like the sprintf which prints value to a string based on specific format
I got reintroduced to some pointer arithmetic and binary algebra
I've used the RGBTRIPLE data type which is structure that includes thr red green and blue colors represented  by a two-byte integer 

## Things to learn more
what is actually atof and getopt
