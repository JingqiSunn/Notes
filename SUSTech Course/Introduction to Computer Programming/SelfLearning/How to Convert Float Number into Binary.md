#### How to Convert Float Number into Binary

I will just give the example here, suppose I want to translate the float number 15.34 into binary type,

*Solution:*

I have to separate the number 15.34 into two parts 15 and .34 and we will deal with them separately.

For the number 15, we know that the binary type of it is 1111. 

Now let us take .34 a look.

| Number multiplied by Two | Answer | Integral Parts |
| :----------------------: | :----: | :------------: |
|          .34*2           |  0.68  |       0        |
|          .68*2           |  1.36  |       1        |
|          .36*2           |  0.72  |       0        |
|          .72*2           |  1.44  |       1        |
|          .44*2           |  0.88  |       0        |
|          .88*2           |  1.76  |       1        |
|          .76*2           |  1.52  |       1        |
|          .52*2           |  1.04  |       1        |
|          .04*2           |  0.08  |       0        |
|          .08*2           |  0.16  |       0        |
|          .16*2           |  0.32  |       0        |
|          .32*2           |  0.64  |       0        |
|          .64*2           |  1.28  |       1        |
|          .28*2           |  0.56  |       0        |
|          .56*2           |  1.12  |       1        |
|          .12*2           |  0.24  |       0        |
|          .24*2           |  0.48  |       0        |
|          .48*2           |  0.96  |       0        |
|          .96*2           |  1.92  |       1        |
|          .92*2           |  1.84  |       1        |
|          .84*2           |  1.68  |       1        |
|          .68*2           |  1.36  |       1        |
|          .36*2           |  0.72  |       0        |
|          .72*2           |  1.44  |       1        |
|          .44*2           |  0.88  |       0        |
|          .88*2           |  1.76  |       1        |
|          .76*2           |  1.52  |       1        |
|          .52*2           |  1.04  |       1        |
|          .04*2           |  0.08  |       0        |
|          .08*2           |  0.16  |       0        |
|          .16*2           |  0.32  |       0        |
|          .32*2           |  0.64  |       0        |
|          .64*2           |  1.28  |       1        |
|          .28*2           |  0.56  |       0        |
|          .56*2           |  1.12  |       1        |
|          .12*2           |  0.24  |       0        |
|          .24*2           |  0.48  |       0        |
|          .48*2           |  0.96  |       0        |
|          .96*2           |  1.92  |       1        |
|          .92*2           |  1.84  |       1        |
|          .84*2           |  1.68  |       1        |
|          .68*2           |  1.36  |       1        |
|          .36*2           |  0.72  |       0        |
|          .72*2           |  1.44  |       1        |
|          .44*2           |  0.88  |       0        |
|          .88*2           |  1.76  |       1        |
|          .76*2           |  1.52  |       1        |
|          .52*2           |  1.04  |       1        |
|          .04*2           |  0.08  |       0        |
|          .08*2           |  0.16  |       0        |
|          .16*2           |  0.32  |       0        |
|          .32*2           |  0.64  |       0        |
|          .64*2           |  1.28  |       1        |
|          .28*2           |  0.56  |       0        |
|          .56*2           |  1.12  |       1        |
|          .12*2           |  0.24  |       0        |
|          .24*2           |  0.48  |       0        |
|          .48*2           |  0.96  |       0        |
|          .96*2           |  1.92  |       1        |
|          .92*2           |  1.84  |       1        |
|          .84*2           |  1.68  |       1        |
|          .68*2           |  1.36  |       1        |
|          .36*2           |  0.72  |       0        |
|          .72*2           |  1.44  |       1        |

Then we will find that for the integer part, the binary part is 1111, and for the decimal part, the binary is 0101011100001010001111010111000010100011110101110000101000111101, and as we see here, it will have no end, so the binary number is just an approximation.

and we have to combine these two things together.

|        Type         |                          Expression                          |
| :-----------------: | :----------------------------------------------------------: |
|       Decimal       |                           $15.34 $                           |
|       Binary        | $1111.0101011100001010001111010111000010100011110101110000101000111101$ |
| Scientific Notation | $1.1110101011100001010001111010111000010100011110101110000101000111101\times 10^3$ |
|       32-BIT        |         $0~~~~ 10000010~~~~ 11101010111000010100011$         |
|     64 - Double     | $0~~~~10000000010~~~~1110101011100001010001111010111000010100011110101110$ |

*Website can examine:* 

https://www.h-schmidt.net/FloatConverter/IEEE754.html

https://binaryconvert.com/convert_double.html

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240303163824224.png" alt="image-20240303163824224" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240303163914541.png" alt="image-20240303163914541" style="zoom:33%;" />

There is a very big question that why the results are different.

But anyway, we have already mastered the method to convert the decimal numbers into binaries.

**The Format For Data Memorization As a Float 32-BIT**
$$
x_{Signbit}~~xxxxxxxx_{ Eight~Exponetionalbits}~~xxxxxxx...xxxx_{Twentythree~Fractionbits}
$$
**The Format For Data Memorization As a Double 64-BIT**
$$
x_{Signbit}~~xxxxxxxxxxx_{ Eleven~Exponetionalbits}~~xxxxxxx...xxxx_{Fiftytwo~Fractionbits}
$$
**The Calculation for the Exponentialbit**

This is ruled by IEEE 754.

*IEEE 754: 32-BIT Floating Point Notation Exponential Bias: 127*

​		64-BIT Double Point Notation Exponential Bias: 1023

**More resources**

https://stackoverflow.com/questions/3954498/how-to-convert-float-number-to-binary

https://www.youtube.com/watch?v=9UPzza_OMe4&amp;ab_channel=SankarSrivatsa

https://www.youtube.com/watch?v=8afbTaA-gOQ&amp;ab_channel=AbishaliniSivaraman



