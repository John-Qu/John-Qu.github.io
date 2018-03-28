---
layout: post
title:  "Transcripts in 1 Introducion to Python of MITx6001x"
date:   2017-09-08 11:45:45 +0800
categories: notes
---

This is a note of MIT6001x 1 Introduction. The transcription is divided by meanings, and words unfamiliar for me are made Italia. I would like to type some of the content in video slides here, because I have found the intend that I don't read and understand them seriously.

## Video: Introduction

2017-09-06 WED

`01_01_Introduction_MITX60012016-V000700_DTH.mp4`

...
Welcome to 600 part 1.
We're delighted you're going to join us
for the next several weeks as we explore
interesting issues around computational thinking
and programming.

### OVERVIEW OF COURSE

- learn computational modes of thinking
- Master the art of computational problem solving
- Make computers do what you want them to do

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fj9uzjmjisj311c0s011r.jpg)

Now, what are we going to do in this course?
What do we want you to take away?
At the end of this course, what is
it we'd like you to have in your *armamentarium*
of great problem-solving tools?

We're certainly going to teach you about programming.
We'll teach it in a particular language called Python.

But more importantly, we want you
to start learning how to think computationally,
to think algorithmically, to think like a computer
scientist.

And what does that mean?
It means we'd like you to think about when
given a new challenge how can I get the computer
to solve this for me?

How can I describe the *stages* I want
to use to get this done in such a manner
that I don't have to do it.
I can get the computer to do it.

That's the *notion* of computational thinking,
of algorithmic thinking, and that's
what we're going to try and teach you about in this course.
Now, that means you really want the computer
to do the work for you.
It's going to be your **servant**, and that
means you need to think about how do you get it to do
the things you want it to do.

### TOPICS

* Represent knowledge with data structures
* Iteration and recursion as computational *metaphors* (隐喻？)
* abstraction of procedures and data types
* Organize and modularize systems using object classes and methods
* Different classes of algorithms, searching and sorting
* Complexity of algorithms

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fj9uwtm5lgj311a0s6gxn.jpg)

To do that, we're going to cover a range of topics,
and we'll see all of these over the next several weeks.

We want the computer to compute something for us,
infer some new knowledge for us.
That means we have to think about
how do we represent that knowledge,
and we'll do that with particular things
inside the machine called data structures.

We want it to infer a new information
or define information, and we're going
to see there are standard tools for making that happen.
Things called iteration and recursion.
And we'll come back to those over the next several lectures.

A big part of what we want to do inside the computer
is to have it be able to deal with things in a manner
that we can see and understand, and that's says
we're going to use the notion of abstraction to capture elements
and then treat them as if they were *primitives* and reuse them.

And that leads naturally to the idea of modularization,
creating modules, tokens, elements
that we can *stitch* together to come up
with solutions to problems in interesting ways.

Once we started learning how to build algorithms to think
algorithmically, we're going to see
that there are standard classes of algorithms,
and we're going to use those for common *parlance* (problems)2'40''
like searching and sorting and we're
going to see as well that different algorithms have
different costs.

And we want to see how to use that to reason
about the expense of doing something and better
ways of finding a solution to different problems.

So here's our roadmap.
These are the things that we're going
to deal with over the next several weeks as we talk about
and get you engaged in computational thinking.

### WHAT DOES A COMPUTER DO

* Fundamentally:

  * Performs calculations

    a billion calculations per second!

    ​	two operations in same time with light travels 1 foot

  * Remember results

    100s of gigabytes of storage!

    ​	typical machine could hold 1.5M books of standard size

* What kinds of calculations?

  * Built-in to the language
  * ones that you define as programmer

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fj9v732yf2j311a0s013v.jpg)

If we're going to get the computer to do this for us
though, we could start by asking so what does it really do?
Boy, that sounds like a dumb question, right?
Of course, computers do all sorts
of amazing and awesome things.
They can play Go, they can find things in the World Wide Web,
they can do all sorts of wonderful, marvelous things.

But fundamentally, a computer really only does two things.
It performs calculations.
Well, duh.
But in this case, the calculations
are actually very simple things.
Turns out they can do them amazingly fast.
But all they really do, they perform calculations,
and they remember things.
Early computers didn't have much of this power.
Modern computers have a lot.
But those are really the basis of them--
perform a lot of calculations really
quickly and remember results.

Now you could ask, how fast is it really in terms
of performing calculations?
The machine you're using can probably
do about a billion calculations a second.
And just to put that in context, if I had a lamp sitting
on my desk here-- about a foot above--
and I hit the switch, by the time light went from the bulb
to the table, your computer's performed two operations.
That's amazing.
It's really fast, and it sounds like that's
going to let a computer do almost anything.

How about remembering things?
Depends on the size of your computer.
You probably have a few gigabytes of memory in there.
A big computer or something on the cloud
might actually have hundreds of gigabytes of storage.
What does that say in terms of what it can hold?
Well, if you took the standard novel
and you put it inside a machine, a typical machine
could hold about 1 and 1/2 million books
of a standard size.
So if you're going to start reading those great classics,
now it's going to take you a while
before you get through all the things that
are stored on your machine.

So sounds like computers are amazingly good,
even though they only do simple calculations
and they remember results.
Hold that thought, because we're going to come back to it.
Because we can also ask what kinds of calculations
does the computer actually do?
Every computer comes with a set of built-in operations.
These are typically primitive arithmetic operations--
multiplication, addition, division-- and simple logic
operations, comparing true and false values in order
to make decisions with that.
If that's all we had, that's going to be a real pain.
And so what we want to do through this course
is figure out how to define new **calculations**,
new **operations**, things we create and give to the computer
so that it can ***abstract*** them, ***encapsulate*** them, and treat
them as if they're **primitives**.
But to start with, a computer simply
performs a lot of those calculations.
So simple primitive calculations very quickly.

### SIMPLE CALCULATIONS ENOUGH?

* Searching the World Wide Web
  * 45B pages; 1000 words/page; 10 operations/word to find
  * Need 5.2 days to find something using simple operations
* Playing chess
  * Average of 35 moves/setting; look ahead 6 moves; 1.8B boards to check; 100 operations/choice
  * 30 minutes to decide each move
* Good algorithm design also needed to accomplish a task!

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fj9vryroycj311c0s0dqn.jpg)

Is that enough?
It might be.
If that's the case, we really don't
have to do a lot in terms of computation.
And I want to give you a couple of examples to show you
why even with the speed of modern computers,
you need to be able to think carefully, cleverly,
algorithmically.

Here are two obvious examples of things you might like to do.
You want to find a piece of information
on the web, something you do every day with a search engine.
You might want to play chess or have your computer play
chess for you.

Suppose you want to search the web.
How much could you do if you just
were using simple calculations?
Well, here's a little computation
I did before I came in to capture this lecture.
There are about 45 billion pages right now
on the World Wide Web.
On average, there are about 1000 words on a page.
And for sake of argument, let's assume
if we want to find a word on a page,
it's going to take us about 10 operations
to try and find out whether that word is on that page or not.
We'll see later on how he got it down to about 10 operations.
That says if I'm going to just **brute force**
try and search everything on the web
to see if I can find the thing I'm looking for, it's only
going to take me about 5.2 days to find something.
You probably don't want to wait that long.
So even with a very fast machine using
these simple calculations, it's not going to be enough.

How about playing chess?
An expert will tell you there about,
on average, 35 moves for every setting on the transport
until you get to the endgame.
Suppose you want to look ahead six moves
in order to try to decide what you want to do in order
to beat your opponent.
That says you've got about 1.8 billion boards
that you need to check.
And if it's going to take you, for example,
100 operations for every choice, it's
going to take you about 30 minutes to decide each move.
Probably too slow.
And this is simply a way of saying
that even with fast computers, we need cleverness,
we need algorithmic thinking to take those simple computations
and turn them into something more powerful.

And that's as good algorithm design is going to be crucial
and it's one of the skills you're
going to learn throughout this course.

### ENOUGH STORAGE?

- What if we could just pre-compute information and them look up the answer
  - Playing chess as an example
    - Experts suggest 10**123 different possible games
    - Only 10**80 atoms in the observable universe

![](https://ws1.sinaimg.cn/large/006tKfTcly1fj9w37xd3cj311a0s2jxz.jpg)

What about storage?
For lots of storage in the machine.
Why don't I just compute everything once, store it away,
and then just look it up.

So let's go back to chess.
Imagine I just want to look at all the possible chess games
and store them away so that when I'm in any move,
I'll just know what I want to do in order
to get to a winning position.
Well, experts would suggest that there
are something on the order of 10 to the 123 different
possible chess games.
That's a really big number.
And in fact, there are only about 10
to the 80th atoms in the observable universe.
So there's no way that we can store all of that information
away.

And again, it comes back to saying we can't just
use **brute force** or **pre-compute**.
We need to be clever about how we come up with solutions.

### ARE THERE LIMITS?

- Despite its speed and size, a computer dose have limitations
  - Some problems still too complex
    - Accurate weather prediction at a local scale
    - Cracking encryption schemes
  - Some problems are fundamentally impossible to compute
    - Predicting whether a piece of code will always halt with an answer for any input

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fj9w9lwshkj311e0s4the.jpg)

Even with that, we're going to ask
are there going to be limits to computation,
even if we can build clever algorithms?
And in fact, one can suggest that there are still
some limitations to what a computer can do.

Some problems are still, at least at the moment, too
complex, even with clever algorithms
to come up with solutions fast enough.
I'd love to know what the weather's going to be right
in my neighborhood every morning before I
get in my car to come to work.
I just don't have enough data and enough compute power
to be able to model at that level of scale.
Maybe eventually, but not yet.

In some cases, the fact that some things
are too hard to compute actually works in our favor.
And encryption schemes are an example of that.
Things that you want to store on a computer
encoded so nobody can break them rely on encoding or encryption
schemes that in turn, rely on the fact
that some problems are simply too complex to be solved
by a computer.

And in some cases, even if the computers get faster,
it's still not going to be possible to solve them.
Some problems are just fundamentally
impossible to compute.
And the classic one from computer sciences
called the Turing halting problem
and it simply says if I want to write a piece of code,
a program that could take in as input any other program
and tell me whether it will always work,
whether it will always stop with an answer,
it turns out you simply can't compute that in all cases.
So there are going to be limits to computation.

Not to worry.
It's going to be a lot of things we can do,
and that's what we're going to do throughout this course.

## Video: Knowledge

2017-09-07 THU

`01_02_Knowledge_MITX60012016-V000100_DTH.mp4`

...
OK.
We want to start thinking about how do we get a computer
to do things for us?
So we can start by saying, well, what
do we want a computer to do?
We want it to compute something.
That sounds like a deep, philosophical question,
and in fact, it is.

### TYPES OF KNOWLEDGE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjarweazxqj30sc0l8gte.jpg)

And that leads to an even deeper philosophical question which
is if we want a computer to compute something,
we can ask, well, what's the knowledge that it's going
to use to do that computation?
And that actually leads to an interesting distinction,
because we can divide knowledge into two types.
What we're going to call declarative knowledge
and what we're going to call imperative knowledge.

Declarative knowledge-- those are statements
of fact, statements of truth.
For example, if I were lecturing here at MIT,
I might have gone in ahead of time
and strapped some-- or taped some candy
under one of the chairs inside the lecture hall.
A declarative piece of information
simply says, there's candy taped to the underside of a chair.
It doesn't tell you anything about how to find it.
It doesn't tell you where to look for it.
You'd either have to do it in parallel
by having every student reach under the chair
or search the entire lecture hall.
It's simply a statement of fact.

Imperative knowledge is a recipe.
It's how to knowledge or how to information,
and this gives us a sequence of steps to find a solution.
Again, if I stuck candy under a chair inside the lecture hall,
I might say to the lecturer, do the following-- face
the students at the front of the room.
Count up one, two, three rows.
Start in the middle section left side, go in one chair.
Look underneath it.
Candy is there.
It's a recipe.
It's a sequence of how to steps, very mechanical,
to get things done.
Those two kinds of knowledge are important,
but only the second one's going to really be of value to us,
because that's what's going to help us get the computer
to do something for us.

### A NUMERICAL EXAMPLE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjas5m894aj30se0lcal8.jpg)

To see it, let's look at a simple example.
Suppose I want to compute the square root of some number.
To make it easy, I'm going to start
with just an integer number.
Here's a statement of fact-- the square root
of the number x is that y such that y squared is equal to x.
And I'm just going to highlight it right here.
There it is.
There's a statement of fact.

Does it tell me how to find a square root?
No.
If somebody gives me a good guess, I can use this to check.
So if I'm trying to find the square root of, say, 16,
and somebody gives me a guess of 4,
I'm lucky because I can say 4 times 4 is 16 and I'm done.
But it doesn't help me find something.
Here's a version of imperative knowledge,
and this is actually a very old algorithm.
It's attributed to Alexandria of Heron, dating back
into the 2nd century BC, although other people suggested
it existed earlier than that.
But here's a recipe for finding square root.
I'm going to start with a guess, and I'm going to call it g.
If g times g-- if g squared-- whoops.
Sorry, I'm going to go back.
If g squared is close enough to x, then
I'm going to stop and say g is the answer.
Otherwise, I'm going to create a new guess
by taking g and x divided by g, and averaging them together.
Take the average.
OK.
Once I've done that, I'm going to repeat.
I'm going to go back up and do the same thing again.
And that's going to give me a little algorithm, because it's
going to let me now say, start with a guess,
check to see if the guess is close enough, and if not,
keep going.
And you can see that little graph at the bottom.
I start with not a very good guess.
g is equal to 3.
I square it.
That's 9.
9 is not, as you can see here, very close to 16,
so I'm going to take x divided by g, which is right there.
And I'm going to take g, and I'm going
to average them together to get a better guess right there.
With that better guess, I'm now going to do the same thing.
I'm going to go back through that loop,
go back up to step number one, and say try it again.
And you can see the steps here.
I square 4.1667.
I get 17 and change.
It's really not close enough.
I take x divided by g.
I take the average of x and x divided by g
and I get a much better guess.
And you can see after the next round,
I get a guess that's close enough.
I'm probably ready to stop.
So this is a nice example of a little algorithm.
It's a little recipe.

### WHAT IS A RECIPE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjasdwojb0j30se0ladqd.jpg)

And let's capture those pieces together.
What's a recipe?
Three pieces.
It's a sequence of simple steps.
It's a flow of control, a process that's going to tell us
what order in which to execute the steps,
and it's going to give us a way of deciding when to stop.
So those three pieces-- 

- simple steps.A sequence of things I want to do,
- a checklist, a flow of control, a thing that tells me when to go to the next step, when to jump to some other place in that sequence of steps,and 
- a way of deciding when to stop.

Those three pieces constitute an algorithm.
And you just saw it in the little square root example.
In general, the flow of control was going successively
through the steps until I got to a test,
and that test had me jump back to another place
inside the algorithm.
That's what an algorithm is.
That's what a recipe is, and that's what we want to capture. 

## Video: Machines

2017-09-07 THU

`01_03_Machines_MITX60012016-V000600_DTH.mp4`

...
We've described a recipe.
We said it's a sequence of mechanical steps.
It's going to capture the sequence of things
I want to do in order to compute something.
But now I want to get it inside the computer.
I don't want to just give it to my friend
and have him do all the work for me.
So the next question is how do I **capture a recipe**
**inside a mechanical process**?

### COMPUTERS ARE MACHINES

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjaw5n6a7rj30sa0l6dy6.jpg)

Go back to my square root example.
I'd like to get a machine that's going
to compute square roots for me.
Historically, there were two choices here.
The first one was to use what was called a fixed program
computer, and this would be a computer designed specifically
to calculate a particular computation.

You've actually seen them.
Actually, you may be too young to have seen them,
but people my age have seen them.
*Handheld* calculators were a fixed program computer.
They did addition, subtraction, multiplication,
a simple set of arithmetic operations.
That's all they could do.
If you wanted it to search the web, good luck.
Wasn't going to happen.

Very famous historical example was Alan Turing's bombe
this was a machine designed during World War II
to break German codes for the Enigma machine.
And it was designed specifically for that process.
It was also built out of devices you don't see anymore
like vacuum tubes and relays, and you
can imagine the challenge of building such a machine.
But it was designed to be a fixed program computer.

That'd be boring if that's all we could do.
I don't want to have to carry around
a computer for square root and a computer for cube root
and a computer for quadratic root, you get the idea.

The alternative is what's called a stored program computer,
and that's what you're used to seeing.
Difference with a stored program computer
is that you can load into it that description, that sequence
of instructions, that recipe.
And then inside that computer, there
are going to be a set of parts that
are going to do those instructions when
I ask them to.

And in particular, there's going to be a special program
inside the computer typically called an interpreter, which
when you start it up, is going to walk through each
of those sequence of instructions,
in turn, doing the computation I want.

And the advantage of a stored program computer
is I can load in a different program
and have it do the same thing.
In essence, that stored program computer
is emulating or imitating a fixed program
computer for each program that I load in.
Gives me an infinite range of things that
are going to be able to do.

So what I want to now think about is,
how do I take a description of a process
in those mechanical steps and write it in such a way
that I can load it into the computer
and the computer can do the work for me?

### BASIC MACHINE ARCHITECTURE

![](https://ws1.sinaimg.cn/large/006tNc79gy1fjawa9m3mij30se0l67ek.jpg)

Before I do that, I need to think about what's
inside the machine.
So we're going to take just a second to open up the *hood*
and look inside a typical computer.
Basic machine architecture of a computer
has some simple pieces.

It's obviously got some memory, places in which I'm
going to store things.
Now, up here in this memory, it could be data,
but it also could be a sequence of instructions
that are my program.
That mechanical set of steps.
I haven't said exactly what they look like,
but you got a sense of them from what I did in that square root
example.

I'm also going to have a way to load things into the machine
and print things out of the machine.
Input and output.
We'll come back to those later on.

Inside the heart of the machine there are two elements.
The first is often called an ALU-- an Arithmetic Logic Unit.
And what this unit does is it takes information from memory,
reads it in-- often two pieces of information if I'm
going to do an operation that takes two inputs-- is going
to do a primitive operation could be addition,
could be subtraction, could be testing
to see if something is true or false,
and then typically is going to store stuff
back up into memory.

To make that happen, we need one more piece,
and that's the control unit.
And that's going to keep track of what a specific operation
I want to do in that ALU at each point in time.
And inside the control unit there's
an important thing called a program counter.
So very simply, when I load a program
into the machine- in a second we'll get into how to do that.
But I load a program into the machine.
It's a sequence of instructions appear.
and the program counter points to the location
of the first instruction.
And when I ask the machine to execute,
the program counter reads that first instruction.
It's going to cause an operation to take place,
and is then going to add one to the program counter, which
is going to take it to the next instruction in the sequence.
Just as we saw in the square root example.
That's going to do another operation.
Typically doing some arithmetic operation,
move things back into memory, and it's
going to increase the program counter.
Eventually, we're going to get to a test,
and that test is going to say whether something
is true or false.
And based on that, we're going to change the program counter
to go back up, for example, to the beginning of the code.
But that's, in essence, what happens
inside a modern machine.
Control unit tells me where I am in a sequence of instructions.
I've read into the machine, that stored program.
That causes a simple loop inside the machine of operations.
When I get to a test, it's going to potentially change
the program counter, and when I get
to something that says stop, it will
and it'll print something out on the machine.
That's the heart of a machine.
That's all there is inside a computer.

All right.
It's a lot of stuff inside there,
but that's basically what the machine is going to do,
and our goal is now to figure out
how do we write that sequence of instructions
so that the computer can do the things I want it to.

### STORED PROGRAM COMPUTER

![](https://ws2.sinaimg.cn/large/006tNc79gy1fjawc9mvm7j30sc0ledn1.jpg)

To summarize, a stored program computer, then,
is going to be that sequence of instructions.
It's going to be built out of simple arithmetic and logic
instructions.
It's going to be built out of simple tests.
And it's going to allow us to move data around.
And associated with that is going
to be this special program called the interpreter that's
going to execute each of those sequences of instructions
in order, changing things with the flow of control
when a test says, I want to go somewhere else.
And then finally, when I'm done, print out the answer.

### BASIC PRIMITIVES

![](https://ws3.sinaimg.cn/large/006tNc79gy1fjawfq4ju4j31kw122hdt.jpg)

That sounds great.
So what are the basic parameters?
Most machines will come, as I said,
with simple arithmetic and logic operations.

But in fact, you can go even simpler than that.
And if you go back to that gentleman I mentioned earlier--
Alan Turing, one of the greatest computer scientists
in the history of the world-- Turing
showed that you can compute anything
with just six primitives.
In fact, there's something called a Turing machine,
an old example of which is shown in that little image
on the slide.
A Turing machine is an infinite tape
with a set of squares on it.
In each square, there's a symbol,
could just be a 0 or a 1.
And what Turing showed is if you have six operations.
And those are move left, move right, scan, read, write,
do nothing.
With just those six primitives, you
can compute anything that's computable.
You're now *panicking* and looking to find a different class,
because if what you had to do was program
a computer by saying move left, move right, read, write, scan,
stop, you don't want to program.

Fortunately, modern programming languages
come with a more convenient set of primitives.
But the fundamental idea is that with a simple set
of primitives, you should be able to compute anything.
Equally importantly, you don't want to just write everything
in terms of addition, subtraction, logical tests.
What you want to do is write descriptions
like that square root program that we
talked about earlier and then **abstract** them.
And I want to highlight that word,
because abstract is going to be really important.
You want to treat that square root as if the manufacturer had
built a little primitive and installed it in your machine.
You want to be able to use it as if it was something that
came with the machine, and that's
what the power of computational thinking is going to give us.

*One* last thing about computation.
Let's go back to the Turing machine idea.
I said you could compute anything
if you just had the six moves.
There are some *nuances* to this.
A more *sophisticated* computer scientist
could debate some of those details,
but there's a fundamental property
which says anything that's computable in one programming
language is, in fact, computable in any other programming
language.
Wow.
That's amazing.
Says, well, you may get heated debates between people
about whether Python or C or Fortran or LISP
is the best computer programming language.
They're all the same.
OK.
Slight *misstatement*.

In some languages, it's going to be easier
to do some kinds of things than others.
In Matlab, it's easier to manipulate matrices.
In C, it's easier to deal with web programming.
But nonetheless, anything you can compute in one language,
you can compute in any other language,
and this is a property called **Turing complete**.
It's one of the fundamentals of computer science.

## Video: Languages

2017-09-08 FRI

`01_04_Languages_MITX60012016-V000500_DTH.mp4`

...
So now that we've had the idea of creating
a recipe as a generic idea.
We know a little bit about what's inside the machine.
What we need to do is put those two things together.

### CREATING RECIPES

![](https://ws3.sinaimg.cn/large/006tNc79gy1fjbytpeackj30se0legri.jpg)

We want to now go from a description
of a process to a specific set of statements
that we can store in the machine so
that that interpreter, that evaluator,
can then run those operations to use
the primitives inside the machine to do the work for us.

As we said, the programming language
is going to provide us with a set of primitive operations.
And the next step is to start talking about how
do we put them together.
To do that, we use something that we call an expression.
And the expressions in a language
are simply more complex but legal combinations
of primitives that the programming language
will recognize.
And we're going to start building those up.
So you're finally getting to the stage,
after all of this high level discussion,
of getting to the place where we're
going to begin to get the computer to do something.
One of the things we're going to talk about though
is that any legal expression in a programming
language, any computation, has associated with it a value.
That value is the meaning of the expression.
And that's going to be important, in part
because if we know we want to get
to a particular computation, we want
to understand how do we get to that value,
well how do we back out of that the sequence of steps,
the expressions that are going to compute it for us.

### ASPECTS OF LANGUAGES

![](https://ws3.sinaimg.cn/large/006tNc79gy1fjbyvtl3mkj30sc0lcapv.jpg)

So let's look at how we put this together.
Every programming language could be thought of
as consisting of 

* a set of primitives,
* a means of combination, a way of putting those primitivestogether to create new expressions,and 
* a means of abstraction, a way of taking some complex expression and treating it as it's a primitive.

To talk about this in a programming language,
I'm going to give you an analogy to a natural language
like English.
In English, what are the primitive constructs?
They're words, lots of them, some of them
more common than others.
In a programming language, we also have primitive constructs.
These are the atoms on which we're going to build things.
And in a programming language those
are typically numbers, strings, or just sequences
of characters, and simple operations, the things that
were provided to us by the manufacturer-- addition,
subtraction, comparison.
Given those primitives, we want to put them together.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjbz2y7dv7j30sa07agp6.jpg)

When we put them together, we have
to think about two different parts.
This is taking you back to an English class,
because we have both the syntax and the semantics.
The syntax is that parsing of a sentence to know,
is this a legal sentence or not.
And some combinations of expressions are legal.
Some are not.
For example in English, cat dog boy
is not syntactically valid.
It does not make sense.
There is no verb in there.
On the other hand, cat hugs boy is syntactically valid.
It is a noun, a verb, a noun.
That's something that makes sense.
The same thing's going to happen in programming languages.
Some combinations of primitives are not legal.
They're not syntactically valid.
For example this expression right
here, the first part-- we're going
to come to this in a second-- is a string.
It's a sequence of characters enclosed in double quotes
followed by a number.
It's not a legal expression.
On the other hand, as we'll see in a second,
this is a syntactically valid expression.
It consists of a number, an operator, and a number.
So we're going to talk about how do we
put together legal expressions.
What is the syntax of those, both
in terms of simple combinations like this and how
we do it when we get to more complex aspects
of the language?

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjbz2zpusaj30se08sdk8.jpg)

Associated with every expression that is syntactically valid
is potentially a meaning, the semantics.
What does this expression evaluate to?
And here we're going to separate out both **static semantics**
**and full semantics.**
Static semantics tells us which syntactically valid strings
actually have a meaning.
In English, in bad English, the sentence I are hungry
is not actually meaningful.
It's syntactically valid, meaning
it's put together properly.
It's in this case a pronoun, a verb, and then an adjective.
A perfectly legal combination, but semantically
it doesn't make sense.
Same thing happens in a programming language.
The first expression, 3.2 times 5, is syntactically valid.
The second one, 3 plus the string hi,
is syntactically valid.
It is a primitive, an operator, and a primitive,
but semantically it doesn't make sense.
I can't add a number and a string together.
So we have to distinguish things that are not
statically semantically valid because they're not
going to be expressions we want to try and assign a meaning to.

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjbz7zgi9zj30si0aitem.jpg)

Once we have both syntactically correct and static semantically
correct expressions, we want to then know
what's the meaning associated with them.
And I'm goin g to start building this up.
Semantics then is the meaning associated
with that syntactically correct string of symbols
with no semantic errors.
Even here there can be some wonderful nuances.
In English, we can have a sentence
that's both statically semantically
correct and syntactically correct,
but can have multiple meanings.
Flying planes can be dangerous.
Does that mean if I'm flying that it's dangerous?
Does it mean if they come out of the air and crash on you
they're dangerous?
There are multiple interpretations to it.
Or from an old joke, this reading lamp
hasn't uttered a word since I bought it,
obviously playing on the word reading
lamp in a different way-- different meanings associated
with it.
In a programming language, there's
both good news and bad news.
The good news is any syntactically correct
and static semantically correct expression in a programming
language will only have one meaning.
But the challenge is it might not
be the meaning you intended.
And that's where bugs are going to show up.
And we're going to come to that as we go through the term.
But these pieces now are how we're going
to talk about the language.
What's the syntax of putting things together,
and what's the semantics, the meanings associated with them?

### WHERE THINGS GO WRONG

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjbzaas9t0j30sg0legu3.jpg)

With those three things in mind, you
can ask what could go wrong.
And these are also things we're going to see in the course.

First of all I could have a syntactic error.
I've not written down a legal expression.
These are common and easily caught.
And in fact most good programming languages
or the environments that interpret them
will catch those directly.
As you'll see as we go along, and I'm
sure I'm going to make some mistakes as I
do some work here, Python will catch those right away.
So you won't try and do anything with them.

Once you've got something that's syntactically correct,
what about static semantic errors,
things where things are in the right order but they
don't make sense?
Some languages are very strict about catching these.
They'll actually check before you ever run
a sequence of operations to make sure there
are no static semantic errors.
Other languages-- and Python is one of them--
will **do it on the fly**.
As you're going through a sequence of instructions, when
it comes to one that is not statically semantically
correct, it will stop.
That's good news, but it can lead
to some unpredictable  behavior.
And we're going to see that as we go along.

The bigger problem is one where there are no semantic errors,
but you get a different meaning than what you actually
intended.
These are the bugs that are challenging and are
going to be difficult to find, but you need to find.
Now what are some of the consequences?
The program could crash, simply stop running.
Even worse the program could run forever or until you get really
tired and stop the machine because it's not
coming back with an answer.
And even worse yet, the program gives you an answer,
but it's different than what you had expected,
and you're going to use that to now do
incorrect conclusions based on that error in computation.

### OUR GOAL

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjbzgr5xyqj30si0lgq94.jpg)

So what we're going to do now is start talking about Python.
And our goal is to learn the syntax and the semantics
of this particular programming language,
and then to use that to learn how we can translate
our recipes for solving a problem into a form that
can go into the computer so it can run through that very
mechanical sequence of steps to compute things
that we want to do.
And finally as we do all of this,
we're going to start seeing patterns of computation.
We're going to build up computational modes of thought,
different styles of solving problems,
because those styles are going to be common
and can be easily reused when we see a new problem that
fits into the same category.

## Video: Types

2017-09-08 FRI

`01_05_Types_MITX60012016-V000400_DTH.mp4`

...
Now that we have the idea that we want to put together
expressions, by putting together primitives in legal ways,
we can take up that idea of how to use
that to start capturing recipes, start capturing algorithms.
So let's talk about a Python program.

### PYTHON PROGRAMS

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjc0lu0as5j30s80le7b1.jpg)

Python being the language we're going
to use in this class to do programming.
And the program, just as you saw with the recipe,
is going to be a sequence of definitions and commands.

Definitions as we'll see a little bit later on,
are ways of either assigning names to values,
or more importantly, creating procedures
that we're going to treat as if they're primitives.
Those we refer to as being evaluated.

Commands, are simpler expressions
that we can execute directly within Python.
And we do that in something called a shell.
In a moment I'm going to use a shell.
A shell is simply a window into which I can type expressions.
They get passed into the Python interpreter,
it follows the set of instructions to figure out
what's the semantics -- what's the meaning associated with
that expression?
And then it prints out the result.
Commands are statements that instruct the interpreter to do
something.
So the commands could be simply, do this arithmetic operation.
Or commands could be apply a primitive that I
created to do some work for us.

The last piece, and we're going to see both of these
as we go through the course, is that we can either type things
directly into the shell.
That's a window that the interpreter is listening to.
That's something where we type something in
and the machine does something with it.
Or, we can store it in a file that gets read into the shell
when we're ready to use it.
But otherwise, can be saved away.
To start with, we're just gonna type directly into the shell,
but we'll see examples of files in a little bit.

### OBJECTS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjc0qixk75j30si0lejwa.jpg)

OK, we're almost ready to start programming.
We know the pieces we need.
Let's start with what are the fundamental primitives that
represent data?
Those, we call objects.
And programs manipulate data objects
in order to get out parts of those objects
or to do something with those objects.
Every object has a type associated with it
that tells us what kind of thing it is.

And more importantly, that type is really important.
That type tells programs whether they can act on it or not.
If a program is expecting a number and I give it a string,
it's not going to try and do something with it.
So the type of the object is really valuable.

Finally, objects come either as scalars, which
says they can't be subdivided.
Or, if they're scalars, obviously
non-scalars which are things that
have internal structure into which we can pull out parts.

### SCALAR OBJECTS

![](https://ws1.sinaimg.cn/large/006tNc79gy1fjc0sptg0jj30sg0leaig.jpg)

Let's start with the simplest version of these,
scalar objects in Python.
There are very few of them.
We have ints.
These are integers.
Standard numbers that you recognize, 5.
17.
27.
Minus 6.
We have floats.
These are real numbers, things with numbers
after the decimal point.
3.27.
3.14159, my favorite.
You have something called a bool, short for Boolean.
And that represents true or false.
Those are going to be important when
we get to tests, because we want to know if a test is true,
do something.
If it's not, do something else.
There's one weird one.
It's called NoneType.
It's a very special one.
It has only one value, which is none.
We're going to see why that's important later on,
but just to be careful, NoneType is a scalar object.
Those are four fundamental scalars.
There are only a couple of more, which we'll get to a little
later on.

Once I have knowledge of those different types,
I can also find out the type of an object,
by using a built-in procedure called type.
And I want to show you some examples.
So I'm going to go over to my little machine over here,
and I'm going to skip down.
I'm now talking to a shell.
And you'll notice it's got a little prompt that says in,
saying what's the input you want to give?
The fact it's got 30 on the machine
is because I was doing some other work earlier.
So this is going to be the 30th expression typed in.
And I'm simply going to type in a number.
And the output is the number itself.
Well duh, you say.
But it's actually important, because what the machine did
was it read in that sequence of characters, understood
that it was a number, and the value
associated with the number is simply the number.
And in fact, I can check it because I
can say what's the type of 3.5?
Notice the open and close parentheses around it.
And it says, it's a float.
And I can have integers.
And if I say what's the type of that,
it's going to give me back an int.
Simple things.
OK.
Again, just to *recap* what this says is here's
what I'm going to type into this Python shell.
And here's what shows up after I hit Enter as you just saw.
And in and out are simply going to identify what I typed in,
in the output that you've recovered.

### TYPE CONVERSION(CAST)

![](https://ws2.sinaimg.cn/large/006tNc79gy1fjc0xjy199j30sg0lcn18.jpg)

Sometimes I want to change types, especially with numbers.
This is called casting.
And I can cast types of different forms,
and you can see the example.
If I say, I want to take an int, such as 5,
and turn it into a float I can ask it to do so, by giving it
the special command float -- the thing contained within
parentheses -- and it converts it.
The other direction also works.
If I want to take a float, such as 3.9,
and convert it into an int.
Here you say, boy there might be some choices.
Python simply gives the whole number part of it.
It doesn't round it to the nearest integer,
as you might expect.
If you want to build your own programming language,
knock yourself out.
You could do that.
But it simply will truncate it down to that int.
So I can convert back and forth.
Now, once I've got these things, I
can start putting things together.
And in particular, here's a legal expression.
3 plus 2.
That has a value associated with it.
In fact, that expression is to take the 3 and the 2
and apply the arithmetic operation of addition to them.
And when I evaluate it, it simply returns out 5.
Makes sense.

### PRINT TO CONSOLE

![](https://ws1.sinaimg.cn/large/006tNc79gy1fjc0zqfi4qj30sg0lgdk1.jpg)

Sometimes I might want to use something
that's going to print.
And I can type, for example, print
which controls output to the console
by saying print 3 plus 2.

Huh.
Little bit of a difference.
And in fact, there's no out here because no value is returned.
Print returns that NoneType and doesn't print anything out.
It just printed something.
At this stage, you may be saying, well why do this?
Why the difference?
What we're going to see is, when we're
in the middle of a computation and we want to print something
out to the shell, we can use a print command to do that.
If we just return the value, that
goes back into the computation to be used for the next step.
And so in the simple first case, the whole value
of the computation was 3 plus 2 equals 5.
It was printing all 5.
In the second case, the side effect is to print something.
The value returned is nothing.
There is no value.
We'll come back to that as we go along.

### EXPRESSIONS

![](https://ws3.sinaimg.cn/large/006tNc79gy1fjc11horizj30sg0letd3.jpg)

I've already hinted at this, but now we
can start putting things together.
To combine objects and operators into expressions,
we use a standard form.
And the syntax is simply an object, an operator,
and another object.
Any expression like this that is syntactically valid,
has a value, which is itself a type.
So we talk about the types of scalar objects,
we talk about the types of more complicated expressions.

OPERATORS ON ints and floats

![](https://ws1.sinaimg.cn/large/006tNc79gy1fjc140dqwtj30se0laahs.jpg)

What would those expressions look like?
Well, here's the first set of them.
There's a lot on this slide, but you're
going to get used to them.
And most of them make sense.

If I want to add together either two ints or two floats,
my expression is to have two numbers
as I just did, 3 plus 2.
The value associated with that is the combination
of adding the two things together.
I can subtract, I can multiply.
And for these examples, if both I and J are ints,
the result is an int.
If either of them or both of them are floats,
the result is a float.
And let's look at an example.
If I do 3 plus 2, I get 5.
If I do 3.0 plus 2, I get the float 5.
So Python is always using, if you like,
the higher level representation when it
does those kinds of operations.

Divisions, a little trickier, because I
have both standard division, which will be a float,
and I have integer division, which
will be the quotient without the remainder.
And let's look at two examples.
If I do 5 divided by 2, I get 2 and 1/2.
If I do 5 with two slashes divided by 2,
I get the integer part, which is 2.
The .5 is thrown away.
And if I wanted to get the .5 I could
do 5 remainder 2, which is the percent sign,
and that gives me the piece left over when I divide those two
pieces together.
Finally, I can raise something to a power.
And that is done right here with I. Two stars, J. So one star
is multiplication.
Two stars, gives me power.

### SIMPLE OPERATIONS

![](https://ws2.sinaimg.cn/large/006tNc79gy1fjc162w4b4j30si0lg798.jpg)

Once I've got that, I'm ready to start putting together pieces.
In particular, I've got different operations.
So I have to think about how do I put together pieces in ways
that control what I want to do?
And here, we're going to use parentheses
to tell Python in what order to do the operations.
There's a precedence to those operations.
And those are shown right down here, going in this order.
Exponentiation, powers are always done first.
Then multiplications, then divisions.
And then finally, additions or subtractions.
And overall it's done in a left to right order, as it
appears inside the expression.
And that means that as I change where the parentheses are,
I'm changing the order in which I'm doing things.
So to do an example, if I take 3 times 5 plus 1.
That's going to give me 16.
And that's because the multiplication is done first,
3 times 5 gives me 15.
And then the addition is done, to give me 16.
On the other hand, if I say 3 times,
and then in parentheses 5 plus 1,
the parentheses say reduce this expression first.
Add 5 and 1.
That gives me 6.
And then do the multiplication, which gives me the 18.

As a consequence.
I can create very complicated expressions.
And I will simply use parens open
and close-- to define what operations to do first.
Always **simplifying inside out**, before then using the operator
precedence order, in order to decide what
the expression actually means.

## Video: Variables

2017-09-09

`01_06_Variables_MITX60012016-V000200_DTH.mp4`

...
So we've now seen primitives.
We've also seen means of combination, simple arithmetic
things, expressions that we can use to compute values.

### BINDING VARIABLES AND VALUES

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjd5001m3aj30si0la10u.jpg)

I said earlier there was one last piece, abstrac tion,
ways of giving names to things.
So I can refer to a value just by its name and reuse it.
We're going to see other kinds of abstractions
as you go along, but that's probably
the most important first one.
And so we can now introduce that into our programming language.
In Python, we do an assignment using an equal sign.
And you see an example of it right here.
There is an assignment of a name to a value.
And in particular, the value will just
be computed the normal way.
In this case it's simply that float.
That's what we call a variable.
It's a name.
And the equal sign gives us an expression
called an assignment that says bind to
or associated with the name pi the value 3.14159.
Once we have that, we can use pi wherever we would like.
So in fact if I go over to my machine
and I do the same thing, I say pi is equal to 3.14159.
If I now ask for the value of pi, it prints it back out.
I've bound pi to a number.
I could do other things.
I could give an approximation to pi.
And I want to put this one up because I want to remind you
that if I were to use double slash,
I would get just the expression 3.
But here it's going to give me something a little different.
And if I do pi approx, I say 22 divided by 7,
and I ask for that value, I get a little bit better,
or maybe not better representation of pi.
That value is stored away in computer memory.
It's in something we call a name table where the variable pi has
associated with it a value.
And as we said, we can just retrieve it
by asking what's the value associated with that name.

### ABSTRACTING EXPRESSIONS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjd50fd1xtj30si0laq7f.jpg)

Once we have that, we can start putting together
more complicated expressions.
So why will we give names to values of expressions?
Couple of reasons-- one is I want to just reuse the name
and not redo the computation to get the value.
If I actually had some very complicated arithmetic
expression that reduced to a simple value,
I don't want to redo it every time.
I just want to give it the name.
The second one is it can give me code that's
much easier to understand.
The name ought to be informative.
It lets me think about what it's telling me
about what this represents.
And finally it's going to be easier to change the code later
if I've just got a name and I want
to change the binding of the name and reuse it.
So here's a simple example.
I can bind pi to a value.
I can give a radius, say 2.2.
And then I can compute the area, pi r squared.
And that'll give me a simple little computation.
Those expressions also tell me something about what
I'm trying to capture.
And so those names turn out to be really valuable.

###  PROGRAMMING vs MATH

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjd54h4qjgj30se0le11s.jpg)

One of the things to keep in mind
is that this is simply following the sequence of steps
we talked about.
It's not like doing math.
In programming, you do not solve for x.
So for example in this little example,
I define pi to be 3.14159.
I set up a radius.
This is just a comment.
We're going to come back to that.
That hash sign says it's just something
that's going to be there for me to read.
The computer doesn't do anything with it.
I can now compute the area.
And then I can decide I want a different radius.
And in fact look at this expression
here, because what it says is get
the value of this expression, which is what's
the value of radius, 2.2.
What's the value of one-- 1.
Add them together, that gives me 3.2.
And change the binding so that radius is now 3.2.
This does not change area.
It's not like a set of mathematical expressions.
It's simply following the sequence
of instructions we gave it.
And that means that if we want to do something different,
we would need to recompute area.
Again, I just want to repeat what we
said, because it's important.
An assignment statement says, find the value
on the right hand side of the expression.
Take the name on the left and assign that name to that value.
One last thing-- we're going to see a lot of shorthand here.
That expression, adding 1 to something,
it's something we're going to do a lot.
It's called incrementing.
And so there's a shorthand which is you could write this instead
as just +=.
And that is simply short for saying radius += 1 is radius
equals radius incremented by 1.

### CHANGING BINDINGS

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjd56vul6qj30se0lg7e5.jpg)

The last piece here is you saw we could change the bindings.
I can rebind a variable name in a new assignment statement.
The previous value may still be around in memory,
but it's lost.
There's no handle, no way to get to it.
And as we just saw, the value for area
doesn't change until you tell the computer
to do the calculation again.
Another way of thinking about it is, if this cloud is my memory,
when I do a binding for pi, it associates the name pi
with a value off in memory.
When I do radius, I get the same thing.
When I compute area, it looks up radius, squares it,
multiplies it by pi, and then associates the name area
with that value in memory.
And now if I change radius, it loses that first association
and creates a new one.
But area hasn't changed.
If I wanted to recompute the area for this circle,
I would need to do another call to area to make it happen.

## Video: Operators and Branching

`01_07_Operators_and_Branching_MITX60012016-V000300_DTH.mp4`

...
So we've now seen the beginning of programming.
Simple expressions, ways of putting them together
into more complex things of means a combination,
and the very first version of abstraction,
giving names to things.
But so far, all we've been able to do with these pieces
is just behave like we're a simple calculator.
We can do arithmetic.

### COMPARISON OPERATORS ON int and float

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjitvsnrdpj317i0wi0w7.jpg)

Let's add one more piece in, which
is the ability to make decisions based on tests.
And for that, we have to compare things.
We have to decide, am I close enough to square root
that I'm done?
Am I close enough to something else that I'm done?
So we have to be able to compare things.
And since so far we've just talked about numbers,
what are the comparison operators
for integers and for floats?
They're the things that you might expect from arithmetic.
If i and j are any names of variables,
they have values as numbers, then
we have ways of testing if something is greater
than something else, if something
is greater than or equal to something else,
less than, less than or equal.
So is 2 less than 3?
And if I do a simple example over here.
2 Less than 3, returns true, that's good.
2.0 greater than 3.0?
Returns false.
Also good.
Is 2 less than or equal to 2?
Returns true.
On the other hand, is 2 less than 2?
Returns false.
Simple comparisons.
I also want to be able to tell when something's equal.
And you might think, well, that's easy.
Is 2 equal to 2?
Wait.
We already used equal as an assignment statement,
so that won't work.
And as a consequence, equality is done with double equal.
Is 2 equal equal to 2?
So for example 2 equal-- try that again.
Returns true.
And then finally, if we want to know is something not equal,
we use the exclamation point followed by the equal sign.
Often referred to or pronounced as bang equal or not equal.
That will return true if i is not equal to j.
Simple comparisons.
They're going to let us build the very first kinds
of programs that are going to let us make decisions.
Because based on whether something is true or false,
I'm going to be able to decide which operation I
want to do next.
You're going to get a chance to explore all of these,
but these make sense because they're simple arithmetic
things other than that double equal sign-- which
as I said, is there because equal is already reserved.

### LOGIGCAL OPERATORS ON bools

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjityphyytj317g0wigok.jpg)

Once we have logical expressions,
we also need to be able to combine them.
I might want to say, is something less than this
and greater than something else?
And so if I have two expressions that are Booleans
I can also combine them using either and, which
is true if both are true.
Or, which is true if either of them are true.
And of course, not, which will be the opposite.
Not a is true of a is false.
It's false if a is true.
Once I've got those pieces, I can
put together more complicated expressions to decide tests.

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjiu0wtjukj31000fm1kx.jpg)

How might we use these?
Well, here's a simple little example.
This is actually a map of MIT.
MIT students are always looking for free food.
So imagine there's some food stored away somewhere at MIT.
And I want to give instructions to a student to find them.
All right.
This is a complicated map, but we could
use a simpler version of it.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiu1xv2rcj317m0wkgri.jpg)

I've got my student.
So over here with his backpack ready to
find that free food, which is a way over here.
And I want to think about how would I
instruct him to get there.
What would the test be that I might want to use?
Well, I might say, if you can go to the right,
keep going to the right.
On the other hand, if you get to the right and it's blocked,
change and go forward.
Unless both the right and the front
are blocked, in which case go to the left.
Unless all of them are blocked, in which case backtrack.
Won't be perfect, I could still get stuck.
But this will work pretty well to get my way through a maze.
What I've just described are four simple tests
to let me think about how I would instruct somebody
to solve a problem.
In this case, trying to find the free food.
Oh, yeah, I need one more thing, which
is to test when I found the food to know when to stop.
Simple tests.

### BRANCHING PROGRAMS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiu2q5w5oj317m0wedmn.jpg)

With those ideas, I can put together
the first kind of actually more reasonable
or interesting rather program called a branching program.
And it would say, in that case of the maze,
move forward unless a test's true.
That test might be moving to the right is blocked.
If it's not blocked to the right,
I'm going to do one thing-- keep moving forward.
If it is a block to the right, I'm going to move ahead.
And a branching program then simply consists
of a test, something that's going to return
a Boolean true or false.
If the test is true, it's going to have some code that tells
me what to do in that case.
On the other hand, if the test is false
it's going to have some code to tell me
what to do in that case.
And in either case, once I'm done with those pieces of code
I can pick up the rest of the computation.
You can see why it's called a branching program,
it takes one of two branches based on that test.
In Python, we don't necessarily have to have the false block.
We have to have the true block.
If this is true, there should be something I would do.
But if it's not always the case that I
want to do something even when it's not true, I can skip that.
With that in mind, I can start now
building a little bit more interesting programs.
And so here's a simple example.

### A SIMPLE EXAMPLE 

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjiu3y43zxj317g0wmgoq.jpg)

There are some pieces here we're going to come back to.
Don't worry about them.
Pieces like input, which is going to give me
a way to read something in.
But what I want you to see here are the tests.
And the first case of a branching program
is an if-statement, that's a special symbol.
It is treated differently and when the Python evaluator
sees this it says, given that's an if,
I'm going to evaluate this expression, which
should return a Boolean.
It says, if the remainder of x divided by 2 is equal to 0--
notice the double equal sign there, if it's equal to 0,
if that is true, then I want to execute this set of code.
It's going to print out a blank line
and then print out the word even.
If it's not true, I need to tell it what to do.
And I use the special symbol else for that.
These are often called if-else expressions.
If this is true, do this.
Otherwise, do that.
And here again, I've got a block of code.
In this case, it's going to print out a blank line and then
the word odd.
In either case, when I'm done with all of that
I'm going to go down to the rest of the code.
Which is just going to print out a simple thing that says,
I'm done with this conditional.
You could type this in and run it, I invite you to do that.
But what I want you to see here is a couple of things.
This if-else structure.
And I said in a branch there should be three pieces.
And you can see them, there's the test.
There's the first block, that's the true block.
And there's the false block.
Now, how did I know?
Or rather, how did Python know those are the blocks?
Because of this indentation right here.
The fact that those lines of code are inset
are important, because it tells us
that's an entire block of code and when I get done here,
I'm going to pick back up the rest of the else.
And more importantly, when I get done there
it tells me where the rest of the code picks up.
A simple example of a branching program.

### SOME OBSERVATIONS

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjiu6c0zckj317g0wkgqu.jpg)

I've already said this, but I want to recap it.
I've got a test, it evaluates the true--
when in fact, in this case x divided by 2
has a remainder of zero.
As I've already said, notice the double equals sign rather than
a single equal sign to do the comparison.
As I've also said, the indentation
is really important, it tells us what
pieces are associated together.
And notice how that indentation gives us
a nice visual structure for seeing where the code is.
To see the semantic structure of the code.
What's the true block?
What's the false block?

### NESTED CONDITIONS

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiu7zq8xhj317g0wi77t.jpg)

Now, it turns out that you can have nested conditionals.
Inside of a block I could also have a conditional.
And that's perfectly fine.
It says, if this is true, then I'm
going to go in and look at this portion.
And if this is also true, I'm going to do that.
On the other hand, if this is true, but this is false
I'm going to jump down here and run that piece.
Again, I invite you to type this and try it.
But it's going to do something that
based on what the value of x is, it prints out whether it's
divisible by 2 and 3, by 2 and not 3, or by 3 and not 2
as it runs through that sequence of branches appropriately.

### COMPOUND BOOLEANS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjiu96871qj317i0wm0vm.jpg)

And finally, we can have compound Booleans.
As I said, I have things that can be combined.
This is a Boolean.
That's a Boolean.
And the combination with the end also gives me a Boolean.
So in this case, if x is less than y
and x is also less than z, then the combination is true
and I'm going to print out a particular thing.
Again, don't worry about what this actually does.
What I want you to see is the structure,
including one last piece, which is elif also shorthand
for else-if.
This says, if this test is true, do that.
But if this test is false, then see if this is true.
If that's true, do that.
But if it's false, then skip down.
In this case, there's an else and it will always do this.
I could have multiple elif statements.
It's a way of giving me a sequence of tests in order.
If this is true, do something.
If it's false, but this is true do something.
If that's also false, but this is true do something.
And so on.

### CONTROL FLOW - BRANCHING

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjiube2c6xj317i0win2b.jpg)

This just then pulls them together.
I've got a basic conditional.
If this condition is true, do a sequence of expressions.
You can also have an if and an else.
Or I can have an if, a sequence of elifs, and an else.
And again, notice how the indentation
tells us which things to do associated
with which block of code.

### INDENTATION

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiuen92rfj317g0wa0x8.jpg)

That indentation is how we are going to capture
other pieces as well.
And it doesn't have to just be conditionals.
I could have something that has other statements inside
of it, such as the print statement here.
Again, don't worry what this code does,
it's a simple piece of code to execute some simple comparisons
on numbers.
What I want you to see is how we walk through the branches.
And with that, we now have the first kind of code.
There is one set of blocks inside of which,
I've got another set of blocks.
And again, if this is true and that's true,
I'll get to that point.
But if this is true and this is false-- so true
here, but false here what happens?
Oh, there is no code here, so nothing happens.
It simply skips out to the end and jumps past it.
Again, I invite you to try this to see if it works
the way I've described it.

### = VS ==

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiugao6vrj317a0wg42w.jpg)

What I want you to see is the form of it.
One other piece I want to remind you of
is the fact that when we do comparisons
we need to use the double equal.
Equal sign binds a value to a variable.
Here I, want to compare two things.
And this is a standard place I make it all the time
where you'll get a bug.
Don't worry when you do it, Python is going to complain
at you saying you're trying to do a binding in a place that
you can't.
But remember, this is a place where
when I'm doing a comparison I want
to use the double equal sign in order
to make the comparison of two values and return a Boolean.

### WHAT HAVE WE ADDED?

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiuh4y99rj31780wgdjh.jpg)

OK.
What have we added?
First, simple kind of program.
Branching programs allow us to make choices
and do different things.
But it's still the case that at most each statement
gets executed once.
I might skip a set of statements if I skip over that branch,
because I don't get there.
But as a consequence of this, these
are what we would call linear programs.
They run in constant time because I execute
each instruction at most once.
And the maximum time to run the program
is going to depend only on the number of instructions
that I have there.
Still valuable to make some decisions,
but it's not going to give us the power that we
want to really build interesting algorithms.
And that, we're going to get to next time.

