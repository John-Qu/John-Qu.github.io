---
layout: post
title:  "Notes for C1 GETTING STARTED"
date: 2017-09-13 11:09:04 +0800
categories: notes
---

Here is my reading notes for Chapter 1 GETTING STARTED in Prof. Guttag's book *Introduction to compuation and programming using Python*.

## What is the limitations of computaion in human history? And to what extend modern computers do?

> For most of human history, computation was limited by the speed of calculation of the human brain and the ability to record computational results with the human hand. This meant that only the smallest problems could be attacked computationally. 
>
> Even with the speed of modern computers, there are still problems that are beyond modern computational models (e.g., understanding climate change), but more and more problems are proving amenable to computational solution.

That means we can solve problems computationally, which cannot be imagined to be solved this way. That's amazing, a lot of new chance, e.g., natural languages.

> A computer does two things, and two things only: it performs calculations and it remembers the results of those calculations. But it does those two things extremely well.

Prof. Guttag arise two examples to illustrate the speed and storage abilities. But his example is not as imaginable as Prof. Grimson's. Let's take a look.

|               | Calculation Speed                        | Remember Results    |
| ------------- | ---------------------------------------- | ------------------- |
| Prof. Guttag  | Ball fell half meter, a billon instructions | One byte, one ounce |
| Prof. Grimson | Table light came, two instructions       | All of human books  |

We have sence with how fast light run, all the books' many, but no vivid sence with billon and 100GB-3,000,000 tons.

## Why does only the smallest problems could be attacked computationally in history?

> For most of human history, computation was limited by the speed of calculation of the human brain and the ability to record computational results with the human hand.

Human brain and human hand are the limitations of problem solving methods. Now, with high speed and huge memory, some unusual algorithms can be used, e.g.. Eucilid's GCD method.

The good news and big chance is:

> more and more problems are proving amenable to computational solution.

## What are two kind of knowledge?

imperative knowledge vs declarative knowledge

> **Declarative knowledge** is composed of statements of fact. For example, “the square root of x is a number y such that y*y = x.” This is a statement of fact. Unfortunately it doesn’t tell us how to find a square root.

> **Imperative knowledge** is “how to” knowledge, or recipes for deducing information.

> A bit more formally, an **algorithm** is a finite list of instructions that describe a computation that when executed on a provided set of inputs will proceed through a set of well-defined states and eventually produce an output.

The keywords here are:

* fact
* recipe
* deduce
* finite
* Set of inputs vs. an output
* Set of well-defined states

### What is the base of guess-and-check algorithm?

>  It is easy to check whether or not a guess is a good one.

## How does one capture the idea of a recipe in a mechanical process?

* fixed-program computers
  * to compute the trajectory of an artillery shell
  * First built in 1941, solve systems of linear equations
  * Alan Turing's bombe machine, breaking German Enigma code
  * a four-function calculator, doing basic arithmetic
* Stored-program computers
  * First: Manchester Mark 1
  * Create and instruction-set architecture
  * Detail the computation as a sequence of instructions
  * By treating those instructions in the same way as data, one can change the program, and can do so under program control.
  * Interpreter, the heart of computers

## What does the metaphor of recipe describe the relationship between a good chef and a good programmer?

With a fixed set of ingredients or primitive elements, both of them can produce an unbounded number of tasty dishes or useful programs.

> This is what makes programming such an amazing **endeavor**.

## What is Church-Turing thesis, and the halting problem?

> The Church-Turing thesis states that if a function is computable, a Turing Machine can be programmed to compute it.

> Turing showed that it is impossible to write a program that given an arbitrary program, call it P, prints true if and only if P will run forever. This is known as the halting problem.

Key words: computable, arbitrary program, run forever, halting

## What is Turing completeness?

> A programming language is said to be Turing complete if it can be used to simulate a universal Turing Machine. All modern programming languages are Turing complete.

In this sence, any modern programming languages are equal with respect to computational power.

## What is `primitive` in programming?

In [wikipedia](https://en.wikipedia.org/wiki/Primitive), primitive have many catagories, but

>  In computing, **language primitives**[*citation needed*] are the simplest elements available in a [programming language](https://en.wikipedia.org/wiki/Programming_language). A primitive is the smallest 'unit of processing' available to a programmer of a given machine, or can be an [atomic](https://en.wikipedia.org/wiki/Atomic_operation) element of an [expression](https://en.wikipedia.org/wiki/Expression_(programming)) in a language.
>
> Primitives are units with a **meaning**, i.e., a [semantic](https://en.wikipedia.org/wiki/Semantics_(computer_science)) value in the language. Thus they are different from [tokens](https://en.wikipedia.org/wiki/Token_(parser)) in a [parser](https://en.wikipedia.org/wiki/Parser), which are the minimal elements of [syntax](https://en.wikipedia.org/wiki/Syntax_(programming_languages)).

Note that primitive is not the same with token. [A token in Lexical analysis](https://en.wikipedia.org/wiki/Lexical_analysis#Token) has "token name" and "token values", like 

| Token name | Sample token values                      |
| ---------- | ---------------------------------------- |
| identifier | x, color, UP                             |
| keyword    | if, while, return                        |
| separator  | }, (, ;                                  |
| operator   | +, <, =                                  |
| literal    | true, 6.02e23, "music"                   |
| comment    | // must be negative, /* Retrieves user data */ |

But, primitives don't have names.

## What does each programming language have, by analogy with a nature language?

* The primitive contructs are words

  * Literals, e.g.,  `3.2, `, `'abc'.
  * Infix operators, e.g.,  `+`, `/`.

* The syntax describe which strings of words constitute well-formed sentences.

  * E.g., "Cat dog boy", "`3.2 3.2`"

* The static semantics defines which sentences are meaningful.

  * e.g., "I are big.", `3.2/'abc'`

  * Java do a lot of static semantic checking before allowing a program to be executed. C and Python do relatively less.

  * > When these errors are not detected, the behavior of a program is often unpredictable.

* The semantic defines the meaning of those sentences.

  * > In natural languages, the semantics of a sentence can be ambiguous. For example, the sentence “I cannot praise this student too highly,” can be either flattering or damning. Programming languages are designed so that each legal program has exactly one meaning.

  * > One doesn’t usually speak of a program as having a semantic error. If a program has no syntactic errors and no static semantic errors, it has a meaning, i.e., it has semantics.

    But the semantics means something other than what its creator think it means.

## What might happen if the program has an error, and behaves in an unintended way?

* It might crash, i.e., stop running and produce some sort of obvious indication that it has done so.
* Or it might keep running, and running, and running, and never stop.
* Or it might run to completion(竣工) and produce an answer that might, or might not, be correct.

> Each of these is bad, but the last of them is certainly the worst, When a program appears to be doing the right thing but isn’t, bad things can follow. Fortunes can be lost, patients can receive fatal doses of radiation therapy, airplanes can crash, etc.
>
> Whenever possible, programs should be written in such a way that when they don’t work properly, it is **self-evident**. We will discuss how to do this throughout the book.

Write test function?

---

2017-09-21 above

---

