---
title: Python compile() built-in function - Python Cheatsheet
description: Compile the source into a code or AST object. Code objects can be executed by exec() or eval(). source can either be a normal string, a byte string, or an AST object. Refer to the ast module documentation for information on how to work with AST objects.
---

<base-title :title="frontmatter.title" :description="frontmatter.description">
Python compile() built-in function
</base-title>

<base-disclaimer>
  <base-disclaimer-title>
    From the <a target="_blank" href="https://docs.python.org/3/library/functions.html#compile">Python 3 documentation</a>
  </base-disclaimer-title>
  <base-disclaimer-content>
   Compile the source into a code or AST object. Code objects can be executed by exec() or eval(). source can either be a normal string, a byte string, or an AST object. Refer to the ast module documentation for information on how to work with AST objects.
  </base-disclaimer-content>
</base-disclaimer>

## Introduction

`compile()` is a built-in function in Python that allows you to compile Python source code into a code object that can be executed using the `exec()`, `eval()`, or `import` functions.

## Syntax

The syntax of the `compile()` function is as follows:

```python
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
```

- `source` - the source code to be compiled (a string, a bytes string, or an `ast.AST` object);
- `filename` - the name of the file that contains the source code (a string or `'<stdin>'` if the code is entered from the console);
- `mode` - the compilation mode (`'exec'`, `'eval'`, or `'single'`);
- `flags` - additional compilation flags (optional);
- `dont_inherit` - specifies whether to inherit compilation flags from the current environment (optional);
- `optimize` - the optimization level (optional).

Compilation modes determine how the compiled code will be used:

- `'exec'` - the compiled code represents a block of statements that will be executed as a program module or file;
- `'eval'` - the compiled code represents an expression that will be evaluated;
- `'single'` - the compiled code represents a block of statements that will be executed line by line.

## Examples

Here is an example of using `compile()` to compile and execute code:
```python
code = compile('print("Hello, World!")', '<string>', 'exec')
exec(code) # outputs "Hello, World!" to the console
```

Here is an example of using `compile()` to compile and evaluate an expression:
```python
code = compile('2 + 3', '<string>', 'eval')
result = eval(code)
print(result) # outputs 5 to the console
```

## Applications

The `compile()` function is used in various scenarios where dynamic code creation and execution is required. Some of the most common use cases for `compile()` include:

- Dynamically creating and executing code during program execution. For example, `compile()` can be used to compile code entered by a user and execute it in the context of the program.

- Using code from multiple sources, such as files, databases, or network sources. In this case, `compile()` can be used to compile and combine multiple sources into a single code object that can be executed in the program.

- Optimizing source code using additional compilation flags, such as `AST_OPTIMIZED` or `AST_FUTURE`.

- Analyzing source code using the `ast` module. The `ast` module allows parsing source code at the level of an abstract syntax tree (AST), which can then be compiled using `compile()`.
