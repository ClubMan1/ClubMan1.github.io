---
title: The RSA Algorithm
author: ClubMan
date: 2023-07-14 22:30:00 +0800
categories: [Cryptography, RSA Algorithm]
tags: [RSA Algorithm]
render_with_liquid: false
---


RSA algorithm is an asymmetric cryptography algorithm. Asymmetric actually means that it works on two different keys i.e. Public Key and Private Key. 

## Know the facts
s/n 1: The **prime numbers** from 1 to 100 are: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, **53**, **59**, 61, 67, 71, 73, 79, 83, 89, 97. 

s/n 2: The **Euler phi function**, written **ϕ(n)** for positive integers n.


## Creating the Public Key 
```
First step we will select two prime numbers, in this example using P = 53 and Q = 59.

The public key is made of both exponent 'n' & 'e'

Calculate n: 
P * Q = n
53 * 59 = 3127

Choose an encryption key: Let's select e = 3.
'e' must be an integer & "1 < e < Φ(n)"


Note: The number 'e' is called "public key exponent". It is usually 65537 (0x010001).

```

## Creating the Private Key 
```

The equation to get the the private key exponent 'd'

d = (k*Φ(n) + 1) / e 

In this example, let k =2

Calculate φ(n): 
First we will compute Φ(n) = (P-1)(Q-1)
3016 = (53-1)(59-1)
Φ(n) = 3016

d = (2*3016 + 1) / 3

Therefore d = 2011

```

## The Encryption
```

In this exercise, we will encrypt plaintext "clubman".

Plaintext: "clubman"
Numerical values: 2-11-20-1-12-0-13

The formula
Modular Exponentiation Calculator (Numerical values)^e mod n

Encryption:
Encrypt '2': c1 = (2^3) % 3127 = 8
Encrypt '11': c2 = (11^3) % 3127 =  1331
Encrypt '20': c3 = (20^3) % 3127 =  1746
Encrypt '1': c4 = (1^3) % 3127 =  1
Encrypt '12': c5 = (12^3) % 3127 = 1 1728
Encrypt '0': c6 = (0^3) % 3127 =  0
Encrypt '13': c7 = (13^3) % 3127 =  2197

The encrypted message is the concatenation of the resulting ciphertext values: 8-1331-1746-1-1728-0-2197.

```

## The Decryption 
```

Decrypting the ciphertext values: 8-1331-1746-1-1728-0-2197.

The formula
Modular Exponentiation Calculator (Numerical values)^d mod n

Decrypt:
Decrypt '8': m1 = (8^2011) % 3127 = 2
Decrypt '1331': m2 = (1331^2011) % 3127 = 11
Decrypt '1746': m3 = (1746^2011) % 3127 = 20
Decrypt '1': m4 = (1^2011) % 3127 = 1
Decrypt '1728': m5 = (1728^2011) % 3127 = 12
Decrypt '0': m6 = (0^2011) % 3127 = 0
Decrypt '2197': m7 = (2197^2011) % 3127 = 13

Convert this numerical value back into plaintext, we can use the mapping A=0, B=1, C=2, and so on.
Hence, the corrected decrypted message for the ciphertext "8-1331-1746-1-1728-0-2197" is "clubman".

```

> Reference link
{: .prompt-info}

<a target="_blank" href="https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts">https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts</a>

<a target="_blank" href="https://www.dcode.fr/modular-exponentiation">www.dcode.fr</a>

