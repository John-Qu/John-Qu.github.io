---
layout: post
title:  "Notes for C3 SOME SIMPLE NUMERICAL PROGRAMS"
date: 2017-09-26 16:43:18 +0800
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

