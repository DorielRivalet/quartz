---
title: "euler-number"
date: "2022-06-25 01:40"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- euler
- definition
- c
- recursion
- math
- calculus
- limits
---

# Metadata
2022-06-25 01:40  | euler-number | [Doriel Rivalet](https://github.com/DorielRivalet)

# Content
Concept of growth
$$e\approx1.00000001^{100000000}$$
$$e:=\lim_{n\rightarrow\infty}(1+\frac1{n})^n$$
$$e=\sum_{n=0}^\infty \frac1{n!}$$
$$\frac{d}{dx}e^x=e^x$$
$$\int_1^t\frac{1}{x}dx=1$$
```c
#include <stdio.h>

float factorial (int n) {
	if (n >= 1)
		return n*(factorial(n-1));
	else
		return 1;
}

float euler(int iterations, int n){
	# RECURSION WITHIN RECURSION
	if (iterations >= 1)
		return (1/factorial(n))+(euler(iterations-1,n+1));
	else
		return 1/factorial(n+1);
}

int main () {
	int iterations = 10;
	int n = 0;
	float e = euler(iterations,n);
	printf("eulers number with %d iterations is %f",iterations,e);
	return 0;
}

```


# Sources
Own notes (with help of calculator and online c compiler)

https://www.youtube.com/watch?v=sKtloBAuP74

https://www.youtube.com/watch?v=pg827uDPFqA

https://www.youtube.com/watch?v=rbmUqseGOOM


# Content Lists
If you prefer browsing the contents of this site through a list instead of a graph, you can find content lists here too:

- [All Notes](notes/)
