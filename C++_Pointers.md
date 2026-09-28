1. Variable address
int a{ 5 };
int* b{ &a }; // int* b = &a;
std::cout << b;
std::cout << std::endl;

a has the value of 5 , b is a pointer that has the address of a , respectively the value of a ( 5 )

What is the type of variable b?

integer

What is the type of expression &a?

integer address
 
2. Address of an uninitialized variable
Is something like this allowed?

int a;
int* b{ &a };
std::cout << b;
std::cout << std::endl;

yes it's allowed , taking &a doesn't read the value, so it prints an ordinary address

3. Dereference operator (writing)
int a { 1 };
int* b{ &a };
*b = 2;
std::cout << a;
std::cout << std::endl;

it prints 2 ,  *b = 2 writes through the address in b, which is a.

4. A number as an address
Is something like this allowed?

int* b{ 32 };
std::cout << *b;
std::cout << std::endl;

it will produce a compile error ,  an integer can't be converted to a pointer , addresses must come from & or another pointer.

5. Dereference operator (reading)
int a{ 5 };
int b{ *(&a) };
std::cout << b;
std::cout << std::endl;

it prints 5 , &a gives the address, * goes back to a, and a gives 5.

6. Printing a complex expression
int a{ 5 };
int* b{ &a };
std::cout << (*b) + 7;
std::cout << std::endl;

it prints 12 , *b is a (5), and 5 + 7 = 12.

7. Pointer to a larger data type
uint8_t a{ 5 };
int* b{ &a };

it will produce an error , &a is uint8_t*, which can't convert to int*.

8. Pointer to a smaller data type
int a = 5;
uint8_t* b = &a;

again an error ,  &a is int*, which can't convert to uint8_t*.

9. Dependence of the address on the value
Will b and c contain the same address?

int a = 5;
int* b = &a;
a = 6;
int* c = &a;

yes, same address , assigning a = 6 changes the contents of the address, not its location.

10. It is the same memory!
int a = 5;
int* ap = &a;

*ap = 6;
std::cout << a;
std::cout << std::endl;

a = 7;
std::cout << *ap;
std::cout << std::endl;

it will print 6 and then 7 , ap and a refer to the same memory.
		
11. Assigning a value through a pointer
Is something like this allowed?

int a;
int* b = &a;
*b = 5;
std::cout << a;
std::cout << std::endl;

yes it's allowed , writing to an uninitialized variable is fine, so it prints 5... just don't read it before you write it.

12. Reassigning a pointer
int a = 5;

int* p = &a;
*p = 6;

int b = 7;

p = &b;
*p = 8;

std::cout << a;
std::cout << std::endl;

std::cout << b;
std::cout << std::endl;

prints 6, then 8 , a stays 6 because p was redirected to b, and *p = 8 then wrote into b.

13. Double pointer
int a = 5;
int b = 6;
int* p = &a;
int** pp = &p;
**pp = 7;

*pp = &b;
**pp = 8;

std::cout << a;
std::cout << std::endl;

std::cout << b;
std::cout << std::endl;

prints 7, then 8 , **pp = 7 writes to a , *pp = &b redirects p to b, so **pp = 8 writes to b.

14. Pointer sizes
int a = 7;
int* pa = &a;
void* voidp = pa;

uint8_t c = 9;
uint8_t* pc = &c;

std::cout << sizeof(pa);
std::cout << std::endl;

std::cout << sizeof(voidp);
std::cout << std::endl;

std::cout << sizeof(pc);
std::cout << std::endl;

prints 8, 8, 8 on a 64-bit system , all pointers hold an address, so they have the same size regardless of the type they point to.

15. Pointer and variable sizes
int a = 7;
int ap = &a;

std::cout << sizeof(a);
std::cout << std::endl;

std::cout << sizeof(ap);
std::cout << std::endl;

std::cout << sizeof(*ap);
std::cout << std::endl;

the code as written has a typo: int ap = &a; is a compile error , it should be int* ap = &a; with that fix, it prints 4, 8, 4.

16. Pointer to itself
void* p = nullptr;
p = static_cast<void*>(&p);

std::cout << p;
std::cout << std::endl;

std::cout << &p;
std::cout << std::endl;

prints the same address twice , p stores its own address, so p == &p.

17. Copying a variable and a pointer with similar names
int x{ 0 };
int* px{ &x };
int y{ x };
int* py{ px };

*px = 1;

std::cout << x << std::endl;
std::cout << y << std::endl;
std::cout << *px << std::endl;
std::cout << *py << std::endl;

x >>> 1, because *px = 1 writes to x , y >>> 0, because y is a separate copy of the value.
*px >>> 1, because it follows the pointer to x , *py >>> 1, because py is a copy of px and holds the same address, so it also points to x.
