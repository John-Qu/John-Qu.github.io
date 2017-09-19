---
layout: post
title:  "Transcripts in 4 Functions of MITx6001x"
date:   2017-09-19 09:20:21 +0800
categories: notes
---

This is a collection of transcripts of [MIT6001x 4. Functions](https://courses.edx.org/courses/course-v1:MITx+6.00.1x+2T2017_2/course/#block-v1:MITx+6.00.1x+2T2017_2+type@sequential+block@38007cdb67c44b46b124cdbce33510b5)'s videos. 

## Video: Decomposition and Abstraction

2017-09-19 09:22:15

...

1![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjowzdz0k1j319q0y2adj.jpg)

Let's think about what we've been doing so far.
We started introducing elements to our language.
We started off with simple things-- basic objects, ways
to do arithmetic operations on them, ways to compare them.
We introduced conditionals as a consequence of that.
And we started looking at the first version of ways
to actually put things together into pieces of code.

### 2 HOW DO WE WRITE CODE?![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjowzrjth2j319k0yg78x.jpg)

So we've covered language mechanisms.
We've also covered the first notion of for and while loops
and, therefore, of iteration.
And we've also seen that we could
write different kinds of computations,
each one in a different file that I save away on my machine,
so I can use when I want to do something with it.
Each file contains a piece of code.
And each piece of code is some sequence
of operations-- could be a simple branching program.
It could be an iteration like a for loop or a while loop,
could be something else.
This is fine when our code consists of a few lines.
This is fine when our problems are very small.
But it doesn't really scale very nicely.
As I start thinking about pieces of code that
might be hundreds or thousands of lines long, simply doing it
this way is a real challenge.
It's hard to keep track of the details.
It's hard to make sure that I've got
the right information in the right place in that code.
Does this go at line 95, or at line 296?

I need a way to really capture this better.
I need a way of structuring my code,
structuring my computation, so that I can think about it
much more efficiently.
And that's what we're going to introduce now.

### 3 GOOD PROGRAMMING![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjox0skm3oj319k0y2adl.jpg)

One of the things to keep in mind
is, in fact, good programming is more than just adding
more code.
In fact, I would argue that a good programmer is measured
not by the number of lines of code she's written,
but by the amount of functionality that she's
provided-- the ability to do computations easily.
And so to make that happen, we're
going to take a really nice pivot, introduce
a major new thing, and that's the idea of a function.
We're going to describe it in a second.
But the idea of a function is it's
going to give me a way to encapsulate
pieces of computation.
And in fact, a function is intended
to give me two really important aspects
of computational thinking-- decomposition,
sometimes also called modularity, and abstraction.
So what do those mean?

### 4 EXAMPLE — PROJECTOR

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjox1lyfi4j31920yc7d0.jpg)

Let me give you an analogy-- something
a little bit different.
I'm sure you've all seen a projector.
I think of a projector as a black box.
Now, the one I'm showing here happens
to have a black box around it, but my black box,
I literally mean a construct whose details
I don't understand.
In fact, most of us don't know what's inside it,
how it actually works.
If you open it up, you see a bunch of electronics.
And unless you're a really good electrical engineer,
you probably don't understand how it works.
It doesn't matter, because you know the interface,
you know the input-output behavior.
And in fact, that black box comes
with a standard interface, that says,
if I plug an appropriate piece of electronics
into it, that box can communicate with it.
And it's going to produce an output.
It's going to show slides on the wall.

That's the notion of abstraction.
It's the idea that once I've built something-- in this case
a projector, might be a piece of code--
once I've built something, I don't
need to know what's inside it as long as I know how it works.
So abstraction, in some sense, comes
with a contract that says, if you give me appropriate inputs,
I'm going to behave in an appropriate way.
That's a really nice idea.
That's something that we're going to want to use.
And we're going to use it with code.

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjox2ax8g1j31920ya1kx.jpg)

There's a second piece to it.
And we'll stick with the projector idea.
If you happened to see the opening
ceremonies for the Vancouver, Olympics,
there was a wonderful display in which
there was a huge multi-story-high structure
in the middle of the rink onto which images were projected.
Now, it wasn't one projector.
It was way too big.
It was a sequence of projectors.
Each of them took an input.
Each of them produced an output.
And they all worked together in synchrony
to produce that wonderful larger image.

That's the second big idea, decomposition,
that I can, in this case, take different devices,
have them synchronize, so that they work together
to achieve an end goal.
I want to use the same thing with code.

### 6 APPLY THESE IDEAS TO PROGRAMMING

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjox2q85atj318w0y2tca.jpg)

So we're going to apply those ideas to programming.
Decomposition-- I'm going to break a problem up
into different self-contained pieces.
And once I've built them-- or even better, once somebody else
has built one of them for me, all I need to know
is, what does it expect as input,
and what will the behavior be when it gives me an output?

And the second big idea, abstraction,
that I want to be able to suppress
the details inside that method in order
to be able to compute something using that computation.
And in fact, I just said them in the wrong way.
What I first described was really abstraction.
Decomposition is that idea of breaking it up
into smaller pieces.

With those two things together, we're going to now look at,
how do we make programs have those two properties

### 7 CREATE STRUCTURE with DECOMPOSITION 

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjox3qk130j31900y079e.jpg)

Inside of code with decomposition,
we're going to do the same thing we
did when we talked about having multiple projectors working
together.
When I'm going to structure a big piece of code,
I'm going to divide it up into modules.
And those have the property that they're self-contained.
That means, they have everything they need inside of them.
I'm going to use it to break the code up into pieces that I
can separate apart.

And they're intended to be re-usable.
I can use them multiple places.
If you think about it, so far, even if I have a little file,
I can only use it once.
Or if I want to reuse it, I've got
to go back and recall the file.
Here, I'm going to structure code so that I
can use it in multiple places.
And we're going to see that this idea of dividing code
into modules is both going to keep the code organized
and coherent.
It's going to be easier to structure.
Today, we're going to do decomposition with functions.
And in a few weeks time, we're going
to see how to do decomposition with classes,
an equally powerful idea.

### 8 SUPPRESS DETAILS with ABSTRACTION

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjox4ei5j4j318m0y8jw0.jpg)

We're going to suppress details with abstraction.
Again, I said with the projector,
I don't need to know what's inside.
I just need to know what it does.
In programming, we're also going to think of a piece of code
as a black box.
I don't need to see the details inside once I've written it,
or especially if somebody else has written it for me.
I, in fact, don't want to see the details inside.
What I simply want to know is that it's
going to work the way it was advertised.
And we're going to achieve abstraction
with something called a function specification or a doc string.
And in a second, we're going to see examples of both of those.

But there is the idea-- abstraction, decomposition,
two powerful ideas that we want to capture
inside a computation.

### 9 DECOMPOSITION & ABSTRACTION

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjox4x4q9wj318a0y4q5p.jpg)



One of the things that comes out of this
is, not only do they work well together,
but that can then be used many times.
And in fact, not only can they be used many times,
I only have to debug it once.
It's one piece of code.
If I want to make a change to it,
I change that piece of code.
Anything else that depends on that code
will inherit that behavior, because they simply
depend on that code.

## Video: Functions and Scope

2017-09-19 10:08:36

...

### 11 FUNCTIONS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjox5m43rhj31860y40wx.jpg)So how do we create this notion of abstraction
and decomposition in Python, or actually
in any programming language?
And the answer is, we introduced the idea
of a reusable piece of code, or a chunk of code,
called a function.
Functions are not going to be run in a program
until we actually ask them to do that.
So as opposed to things I was typing into my shell--
every time I typed in an expression,
it was invoked or evaluated-- I'm
going to create a definition of a function.
And when I read that in, it's simply
going to create the ability to do that computation,
but not actually call it.
And we'll see an example of that in a second.

What are the characteristics of a function?
Several.
First, it has a name.
That makes sense.
I've got to be able to refer to it.
In the same way that I had a variable as a name for a value,
a function will have a name.
It will also take a set of parameters.
These are arguments or values that I'm
going to use inside the function when I do a computation.
It's going to make sense in a second
when we look at an example.
Every function has to have parameters.
But the number of parameters could be zero.
Or it's a funny way of saying, it's
going to take in a parameter list,
but in fact, it may need no parameters.
And I'm going to decide when I create a function how
many parameters I need.
We'd like every function to have a doc string.
That is a documentation that tells me
what the function does.
We'll see an example of that in a second.
And finally, a function has a body.
And the body is the sequence of commands or instructions
that we want to actually have happen
when we use the function.
Those are a lot of words.
Let's look at an example to get a sense of this.

### 12 HOW TO WRITE and CALL/INVOKE A FUNCTION

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjoxdr0pk1j318i0ycgrk.jpg)

Here's a definition of a function.
And I'm going to walk through each of these pieces.
So the first part of it is I've got a keyword, in this case
def.
And it is a key word, meaning it's
a special symbol to Python that tells me
I'm about to define something.
In this case, I'm about to define a function.

That is followed by a string that
is the name of the function.
In this case, it's is even, or is underscore even.
That's the name I'm going to give to this function.
That is followed in parentheses, in those parens,
by zero, one, or more parameters.
In this case, I've got one.
And I'm giving it a name.
Think of it like a variable name.
Well, I'm saying, I'm going to use the name
i as the name for a parameter inside this function.
And that's then followed by a colon
to tell me I'm done with the top line of the definition,
I'm about to follow it with other information.
So keyword def, a name, and in parens
some number of parameters.

Immediately below that in triple double quotes--
which is a wonderful expression-- is a docstring.
It's up to you how to use this.
But traditionally, you would specify
what's the input to this function
and what's the output of this function.
It's a little bit like a contract.
In this case, I'm saying I'm expecting one input.
I'm calling it i.
And it's a positive integer.
And what I'm going to return is true if i is even.
Otherwise, I'm going to return false.
As you'll see in a little bit, one
of the nice things about a docstring
is, once I've defined this function, if I go to call it,
which I'm going to get to in a second, Python will
automatically bring up a little window that tells me
the docstring that's remind me what
the conditions for this function are, which is great.

So keyword, name, parameters, I've got a docstring.

Immediately below that is the body of the function.
This is the sequence of commands or expressions
I want to evaluate when I'm ready to use this.
Notice the indentation-- all of this is indented here.
This is telling me where the body of the function is.
And in fact, it will be everything
until I get back to something that
returns to the left hand side of the editor or of the shell.
In this case, I've got two expressions in my body.
It's going to print out simply the string hi.
And then it's going to return a value.
We'll come back to the return in a second.
There is how I write a function.

Now, how do I use it?
The function has a name.
The same way I could use a variable
as a name inside of an expression,
I can use the function name.
And in particular, later on in the code,
I can say an expression like, is underscore even,
and then an open paren, followed by an expression whose value
I'm going to use inside of that procedure
followed, in this case, by a closed paren, because there's
only one parameter.
I call this invoking or calling the function.
I'm using the function.
We're going to look at some examples in a second.

But the basic idea here is that, when I call this function,
I'm going to take the value 3, in this case,
and everywhere I see an i in the body of the function,
I'm going to use that value in place of i.

### 13 IN THE FUNCTION BODY

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjoxe1zfohj318m0y80wi.jpg)

And in fact, if I look at it then,
inside of this particular expression,
I'm going to print out simple the string hi.
And then I'm going to evaluate this particular expression.
And it has the keyword return followed by an actual value.

Now, I just said, in this case, if I've
called is_even with the parameter 3,
i now holds the value 3.
So I'm going to evaluate 3 remainder 2 and say,
is that equal to 0?
In this case, it's not, because the remainder is 1.
And I'm going to then return that value to whoever
called this function.
So that's the expression I want to evaluate and actually
return.
So return is a keyword that tells me
I'm ready to stop the computation.
And whatever the following expression is,
that is the value I'm going to give back
to the person who asked for it.

In this case, it was simply at my shell.
But we'll see in a second, it could
be somebody else that's going to use it
as part of another computation.

## Video: Calling Functions

2017-09-19 10:24:03

...

### 15 VARIALBE SCOPE

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjoxefvqtmj318c0y2dlj.jpg)

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjoxezx31xj31840ycjw8.jpg)

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjoxfacqlpj317q0y4jwa.jpg)



This idea of function invocation-- function calling--
is really important.
It's central to how we're going to use
functions to control our code.
So I want to work through in a little more careful detail
exactly what happens when we call a function
and how we get values associated with variables.

You'll see on the screen here, I've
got a little piece of code.
I'm defining a function called f.
I'm binding x to 3, and then I'm going
to call f with the value of x and bind that to z.

Let me show you what happens if I actually run this.
So on my computer, I've got a version of that file.
And I'm going to load it into my shell.
And what it prints out, as you can see, as it says in f of x,
x is equal to 4.

How'd that happen?
What's going on here, because x seems like it's
used in a lot of places?
So this is going to be an important opportunity
to look at how functions are called.
As I've already said, the key idea is each formal parameter--
in this case, I only have one-- is
going to get bound to the value of the actual parameter
when the function is called.
And then when I call a function, I'm
going to create a new environment,
sometimes called a frame or a scope,
a new place in which I'm going to bind variables
and relative to which I'm going to evaluate
the body of the function.

Think of that scope as a mapping of names to objects.
And, in fact, we've been using that idea when we were just
talking to the shell, when we defined
x to have a value of, say, of 5, we were creating
in the global scope or frame a binding of the name
x to the value 5.

Now, let's look at this in a little more careful detail.
Imagine I now do what I just did on my computer.
I evaluate this sequence of expressions.
There is that formal parameter.
There's the actual parameter I'm going to use,
and let's look at what happens.
I evaluate that, and in that global frame,
I create a set of bindings.

First one is evaluating that definition
binds the variable name f to something.
Oh, but that's important, because that something is just
a set of code.
I haven't run f yet.
I haven't tried to do x equals x plus 1 or anything else.
I've literally, in the machine, said associate the name
f with a chunk of stuff.

Next thing I did was I evaluated x equal 3,
and that just creates a binding.
We've seen this before.
So in the global scope, x has a binding to the value of 3.
And now I'm ready to evaluate that last expression, which
says give the name z the value of calling f on x.
And I'm ready to do that.
Now remember, before I can actually do the binding of c,
I have to get the value of that expression.

So calling f literally creates a new scope, a new frame.
It will actually inherit things from the global frame
if it needs it, but right now I've got a new environment.
The definition of x has a formal variable
x, and that's exactly what that corresponds to.
And the value associated with it is
the value of x that I passed in, which actually came from there.
I know it looks a little confusing.
I'm deliberately using two different values
of x so you can see where the bindings come from.
So f evaluated on x says, what is the value of x?
I get it from the binding that I just did previously.
So inside that f scope, x is bound to 3.

Now, relative to that scope, I'm going
to evaluate the body of f.
I want to do the work that f says it's going to do.
So let me see what happens there.
First expression says, evaluate x plus 1,
and I'm actually going to go back for a second.
Remember, in the f scope, x has the binding of 3.
I add 3 plus 1, that 4, and I create a new binding
for x but in the f scope, because that's
where I'm doing the work.
So it changes it here.
It does not change the thing that
was out in the global frame.
That's great.
Now, relative to that, I'm going to print out something,
and on my computer screen you saw
it said, in f of x, x is equal to-- ah--
the value of x in the f scope.
And that's why it printed out 4.
And then what it's going to do is it's going to return x.
So literally it's going to get the value of x
in the f scope, which is 4, and it's
going to return it to the person who asked for it.
And what was that person?
That was down here.
We're doing the binding of z.
So I've just returned to that binding,
a value for f of x, which is 4, and that
creates the binding for z.

If this is a little confusing, watch the same segment again,
because this is an important idea.
Any time I do an evaluate-- sorry, rephrase
that-- any time I do an invocation of a function,
I create a new frame.
I bind the formal parameter of that function, or parameters
if there is more than one, to the values
of the expressions passed in.
And relative to that frame, I now
evaluate the body of that expression.

When I'm done with the body of the function,
if there's a return, I'm going to send the value back
to whoever called for it and erase or remove that frame
because I no longer need it.
OK.
With that idea, let's look at a couple of other examples.

### 19 ONR WARNING IF NO `return` STATEMENT

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoxg0u1rqj318q0yc0wx.jpg)

First, what happens if there is no return statement?
Here's my function from before-- is even.
But rather than returning is the remainder of [? r ?] divided
by 2 equal to 0, I just have the expression.
So there's no return here.
What happens in this case is that Python returns the value
none, because I did not give a return.
So Python will say in a function call,
if you don't have an explicit return,
I return the none value.
It represents the absence of a value,
and unfortunately that would mean, in this case,
I would not get back the answer of true or false.
I would simply print out nothing, because there's
nothing to be returned.

Point of this is, any time I want
a function to do something, unless it's simply
doing something we call a side effect,
I always want to have at least one return that's
going to give a value back.
So remember to keep your returns in.

### 20 `return` vs. `print`

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoxh3nsa5j31840y4jx6.jpg)

In fact, that gives me a chance to talk about the difference
between return and print.
You can see the description here,
and let's just do it quickly.
Return only has a meaning inside a function.
It's the only place we can use it, inside a function.
I could have more than one return.
If I have branches or other conditionals,
I might have different places from which I want a return.
But only one return will ever be executed inside the function,
because it's going to throw me outside of the function
and return a value.

Any code inside the function but after the return statement
will never be executed.
And of course, a return does have
a value associated with it.
It's given back to the person who called the function.

By comparison, while return has a meaning only
inside a function, a print can certainly
be used inside a function, but it can also
be used outside of a function.
We've already seen that.
We can also execute many print statements inside a function.
And any code inside the function after that print statement
can, in fact, be executed.

Again, a print has a value associated with it,
but it is simply output directly onto the console
rather than being returned.

So prints are going to be handy to have us pass information
back to the user to let them know
the status of a computation.
Return is the way in which I'm going
to get a value back to somebody who asked for it, whether it's
me as the user or some other function call.

### 21FUNCTION AS ARGUMENTS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjoxie0nn0j318q0yiagj.jpg)

With that in mind, let's look at,
in fact, how you might have other function calls.
So not only can parameters have numerical values,
they could also have another values,
including being a function.
So I have three definitions of functions here.
The first one, A, takes no parameters.
I've said this earlier, but I'm going to say it again.
Notice it has an open and close paren.
That's important.
I have to tell it that there are no parameters there.
Function B takes one parameter, in this case called y.
And function C also takes one parameter, in this case it's z.

What's interesting about this is how these functions
are going to use them.
And in a second, I'm going to run it.
But notice I'm going to call function A with no parameter.
So an open and close paren to tell me there
are no parameters.
I'm going to call function B. It's
going to take in one parameter.
In this case, I'm going to give it a number.
And function C is going to take in one parameter,
but in this case it's another function.

Whoa.
That's funky.
It's actually OK.
I can pass in the name of the function,
and that will literally pass the actual function
in to that parameter call for function C.
Let's see what happens if we try this.
So I've got that code loaded up over here.
I'm going to pass it into my computer.
And notice what it printed out.
The first thing is it printed out inside function A.
That came from calling this function,
and that's the print statement right there.
There is no return in function A.
And so, in fact, the print takes the value returned
by function A, which was none, and it printed it out
on my computer.
I then take the next call.
I pass into the function B. Function B
prints inside function B right there,
which is the next thing it did.
And then it returns the value passed in, which
is the value of y, which is 2.
That gets out at the 5, which is why on my machine
I printed out 7.
The print statement printed out 7.
And then the last one, again, a little funky.
I passed in function A as an argument for z in function C.
And what happened?
It printed out inside function C,
and then it called a return of calling z with no arguments.
And what's z?
It's function A. Oh, that's nice, because function A then
said print out inside function A, which it did.
Return nothing, because there is no return statement.
And so this print at the bottom then printed out none.
We could step through it more carefully,
but you hopefully get the idea.
In each case, I'm simply evaluating the body
with respect to a frame.
And the arguments could, in fact,
be other functions that I can invoke inside
of a function call, which I did inside of function C.

### 22 SCOPE EXAMPLE

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjoxixwk1bj31a00yiahe.jpg)

So as a consequence, inside of a function,
we can both access a variable defined outside
as well as a variable defined inside.
On the other hand, inside of a function,
we can't modify a variable that's
defined outside of the scope of that function.
And here I have three little examples just
to give you a sense of that.

What I'm going to do is show you basically
what would happen for each one of these function calls.
So I've defined f of x to be set x equal to 1, add 1 to x,
and then print out the value of x.
I've define g to simply say print x,
and then print x plus 1.
And I've defined h to have a body that
says simply increment x by 1.
And I want to think about what do those things actually do?

Well, let's look at each of those examples.
In each case, I'm going to define x to have the value 5.
I'm going to call the function with that value of x,
and then I'm going to print out x.
What happens?
In the case of f of x, x as 5 is passed in.
I redefine x to be 1 inside of there.
And then I add 1 to that value of x, which is 2,
and then I print out x.
So, in fact, f of x is going to print out the value 2.
And then this print statement is going to print out the value 5.
Why?
Because it sees the value of x defined in the global scope,
which is where I am.
What happens in the case of g? g says-- well, first of all,
I called g with the value of x, which
is 5, which means 5 is going to be used in place of y.
And then I say print x.
Hmm.
You say, wait a minute.
There is no x as a parameter to g.
That's fine, because it then says
if I can't find it in the frame associated with g,
let me look outside.
And there is a value, which is 5.
So in this case, it's going to print 5,
then it's going to print 6, which is x plus 1.
It has no return.
So it's not going to do anything else.
And then I'm going to print the value
of x, which I get from here, the global environment.
And it's going to print 5.
Finally, I define h of y.
I've done that.
I've defined x to be 5, and now I call h with the value of y
being 5.
And what do I do?
I'm going to print out-- sorry, not that.
Rephrase that.
I'm going to try and define x to be x plus 1.
And let's think about what happens.
So just to go back to this, I've already
defined x from outside g.
That's why I pick up that scope.
What happens in the case of h?
Oh, I got an unbound variable error,
because I'm trying to look up the local variable value of x.
I'm referencing it before I've assigned it.
So, in fact, I'm going to complain about this,
and I'm not going to succeed.

So we can see, I can look up values outside the scope,
but I can't change the values of those things
outside of the scope appropriately.
And that's a place where I have to be
careful about how I actually use these different procedures.

### 23 SCOPE EXAMPLE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjoxj9m0gzj319e0yejw1.jpg)

Three different examples shows you different ways
in which we can deduce how we actually pick up
the values of the variables.
In each case, as I said, the x comes
from the global or main program scope
when I print out this value at the bottom down here.

### 24 HARDER SCOPE EXAMPLE

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjoxzc8j7pj31940yg78m.jpg)

I'm going to show you one more example of scoping.
I want to do a quick aside, which
says when you get to really tricky things,
there's a nice place to go look, which
is this place on the web called the Python Tutor that helps
you sort these pieces out.

### 25 SCOPE DETAILS

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoxzmik1aj319e0ygade.jpg)

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoy04ocalj319m0yaq6b.jpg)

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjoy0cmay1j317a0y877r.jpg)

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjoy0q6kczj319w0yedjk.jpg)

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoy0wmke0j319o0ye0wq.jpg)

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjoy11hrdmj319k0ya41i.jpg)

And the last example, before we move on to other topics,
is to look at something that actually has a function defined
inside another function.
Wow, that sounds neat.
Here I've got a definition for g, and inside of there,
I've got a definition for h.
And if I look at this code, I'm going
to actually run it over here.
Let's see what happens when I run it,
and let's see why it does that appropriate thing.
And when I ran it, it prints out the statement
inside g of x, x bound to 4.

And I want to see how that comes about.
So here we go.
When I evaluate or when I just, in fact,
evaluate it inside my machine, this description, here's
what happened.
As I saw before, in the global environment,
g was bound to a bunch of code.

Where is h?
It hasn't happened yet.
It's simply sitting in a chunk of code.
We have not yet evaluated that body.
So nothing has happened yet.
x is bound to 3.
So when I get to the point shown by the arrow here,
this point in the code, I've got g as some code.
I've got x bound to the value 3.
Now I'm ready to do a binding for z to be a call to g.
We saw it happen before.

g creates a new scope, and inside of that scope
I'm going to bind the value of x.
And that x is coming from the formal parameter for g.
The value is coming from the binding
for x in the global scope.
So x is bound to 3.
And then I'm going to evaluate the body of g.
And this is cool, because that says inside of here,
I'm evaluating the definition of h.
This is sometimes called an internal or helper function,
because it belongs only to g.
The binding for h right here is to some set of code.
Only when I'm inside of g can I use h.
It's protected.
That's great.
Haven't used it yet.
I've just got a binding for h.

And then what do I do?
I create a binding for x, and notice what happened.
I say get the current value of x, which was 3, add 1 to it,
and then change the binding for x in the scope of g,
because that's where I'm doing the work.
So it's changed that binding for x but not this one
over here, which is still 3.
And then I do the print statement,
which is why it says in g of x, x has got the value 4.
Because, in fact, I see this value of x over here.
All right.
Almost done.

Now I'm going to call h.
How?
H is a function.
It's right there.
And since I'm invoking it, I create a new scope.
And this scope inherits from g, which inherited
from the global scope.
Inside of h, I bind any formal parameters.
There aren't any.
What do I do?
I evaluate the body of h.
So I bind x to the string abc, and then what do I return?
Oh, yeah.
Nothing.
Because I have no return statement.
So having done that binding for x, I'm done with the call to h,
and there is nothing to return.
Having done that, I'm now ready to do the last part of g,
which was to return x.
And you notice that binding inside of h, of x equal to abc,
it's gone.
It's been garbage collected.
And so I now simply return the value x, which I know
is defined inside the scope of g.
And that gets returned as the value that I associate with z.
Perfect.
I'm now set, because z has the binding 4.

So there is a more complicated example,
but you notice how those rules for scopes
very nicely tell me and, more importantly,
tell Python exactly how to look up values
and how to use those to store new values as I do bindings.

## Video: Keyword Arguments

2017-09-19 11:53:05

...

32

Now that we've introduced the idea
of a definition, a function in particular,
as a way of doing encapsulation of information,
we can start exploring some of the variations to them.
And I want to show you one place in Python this actually
can be very handy.
And that is that I can have a function definition
that I can change in terms of how I want
to think about invoking it.
So let's start with a simple function here.
This is a very simple function that
says if the last argument is true,
then I'm going to print the last name comma first name.
Otherwise I'm going to print the first name comma followed
by the last name.

And I'm going to expect those to be strings.
And I've got a simple little implementation over here.
I'm going to import it into my Python shell so I can use it.
But at this stage, you can hopefully look at this function
and realize, given some value for reverse,
I'm going to test that.
If it's true, I'm going to do this, which is just to print.
It's not going to return anything.
If it's false, I'm going to do that.
OK?

33

Now, here's one of the nice variations on it.
First of all, that first call does what I'd expect.
And, in fact, if I go to my Python and type
it in, I can say if I do print name--
and I'll do myself-- of Eric Grimson,
and I give false as a value for reverse,
it prints it out in the order I expect it.
I could do, by the way, the same thing.
I could say print name just to show you
it does the right thing of Eric and Grimson.
Notice the commas, by the way, to separate the parameters.
And I give it true.
It would help if I can type.
So I'll do it one more time with Eric Grimson and true.
Now it prints it out in the other order.

But here are some of the variations.
I could say explicitly give the binding to the parameter
name reverse the value false.
So doing it in the same place, but I can actually specify it.
I could similarly for any of the parameters in the invocation
literally say the parameter followed by an equal sign
and the value that I want.
And all three of these are going to print out
exactly the same thing.
And, in fact, so will the last one.
But notice here I have reversed the order.

So if I'm not going to use this kind of formalism,
I have to give the parameter in the place it expects.
But in this case, I reversed it.
Even though the function expects first name then last name,
I've said I'm going to have last name have the binding
Grimson, first name have the binding Eric,
and reverse equal to false.
That's nice if I forget the order
or if I just decide I want to call them in a different way.

34

I can do some other things here though.
I can change the definition of my function to give a default
value to one of the parameters.
In this case, the syntax is there's the parameter name,
and I'm saying let it have initially the binding of false.
And that means that if I call the function, as I do right
here, without an explicit parameter passed in,
or value passed in for that parameter,
the default holds true.
In this case, I'm going to assume that reverse is false,
and therefore I'm going to do this particular print
statement.

Now, on the other hand, if I want
to change the value of that, I need
to give it an explicit value to overwrite the default value.
And this is handy if I've got a parameter that normally I
expect just to have a particular value, but on a rare occasion
I might want to change it, my invocations
don't have to always pass in those values.
So a nice little variation on how we pass
values into parameters of definitions of functions.

## Video: Specification

2017-09-19 11:58:04

...

36

We've now begun to look at functions.
We're going to do more of those in a second,
but it's important to take a little break here
to talk about one other piece of a function
and that was the idea of a specification.

This is something we're going to use
to be able to decide how we want to use a function.
And think of a specification therefore, as a contract.
We don't enforce it necessarily, but it's
a contract between the implementer
of the function and the people who are going to use it.

That specification ideally will say here are the assumptions.
Here's what the implementer of this function assumed
was going to be true, especially about the values of parameters.
If you like, it's the conditions that a client
needs to guarantee are true before they use it.
And then if those assumptions are in fact
met the second part of the specification
are the guarantees.
It says, here's what the function
will do provided it's been called in a manner
consistent with the assumptions.

37

The way we do it in Python is to use this idea of a docstring,
and there's my earlier definition of is even.
It has a condition on the input, it says,
if you give me an integer which I'm calling I,
in particular a positive integer,
then here's what I guarantee-- that it will return true
if I is even, otherwise it's going to return false.

Now, you're not required to put in a doc string or a spec,
but good programmers always do.
In part because somebody else might use this
and you want to tell them how you expect
it to be used or because a year from now, two years from now,
you may come back to this function
and you'd like to know what was I thinking when I built it.
So I encourage you to build your own docstrings even though it
takes a little more time because it helps
you understand what's expected of a piece of code
and where can I use it.

## Video: Iteration vs Recursion

2017-09-19 13:58:37

...

39

Let's go up a level just for a second.
What have we've built so far?
Simple objects, the idea of iteration,
for and while loops as a way of doing
particular kinds of computations,
reusing the same piece of code over and over again.
And now we've introduced the idea of functions
as a way of capturing that code.
That puts us in a position to introduce another really
big idea in computer science.
And that's the notion of recursion.

I'm going to show you an example of recursion in a second,
but let me give you the sense of what recursion is about.
Recursion is going to be a nice way to design solutions
to problems by breaking it up into pieces that I can reuse.
Divide and conquer, or decrease and conquer,
are words that we're going to use around here.
And it's, in particular, a programming technique
where inside of the function, it calls itself.

So I'm going to define a function, say f.
And inside the body the function,
I'm actually going to call f.
Now, this is the kind of thing that in high school geometry
class, you could get into trouble.
Right?
You don't define something in terms of itself.
But in recursion, as long as we don't set up an infinite loop,
we don't call it infinite numbers of times, we're fine.
And so we're going to see in recursion
that as long as we have one or more base cases
that are really easy to solve, and can be solved directly,
then I can solve a problem by reducing it to a solution
to a simpler version of the same problem
until I get down to a simple base case.

That notion of recursion is going
to nicely amplify iteration.
It's going to give us a much more simple way
of thinking about how to break problems up into simple pieces.
And so we're going to spend the next portion
of this lecture just looking at different ways of using
recursion.

40

If you think about iterative algorithms,
to set the stage for recursion, what do we have?
They're basically looping constructs.
And they are captured by the idea
of having a set of state variables
that update each time through the loop.
So I got a while loop or a for loop.
In the case of a while loop, we talked
about setting up the variable outside the loop,
inside the loop, changing it, usually decreasing it,
until I got down to a state where I'm done.
And then returning a value.
That's what an iterative algorithm does.

41

So here's a simple example to think about that.
Suppose I wanted to do integer multiplication.
And yeah, I know that already happens in Python,
but I want to use it as an example.

I could think about multiplying a by b as the same thing
as adding a to itself b times.
So it's really, if you like, a plus
a plus-- I've got b of those.
That's the same thing as a times b.
Iteratively, I would solve this by saying,
I want to capture the state of the computation
with an iteration variable, let's call it i.
I'm going to start it off at b because I've
got b additions to do.
And a current state of the computation,
I'm going to call it result. And I'll start that off at 0.
And then my iteration is to simply, at each stage,
do one more addition and reduce that variable by 1,
that iteration variable by 1.
And down here at the bottom is a function to do that.
Multiplication iterative.
Takes in two parameters, a and b.
It sets result when I call it to 0.
And then it runs the iteration I would expect,
that little loop right here, that
says as long as b is bigger than 0,
I'm going to change result by adding a to it.
I'm going to reduce b by 1.
And I'm going to keep doing that until b gets down to 0,
in which case, I'm going to return the result. Cool.

Nice iterative way of trying to make that happen.
There's the iteration.
There's how I'm changing the computation.
There's where I'm changing the iteration variable.
And when I'm done, I'm simply going to return the result. OK.
I'm not going to run it.
I encourage you to try it yourself,
but you'll see that it actually does
the multiplication I'd expect.

42

With that in mind, now let's look at a recursive solution
to this problem.
And here's a way about thinking about this idea of doing
successive additions to compute multiplication recursively.

Again, a times b is adding a to itself b times.
But I could think of that as saying,
that's the same as adding a to-- adding a to itself b minus 1
times.
OK, you say.
That sounds like semantics.
It is, but it's an important point.
Because what's this?
That's just a multiplied by b minus 1.
Ooh, that's cool.
Because now I've taken a problem and I've reduced it
to a simpler version of the same problem plus an operation
I know how to do.
OK.
What's a times b minus 1?
Oh, I know how to do that.
That is just a plus a times b minus 2.
I could do exactly the same reduction.
And I could keep unwinding this computation.
I need to stop somewhere.
I could keep unwinding this computation
until I get down to a base case, something
that I know how to do.

And what's the base case?
When b is equal to 1, the answer is just a.
And boy, that's nice, because there's
a recursive implementation of multiplication.
Inside the body it says, if b is equal to 1, that's
my base case, just return a.
Otherwise, return whatever I get by adding
a to-- doing the same thing, but on a slightly smaller problem.
Multiplying a times b minus 1.
And that will again call itself until we
get unwound down to the level that we want to get to.
There's the recursive step.
And that's a standard form for a recursive function,
and is a really elegant way of thinking about how
to solve this problem.

43

I could do the same thing.
Let's think about computing factorial.
Factorial written in mathematically
as n followed by an exclamation point,
is the product of n times n minus 1 times n minus 2,
all the way down to 1, where n is a positive integer.
If I wanted to solve this problem,
I could say, for what values do I actually know factorial?
And that's easy.
If n is 1, factorial of 1 is just 1.
There's my base case and the value I want to return.
How would I return it?
Well, just as I did with the multiplication case,
n factorial is the same as multiplying n by n
minus 1 factorial.
So there's the recursive step.
And I've just written the body of code for something
that would be a definition for factorial, or fact.

What you're seeing here is a pattern.
And this is the idea of a recursive function.
Break it down into a smaller version of the same problem,
plus some operations I want to do,
and figure out when can I stop breaking it down
into smaller versions of the same problem
because I know how to compute it directly?
In the case of factorial, when I get down to a factorial of 1.

44

With that in mind, let's deal with something
that may be puzzling you, which is how in the world
does the computer know when to stop unwinding this?
And how does the computer know which
versions of the function-- of the parameters of the function
to use?
I'm calling fact of n.
How does it know which version of n to use?
We've already kind of seen it, but let's walk it through.
So here's my definition of fact.
Fact of n is if n is equal to 1, return 1.
Otherwise, return n times fact of n minus 1.
Then I'm going to call it on a value of 4,
and I want to print out the result of that.

I'm going to do this reasonably quickly,
because you've seen these pieces before.
But let's look at what happens.
When I define fact in that global scope,
I create a binding of fact to some code.
Hasn't been run yet.
And now I'm ready to run it by actually calling it
on print of fact 4.
OK.
Here we go.

I've got to call fact of 4.
Fact creates a new scope, inside of which n is bound to 4.
And relative to that, it's going to evaluate
the body of the procedure.
Says is n equal to 1?
No.
It's equal to 4 here.
So I go to the else clause, which says return n times
fact of n minus 1.
Aha.
I've got to call fact again.
I know I want to return 4 times fact of 3.
That's the value of n minus 1.
But I've got to call fact.
Great.
It creates a new frame, inside of which the formal parameter,
n up here, is bound to 3.
And relative to that, it does exactly the same thing.
So I'm now going to go faster.
Is 3 equal to 1?
No.
So I'm going to return 3 times calling fact
on n minus 1, which is 2.
That calls a new frame.
Here's the binding for n.
n's still not equal to 1.
I'm going to again go to the return clause, or the else
clause, that says return 2, which
is the value of n times fact of n minus 1, which is 1.
And that calls one more frame.
And aren't you glad I didn't do fact of 64?
Almost done.
In that frame, I now say is n equal to 1?
Great.
It is.
And so in that case, I know that's the expression
I want to call.
And it says, ah, return 1.

Where does that go?
I'm returning 1 to the person who asked for it.
And that was that call to fact.
That's great, because now that expression
says return 2 times 1, the value returned by that call to fact.
And who asked for that?
Right there.
That reduces to return to 3 times
2, which reduces that one to return 4 times 6,
which prints out 24.
And I'm done.

So you can see the computer, with these nested scopes,
these nested frames, nicely knows
exactly where to get values in order to do the computation.
And therefore, the computer knows
to stop at the right time.
I've just said that.

45

Simply going to put the slide up so you can see it.
Each recursive call creates its own scope.
Bindings of variables in a scope are not
changed by the recursive call.
And the flow of control passes back to the previous scope,
because that was the person who asked for that function call
as we did it.
And therefore, I'm going to be able to use
exactly the same variable name.
I need to because that's the formal parameter
of the function.
But it's always done in a different scope.
And therefore, it's always clear which version
I'm using when I'm calling the body of the procedure.
46

This leaves us then with this nice comparison
between iteration and recursion.
Both of these pieces of code do exactly the same thing
in terms of what they compute.
How they do it is done differently.
I'll let you decide your own style.
Personally, I like recursion better.
I think it's more intuitive.
I don't have to remember to set up a parameter variable
before I start things.
I don't have to worry about dealing with all those pieces.
I can make them a little different.
In this case, I've changed it slightly
to use range rather than setting up the iteration variable.

But I personally find the right-hand side easier
to look at, because I can easily see
where the recursive call is.
From the programmer's point of view,
recursion may be more efficient.
From the computer's point of view,
it may not be as efficient.
And we'll see that.
But basically, the idea is each of these things
does the same thing.
You get to decide which one you want to use.

## Video: Inductive Reasoning

2017-09-19 14:24:02

...

We just saw an example where we walked through carefully
the execution or the invocation of a function
called a factorial in order to see
how the different scoped frames were created
and to help us sort of decide that, in fact, it
will stop when it reaches a base case and return a value.

48

But when I start trying to design code,
I have to think about the same thing--
how do I set it up so that I know
it's actually going to stop?
How do we know a recursive code is going to work?
In the case of an iteration, we know that
by making sure that we've got a loop invariant that
changes as we go through it in order to make sure
that we actually get down to a place where we hit the end
test.
So mult inter terminates because b is initially positive,
and it decreases by 1 each time through.
I've set that up by making sure I change it by 1.
And so I know eventually it's got to get down to a place
where it's less than 1, which is going to trigger that n clause.
And I can use that to deduce that I've
written code that is, in fact, going to terminate if I give it
an appropriate set of values.

What about the recursive version?
Sorry, as I said, mult is called with b1,
in that it has no recursive call, and it stops.

But how do I know that it stops in general?
Well, if I call mult where b is greater than 1,
it makes a recursive call with a smaller version of b.
And so, again, I know that eventually it
must reach a call where b is equal to 1.
This tells me that when I write a recursive version
of a function, I need to make sure that I'm
changing the parameter.
In this case, this value, so that I'm
going to get down to that test case.

That's nice, but there's another way in which, in fact, I
could reason about my code to decide,
is it going to, in fact, terminate
or is it going to get into an infinite loop,
because it's going to recursively call itself
over and over again?

49

And to do that, we can use, as a little sidebar,
a nice little mathematical tool called mathematical induction.

Here's the idea behind induction.
If I want to prove a statement that
is indexed on integers, that is, it's
a statement that is applied to a set of integers.
If I want to prove that statement
is true for all values of some parameter n,
I just need to prove that it's true
when n has it's smallest value.
For example, n is equal to 0 or 1.
And then I need to prove that if it is true on an arbitrary
value of n, I can also then show that it
must be true for n plus 1.
And with that, I can then essentially
deduce mathematically, that it's true for all values of n.

50

Let me show you a little mathematical example of this.
The sum of the integers for 0 up to n,
I claim as n times n plus 1 divided by 2.
If n is 1, it says 1 times 2 over 2 is 1.
If it's 2, 1 plus 2 is 3, and 2 times 3 divided by 2 is 3.
You get the idea.
How would I prove this is actually a true statement?
Well, the proof says take the simplest case.
If n is equal to 0, what do I have?
Then the left-hand side is just 0,
and the right-hand side is 0 times 1 divided by 2,
which is just 0.
So it's true.

To prove it in general, I simply assume
it's true for some value-- let's call it k.
And then I need to show that it's true for k plus 1.
So I need to show that this statement is true.
Well, but that's nice, because the left-hand side,
I know that it's true for that.
I just assume that.
I know that in that case, that is
k times k plus 1 divided by 2.
So the left-hand side is simply that, by that assumption.
And if I do just a little bit of algebra,
I can show that that is, in fact, the same as this,
and I'm done, having proved it.
Assuming k, therefore it's true for k plus 1,
I can now say it's true for all values of n.
So this formula is always true.

51

What does that have to do with code?
Well, I can do the same thing.
Here, with my case of a recursive call to mult,
I need to do the following-- I need
to show the base case is true.
Will this true return the right answer when b is equal to 1?
Yep.

Now, what about in the recursive case?
I'm going to assume that my code does
the right thing for smaller versions of the problem,
meaning that I'm going to assume that mult returns
the right answer.
And, in that case, I can then say on this piece of code,
if it does the right thing, then this return does
the right thing, because it's simply an addition.
So in that case, I know it returns the right answer
for a problem of size b.
And by mathematical induction, my code
will always do the right thing for appropriate values
of a and b.
Thus induction tells me I've got code that works.

## Video: Towers of Hanoi

2017-09-19 14:33:45

53

We've seen some simple examples of recursion,
factorial, doing multiplication by doing recursive addition.
These are nice places to start.
But recursion is actually really a powerful tool.
And I want to show you a very different way of thinking
about recursion on a problem that's
otherwise hard to solve if you don't
think about it recursively.
And this is to take a classic problem called
the Towers of Hanoi.

The story is that somewhere in the temple in Hanoi
there are three tall spikes on which there are initially
64 disks of different sizes all stacked together
in decreasing order with the largest at the bottom
going all the way up to having the smallest at the top.

And the goal of the priests in this temple
is to move the entire stack from one spike
to another one, moving one disk at a time,
but with the property that they can never
have a larger disk covering up a smaller disk.
And there's a little animation you
may be watching at the bottom here
that's showing an example of that
with a stack of size three.

We want to figure out how would I write a program
to tell the priests exactly how to move those disks so they
can move all 64 from one spike to the other.
And I'm going to do a little demo to show that to you.

So I want to demonstrate for you how to solve Towers of Hanoi
and especially how to use recursive thinking to do that.
But to begin with, I'm simply going to show you solutions
to Towers of Hanoi and see if you can figure out
how to write code to describe the set of moves
that would solve it.
Let's start with the easiest case.
I have a stack of size one.
Moving it is easy.
I just move the disk.
If I have a stack of size two, I know
I've got to move the higher to the smaller
disk to the spare place while I move the bottom one,
and then move it over-- pretty straightforward.
If I want to move a stack of size three,
takes a little more work because I got to move the top disk.
I got to be careful not to cover up a smaller disk with a larger
one.
But once I've cleared the bottom disk,
I can move it, and, again, move the top disk to the spare one
so that I move the entire thing without covering up a smaller
disk with a larger disk-- also pretty easy.
But what about a stack of size four.
It takes a little more thinking because I
have to really be careful here that I'm not accidentally
covering things off.
And it takes a lot more work to, in fact,
expose that bottom disk, which I'm now ready to move.
And now I've got to get all of those back over again
without covering a smaller disk with a larger one.
And so that allows me, basically,
to make that set of moves to get to that point.
Great-- easy to write code to do this.
Right?
Probably not.
But if I think about it recursively, it's really easy.
So what does that mean?
I want to move a stack of N disks.
And recursively, I would say if I already
knew how to move a smaller stack, what's my solution?
Oh, that's easy.
Move a slightly smaller stack to the spare disk.
Now I can move the bottom disk and move
that stack to the target.
And what does it mean to move that stack to the target?
Move a slightly smaller stack to the spare disk,
move the bottom one, and move that stack.
And I'll just keep on winding that until I'm just
moving single disks.
Recursively, this is easy to see.
And that leads to a very natural implementation.

54

OK.
What you saw in that demo is that it's
going to be hard, even if you watch things
like moving a stack of three or stack of four.
How would you write the code to do it?
And then what you saw is if I think about it recursively,
it's actually really easy.
Because recursively, what do I do?
I solve a smaller problem.
Move a stack of size N minus 1 onto the spare disk.
Then I've got just one disk left on the bottom of it.
I move that one, which is a simpler problem.
And then I move that stack that I just temporarily
moved to the other side back on to the place I'm going to.
Recursively, this is really easy to see.
And so even though this looked like a very hard problem,
it's very easy to write code to do it.

55

And so there is, in fact, a little set of code
that says-- I got a function that simply
says print an individual move from the from stack
to the to stack.
And then here, notice what I've got I've got.
I've got a test for a base case.
If I've got just a stack of size one,
I'm just going to print the move to take it from from to to.
Otherwise, I actually now have to solve
two recursive problems.
So it's a little bit different.
I'm going to move a smaller stack from to
from to the spare swap.
Having done that, I'm going to move
the simple case to the place I'm trying to go to.
And then I got to move another smaller size
stack from the spare over to the to spot.
But the code itself is really straightforward.
And if in fact I go and run this on a stack of size four,
it gives me very nicely all of the moves
I want to do to move that stack over.

What I want you to see here are two things.
One, I can have multiple recursive calls
inside of a function body.
It's perfectly fine.
And two, this is a problem that I suggest
is really hard to solve iteratively,
but elegantly easy to solve recursively.
And I want you to think about the notion of break it down
into a smaller version of the same problem,
assume that can be solved, build your solution with that
and other simple operations, and let the recursion then
unwind it to get to the solution that you want.