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
		<li>Specifiers</li>
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

