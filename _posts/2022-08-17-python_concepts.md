---
title: Python Basic Concepts
date: 2022-08-17 00:00:00 -500
categories: [Foundamentals]
tags: [Python] # TAG names should always be lowercase
img_path: /assets/posts/
---

Reference:

https://www.interviewbit.com/python-interview-questions/#pandas-in-python

## static vs dynamic languages

- Static: Data types are checked before execution
- Dynamic: Data types are checked during execution

## strongly vs weakly typed languages

- Strongly-typed: "1" + 2 will result in type error. Don't allow _type-coercion_
- Weakly-typed: "1" + 2 -> "12"

## scope in python

- local scope: available in the current function
- global scope: available throughout the code execution since their inception

## **init**

`__init__` is a constructor method in Python, and is automatically called to allocate memory when a new object/instance is created. All classes have a `__init__` method associated with them.

## decorators

`Decorators` are essentially functions that add functionality to an existing function, without changing the structure of the function itself. They are represented the `@decorator_name` in Python and are called in a bottom-up fashion. For example:

```python
# decorator function to convert to lowercase
def lowercase_decorator(function):
   def wrapper():
       func = function()
       string_lowercase = func.lower()
       return string_lowercase
   return wrapper
# decorator function to split words
def splitter_decorator(function):
   def wrapper():
       func = function()
       string_split = func.split()
       return string_split
   return wrapper
@splitter_decorator # this is executed next
@lowercase_decorator # this is executed first
def hello():
   return 'Hello World'
hello()   # output => [ 'hello' , 'world' ]
```

## lambda

Lambda is an anonymous function in Python, that can accept any number of arguments, but can only have a single expression.
