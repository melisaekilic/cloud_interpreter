# Cloud - Mini Programming Language Interpreter

Cloud is a small interpreted programming language written in Python.
It was built as the course project for CS305 Programming Languages
at International University of Sarajevo, Spring 2026.

The goal of the project was to understand how a programming language
works behind the scenes by building the main parts of an interpreter:
lexical analysis, parsing, abstract syntax tree (AST) generation and execution.

This project was originally developed by a team of three students.
The version in the first commit is the one submitted for the course.

### My Parts

- `interpreter.py` - running the code, evaluating expressions and handling variables
- `main.py` - console interface, commands and the main loop
- Connecting the interpreter with the lexer and parser
- Contributed to the shared error system in `error.py`

## Features

- Integer and floating point numbers
- Variables and assignments
- Arithmetic operators `+ - * / ^`
- Unary operators `+x` and `-x`
- Comparison operators `<` and `>`
- Strings and string concatenation
- `print()` statements
- Parentheses and operator precedence
- Comments starting with `#`
- Syntax and runtime error messages with line and column information

## Planned Features

The following features are not supported yet and will be added in future updates.

- if statements
- while loops
- comparison operators `==`, `<=`, `>=`, `!=`
- boolean values and logical operators `&&`, `||`
- functions
- arrays
- escape characters in strings like `\n`

## Requirements

- Python 3 (developed and tested with Python 3.14)
- No external libraries

## How to Run

```bash
python3 main.py
```

When the program starts you will see this screen:

```
=======================================================================
                       ☁️   WELCOME TO CLOUD   ☁️
=======================================================================
Write your code line by line.
Press 'Enter' to go to the next line.
Type 'help' to see commands.
=======================================================================

Commands:
  run    -> run the current program
  clear  -> clear the whole program
  undo   -> remove the last entered line
  show   -> show the current program
  exit   -> close the interpreter
  help   -> show the commands menu
```

Write your code line by line and use the commands to run or edit it.
If an error happens the program is cleared automatically so you can start again.
After a successful run you can keep adding lines to the same program.

## Example

```
☁️ >>> x = 5
☁️ >>> y = 3
☁️ >>> z = (x + y) * (-10)
☁️ >>> print(z)
☁️ >>> print(x / z)
☁️ >>> print(2 ^ 3 ^ 2)
☁️ >>> print(x > y)
☁️ >>> run
```

Output:

```
[OUTPUT]
-80
-0.0625
512
True

Program finished. You can continue or start a new program with 'clear'.
```

When you type `exit` the program says `Ciao :)` and closes.

## Project Structure

```
├── main.py          # console interface and main loop
├── Lexer.py         # turns source code into tokens
├── parser.py        # recursive descent parser that builds the AST
├── ast_nodes.py     # AST node classes
├── interpreter.py   # walks the AST and runs the program
├── TokenType.py     # token type definitions
├── token_class.py   # Token class
├── error.py         # custom error classes
└── grammar.txt      # grammar of the language
```

## Error Types

| Error | When it happens |
|---|---|
| Illegal Character | an unsupported character like `@` or `$` is used |
| Invalid Number | a number has more than one dot like `2.3.4` |
| Missing Quote | a string is not closed with `"` |
| Syntax Error | the code does not follow the grammar |
| Runtime Error | division by zero or an undefined variable |
| String Error | an invalid operation on strings like `"a" - 1` |
