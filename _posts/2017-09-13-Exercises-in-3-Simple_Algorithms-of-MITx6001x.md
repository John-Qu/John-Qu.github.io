---
layout: post
title:  "Exercises in 3. Simple Algorithm of MITx6001x"
date:   2017-09-14 15:35:53 +0800
categories: notes
---

This is a note of exercises in [3. Simple Algorithm of MITx6001x course](https://courses.edx.org/courses/course-v1:MITx+6.00.1x+2T2017_2/courseware/0de4fecc5a9a4749923133fcf4de181f/62f08cc899344863a1ab678aee506dec/?activate_block_id=block-v1%3AMITx%2B6.00.1x%2B2T2017_2%2Btype%40sequential%2Bblock%4062f08cc899344863a1ab678aee506dec).

## Exercise 2 

```python
x = 25
epsilon = 0.01
step = 0.1
guess = 0.0

while guess <= x:
    if abs(guess**2 -x) < epsilon:
        break
    else:
        guess += step

if abs(guess**2 - x) >= epsilon:
    print('failed')
else:
    print('succeeded: ' + str(guess))
```

It's correct. The `while` test, which garantees when steping-over problem happens the loop won't run infinitely, could be terminated by the `epsilon` test.

But if the `while` loop is coding as:

```Python
while guess <= x:
    if abs(guess**2 -x) >= epsilon:
        guess += step
```

The guess might step onto the appropriate value, which is 5.0 here, but the `while` loop will never terminate, for that `guess` is always smaller than `x`.

Note that, the outer test is a garantee, the inner check is for incrementation. If it change position like this:

```Python
while abs(guess**2-x) >= epsilon:
    if guess <= x:
        guess += step
    else:
        break
```

With big `step`, small `epsilon`, and eccentric x(non perfect square),  it will step over the better approximate value as well.

## Exercise: guess my number

2017-09-14

My code:

```Python
"""
Created on Thu Sep 14 14:39:04 2017

@author: johnqu
"""

print("Please think of a number between 0 and 100!")
low = 0
high = 100
while True:
    guess  = int((low + high) / 2.0)
    print("Is your secret number " + str(guess) + "?")
    judge  = input("Enter 'h' to indicate the guess is too high. Enter 'l' to indicate the guess is too low. Enter 'c' to indicate I guessed correctly. ")
    while judge not in "hlc":
        print("Sorry, I did not understand your input.")
        print("Is your secret number " + str(guess) + "?")
        judge  = input("Enter 'h' to indicate the guess is too high. Enter 'l' to indicate the guess is too low. Enter 'c' to indicate I guessed correctly. ")
        
    if judge == "l":
        low = guess
    elif judge == "h":
        high = guess
    else:
        print("Game over. Your secret number was:", guess)
        break
```

His code:

```Python
print("Please think of a number between 0 and 100!")

# At the start the highest the number could be is 100 and the lowest is 0.
hi = 100
lo = 0
guessed = False

# Loop until we guess it correctly
while not guessed:
    # Bisection search: guess the midpoint between our current high and low guesses
    guess = (hi + lo)//2
    print("Is your secret number " + str(guess)+ "?")
    user_inp = input("Enter 'h' to indicate the guess is too high. Enter 'l' to indicate the guess is too low. Enter 'c' to indicate I guessed correctly. ")

    if user_inp == 'c':
        # We got it right!
        guessed = True
    elif user_inp == 'h':
        # Guess was too high. So make the current guess the highest possible guess.
        hi = guess
    elif user_inp == 'l':
        # Guess was too low. So make the current guess the lowest possible guess.
        lo = guess
    else:
        print("Sorry, I did not understand your input.")

print('Game over. Your secret number was: ' + str(guess))
```

### Better:

* His `hi` and `lo` have the same length.
* His `//2` means my `int(a/b)`, not my former `round(a/b.0)`. Round returns weird result in web processing - a number bigger than correct.
* He let `if` checking's result affect while test with `guessed` flag. I used `break`. Maybe the two are the same.

### Should:

* My inner `while` loop checking in not necessary.

### Question:

* How can I wrap the `input`'s string, without those annoying spaces? I don't think this question vital, so I think it's better to leave it here. I might encounter a code example soon, which obey python guide.

## Exercise 3

> True or False? The internal representation of the decimal number 1/10 = 0.1 requires an infinite number of digits.

It's true. Because 1/10 cannot be represented as sum(int/2**k).

> After many computations, you get two floating numbers stored in variables `a` and `b`. Your code compares the numbers with `a == b`.

Not "always", not "never", it is "sometimes" program can interpret it well, depending on whether the program language's designer.

