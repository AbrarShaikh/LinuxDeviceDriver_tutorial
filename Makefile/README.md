# Makefile
- A Makefile is a script used by the make build automation tool to compile and build applications.
- It defines the relationships between source files, object files, and executable files, specifying how to create the final program.
1. ```Targets```: These are typically the files you want to generate. Targets can be executable files, object files, or even labels for groups of commands (called "phony targets").
2. ```Dependencies```: Files that a target depends on. If any dependency has changed, the target needs to be rebuilt.
3. ```Commands```: The shell commands used to build the target. These commands are executed if the target is out of date with respect to its dependencies.
### basic syntax 
```C
target: dependencies;
    commands
```
Example
```C
# Compiler
CC = gcc

# Compiler flags
CFLAGS = -Wall -g

# Target executable
TARGET = myprogram

# Source files
SRCS = main.c foo.c

# Object files
OBJS = main.o foo.o

# Rule to build the target
$(TARGET): $(OBJS)
    $(CC) $(CFLAGS) -o $(TARGET) $(OBJS)

# Rule to build the object files
%.o: %.c
    $(CC) $(CFLAGS) -c $< -o $@

# Clean up
clean:
    rm -f $(TARGET) $(OBJS)
```
### Variables:
- CC sets the compiler to gcc.
- CFLAGS sets the compiler flags, such as ```-Wall``` for all __warnings__ and ```-g``` for __debugging__ information.
- TARGET specifies the name of the output executable.
- SRCS lists the source files.
- OBJS lists the object files.
### Rules:
The first rule specifies how to build the final target myprogram from object files.
### Phony Targets:
- This ensures that make clean always runs the clean rule, even if a file named clean exists.
```C
.PHONY: clean
clean:
    rm -f $(TARGET) $(OBJS)
```

##  Features
1. Automatic Variables:
- $@ represents the target name.
- $< represents the first dependency.
- $^ represents all dependencies.

2. Pattern Rules:
- % is a wildcard for pattern matching.
For example, %.o: %.c means any .o file depends on the corresponding .c file.

3. Special Built-in Targets:
- .PHONY: Declares phony targets to avoid conflicts with files of the same name.
- .SUFFIXES: Specifies suffixes for implicit rules.

4. Conditional Statements:
- ifeq, ifneq, ifdef, ifndef for conditional parts of the Makefile.
