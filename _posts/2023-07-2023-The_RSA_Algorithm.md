---
title: The RSA Algorithm
author: ClubMan
date: 2023-07-12 22:30:00 +0800
categories: [Cryptography, Everything]
tags: [RSA Algorithm]
render_with_liquid: false
---

## The RSA Algorithm

RSA algorithm is an asymmetric cryptography algorithm. Asymmetric actually means that it works on two different keys i.e. Public Key and Private Key. 


Public Key Math
```
Select two prime no's. Suppose P = 53 and Q = 59.
Now First part of the Public key  : n = P*Q = 3127.
 We also need a small exponent say e : 
But e Must be 
An integer.
Not be a factor of Φ(n). 
1 < e < Φ(n) [Φ(n) is discussed below], 
Let us now consider it to be equal to 3.
    Our Public Key is made of n and e
```

> Reference link
{: .prompt-info}
<a target="_blank" href="https://www.geeksforgeeks.org/rsa-algorithm-cryptography/">https://www.geeksforgeeks.org/rsa-algorithm-cryptography/</a>
<a target="_blank" href="https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts">https://cryptobook.nakov.com/asymmetric-key-ciphers/the-rsa-cryptosystem-concepts</a>

