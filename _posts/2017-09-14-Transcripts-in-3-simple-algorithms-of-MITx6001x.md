---
layout: post
title:  "Transcripts in 1 Introducion to Python of MITx6001x"
date:   2017-09-08 11:45:45 +0800
categories: notes
---

This is a note of MIT6001x 3. Simple Algorithms. From now on, I would not insert course slides into transcripts, because I find it a bit annoying and time consuming.

## Video: So Far...

...
In the last lecture, we added looping variants.
We had for loops, we had while loops,
we had the notion of iteration.
We used that to start generating some examples of guess
and check algorithms.
In this lecture, we're going to go back to that idea
but it.
And we're going to add in another kind
of data type, a string.
We talked about it a little bit earlier on,
but we're going to use it to actually
look at ways to generate algorithms
that can start to do some more interesting kinds of things.
Just to review, I want to remind you
what we did inside of loops.
Here's an example of some code that's
going to compute a square root of something.
And it does it by running through a loop.
As we've done before, it's going to set up
an initial value, which it gets here by inputting something
that enters an integer.
And then it's going to run through a little while loop
where it does guess and check.
It keeps trying different versions of answers,
starting at 0, then 1, then 2, going on
until it sees whether that answer squared
is bigger than or equal to x.
Once it gets to that point, it checks
to see if the square is equal to x, in which case
it prints out that it's found the cube root.
And if not, it tells me that it's not a perfect cube.
And just depending on whether it was a positive or negative
thing, it gives me a little bit of additional information.
You can look through the code.
I'm not going to run it.
What I want you to see is that idea of guess and check.
I generate values for answer until I get to a point
where either I'm done and I have the answer
or I've gone too far.
And again, as before, I've got something
where I'm setting up the variable outside,
and I'm changing the variable inside
with a test that depends on it.
We're going to use that idea as we generalize,
but I want to remind you of what loops do.
And as before, I don't need to do that actual version
of answer equal answer plus 1, I could use plus equal
as a variation of it.
We also talked about strings earlier,
and I just want to remind you of those,
because we're going to use them in this lecture as well.
Think of strings as a sequence of characters, in fact,
case-sensitive characters for letters.
It could be lower case or upper case.
As with numbers, I can compare them.
I can say if two strings are equal while using
the double equal sign, I can use greater than or less
than using lexicographic order to decide
if two strings are greater than or less than each other.
Length can give me the number of things in the string
and, as we saw before, we can use square brackets
to do indexing into a string.
We can get the zeroth element.
Remember, it starts at 0, the first element,
the second element.
And if I have a string three long,
and I try and get something three or bigger,
it's going to complain, telling me
that I've tried to access beyond the end of the string.
We also saw slicing in strings.
This lets us go into a string of pull out pieces of the string.
And here we saw we can specify a start point, a stop
point, and how many steps to take as we do the accessing.
And that lets us pull out different elements
out of a string.
One unusual thing we haven't seen
before is if the step is negative 1,
we actually access the string in reverse order.
There it is right there.
Otherwise, if we say for example start with the element 3,
it says 0.
0, 1, 2, 3.
So I start here, and I stop just before the sixth one.
So 3, 4, 5.
I'm going to pull that out, which gives me
the piece that I wanted there.
One last thing about strings is that they are
what we call an immutable type.
You can't change them.
They can't be modified.
And to see that, let me do a little example.
I've shown it on the slide, but let me actually
type it in over here.

I'm going to define the name as to be the string hello.
If I print out s, it gives me back.
If I say what's the type of s, it
tells me that it's a string, which is great.
I can certainly index it by saying
give me the zeroth element of s.
But if I wanted to change the zeroth element of s,
for example, saying I want to have the zeroth element of s
be the character y.
It's going to complain.
I can't go in and change a piece of s.
We're going to see other structures where we can do
that that are called mutable.
Strings are not.
I can't say I want the zeroth element of s to be y.
I can change it, but I have to redefine it.
So I could say let s be the character y plus the rest of s
starting at 1.
And I could, in fact, say until I get to the length of s,
or I can just say 1 all the way onto the end.
And now if I look at s, it's yellow, misspelled for yellow.
Point is, I've now changed the definition for s.
So I can't change it individually,
I have to redefine s.
And that's why I say strings are immutable.
One of the things I would suggest to you
is if you're not sure what a command does, look it up or try
it out yourself.
That will give you a sense of the different things you can do
with strings as you move along.
And here, just to remind you, s was initially bound to hello.
When I do the last call, I'm changing that binding
and redefining it to be a changed
new version of a string.
The original string is still stuck in memory.
It's just floating around.
I can't access it anymore.
Finally, remember for loops, the quick recap.
We have that idea of having a loop variable that
iterates over a set of values.
And we can either do that with simple things
like the range shown here, which is going to go from 0 up to 4,
but I could also do it starting at 4, going up to 8.
Expressions inside the loop are going
to be executed for each value of the variable that I use.
And so range is a nice way to iterate over numbers,
but a loop, a for loop variable, can iterate over any set
of values, not just numbers.
And so for example, I could loop over strings.
That sounds kind of neat.
So here's a simple little piece of code.
I've defined s to be a string, the first set of letters
in the alphabet.
And I can now write a for loop that
says loop for the index over the range of the length of s.
Boy, that's a lot of words.
Let's say it a little bit better.
It says, I'm going to see how long is s,
and then I'm going to use range to generate the integers from 0
up to the length of s minus 1.
I'm going to call that index, and then
I could run through a loop that says
if the element of s at that point is either an i or a u,
I'm going to print out a little piece of information.
No big deal.
That just looks like a normal loop over integers.
But I could also write it this way.
I could say loop for character in s.
And that's kind of cool. s is something we call an iterable.
It says I can actually write a loop that
lets characters start with the first element of s,
and then the second element of s,
and then the third element of s, doing the same kind of test
as I move along.
And it will do this until it runs out
of characters in s, in which case it will exit from the loop
and move on to other kinds of things.
That second piece of code is much cleaner.
It's easier to see what I'm doing.
I'm looping for all the characters
in a string as opposed to saying I'm
looping for an index over all the indices into the string.
And that's one of the nice things about both strings
and especially about loops.
I can iterate over anything where
I can successively enumerate each
of the elements of that piece.
So now I've got strings as something
which I can use as parts of loops, and that's really nice.
Let me give you one last example, sort of a fun example.
I'm going to set up a little loop that is going to run over
basically a set of words.
And what is it going to do inside of here?
I've got a little while loop here
that says as long as-- sorry, rephrase that.
I'm going to input a word based on some input I give there.
And what it's going to do is it's
going to loop over all of the things inside of the word,
basically saying if the character in the word
is in a special set of characters,
I'm going to print out something based on that.
If it's not, I'm going to print out something different
based on that.
And then I'm going to increment i, and I'm going to keep going.
So, again, it's a while loop, but I'm using the character
inside there to loop over particular elements
of a string.
Let's see what this does.
So here's the code.
And if I load it into my environment,
says I'm going to cheer for you.
Give me a word.
So we'll give it the best word I know,
which is-- let me just get it over here-- which is MIT.
And it says how enthusiastic are you about MIT?
Well, I like MIT a lot, so I'm going to give it a 10
out of 10.
And it says-- I'm not going to repeat it all,
but give me an M, M. Give me an I,
I. Give me a T, T What does that spell?
And it prints it all out.
All right.
It's a lame example, but you know what?
I'm from MIT.
I like it.
What I want you to see is how I'm
looping over, especially here, in this place right in here.
I'm using the loop over a set of strings
in order to be able to decide what I'm going to do.
And why am I doing that?
Because if it's something that is a vowel,
I don't want to say give me a A. I want to say give me
an A. If it's something like an M that we pronounce that way,
I want to say give me an M, whereas in the other cases,
I want to say just give me a C, give me a D. OK.
Cute example.
Key point, I've now got two different loops going on here.
The outer one is walking through each
of the elements of the word.
That's this one right here.
And that's just doing the standard thing
where I've set an iteration variable outside right there.
I'm changing it inside the loop, but in the loop
I've got another one, which is right here where
I'm looping over all of the elements of a string.
I can do it either way, and that works out really well.
On that cheery note, we're going to move on to another topic.

## Video: Approximate Solutions

...
We've been using exhaustive algorithms, guess and check
algorithms to solve some simple numerical problems.
But if you think about it, they've
all been doing things with integers
where there is a finite number of choices
that we have to check.
And that makes sense.
I can certainly run through all of them
until I get to either the right answer
or determined there isn't a possible answer.
But now, suppose we want to find, say,
the square root or the cube root of any non-negative number.
Could be an integer, it could be a float,
it could be any number.
I can't generate all possible guesses.
They're infinite.
So I can't, in this case, guarantee an exact answer,
but I could come close.
Now what I just want to do is try and find
a guess that's close enough to the cube
root or the square root of the thing I'm looking for.
I can still use that notion of exhaustive enumeration.
But I'm going to now have to pick examples
where I take small steps in order to generate the guess
and check to see if I'm close enough.
Let's see what that might look like.
Here, the idea is I have to define
what's a good enough solution.
So I want to start with a guess, say, one.
I want to check to see if that's close enough.
If it isn't, I'm going to change it by a tiny amount, say 1.001.
Check that one.
Then 1.002 and keep doing that.
So I need to increment by some small value as I go along.
But I also have to define, what does it
mean to get close enough?
It won't be exactly the same because I'm not going
to be able to guarantee that.
So here, I'm going to use, in the case
of cube root, something that tells me
whether I'm close enough.
By looking at-- sorry, the guess cubed,
take the absolute value in case it's negative,
and look at the difference between that
and cubed to see if it's less than
or equal to a small number.
And if it is, I'm going to say I'm close enough
and I'm going to stop.
One of the tricks here is that when I have these small values,
I'm going to have to be careful.
If I make them really small, I'll
make sure I find a really good guess
but it's going to slow the program down.
If I make them really large, I might actually miss the answer.
And similarly, when I decide how close I
want to get with epsilon, if I make epsilon big,
I'm going to make it easier to find an answer,
but I might get a less accurate answer.
And so I have to think carefully about how I do both of those.
But let's look at that idea to see
how I can still use the idea of guess and check, but now
with things that could compute the cube root of anything.
So here's an example.
I'm going to start off with some value for the thing I'm
trying to find the cube of.
27 is going to be an easy one.
I'm going to set up some initial values.
Epsilon is going to be something that tells me how close I
want to get to the answer.
Guess is where I'm going to start.
And increments, the size in which
I'm going to increase my guess as I move along.
And just to keep track of it, I'm
going to set up another variable called number of guesses.
I'm going to use that to keep track of how many times do I go
through the loop as I do this.
And then what does this code do?
It says while the difference between the cube or the guess
cubed and the thing I'm trying to find the cubed root of,
while that difference is still bigger than epsilon,
I'm going to keep going by incrementing guess
by increment.
There's that plus equal that I've used before.
And changing number of guesses by one.
Saying I've done another guess and keep going.
I'm going to keep doing that until I get to something where
the difference between guess cubed and cubed
is small enough.
And at that point, I'm going to stop.
And I'm going to return both how many guesses did I run
and some information about did I find the right answer.
Let's see what happens if I run that.
So there's a piece of code.
Let me start with 27, which is the thing I had before.
And if I load that and run it, it
gives me, oh, not quite the answer I expected.
It says 2.997000000001906 is close to the cube root of 27.
And that's true.
We're going to see us in a little bit
why it doesn't just give me 3.
It gives me this funny answer in there.
But you're going to also see that it
took almost 30,000 times through the loop before it got to that.
Why?
Because I started with a very simple answer, zero.
That wasn't close enough.
Then I went to 0.0001, then to 0.0002.
And you can see I'm going to have to do a lot of things
until I get to something that's going to give me a good guess.
Now, I could pick another example.
Let's make it 29, which I know is not a cubed root.
Let's see what happens if I do that.
It's not a perfect cube, but in this case it found it.
That's actually nice.
In the previous case, I could only
find things that were cube root of integers.
And now I've got something where the cube root isn't an integer,
but I can still find it.
This took almost 31,000 times through the loop.
So I could say, you know what?
I want to use something where I'm going
to step a little more broadly.
Let's step every thousandth of a step
rather than every ten thousandth of a step.
And now if I run it, OK, I get a little bit different guess.
But it only took 3,000 trials through it.
And if I change it to say the increment should
be in hundreds, I can run that.
And if I do that-- whoops, sorry.
It decided it didn't like that.
Let me think about why it didn't like that.
Ah, what's happened here?
It's off in an infinite loop.
And the reason it's off in an infinite loop
is because I'm checking only to see if I get to a place
where it's close enough.
I've actually gone right past the cube root,
and it's still running.
So I need to stop this.
And I'm going to interrupt it to hold it back.
That's something I need to fix.
So if I go back to a little bit better increment
here and rerun it, I get back to the thing I wanted to have.
OK, how would I fix that?
I need to make sure that the guess isn't too big.
If you think, and I'm going to go back to where I was,
with this test, it simply says when guess cube minus cube,
as long as it's bigger than epsilon,
I'm going to keep going through the loop.
If my step is too big, I could try something just below cubed
but not have it work.
And then go past cube and keep going further and further on.
That says I need to make a change here,
so I want to make sure that my guess is still small enough.
And if I make that small change, which
I'm going to do over here, and guess less than
or equal to cube, I should be in a little bit better shape.
I can still run the same one.
But now, if I change increment to tense, run that.
Ah, it gave me a solution.
Not a very good one.
It basically says I didn't find a solution.
But at least I didn't keep running forever.
What was the point of doing this?
It's not to try and trick you.
It's to remind you that as you make changes to the code,
you need to think about the consequences.
And this was one where my test wasn't
capturing all of the cases.
So what can I say about this particular algorithm?
Step could be any small number.
If it's too small, it's going to take a long time.
But as we just saw, if it's too large and I'm not careful,
it could skip over the answer without getting close enough.
At least in this case I stopped, rather than running forever.
In general, it's going to take x divided by step number times
through the code to find a solution.
And so clearly, as I make steps smaller and smaller,
it's going to increase the number of steps.
And I'd like to find a more efficient way
to solving this problem.

## Video: Bisection Search

...
We've been using exhaustive algorithms, guess and check
algorithms.
When we got integers we saw.
That's nice, because there's only
going to be a finite number of solutions.
But we won't be able to find, say,
square root of cube roots of numbers
where that isn't a perfect square or a perfect cube.
We've generalized that to look at something
that does a different kind of guess
and check where we take incremental steps,
still enumerating all the possibilities
within the resolution of that step,
trying to find a solution.
And we saw that that either means we take very small steps,
and we take a long time.
Or if we take larger steps, we might miss the solution.
And I suggest that we want to find a more effective way
of doing that.
So here's an example of that and a wonderful tool
that we're going to see a lot as we go through the course.
It's called bisection search.

![14](https://ws2.sinaimg.cn/large/006tKfTcgy1fjj2rgu7oej311w0se418.jpg)

Let's think about a square root.
One of the things we know about the square root of a number
is that it lies between 1 and that number
if that number is bigger than or equal to 1.
We'll do fractions in a second.
So square root of 25 lies somewhere, we know,
between 1 and 25.
Here's the basic idea.
Rather than trying everything starting at 1
and taking small steps, suppose we
pick a number in the middle between 1 and say 25?
12 and 1/2.
If we're lucky, that's going to be close enough.
Well, it's probably not close enough in this case.
We know where it is, but it's a nice start.

![15](https://ws2.sinaimg.cn/large/006tKfTcgy1fjj2rfmtwpj311s0siq69.jpg)

But we can take that idea and generalize it.
If it's not close enough, then we can ask,
well, was the guess too big or too small?
And in particular, if that guess g squared is bigger than x,
we know it's too big.
So what can we say?
Well, we know that the answer has to lie below g,
and that's really cool, because it says all of this stuff here,
throw it away.
I don't have to look there.
I know that the answer has to be somewhere between 1 and g.
Do the same thing.
Pick something halfway between.
That's my new guess.
Try it again.
If it's close enough, I'm done.
If it's not, ask the same question.
And for example, in this case, if g squared is less than x,
then we know it was too small.
So we can throw that stuff away and only focus on this portion.
And, again, pick something in the middle and keep trying.
You can already see why this is going
to be really nice, because on each step,
I'm throwing away half of the things
that I don't have to look at anymore.
And that's going to let me hopefully very quickly zero in
on finding the right solution.
That's a wonderful idea.
It's called bisection search, and we're going to use it.
So what do we say at each stage?
I'm losing half the values.
Really cool.
Let's see what happens if we wanted
to actually make code for it.

![16](https://ws3.sinaimg.cn/large/006tKfTcgy1fjj2rcjb6rj311m0sejur.jpg)

So this is a little bit of a busy slide,
but we'll walk through it.
This is an example of computing square root using that example
of a bisection search.
I'm going to start off just giving it the thing I'm
going to look for.
x will be 25.
That's the thing I'm going to use as the root.
Again, I'm going to pick something
that I'm going to use to tell how close I am.
And I'm also going to keep track of how often do I actually
run through the loop just to compare it
to what we saw earlier.
I need to set a low value and a high value,
the range in which I'm going to look.
Initially, that is 1 to the number itself.
And then I'm going to make an initial guess, which is halfway
in between.
Just high plus low divided by 2.
And then I run through one of those nice little loops.
What do I do?
I say if the difference between the answer
squared and x is bigger than or equal to epsilon,
I'm not close enough.
And in that case, I'm going to print out some information,
increase the number of guesses by 1.
And then do what I just did, which
is if answer is too small, that is,
answer squared is less than x, then
I can change the low part of the range to move up to answer.
And if answer is too big, I can change the high part
of the range down to answer.
As I did before, I start out here.
If answer was too big, I changed the high arrange
to bring it down into there.
If answer is too small, I bring the low range down into there,
and I keep sorting it down until I get into something
that's reasonable.
This algorithm just captured that idea I just described.
So let's try it out We'll do it with 25.

Here's a bisection search on square root.
And if I run this code, wow, it actually
got there very quickly.
It did it in 13 guesses.
I'll remind you, in the previous case we took
30,000 guesses to get there.
I don't want to print all that out on my screen.
And notice how quickly it zeroes in.
It starts off with low 0 and high 25.
And then it says low 0 and high 12 and 1/2, half and then low
0 and high 6 and 1/2.
You can see, if you look at the printout,
how quickly it narrows in on the range.
That's really cool.

![17](https://ws1.sinaimg.cn/large/006tKfTcgy1fjj2rb95i5j311c0scwi3.jpg)

Do the same thing with cube root.
I can do exactly the same idea.
This is almost exactly the same code.
The only difference is I'm using guess cubed
rather than guess squared.
And I'm going to keep track of otherwise exactly
the same information.
And let's compare that.
If I go over and pull up my cube root example,
we'll start with 27.
Again, I'll remind you that in this case
I was doing 30,000 checks to deal with this.
Now I run it, and in 14 guesses it
gives me a really good answer.
And if I pick something that's not a perfect cube, like 54,
and I do the same thing, in this case
it took 15 guesses to get me a really good answer.
This is a powerful tool, that idea of bisection search,
throwing away half the possible values at every stage,
let's me very quickly zero in.
As before I can ask, well, can I do everything?
This is only going to work for numbers bigger than 1.
What about fractions?
Well, I know with fractions between 0 and 1,
now the difference is that the root doesn't
lie between the number and x itself,
or it lies between 0 and that number.

![18](https://ws4.sinaimg.cn/large/006tKfTcgy1fjj2r9y9lmj31100si425.jpg)

But that's an easy way to change,
and we can actually think about making that change.
But just to remind you of how powerful this is,
notice what happens.
If I start if with the number n, on the first guess
I reduce the set of things in half.
On the second guess, I reduce it by another half.
So it's now n over 4.
After g guesses, I've got a range that's only n over 2
to the g.
And what this says is that in an amount of time that
is going to grow as the log of n,
I'm going to get to an answer.
That's really nice, because it says
I don't take a linear time, I actually take less than linear
time to get there.
We'll come back to that idea later on in the course,
but this is a great example of a logarithmic time algorithm
finding an answer very quickly.
I jumped ahead a little bit, because I already
started talking about what happens
if I want to look for cubes only greater than 1,
I could modify to look at negative cubes,
and I could modify it to look at things where
the answer is less than 1.

![19](https://ws3.sinaimg.cn/large/006tKfTcgy1fjj2r79437j310s0siwg6.jpg)

And so for example, if x is less than 1,
I just change the search space.
So now, rather than going from 1 up
to x, it goes from 0 to x-- sorry,
rather than going from 0 to x, I want to go from x up to 1.
I'm not going to do it.
I'm going to leave it for something for you to try out,
but it's really easy to make that change.
And, again, notice what I've done.
Start with a basic set of code, check to see what it runs on,
and then decide if I wanted to use the same code,
how could small changes have it run
on other kinds of solutions?

![20](https://ws1.sinaimg.cn/large/006tKfTcgy1fjj2r6bd3jj31160skdim.jpg)

What can I take away from this?
Bisection search really radically reduces
computation time.
I went from 30,000 times through a loop to 10 or 15 times
through a loop.
That's really nice.
And this should work on any problem we would
call an ordering property.
That is, the value of the function being solved
varies monotonically, that is, it increases
as the input value increases.
G squared has that property.
As I change g, it grows.
G squared grows as g grows.
G cubed, same kind of idea.
So bisection search will work on any problem
that has that kind of property.
We're going to see more examples of that
as we go through the course.

## Video: Floats and Fractions

...
We've just seen an example of an algorithm that
computes floating point numbers as an answer,
and we've been playing with floats earlier on.
I now want to take a little sidetrack to talk about floats
and how they're represented inside the computer.
And in particular, to deal with something
that you may have experienced earlier on in the course, where
you'll get answers that will give you
some funny number where you expecting 3.0,
and it gives you 3.00000125 or something else.
To deal with this, we need to go inside the machine for a second
and talk about how floats represent real numbers.
They certainly approximate them, but it's
useful to get a sense of how the machine actually stores it,
because it can't store an infinite number
of decimal points or digits after the decimal point
inside the machine.
Here's the basic idea.
Let's start with a decimal number, the numbers
you're used to dealing with.
The number 302 is really 3 times 10
squared plus 0 times 10 to the first power plus 2 times 10
to the 0-th power or 1.
It's 300 plus zero 10s plus two 1s.
Binary numbers, which is how the computer store things,
are actually represented the same way, but now
in terms of powers of 2.
So the number 10011 in binary is 1 times
2 to the fourth, plus 0 times 2 cubed, plus 0 times 2 squared,
plus 1 times 2 to the 1, plus 1 times 2 to the 0.
Which is actually 16 plus 2 plus 1, or 19 in decimal notation.
Internally, the computer represents
every number in binary, whether it's an integer
or it's a float.
How would we use that idea to think about how do we represent
floating point numbers?
Well, let's think about how we could convert a decimal integer
into a binary representation, and then we'll
do the fraction portion of it.
So given a decimal integer, how would we convert it to binary?
Well, let's take an example.
My example would be the one I just had before.
19 in decimal is 10011 in binary.
If I had 19, or anything that represents that number,
how could I get it out?
Well, what I can do is the following little trick.
I can take the remainder of that number relative to 2,
and that remainder actually gives me the last binary bit.
It'll give me this bit right here,
because that's the remainder that's left when I divide by 2.
If I then take x and divide it by 2 integer-wise using
that double slash idea, all of the bits get shifted right.
That is x double divide by 2 is now 1 times 2 to the third
rather than 2 to the fourth, plus 0 times 2
squared rather than 2 to the third, plus 0 times 2 to the 1
rather than 2 squared, plus 1 times 2
to the zero rather than 2 to the one.
Or another way of saying it, and notice I've taken these digits
and just shifted them to the right.
If I keep doing successive divisions like this,
I can keep track of each of the bits
that comes out, because the remainder gives me
the next bit.
And when I'm done with all of that,
I've converted to binary form.
So basic idea, given an integer, take the remainder with respect
to 2.
That's the low order bit.
Divide integer-wise by 2, shifts right.
Do the same thing until I've exhausted the entire integer
representation.
So here's a little piece of code that would do exactly that.
If the number is less than 0, I'm
going to put on a flag that says it's negative.
And I'm going to use the positive version of it
by taking the absolute value of that number.
Otherwise I'm going to put in a flag that says it's not.
And then I'm going to simply accumulate those results.
If the number is equal to 0, it's just 0.
That's pretty obvious.
Otherwise, as long as the number is greater than 0,
I'm going to do remainder, add that in,
because that's the next bit into result,
do the division to shift it to the right, and keep going.
So if I look at that, here's a simple example
of doing that conversion, converting decimal to binary.
I'll start with a real simple example.
If I start off with number as 3 and I do that computation,
I didn't print anything, but the result is sitting in result.
And there I get it.
The binary representation of 3 is, not surprisingly, 1 plus 2.
Let's just check to make sure I wasn't misleading you
when I said 19 was, in fact, what I claimed it was.
So if I make it 19, and I run it, and I look at result,
it gives me back 10011, exactly as I said.
All right, cool, so I can take integers and convert them
into binary, but I started talking about floats.
So how do I deal with the fraction part of this?
Well, I can do almost the same thing.
Let's take an example.
3/8 is 0.375.
And in binary, that is 3 times 10 to the minus 1 plus 7 times
10 to the minus 2 plus 5 times 10 to the minus 3.
It's just the digits associated with each of the placeholders.
Here's the trick I'm going to play.
If I can find a power of 2 big enough to convert all of that
into a whole number-- that is, multiply it by something so
that it gets converted into a whole number,
then I can convert that into binary.
I just did that, I know how to do that.
And then when I'm done, just divide by that same power of 2,
and I've got no representation in binary
of the fractional part of this number.
In this case, I picked an easy example.
0.375, if I multiply it by 2 to the third, or 8,
that's going to get me a 3 in decimal.
I can then use what I just did as my trick
to convert that to binary.
That's 11.
And then I divide by 2 to the third, which simply says
shift it right three points.
And there is the binary representation
of that decimal fraction.
That's cool, right?
It's a really neat idea.
What am I doing?
I'm using something I did for one computation,
but converting another problem into the same problem.
In this case, given a fraction, I'm
saying find a power of 2 that shifts it into an integer,
use the same machinery, and then shift it back.
And I'm simply taking advantage of powers of 2
because that's simply moving the placeholder, if you like,
for the decimal point, or I should say the binary point
in a binary representation.

There's code that'll do it.
I'm not going to walk through it.
I'm going to let you look at it.
I'm simply going to show you that this will actually convert
a decimal to a binary fraction.
So if I take this and I run it, in this case,
it says give me a decimal between 0 and 1.
Let's pick out a nice example.
Let's start with the one that we had, which was 0.375.
Sorry, let me make sure I'm here.

And it says, oh, I'm going to tell you
when I've gone through it to get it up to something
that is big enough.
How many times I have to shift it over, what's the remainder,
and there's the printed solution.
Let's be daring and try another example
I haven't tried before just to make sure
that it actually works.
So again, we're going to call this out.
It says give me a number between 0 and 1.
And I don't know, let's take 0.333.
And what do I get?
Well, it goes through a whole lot more computation.
It's telling me what the remainders are,
but it's running through that computation.
And it says the binary representation for 0.333
is this horrible-looking mess you see on my computer screen
down there.
But the point of this is now I can take any floating point
number, convert into something that
can be represented inside of the machine in binary form,
and use it.
And that, by the way, is why you will occasionally
see these strange things where you're expecting 3.0 back,
and it has a little bit of an extra piece
on it because in binary it can get close to it,
but not quite to the place it would like.
But with that, we now have a way of understanding
how we can represent floating point numbers inside a machine
where everything is stored just in terms of binary bits.
What are some of the implications of this?
If there is no integer p such that a power of 2
multiplied by x gives me a whole number,
then the best I'm going to get is an internal representation
that's close.
Which is why I won't get something exactly right.
And obviously, I'm only going to do this so many times
before I run out of powers of p to use this.
It also suggests that when you want
to test equality of floats, you should be careful.

Given two floats, x and y, you really
don't want to use double equal sign,
because it's going to check to see
is the binary representation exactly the same.
It might not be.
It might be really close.
So we're always better off using the absolute value
of the difference of two floating point numbers.
Is it smaller than some small number,
rather than using the more exact are they exactly the same.
And then finally, as I've already said,
we may not always get an exact representation
for a float in the way we would like.
But if I do print of something, why does
it always return what I'd expect,
even if the representation isn't different?
And the answer is because, wonderfully, the designers
of Python designed it so that it would automatically
round to the closest representation in terms
of that floating point number.
There are floats.
Now we've got ability to do integers and floats,
we're in good shape.

## Video: Newton-Raphson

...
Now that we've got an understanding of floating point
numbers, now that we've got the idea of generalizing guess
and check methods to do things, it
can do approximations to find solutions to things,
we can really start building some pretty powerful programs.
We've already seen something that
searches for cube roots of numbers,
even if they're not a perfect cube, square roots of numbers
even if they're not a perfect square.
And we've seen how we can get to quick solutions
very nicely using things like bisection search,
have great accuracy and still find good answers.
I want to show you one last example just
to give you a sense of the power of computation we can now do.
I'm going to stick with the idea of finding roots of things
but show you how you can actually capture things
very dramatically.
And that's to use a technique called Newton-Raphson.
It was discovered by Sir Isaac Newton three or four centuries
ago, also discovered by Raphson at about the same time.
And here's the basic idea behind Newton-Raphson.
It's a general approximation algorithm
that's going to let us find roots of any polynomial in one
variable.
So that could be, for example, the polynomial like this-- I've
got p of x is some coefficient times x to the n
plus some other coefficient times x to the n minus 1
and so on.
And what I want to do is find the value r such that p of r
is equal to 0.
It's called a root.
It basically is the root of this equation.
Newton-Raphson will apply to any polynomial.
I'm going to show you an example of using
it to find square roots, and you can say,
well, I already did that with bisection search.
You're right, but it's a nice way
of looking at how we can generalize the computation.
So in particular, if I want to find the square root of 24,
I'm going to use the polynomial x squared equals 24.
Because if I can find the value of x for which this is 0,
then x is in fact the square root of 24.
What Newton showed was that if g is a good guess to that root,
then you can get an even better guess by taking g
and subtracting from it the polynomial evaluated
at g divided by the derivative of the polynomial evaluated
at g.
And if you haven't done calculus,
and you don't know what a derivative is, don't worry.
We're going to show you what it is
in this simple case of a square root.
But I want to let you see the power of doing Newton-Raphson.
So Newton showed, if I got a good guess,
I can make it better by taking p of g
divided by the derivative of p of g
and subtracting it off of g.
So in the simple case, if I've got an equation that
is some constant times x squared plus another constant,
then the first derivative of c times x squared is just 2cx.
So in my case of looking for square roots--
x squared plus k is the thing I'm
trying to find a solution of-- the derivative is just 2x.
And so Newton-Raphson says, given a guess for the root,
take the polynomial at that point, which
is g squared minus k, take the derivative of that point, which
is just 2g, take that ratio and subtract it off from g.
Cool.
We ought to be able to build that, and we can.
It's a nice tight little iterative loop.
So here's a nice way of generating the guesses.
OK, and I'm going to have some epsilon that's going to let
me decide how close I am to an answer.
I've got the thing I'm going to look for, and my initial guess,
I'm just going to pick as that value divided by 2.
And then here's the loop.
As long as guess squared minus y, the absolute value of that
is too big, I'm going to keep going.
And as before, I'm going to count the number guesses to see
how long it takes.
Each time around, I'm going to use that little equation
from Newton-Raphson.
I'm going to take g squared minus y divided by 2 times g
or guess, subtract that off of guess, and go back around.
That's just the thing I did before.
And I'm going to run through that loop
until I get something close enough,
and then I'm going to jump out.
So let's see what happens if we do it.
I've got the code over here.
I'm going to load it in and run it.
And in four guesses, it got a good solution-- four.
OK.
It's a whole lot better than 30,000,
which is where we started.
With the bisection search, it was about 15 or 20.
Now I've got it down to four.
Let's pick another example.
Let's take my favorite example here of 54.
Same thing, and I run it.
And in five guesses, it gives me a good solution out.
This is really cool.
I know you don't believe it, but it really
is cool, because it lets me not only find
cube roots and square roots, it lets me find the solution
to any equation very quickly.
So what we've now seen is that this idea of a guess and check
method builds on reusing the same code over and over again.
It takes the idea of a looping mechanism
and adds to it, building into it different ways
to generate the guesses and then checking
to see whether I'm close enough or I want to keep going.
And we've already seen now simple exhaustive enumeration,
bisection search, which cuts down
the amount of expense dramatically and now,
at least for root finding, Newton-Raphson, which
improves it even more formally.
So you've already seen three different classes
of algorithms, and you've got a lot of tools
for doing numerical computation.
We're going to come back to that as we move on
through the course.

