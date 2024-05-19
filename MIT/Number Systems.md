
# Decimal Number System

Decimal means **base 10**, hence the prefix **dec**. In this number system, the digits that can be used to count are 0,1,2,3,4,5,6,7,8,9. These are **10** symbols. 

When a number system is **at least equal to** the base, **place values** are used.

In any number system, the counting always starts at **0**.

Decimal forms in this note will be represented as **N**<sub>10</sub>; with N being any interger.

Example: The number **1,234**<sub>10</sub>:
	This can be represented as: 1\*10\*\*3 + 2 \*10\*\*2 + 3 \*10\*\*1 + 4 \*10\*\*0. This is the same number in an **expanded form**.
	**1**<sub>10</sub> is in the **thousands** place. 
	**2**<sub>10</sub> is in the **hundreds** place.
	**3**<sub>10</sub> is in the **tens** place.
	**4**<sub>10</sub> is in the **ones** place.


Example 2: The number **1234.567**<sub>10</sub> :
	This can be represented as: 1\*10\*\*3 + 2 \*10\*\*2 + 3 \*10\*\*1 + 4 \*10\*\*0 + 5 \*10\*\***-1** + 6 \*10\*\***-2** + 7 \*10\*\***-3**
	**5**<sub>10</sub>  is in the **tenths** place.
	**6**<sub>10</sub> is in the **hundreths** place.
	**7**<sub>10</sub> is in the thousandths place.



# Binary Number System

Binary means **base 2** (i.e. 2 symbols). We can only count from 0~1. This numbering system is commonly used for computers. 

A bit is the **smallest** piece of information stored in a computer. The 2 symbols can be interpreted as **false**, and **true**.

These can be represented as voltage levels **0V** and **+3.3~5V**. 

This number system also uses **place values** to represent bigger numbers and more information.

Example: The binary **1101**<sub>2</sub>:
	This can be represented as: 1\*2\*\*3 + 1 \*2\*\*2 + 0 \*2\*\*1 + 1 \*2\*\*0.
	This is the number 13<sub>10</sub>.


Example: The binary **1101.101**<sub>2</sub>: 
	This can be represented as: 1\*2\*\*3 + 1 \*2\*\*2 + 0 \*2\*\*1 + 1 \*2\*\*0 + 1 \*2\*\*-1 + 0 \*2\*\*-2  + 1 \*2\*\*-3
	This is the number 13.625<sub>10</sub>.


# Series of bits

**Nibble** is a group of 4 bits.

**Byte** is a group of 8 bits.

**Word** is an even number of bytes, usually 4 bytes (32 bits), though it depends on the processor.



In most computers, the smallest unit we can use is a **byte**. The most significant bit (msb) is the the highest place value of that byte, and least significant bit (lsb) is the least.

> [!question]- What is the value of the bit pattern 11111111<sub>2</sub>?
> 255. In 8 bits, the highest number you can reach is 255.



> [!question]- What is the range of values represented by an 8-bit binary number?
> 0~255. 


# Big-end, little-end


There are **two ways** to store bigger numbers. As bigger numbers require more and more **bytes** (not bits), the question of: "which **byte** comes first?" rises. In a **Big-endian** system, the byte with the biggest signifance is stored first, while a **little-endian** system stores the least signficant first. 

When you read a binary expression from left-to-right, you are using the big-endian system. When you read a binary expression from right-to-left, you are using the little-endian system.

IBM mainframes use big-endian, while most modern computers use little-endian. PowerPC (a RISC ISA) understands both systems.


Example: The number 1025<sub>10</sub>.
	Binary: 00000100 00000001<sub>2</sub>.
	Big-endian representation: 00000100 00000001<sub>2</sub>.
	Little-endian representation: 00000001 00000100<sub>2</sub>.

The endian system might be used to represent the bit order in a byte (???).


# Operation on numbers

Base 10:
```	
	11  <- Carry
	145
+	256
---------
	401 <- Sum area
```




Base 2:
