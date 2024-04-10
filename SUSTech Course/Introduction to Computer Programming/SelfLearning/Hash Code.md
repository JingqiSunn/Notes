#### Hash Code

**The Definition of Hashing**

The very basic function of it is to convert data into another type, and the output will always be a fixed-length string of letters and numbers, the way we do it is just give the data to a function called the hash function.

For example, if a hash function's aim is to change the information into a 32-character long code, so if you have an input of a word "General", the output will be a 32 characters long hash value. Or if the input is the whole work of Shakespeare, the output will just be a 32 characters long hash.

**How Hash Works**

1. The input is the key, which will directly define the output you will get.
2. The hash function is the very important part of the process.

**How Hash Function Can Make Any Information into a Fixed Sized Characters **

The hash function scan change the value input into some specific hash code, which can be very long and some can be very short. They will be saved at the hash table so it will be very easy to look them up.

**Hashing Algorithms Works with Block Size between 160 and 512 bits**

This is the most popular type of the hash code algorithm.

There is a very famous type of hash code working on the 512 sized block, called the SHA-1.

**SHA-1**

We know that the modern world will always be saved in a space of 32 bits, but in the older generation we will find that the word will always be saved in a space of 16 bits.

Then we will find that the 512 bits can at most save for the 32 words if we think it will save every word in 16 bits.

So if a small message shorter than 32 words, if you put that into the SHA-1 program the output will be a single hash code.

If the massage is bigger than 32 words we will divide it into parts before giving it into the SHA-1, after the degeneration the output will be the combination of the previous part.

**The Properties of the Hash Functions**

1. Deterministic, that any two different input will turn out to be different output.
2. Quick computation,it must be very effective.
3. Irreversible, hash functions are making it impossible to regenerate a message or a file from their hash code. 

**Why We Need to Learn the Hash Code**

1. Message and Data Authentication 
2. Detecting Changes in Data
3. Data Privacy
4. Blockchain
5. Database Management

**Why the Hashing Method is Irreversible**

1. Loss of information, because no matter what kind of thing the input is, the hash code output will always be the fixed size, so there will be a loss in information.
2. Collision Resistance, we will find that the input range is  much larger than the output range so that there will be some moments that there are two same inputs with the same output.

**Message and Data Authentication**

We can change the information by the hashing function then we will find that if the reverse is not a valid sentence we will find that our words have been changed.

**Detecting Changes in Data**

It can enlarge the difference in data.

**Other Resources**

https://www.codecademy.com/resources/blog/what-is-hashing/

