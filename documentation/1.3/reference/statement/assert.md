---
layout: reference13
title_md: '`assert` statement'
tab: documentation
unique_id: docspage
author: Tom Bentley
doc_root: ../../..
---

# #{page.title_md}

The `assert` statement validates a given condition, throwing an `AssertionError` 
if the condition is not satisfied. An assertion may narrow the type of values as 
seen by subsequent statements.

## Usage 

The general form of the `assert` statement is

<!-- check:none -->
<!-- try: -->
    assert ( /* some conditions */ );

## Description

Unlike the `assert` statement in the Java programming language, `assert` in 
Ceylon cannot be disabled at runtime. It's important to know about bugs that
occur in running production systems, and assertions help us find out about
them.

### Execution

The condition (or conditions) in the `assert` statement are evaluated in the
order they occur. If they are all satisfied, then execution continues with the
statement immediately following the `assert`. Otherwise, an 
[`AssertionError`](#{site.urls.apidoc_1_3}/AssertionError.type.html) 
is thrown with information about the condition that was violated.

### Purpose

`assert` is used to make assertions:

- regarding program invariants which the programmer *knows* to be true, but 
  which cannot be proved to be true within the type system, or
- about preconditions required by an API, which cannot be enforced within
  the type system.

Failure of an assertion represents a bug in the program or misuse of the API.

Here's an example using the 
[`parseInteger()`](#{site.urls.apidoc_1_3}/index.html#parseInteger) 
function from `ceylon.language` which returns `Integer?`, forcing the caller 
to handle the possibility that the argument was not `String` representing 
a number:

<!-- try: -->
    value num = parseInteger("1");
    // before the assert statement num is of type Integer?
    assert (exists num);
    // after the assert statement num is of type Integer
    value plusOne = num + 1;
    
Here, `parseInteger()` is being called with a `String` literal which we 
*know* is a valid number. The type checker cannot know this, however, 
because it can only reason about types, not about what the `parseInteger()` 
function does for a particular input value. 

Here's a different example, from the internal implementation of that
function:

<!-- try: -->
    shared Integer? parseInteger(String string, Integer radix = 10) {
        assert (radix >= minRadix, radix <= maxRadix);
        ...
    }

Here, the assertion imposes a constraint upon the argument `radix`. If
a client calls `parseInteger()` with an illegal value for `radix`, then
the `AssertionError` will indicate this.

### Conditions

The conditions in an `assert` statement form a
[condition list](../conditions#condition_lists).

Any expression of type [`Boolean`](#{site.urls.apidoc_1_3}/Boolean.type.html) 
may be occur in the condition list of an `assert` statement. The `assert` 
statement also supports the use of typing conditions:

* [`is` conditions](../conditions/#_is_conditions), 
* [`exists` conditions](../conditions/#_exists_conditions), and
* [`nonempty` conditions](../conditions/#_nonempty_conditions).

These conditions narrow the type of a reference in the statements following 
the `assert`, and in later conditions in the condition list.

<!-- try: -->
    void printSqrt(Object x) {
        assert (is Float x, x >= 0.0);
        print(x^0.5);
    }

## See also

* The [`if` statement](../if) statement and the [`throw` statement](../throw)
  statement can be used together to achieve a similar effect.
* [Assertions](#{site.urls.spec_current}#assertions) in the Ceylon language 
  specification
