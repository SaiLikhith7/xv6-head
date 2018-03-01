# Implementing the 'hello' command
Write a program for xv6 that, when run, prints "Hello world" to the xv6 console. This can be broken up into a few steps:
1. Create a file in the xv6 directory named  hello.c
2. Put code you need to implement printing "Hello world" into  hello.c
3. Edit the file  Makefile , find the section  UPROGS  (which contains a list of programs to be
built), and add a line to tell it to build your Hello World program.
4. Run  make  to build xv6, including your new program (repeating steps 2 and 4 until you have compiling code)
5. Run  make   qemu  to launch xv6, and then type  hello  in the QEMU window. You should see "Hello world" be printed out.

### Hints:
1. In places where something asks for a file descriptor, you can use either an actual file descriptor (i.e., the return value of the  open  function), or one of the standard I/O descriptors: 0 is "standard input", 1 is "standard output", and 2 is "standard error". Writing to either 1 or 2 will result in something being printed to the screen.
2. The standard header files used by xv6 programs are " types.h " (to define some standard data types) and " user.h " (to declare some common functions). You can look at these files to see what code they contain and what functions they define.

# Implementing the 'head' command
Write a program that prints the first 10 lines of its input. If a filename is provided on the command line (i.e.,  head FILE ) then head should open it, read and print the first 10 lines, and then close it. If no filename is provided, head should read from standard input.You should also be able to invoke it without a file, and have it read from standard input.

The traditional UNIX head utility can print out a configurable number of lines from the start of a file. Implement this behavior in your version of  head  . The number of lines to be printed should be specified via a command line argument as  head -NUM FILE , for example  head -3 README  to print the first 3 lines of the file README. If the number of lines is not given (i.e., if the first argument does not start with - ), the number of lines to be printed should default to 10 as in the previous part.

### Hints:
1. Many aspects of this are similar to the wc program: both can read from standard input if no arguments are passed or read from a file if one is given on the command line. Reading its code will help you if you get stuck.
2. You can convert a string to an integer with the atoi function.
3. You may want to use pointer arithmetic (discussed in class in Lecture 2) to get a string
suitable for passing to  atoi .

