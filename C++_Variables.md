1.

int a = 5;
std::cout << a << std::endl;

What type is a?

integer

2.

int a;
std::cout << a << std::endl;

What happens if you read from variable a?

It will display the value 0 , because it hasn't been assigned to a value

3.

int a = 5;
int a = 6;
std::cout << a << std::endl;

You cannot define 2 variable with the same name , either the first or second a needs to be deleted in order for the one of the a to be displayed

4.

int a = 5;
int b = 6;
a = b;
b = 7;
std::cout << a << std::endl;

on the console a will display 6 instead of 5 because it has been defined by b , b however is not displayed

What counts as an expression here?

a = b;
b = 7;

What is the type of expression b?

read the value of the variable b

5.

int a = 5;
int b = a + 6;
a = 7;
std::cout << b << std::endl;

b has defined having the value of 11 , a being assigned the value of 7 doesn't change the value of b , therefore b will be displayed of having a value of 11

6.

int a = "abc";

it will display an error , because a is an integer and cannot be assigned a string value.

7.

int a{5};

it is the same as int a = 5;

8.

std::cout << sizeof(int) << std::endl;
std::cout << sizeof(uint8_t) << std::endl;
int a;
std::cout << sizeof(a) << std::endl;

sizeof(int) will display 4 bytes
sizeof(uint8_t) will display 1 bytes
sizeof(a) will display 4 bytes

9.

auto a = 5;

a will be treated as integer

10.

auto a;
a = 5;

it will not work since , auto works only when the value is also assigned.

11.

int a{ 5 };
auto b{ a + 5 };

b will be treated as a integer since a value has been assigned.

12.

auto a{ 5 };

it is the same as auto a = 5;

13.

auto a{ static_cast<uint8_t>(5) };

static cast basically tells to 5 to be converted into uint8_t (0,255) which it can without any problem , it will convert to 5 and the auto will interfere and define a as integer.

14.

uint8_t a{ 5 };
int b{ static_cast<int>(a) };

a will be defined as an unsigned 8bit of 5 and b will be defined as a that has been converted into integer but uint_8 falls into the range of values of the integer so it will convert without any problem , b will be displayed as 5.

15.

#include <cstdint>
#include <iostream>

int main()
{
    uint32_t a{ 256 };
    uint8_t b{ static_cast<uint8_t>(a) };
    uint32_t c{ b };
    std::cout << c << std::endl;
}

a has the value of 256 , b tries to convert a into uint8_t but cannot because the limit is from 0 to 255 , therefore it will be an overflow and b will have the value 0
c will take that value of b which is 0 and it will display 0

16.

#include <cstdint>
#include <iostream>

int main()
{
    uint8_t a{ 0 };
    uint8_t b{ ~a };
    int32_t c{ b };
    std::cout << c;
}

a will have the value of 0 , b will be signed a but as a temporary uint32_t that it will also be flipped due to the ~ operator. Afterwards c gets the value of b which can hold without any problem a value of 255 and it will be displayed 255

17.

#include <cstdint>
#include <iostream>

int main()
{
    uint8_t a{ 255 };
    int8_t b{ static_cast<int8_t>(a) };
    int32_t c{ b };
    std::cout << c;
}

a will have the value of 255 , b will get the an overflow problem since it cannot hold the value of 255 and so it will have -1 , c will get the value of b since it can hold it without any problem. Which is still -1 

18.

int a { 1 };
int b { 2 };
a = b;
b = a;
std::cout << a << std::endl;
std::cout << b << std::endl;

a will have the value of b which is 2 , however a's value which was 1 has been lost , and so b will also have the value of 2, it will display that a has the value of 2 and b has the value of 2.