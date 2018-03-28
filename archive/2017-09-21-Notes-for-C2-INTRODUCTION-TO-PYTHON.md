---
layout: post
title:  "Notes for C2 INTRODUCTION TO PYTHON"
date: 2017-09-22 10:00:47 +0800
categories: notes
---

Here is my reading notes for Chapter 2 INTRODUCTION TO PYTHON in Prof. Guttag's book *Introduction to compuation and programming using Python*. Note that here are what I have been enlightened, rather than all the points in this chapter. (1351 words)

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

  Both because of its weak static semantic checking

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

## 2.1.1 Objects, Expressions, and Numerical Types

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

## 2.1.2 Variables and Assignment

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
> As far as Python is concerned, they are not different. When executed, they will do the same thing. To a human reader, however, they are quite different. When we read the fragment on the left, there is no **a *priori*(演绎) reason** to suspect that anything is amiss. However, a quick glance at the code on the right should prompt us to be suspicious that something is wrong. Either the variable should have been named radius rather than diameter, or diameter should have been divided by 2.0 in the calculation of the area.

---

2017-09-22 above

---

## 2.1.3 IDLE

### What does IDLE mean?

> IDE-Integrated Development Evironment
>
> IDLE - the IDE that comes as part of the standard Python installation package
>
> Allegedly, the name Python was chosen as a tribute(致敬) to the British comedy troupe Monty Python (Monty Python's Flying Circus 1969-1974). This leads one to think that the name IDLE is a pun(双关语) on Eric Idle, a member of the troupe. 

### What does IDLE provide?

> * A text editor, with syntax highlighting, autocompletion, and smart indentation;
> * A shell, with syntax highlighting, and
> * An integrated debugger.

## 2.2 Branching Programs

### Straight-line programs are downright boring.

### What is the advantage of Python's indentation approach?

> An advantage of the Python approach is that it ensures that the visual structure of a program is an accurate representation of the semantic structure of that program.

You see the structure as an oil painting, and that it is. Not that, you see and comprehend it one way, but acturely means other way.

### Note that `elif` is also a "nested" conditional.

```python
if x%2 == 0:
    if x%3 == 0:
        print 'Divisible by 2 and 3' 
    else:
        print 'Divisible by 2 and not by 3' 
elif x%3 == 0:
    print 'Divisible by 3 and not by 2'
```

`elif`can be rewrited as:

```python
else:
    if test conditional:
        block
```

### What does it say by saying "run in constant time"?

There is a roof,  no higher than that. A constant k exists, no more than k steps.

>  Consider, for example, writing a program to tally the votes in an election. It would be truly surprising if one could write a program that could do this in a time that was independent of the number of votes cast. In fact, one can prove that it is impossible to do so.

## 2.3 Strings and Input

### The operator "+" is said to be overloaded.

It has different meanings depending upon the types of the objects to which it is applied.

## 2.4 Iteration

### Will you hand-simulate the code?

> We constructed it by hand-simulating the code, i.e., we pretended to be a Python interpreter and executed the program using pencil and paper. Using pencil and paper might seem kind of quaint, but it is an excellent way to understand how a program behaves.

---

2017-09-25 above

---

