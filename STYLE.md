# Coding Style and Conventions

## Summary
This file is here to describe the overall coding style and conventions that SnekBot uses in it's Python code.
The code is very much like C/C++ Hungarian notation with some mixing of personal styles.

## Documentation
All the code ***MUST*** be documented. It's ***REQUIRED*** that every class/object and it's methods/members have comments describing how they work and why they exist.
It's also required that every sub-module (\*.py file) have a block comment at it's head describing who wrote it, and why they though it was necessary.
Beyond that, comments are encouraged, but not required when describing logic as long as the following rules are met:
* Variables are self-documenting (non of this `for i in var` crap).
* Code is neatly organized into logically blocks.
* Code adheres strictly to the function documentation/blueprint.

## Variable Naming
As mentioned above, many of the variable and functions will have a Hungarian style to them, with some tweaks as Hungarian notation can be very verbose. The standard rules in SnekBot are:
* Make sure to define the type of the variable in the name using a prefix
* Make sure to define the scope in the variable name if not local using a prefix
* As mentioned above, make sure the variable name is short and concise to avoidthemassivevariablename3000ultra

**EXCEPTION:** The only exception to these rules is when using a throw-away variable, such as a temporary variable holding data for a loop iteration. The variable **MUST** have a self-documenting name, but it can be all lowercase and a single word, such as "count", "iteration", or "index".

### Format
The basic format is:
`[scope]<data_type>(Variable_Name)`

For instance: `g_iCount` is a global integer (whole number) representing a count of some kind. Pretty easy and straight-forward.

| Data Type | Scope | Prefix characters | Capital? |
|:----------|:-----:|------------------:|:--------:|
| Boolean   | any | b | No |
| Character | any | c | No |
| Integer | any | i | No |
| Float   | any | f | No |
| String  | any | s | No |
| List    | any | v | No |
| Queue   | any | q | No |
| Qt Obj. | any | qt | No |
| Dict    | any | d | No |
| Except  | any | e | No |
| RegExp  | any | r | No |
| Tuple   | any | t | No |
| Mutex   | any | x | No |
| Class Member | any | m | No |
| ---- | Global | g_ | No |
| ---- | Module | l_ | No |

## Classes and objects
For classes and objects, they follow a similar naming convention, just minus the *scope* part:
`CMyClass` is a class while something like `MMyModule` is a module.

| Data Type | Scope | Prefix characters | Capital? |
|:----------|:-----:|------------------:|:--------:|
| Class   | any | C | Yes |
| Struct  | any | S | Yes |
| \*Module  | any | M | Yes |

\* Modules aren't strict, so forgetting to add that prefix is OK.

## Functions/Methods
Whenever you create a function/method, it should **ALWAYS** begin with a capital and be CamelCase, like so: `MyFunction()`.

## Constants
Constants need to stand out, this is done by simply making them all CAPS, like so: `MY_CONST`.

## Comments
All code needs to contain at least some comments describing what is happening. For 99% of the time, a single line comment that is clean and concise will suffice. However, when writing a comment for something like a class or design documentation, it's important that a Doxygen/JavaDoc style be followed. This style is well documented here: [Documenting the Code](http://www.doxygen.org/manual/docblocks.html)

The basic format you'll see is as follows:
```
'''!
\brief Basic one-line summation

\note Any warnings go here, things like thread-affinity for instance.

Big paragraph description goes here. All kinds of things can do into it.

\param[in|out] arg1 - Description of arg1
\param[in|out] arg2 - Description of arg2
\param[in|out] argN - Description of argN

\return [Data Type] - Description of what is returned and how to read it.
'''
```

Pretty simple and straight-forward.
