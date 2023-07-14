---
title: The RSA Algorithm
author: ClubMan
date: 2023-07-14 22:30:00 +0800
categories: [Cryptography, RSA Algorithm]
tags: [RSA Algorithm]
render_with_liquid: false
---


RSA algorithm is an asymmetric cryptography algorithm. Asymmetric actually means that it works on two different keys i.e. Public Key and Private Key. 

## knowing the facts
1) The prime numbers from 1 to 100 are: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, **53**, **59**, 61, 67, 71, 73, 79, 83, 89, 97. 

2) The Euler phi function, written **ϕ(n)** for positive integers n.


## Creating the Public Key 
```
First step we will select two prime numbers, in this example using P = 53 and Q = 59.

The public key is made of both exponent 'n' & 'e'

P * Q = n
53 * 59 = 3127
Therefore n = 3127

'e' must be an integer & "1 < e < Φ(n)"
In this example, we will use a small value for e, which is 3.

Note: The number 'e' is called "public key exponent". It is usually 65537 (0x010001).

```

## Creating the Private Key 
```

The equation to get the the private key exponent 'd'

d = (k*Φ(n) + 1) / e 

In this example, let k =2

First we will compute Φ(n) = (P-1)(Q-1)
3016 = (53-1)(59-1)
Φ(n) = 3016

d = (2*3016 + 1) / 3

Therefore d = 2011

```

## The Encryption
```

In this exercise, we will encrypt plaintext "clubman".

First covert each letter to number as follow:
3 12 21 2 13 1 14 

The formula
Modular Exponentiation Calculator a^b mod n
(31221213114^e) mod n = 1978

```

> Reference link
{: .prompt-info}
<a target="_blank" href="https://www.geeksforgeeks.org/rsa-algorithm-cryptography/">https://www.geeksforgeeks.org/rsa-algorithm-cryptography/</a>

<a target="_blank" href="https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts">https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts</a>

<a target="_blank" href="https://www.dcode.fr/modular-exponentiation">The calculator</a>

