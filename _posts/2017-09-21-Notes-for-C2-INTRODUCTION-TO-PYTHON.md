---
layout: post
title:  "Notes for C2 INTRODUCTION TO PYTHON"
date: 2017-09-22 10:00:47 +0800
categories: notes
---

Here is my reading notes for Chapter 2 INTRODUCTION TO PYTHON in Prof. Guttag's book *Introduction to compuation and programming using Python*. Note that here are what I have been enlightened, rather than all the points in this chapter. (633 words)

### What are the dimensions along which different programs(thought not as different as their designers would have us believe) can be related?

* Low-level versus high-level

  > refers to whether we program using instructions and data objects at the level of the machine (e.g., move 64 bits of data from this location to that location) or whether we program using more abstract operations (e.g., pop up a menu on the screen) that have been provided by the language designer.

* General versus targeted to an application domain

  > refers to whether the primitive operations of the programming language are widely applicable or are fine-tuned to a domain.

* Interpreted versus compiled

  > refers to whether the sequence of instructions written by the programmer, called source code, is executed directly (by an interpreter) or whether it is first converted (by a compiler) into a sequence of machine-level primitive operations. (In the early days of computers, people had to write source code in a language that was very close to the machine code that could be directly interpreted by the computer hardware.)

### What are the weaknesses and strongthes of Python?

Not optimal for programs:

* that have high reliability constraints (e.g., Web service?)
* that are built and maintained by many people or over a long period of time (How about the open stack projects?)
* Both because of its weak static semantic checking

Good news:

* Easy to learn. designed to be interpreted, can provide the kind of runtime feedback to novice programmers.
* a large number of freely available libraries that interface to Python and provide useful extended functionality.

### What is the ulterior purpose, and forewarning about this book?

> We use Python as a vehicle to present concepts related to computational problem solving and thinking. 
>
> The language is presented in dribs and drabs, as needed for this ulterior purpose.

### What is a brief history of Python?

* 1990, introduced by Guido von Rossum
* 2000, version 2.0 marked a shift in the revolutionary path
* 2008, version 3.0 cleaned up many of the inconsistencies

## 2.1 The Basic Elements of Python

### What is the relationship of program, script, and shell?

> A Python **program**, sometimes called a **script**, is a sequence of definitions and commands. These definitions are evaluated and the commands are executed by the Python interpreter in something called the **shell**.

### What does "literal" mean?

> Literals of type int are written in the way we typically denote integers (e.g., -3 or 5 or 10002).

> Literals of type float always include a decimal point (e.g., 3.0 or 3.17 or -28.72).

The way of presenting a type, which is identical.

### Why call it `float` rather than `real`?

> Within the computer, values of type float are stored in the computer as floating point numbers. This representation, which is used by all modern programming languages, has many advantages. 
>
> However, under some situations it causes floating point arithmetic to behave in ways that are slightly different from arithmetic on real numbers. We discuss this in Section 3.4.

### How to pronounce `i%j`?

> i%j is the remainder when the int i is divided by the int j. It is typically pronounced “i mod j,” which is short for “i modulo j.”

### Does `i**j` both have to be integers?

No. 

> `i**j`is `i` raised to the power `j`. If either of them is a float, the result is a float.

``` Python
In [1]: 3**1.5
Out[1]: 5.196152422706632
```

### What does it mean by "bind", "associate", and "assign"?

An **assignment** statement must have the symbol `=`, which **associates** the name to the left of the = symbol with the object denoted by the expression to the right of the =. In this way, it **binds** the name to an object of certain type. 

### Do names matter?

Yes!

> In Python, a variable is just a name, nothing more. Remember this—it is important.

> Perhaps we shouldn’t have said, “a variable is just a name.” Despite what Juliet said, 9 names matter. Programming languages let us describe computations in a way that allows machines to execute them. This does not mean that only computers read programs.

> As you will soon discover, it’s not always easy to write programs that work correctly. Experienced programmers will confirm that they spend a great deal of time reading programs in an attempt to understand why they behave as they do. It is therefore of critical importance to write programs in such way that they are easy to read. **Apt** choice of variable names plays an important role in enhancing readability.
>
> Consider the two code fragments
> ``` Python
> a = 3.14159
> b = 11.2
> c = a*(b**2)
>
> pi = 3.14159
> diameter = 11.2
> area = pi*(diameter**2)
> ```
>
> As far as Python is concerned, they are not different. When executed, they will do the same thing. To a human reader, however, they are quite different. When we read the fragment on the left, there is no a *priori*(演绎) reason to suspect that anything is amiss. However, a quick glance at the code on the right should prompt us to be suspicious that something is wrong. Either the variable should have been named radius rather than diameter, or diameter should have been divided by 2.0 in the calculation of the area.

---

2017-09-22 above

---

