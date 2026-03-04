# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P29：-029-Pattern Matching Chap3 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we've seen some of the other basic built in data types in OcaMel。

 and we've seen how to create values of those types， let's study how to break them apart。

Pattern matching is a feature that enables us to do this in general。 It's a very powerful feature。

 We're going to build up from the basics of it to something more complicated。😊。



![](img/de69a48bacd50d8b9bb16deefe5a2bb7_1.png)

Here's a very basic use of pattern matching。I could write match and some expression。

 let's say not true， which of course， we know evaluates default false with。

And if it evaluates to true， I could return nope， I know that that's actually not what it's going to evaluate to。

Or if it evaluates to false， I could return yep， because I know that is what it's going to evaluate to。

And I do get y。

![](img/de69a48bacd50d8b9bb16deefe5a2bb7_3.png)

A better way to format this actually would be with some line breaks might help us understand a little better。

So I can't really do that easily here inside of the terminal。

 but I could put this inside of VS code to format a little more cleanly， so let's do that。

I've created a file to sort my matching code in， could say let X equal。Match， not true。With。

If I get true。No。Else， false。Yeah。And if I were to load that code into Utah here。Use matching。

t email。 I've got the string， yeahep。So that's a pattern match。 I'm matching against a value here。

 And if it's one thing。Im returning one value。If it's another thing， I'm returning another value。

This might look a bit like a switch statement from other languages in the C or Java family。

 If you have seen those before。 turns out it's more powerful than those are。

 but it's not a bad place to start trying to understand it。

 If you've seen that kind of syntax before。How about another match expression here。

 Let y equal match 42 width。And then I'll say a A， so I'm just introducing a variable name here。 A。

 I picked it randomly。 I could have said foo， if I wanted there to， if you like。

What does this evaluate to？Well， I could load that into U with use or I could just copy and paste it ladder is going to be a little simpler here。

Evaluates to 42。So I've matched against 42 as an expression。With a pattern variable here。

That pattern variable is going to have the value 42 inside of the right hand side here of that arrow。

 So whole thing is called a branch。 We had one branch here in this match expression。

 We had two branches up here in the first match expression。We could also match against， let's see。

 we've done booles， we've done integers， we could also match against strings so I could match。

The string fo with。Does that match bar， Well， it shouldn't definitely not。

 How about I return 0 for that。And with， well， if if fo match anything else。

 like suppose I just didn't care what it was。Good right underscore。This is also called a wild card。

 It's like， match anything you want。Could return one。

What's Z going to be bound to here when I run this， Well， it's going to be one。I hope。There we go。

 It is one。Because food does not match bar， they're not the same string。

 So no matter what else the expression we're matching could have been。

 we're going to return one in that case。 So's sort of like a default value at the end， if you like。

We can also use pattern matching with structured data。

 pieces of data that are bigger than just ins or strings。

 We can use it with lists and tuples and records。Let's say， let a equal。Match， O say the empty list。

With。If I've got the empty list， then return the string empty。 Otherwise。

 if I've got some bigger list， I don't care what that list is。 I could return， not empty。

If I throw that into Utah， what do I get？Empty。😡，Match the empty list with。 If it's the empty list。

 return the string empty。 So I got the string empty back。Of course。

 if I had been matching that with something else， like'd say the list 1， too。

 I ought to get back not empty。 Let's try that out。And indeed， that's what I get。

But we can do much more than just checking whether a list is empty。

 Suppose we wanted to get a piece of the list out。Let be be。Match。Taylor。Swift。

One of my favorite artists。If that's the empty list， then return， how about folklore？Otherwise。

 if it's not the empty list， suppose I just wanted to get out the first piece of that list。

 like the first element of it。I can do that。By writing something that we haven't seen so far here。

And write， H cons T is called a pattern。 It looks a lot like a normal expression。 In fact。

 all of the things we've been writing on the left hand side of arrows here have been patterns。

But now on the right hand side， I can use that H or that T over here， just like up here above。

 I could use foo when I wrote it。So if I return H here， what that's going to do is match the list。

 Taylor Swift。 Is it the empty list。 No， go on to the next possibility here。

 Does it look like head cons tail for some head of a list and some tail of a list。

 I'm using head here to mean the first element and tail to mean the rest of the elements in the list。

If so， then return the head。Let's see what happens when we put that into Utah。I get Taylor out。

As we've matched the list， Taylor Swift。Against the pattern， H cons T。

Inside of that branch of the pattern match， H is going to be bound to Taylor。

Tea is going to be the bound to the list， containing the string。Swift。You want to see that。

Let's try changing this to tea here。And I get a type error。Why do I get a type bear。

 This expression has type string list， but an expression was expected of type string。Notice how。

The list containing Swift is inconsistent with the type of just the string folklore。1 is a string。

 the other is a string list。So maybe I could change that to be a string list there now the type error goes away。

Let we run that again。We get the list containing Swift。

So I've used pattern matching here to kind of split apart the list and get at a piece of it。

I can do that with tus and records as well。Suppose I wanted to get out the first component。

Of a triple。I'll call that FST3 the first component of a triple。And suppose I take in a tuple。

 I could match that tuple with。And it has a first component， a second component。

 and the third component， I'll call those A， B and C。I could return the first component of it。

So now that I have that code。I could take the first component of a coordinate in X，Y，Z space， say。

 one，2，3。But it's with first。3 that I just wrote that that works。 Remember。

 the FST that's built into the standard library only works with pairs。

 It Lets me take the first component of a pair， for example。Okay。

 so the fact that the standard library doesn't contain a first for triples that probably suggests it's not something people find useful terribly often and that's more or less true。

 by the time you have three or four or five or eight components of a TL。

 you're better off usually using a record at which point you'll access by name instead。

Let's try one more example with records。 Now。 suppose you wanted to form a string based on a Corneian's name and here。

 So I can say let name with year of some student B。 Now， of course。

 I could do this with field access。 But for fun， let's try it with a match expression。 match S with。

And I have a record， the name and a year。 So I can just write the field names in there。

 name and year。And on the right hand side here， those will be bound to the values of those fields inside the record S so I could write name concat。

Space and then a single quote。I could convert that ear to a string。String of int。Year。

And now I have a way of producing a name for someone。Let's reuse that file。

And now I can say what is the name with here of RBG？Ruth Baer， 1954。Of course。

 usually we don't write those with the 19 dowey。 We usually just write it as 54。

 so I could say year Mau 100。

![](img/de69a48bacd50d8b9bb16deefe5a2bb7_5.png)

And that gets me Ruth Bader 54， as her graduation year。



![](img/de69a48bacd50d8b9bb16deefe5a2bb7_7.png)