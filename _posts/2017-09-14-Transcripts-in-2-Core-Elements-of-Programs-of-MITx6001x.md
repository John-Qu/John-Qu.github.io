---
layout: post
title:  "Transcripts in 2. Core Elements of Programs of MITx6001x"
date:   2017-09-14 09:48:19 +0800
categories: notes
---

This is a note of MIT6001x 2. Core Elements of Programs. 

## Video: 1 Bindings

...
Welcome back to 600 part 1.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjivbaylncj31f612c77k.jpg)

In the first lecture, we started talking
about computation, computational thinking.
And we began to introduce simple expressions
and very simple programs.
In this lecture, we're going to add a new type.
We're going to go back and look at branching as a key element
in order to make decisions in algorithms.
And then we're going to start introducing
the first class of algorithms that
are going to be really valuable, things
called iteration or iterative algorithms.
To do that, I want to just quickly remind you of things
that you saw last time and that you need to keep in mind.

### VARIABLES (REVISIT)

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivbrtwouj31f412aq6q.jpg)

First of all, variables, often called
bindings-- these were names that we had to which we
could associate values.
And we saw they were created by using a name followed
by an equal sign followed by an expression that had a value.
Why did we want the name?
It could be descriptive.
It tells us what that value is.
It gives us something that helps us think about how
we're going to use that.
It let's us reread code more easily,
and it certainly can be meaningful
because it gives us a sense of how we want to use computations
in more complicated ways.
One of the things to remind you is there are certain words that
cannot be used as variables.
These are things called keywords,
things like int or float.
They describe a type that cannot be used as a name
for a variable.
There's a set of these that we'll
talk about as we go through.
And you'll notice in Python when you type one of these keywords
in, it will show up in a different color, which
is a hint that it's a keyword and not something you should
be trying to bind as a name for a value.
The value could be any legal expression
that returns a value.
And that's going to store information
that we're going to use.
And finally we saw that we could update the value associated
with a name by reassigning it using another assignment
statement.

### VARIABLE BINGDING WITH =

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjivcuec65j31f212e44a.jpg)

The way we did it, just to remind you,
was we compute the right hand side of the expression.
For example here, the value associated with two
is just the int 2.
We then store it-- sometimes we refer
to that as bind it-- to the left hand side, which
is the variable name.
That creates a binding off in the machine
of x associated with 2.
But of course we can also replace it with a new value.
And here, again, if you look at the second expression,
remember we first evaluate that expression.
The value of x right now is 2, so 2 times 2 is 4.
That associates the value 4 with the variable x,
which says when I get around to then evaluating x plus 1,
this is going to be 5, which is the value associated with y.
Equals sign does the assignment.
It creates those bindings for us.
And as I just said, we're going to always compute the value
first and then override the name if that value is actually used,
or rather if that name is used as part of the expression
to get the value.

### BINDING EXAMPLE

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjive0gcscj31ew12edk2.jpg) 

You might think this is pretty straightforward,
but we need to be careful about the order in which things
are done.
Suppose I got two variables named x and y,
and I want to swap their values.
The little sequence of expressions
here looks like it should do the right thing, right?
Wrong.
Let's think about it.
The first expression assigns x to the value 1.
The second expression assigns y to the value 2.
The third expression gets the value of x, which is 1,
and assigns it to y.
So I have x is 1.
I have y is 2.
I look up the value of x.
I now assign it to y.
So the 2 was replaced by 1.
Now when I do this expression, it says what's the value of y?
It's 1.
Assign it to x.
And I replace the 1 with a 1.
So it didn't swap them because there's
a sequence to this operation.
It doesn't do what you think it was going to do.
There's a better way to do it in fact, the right way to do it,
which is to temporarily assign the value of y
to the variable temp so that I can overwrite the value of y,
and I still got that value around to restore into x.
So we need to think carefully about not only what
do I compute as a value and what do I give as a name,
but the order in which I do it.
Because if I lose a binding for a name, I can't get it back.
But that reminds us then of how to do assignments,
how to do bindings, and how to do
the actual sequence of operations
to create bindings associated with variables.

## Video: 2 Strings

...

### TYPES

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjivfsfe3vj31e011wdie.jpg)

So far, we've just been playing with numbers-- names
for numbers but basically just with numbers.
Now we want to add in one more type of object.
We've seen ints, we've seen floats,
we've seen bools, which are ways of getting values
back out of tests.
The next thing we're going to add in is a string.

### STRINGS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivg8wxowj31e8128jv6.jpg)

We'll see a few others as we go along,
but strings are going to be valuable to us.
And what's a string?
A string is simply a sequence of characters-- letters,
special characters.
Could be spaces, could actually be sequences
of characters put together into words,
put together into sentences.
And those are all contained within either double quotation
marks or single quotes.
Let me show you some examples.
I've got some on my slide, but let
me show you some examples with my screen.
I can give the name hi to the string H-E-L-L-O space
T-H-E-R-E double quote.
Those quotes on either end say treat this entire sequence
as literally a sequence of characters.
And if I ask for the value of hi,
it prints it back out, in this case,
with a single quote around it.
As we said, we can either use double quotes or single quotes.
Why?
Partly historical.
One would really work, but a place
where double quotes are handy is if I actually
want to use an apostrophe somewhere in a string.
Because from Python's perspective,
the apostrophe looks like an end of a quote.
And so for example, if I want to say foo is this isn't right,
notice that the single quote does not get interpreted
as the end of a quote.
And I can put out the value of foo.
Once I've got strings, I can put them together.
So for example, I could say I'm going
to give name the value Eric.
I could certainly print out name.
What's its value?
There it is.
But I could also put things together.
And the next expression looks a little unusual.
Greet is hi plus name.
And when I print out greet-- sorry, if I type properly,
it would help.
Print out greet.

It puts the two things together-- hi there and Eric.
Two things going on here.
The first one is-- whoa, little funky
to think about adding strings together.
But just as we can add numbers together,
strings have a natural way of getting combined.
And in this case, it's to concatenate them together,
to literally take the first string, glue the second string
onto the end, that creates a new string, and I can print it out.
But if you look at my computer monitor,
it didn't quite do what I wanted.
It said hello Theric.
I have no idea who Theric is.
I'd really like to have it say hello there, Eric.
And so I can get that by adding in a little blank space.
And so if I type in greeting as hi plus a space plus name,
then the value of greeting is what I wanted-- hello there,
Eric.
Really nice.
Notice concatenation, just as with numbers,
could have multiple things in a row.
So I can concatenate multiple things together as I did here.
What we say when we talk about using addition this way,
by the way, is we say we have overloaded it.
We have had addition apply not only to numbers but now
to strings.
Oh, yeah.
We talked about that earlier on.
Remember when I said in the first lecture
that the type of an argument, the type of an object,
would tell an operation some important information?
Here it does that because it's telling addition,
if the two things are strings, concatenate them.
It's also telling addition, if I give you two numbers,
just add them together using straightforward arithmetic.
So I can use addition in multiple places
to let the type of the object define what's going to happen.

### OPERATIONS ON STRINGS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivigx7ovj31em12a7ak.jpg)

Once I have strings, I need operations on them.
I've already seen the first one.
We can do concatenation, but we can do some other things
with strings.
In particular, we can do successive concatenation.
So if I type three times the string Eric, I get an echo.
Three versions of Eric are stitched together.
So I can successively concatenate things together.
It's kind of nice.
And, again, notice I'm overloading multiplication
here.
I'm saying multiplication of a number times a string is simply
saying give me three versions or n versions,
however many versions of that string put together.
I can ask for the length of a string, and that makes sense.
It tells me how many characters there are in that string.
And that will include, by the way, counting spaces.
So the length of hi there includes the space, not just
the characters.
It tells me how many literal elements there
are inside of it.
Strings have things inside of them.
They're the first version of a non-scalar object,
in that I can get out pieces.
And one of the ways I can do it is say I can index into it.
So if I take the string, Eric, and I
want to get out the first element in square brackets,
I can say give me the first element, and it gives me r.
Wait a minute.
That's not the first element.
The First element's e.
Eh, in Python we have chosen to decide to start
counting starting at 0.
So if I want to get the zeroth element of Eric,
I would say give me the zeroth element, and there it is.
I've already bound name to be Eric so notice, by the way,
I could ask for the zeroth element of name,
and it gives me the zeroth element of the value associated
with name, which pulls back out the e, exactly what I wanted.
If I try and index beyond the length minus 1 of a string,
I'm going to get an error.
And that's because I start at 0.
So even though this is of length 4, if I take the string Eric
and I ask what's the fourth element?
It gives me an error, something called an index error
that says you tried to go too far outside of it.
One last thing about strings.
I can certainly get a single element out.
I might want to get a chunk out of it.
And so I can slice a string apart by giving it a somewhat
funky looking expression.
I take Eric and, again, in those square braces
I give it a starting point, which is 1, and a colon,
and then an ending point, in this case 3,
and it gives me the first and second elements
of the string, r and i.
I can choose to say everything starting at the beginning,
I could use that as a 0, but I can also
do that by saying give Eric with nothing
before the colon and just 3, and it gives me all the elements
up to but not including the element number 3.
And similarly, I could do it by saying take Eric,
give it 1, but nothing after the colon,
and it gives me all the elements starting at element number 1.
And if I just want to make a copy of the whole thing,
I can say open square brace colon close square brace,
and it gives me literally a copy-- not the original--
but a copy of this entire string.

## Video: 3. Input/Output

...

### IMPUT/OUTPUT: print

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivl49k18j31ei12242a.jpg)

As we've already seen in our programs,
we need to be able to both read input in and print stuff
out, or return values.
I want to now spend a little bit more time on that.
We showed a very quick example of it earlier on.
But I want to come back to that to be
able to give you a sense of how you can control that.
So let's start with output.
I want to be able to print something to the monitor
as I'm doing computation, not just
at the end of a computation, but perhaps partway through that.
And here, we have a keyword called print
that's going to do that for us.
And I've got a simple little example here,
which I'm going to run on my machine.
I'm going to define x to have the value 1.
I could just print x.
So the keyword print followed by an open paren followed by,
in this case a name, x, followed by closed paren
simply prints out that value on the screen,
kind of trivial in this case.
But I want to show you some examples
of how I could control the print a little bit differently.
So I'm going to define x string to be the string x.
And notice what I'm doing here. x is an int.
str is going to actually cast it into, or convert it,
into a string, that is, the symbol x.
And I'm going to have a name.
In this case, I've called it x underscore str.
When I do that on my machine, I've now got a binding for x
string.
Now, I can do printing.
And printing here can take multiple arguments.
You can see it on my slide.
I'm going to print out a combination of this expression,
that expression, a sequence of expressions,
all separated by commas.
Let's see what happens if I do that.
So I'm going to print of my favorite number is a comma,
to say I've got something.
And then I'm going to give it x.
And then I'm going to give it a period enclosed
in double quotes.
And then I'm going to give it something
that says what's the actual value of x and x,
sequence of things.
And if I print it, I get something pretty funky.
It says my fav num is 1.
Oh, but then there's a space before the period.
And then it says x is equal to 1.
Hm, what happened there?
Well, what happened is that print is literally
printing each element followed by a space.
And in particular, x has a value that's
going to show up separately from the period.
On the other hand, if I give x as a string,
it's simply going to put the two pieces together.
And so I can do a second kind of print, which is, I can say,
print my favorite number is.
And then I'm going to add to that, or concatenate, x string.
And then I'm going to add to that period,
add to that the last part of the string, x equals,
and add to that x string.
And if I print that out, I get something a little better.
In fact, I blew it.
I wanted to have a space between the period,
so that it would actually print it out as saying,
my favorite number is 1.
So let's do that one more time.
Print my favorite number is, and a space,
concatenate x string with period, and a space,
concatenate that with x equals, with a space at the end.
We concatenate all of that with x string.
And I finally get what I wanted.
What am I showing you here?
In the case of print with multiple arguments,
it will print each one of them spaced apart.
In this case, I am concatenating the entire thing
into one long string and then printing it out.
And I can control the spacing around it.
So this is going to give me a way
to give an output to the machine telling me
what I've done as I control it.

### INPUT/ OUTPUT: input("")

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjivo071lbj31ey12caf6.jpg)

What about the other direction?
I want to bring in input.
And here, I have another key word
called input not surprisingly.
And it takes a single argument, which is a string.
And its behavior is it's going to print out whatever is inside
of those quotes, that string.
It's going to wait for me to type something in.
When I hit Enter, it's going to evaluate whatever I typed in
and return that as the result of the input statement.
Typically, I'm going to want to bind that to something.
So I can bind it to a variable named, like text.
And if I try this, I can say, text equals input.
And I'm going to simply say type something.

Notice what it did.
It just printed out type something.
It's waiting for me to do something.
And I can say, foo.
What did I do?
I bound that to the name text.
If I look at the text, there it is.
So if I wanted to really be annoying about it,
I could then say print 5 times text.
And there it is.
Now, maybe you're looking at that and saying,
wait a minute, why are the double quotes there?
Because I typed them in.
Input simply expects everything to be a string.
So I could do the same thing.
I could say text equals input type something.

Again, it's waiting for it.
In this case, I'm simply going to write in the string bar.
And what's text?
It's just bar.
And in fact, if I say, what's the type of text,
it says it's a string.
So if I'm going to type something in,
it's automatically going to read it in as if it's a string.
Ah, but that says, if I wanted to get a number in,
I need to cast it.
And that's what this last example does down here.
Input, even if I type in a number,
is going to interpret it as a string of the characters
of the number.
And so I need to turn it into an int before I actually use it.

## Video: 4. IDEs

...

### IDE's

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivq03zhwj31eo12e793.jpg)

So far we've just been typing things into our Python shell.
And for simple expressions, that's OK.
But it's even there a little bit painful.
And when we want to do things that we might like
to run multiple times or when we want to do things
with multiple commands, we'd really like a better way
to deal with that.
And for that, we'd like to have a text editor.
Just like an editor you'd use for writing Word documents,
we'd like an editor into which we can type Python expressions.
And in most cases that comes as part of something
called an IDE, an integrated development environment.
I happen to be using one from Anaconda.
IDLE's another version of it.
And that IDE comes both with a text editor into which I
can enter things, I can edit them,
and I can save them away, a shell, which
is that place where I'm going to be able to interact
and where I can load that information in before I do
that interaction, and as we'll see later on,
an integrated debugger.
And I want to show you just an example
of how I would use that text editor as part of the IDE.

Your own computer may have a slightly different version,
but you should be able to figure it out.
Let me simply show you an interaction on mine.
So on my computer, I have both a text file opened up
as well as the shell.
And here I'm going to type in a couple of expressions.
I'm going to set x to the value 5.
And then I'm going to create a little conditional.
I'm going to see if x is not equal to 5-- and remember,
I'm going to close that conditional with a colon
to tell me I'm at the end of it.
When I hit a carriage return, the editor automatically
indents, which is really nice.
I know that the next set of things should be indented.
So in this case I'm going to say print out I am here.
I have no idea, why but it seems like a reasonable thing
to print out.
I hit a carriage return.
I'm still at the same place.
But then I'm going to put in an else clause.
And notice it nicely indents back
because the else should be at the same level as the if.
And then I'm going to say print, no I am not.
Now I want to run this, meaning I'd
like to load this information into my shell.
There are a number of ways to do it.
But the easiest one is if I go up to my menu item at the top,
there is something called Run.
And if I click on that, it gives me a set of options,
including something called Run.
And I hit Run.
And it's going to ask me where to store that file.
I'm going to give it a name temporarily.

And it said I didn't like that.
So I'm going to try it again, giving it a place
that I know I can store it to.
Let me do that.
I want to pick a particular place, save it away.
Oh nice.
If you now look at my shell, it's
actually evaluated that code.
It turns out that I have other options here.
Under that menu I could run the entire file,
or I could pick something out and run just a portion of it.
I could select a thing using the mouse or run a line.
One of the other things I'd like to do
is to run that file multiple times.
So for example I could say I'm going to change x from 5 to 6.
And now it turns out on my machine
there's a short cut, which is just function F5.
It may be different on your machine.
It automatically saves the file away, executes it.
And again, on my shell, I've now seen a printout.
This is going to be really nice.
It's going to let me have easier ways to edit files,
edit code before I run them.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjivuocb5fj31fq0uagtl.jpg)

And so what you have then is that ability
to have both a place into which you can type things, save them
away, and a place in which you can then evaluate them in order
to do the kinds of computations we've been discussing.

## Video: 5. Control Flow

...

With these new data types in mind,
strings, with some of the other pieces we've added in,
let's go back and just remind ourselves
about branching programs so that we can build on that to start
creating iterative programs.
So just to remind you, what's a branching program?
It's something where I have a conditional that I test.
If that test returns the Boolean value true,
then I have a block of code I'm going to run.
If it returns the Boolean value false,
I've got something different I'm going to run.
And I'm going to simply take either this branch
or that branch and pick up the remainder of the code.
We've already seen a simple version of that with an IF.
To do the testing, we had comparisons,
things like comparisons on ints and floats.
These are simple numerical things.
I will simply remind you again the double equal checks
equality, equal sign does not.
And we had logical operations to put things together.
With that in mind, we could start then
building the simplest of the branching code, which
were either IF statements, which says if this condition is true,
execute a set of code.
And IF ELSE, which said if this condition is true do this,
otherwise do that.
Or the more general, IF ELIF ELSE,
which says if this condition is true, do this.
If it's false, check to see if this condition is true,
in which case do this.
And keep doing that until I get through all of the ELIF
clauses, and if all of the conditions are false,
pick up the ELSE clause and do the rest of that.
It's just repeating what we've done before, things
that you've already seen.
With that though, I'm still stuck
with things that can only flow through code once.
I can take different branches to get there,
but I can't go back and do something again.

### USING CONTROL LOOPS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjivxpoptpj31f812aq6d.jpg)

And let's think about where that might actually not
help the way I'd like.
As I said, simple branching programs just make choices.
Sometimes though I might want to do something
over and over and over again.
How would I do that?

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjivyocwdsj31eo124jxz.jpg)

Well, imagine you're writing a simple little video game.
And part of that game has a character
that gets lost in some woods.
And I agree the graphics here aren't great,
but you get the idea.
I'm stuck in a set of woods.
What I'd like to do is to say to the character, if you go right,
you're going to get back to the same place.
You're going to be stuck in the same piece of the woods.
How would I write that as code?
Well, you could say, gee, I could have an IF statement that
says if I'm told to go right, here's
a set of things I want to do, otherwise if I go left,
I'll get out of there.
OK?
But I want this to be something that if I keep going right,
I keep getting stuck in the same spot.
All right.
You say, gee, that's easy.
I could have another IF statement
that says if the command is still exit right, do something.
On the other hand, if I exit left,
I'll get out of the woods.
But I didn't want to do that again.
If I'm going right, I want to keep doing it.
You can see the problem.
I want to be in literally an infinite loop
in this little video game that says if I'm going right,
I'm always coming back to the same spot.
How would I write code to do that?
Well, I could say I'm going to assume that a character doesn't
push go right more than 100 times,
and I could write literally a big loop here-- not a loop,
sorry-- a big sequence of IFs that was 100 deep.
But maybe somebody is really persistent,
and they want to do it 1,000 times.
You could see my problem.
I don't want to write code when I have an indeterminate number
of things that I want to do.

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjiw09w845j31dy122wj0.jpg)

I need a different way of controlling this,
and I have that.
It's called a while loop.
We're going to look at it in detail,
but the idea is that I'm going to say here's
a check, a condition.
If it's true, I'm going to do this,
and I'm going to go back around and do it again.
And I'll keep looping around and around on this while
until this condition is false, in which case
I'll jump out and do the next kind of thing.
And that says, no matter how many times I go right,
I'll always be in that loop until I finally go left
and break out of it.

### CONTROL FLOW: while LOOPS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiw11gabnj31ds12ewj9.jpg)

So I can control the flow.
Now, for the first time, not just
in a linear way with something that lets me check conditions.
And so the format of a while loop is very simple.
There's the while expression.
There's a test that's going to return a Boolean value,
either true or false, and then with indentation
a set of expressions I'm going to evaluate.
And the performance of this is exactly what I just described.
If the condition is true, I'm going
to do all the steps inside that code block.
I'm going to go back up and check the condition.
And I'll keep going through that loop
until the condition finally comes out as false.
All right.
How might I use that to do something a little more
interesting than trying to get out of the woods?

### while LOOP EXAMPLES

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiw27e08tj31e8126gpu.jpg)

Well, first of all, let's fix the woods.
Here's a nice little piece of code that will do that for me.
The first one says input based on this prompt,
an instruction, left or right.
So n's going to be either the word left or the word right.
Notice what the while loop says.
It says, if n is equal to the string right,
then I'm going to execute this block of code,
which simply again says you're in the lost forest.
Go left to right.
And notice what that while loop will now do.
As long as n is equal to right, it
will keep prompting me, asking for an input, until I
finally type in left, at which case, this will be false,
and I'll jump down and pick up the print statement.
I can have an indeterminate number of times here.
It's still always going to do the same thing.
A little brain damaged, but it's still
going to do the right thing.
And that's kind of nice.

### CONTROL FLOW: `while` and `for` LOOPS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjiw3gnb5kj31d6128tdj.jpg) 

Now, let's see how we might use this then
in other kinds of things.
So here's a while loop.
And notice what I need to do inside a while loop.
I need to set up a variable outside so that I can test it
and then do some pieces.
And I need inside to have something that actually changes
that variable, otherwise I'm never
going to get out of the loop.
Now, we can see what this does.
If I type this into my Python shell,
I can set n equal to 0, which is done.
And then I can say while n is less than 5 colon,
I'm going to print out n, and I'm going to set n to n plus 1.

Cool.
It just did what I'd expected.
It starts out with n equal to 0.
Is 0 less than 5?
You bet.
So it prints out n, changes n by 1, goes back around
and checks again.
Is 1 less than 5?
You bet.
And you get the idea.
That pattern is something that we would use pretty regularly.
That pattern is also slightly annoying,
because what if I forget to set n equal to 0 before I start?
I'm either going to get an error, because n isn't bound
to anything, or I'm going to get a performance I don't expect,
because n has got some value I didn't expect.
Similarly, what if I forget to increment?
I set n equal to 0, and I say while n is less than 5,
print n.
Well, I'm going to print out 0 a billion times
until I finally stop the machine,
because I haven't incremented.
So it turns out there's another form that we're
going to use that is much more convenient,
and that's called a for loop.
And the for loop has a particular syntax.
It has a variable.
It has the key word in in this case,
and then it has something we're going to come back to
in a second, but an expression.
And what for does in this case is
it is going to work through all of the values
returned by that expression one at a time,
executing the body of the code.
Now, range is something that returns
basically a sequence of integers starting at 0
and ending before 5.
0, 1, 2 3, 4.
It actually does something a little different
we're going to talk about later in the course,
but think of it for now as giving us the collection
of integers 0 up through 4.
And so if I go over here and type it,
I say for n in range of 0 to 5, print out n.
I get the same behavior, but this code is easier to see.
It says for n in this sequence, do something.
As we said, range gives us back, in essence, the integers
0 up through 4.
We'll see some other variations on range
shortly in terms of other ways in which we control it.
But the for loop gives us a nice way
to capture easily an iteration, a repeating of code
some number of times based on, in this case,
a specific number, although I could also base it on a test.

### CONTROL FLOW: `for` LOOPS

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiw5vb0sej31e01240xc.jpg)

Just to recapture this then, the overall general
format for a for.
The special character in, in this case using
range to get me out a set of numbers and a body of code
that I'm going to execute.
And just to remind you again it says,
each time through the loop, variable
is going to take a value.
The first time it starts at the smallest value in range.
The next time it gets the next value, in this case, for range
added by 1 and so on.

### `range(start, stop, step)`

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiw7cgqlmj31d011s0x3.jpg)

Now, I can actually be a little more clever about range,
because maybe I don't want to do every value in that range.
Maybe I want to skip some of them.
So, in fact, I have something that
says I can start at a different point than 0
if I give it two arguments.
In this case, it will give me the range of numbers from 7
up to but not including 10, or I can give it three arguments.
Start at 5, end when I get up to or past 11, but do it by 2.
And in each case, I'm going to get a different range out.
So let's look at what those do.
If I go over here and say my sum is 0,
and then I'm going to say for i in the range 7 to 10,
I'm going to increment my sum by i.
And then if I print out my sum, I
get 7, 8, and 9 added together, which
gives me out the thing I would expect to see.
If I do the second one, my sum again
starts out as 0, and for i in the range 5 to 11 by 2,
this should be 5, 7, 9, but not 11.
And, again, I'm going to say my sum I'm
going to increment by i, and remember plus equal says
add to my sum the value of i.
And I print out my sum.
I get 21 in this case-- 5 plus 7 plus 9.
Sounds right.
So I can use range to actually give me a set of values,
but the nice part about all of this is the for loop
always will just run through all of those values
and executing the body of the loop each time through.

### `break` STATEMENT

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiw8qccu9j31dw11qae6.jpg)

Now, as I'm doing these loops, it
might be the case that I want to get out of one of them.
I might want to stop if something is actually,
for example, a condition is true.
And for that, I have another special thing called a break
and does exactly what you would expect.
If I'm running through some code,
and I execute or see rather that special key word break,
it stops the execution of that loop at that point or that code
block at that point and breaks out of it.
So in this case, if I'm inside this while
loop, when I hit break, it will never execute that expression.
It will pop out of all of this and pick up at that point.
That lets me control how I want to deal with loops.
For example, I might see a particular condition is true
and, based on that, say I don't want to do the rest of this
and jump out of it.
I could write it as an if, but the break
gives me a natural way to control
where I am inside of that loop.

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjiw9t2lyhj31ek11s0w2.jpg)

And so there's an example.
I could set my sum equal to 0.
I could run over that range, but I'd say in this case
if it's actually equal to 5, I can just break out.
While I'm typing that in, think about what this might do.
So I'm going to set my sum to 0, for i in range 5 to 11 by 2.
I'm going to increment my sum by i,
and then I'm going to say if my sum is equal to 5, break out.

And what do you think?
If I look at the value of my sum, it's just 5,
which is exactly what I'd expect,
because the first time around i is going to have the value 5.
I'm going to increment my sum by 1, but then this test is true,
and this break pulls me out of that entire loop
and stops the computation.
Silly example, I agree, but it lets
you see how break controls the actual processing, breaking
myself out of a loop when I decide I'm ready to do that.
And there's the body of code it's going to break out of,
which is why it stops after only the first stage.

### `for` vs `while` LOOPS

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiwav068uj31ds12845f.jpg)

To put all of these together, here's
a little summary of for and while loops.
In a for loop, we know the number
of times it's going to run through an iteration,
although I can end it early with a break.
Because I've defined the range of things over which
I'm going to do the work.
It uses a counter that's captured
inside the for loop itself.
I can always rewrite a for loop as a while loop
by taking that variable that I'm using, that counter I'm using,
pulling it outside, initializing it, and explicitly doing
the increment to the counter inside of the loop.
A while loop can have an unbounded or unknown number
of iterations.
Again, I can always end it early with a break statement,
but I here have to set up the counter ahead
of time outside of the loop.
And I have to make sure I increment it inside the loop.
And unfortunately, I can't always
rewrite a while loop using a for loop.
You'll see in most code, we tend to use for loops
when we know what we're going to do as a computation.
We'll use the while loop when there's
going to be a condition that we can't
predict that's going to allow us to break out of that loop.
But both of them give us the first version
of iterative algorithms.

## Video: 6. Iteration

...

### ITERATION

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjixp610nmj31eo12e11w.jpg)

The notion of a for loop or a while loop
extends the ability to write programs considerably for us.
That generalization of a concept of iteration
goes much beyond what we could do
with simple branching programs.
Remember with a branching program, based on a test
we could either execute one piece of code
or a second piece of code, but we
would then proceed below that and would not
be able to repeat that code in any significant way.
With an iteration, we can now do more.
We can use the same code multiple times.
As with a branch, we start with a test.
If that test is true, then we're going to execute the loop body,
loop once, go back and check the test again.
And we'll keep doing that until the test evaluates to false,
at which point we go to the code following the iteration
statement and execute that.
So this says we can go through this loop
multiple times before we come out.
Whereas in the branching program,
we only went through the code once before we executed.
That's a powerful tool, and we're
going to capture that a lot as we move forward. 

### AN EXAMPLE

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fjixqoq8m1j31eg11yjut.jpg)

Here's an example that will give you a sense of this.
And the example here is to do squaring
by repetitive addition.
So another way of saying it is if I
wanted to compute n squared, that's
n plus n plus n all n times.

I could write a little piece of code to do it.
I've got it here.
I'm going to run it in a second.
I'm going to start off with something
that I want to square.
In this case x is equal to 3.
I'm going to start off with an initial value for answer.
That's going to be where my answer goes.
And I'm going to keep track of how many times
I need to go through the process.
Remember I said that before about loops like while loops.
I need to set a variable outside.
Then I'm going to see, do I have anything left to do?
And if I do, if I'm not down to 0,
I'm going to increase ans by x.
I'm going to decrease the number of steps by 1.
And I'm going to go back around the loop.
And I'll do that until I'm done.
So if I look at a version of that over here now in my IDE,
I've got a little file I've written
that is going to do that.
It's exactly that same code.
And I'm going to load it into my environment.
And wow, there it is.
It printed out, as you can see on my little computer screen,
3 times 3 is 9.
It ran through that loop.
Just to check it again, let's make
something a little bit bigger.
I'll change x to 5.
Again I'm going to load it and run it.
And it computes the computation as we'd expect and returns
5 times 5 equals 25.
OK, big deal, I can square things.
But what I want you to see here is that idea
that I've now got a loop that lets
me use the same code arbitrary numbers of times.
When x was equal to 3, I ran through this portion
of the code three times.
When x was equal to 5, I went through it five times.
That notion of iteration, that's really useful.

### STEPPING THROUTH CODE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjixt9vjt3j31e6126qac.jpg)

Let's make sure it really did what I thought it would
by actually stepping through this.
Again I've got a copy of the code there.
And on the side I've got a little table that gives me
the values I'm going to use.
I'm going to start off with x equal 3.
That comes from that statement.
I'm going to start off with answer equals 0.
That comes from that statement.
And I'm going to start off with the number of iterations left
equal to 3, the value of x.
Here's what the code does.
First thing it does is it checks to see
is iters_left equal to 0.
So it does that test.
Answer is no.
So what does it do?
It takes answer and x, adds them together,
gives us a new value to store in answer.
It takes iters and reduces it by 1 and stores a new value.
Now I've got another version of the computation.
The while loop says go back around.
I check, is iters_left equal to 0?
It's not.
So same process, the current value
of answer or ans, which is 3, is added to x to give me 6.
iters_left is reduced by 1.
Go back around the while loop.
Is 1 equal to 0?
No, one more time, change answer by incrementing it
by 3, the value of x.
Changes iters_left by 1 to get it down to 0.
Now check, is answer left equal to 0?
It is, and I return 9.
And aren't you glad I didn't pick 27 to do this
on but something simple like 3?
My point is you can see how the while
loop executes appropriately.
It keeps reducing one variable, the thing that's
counting how many steps I want to go
through here, while accumulating an answer in ans
as it goes through.
And you see the properties we need for this kind of a loop.
I need to set the variable outside the loop.
I need to test it to determine when it's done.
And I need to change the variable
inside the loop in addition to whatever other work I want
to do as I go through this.

### ITERATION CODE

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjixv1tmfpj31ek12e42z.jpg)

And in fact what we see then is that we've now
got a greater capability.
Branching structures, things like ifs,
only let us go through a different piece of code
based on a test once.
They run in constant time.
They're only going to go through the code once.
Looping structures like whiles let
us repeat code until a particular condition is
satisfied.
But now the amount of time that it takes
is going to depend on the values of the variables
as well as the length of the program.
And later on in the course we're going to come back
to look at that in more detail.

## Video: 7. Guess and Check

...

### CLASSES OF ALGORITHMS

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjixxl3tjmj31ew12on1i.jpg)

This notion of an iterative algorithm is really valuable.
It broadens dramatically the class
of things that we can compute.
Again, if I just have branching things,
I can only go through the code once.
Now, I can start generalizing.
And so we've got things that do much more
than just the simple arithmetic we were doing earlier.
We can repeat a sequence of steps
multiple times based on the decision.
One of the things that comes out naturally
once we have this idea of repeating things
is a set of methods that are sometimes
called guess-and-check methods.
They're very useful, even though they're not always
the most efficient technique.
And I want to extend that notion of iterative algorithms
to capture examples of guess-and-check methods.

### GUESS AND CHECK

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjixz569qtj31ek130n0z.jpg)

Go back to what we talked about in an earlier lecture.
Remember we had that declarative definition of square root.
Square root of x was that y such that y squared was equal to x.
And I said, if we were lucky, somebody gave us a guess.
We could at least use it to check whether we were right.
Now, we went and looked a different direction.
We looked at an algorithm to actually compute it,
but we can go back to that idea, because if we had a good way
to generate guesses, we could use that declarative definition
to check.
That's the basis of guess-and-check.
I'm going to have to come up with a way of systematically
making guesses for the possible answer,
check them, and keep doing that in an iterative algorithm
until I find a good solution.

### FINDING CUBE ROOT OF INTEGER

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjixzwsm79j31dq12wjvl.jpg)

Let's see how we might do that.
I'm going to use cube root rather than square root
just to change it up a little bit,
but the same idea would work.
One way to use this idea would be to try and find,
for example, starting at 0, try 0 cubed,
then 1 cubed, then 2 cubed, and so on, until I get to a point
where I find a k such that k cubed is greater than x.
If I found the square root-- sorry,
the cube root before then, I stop,
but once I've got something greater than x,
I know I can stop.
Now, clearly this is only going to work for integers.
I can't do it for all possible numbers.
But in this case there's only a finite number of things
that I need to try.
So let's see what that would do.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiy0xlf42j31f612o0wn.jpg)

Here's some code that would actually make it happen.
I'm going to start by inputting an integer.
Notice my use of input.
I'll remind you that says it's going to print out
that message, then read in whatever I type
in into the environment inside Python.
Remember that input returns something as a string,
so I'm going to convert it into an integer.
It's going to assume I typed in an integer.
If I give it something else, it's not going to work.
And then I'm just going to have a little loop.
I'm going to set up answer to be 0,
and then as long as I have something that's
less than the thing I'm trying to find the cube of,
I'm just going to increment-- add 1 to it.
And I'm going to keep doing that until I get something that
is equal to-- sorry, something where the cube is either
equal to x or greater than x.
And once I get there, I'll simply check to see,
did I actually get the cube, by doing a test.
Let's try this out.
Again, I've got a little piece-- same piece of code over here.
I'm going to load it into my system.
It says "enter an integer."
Let's give it something reasonable, like 27.
So in my environment, I give it 27.
Ah, good.
Cube root is in fact 3.
Let's try something else.
Again, I'm going to load this into my system,
and I don't know, let's pick 38.
And it says, doesn't work.
It's not a perfect cube.
All right.
My code runs.
What was this doing?
It's simply using a loop, right here, to generate guesses.

And it's going to keep doing that until it gets
either to something that is the right thing,
or has gone too far, in which case,
I'm simply going to do a check to see which case I'm in.
Here, I'm using that declarative knowledge,
because there's the test.
Test is right there to see, do I have something
that is in fact the cube root?
That's nice.
That's what I'd like.

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiy21pfxcj31e412kjua.jpg)

What could I say about this piece of code?
Well, first of all, it's only going
to work for positive integers.
OK.
I could easily fix that by just keeping track of the sign
and then [INAUDIBLE] the solution to the positive case.
And I do this because one of the things we want to do with code
is think about how well does it run?
Does it run on all the things I expected?
And how might I modify it?

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiy49svruj31ea12w0x1.jpg)

And here the modification is actually
pretty straightforward.
I'm going to do the same kind of thing.
I'm going to run the code, but I'm
going to use "abs," which is a built in function,
to take the absolute value of x.
I'm going to check the cube root against the absolute value
of x.
And then when I'm done, I can just decide down here
whether in fact I want the negative or positive version
of that.
I could make that change and run it.
I'm not going to do it.
It'll work for me, but it simply shows you
that I can easily extend my code to build new versions of things
to handle cases that I didn't think about when I wrote
the first version of the code.
There's the first version of a guess-and-check method.
A little slow, but it does the right kind of thing.

### LOOP CHARACTERISTICS

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fjiy5m3ff1j31e212wdl6.jpg)

Now, one of the things that we've talked about
is that we know when we do a loop that we
need some characteristics.
In particular, we need a loop variable
that's initialized outside the loop, that
changes within the loop, and that's
used to test when I'm done.
That notion we can also capture in a little bit
more general form, because it's useful to think about what's
happening inside the loop.
How do I know the loop's actually going to stop?
And for that, we often want to think
about something we call a decrementing function.
The idea is that we're going to map all of the program
variables into an integer, and when the loop is entered,
that value is going to be something that's non-negative.
When I go through the loop, it's going to keep decreasing,
and when that value gets less than or equal to 0,
I know I want to terminate.
So this is a capturing of this idea of the loop variable
in terms of looking at what's being done inside the loop.
And in my case here, I was simply
using the absolute value of x minus answer cubed
as my decrementing function.
If you think about it, every time through the loop,
that is decreasing.
And once it gets to a stage where
it's either less than or equal to 0, I'm ready to stop,
and I'm going to be able to go on
to see whether I've actually computed-- sorry,
a perfect cube or not.

### WHAT IF MISS A CONDITION?

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiy7l2m17j31f012u78r.jpg)

What could go wrong?
Well, these are the standard problems with a loop.
Suppose I don't initialize the variable.
Most likely thing is I get something called a name
error, which is I'm going to try and refer
inside the loop to something that I haven't defined
outside the loop.
There is no value.
I can't look it up.
That's at least OK.
I'm going to stop.
What's worse is if I've used that loop variable somewhere
else in my code before this, I'm actually
going to get something that starts off
the computation in a place I don't expect,
and that's a harder problem to find.
So this is one of the things we always
want to remember with loops-- make
sure we initialize the variable before we start it.
What if I forget to change the variable inside the loop?
I'm in trouble, because I'm going to go through that loop
until I get really tired of the machine running.
It's going to simply go through what we call an infinite loop,
doing exactly the same code over and over and over again,
because it will never reach a terminating condition.
And those are two standard problems with using a loop.
A while-loop, in particular, is I've
gotta make sure I set up the variable ahead of time.
I've gotta make sure I'm changing it inside the loop.
And I need to make sure that the termination test is actually
using that variable appropriately.
But as long as I get into the discipline of that
set the variable, write the loop,
decrement the variable inside the loop, and check for it,
I should be OK.

### GUESS-AND-CHECK

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiy8z6blhj31cq12cn0z.jpg)

So that gives us actually a broad class of algorithms.
Not the most efficient, not going to work in every case,
but a good guess-and-check algorithm
is something where you guess a value,
you check to see if it's right, you change the conditions
inside the loop, and you keep guessing
until you find a solution or you've used up
all the possible values.
This is an example of a set of algorithms
called exhaustive enumeration, and you
can see why "exhaustive."
Two reasons.
One, you're going to exhaust all possible options to use.
And two is it's going to take a while to run,
so you get tired waiting for it to finish.
But as computers get faster, surprisingly,
many of these algorithms can actually work quite well.

CLEANER GUESS-AND-CHECK -  cube root

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fjiy9z6fbkj31cq12un0u.jpg)

On the other hand, I might not want
to always think about making sure I initialize a loop
variable, do a while-loop and then change it inside.
So I could clean this code up by using
the other kind of variable-- sorry,
the other kind of iteration structure, a for-loop.
So here's a nice variation of that.
I could set up a value for cube.
I could have read it in, but I could set up
a value for the thing I'm trying to find the cube
root of, and then just run a for-loop, because I know
that the cube root has to be less than cube itself,
at least for positive integers, things greater than 1.
So I can simply use "range" to generate all possible things
I want to use as a guess, and then
run a for-loop, where I'll run this and simply say, again,
check to see, is guess cube equal to cube?
If it is, I'm done.
Let's see what happens if we find-- if we try that one out.
So I've got a little simple version of that over here.
I'm going to start off with cube equal to 8.
And if I run it, does the right thing.
It says cube root of 8 is 2.
Let's try 27.
And if I run that, wow, it's great.
Cube root of 27 is 3.
This is working really well.
OK.
But suppose I now give it something different, like 28,
and I run it.
Hm.
What happened?
Well, it completed.
I can check that over here, if I go back to my process.
I've got things here, but it didn't print anything out.
Ah, because I made a slip when I wrote the code.
That code is going to run through all possible options
for guess, but it's only going to print something out
if in fact I find something that is the cube root-- if there
is a perfect cube.
28, that's not going to happen.
It didn't give me anything informative.

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiye5bq2cj31f012ywji.jpg)

So I ought to clean that up, and I can, by simply saying,
do the same thing.
I've actually cleaned it up to add
an "abs" here so that I'm going to deal
with the negative cases.
But do the check here, and if I get to a place
where I've gone too far, simply break.
Break out of it.
OK?
Otherwise, run through the loop, but now, when I do the check,
do the print.
Otherwise, do the check with the second piece.
And actually, I've done that in an inverse way.
Here I'm checking to see it's not a perfect cube,
and I'm going to print that out.
If it is a perfect cube, I'm going
to basically determine whether I want the positive or negative
version of it.
So I'm cleaning up two things here.
I'm allowing for negative integers,
but I'm also allowing for it to print out something that's
going to do the right thing.
And let me show you what would happen if I run that version.
So now when I run this, cube root of minus 27 is minus 3.
And if I give it a minus 28, it says it's not a perfect cube.
And I'm all set.
**What was my point?**
**When I run the code, I shouldn't just**
**run it on things I'm expecting, like perfect cubes.**
**I should run it on other things to see**
**if it does the right thing.**
When it didn't, I wanted to add in a different check,
and I added in a second thing here which
I had done earlier, which is to make
sure I can deal with negative integers and not just positive
integers.

### EXHAUSTIVE ENUMERATION

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fjiyggupelj31da12s422.jpg)

But that now gives us a nice tool.
I've got exhaustive enumeration, guess-and-check methods that
can work on problems where there's
a finite number of choices.
I can come up with a way of exhaustively testing
all of those, and it's a good way
to generate guesses in an organized manner using
those iterative loops as a technique to tell when I'm done
and to return a great answer.
And we're going to build on that idea as we move on.