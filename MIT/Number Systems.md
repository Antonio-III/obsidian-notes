
# Decimal Number System

Decimal means **base 10**, hence the prefix **dec**. In this number system, the digits that can be used to count are 0,1,2,3,4,5,6,7,8,9. These are **10** symbols. 

When a number system is **at least equal to** the base, **place values** are used to allocate bigger numbers.

In any number system, the counting always starts at **0**.

Decimal forms in this note will be represented as **N**<sub>10</sub>; with N being any integer.

Example: The number **1,234**<sub>10</sub> (1234, in base 10):
	This can be represented as: $1*(10^3) + 2 *(10^2) + 3 *(10^1) + 4 *(10^0)$. This is the same number in an **expanded form**.
	**1**<sub>10</sub> is in the **thousands** place; exponent of 3. 
	**2**<sub>10</sub> is in the **hundreds** place; exponent of 2.
	**3**<sub>10</sub> is in the **tens** place; exponent of 1.
	**4**<sub>10</sub> is in the **ones** place; exponent of 0.


Example 2: The number **1234.567**<sub>10</sub> :
	This can be represented as: $1 * 10^3 + 2 * 10^2 + 3 * 10^1 + 4 * 10^0 + 5 * 10^{-1} + 6 * 10^{-2} + 7 * 10^{-3}$
	**5**<sub>10</sub>  is in the **tenths** place; exponent of -1.
	**6**<sub>10</sub> is in the **hundredths** place; exponent of -2.
	**7**<sub>10</sub> is in the **thousandths** place; exponent of -3.



# Binary Number System

Binary means **base 2** (i.e. 2 symbols). We can only count: 0,1. This numbering system is commonly used for computers. 

A bit is the **smallest** piece of information stored in a computer. The 2 symbols can be interpreted as **false**, and **true**. These can also be represented as voltage levels **0V** and **+3.3~5V**. 

This number system also uses **place values** to represent bigger numbers and more information.

Example: The binary **1101**<sub>2</sub> (1101<sub>10</sub>, in base 2 context):
	This can be represented as: $1* 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0$.
	This is the number 13<sub>10</sub>.


Example: The binary **1101.101**<sub>2</sub>: 
	This can be represented as: $1 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0 + 1 * 2^{-1} + 0 * 2^{-2} + 1 * 2^{-3}$.
	This is the number 13.625<sub>10</sub>.


# Series of bits

**Nibble** is a group of 4 bits.

**Byte** is a group of 8 bits.

**Word** is an even number of bytes, usually 4 bytes (32 bits), though it depends on the processor.



In most computers, the smallest unit we can use is a **byte**. The most significant bit (msb) is the highest place value of that byte, and least significant bit (lsb) is the least.

> [!question]- What is the value of the unsigned bit pattern 11111111<sub>2</sub>?
> 255\. In 8 bits, the highest number you can reach is 255.



> [!question]- What is the range of values represented by an unsigned 8-bit binary number?
> 0~255. 


# Big-end, little-end


There are **two ways** to store bigger numbers. As bigger numbers require more and more **bytes**, the question of: "which **byte** comes first?" rises. In a **Big-endian** system, the byte with the highest place value is stored first, while a **little-endian** system stores the byte with the lowest place value first.

When a binary expression's place values increase from right to left, you are using the big-endian system. When a binary expression's place values increase from left to right, you are using the little-endian system.

Example: The number 1025<sub>10</sub> stored in 2 bytes. 
	Binary: 00000100 00000001<sub>2</sub>.
	Big-endian representation: 00000100 00000001<sub>2</sub>.
	Little-endian representation: 00000001 00000100<sub>2</sub>.

IBM mainframes use big-endian, while most modern computers use little-endian. PowerPC (a RISC ISA) understands both systems.

The endian system can be used to represent the bit order in a byte. For example, the number 1101<sub>2</sub>:
	In big-endian representation, it is stored as 1101<sub>2</sub>, which is equivalent to: 
	$1 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0 = 13_{10}$.
	In small-endian representation, it is stored as 1011<sub>2</sub> (reverse), which is equivalent to: 
	$1 * 2^0 + 0 * 2^1 + 1 * 2^2 + 1 * 2^3 = 13_{10}$.
	As you can see in the big-endian, the highest place value is stored first (leftmost), and in small-endian, the lowest place value is stored first (leftmost).


# Operation on numbers

Base 10:

```
	11  <- Carry Area
	145
+	256
---------
	401 <- Sum Area
```


The algorithm is to start from **right** to **left**. We add the 2 lowest-significant digit, which are 14**5** and 25**6**. 

If the sum of these 2 numbers is at least equal to the Base, the sum is divided by the Base, and its remainder is put into the Sum Area, and into the same Place Value; i.e. if a *ones-place*'s sum is 10, 0 will be put into the Sum Area's *ones-place*. 



The same principle applies to Base 2.

Base 2:

```
	    1    <- Carry Area
	11100100 <- First Number
+   00000101 <- Second Number
--------------
	11101001 <- Sum Area
```

> [!question] Perform the operation above but use base 10 representation.
> First Number is 228<sub>10</sub>, and Second Number is 5<sub>10</sub>, this results in the sum being 233<sub>10</sub>.
  
Decimal subtraction works similarly as decimal addition; the numbers are aligned, and the operation starts from right to left. The difference is how the arithmetic is performed. In decimal addition, we add regardless of which number is on top and bottom. In decimal subtraction, we reduce the **top** number by the amount of the **bottom** number. 

If the top number is less than the bottom number, we look at the top number's next significant digit, reduce it by 1, and add the radix (base) to the borrower. If this is not possible, a heuristic (a problem-solving shortcut) is to order the bigger number at the top, and the smaller at the bottom, and perform the subtraction. The sign of the bigger number shall be the sign of the resulting difference.

Example:
```
	    3 13 15  <- New Values	
		4  4  5  <- Top Number
	-   2  5  6  <- Bottom Number
		---------
		1  8  9
```


In computer hardware, binary addition is implemented. Therefore, we can use the addition operation when subtracting, by making one of the numbers **negative**. 

$x - y$ can be rewritten as: $x + (-y)$.



# Negative Numbers


Negative numbers are formed with a `-` followed by the absolute value of a number. Negative numbers --if we want them to work with positive numbers-- need to have the sign in the bit pattern.

There are a few ways to implement this.

## Signed Magnitude Representation

This form represents negative numbers by using the leftmost bit as the notation bit. 0 in the leftmost bit means the number is positive, 1 is negative. The remaining bits determine the absolute (or magnitude) value of the number.

| Bit pattern, 4 bits | Number<sub>10</sub>, unsigned | Number<sub>10</sub>, signed magnitude |
| :-----------------: | :---------------------------: | :-----------------------------------: |
|        0000         |               0               |                   0                   |
|        0001         |               1               |                   1                   |
|        0010         |               2               |                   2                   |
|        0011         |               3               |                   3                   |
|        0100         |               4               |                   4                   |
|        0101         |               5               |                   5                   |
|        0110         |               6               |                   6                   |
|        0111         |               7               |                   7                   |
|        1000         |               8               |                  -0                   |
|        1001         |               9               |                  -1                   |
|        1010         |              10               |                  -2                   |
|        1011         |              11               |                  -3                   |
|        1100         |              12               |                  -4                   |
|        1101         |              13               |                  -5                   |
|        1110         |              14               |                  -6                   |
|        1111         |              15               |                  -7                   |

The downside to this representation is that the amount of available numbers is halved, since we have to save the leftmost bit as the sign bit; there will be 2 zero representations; and subtraction cannot be performed using $x + -(y)$.

For example, adding -1<sub>10</sub> and 1<sub>10</sub> results in -2<sub>10</sub>: 
```
	1001
+   0001 
-----------
	1010
```


## One's Complement

This form represents a negative number by inverting all the bits in place from its unsigned form. 

| Bit pattern, 4 bits | Number<sub>10</sub>, unsigned | Number<sub>10</sub>, one's complement |
| :-----------------: | :---------------------------: | :-----------------------------------: |
|        0000         |               0               |                   0                   |
|        0001         |               1               |                   1                   |
|        0010         |               2               |                   2                   |
|        0011         |               3               |                   3                   |
|        0100         |               4               |                   4                   |
|        0101         |               5               |                   5                   |
|        0110         |               6               |                   6                   |
|        0111         |               7               |                   7                   |
|        1000         |               8               |                  -7                   |
|        1001         |               9               |                  -6                   |
|        1010         |              10               |                  -5                   |
|        1011         |              11               |                  -4                   |
|        1100         |              12               |                  -3                   |
|        1101         |              13               |                  -2                   |
|        1110         |              14               |                  -1                   |
|        1111         |              15               |                   0                   |

The downside of this is the same as the Signed Magnitude Representation's downsides; it has 2 representations of zeroes, and subtraction does not work with $x + -y$. 

For example, adding -2<sub>10</sub> and 3<sub>10</sub> results in 0<sub>10</sub>, when it should be -1<sub>10</sub>.

```
	1101
+	0011
----------
  1|0000  <-- Result
  ^
  End-around Carry
```

However, it is possible to perform this operation by adding the End-around Carry to the result. This makes the answer 1<sub>10</sub>. 

It is also possible to perform subtraction. We perform this similarly to how we subtract in base 10; we align the numbers by their place value, and use borrow if the top value is less than the bottom value. If there are not enough place values, we "imagine" an extra place value to borrow from, and put a 1<sub>2</sub> to the left of the result. This 1<sub>2</sub> is then subtracted from the result to get the correct answer.

For example, lets subtract 19<sub>10</sub> by -3<sub>10</sub>, this should result in 22<sub>10</sub>:
```
  0 1 1 1 2 1 2      <-- New Values	
	0 0 0 1 0 0 1 1  <-- Top Value
-   1 1 1 1 1 1 0 0  <-- Bottom Value
-----------------------
  1|0 0 0 1 0 1 1 1  <-- Result, incomplete (23)
  ^
  End-around Borrow
```

```
	0 0 0 1 0 1 1 1
-   0 0 0 0 0 0 0 1
----------------------
    0 0 0 1 0 1 1 0  <-- Result (22)
```

## Two's Complement

Two's complement form can be obtained by inverting all the bits of an unsigned binary number and adding 1<sub>2</sub> to the result. However, there is an easier way to understand how two's complement works: The most significant bit is coded to have a negative sign, and the rest of the place values are equal to unsigned's place values. When determining the value of a two's bit pattern, we add all of the relevant bits, while keeping in mind that the most significant bit is negative.

In this form, $x + -y$ is possible without extra steps; and there is only 1 representation of zero, meaning 1 more number can be represented. 

The difference between two's and one's is that the most significant bit of two's represents a negative number of unsigned's equivalent place value, whereas one's just inverts unsigned's bits with no regard for place values arithmetic.

| Bit pattern, 4 bits | Number<sub>10</sub>, unsigned | Number<sub>10</sub>, two's complement |
| :-----------------: | :---------------------------: | :-----------------------------------: |
|        0000         |               0               |                   0                   |
|        0001         |               1               |                   1                   |
|        0010         |               2               |                   2                   |
|        0011         |               3               |                   3                   |
|        0100         |               4               |                   4                   |
|        0101         |               5               |                   5                   |
|        0110         |               6               |                   6                   |
|        0111         |               7               |                   7                   |
|        1000         |               8               |                  -8                   |
|        1001         |               9               |                  -7                   |
|        1010         |              10               |                  -6                   |
|        1011         |              11               |                  -5                   |
|        1100         |              12               |                  -4                   |
|        1101         |              13               |                  -3                   |
|        1110         |              14               |                  -2                   |
|        1111         |              15               |                  -1                   |

How -8<sub>10</sub> came to be represented is not possible to explain through its conversion algorithm, as its complementary value is itself. But, we can use its place value rules when converting any two's form to base 10; which is that the most significant bit is negative.

-8<sub>10</sub> is 1000<sub>2</sub> because: $-1 * 2^3 + 0 * 2^2 + 0 * 2^1 + 0 * 2^0 = -8$
-7<sub>10</sub> is 1001<sub>2</sub> because: $-1 * 2^3 + 0 * 2^2 + 0 * 2^1 + 1 * 2^0 = -7$
 5<sub>10</sub> is 0101<sub>2</sub> because: $-0 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0 = 5$

It should be noted that the representation for a positive number within two's form should be equal to unsigned's representation, with added bits if it is the biggest number from unsigned.

## Excess Notation

This form represents a signed number $n$ by the bit pattern of the unsigned number $(n + K)$, where $K$ for an $h$-bit binary word is $2^{e-1}$. For example: The excess-$K$ for a 4-bit number is $2^3 = 8$. 

We can also use the two's complement of a given $n$, and invert its most significant bit.

For example, $2_{10}$ in excess-8 notation is:

$$
\begin{aligned}
2_{10} &= 0010_2 \ &(unsigned, two's) \\
0010_2 \ &= \ !(0)010_2 = 1010 \ &(excess\ 8)
\end{aligned}
$$
