# Join me on my journey to learn C++

## Purpose

This repository is dedicated to learning the C++ language via project-based learning with my background of C#. This repository contains my practice programs I have made along my journey to learning C++. I aim to learn the ins-and-outs of C++, especially the fundamentals. 😁😆😺

## Programs

| Folder Name      | Brief Description       |
| ---------------- | ----------------------- |
| bank_prog        | Banking Program         |
| bubble_sort      | Bubble Sort Algorithm   |
| calc_prog        | Calculator Program      |
| credit_card_vali | Luhn Algorithm          |
| hype_calc        | Hypotenuse Calculator   |
| num_guess        | Number Guessing Game    |
| quiz_game        | Quiz Game               |
| ran_event        | Random Event Generator  |
| rng              | Random Number Generator |
| temp_conv        | Temperature Converter   |
| tictactoe        | Tic-Tac-Toe Game        |

## Technologies Used

- Visual Studio Code
- C/C++ Extension
- Code Runner

## What I have learnt thus far!

#### My Notes: `https://fluorescent-frame-930.notion.site/C-175c16e1f75d4171aaf33ff2a933d18f?pvs=25`

### Prerequisites

`C#`

### Important Notes

```cpp
// iostream - standard input-output stream
// iostream declares objects that control reading from and writing to standard stream
#include <iostream>

// return 0 - program executed successfully
// return 1 - program not executed successfully
int main() {
    return 0;
}
```

### Printing

```cpp
int main() {
	std::cout << "Hello, World!";
	std::cout << "meow";
	return 0;
}

/*Output:
Hello, World!meow*/
```

### Next Line - endl & '\n'

```cpp
// endl - endline forces a flush
// '\n' - next line does not force buffer flush frequently, better performance wise
int main() {
    std::cout << "Hello, World!" << std::endl;
    std::cout << "Hello, World!" << '\n';
    std::cout << "Hello, World!";
    return 0;
}

/*Output:
Hello, World!
Hello, World!
Hello, World!*/
```

### Declaration & Assignment - Same as C#

```cpp
#include <iostream>

int main() {
    int x; //Declaration
    x = 5; //Assignment
    int y = 6; //Declaration + Assignment
    int sum = x + y;

    std::cout << "x-value: " << x << '\n';
    std::cout << "y-value: " << y << '\n';
    std::cout << "sum: " << sum << '\n';

    return 0;
}

/*Output:
x-value: 5
y-value: 6
sum: 11*/
```

### Data Types - Similar to C# except std::string

```cpp
#include <iostream>

int main() {
    // double
    double a = 2.232;
    std::cout << a << '\n';

    // bool
    bool b = true; //Outputs true as 1
    bool c = false; //Outputs false as 0
    std::cout << b << '\n';
    std::cout << c << '\n';

    // char
    char d = 'A';
    char e = 'AB'; //if there is multiple characters in char, it will take the last character
    std::cout << d << '\n';
    std::cout << e << '\n';

    // int
    int x = 12;
    std::cout << x << '\n';

    // string
    std::string name = "john";
    std::cout << "Hello " << name << "!\n";

    // const
    const double pi = 3.14;
    pi = 3; // will return an error
    double radius = 10;
    double cir = 2 * pi * radius;
    std:cout << cir << "cm";

    return 0;
}

/*Output:
2.232
1
0
A
B
12
Hello john!
62.8cm*/
```

### User Input & Output - cout & cin

```cpp
// cout << - Insertion operator
// cin >> - Extraction operator

Example 1: std::cin to get input
#include <iostream>

int main() {
    std::string name;
    std::cout << "Enter your name: ";
    std::cin >> name;

    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
/*Output:
Enter your name: Johnny Cash
Hello, Johnny!*/

Example 2: std::getline to include spaces
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cout << "Enter your name: ";
    std::getline(std::cin, name);

    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
/*Output:
Enter your name: Johnny Cash
Hello, Johnny Cash!*/

Example 3: std::ws to exclude any whitespaces and new lines from getline
Problem: Check output
#include <iostream>
#include <string>

int main() {
    std::string name;
    int age;

    std::cout << "Enter your age: ";
    std::cin >> age;

    std::cout << "Enter your name: ";
    std::getline(std::cin, name);

    std::cout << "Hello, " << name << "!" << std::endl << "You are " << age << " years old." << std::endl;

    return 0;
}
/*Output:
Enter your age: 5
Enter your name: Hello, !
You are 5 years old.*/
Solution: std::ws
#include <iostream>
#include <string>

int main() {
    std::string name;
    int age;

    std::cout << "Enter your age: ";
    std::cin >> age;

    std::cout << "Enter your name: ";
    std::getline(std::cin >> std::ws, name);

    std::cout << "Hello, " << name << "!" << std::endl << "You are " << age << " years old." << std::endl;

    return 0;
}
/*Output:
Enter your age: 5
Enter your name: John China
Hello, John China!
You are 5 years old.*/
```

### Namespaces

```cpp
Example 1:
#include <iostream>

int main() {
    int x = 5;
    int x = 6; // Error: redeclaration of 'int x'

    return 0;
}
/*Output:
Error: redeclaration of 'int x'*/

Example 2: using variables in other namespaces
#include <iostream>

namespace first{
    int x = 1;
}

namespace second{
    int x = 2;
}
int main() {
    int x = 0;
    std::cout << "Main namespace x: " << x << std::endl;
    std::cout << "First namespace x: " << first::x << std::endl;
    std::cout << "Second namespace x: " << second::x << std::endl;

    return 0;
}
/*Output:
Main namespace x: 0
First namespace x: 1
Second namespace x: 2*/

Example 3: using namespaces
#include <iostream>

namespace first{
	int x = 1;
}

int main() {
    using namespace first; //References everything from namespace 'first'
    std::cout << x << std::endl;

    return 0;
}
/*Output:
1*/

Example 4: using namespace std
// std - saves time by removing the need of writing std::
// High likelihood that variables have naming conflicts such as data
#include <iostream>

int main() {
    using namespace std;
    int x = 0;
    cout << x << endl;

    return 0;
}
/*Output:
0*/

Example 5: using std::cout; using std::endl;
// using std::cout - saves time by removing the need of writing std::cout
// using std::endl - saves time by removing the need of writing std::endl
#include <iostream>

int main() {
    using std::cout;
    using std::endl;

    int x = 0;
    cout << x << endl;

    return 0;
}
/*Output:
0*/
```

### Typedef & Type Aliases

```cpp
// typedef - helps readability by assigning a data type to a typedef variable
// typedef - naming convention ends with _t
// using - can use 'using' instead of 'typedef': more suitable for templates
#include <iostream>

typedef std::string text_t; // Assign text_t to be a string data type
using number_t = int; // Assign number_t to be a int data type

int main() {
    text_t name = "Johnny";
    std::cout << "Hello, " << name << "!" << std::endl;

    number_t age = 25;
    std::cout << "You are " << age << " years old." << std::endl;

    return 0;
}

/*Output:
Hello, Johnny!
You are 25 years old.*/
```

### Math Operators - Same as C#, has order of precedence

```cpp
// Operators are similar to C#
#include <iostream>
#include <cmath>

int main() {
    double students = 20;

    // Addition
    students = students + 1;
    students+=1;
    students++;

    // Subtraction
    students = students - 1;
    students-=1;
    students--;

    // Multiplication
    students = students * 2;
    students*=2;

    // Division
    students = students / 2;
    students/=2;

    // Modulus
    int apples = 20;
    int remainder = apples % 3; // Both must be the same data type

    // Math functions
    // Max: Get higher of the two numbers
    int max = std::max(5, 10);
    // Min: Get lower of the two numbers
    int min = std::min(5, 10);

    //CMath functions - Must #include <cmath>
    // Power: a^b
    double power = pow(2, 3);
    // Sqrt: Square root
    double squareRoot = sqrt(64);
    // Abs: Absolute value, removes negative sign
    double absolute = abs(-4.7);
    // Round: Rounds to nearest whole number
    double rounded = round(4.7);
    // Floor: Rounds down to nearest whole number
    double floored = floor(4.7);
    // Ceil: Rounds up to nearest whole number
    double ceiling = ceil(4.7);

    std::cout << "Students: " << students << '\n';
    std::cout << "Remainder: " << remainder << '\n';
    std::cout << "Max: " << max << '\n';
    std::cout << "Min: " << min << '\n';
    std::cout << "Power: " << power << '\n';
    std::cout << "Sqrt: " << squareRoot << '\n';
    std::cout << "Abs: " << absolute << '\n';
    std::cout << "Round: " << rounded << '\n';
    std::cout << "Floor: " << floored << '\n';
    std::cout << "Ceil: " << ceiling << '\n';

    return 0;
}

/*Output:
Students: 20
Remainder: 2
Max: 10
Min: 5
Power: 8
Sqrt: 8
Abs: 4
Round: 5
Floor: 4
Ceil: 5*/
```

### Type Conversion - Implicit & Explicit, Same as C#

```cpp
//Implicit - Automatic
//Explicit - Precede value with new data type

Example 1: Implicit
#include <iostream>

int main() {
    int x = 6.9; // Assigning double to int
    char y = 100;  // Assigning int to char - converts using ASCII

    std::cout << x;
    std::cout << y;

    return 0;
}
/*Output:
6d*/

Example 2: Explicit
#include <iostream>

int main() {
    double x = (int)6.9; // Assigning double to int

    std::cout << x;
    std::cout << (char)100; // Assigning int to a char - converts using ASCII

    return 0;
}
/*Output:
6d*/
```

### If, else, else if statement - Same as C#

```cpp
// Order matters
#include <iostream>

int main() {
    int age;
    std::cout << "Enter your age: ";
    std::cin >> age;

    if (age >= 18) {
        std::cout << "You are old enough to enter the club." << std::endl;
    } else if (age < 1) {
        std::cout << "Invalid input." << std::endl;
    }
    else {
        std::cout << "You are not old enough to enter the club." << std::endl;
    }

    return 0;
}
```

### Switch statements - Same as C#, more efficient and better readability than if else

```cpp
#include <iostream>

int main() {
    int month;
    std::cout << "Enter the month (1-12): ";
    std::cin >> month;

    switch (month) {
        case 1:
            std::cout << "January";
            break;
        case 2:
            std::cout << "February";
            break;
        case 3:
            std::cout << "March";
            break;
        case 4:
            std::cout << "April";
            break;
        case 5:
            std::cout << "May";
            break;
        case 6:
            std::cout << "June";
            break;
        case 7:
            std::cout << "July";
            break;
        case 8:
            std::cout << "August";
            break;
        case 9:
            std::cout << "September";
            break;
        case 10:
            std::cout << "October";
            break;
        case 11:
            std::cout << "November";
            break;
        case 12:
            std::cout << "December";
            break;
        default:
            std::cout << "Invalid input";
            break;
    }

    return 0;
}
```

### Ternary Operators - Same as C#

```cpp
// Alternative to if else, switch statements
#include <iostream>

int main() {
    int grade;
    bool result;

    std::cout << "Enter your grade: ";
    std::cin >> grade;

    result = (grade >= 50) ? true : false; //Ternary

    if (result == true) {
        std::cout << "You pass!" << '\n';
    }
    else {
        std::cout << "You failed!" << '\n';
    }

    return 0;
}
```

### Logical Operators - Same as C#

```cpp
// && - and
// || - or
// ! - reverse
#include <iostream>

int main() {
    int temp;
    bool sunny;

    std::cout << "Enter temperature: ";
    std::cin >> temp;

    if (temp < 0 || temp >= 30) {
        std::cout << "Bad temperature" << '\n';
    }
    else {
        std::cout << "Good temperature" << '\n';
    }

    std::cout << "Enter if sunny (0/1): ";
    std::cin >> sunny;

    if (!sunny) {
        std::cout << "Cloudy outside" << '\n';
    }
    else {
        std::cout << "Sunny outside" << '\n';
    }

    if (sunny && temp <= 25) {
        std::cout << "Amazing weather today" << '\n';
    }
    else {
        std::cout << "Bad weather today" << '\n';
    }

    return 0;
}
```

### String Manipulation

```cpp
// .empty() - checks if string is empty, returns boolean
// .length() - returns the length of the string
// .clear() - clears the string
// .append("string") - appends a string to another string
// .at(index) - returns the character at a specific index
// .insert(index, "string") - inserts a string at a specific index
// .find("string") - finds a string within a string, returns index + 1
// .erase(index, length) - erases a string from a specific index to a specific length

#include <iostream>
#include <string>

int main() {
    std::string name;

    std::cout << "Enter your name: ";
    std::getline(std::cin >> std::ws, name);

    // .empty()
    if (name.empty()) {
        std::cout << "Invalid input" << '\n';
    }

    // .length()
    if (name.length() > 4) {
        std::cout << "Hello, " << name << "!" << '\n';
    }
    else {
        std::cout << "Your name needs to be over 5 characters" << '\n';
    }

    // .clear()
    name.clear();
    if (name == "") {
        std::cout << "Name has been cleared" << '\n';
    }

    // .append()
    name.append("@gmail.com");
    std::cout << "Appended '@gmail.com': " << name << '\n';

    // .at()
    std::cout << name.at(1) << '\n';

    // .insert(index, string)
    std::cout << name.insert(0, "hello ") << '\n';

    // .find(string)
    std::cout << name.find("gmail") << '\n';

    // .erase(index, length)
    std::cout << name.erase(0, 6) << '\n';

    return 0;
}
/*Output:
Enter your name: johnny cash
Hello, johnny cash!
Name has been cleared
Appended '@gmail.com': @gmail.com
g
hello @gmail.com
7
@gmail.com*/
```

### While Loops - Same as C#

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name;

    while (name.empty()) {
        std::cout << "Enter your name: ";
        std::getline(std::cin, name);
    }

    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
```

### Do While Loop - Same as C#

```cpp
#include <iostream>

int main() {
    int number;
    do {
        std::cout << "Enter a postive number: ";
        std::cin >> number;
    } while (number < 0);

    std::cout << "The number is: " << number << "!\n";

    return 0;
}
```

### For Loop - Same as C#

```cpp
#include <iostream>

int main() {

    for (int i = 0; i < 3; i++) {
        std::cout << "Hello, World!\n";
    }

    return 0;
}
/*Output:
Hello, World!
Hello, World!
Hello, World!*/
```

### Break & Continue - Same as C#

```cpp
// break - break out of loop
// continue - skip to next iteration of loop

// continue
#include <iostream>

int main() {

    for (int i = 0; i < 3; i++) {
        if (i == 1) {
            break;
        }
        std::cout << "Hello, World!\n";
    }

    return 0;
}
/*Output:
Hello, World!*/

// break
#include <iostream>

int main() {

    for (int i = 0; i < 3; i++) {
        if (i == 1) {
            continue;
        }
        std::cout << "Hello, World!\n";
    }

    return 0;
}
/*Output:
Hello, World!
Hello, World!*/
```

### Random Number Generator (RNG) - srand

```cpp
int main() {
    // Pseudo-random number generator (Not totally random but close)
    srand(time(NULL));
    int num = rand(); // Goes up to 32767
    std::cout << num << std::endl;

    // Simulate a 6 sided die
    int num1 = (rand() % 6) + 1; // 0 to 5 + 1 = 1 to 6
    std::cout << num1 << std::endl;

    return 0;
}
/*Output:
21229
6*/
```

### Functions & Return - Same as C#

```cpp
Function
#include <iostream>

// Declare the function to be used in the main function
void print();
void greet(std::string name);

int main() {
    print();
    greet("John");

    return 0;
}

// Function without argument
void print() {
    std::cout << "Hello, World!\n";
}

// Function with argument
void greet(std::string name) {
    std::cout << "Hello, " << name << "!\n";
}
/*Output:
Hello, World!
Hello, John!*/

Return
#include <iostream>

// Declare the function to be used in the main function
double square(double x);

int main() {
    double value;
    value = square(1.5);
    std::cout << "Squared value: " << value << "!\n";

    return 0;
}

double square(double x) {
    return x * x;
}
/*Output:
Squared value: 2.25!*/
```

### Overloaded Functions - Same function names with different arguments

```cpp
#include <iostream>

void bakePizza();
void bakePizza(std::string topping);

int main() {
    bakePizza();
    bakePizza("pepperoni");

    return 0;
}

void bakePizza() {
    std::cout << "Here is your pizza!\n";
}

void bakePizza(std::string topping) {
    std::cout << "Here is your " << topping << " pizza!\n";
}
/*Output:
Here is your pizza!
Here is your pepperoni pizza!*/
```

### Memory Management

```cpp
Memory Management

// Reset error flags
std::cin.clear()

// Clear input buffer
fflush(stdin)
```

### Array - Similar to C#

```cpp
#include <iostream>

int main() {
    using std::cout;

    std::string car[] = {"BMW", "Audi", "Mercedes", "Toyota", "Honda"};

    for (int i = 0; i < 5; i++) {
        cout << car[i] << '\n';
    }

    // Reassigning the value of index
    cout << "Value of index 0 before reassigning: " << car[0] << '\n';
    car[0] = "Ford";
    cout << "Value of index 0 after reassigning: " << car[0] << '\n';

    // Setting array size
    int arr[5] = {1, 2, 3, 4, 5};
    cout << "Size of array: " << sizeof(arr) / sizeof(arr[0]) << '\n';

    return 0;
}
/*Output:
BMW
Audi
Mercedes
Toyota
Honda
Value of index 0 before reassigning: BMW
Value of index 0 after reassigning: Ford
Size of array: 5*/
```

### Sizeof() & Size() - size in byts of a variable, data type, class, object etc

```cpp
// sizeof(variable) - returns the size of the variable in bytes
// sizeof(array) / sizeof(array[0]) - returns the number of elements in the array
// string.size() - returns the number of characters in the string
#include <iostream>

int main() {
    using std::cout;

    // Get number of bytes
    double gpa = 4.0;
    cout << "Size of double: " << sizeof(gpa) << " bytes\n";

    // Get number of elements in array
    int arr[5] = {1, 2, 3, 4, 5};
    cout << "Size of array: " << sizeof(arr) / sizeof(arr[0]) << '\n';

    // Get number of elements in string
    std::string name = "Johnny Bravo";
    cout << "Size of string: " << name.size() << '\n';

    return 0;
}
/*Output:
Size of double: 8 bytes
Size of array: 5
Size of string: 12*/
```

### For each

```cpp
// for (datatype element: variable)
#include <iostream>

int main() {
    using std::cout;
    using std::string;

    string car[] = {"BMW", "Audi", "Mercedes", "Toyota", "Honda"};

    for (string x : car) {
        cout << x << "\n";
    }

    return 0;
}
```

### Fill function - fills a range of elements with a specific value

```cpp
// fill(begin, end, value)
#include <iostream>

int main() {
    using std::cout;
    using std::string;
    using std::cin;

    const int size = 10; // needs to be a constant to work with fill
    string food[size];
    fill(food, food + size/2, "Pizza"); // Fill first 5 with Pizza
    fill(food + size/2, food + size, "Fries");  // Fill second 5 with Fries

    cout << "Food array: \n";
    for (int i = 0; i < 10; i++) {
        cout << food[i] << "\n";
    }

    return 0;
}
/*Output:
Food array:
Pizza
Pizza
Pizza
Pizza
Pizza
Fries
Fries
Fries
Fries
Fries*/
```

### 2D Arrays

```cpp
// int arr[2][3] - 2d array -> 2 rows 3 columns, setting column is required
#include <iostream>

int main() {
    using std::cout;
    using std::cin;
    using std::string;

    // Creating 2d array
    string cars[2][3] = {{"Mustang", "Corvette", "Porsche"},
                        {"BMW", "Toyota", "Honda"}};

    // Displaying 2d array
    for (int i = 0; i < 2; i++) {
        if (i == 1) {
            cout << "\n";
        }
        for (int j = 0; j < 3; j++) {
            cout << cars[i][j] << ' ';
        }
    }

    // Getting the row and column size of 2d array
    int rows = sizeof(cars) / sizeof(cars[0]);
    int cols = sizeof(cars[0]) / sizeof(cars[0][0]);
    cout << "\nRows: " << rows << "\nColumns: " << cols;

    return 0;
}
/*Output:
Mustang Corvette Porsche
BMW Toyota Honda
Rows: 2
Columns: 3*/
```

### Memory Addresses/Reference

```cpp
// Memory Address/Reference - location in memory where data is stored, accessible with &
#include <iostream>

int main() {
    using std::cout;
    using std::cin;
    using std::string;

    string name = "John";
    int age = 21;
    bool student = true;
    double gpa = 3.5;
    string address = "123 Main St";

    cout << "String Name Memory Address: " << &name << "\n"; // 0x61a2dff8b0, 419344414896
    cout << "Int Age Memory Address: " << &age << "\n"; // 0x61a2dff8ac, 419344414892
    cout << "Bool Student Memory Address: " << &student << "\n"; // 0x61a2dff8ab, 419344414891
    cout << "Double GPA Memory Address: " << &gpa << "\n"; // 0x61a2dff8a0, 419344414883
    cout << "String Address Memory Address: " << &address << "\n"; // 0x61a2dff880, 419344414851

    cout << "\nSize of int: " << sizeof(int) << " bytes\n";
    cout << "Size of bool: " << sizeof(bool) << " bytes\n";
    cout << "Size of double: " << sizeof(double) << " bytes\n";
    cout << "Size of string: " << sizeof(std::string) << " bytes\n";

    // Difference in memory address between name and age converted to decimal = 4.
    // Difference in memory address between age and student converted to decimal = 1.

    // Between name and age = 4 as age is a int and takes 4 bytes.
    // Between age and student = 1 as student is a bool and takes 1 byte.

    return 0;
}
/*Sample Output:
String Name Memory Address: 0x68fb7ffb00
Int Age Memory Address: 0x68fb7ffafc
Bool Student Memory Address: 0x68fb7ffafb
Double GPA Memory Address: 0x68fb7ffaf0
String Address Memory Address: 0x68fb7ffad0

Size of int: 4 bytes
Size of bool: 1 bytes
Size of double: 8 bytes
Size of string: 32 bytes*/
```

### Pass by Value / Pass by Reference

```cpp
// Pass by Value - uses value (values all have different memory addresses)
#include <iostream>
using std::cout;
using std::cin;
using std::string;

void swapValue(string x, string y);

int main() {


    string x = "Kool-Aid";
    string y = "Jammers";

    swapValue(x, y);

    cout << "X: " << x << "\n";
    cout << "Y: " << y << "\n";

    return 0;
}

void swapValue(string x, string y) {
    string temp = x;
    x = y;
    y = temp;
}
/*Output:
X: Kool-Aid
Y: Jammers*/

// Pass by Reference - uses memory address (use as often as possible unless there is a reason to pass by value)
#include <iostream>
using std::cout;
using std::cin;
using std::string;

void swapReference(string &x, string &y);

int main() {


    string x = "Kool-Aid";
    string y = "Jammers";

    swapReference(x, y);

    cout << "X: " << x << "\n";
    cout << "Y: " << y << "\n";

    return 0;
}

void swapReference(string &x, string &y) {
    string temp = x;
    x = y;
    y = temp;
}
/*Output:
X: Jammers
Y: Kool-Aid*/

// Const Pass by Reference - Read only
#include <iostream>
using std::cout;
using std::cin;
using std::string;

void print(const string &name, const int &age);

int main() {

    print("John", 21);

    return 0;
}

void print(const string &name, const int &age) {
    // name = "Jane"; // Error: const
    // int = 2; // Error: const
    cout << name << " is " << age << " years old.\n";
}
/*Output:
John is 21 years old.*/
```

### Pointers - variable that stores a memory address of another variable

```cpp
// & - address of operator
// * - dereference operator
#include <iostream>
using std::cout;
using std::cin;
using std::string;

int main() {

    string name = "John";
    string *pname = &name;
    cout << "Name: " << *pname << "\n";

    // Arrays
    int arr[5] = {1, 2, 3, 4, 5};
    int *parr = arr;
    // int *parr = &arr; would give an error as arrays are already memory addresses
    cout << "First element: " << *parr << "\n";
    cout << "Second element: " << *(parr + 1) << "\n";

    return 0;
}
/*Output:
Name: John
First element: 1
Second element: 2*/
```

### Null Pointers

```cpp
// nullptr = keyword representing a null pointer
// when using pointers, check if the pointer is null before dereferencing it
// deferencing null pointers can cause runtime errors
#include <iostream>
using std::cout;
using std::cin;
using std::string;

int main() {

    int *pointer = nullptr;
    int x = 123;
    pointer = &x; // pointer now holds the address of x, making it not a null pointer

    if (pointer != nullptr) {
        cout << "The value of x is: " << *pointer << "\n";
    }
    else {
        cout << "Address is not assigned, you tried deferencing a null pointer\n";
    }

    return 0;
}
/*Output:
The value of x is: 123*/
```

### Dynamic Memory - Makes programs more flexible, useful when memory needed is unknown

```cpp
// if new is used, delete should be used to free memory
// new operator - allocate memory
// delete operator - free memory
#include <iostream>

using std::cout;
using std::cin;
using std::string;

int main() {
    char *pGrades = NULL;
    int size;

    cout << "Enter number of grades: ";
    cin >> size;

    pGrades = new char[size];
    for (int i = 0; i < size; i++){
        cout << "Enter grade #" << i + 1 << ": ";
        cin >> pGrades[i];
    }

    for (int i = 0; i < size; i++){
        cout << "Grade #" << i + 1 << ": " << pGrades[i] << "\n";
    }

    delete[] pGrades;

    return 0;
}
/*Output:
Enter number of grades: 5
Enter grade #1: A
Enter grade #2: B
Enter grade #3: C
Enter grade #4: D
Enter grade #5: E
Grade #1: A
Grade #2: B
Grade #3: C
Grade #4: D
Grade #5: E*/
```

### Recursion - function invokes itself

```cpp
// Iterative vs Recursive
// Advantage of recursive: Less code, cleaner, useful for sorting and searching algorithms
// Disadvantage of recursive: use more memory, slower, harder to debug
#include <iostream>

using std::cout;
using std::cin;
using std::string;

void walkIterative(int steps);
void walkRecursive(int steps);
int factorialIterative(int num);
int factorialRecursive(int num);

int main() {

    // Iterative
    cout << "Iterative\n";
    walkIterative(10);
    // Recursive
    cout << "\nRecursive\n";
    walkRecursive(10);
    // Iterative Factorial
    cout << "\nIterative Factorial: " <<
    factorialIterative(5);
    // Recursive Factorial
    cout << "\nRecursive Factorial: " <<
    factorialRecursive(5);

    return 0;
}

// Iterative
void walkIterative(int steps) {
    for (int i = steps; i > 0; i--) {
        cout << "Step " << i << "\n";
    }
}

// Recursive
void walkRecursive(int steps) {
    if (steps > 0) {
        cout << "Step " << steps << "\n";
        walkRecursive(steps - 1);
    }
}

// Iterative Factorial
int factorialIterative(int num) {
    int result = 1;
    for (int i = 1; i <= num; i++) {
        result *= i;
    }
    return result;
}

// Recursive Factorial
int factorialRecursive(int num) {
    if (num == 0) {
        return 1;
    } else {
        return num * factorialRecursive(num - 1);
    }
}
/*Output:
Iterative
Step 10
Step 9
Step 8
Step 7
Step 6
Step 5
Step 4
Step 3
Step 2
Step 1

Recursive
Step 10
Step 9
Step 8
Step 7
Step 6
Step 5
Step 4
Step 3
Step 2
Step 1

Iterative Factorial: 120
Recursive Factorial: 120*/
```

### Function Templates - Used to generate as many overloaded functions as needed with different data types

```cpp
// auto keyword can be used to automatically determine the data type of the variable
#include <iostream>
using std::cout;
using std::cin;

// Function Template
template <typename T>
// This only works with same data type
T max(T x, T y) {
    return (x > y) ? x : y;
}
// This works with different combinations of data types
template <typename T, typename U>
auto max(T x, U y) {
    /*auto is the return type,T can be used to return the T data type,
    U can be used to return the U data type,
    auto can be used to return the data type automatically*/
    return (x > y) ? x : y;
}

// Function overloading for different data types
int max(int x, int y) {
    return (x > y) ? x : y;
}
char max(char x, char y) {
    return (x > y) ? x : y;
}
double max(double x, double y) {
    return (x > y) ? x : y;
}

int main() {
    // Function overloading for different data types
    cout << "Normal Function Overloading\n";
    cout << max(5, 10) << '\n';
    cout << max(5.5, 10.5) << '\n';
    cout << max('A', 'B') << '\n';

    // Using Function Templates
    cout << "\nFunction Templates\n";
    cout << max(5, 10) << '\n';
    cout << max(5, 10.5) << '\n';

    return 0;
}
/*Output:
Normal Function Overloading
10
10.5
B

Function Templates
10
10.5*/
```

### Structs - Structure that groups variables under one name, think of it as a class

```cpp
// Variables in structs are known as "members"
#include <iostream>
using std::cout;
using std::cin;
using std::string;

struct student {
    string name;
    int age;
    double gpa;
    bool enrolled;
};

int main() {
    student s1;
    s1.name = "John";
    s1.age = 21;
    s1.gpa = 3.5;
    s1.enrolled = true;

    cout << "Name: " << s1.name << "\n";
    cout << "Age: " << s1.age << "\n";
    cout << "GPA: " << s1.gpa << "\n";
    cout << "Enrolled: " << s1.enrolled << "\n";

    return 0;
}
/*Output:
Name: John
Age: 21
GPA: 3.5
Enrolled: 1*/

// Passing by structs as arguments uses pass by value by default
// Using pass by reference to avoid copying the struct
#include <iostream>
using std::cout;
using std::cin;
using std::string;

struct Car {
    string model;
    int year;
};

void printCar(Car &car);

int main() {
    Car c1;
    c1.model = "Corvette";
    c1.year = 2021;

    cout << &c1 << '\n';

    printCar(c1);
    return 0;
}

void printCar(Car &car) {
    cout << &car << '\n';
    cout << car.model << '\n';
    cout << car.year << '\n';
}
/*Output:
0x2baffffe20
0x2baffffe20
Corvette
2021*/
```

### Enumerations

```cpp
// Enums - user defined data type consisting of paired integer constants
#include <iostream>
using std::cout;
using std::cin;
using std::string;

enum Day {sunday = 0, monday = 1, tuesday = 2, wednesday = 3, thursday = 4, friday = 5, saturday = 6};

int main() {

    // Enumeration data type
    Day today = sunday;

    switch (today) {
        case sunday:
            cout << "Today is sunday";
            break;
        case monday:
            cout << "Today is monday";
            break;
        case tuesday:
            cout << "Today is tuesday";
            break;
        case wednesday:
            cout << "Today is wednesday";
            break;
        case thursday:
            cout << "Today is thursday";
            break;
        case friday:
            cout << "Today is friday";
            break;
        case saturday:
            cout << "Today is saturday";
            break;
        default:
            cout << "Invalid day";
            break;
    }

    // Switch statement cannot be used with string data type
    // string today = "sunday";
    // switch(today){
    //     case "sunday":
    //         cout << "Today is sunday";
    //         break;
    //     case "monday":
    //         cout << "Today is monday";
    //         break;
    //     case "tuesday":
    //         cout << "Today is tuesday";
    //         break;
    //     case "wednesday":
    //         cout << "Today is wednesday";
    //         break;
    //     case "thursday":
    //         cout << "Today is thursday";
    //         break;
    //     case "friday":
    //         cout << "Today is friday";
    //         break;
    //     case "saturday":
    //         cout << "Today is saturday";
    //         break;
    //     default:
    //         cout << "Invalid day";
    //         break;
    // }

    return 0;
}
/*Output:
Today is sunday*/
```

### Object Oriented Programming

```cpp
#include <iostream>
using std::cout;
using std::cin;
using std::string;

class Human {
    public:
        string name;
        int age;
        void introduce() {
            cout << "Hello, my name is " << name << " and I am " << age << " years old." << "\n";
        }
        void drink() {
            cout << "I am drinking water." << "\n";
        }
        void eat() {
            cout << "I am eating food." << "\n";
        }
};

int main() {

    Human human1;

    cout << "Enter your name: ";
    cin >> human1.name;
    cout << "Enter your age: ";
    cin >> human1.age;

    human1.introduce();
    human1.drink();
    human1.eat();

    return 0;
}
/*Output:
Enter your name: John
Enter your age: 12
Hello, my name is John and I am 12 years old.
I am drinking water.
I am eating food.*/

// With Constructors
#include <iostream>
using std::cout;
using std::cin;
using std::string;

class Pizza{
    public:
        string topping1;
        string topping2;

    // Constructors
    Pizza(){
    }

   // Overloaded Constructors
    Pizza(string topping1){
        this->topping1 = topping1;
    }

    Pizza(string topping1, string topping2){
        this->topping1 = topping1;
        this->topping2 = topping2;
    }
};

int main() {
    Pizza pizza1("cheese");
    Pizza pizza2("cheese", "pepperoni");
    Pizza pizza3;

    cout << pizza1.topping1 << "\n";
    cout << pizza2.topping1 << " and " << pizza2.topping2 << "\n";

    return 0;
}
/*Output:
cheese
cheese and pepperoni*/
```

### Getters & Setters

```cpp
// Getter - makes private attribute readable
// Setter - makes private attribute writable
#include <iostream>
using std::cout;
using std::cin;
using std::string;

class Stove{
    private:
        int temperature = 0;

    public:
        // Setter - makes private attribute writable
        void setTemperature(int temp){
            if(temp > 500){
                cout << "Temperature is too high!\n";
            }
            else if (temp < 5){
                cout << "Invalid Temperature!\n";
            }
            else {
                temperature = temp;
            }
        }

        // Getter - makes private attribute readable
        int getTemperature(){
            return temperature;
        }
};

int main() {
    Stove stove;
    stove.setTemperature(-3);

    cout << "Stove temperature: " << stove.getTemperature();

    return 0;
}
```

### Inheritance

```cpp
#include <iostream>
using std::cout;
using std::cin;
using std::string;

// Parent class
class Animal {
    public:
        bool alive = true;

        void speak() {
            cout << "Grrrr\n";
        }

        void eat() {
            cout << "Nom nom nom\n";
        }

};

// Child class
class Dog: public Animal {
    public:
        string breed;

        void bark() {
            cout << "Woof Woof\n";
        }
};

int main() {
    Dog dog;
    Animal animal;

    cout << "Animal class\n";
    cout << animal.alive << "\n";
    animal.speak();
    animal.eat();

    // Dog class inherits from Animal class
    cout << "\nDog class\n";
    cout << dog.alive << "\n";
    dog.bark();
    dog.speak();
    dog.eat();

    return 0;
}
/*Output:
Animal class
1
Grrrr
Nom nom nom

Dog class
1
Woof Woof
Grrrr
Nom nom nom*/
```

---

## Algorithms

### Bubble Sort - Sorts by comparing adjacent elements e.g. if a is greater than b, swap them

```cpp
#include <iostream>

void bubbleSort(int array[], int size);

int main() {
    using std::cout;
    using std::string;
    using std::cin;

    int array[] = {2, 1, 3, 4, 5, 6, 7, 8, 9, 10};
    int size = sizeof(array) / sizeof(array[0]);
    bubbleSort(array, size);

    for (int element: array) {
        cout << element << " ";
    }

    return 0;
}

void bubbleSort(int array[], int size) {
    int temp;
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (array[j] < array[j + 1]) { // If statement to check if first element is less than second statement
                temp = array[j]; // temp -> 1st, Assign the first element to temporary variable
                array[j] = array[j + 1]; // 1st -> 2nd, Assign the first element to the second element
                array[j + 1] = temp; // 2nd -> temp, Assign the second element to the temporary variable which is the first element
            }
        }
    }
}
```

### Luhn Algorithm - Used to validate credit card number

> #### <u>How it works</u>
>
> 1.  Double every second digit from right to left.
> 2.  If doubled number is 2 digits, split them.
> 3.  Add all single digits from step 2.
> 4.  Add all odd number digits from right to left.
> 5.  Sum results from steps 3 & 4.
> 6.  If step 5 is divisible by 10, credit card number is valid.

```cpp
//Luhn Algorithm
#include <iostream>

using std::string;
using std:: cout;
using std:: cin;

int getDigit(const int number);
int sumOddDigits(const string cardNum);
int sumEvenDigits(const string cardNum);

int main() {
    int result = 0;
    string cardNum;

    cout << "Enter a credit card number: ";
    cin >> cardNum;

    int sumOdd = sumOddDigits(cardNum);
    int sumEven = sumEvenDigits(cardNum);
    result = sumOdd + sumEven;

    std::cout << "Sum of odd numbers: " << sumOdd << "\n";
    std::cout << "Sum of even numbers: " << sumEven << "\n";
    std::cout << "Total: " << result << "\n";

    if (result % 10 == 0) {
        std::cout << "Valid Credit Card Number!\n";
    } else {
        std::cout << "Invalid Credit Card Number :(\n";
    }
}

// Get the last digit of the number only if the number is greater than 10
int getDigit(const int number) {
    return number % 10 + (number / 10 % 10);
    // Example: number = 18
    // 18 % 10 = 8
    // Since int division, 18 / 10 = 1
    // 1 % 10 = 1
    // 8 + 1 = 9
    // Return 9
}

int sumOddDigits(const string cardNum) {
    int sum = 0;
    for (int i = cardNum.size() - 1; i >= 0; i -= 2) { // Since using index, -1 to start from the last value, -2 to start from second last value
        sum+= (cardNum[i] - 48);
        // Subtract 48 or '0' to convert from ASCII
        // 0 has a decimal value of 48
        // 1 has a decimal value of 49
        // 2 has a decimal value of 50 and so on....
        // cardNum[i] returns the decimal value of the character
        // cardNum[i] - 48 returns the actual number
    }
    return sum;
}

int sumEvenDigits(const string cardNum) {
    int sum = 0;
    for (int i = cardNum.size() - 2; i >= 0; i -= 2) { // Since using index, -1 to start from the last value, -2 to start from second last value
        sum+=getDigit((cardNum[i] - 48) * 2);
    }
    return sum;
}
/*
Positive Output:
Enter a credit card number: 5396190365417138
Sum of odd numbers: 36
Sum of even numbers: 34
Total: 70
Valid Credit Card Number!

Negative Output:
Enter a credit card number:
5396190365417139
Sum of odd numbers: 37
Sum of even numbers: 34
Total: 71
Invalid Credit Card Number :(*/
```
