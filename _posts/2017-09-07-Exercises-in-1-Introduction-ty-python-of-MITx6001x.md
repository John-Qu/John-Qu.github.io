---
layout: post
title:  "Exercises in 1 Introduction to Python of MITx6001x"
date:   2017-09-07 11:20:11 +0800
categories: notes
---

This is a note of exercises in 1 Introduction to Python of MITx6001x course.

## Exercise 1 

> True or False? A computational mode of thinking means that everything can be viewed as a math problem involving numbers and formulas.
>
> * True correct 
> * False incorrect

Something cannot be turned into conputational problems. So I chose False. 

But this question is asking about **computational mode of thinking**, not computable problems.

## Exercise 2

> A recipe for deducing the square root involves guessing a starting value for y. Without another recipe to be told how to pick a starting number, the computer cannot generate one on its own.
>
> - True correct
> - False me

I thought the guessing is not important for this recipe, because it can start with any number. 

But this "any" is even unmechanical to computer, you must tell it how to decide one.

The "Show Answer" says:

> **Explanation:**
>
> Q3. The recipe in question, by itself, says to start with a guess. But in order to make this guess, we would need to have another recipe for how to guess! 
>
> Examples of such recipes include to use a fixed number, or a pseudorandom number generator, to give 2 examples. So by itself, the recipe in question is **not sufficient to be made into a real program**. 
>
> This question is indicative of how you should not assume you have more info than what the problem specifies.

## Exercise 6

2017-09-09

`- - 4`is

4, no error. Primitive, operator, primitive, can be interpreted smartly. Here, `- 4` can be treated as an integer as `-4`, so there is no syntax error.

## Exercise 10

`5/2 == 5/2.0` is True, because 4/2 returns 2.0, with `float` type.

`round(2.6)` is 3, with `int` type.