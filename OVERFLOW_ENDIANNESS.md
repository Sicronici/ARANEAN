<overflow errors>

an overflow error occurs when a result has a magnitude too big to be represented with the number of bits available

e.g. when two numbers with the same sign are added together the result may require too many bits.


			-128 to + 127 <<< LIMIT

	(1111)
	0111 1001	121
+	0110 1010	106

	11100011	-129 <<< ERROR


e.g floating point with a bit 5 mantissa and a 4 bit exponent

largest positive number is 0.1111 * 2^0111 = 120
smallest negative number is 1.0000 * 2^0111 = -128

Results > 120 or results < -128 would overflow

Overflow errors can be handled through interrupts , clamping or treating results as infinity.

<underflow errors>

An underflow error occurs when a result has a magnitude too small to be represented with the number of bits available

This usually happens when you get too close to 0

e.g. in floating point with a 5 bit mantissa and a 4 bit exponent

smallest positive number is 0.1000 * 2^1000 = 0.0019531

largest negative number is 1.0111*2^1000 = -0.0021973

-0.0021973 < underflow < 0.0019531

<Endianness>

hexadecimal number 0x00c0ffee - 32 bit number (00000000110100001111111111101110)

4 different memory locations >>>

0 (00) 1(c0) 2(ff) 3(ee) - Big Endian

Big Endian was usually used , IBMs machines used big endians

other 3 different memory locations >>>

0 (ee) 1(ff) 2(c0) 3(00) - Little Endian

Little Endians now is mostly used due to Intel chips.

All translations between machines over the network whenever they have to agree on what endian is used. Happens in the software , for example it will take your TCP number and is run in a function of a host ordering whenever you log into a web.

Whenever translations happen , shuffling around the bytes slow down somewhat. But they are not visible since it doesn't happen that often.


<negative numbers>

-128 (0) 64 (0) 32 (1) 16(0) 8(0) 4(1) 2(1) 1(0)

32 + 4 + 2 = 38

-128 (1) 64 (0) 32 (0) 16(1) 8(0) 4(0) 2(1) 1(1)

-128 + 16 + 2 + 1 = -109

How to convert a negative denary into a negative binary?

Convert your negative denary into it's positive binary equivalent

-66 to positive 66 and viceversa
-66	(0100010)
 66	(1011110)

-128 + 32 + 16 + 8 + 4 + 2 = -66 