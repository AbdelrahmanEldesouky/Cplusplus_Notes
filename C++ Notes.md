# C++ Programing Language

## About

> ### Year 
>
> Fall 2022
>
> ### Level
>
> Beginner and Advanced  

> # BY 
>
> ### A. S.  Eldesouky

## Table of Content

[TOC]

## Diving In 



## Variables and Data Type 

- **Variables :** A named piece of memory that use to store specific types of data.
- **Data Type :** A particular kind of data item, as defined by the values it can take.

 ### Number Systems 

- There is different number systems other than decimal system (Binary, Octal, Hexadecimal, etc.)

- All data is represented by a bench of grouped cells of **0**'s and **1**'s in memory 
- Bigger numbers needs bigger memory to represent 
- Hexadecimal makes us deals with the streams of data with **0**'s and **1**'s more easier 
- Octal like hexadecimal but it's no longer used in modern times 

|   System    | Base |            Represent            |     Example      | Symbol |
| :---------: | :--: | :-----------------------------: | :--------------: | :----: |
|   Decimal   |  10  |         **0** to **9**          |       5924       |  non   |
|   Binary    |  2   |          **0** , **1**          | 0001011100100100 |   0b   |
|    Octal    |  8   |         **0** to **7**          |      13444       |   0    |
| Hexadecimal |  16  | **0** to **9** , **A** to **F** |       1724       |   0x   |

```c++
#include <iostream>
int main()
{
    // Representation in C++
    int decimal = 15 ; 
    int binary = 0b1111 ; 
    int octal = 017 ; 
    int hexa = 0xF ; 

    // Print Numbers 
    std::cout << "decimal is " << decimal << std::endl ; 
    std::cout << "binary is " << binary << std::endl ; 
    std::cout << "octal is " << octal << std::endl ; 
    std::cout << "hexa is " << hexa << std::endl ; 
}

/*	Output 
* 
*	decimal is 15
*	binary is 15 
*	octal is 15
*	hexa is 15
*/
```

### Declaration and Initialization  

```c++
// Variable braced initialization
Data_Type Variable_Name {Value} ; 

// Function variable initialization
Data_Type Variable_Name (Value) ; 

// Assignment initialization
Data_Type Variable_Name = Value ;
```

> Size of data type in memory 
>
> ```c++
> std::cout << sizeof(data_type) ; 

### Integer 

- Stores decimal 
- Typically occupies 4 bytes or more in memory (depend on system)

#### Initialization

1. Variable braced initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Variable braced initialization ***************************/
       // declaration and initialization
       int variable_X {} ;							  // Initializes with zero 
       int variable_Y {10} ; 						// Initializes with 10 
       int variable_Z {15} ; 						// Initializes with 15
       int variable_F {variable_Y} ;		 // Initializes with different exist variable
       
       // Error and Warning 
       //int variable_H {variable_W} ; 	// Initializes with different not exist variable -> compiler error 
       //int variable_V {2.9} ;				 // Initializes with different data type ->  error or warning 
   
       std::cout << "variable_X: " << variable_X << std::endl ; 
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
   }
   
   /*	Output 
   * 
   *	variable_X: 0
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   */
   ```

2. Function variable initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Function variable initialization ***************************/
       // declaration and initialization
       int variable_Y (10) ; 						// Initializes with 10 
       int variable_Z (15) ; 						// Initializes with 15
       int variable_F (variable_Y) ;		 // Initializes with different exist variable 
   
       
       // Error and Warning 
       //int variable_H {variable_W} ; 	// Initializes with different not exist variable -> compiler error 
       int variable_V (2.9) ;				 // Initializes with different data type ->  information lost 
   
     
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
       std::cout << "variable_V: " << variable_V << std::endl ;
   }
   
   /*	Output 
   * 
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   *	variable_V: 2
   */
   ```

3. Assignment initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Assignment initialization ***************************/
       // declaration integer 
       int variable_name ; 
       // initialization integer with 20
       variable_name = 20 ; 
       // declaration and initialization
       int variable_X = 0 ;						// Initializes with zero 
       int variable_Y = 10 ; 						// Initializes with 10 
       int variable_Z = 15 ; 						// Initializes with 15
       int variable_F = variable_Y ;		        // Initializes with different exist variable  
   
       int variable_V = 2.9  ;				        // Initializes with different data type
   
    
       std::cout << "variable_name: " << variable_name << std::endl ; 
       std::cout << "variable_X: " << variable_X << std::endl ; 
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
       std::cout << "variable_V: " << variable_V << std::endl ;
   }
   
   /*	Output 
   * 
   *	variable_name: 20
   *	variable_X: 0
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   *	variable_V: 2
   */
   ```

#### Modifiers

1. Singed and unsigned

   ```c++
   signed int variable_X {10} ; 		// Initializes with 10 
   signed int variable_Y {-10} ; 		// Initializes with -10 
   
   unsigned int variable_Z {10} ; 		// Initializes with 10 
   unsigned int variable_F {-10} ; 	// compiler error
   ```

   | Type with Modifiers | Bytes in memory |                  Range                  |
   | :-----------------: | :-------------: | :-------------------------------------: |
   |    unsigned int     |        4        |       **0** to **4,294,967,295**        |
   |     signed int      |        4        | **-2,147,483,648** to **2,147,483,647** |

2. long and short 

   |                     Type with Modifiers                      | Bytes in memory | Example |
   | :----------------------------------------------------------: | :-------------: | :-----: |
   |       short, short int, signed short, signed short int       |        2        | -32768  |
   |                      unsigned short int                      |        2        |   455   |
   |         long, long int, signed long, signed long int         |     4 or 8      |  -1588  |
   |                      unsigned long int                       |     4 or 8      |   33    |
   | long long, long long int, signed long long, signed long long int |        8        | -459874 |
   |                    unsigned long long int                    |        8        |  44658  |

   ```c++
   #include <iostream>
   int main()
   {
       //short and long
       short short_var {-32768} ; //  2 Bytes 
       short int short_int {455} ; // 
       signed short signed_short {122}; //
       signed short int signed_short_int {-456}; // 
       unsigned short int unsigned_short_int {456};
       
       int int_var {55} ; // 4 bytes
       signed signed_var {66};//
       signed int signed_int {77};//
       unsigned int unsigned_int{77};
       
       long long_var {88}; // 4 OR 8 Bytes
       long int long_int {33};
       signed long signed_long {44};
       signed long int signed_long_int {44};
       unsigned long int unsigned_long_int{44};
   
       long long long_long {888};// 8 Bytes
       long long int long_long_int {999};
       signed long long signed_long_long {444};
       signed long long int signed_long_long_int{1234};
       unsigned long long int unsigned_long_long_int{1234};
   
       std::cout << "Short variable, size : " << sizeof (short) << " bytes" << std::endl;
       std::cout << "Short Int, size : " << sizeof (short int) << " bytes" << std::endl;
       std::cout << "Signed short, size : " << sizeof (signed short) << " bytes" << std::endl;
       std::cout << "Signed short int, size : " << sizeof (signed short int) << " bytes" << std::endl;   
       std::cout << "unsigned short int, size : " << sizeof (unsigned short int) << " bytes" << std::endl;   
       std::cout << "---------------------" << std::endl;
   
       std::cout << "Int variable, size : " << sizeof (int) << " bytes" << std::endl;
       std::cout << "Signed variable, size : " << sizeof (signed) << " bytes" << std::endl;
       std::cout << "Signed int, size : " << sizeof (signed int) << " bytes" << std::endl;       
       std::cout << "unsigned int, size : " << sizeof (unsigned int) << " bytes" << std::endl;        
       std::cout << "---------------------" << std::endl;
   
       std::cout << "Long variable, size : " << sizeof (long) << " bytes" <<std::endl;
       std::cout << "Long int, size : " << sizeof (long int) << " bytes" << std::endl;
       std::cout << "Signed long, size : " << sizeof (signed long) << " bytes" << std::endl;
       std::cout << "Signed long int, size : " << sizeof (signed long int) << " bytes" << std::endl;  
       std::cout << "unsigned long int, size : " << sizeof (unsigned long int) << " bytes" << std::endl;  
       std::cout << "---------------------" << std::endl;
       
       std::cout << "Long long, size : " << sizeof (long long) << " bytes" << std::endl;
       std::cout << "Long long int, size : " << sizeof (long long int) << " bytes" << std::endl;
       std::cout << "Signed long long, size : " << sizeof (signed long long) << " bytes" <<std::endl;   
       std::cout << "Signed long long int, size : " << sizeof (signed long long int) << " bytes" << std::endl;       
       std::cout << "unsigned long long int, size : " << sizeof (unsigned long long int) << " bytes" << std::endl;  
       std::cout << "---------------------" << std::endl;
      
       return 0;
   }
   
   /* Output
           Short variable, size : 2 bytes
           Short Int, size : 2 bytes
           Signed short, size : 2 bytes
           Signed short int, size : 2 bytes
           unsigned short int, size : 2 bytes
           ---------------------
           Int variable, size : 4 bytes
           Signed variable, size : 4 bytes
           Signed int, size : 4 bytes
           unsigned int, size : 4 bytes
           ---------------------
           Long variable, size : 4 bytes
           Long int, size : 4 bytes
           Signed long, size : 4 bytes
           Signed long int, size : 4 bytes
           unsigned long int, size : 4 bytes
           ---------------------
           Long long, size : 8 bytes
           Long long int, size : 8 bytes
           Signed long long, size : 8 bytes
           Signed long long int, size : 8 bytes
           unsigned long long int, size : 8 bytes
           ---------------------
   */
   ```

### Fraction

- A numerical quantity that is not a whole number (e.g. 1/2, 0.5).
- Floating point numbers memory representation by **[IEEE_754](https://en.wikipedia.org/wiki/IEEE_754)** 

#### Fraction Data Type

|    Type     | Bytes in memory | Precision | Symbol (Suffixes) |       Example        |
| :---------: | :-------------: | :-------: | :---------------: | :------------------: |
|    float    |        4        |     7     |         f         |      0.123456f       |
|   double    |        8        |    15     |         -         |   0.12345678912345   |
| long double |       12        | > double  |         L         | 0.12345678912345678L |

```c++
  #include <iostream>
  #include <iomanip>
  int main()
  {
      // Declare and initialize floating point 
      float X {0.123456789123456789123456789f} ; 
      double Y {0.123456789123456789123456789} ; 
      long double Z {0.123456789123456789123456789L} ; 

      // Size of data types
      std::cout << "Size of float: " << sizeof(float) << std::endl ; 
      std::cout << "Size of double: " << sizeof(double) << std::endl ; 
      std::cout << "Size of long double: " << sizeof(long double) << std::endl ; 

      // Precision of floating point
      std::cout << std::setprecision(20) ;        // control srd::cout precision length
      std::cout << "float: " << X << std::endl ; 
      std::cout << "double: " << Y << std::endl ; 
      std::cout << "long double: " << Z << std::endl ; 
  }

  /* Output
          Size of float: 4
          Size of double: 8
          Size of long double: 16

          float: 0.12345679104328155518				  #valid 7 precision 
          double: 0.1234567891234567838		  		#valid 15 precision
          long double: 0.12345678912345678912		#valid longer than 15 precision
  */
```

#### Narrowing Conversion

- Precision is a problem for a **float** data type because it's very limited.
- **double & long double** commonly used for floating point representation.

```c++
#include <iostream>
#include <iomanip>
int main()
{
    float X {123400081945.0f} ; 
    double Y {123400081945.0} ; 

    std::cout << std::setprecision(20) ;        // control srd::cout precision length
    std::cout << "float: " << X << std::endl ; 
    std::cout << "double: " << Y << std::endl ;
}

/* Output 
        float: 123400085504
        double: 123400081945
*/
```

 #### Scientific Notation

- Scientific notation is a way of expressing numbers that are too large or too small to be conveniently written in decimal form.

  ![Scientific Notation Definition](/image/scientific-notation.svg)

```c++
#include <iostream>
#include <iomanip>
int main()
{
    double X {192400023} ; 
    double Y {1.92400023e8} ; 
    double Z {1.924e8} ;

    double A {0.00000000003498} ;
    double B {3.498e-11} ;

    std::cout << std::setprecision(20) ;        // control srd::cout precision length
    std::cout << "X: " << X << std::endl ; 
    std::cout << "Y: " << Y << std::endl ;
    std::cout << "Z: " << Z << std::endl ;
    std::cout << "A: " << A << std::endl ;
    std::cout << "B: " << B << std::endl ;
}

/* Output 
        X: 192400023
        Y: 192400023
        Z: 192400000
        A: 3.4979999999999998372e-11
        B: 3.4979999999999998372e-11
*/
```

#### Infinity and NaN

- Infinity happened when we try to divide **value** over **0** 
- NaN happened when we try to divide **0.0** over **0.0**

```c++
#include <iostream>
int main()
{
    double X {5.6} ; 
    double Y {-5.6} ; 
    double Z {} ; 

    std::cout << "X / Z = " << X / Z << std::endl; 
    std::cout << "Y / Z = " << Y / Z << std::endl;
    std::cout << "Z / Z = " << Z / Z << std::endl;
}

/* Output
        X / Z = inf
        Y / Z = -inf
        Z / Z = nan
*/
```

### Booleans 

- A binary variable that can have one of two possible values, **0** (false) or **1** (true).
- Use in decision statement or function return 
- Take one byte in memory

```c++
#include <iostream>
int main()
{
    bool red {false};
    bool green {true};
    
    //size of boolean
    std::cout << "Size of bool : " << sizeof(bool) << std::endl;

    if (red == true)
    {
        std::cout << "Stop!" << std::endl;
    }
    else
    {
        std::cout << "Go through!" << std::endl;
    }

    if (green)
    {
        std::cout << "The light is green!" << std::endl;
    }
    else
    {
        std::cout << "The light is NOT green!" << std::endl;
    }

    //1 -->> true
    //0 -->> false
    std::cout << "red : " << red << std::endl;
    std::cout << "green : " << green << std::endl;

    std::cout << std::boolalpha;                // control std::cout output for booleans data
    std::cout << "red : " << red << std::endl;
    std::cout << "green : " << green << std::endl;
}

/* Output
        Size of bool : 1   
        Go through!        
        The light is green!
        red : 0
        green : 1
        red : false        
        green : true
*/
```

### Characters

- A data type that holds one character (letter, number, etc.)

- Take one byte in memory (2^8 = 256 different values **0~255**)

- Use **ASCII** code for representation

   ![ASCII Code](/image/ASCII-Table.png)

  > - It's possible to assign a valid ASCII code to a char variable, and the corresponding character will be stored in.
  > - ASCII was the first encoding representation text in a computer.
  > - It doesn't represent all characters (e.g. Arabic, east Asian language).
  > - There's better way to represent character in C++ like **Unicode**

```c++
#include <iostream>
int main()
{
	char character1 {'a'};
    char character2 {'r'};
    char character3 {'r'};
    char character4 {'o'};
    char character5 {'w'};
    
    std::cout << character1 << std::endl;
    std::cout << character2 << std::endl;
    std::cout << character3 << std::endl;
    std::cout << character4 << std::endl;
    std::cout << character5 << std::endl;
    
    char value = 65 ;                               				// ASCII character code for 'A'
    std::cout << "value : " << value << std::endl;  // A
    std::cout << "value as intager : " << static_cast<int>(value) << std::endl; 
}

/* Output
        a
        r        
        r        
        o        
        w        
        value : A
        value as intager : 65
*/
```

### Auto 

Let the compiler deduce the type 

```c++
#include <iostream>
int main()
{
	auto A {12};        // int
    auto B {13.0};      // double
    auto C {14.0f};     // float
    auto D {15.0l};     // long double
    auto E {'e'};       // char
    auto F { 123u};     // unsigned int
    auto G { 123ul};    //unsigned long int
    auto H { 123ll};    // long long int

    std::cout << "A occupies : " << sizeof(A) << " bytes" << std::endl;
    std::cout << "B occupies : " << sizeof(B) << " bytes" << std::endl;
    std::cout << "C occupies : " << sizeof(C) << " bytes" << std::endl;
    std::cout << "D occupies : " << sizeof(D) << " bytes" << std::endl;
    std::cout << "E occupies : " << sizeof(E) << " bytes" << std::endl;
    std::cout << "F occupies : " << sizeof(F) << " bytes" << std::endl;
    std::cout << "G occupies : " << sizeof(G) << " bytes" << std::endl;
    std::cout << "H occupies : " << sizeof(H) << " bytes" << std::endl;
}

/* Output 
        A occupies : 4 bytes 
        B occupies : 8 bytes 
        C occupies : 4 bytes 
        D occupies : 16 bytes
        E occupies : 1 bytes 
        F occupies : 4 bytes 
        G occupies : 4 bytes
        H occupies : 8 bytes
*/
```

### Assignment 

- Change the data after declare it with another value 
- Don't change the value of **auto** data type with another to avoid garbage value

```c++
#include <iostream>
int main()
{
	int A{123}; // Declare and initialize
    std::cout << "A : "  << A << std::endl;
    
    A = 55; // Assign
    std::cout << "A : "  << A << std::endl;

    std::cout << "----------------" << std::endl;

    double B {44.55}; // Declare and initialize
    std::cout << "B : " << B << std::endl;
    
    B = 99.99; // Assign
    std::cout << "B : " << B << std::endl;

    std::cout << "----------------" << std::endl;

    bool state{false}; // Declare and initialize
    std::cout << std::boolalpha;
    std::cout << "state : " << state << std::endl;
    
    state = true; // Assign
    std::cout << "state : " << state << std::endl;

    std::cout << "----------------" << std::endl;
    
    auto C {333u}; // Declare and initialize with type deduction
    std::cout << "C : " << C << std::endl;
    
    C = -22; // Assign negative number. DANGER!
    std::cout << "C : " << C << std::endl;
}

/* Output
        A : 123
        A : 55
        ----------------
        B : 44.55       
        B : 99.99       
        ----------------
        state : false
        state : true
        ----------------
        C : 333
        C : 4294967274
*/
```

## Operation on Data





