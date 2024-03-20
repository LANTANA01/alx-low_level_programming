0x1C. C - Makefiles.

Make is a utility that automatically builds executable programs and libraries from source code by reading files called Makefiles. Makefiles are a set of instructions that tell the Make utility how to compile and link a program.

Makefiles are used when there are multiple source files that need to be compiled and linked together to create an executable program. They are especially useful in large projects with many source files, as they automate the build process and ensure that only the necessary files are recompiled when changes are made.

Rules in a Makefile specify how to build a target file from its dependencies. They consist of a target, dependencies, and a recipe. The target is the file to be built, the dependencies are the files that the target depends on, and the recipe is the shell commands to execute in order to build the target.

Explicit rules specify exactly how to build a target file, while implicit rules specify a general recipe for building certain types of files. 

Some of the most common and useful rules in Makefiles include the default rule (usually called "all"), which specifies the default target to build when no target is specified, and the clean rule, which removes all generated files.

Variables in Makefiles are used to store values that can be used throughout the Makefile. They are set using the syntax variable_name = value and can be referenced using $(variable_name).

Overall, Makefiles are used to automate the build process for programs with multiple source files, and they provide a way to specify how to compile and link the program, as well as manage dependencies and other build-related tasks.

Requirements:

General:-

Allowed editors: vi, vim, emacs
OS: Ubuntu 20.04 LTS
Version of gcc: 9.3.0
Version of make: GNU Make 4.2.1
All your files should end with a new line
A README.md file, at the root of the folder of the project, is mandatory.
