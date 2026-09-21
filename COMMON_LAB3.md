1. Explain how to derive the maximum number that can be stored in one byte. What about two bytes?

We assign to each bit the value of 1 OR 0 so that it can be calculated so that we can find out which maximum can we get from those calculations.

unassigned 8-bit 

128 64 32 16 8 4 2 1

1 1 1 1 1 1 1 1

128+64+32+16+8+4+2+1 = 255 - Adjutant: MAXIMUM UNASSIGNED, had it been higher , it would've been an overflow error

assigned 8-bit 

-128 64 32 16 8 4 2 1

0 1 1 1 1 1 1 1

-0+64+32+16+8+4+2+1 = 127 - Adjutant: MAXIMUM ASSIGNED, had it been higher , it would've been an overflow error

unassigned 16-bit

32768 16384 8192 4096 2048 1024 512 256 128 64 32 16 8 4 2 1

1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1

32768+16384+8192+4096+2048+1024+512+256+128+64+32+16+8+4+2+1=65,535 - Adjutant: MAXIMUM UNASSIGNED , had it been higher , it would've been an overflow error

assigned 16-bit

-32768 16384 8192 4096 2048 1024 512 256 128 64 32 16 8 4 2 1

0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1

-0+16384+8192+4096+2048+1024+512+256+128+64+32+16+8+4+2+1 = 32767 - Adjutant: MAXIMUM ASSIGNED, had it been higher , it would've been an overflow error

2. Why is this maximum number one less than the number of possible combinations of bits in those positions?

Because the counting always start at 0 , the patterns 0000000 are valid and is a complete number. Whenever we try to find the maximum number in a 8-bit. It will always be 255 , because the limit of values that is has as an unassigned value is 0-255. Calculating manually or through this formulae 2^n-1 will always result to 255

3. Given a number x (for example, 0000 0011), what must be done to obtain the representation of its negative (in the two's complement system)? Derive a formula/algorithm (1111 1101).
x=	00000011

2+1=3


FLIPPED X:	11111100

-128+64+32+16+8+4=-4

		+00000011

-4 + 3 = -1

Formulae: FLIPPED + 1

E.G. 	00000101

4+1 = 5 

	11111010

-128+64+32+16+8+2= -6 + 1 = -5

5 + (-5) = 0

X = 11111101

-128+64+32+16+8+4+0+1=-3

!X = 00000010

2

Formulae used - !X + 1 = 2 + 1

X + !X = -3 + 3 = 0

4. Under what conditions does a + b < a if both a and b are positive and represented using 8 bits?

CASE 1:

UNASSIGNED 8-BIT 

a = 200 , b = 100

200+100<200 , 300 < 200 , a is higher than a+b due to an overflown error , the 9th bit cannot get carried over into the 8-bit system.

a+b = 100101100
a+b = 256+32+8+4+2+1 = 300 - OVERFLOW

CASE 2:

ASSIGNED 8-BIT

a = 100 , b = 100

100+100 < 100 , a is higher than a+b due to an overflown error , the result of a + b has become negative.

a+b = 11001000
a+b = -128+64+8 = -56 - NEGATIVE RESULT DUE TO OVERFLOW

CASE 3:

B = 0

a = 100 , b = 0

a+b < a , the condition is false , instead becomes a+b = b

CONCLUSION: a + b < a happens only when the result becomes greater than the limit then can hold on to for assigned case the limit of a maximum value is 127 while a unassigned case is 255. Whenever it passes through the threshold , it gets an overflown error. Creating a 9th bit that has no place in a 8bit system and so it gets carried over since it simply cannot fit in.

5. What digits are used in the hexadecimal system?

0 , 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , A , B , C , D , E , F

6. How do you convert 0101 1111 to hexadecimal?

(01011111)2 = (5F)16

*	0101 1111

	8421 8421

	0401 8421

	4+1=5 , 8+4+2+1=15 

7. In which other numeral systems can an 8-bit value be written without performing calculations?

Any base with the power 2 , binary , base 4 , octal base and the hexadecimal base. Each base has an exact group of bits.

