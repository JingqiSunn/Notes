#### Secure Hash Standard

**Main Usage**

This standard specifies hash algorithms that can be used to generate digests of messages, and can be used to detect whether messages have been changed since the digests were generated.

**The Maximum Length of Input Messages**

*$2^{64}$ bits*: SHA-1, SHA-224, SHA-256.

*$2^{128}$ bits*: SHA-384, SHA-512, SHA-512/224, SHA-512/256.

**The Length of the Output**

160-512 bits, depending on the type of the algorithm.

**Other Algorithm that can be Used with the Hashing Algorithm**

1. Digital Signature Algorithm
2. Keyed-hash Message authentication Codes
3. In the Generation of Random Numbers

**Characteristic**

1.  It is irreversible.
2. Any changes to the input message will likely turn out to be a very big difference in the output digest.

**Some Definitions**

*Message Digest:* The output of the hash code algorithm

*FIPS:* Federal Information Processing Standard

*NIST:* National Institute of Standards and Technology

*SHA:* Secure Hash Algorithm

*SP:* Special Publication

*a,b,c,d:* The Words Inputs for the Secure Hash Algorithm

*$H^{(i)}$:* The $i^{th}$ dimension of the output of the Secure Hash Algorithm

*$H_j$:* The Output of the Secure Hash Algorithm for the $j^{th}$ word

*$H_j^{(i)}$:* The $i^{th}$ dimension of the output of the Secure Hash Algorithm for the $j^{th}$​ word

**Secure Hash Algorithm Properties**

|  Algorithm  | Message Size | Block Size | Word Size | Message Digest Size(bits) |
| :---------: | :----------: | :--: | :--: | :--: |
|    SHA-1    |      $2^{64}$        | 512 | 32 | 160 |
|   SHA-224   | $2^{64}$ | 512 | 32 | 224 |
|   SHA-256   | $2^{64}$ | 512 | 32 | 256 |
|   SHA-384   | $2^{128}$ | 1024 | 64 | 384 |
|   SHA-512   | $2^{128}$ | 1024 | 64 | 512 |
| SHA-512/224 | $2^{128}$ | 1024 | 64 | 224 |
| SHA-512/256 | $2^{128}$ | 1024 | 64 | 256 |

**Big-endian Convention**

Here are some examples about this big-endian convention.

*Input:*

``` 
1010 0001 0000 0011 1111 1110 0010 0011
```

*Output:*

```
a103fe23
```

*Input:*

```
1010 0001 0000 0011 1111 1110 0010 0011 
0011 0010 1110 1111 0011 0000 0001 1010
```

*Output:* 

```
a103fe2332ef301a
```

> [!IMPORTANT]
>
> We will find that the most significant bit is stored in the left-most bit position.

**Represent Integers in Bits(Words) Separately**

Any integer between 0 and $2^{32}-1$ can be represented by a 32-bit words.

Here is an example:

If i want to use 32 bits to represent the number 291.

*Input:* 

```
291
```

*Output(In Binomial):*

```
0000 0000 0000 0000 0000 0001 0010 0011
```

But basically we will use hex numbers to represent it.

*Output(In Hex):*

```
00000123
```

In the same way, any integer between 0 and $2^{64}-1$​ can be represented as a 64-bit word.

**Represent Integers in Bits(Words) Compound**

Here is the introduce question:

> What if we can just calculate the decimal to hex when the integer is in the range of $[0,2^{32}-1]$, but now we need to convert an integer $\Z$ in $[2^{32},2^{64}-1]$​ to hex information.

Solution:

Parallelly we can represent the decimal integer $\Z$ as $X\times 2^{32}+Y$ when $X$ and $Y$ are two decimal integer in the range of $[0,2^{32}-1]$. We know that we can actually convert $X$ and $Y$ into the hex information $x$ and $y$ here because they are in the  range of $[0,2^{32}-1]$.

Then we will represent the hex information of $\Z$ by the expression $(x,y)$, this property will be used for SHA-1, SHA-335, and SHA-256.

> [!TIP]
>
> When the range of the input $\Z$ enlarged by two, this time you can also enlarge the range of $X$ and $Y$, after that you can finish this problem in the same way.
>
> This property is used in SHA-384, SHA-512, SHA-512/224, SHA-512/256 

**Operation on Words**



**Other Resources**

https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf

