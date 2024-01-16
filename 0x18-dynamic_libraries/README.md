0x18-dynamic_libraries

Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

General
What is a dynamic library, how does it work, how to create one, and how to use it
What is the environment variable $LD_LIBRARY_PATH and how to use it
What are the differences between static and shared libraries
Basic usage nm, ldd, ldconfig

In C programming, dynamic libraries, also known as shared libraries, are compiled, reusable chunks of code that can be loaded and linked to a program at either compile-time or runtime. Unlike static libraries, which are linked to the program at compile-time, dynamic libraries are linked at runtime.

Dynamic libraries offer several advantages, including:

Code Reusability: Dynamic libraries allow multiple programs to share the same code, reducing redundancy and saving disk space.

Upgradability: If a bug is fixed or an enhancement is made to a dynamic library, all programs using that library can benefit from the update without recompiling.

Reduced Memory Usage: Dynamic linking allows multiple programs to share a single copy of the library in memory, which can lead to lower overall memory usage compared to static linking.

Easier Maintenance: Changes to a dynamic library don't require recompiling the entire program. This makes maintenance and updates more straightforward.

To use a dynamic library in a C program, you typically include a header file that contains the function prototypes and link the program with the dynamic library during compilation or load the library dynamically at runtime using functions like dlopen() and dlsym().


Requirements

C

Allowed editors: vi, vim, emacs
All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
All your files should end with a new line
A README.md file, at the root of the folder of the project is mandatory
Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
You are not allowed to use global variables
No more than 5 functions per file
You are not allowed to use the standard library. Any use of functions like printf, puts, etc… is forbidden
You are allowed to use _putchar
You don’t have to push _putchar.c, we will use our file. If you do it won’t be taken into account
In the following examples, the main.c files are shown as examples. You can use them to test your functions, but you don’t have to push them to your repo (if you do we won’t take them into account). We will use our own main.c files at compilation. Our main.c files might be different from the one shown in the examples
The prototypes of all your functions and the prototype of the function _putchar should be included in your header file called main.h
Don’t forget to push your header file


Bash

Allowed editors: vi, vim, emacs
All your scripts will be tested on Ubuntu 20.04 LTS
All your files should end with a new line (why?)
The first line of all your files should be exactly #!/bin/bash
A README.md file, at the root of the folder of the project, describing what each script is doing
All your files must be executable
