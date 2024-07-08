<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rounded&height=300&color=gradient&text=Work%20in%20Progress" />
</p>
<h1 align="center"> Hello! I'm sorry! Working on that! </h1>

Printf

	1. Introduction
	2. Context of Printf
	3. Understanding its usage
	4. Creating a printf from scratch
		1. Specifiers
		2. Variadic Functions
	5.Building an printf replica





About

	The main objective of this project is to replicate the printf function. It's quite important for two reasons: 1. Develop the ability to build your own tool, recreating fundamental functions like printf and 2. understand more deeply the concepts of variadic functions and more.

1. Introduction

	Printf is a standard function in many libraries that simply does formatted printing of text. :

	As defined in the GNU.org, printf prints the format string, interpreting ‘%’ directives and ‘\’ escapes to format numeric and string arguments in a way that is mostly similar to the C ‘printf’ function.

	In C, printf is a standard library function that formats text and writes it to standard output. The name, printf is short for print formatted where print refers to output to a printer although the functions are not limited to printer output.


2. Context of Printf

	2.1. Writing, writing and writing.

	The function to print is fundamental. Just like performing calculations, to print is a basic routine that every computer must perform. Therefore, the usage of printing is as old as the programming languages itself. Let's briefly discuss about the historical context of printf.

	Before talking about prints, let's see write().

	Write() is one of the most basic functions. The write function writes up to size bytes from buffer to the file with descriptor filedes. The data in buffer is not necessarily a character string and a null character is output like any other character. (Input and Output Primitives https://www.gnu.org/savannah-checkouts/gnu/libc/manual/html_node/I_002fO-Primitives.html#I_002fO-Primitives). 

	When I say that is basic, I mean it. You see, every programming language must perform 5 basic tasks. Those are: 

						1. Input - getting data and commands into the computer 
						2. Output - getting your results out of the computer
						3. Arithmetic - performing mathematical calculations on your data
						4. Conditional or looping - testing to see if a condition is true or false, and cycling through a set of instructions until some condition is met

	In this regard, write is one of those functions that perform input and output. It's basic because it works with fundamental parts of any computer architecture, just like the Input/Output (I/O), CPU and ALU. If you had anything else than the basic computer architecture you should perform the basic tasks, like calculating, reading and writing. And, of course, Printf is a type of a write function.

	The writing functions was always present in the routines of the programming languages since the early days. 

	2.2. Brief history of printf

	In the 1940s, early computers like ENIAC and UNIVAC did not have high-level programming languages. Programs were written in machine code or assembly language. Output was typically handled by hardware-specific instructions to control devices like printers or punched card readers.

	FORTRAN (Formula Translation) was introduced in 1957 it included basic I/O operations, such as PRINT for outputting data

	Even though  we could see printing function in early programming languages as FORTRAN in the 1950s, it was not the first programming language that implemented printf for the first time ever. Classically, Fortran output was dealt with using the write statement. The use of write(*,*) grew out of non-standard use of the  write statement in Fortran 66 which was introduced for device-independent sequential I/O. Fortran 77 introduced the print statement, which is more concise.  It is fairly easy to use, for example:


The first language to have an actual formatted-print function literally named printf was Algol 68, per the 1973 Revised Report (the original Report in 1968 used outf).

The format specification for Algol 68 owed IMO something to FORTRAN usage; elements were format directives unless they were specifically identified as literal strings - the inverse of C usage, if you see what I mean. For example, FORMAT f = $ "the number is " 3d $ (Dollar signs enclose a FORMAT denotation).

An honorary mention goes to BCPL, which had a writef or writes procedure (sources vary in their opinion, and the BCPL Reference Manual describes only the language, not any library), using a standard string for the format, rather than a specialized datatype (Algol [68) or statement type (FORTRAN).
