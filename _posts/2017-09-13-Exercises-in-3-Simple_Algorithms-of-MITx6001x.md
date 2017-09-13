---
layout: post
title:  "Exercises in 3. Simple Algorithm of MITx6001x"
date:   2017-09-13 10:06:32 +0800
categories: notes
---

This is a note of exercises in 3. Simple Algorithm of MITx6001x course.

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





