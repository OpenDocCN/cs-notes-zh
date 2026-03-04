# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p40 39_12_each-of-pattern-matching-truth-about-functions -BV1bw4m1D7MM_p40-

Okay， welcome to one of my favorite segments in the entire course。

 whereby extending our definition of pattern matching just a little bit。

 we're going to learn the truth about a lot of what we've been doing。

So what we're about to find out is that we've been using a lot more syntactic sugar in our ML programs than we even realized that in fact every value binding and every function binding can use pattern matching。

 and then in ML as a result， every function takes exactly one argument， not zero， not two， not three。

 and this is a very flexible， elegant way to design your language。

 but before we get to that great punchline， I need to extend our definition of pattern matching a little bit。

So so far we used pattern matching only on our one of types on our data type bindings。

 and that's because we needed some way to access the values。

 the only way we could take something that had one of our data type types see which constructor it was built from and get the underlying pieces out was with pattern matching and that's still the case but it turns out that pattern matching also works for each of types。

 it works for records and since tuples are always just syntactic sugar for records it works for tuples as well so let me tell you how that works。

 and then I'll show you a number of examples which will use in increasingly good style as we go along。

So here's a new kind of pattern What you can do is in a place where you put a pattern。

 you can put a tuple pattern which looks a little bit like a tuple expression。

 except between the commas we have variables and what that's going to do is if you pattern match one of those expressions against the tuple value。

 it will bind， it will introduce a local variable or x1 is the first component of the tuple x2 is the second component of the tuple and so on up to Xn being match against the last component of the tuple and the type checker will insist that the number of pieces of your tuple correspond to the number of variables in your pattern you're not allowed to mess that up。

Similarly for records， we have a new kind of pattern where you write field name equal variable name separated by commas inside of braces and that matches a record value that has those same field names As usual the order of the field names doesn't matter and what happens when you do this match is the variable X1 will be bound to the value in the F1 field x2 in the F2 field and so on so that was a little abstract。

 let's see some examples This is poor style， but it helps explain how the pattern matching works and will'll get to the better style in just a second。

So first， suppose I had a triple， a threetuple where each component was an integer and I just want a little function to add those three numbers up So what I could do is I could have a function some triple that took in some argument call it triple then I could have a case expression where my pattern matches against tus that have three parts and in fact since I use X Y and z to bind to the corresponding three pieces of data inside that triple I can use those variables on the right- hand side and since I add them together those pieces must all have type int and so the type of some triple is int star int star int。

 the type of three tuples holding three integer things and the return type is int。And similarly。

 here's a function full name。 It takes a record where you have fields first middle and last here I'm concatenating them all。

 this carrot character is ML's operator for concatenating string。 So in fact。

 the three fields are going to have to hold data of type string and this pattern here is extracting its binding to X。

 whatever is in the first field， binding to Y， whatever is in the middle field and binding to Z。

 whatever in the last field。 So we're using pattern matching to get the pieces out。

 We're just doing it on each of types instead of one of types。Okay。

 so now let me tell you another feature that gives us a better way to write this down。😡。

So it turns out ever since the very beginning of section 1。

 I told you that v bindings were written by v variable name equals expression。

And it turns out that's true but it's not the whole truth that what you can actually write is vow pattern equals expression and variables are just a special kind of pattern where the variable matches against the entire result of evaluating the expression E but if you put a different pattern there then it will match against the expression E as well and extract the various pieces This is great for extracting the pieces of an each of type you can even only get some of the pieces out that you need It's bad style to do this where that E is one of the constructors of a data type binding and the reason is this is going to be like a one arm case expression。

 a case expression with only one branch that's great for each of types because you only want one branch but for data types you really want all the different branches and you just put one here you will get an error at runtime if you're wrong and you're giving up the advantage。

😊，Of using case expressions where the type checker makes sure you cover all the possibilities。Okay。

 so here's how our examples would look now。 Instead of using a one armm case expression。

 which is bad style， let's use a let expression instead。

 So now my function sum triple is going to take in this triple。

 And what I'm going to do is pattern match it with this vow binding here。

 So that will indeed value it triple will look up triple in the dynamic environment。

 It's going to get some value， and it's going to make sure that x is bound to the first piece Y to the second piece。

 Z to the third piece。 Then x， Y and z will all be local variables that are in scope in this let expression。

 and I can add them together。 So the type checker will make sure that indeed triple is a topple with three parts all of type n。

 because otherwise the rest of this expression wouldn't type check。

And my full name function works similarly， except now I have a record pattern。

 and since I'm concatenating X， Y， and Z， R has to be a record that has exactly the field's first。

 middle and last， all holding strings， so this is actually quite nice style。

 but I'm going to show you something even better。So here's the final version of how I want to write these things。

 and I have to tell you one more truth about ML。It turns out that a function argument can be a pattern and not just a variable。

So the same way I used to tell you that function bindings looked like name of function variable equals body。

 it turns out what goes right there is actually a pattern， again， if it's just a variable。

 it's going to be matched against the entire argument to the function， but if it's a pattern。

 we'll go ahead and extract pieces of the argument。So now what I have are these beautiful functions。

 some triple takes an argument that will then be pattern matched against this tuple pattern。

 binding x to the first piece， y to the second piece， Z to the third piece。

 and the body can do whatever it wants， add them together。

Full name similarly will have to be past something that can match against this pattern。

 only record expressions with first middle and last fields will match appropriately and since X， Y。

 and Z are used as strings in the body， the type checker rule will require full name to take a record where first middle and last all hold values of type string。

So now that we can do this and now that we have pattern matching for extracting pieces of tuples and records。

 we can write this much more concise， elegant， simple code and to make sure you get practice with this。

 we're going have a rule on homework2 which says that you're not allowed to use anything with the hash character。

 this pound character on your keyboard shift3 for me that's how we used to get pieces of tuples out with hash1 and hash2 and we used to get pieces of records out with hash field name but on homework2。

 we want you to instead always use pattern matching because that's what we're working on。

And one of the nice benefits is because you're writing down these patterns。

 the type checker will always be able to figure out the type of thing you're matching against。

 so you will no longer need to write down any explicit types for the arguments to your functions or any other variables that you're using。

Okay， so now that we know how to do this。 let me switch over to the code and show you something really interesting。

 So here in the file， I have the three versions of both full name and some triple we've been working on。

 So this first version is bad style because it uses one armed branches。

 which don't make a lot of sense。 The second version is okay because it uses a vow binding instead。

 And then this third version is the simple one where， in fact。

 we put the pattern directly in the function argument。😊。



![](img/e70ef777101f2953f924562b65f735f6_1.png)

Now， these are just three ways of implementing the same thing。 So one is really syntactic sugar。

 if you like for another。 So if I go over here and run this。Or at least load all these things in。

You'll see that all three versions of some triple have type。

 Give me a tuple that takes three ins and returns an int。

 and that's the type of all three versions of some triple you see here。 and similarly for full name。

 they always take in a record of first last middle string and return a string。 and indeed。

 these are three ways of writing the same thing。 So you get a 12 if you do it that way。

 and I'll try one other here， you get a 12 if you do it。This way， so in all cases， take a triple。

 return an int。 But I hope some of you are almost ready to jump out of your chair saying。

 wait a minute， wait a minute， wait a minute。 Let's look at this third possibility here。

 This sum triple。 that looks to me like a function that takes three arguments。

 That's how we used to write things that take three arguments。

 And now you're telling me that it's a function that takes one triple is an argument。

 So how can Ml tell which of it I'm trying to do when I define the function there。 And also。

 oh sorry， when I call it， as I meant to here with the third version of the first one。

 how does it know to passing in one triple and pattern match against it instead of passing in three arguments。

 a3， a4 and a5。

![](img/e70ef777101f2953f924562b65f735f6_3.png)

Okay， so let me put this another way。Here on the top of the slide is a function that takes one triple of type intstar instar int and returns an int。

 and it does it via pattern matching， as I've just taught you in this segment。

Here on the bottom is a function that like we learned a long time ago， is takes three arguments， X。

 Y， and Z， and adds them together and returns it。So if you see some difference between the top half and the bottom half and you're seeing something I don't because they're exactly the same and in fact。

 every function in ML takes one argument， not three。

 and we've actually been using pattern matching all along， I just didn't tell you。

So here is the big truth in ML， every function takes exactly one argument。

And what we have been calling multiargument functions are really just functions that take one argument that is a tuple。

 and those functions are implemented by using pattern matching on that tuple so that you get the different pieces of that tuple out。

 This is extremely elegant and flexible， And I'm not going to kid you。

 Everyone when they talk about M code talks about a multiargument function。

 a three argument function a four argument function and so on。

 But we know that what's really going on in terms of the language is that that's just syntactic sugar。

 We're passing one argument that is a tuple and thenre pattern matching to get the pieces out。

And this is actually a useful thing to do， so I have a short example here on the slide that I'll use to finish up this segment。

 here is a very simple program to rotate the pieces of a tuple。

 so how about I just implement that real fast over here。

 rotate left x comma y comma Z equals y comma Z comma X all right。

So now if I call rotate left with3 comma 4， comma 5， and I actually spell it correctly。I get 4。

 comma 5， comma 3。 All right， so I took in some tuple， and I returned a tuple。 and that's all great。

 But what I could do is I could take that thing that was returned。😊。

And pass it into another function like rotate left in which case I would get5 comma 3 comma 4 or directly into say some triple3。

 which case I should still get 12 because the order doesn't matter when you're summing things up。

 This is something you can't do in a lot of programming languages。

 It's usually very awkward to return multiple things from one function and immediately pass them to another。

 but in M， every function takes and returns one argument。

 rotate left takes one triple is an argument。 So if I have some expression that returns a triple like rotate left does。

 I can immediately take that thing and pass it to another function。

 So I have another example here on the slide which is I could write write a rotate right function that takes in some triple T and just implements it by rotate left of rotate left of T because it turns out if you have a triple to left rotations is one right rotation。

 So it's a silly example， but it's nonetheless。Elegant example of how having this policy of every function takes and returns one argument。

 it becomes much easier to take the results of one function and pass them directly to another。

 So now we know the truth about M functions。 everything takes one argument。

 This is one of those great segments where we made our language bigger by adding new kinds of patterns。

 pattern matching over each of types。 But as a result。

 we made our language smaller because we now know that there's no need to have a special concept of multiargument functions。



![](img/e70ef777101f2953f924562b65f735f6_5.png)