---
layout: post
title:  "Notes for C3 SOME SIMPLE NUMERICAL PROGRAMS"
date: 2017-09-27 16:43:18 +0800
categories: notes
---

Here is my reading notes for Chapter 3 SOME SIMPLE NUMERICAL PROGRAMS in Prof. Guttag's book *Introduction to compuation and programming using Python*. Note that here are what I have been enlightened, rather than all the points in this chapter. (458 words)

## 3.1 Exhaustive Enumeration

### Code using exhaustive enumeration to find the cube root:

```Python
x = int(input('Enter an integer: '))
ans = 0
while ans**3 < x:
    ans = ans + 1
if ans**3 != x:
    print(str(x) + ' is not a perfect cube')
else:
    if x < 0:
      ans = -ans
    print('Cube root of ' + str(x) + ' is ' + str(ans))
```

### **Decrementing function** 

is necessary whenever entering a loop, and its properties:

* Mapping a set of program variables into an integer;
* Entering the loop initiately with nonnegative value;
* Terminating the loop when its value no longer > 0; *(Ought it be `>= 0`, or more flexible?)*
* Decreasing every time through the loop.

Here, the decrementing function declares with `0` and "decreasing". We can view it as a distance, as `abs(x) - ans**3` in example above.

### It is not incredibly stupid to use exhaustive enumeration.

It is a variant of guess and check algorithm.

It enumerates all possibilities until check out the right answer or exhausts the space of possibilities and say no.

It is often the most practical way to solve a problem, because it is easy to implement and easy to understand.

It is fast enough for all practical purpose, with the speed of modern computers.

### My code as finger exercise to find root**pwr is equal to the integer entered by the user

```python
"""
Created at 2017-09-26 15:47:01
@author John Qu
"""

x = int(input('Enter an integer: '))
root = 2
pwr = 2
flag = False
while root**pwr <= abs(x):
    print("pwr is " + str(pwr))
    while root**pwr <= abs(x):
        print("root is " + str(root))
        if root**pwr == abs(x):
            print("Root "+str(root)+" to the power of " + str(pwr) + \
            " is equal to " + str(x))
            flag = True
            break
        root +=1
    pwr += 1
    root = 2
if not flag:
    print(str(x) + " is not a perfect integer's power")
```

1. `<=` is necessary.
2. Initiate with `root = 2` and `pwr = 2`is sementically valuable.
3. Using flag to control the two `print`, without co-appearing.
4. Just in line 21, rebind `root` to `2` is necessary, because there is a test in the outer `while` loop.
5. It is not beautiful.

The output is:

```Shell
$ python3 FE-3-1-enumberate.py
Enter an integer: 256
Root 16 to the power of 2 is equal to 256
Root 4 to the power of 4 is equal to 256
Root 2 to the power of 8 is equal to 256

$ python3 FE-3-1-enumberate.py
Enter an integer: 255
255 is not a perfect integer's power
```

---

2017-09-26 above

---

## 3.2 For Loops

### "Stylized"

> The `while` loops we have used so far are highly stylized. Each iterates over a sequence of integers.

> stylize |ˈstīlīz| 
>
> verb [with object] (usually as adjective stylized) 
>
> depict or treat in a mannered and nonrealistic style:
>
> * gracefully shaped vases decorated with stylized but recognizable white lilies(百合).

### `For` loop is a language mechanism

> Python provides a language mechanism, the for loop, that can be used to simplify programs containing this kind of iteration.
>
> ```python
> for variable in sequence: 
>   code block
> ```
>
> The variable following for is bound to the first value in the sequence, and the code block is executed. The variable is then assigned the second value in the sequence, and the code block is executed again. 
>
> The process continues until the sequence is exhausted or a break statement is executed within the code block.
>
> look at the `break` mechanism
>
> ```python
> #Find the cube root of a perfect cube
> x = int(raw_input('Enter an integer: ')) 
> for ans in range(0, abs(x)+1):
>     if ans**3 >= abs(x): 
>         break
> if ans**3 != abs(x):
>     print x, 'is not a perfect cube'
> else:
>     if x < 0:
>         ans = -ans
>     print 'Cube root of', x,'is', ans
> ```
>
> 

### `range` is a built-in function

It return s sequence containing an arithmetic progression. 

> The range function takes three integer arguments: start, stop, and  step.
>
> If the first argument is omitted it defaults to 0, and if the last argument (the step size) is omitted it defaults to 1. For example, range(0, 3) and range(3) both produce the sequence [0, 1, 2].

### `range`function in the line with `for` is evaluated once

> The range function in the line with for is evaluated just before the first iteration of the loop, and not reevaluated for subsequent iterations.
>
> ```python
> x=4
> for j in range(x):
>     for i in range(x): 
>         print i
> 	    x=2
> ```
>
> It prints
>
> ```shell
> 0 1 2 3 
> 0 1 
> 0 1 
> 0 1
> ```

### Finger exercise 3.2 sum with `for` loop

```python
""" Sum float numbers in a string with for loop
"""
s = '1.23,2.4,3.123'
sum = 0
for n in s.split(','):
    sum += float(n)
print("The sum of numbers in string '" + s + "' is " + str(sum) + '.')
```

It prints:

```shell
The sum of numbers in string '1.23,2.4,3.123' is 6.753.
```

## 3.3 Approximate Solution and Bisection Search

### approximation

> An answer that is close enough to the actual square root to be useful.

* It is an answer, answer to what?
* It is close enough, how close is enough?
* It is useful, for what use?

### By computer v.s. By hand

> Once again, we are using exhaustive enumeration.
>
> Notice that this method for finding the square root has nothing in common with the way of finding square roots using a pencil that you might have learned in middle school.

Diffrent tools, different ability, so different approaches.

That's not the difference between pen and pencil, but the speed and memory.

PS: What did we do when at middle school?

### No better

> Should we be disappointed that the program didn’t figure out that 25 is a perfect square and print 5? 
>
> No. The program did what it was intended to do. Though it would have been OK to print 5, doing so is no better than printing any value close enough to 5.

Remember: programs do what it was intended to do, and it meets the problem statement.

### What if step is too big?

> The problem is that our step size was too large, and the program skipped over all the suitable answers. Try making step equal to epsilon**3 and running the program. It will eventually find a suitable answer, but you might not have the patience to wait for it to do so.

Skip over all the suitable answers, with a rather big step.

### How to describe the process of looking up a word in a hard-copy dictionary?

> Exhaustive enumeration would, in principle, work. 
>
> You could start at the first word and examine each word until either you found a word starting with the sequence of letters or you ran out of words to examine. 
>
> If the dictionary contained n words, it would, on average, take n/2 probes to find the word. If the word were not in the dictionary, it would take n probes.

> Fortunately, the folks who publish dictionaries go to the trouble of putting the words in lexicographical(词典编纂顺序) order. 
>
> This allows us to open the book to a page where we think the word might lie (e.g., near the middle for words starting with the letter m). If the sequence of letters lexicographically precedes the first word on the page, we know to go backwards. If the sequence of letters follows the last word on the page, we know to go forwards. Otherwise, we check whether the sequence of letters matches a word on the page.

### What is the essence of the advantage of bisection search method?

> At each iteration the **size of the space to be searched** is cut in half. Because it divides the search space in half at each step, it is called a bisection search. Bisection search is a huge improvement over our earlier algorithm, which reduced the search space by only a small amount at each iteration.

It is a matter of the search space at each iteration.

### FE3-3-2: Constant good enough is not enough.

```python
"""
This is FE3-3-2. Find the cube root with bisection search
2017-09-28
"""
x = 27
epsilon = 0.01
numGuesses = 0
low = 0.0
ax = abs(x)
high = max(1.0, ax)
ans = (high + low)/2.0
while abs(ans**3 - ax) >= epsilon:
    print ('low =', low, 'high =', high, 'ans =', ans)
    numGuesses += 1
    if ans**3 < ax:
        low = ans
    else:
        high = ans
    ans = (high + low)/2.0
print('numGuesses =', numGuesses)
if x < 0:
    ans = -ans
print(ans, 'is close to square root of', x)
```

`abs(x)` is for negative case. `max(1.0, ax)` is for fractions.

with `x = 27`

```shell
low = 0.0 high = 27 ans = 13.5
low = 0.0 high = 13.5 ans = 6.75
low = 0.0 high = 6.75 ans = 3.375
low = 0.0 high = 3.375 ans = 1.6875
low = 1.6875 high = 3.375 ans = 2.53125
low = 2.53125 high = 3.375 ans = 2.953125
low = 2.953125 high = 3.375 ans = 3.1640625
low = 2.953125 high = 3.1640625 ans = 3.05859375
low = 2.953125 high = 3.05859375 ans = 3.005859375
low = 2.953125 high = 3.005859375 ans = 2.9794921875
low = 2.9794921875 high = 3.005859375 ans = 2.99267578125
low = 2.99267578125 high = 3.005859375 ans = 2.999267578125
low = 2.999267578125 high = 3.005859375 ans = 3.0025634765625
low = 2.999267578125 high = 3.0025634765625 ans = 3.00091552734375
numGuesses = 14
3.000091552734375 is close to square root of 27
```

With `x = 0.027`

```shell
low = 0.0 high = 1.0 ans = 0.5
low = 0.0 high = 0.5 ans = 0.25
low = 0.25 high = 0.5 ans = 0.375
numGuesses = 3
0.3125 is close to square root of 0.027
```

Constant test with `epsilon = 0.01` is not good enough for small numbers.

---

2017-09-28 above

---

