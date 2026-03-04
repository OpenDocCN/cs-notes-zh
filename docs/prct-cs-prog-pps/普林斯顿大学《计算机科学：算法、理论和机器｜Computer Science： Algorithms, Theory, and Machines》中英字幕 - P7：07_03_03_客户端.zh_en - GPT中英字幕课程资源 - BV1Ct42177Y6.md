# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P7：07_03_03_客户端.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/4aa21ea508cdc25a5b0caa8ae29fbbbc_0.png)

As usual， before talking about implementations， let's talk about some client codes so you can appreciate the utility of these data types。

There's a huge number of applications， a queue is first come first served resource allocation。

 so this is a line of cars waiting to into get onto a bridge， data transfer。

 standard in and standard out are examples that use the queue abstraction。

 first thing that you read in， you want that to be you want those to come in the order that they were presented。

So or if there's a shared resource within your computer system， any kind of shared resource。

 even in the real world like this line， you want first come first serve。

 that's what cues do and in all kinds of simulations of the real world。

 you want to be able to develop this discipline and that's what our Q data type does。

Stackax is a different kind of discipline。 It's also real world When you have a stack of books and you get another book you put it on the top of the stack and then maybe you're going to read the one on the top of the stack。

 It's maybe not what you want it to do， but that's what happens in the real world Last come first serve resource allocation。

 They actually play and critical role in programming languages when we have function calls and we did examples of recursive calls。

 those are implicitly stacks the place that you go back to is a place that you most recently came from It's a very basic mechanism in programming languages and computer systems。

 very fundamental abstraction and computing and we'll come to examples of that very soon。Okay。

 so here's a Q client example for standard input， standard input now actually implements this。

 this is the readall strings， when we initially implemented standard In we didn't have it。

 but we realized it's a fine example of a Q client。

So we want to take all the strings that are on standard in and just put them in an array。

And so that's the implementation that we're going to look at next and here's a client。

 so thats we just want to read all the strings， put them in an array and then print them out。

Now so this is get Moby Dick into an array， and then we can process data as an array of words individually。

So the challenge in this is that you can't store the strings in an array before you create the array in Java。

 so when I'm implementing read all strings， I'd like to put them in array but I can't create the array because I don't know how many strings。

And you have to know the number of strings in order to create an array in Java。

 you have to know how big an array you want to create。

And but you can't know how many strings there are in the input stream until you read them all now you can various ways to get around this。

 but conceptually that's the challenge that we're talking about。

And it's easy to solve with a queue of strings， so let's look at how that works。呃。So。

We're going to create a queue of strings， and now this is what client code looks like。

For generic data types， our API said that you're supposed to put a real type name instead of the place a place of the word item inside the angular brackets。

 so in this case we use string， so that's precisely how you say Q of strings and the variable name Q create a new Q of strings。

So that calls the Q constructor and also specifies that the type name that's going to be substitute for item in all the code is string。

So， now。We want a while standard in is not empty， we're going to call the NQ method so that says add a new item to the Q and the type of that item is string。

 it's a Q of string and we're going to get that string from standard in， read the next string。

So that because the。Size of the Q is not specified anywhere。 That'll work fine。

 no matter how many strings there are。In standard input。

Then we get the size of the string because they're all there， they're all on the Q。

 now we know we can pick out the value n， which is the size of the Q。

And we can now create an array of that size。So that's array words of size N。

And then we can go through and take all the strings off the queue in the order that they came and put them in the array。

 copy them back into the array。And then return that array。

So that's a fine example of client code that uses aU to accomplish a useful task。

 putting all the strings that standard in into an array。In that code。

 if I have a machine in the future that has got 100 times more memory and I can read 100 times more strings。

 I can use that exact precise same code without changing it at all。

That's the importance of this kind of abstraction。Stack example we'll give plenty of examples later on。

 but just in the use of it in your real life， a typical scenario when you're browsing the web is you visit a page。

 click a link to another page， click a link to another page。

 all the system is doing is saving the links that you've been to on a stack is shown in the bottom right in this slide。

So when you click the back button， it just pops the stack and gets you to the most recently visited page。

So even when you're using a browser， you're using a stack。

Now there's one other point about parameterized ADTs a technical point that I have to cover and that's the idea of raport types。

 so the thing is the generic type can't be a primitive type。

 just the way the implementation of generics is built。

 so instead the idea is that for many reasons each primitive type in Java has a rapper type that contains this kind of equivalence got the same value but it's got more capabilities。

 so for example into a primitive type in Java for holding integers。

 but there's a rapper type for integer values it also can hold integers but also has associated methods like parsing and other things that we've used。

It's a little bit technical but it's useful and we've already seen it in code and in this particular situation so first of all。

 one reason for the wrappper types is that they have large set of operations associated with a primitive type。

 but that's not we're talking about now， the main thing now is that instances of rapper types or objects and then they can be used in any way objects can be used like for example。

 to invoke methods but also as generic types。So we can say， and if we want a stack of integers。

 we have the generic type has to be an object， so we'll use the associated wrappper type。

And then the other thing that makes us convenient in client code is that Java automatically does casts from primitive types to rapper types when warranted。

So when you say stack。 push 1717 is an int literal。

 but Java knows that it needs to be an integer object。

 so it automatically does that conversion at CA， we don't have to do it in client code and similarly the other way。

 when we return a value from stack that's supposed to be integer object and we assign it to an int it's clear that the cast has to be done from the rapper type down to the primitive type in Java automatically do that。

You might not even notice this when you're writing code of this type。

 but anyway it's important to mention that this is a Java language feature。

When we use primitive types for parameterized values in collections like stacks and cues。

It makes the client code very simple without any casts and we like client code with no cas。

So now let's look at an interesting client example for stacks。

 This is called expression evaluation using a particular type of expression called a postfi expression。

The way that you're used to writing arithmetic expressions。

 we use parentheses to express which operators， the order of performance of operators。

 then sometimes there's rules that can help us avoid putting the parentheses。

 but generally if you want to be sure use parentheses to specify the order of operation。

So this says you want to do the two plus3 and the four times 5 before you do anything else。

 so you do those and then that gives you an expression with fewer parentheses and now we do the  five times 20 and add that to one we get 101。

That's an infi arithmetic expression。There's another method for writing an ametic expression called postfi。

And the idea is simply if you've got two operators， two operaans and an operator。

 you write the operator after the operas instead of in between them。

In what's remarkable about postscript， postfi， you can see right away， there's no parentheses。嗯。

And so how's that you have to just take a look at the expression， well。

 what you can do is go through to the first operator since it's the first operator。

 everything before it is operas， in particular the two things right before it must be operaans。

 its operas， so you can just evaluate in this case， 2+3。Then go to find the next operator and again。

 it's the next operator， its two opera have to be right before it。AndSimilarly。

 you can go through and convert the postfi expression to an inf expression in this way。

 don't need the parentheses。And actually， what we'll see is you can just go ahead and evaluate these without even using the expressions if you have a stack。

This is also sometimes called reverse Polish notation because inventeded by a Polish mathematician in the。

19th century， 20th century。It's called reverse pulls because you can do the same thing you put the operator before the operas and get。

The reverse。So this little proof here， this little example you could extend to a proof to show there's only one way to parenthesize a postfix expression and therefore only one way to evaluate it。

What we're going to show is that with a stack compute， we can do that evaluation very easily。

By the way， PostVx has a famous history in the early 1970s。

 it was used as the basis for the first handheld calculator because it was deemed in a little bit too confusing to deal with parentheses when doing calculations and in fact。

 that calculator when you said enter that really means push onto the stack。

 and people got very used to making calculations basically using Postvic with some mental model of the stack。

 just take the two things I most recently computed and compute with them。

That's one of the first hand held calculators in the 70s。

 no parentheses involved and actually that calculator turned out to make slide rules obsolete。

A slide rule is a decidedly nondig computational device that people use for many years。

 if you don't know what they are， you might be interested in reading up about it。Okay。

 so let's take a look at。Postfi arithmetic expression evaluation using a stack。

It's a very simple method。If you have something left on the input， read it。If it's a value。

 just push it on the stack。If it's an operator， then the last take the last two values from the stack。

 apply the operator and push the result back。 let's look at how it works for this example。

 one's a value， so we put it on the stack， twos a value， we put it on the stack， three is a value。

 we put it on the stack。Now we come to plus which is an operator， so we pop the two things。

 two and three， perform the operation and push the result onto the stack。

Now we encounter four with that on the stack。And kind of another five， put that on the stack。

Now the next thing is the times， we pop the two top things on the stack， perform the operation。

 put the result on the stack。Next thing is another operator， pop the two things from the stack。

Perform the operation， now we get 100， put the result on the stack。

And then the last thing is another operator， pop the two operators， perform the operation。

 put the result on the stack。If there's only one thing on the stack and we're at the end of the expression。

 that's the result。Very easy method for evaluating arithmetic expressions。

And here's what the code looks like。So we have a stack of double values。啊。

As long as standard in is not empty。We're going to read the next。String on the standard input。

 which might be a number or an opera an。If it's a star， what are we going to do going。Pop。

The top element on the stack and multiply it by the next element， which we also get by popping。

 take that result and push it on the stack。Same for plus or minus。

And so there's a minus stacked do pop there。Or divide all of those kinds of operations are extremely straightforward。

 we can even do something like square root for our token square root。

 that only takes one argument so we just take the square root of that and pop it。

And you can develop this to include whatever operations that you might want to write down。

And then if it's none of those things we'll say， okay， it must be a double value。

 and we're not checking for errors here， and so you just push double that token is a string that we want to interpret as a double value。

 so we use double at parse double to get it to be a double value and we push that。That's it。

 that's the entire postfi evaluation， then when we're done when we've read all the tokens from the input。

 we take the top thing from the stack and that's our result。And so that program。

 that little 20 line program， does expression evaluation。ItProduces 101 for example。

 if you say something like 15 square plus2 slash， that's equivalent to  one plus squared to 5 over square root to two。

 and that's a golden ratio。Ext useful piece of code and if you want to implement other operations。

 you can go ahead and do it。 it's a very natural paradigm for computing。A。

So very easy to add any operators you want it's actually in the book we have an example where you can actually just do inF if you don't like postF with parentheses at all。

 and that requires two stacks， one for operators one for operaans。

 it's only slightly more complicated than this one and a very fundamental and famous algorithm。

We don't have to actually perform the operations。 We could actually modify this to write the machine language code that performs the operations。

 takes a little。Thoughought to understand what's going on there but it's not that difficult you can take the expression and turn it into a program that evaluates the expression and actually that's an indication of how the Java compiler works very much similar to this if you've got an if for a while you've got more to do or you've got more different kind of code to put out but still the idea of using a stack to keep track of parentheization or in the case of Java code you have to keep track of nested braces and other things like that still stacks or the basis for how the Java compiler is able to figure out what your program is supposed to do and to put out machine code that does it and we'll come back to that in just a second。

Here's another example of stacks in the real world。

 This is the postscript language developed by Warakkenesski in the 80s。

And their idea is to create a turtle with a stack as an effective way to write programs that can produce graphic output。

 graphic image， even images using text。So Postscript program code is if you have a literal value。

 it's implicitly pushed on the stack， just like a postF expression and anything else pops its arguments from the stack performs whatever operation is supposed to do and puts the result back on the stack。

Sometimes you can add commands that drive a virtual graphics machine like a turtle machine。

 and you can also add loops and conditionals and everything else that a programming language like Java has。

 again， it's the marriage of graphics turtle graphics with a stack to get a very expressive programming language。

So here's an example of some postscript code， 100， 100 move to means push 100， push another100。

Call move to that's the turtle command and wheres wheres a move supposed to move to X Y coordinates。

 Wheres it get the X Y coordinates from the stack， pop Y pop X and move there，100300 line2 again。

 that's。100 puts 100 on the stack，300 puts 300 on the stack。 Those are X Y coordinates。

 line 2 is a turtle command to draw a line to that place。 What place pop Y pop X draw a line there。

 300，300 line2， 300 100 line to。 Those define a path that the turtle has traversed and then the command called stroke is a graphics command that applies a stroke to that whole path actually drawing it。

 so that's a postscript code for drawing a square。And actually if you in a lot of computing environments nowadays。

 if you put a percent sign exclamation point in front of that code， double click on the file。

 you'll get a square if you're lucky， or maybe it takes a little more work。

This is a very simple virtual machine， but it's definitely not a toy。

 the way that Warock andeski uses was to develop applications where it's easy to specify what's in the published page。

Easy to implement on lots of different printers so that's because it's got this simple turtle graphics model in this ushered in desktop publishing。

 completely revolutionized the world of publishing and nowadays everything， packaging， books。

 magazine papers， even quite a bit of web content is specified。

 the image that you see is specified in terms of postscript code， which is built on a stack。

Another important example of a stack machine is the Java virtual machine when the Java compiler converts your code into simpler code for execution by machine。

 it's actually using a stack machine and there are programming languages and other machines out there that are based on stacks。

And again， the whole concept of a stack， the operation should be constant time and the stack can grow without bound。

 there's no limitations within the program on the size of the stack。

 means that something like postscript which was developed over 30 years ago is still in use today because there's no restrictions on the size of the stack within the code。

 and it's an extremely simple model that's able to be implemented on all sorts of machines。

So those are some examples of client code， now let's look at implementations。



![](img/4aa21ea508cdc25a5b0caa8ae29fbbbc_2.png)

![](img/4aa21ea508cdc25a5b0caa8ae29fbbbc_3.png)