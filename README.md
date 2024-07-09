<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rounded&height=300&color=gradient&text=Work%20in%20Progress" />
</p>
<h1 align="center"> Hello! I'm sorry! Working on that! </h1>

# Index
<ol>
	<li><strong>Introduction</strong></li>
	<li><strong>Context of Printf</strong></li>
	<li><strong>Understading its usage</strong></li>
	<li><strong>Creating a printf from scratch</strong></li>
	<ol>
		<li>Format Specifiers</li>
		<li>Variadic Functions</li>
	</ol>
	<li><strong>Building a printf</strong></li>
</ol>

# About

The main objective of this project is to replicate the printf function. It's quite important for two reasons: 1. Develop the ability to build your own tool, recreating fundamental functions like printf and 2. understand more deeply the concepts of variadic functions and more.

# 1. Introduction

Printf is a standard function in many libraries that simply does formatted printing of text.

As defined in the GNU.org, printf prints the format string, interpreting ‘%’ directives and ‘\’ escapes to format numeric and string arguments in a way that is mostly similar to the C ‘printf’ function.

In C, printf is a standard library function that formats text and writes it to standard output. The name, printf is short for print formatted where print refers to output to a printer although the functions are not limited to printer output.


# 2. Context of Printf

## 2.1. Writing, writing and writing.

The function to print is fundamental. Just like performing calculations, to print is a basic routine that every computer must perform. Therefore, the usage of printing is as old as the programming languages itself. Let's briefly discuss about the historical context of printf.

Before talking about prints, let's see write().

Write() is one of the most basic functions. The write function writes up to size bytes from buffer to the file with descriptor filedes. The data in buffer is not necessarily a character string and a null character is output like any other character. (Input and Output Primitives https://www.gnu.org/savannah-checkouts/gnu/libc/manual/html_node/I_002fO-Primitives.html#I_002fO-Primitives). 

When I say that is basic, I mean it. You see, every programming language must perform 5 basic tasks. Those are: 
<ol>
	<li><strong>Input</strong> - getting data and commands into the computer</li>
	<li><strong>Output</strong> - getting your results out of the computer</li>	
	<li><strong>Arithmetic</strong> - performing mathematical calculations on your data</li>
	<li><strong>Conditional or looping</strong> - testing to see if a condition is true or false, and cycling through a set of instructions until some condition is met</li>
</ol>

In this regard, write is one of those functions that perform input and output. It's basic because it works with fundamental parts of any computer architecture, just like the Input/Output (I/O), CPU and ALU. If you had anything else than the basic computer architecture you should perform the basic tasks, like calculating, reading and writing. And, of course, Printf is a type of a write function.

The writing functions was always present in the routines of the programming languages since the early days. 

## 2.2. Brief history of printf

**In the 1940s**, early computers like **ENIAC** and **UNIVAC** did not have high-level programming languages. Programs were written in machine code or assembly language. Output was typically handled by hardware-specific instructions to control devices like printers or punched card readers.

**FORTRAN** (Formula Translation) was introduced in **1957** it included basic I/O operations, such as `PRINT` for outputting data. In the following year, we could see this in the **LISP** language, one of the earliest functional programming languages, also introduced basic I/O functions. For example, print was used to display output.  

Was only in **1960s** that **ALGOL** (Algorithmic Language) influential in many modern languages, provided structured programming concepts but relied on implementation-specific methods for I/O. It was the first programming language to introduce the `printf`.  The format specification for ALGOL owed IMO something to FORTRAN usage; elements were format directives unless they were specifically identified as literal strings - the inverse of C usage. Also, **BCPL** (Basic Combined Programming Language) had a writef function, which later inspired ALGOL and C.

The `printf` function was introduced with **The C Programming Language**, written by Dennis Ritchie and Brian Kernighan at Bell Labs for the Unix operating system. The name stands for "print formatted.". In the first chapter of The C Programming Language (Ritchie & Kernighan, 1978) the authors introduced the "Hello, World" C version

```C

#include <stdio.h>
main()
{
	printf("hello, world\n");
}
```
`printf` provided a way to produce formatted text, using placeholders (format specifiers) within a format string to specify how subsequent arguments should be interpreted and displayed.

Accordingly to Ritchie and Kernighan (1978), The output function printf translates internal values to characters. The syntax will be

```C
int		printf(char *format, arg1, arg2, ... );
```
printf converts, formats, and prints its arguments on the standard output under control of the format. It returns the number of characters printed.

## 2.3. Printf in other languages

The influence of printf spread as the C programming language became widely adopted. The book "The C Programming Language" by Kernighan and Ritchie (often referred to as K&R) helped popularize the function. 1980s-1990s: As Unix and C became the foundation for many operating systems and applications, other languages began to incorporate printf-like functions:

**C++ (1983)**: Inherited printf from C but also introduced cout with stream insertion operators for more flexible and type-safe I/O.
```cpp
printf("Hello, World!\n");
std::cout << "Hello, World!" << std::endl;
```

**Perl (1987)**: Included a printf function for formatted output.
```perl
	printf("Hello, %s!\n", "World");
```

**Python (1991)**: Added a printf-like formatting method with the % operator and later introduced more modern string formatting techniques.
```python
	print("Hello, %s!" % "World")
```

**PHP (1995)**: Included printf for formatted output in web development.
```php
printf("Hello, %s!", "World");
```
**Java (1995)**: Java introduced System.out.printf in version 5.0 (2004), providing C-style formatted output.
```java
System.out.printf("Hello, %s!", "World");
```

**C# (2000):** .NET introduced String.Format, which provides similar functionality.
```csharp
Console.WriteLine(String.Format("Hello, {0}!", "World"));
```

**Ruby (1995)**: Included a printf method for formatted output.
```ruby
printf("Hello, %s!", "World");
```

**JavaScript (1995):** Modern JavaScript environments like Node.js can use template literals to achieve similar formatted output.
```javascript
console.log(`Hello, ${"World"}!`);
```

# 3. Understanding its usage

Printf is included in the Standard Input/Output library in C. Hence, to use it, we must declare in the preprocessor the following header:
```C
#include <stdio.h>
```
To read more about preprocessors and libraries, you can find in this [link](https://github.com/lude-bri/libft_42_LP)

As showned earlier, the syntax of printf in C is:

```C
int	printf(char *format, arg1, ...);
```

An example of its usage:

```C
#include <stdio.h>

int	main(void)
{
	printf("Hello, World\n");
}
```
The output wanted will be:
```
Hello, World
```

You can also use it with multiple arguments

```C
#include <stdio.h>

int	main(void)
{
	char	*str = "It works!";

	printf("%s\n", str);
	return (0);
}
```

The output expected will be:
```
It works!
```

Or you can even use like this:
```C
#include <stdio.h>

int	main(void)
{
	char	*name = "Luigi";
	int	age = 26;

	printf("Hello, my name is %s and I am %i years old", name, age);
	return (0);
}
```

The output expected will be:
```
Hello, my name is Luigi and I am 26 years old
```

Let's take a look at this example

<div align=center>
	<image src=images/graph_01.png>
</div>

As you can see, when the function encounters a **format specifier** (beginning with a % character), it retrieves the corresponding argument and formats it in a specific way. 

For example, upon finding the first %, it identifies its type. In our case, the first type is `s` so it processes the first argument as a **string** and uses a specific method to insert the string "Luigi" into the output. The function repeats this procedure with each subsequent `%` it finds, and so on. 

In other hand, when the function printf does not encounter any `%`, writes everything normally into the output.

That is the way that printf function works. Prints every char into the output. If `%` is found, the function will check the next character is a **format specifier** or not. If it is, printf will check which specifier it is to print the correspondent.

# 4. Creating a printf from scratch

As said by Ritchie and Kernighan (1978)
>[!IMPORTANT]
>printf convers, formats, and prints its arguments on the standard output under control of the format. It returns the number of characters printed.

The format string contains two types of objects: ordinary characters, which are copied to the output stream, and conversion specifications, each of which causes conversion and printing of the next successive argument to `printf`.

Each conversion specification begins with a `%` and ends with a conversion character.

Knowing how the printf function works, it's easier to recreate it. First of all, the characteristics of `printf` is summarized in 
<ul>
	<li>a) Print every character,</li> 
	<li>b) If % is found, check what is the specifier and print the correspondent variable type,</li> 
	<li>c) the printf function can handle multiple arguments.</li>
</ul>

Hence, in order to create printf function from scratch we must consider two main aspects:**1. Format Specifiers** and **2. Variadic Functions.**

## 4.1. Format Specifiers

Format specifiers is used to tell the compiler about the type of data to be printed or scanned in input and output operations. Is not exclusive to printf, rather this works generally in C language.

They always start with a % symbol an are used in the formatted string in functions like `printf`, `scanf`, `sprintf`, `fprintf`, etc.

Following the table descripted by Ritchie and Kernighan (1978), we can see the **Basic Format Specifiers**

| **CHARACTER** | **ARGUMENT TYPE** | **PRINTED** |
:-----------: | :-------------: | :--------: |
|     d, i      |   int        | decimal number |
| o | int | unsigned octal number (without a leading zero) |
| x, X | int | unsigned hexadecimal number (without a leading 0x or 0X), using abcdef or ABCDEF for 10, ..., 15 |
| u | int | unsigned decimal number |
| c | int | single character |
| s | char * | print characters from the string until a '\0' or the number of characters given by the precision |
| f | double | [-]m.dddddd, where the number fo d's is given by the precision |
| e, E | double | [-]m.dddddde+xx or [-]m.ddddddE+xx, where the number of d's is given by the precision |
| g, G | double | use %e or %E if the exponent is less than -4 or greater than or equal to the precision otherwise use %f. Trailing zeros and a trailing decimal point are not printed |
| p | void *| pointer |
| % | - | no argument is converted, print a % |

You can also see more format specifiers used, for instance, `%li` for long ints or `%lu` for unsigned int long. Highly recommended for you to read more about this in [here](https://www.geeksforgeeks.org/format-specifiers-in-c/) or, if you are interested in seeing more about this in C programming language, read [this](http://cslabcms.nju.edu.cn/problem_solving/images/c/cc/The_C_Programming_Language_%282nd_Edition_Ritchie_Kernighan%29.pdf).

## 4.2. Variadic Functions

### 4.2.1. Definition
Variadic Functions are functions which take a variable number of arguments, e.g `printf`.

>[!IMPORTANT]
> ISO C defines a syntax for declaring a function to take a variable number or type of arguments. (Such functions are referred to as varargs functions or variadic functions.) However, the language itself provides no mechanism for such functions to access their non-required arguments; instead, you use the variable arguments macros defined in stdarg.h.[(GNU)](https://www.gnu.org/software/libc/manual/html_node/Variadic-Functions.html)

The library function printf is an example of a class of function where variable arguments are quite useful. This function prints its arguments (which can vary in type as well as number) under the control of a format template string.

### 4.2.2. Declaration of Variadic Functions

Defining and using a variadic function involves three steps:

Define the function as variadic, using an ellipsis (‘…’) in the argument list, and using special macros to access the variable arguments.

Declare the function as variadic, using a prototype with an ellipsis (‘…’), in all the files which call it.

Call the function by writing the fixed arguments followed by the additional variable arguments.

### 4.2.3. Macros in Variadic Functions

Here are descriptions of the macros used to retrieve variable arguments. These macros are defined in the header file stdarg.h.

Data Type: va_list
The type va_list is used for argument pointer variables.

Macro: void va_start (va_list ap, last-required)
Preliminary: | MT-Safe | AS-Safe | AC-Safe | See POSIX Safety Concepts.

This macro initializes the argument pointer variable ap to point to the first of the optional arguments of the current function; last-required must be the last required argument to the function.

Macro: type va_arg (va_list ap, type)
Preliminary: | MT-Safe race:ap | AS-Safe | AC-Unsafe corrupt | See POSIX Safety Concepts.

The va_arg macro returns the value of the next optional argument, and modifies the value of ap to point to the subsequent argument. Thus, successive uses of va_arg return successive optional arguments.

The type of the value returned by va_arg is type as specified in the call. type must be a self-promoting type (not char or short int or float) that matches the type of the actual argument.

Macro: void va_end (va_list ap)
Preliminary: | MT-Safe | AS-Safe | AC-Safe | See POSIX Safety Concepts.

This ends the use of ap. After a va_end call, further va_arg calls with the same ap may not work. You should invoke va_end before returning from the function in which va_start was invoked with the same ap argument.

In the GNU C Library, va_end does nothing, and you need not ever use it except for reasons of portability.

Sometimes it is necessary to parse the list of parameters more than once or one wants to remember a certain position in the parameter list. To do this, one will have to make a copy of the current value of the argument. But va_list is an opaque type and one cannot necessarily assign the value of one variable of type va_list to another variable of the same type.

Macro: void va_copy (va_list dest, va_list src)
Macro: void __va_copy (va_list dest, va_list src)
Preliminary: | MT-Safe | AS-Safe | AC-Safe | See POSIX Safety Concepts.

The va_copy macro allows copying of objects of type va_list even if this is not an integral type. The argument pointer in dest is initialized to point to the same argument as the pointer in src.

va_copy was added in ISO C99. When building for strict conformance to ISO C90 (‘gcc -std=c90’), it is not available. GCC provides __va_copy, as an extension, in any standards mode; before GCC 3.0, it was the only macro for this functionality.

These macros are no longer provided by the GNU C Library, but rather by the compiler.

If you want to use va_copy and be portable to pre-C99 systems, you should always be prepared for the possibility that this macro will not be available. On architectures where a simple assignment is invalid, hopefully va_copy will be available, so one should always write something like this if concerned about pre-C99 portability:
```C
{
  va_list ap, save;
  …
#ifdef va_copy
  va_copy (save, ap);
#else
  save = ap;
#endif
  …
}
```

Here is a complete sample function that accepts a variable number of arguments. The first argument to the function is the count of remaining arguments, which are added up and the result returned. While trivial, this function is sufficient to illustrate how to use the variable arguments facility.

```C
#include <stdarg.h>
#include <stdio.h>

int add_em_up (int count,...)
{
  va_list ap;
  int i, sum;

  va_start (ap, count);         /* Initialize the argument list. */

  sum = 0;
  for (i = 0; i < count; i++)
    sum += va_arg (ap, int);    /* Get the next argument value. */

  va_end (ap);                  /* Clean up. */
  return sum;
}

int main (void)
{
  /* This call prints 16. */
  printf ("%d\n", add_em_up (3, 5, 5, 6));

  /* This call prints 55. */
  printf ("%d\n", add_em_up (10, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10));

  return 0;
}
```
