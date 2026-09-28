1\. Array

int arr\[2]{};

arr\[0] = 1;

arr\[1] = 2;



std::cout << arr\[0];

std::cout << std::endl;



std::cout << arr\[1];

std::cout << std::endl;



prints 1, then 2 , arr\[0] and arr\[1] work like two separate variables.



What does int arr\[2]{} mean?



arr\[2]{} means that is two indexes , of each are 0 and 1 , but they hold no value.



What is an array?



an array is like a row that holds different indexes (by default starting from 0) and each index has its own value



2\. Array initialization

int arr1\[2]{ 21, 32 };



std::cout << arr1\[0];

std::cout << std::endl;



std::cout << arr1\[1];

std::cout << std::endl;



prints 21, then 32 , elements are initialized in index order at creation



What does this syntax mean?



it means that the indexes of the array are assigned to hold their own values. e.g. index 0 has the value of 21



3\. Array with an unspecified length

int arr1\[3]{ 1, 2, 3 };

int arr2\[]{ 1, 2, 3, 4 };



std::cout << sizeof(arr1);

std::cout << std::endl;



std::cout << sizeof(arr2);

std::cout << std::endl;



prints 12 and then 16



&#x20;What is sizeof?



sizeof gives the total bytes: 3 × 4 and 4 × 4



&#x20;What does \[] mean?



is a syntax that can hold a value ( or not ) that determines the how many indexes are inside one array







4\. Size of an array of size\_t

size\_t arr\[3]{ 1, 2, 3 };



std::cout << sizeof(arr);

std::cout << std::endl;



prints 24 , sizeof measures bytes, and 3 × 8 (size\_t on 64-bit) = 24.



5\. Computing the number of elements from sizeof

int arr\[]{ 1, 2, 3, 4 };



std::cout << sizeof(arr);

std::cout << std::endl;



std::cout << sizeof(arr\[0]);

std::cout << std::endl;



std::cout << sizeof(arr) / sizeof(arr\[0]);

std::cout << std::endl;



prints 16, 4, 4 , total bytes divided by the size of one element gives the element count , this only works while arr is still an array, not a pointer.



6\. Reading by index

int arr\[3]{ 1, 2, 3 };

size\_t index { 2 };

int it { arr\[index] };

std::cout << it;

std::cout << std::endl;



prints 3 , arr\[index] with index = 2 reads the third element.





7\. Writing by index

int arr\[3]{};

size\_t index { 2 };

arr\[index] = 5;

std::cout << arr\[2];

std::cout << std::endl;



prints 5,  arr\[index] = 5 writes into arr\[2].





8\. An expression as an index

int arr\[3]{};

size\_t index { 1 };

arr\[index + 1] = 5;

std::cout << arr\[2];

std::cout << std::endl;



prints 5 , index + 1 is 2, so arr\[2] gets 5.





9\. Copying an array element into a variable

int arr\[3]{ 0, 2, 1 };

size\_t index { 2 };

int it { arr\[index] };

arr\[index] = 5;

std::cout << it;

std::cout << std::endl;



prints 1 , it is an int, so it holds a copy, changing arr\[2] afterward doesn't affect it.





10\. A pointer as the element type

int a = 1;

int b = 2;

int\* arr\[]{ \&a, \&b };

\*arr\[0] = 3;

\*arr\[1] = \*arr\[0];



std::cout << arr\[0] << std::endl;

std::cout << arr\[1] << std::endl;



std::cout << \*arr\[0] << std::endl;

std::cout << \*arr\[1] << std::endl;



arr\[0] has the address of a

arr\[1] has the address of b

\*arr\[0] is 3 and \*arr\[1] is also 3



11\. Using an array as a pointer

int arr\[2]{};

int\* p = arr;

\*arr = 1;



std::cout << \*p;

std::cout << std::endl;



std::cout << arr\[0];

std::cout << std::endl;



std::cout << arr\[1];

std::cout << std::endl;



prints 1, 1, 0 , arr decays to a pointer to its first element, so p, \*arr, and arr\[0] all refer to the same element , arr\[1] stays 0.





12\. Printing an array

int arr\[3]{ 1, 2, 3 };

std::cout << arr;

std::cout << std::endl;



prints an address, not the contents , arr becomes into int\* (pointing to arr\[0]), and cout prints pointer values as addresses , the exact value differs each run.





