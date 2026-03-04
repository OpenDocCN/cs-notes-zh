# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p137 39_05_static-versus-dynamic-typing-part-one -BV1bw4m1D7MM_p137-

In this segment I'm finally going to start the discussion of which is better static versus dynamic typing and sorry to disappoint you。

 but I'm not going to reach a firm conclusion instead the way we're going to do this is we're going to consider arguments reasons why static checking may be superior or why dynamic checking may be superior and we will give corresponding arguments similar arguments for both sides on similar topics we'll start in this segment and then we'll continue in the next one remember of course。

 that most languages check something things statically and other things dynamically so it's not a matter of should you check everything statically or everything dynamically。

 but for anything you're going to check there are advantages and disadvantages about when you do the checking。

So let's start。Probably one of the most common arguments people make in favor of dynamic type systems。

 languages that check things dynamically is that they're more convenient that if you want to build a list that holds data of different types or you want to write a function that returns things of different types。

 you can just do that。 And you don't have a type system getting in your way。

 So you see the rackcet code here at the top， And I have this function F that sometimes returns a number by adding Y and Y and sometimes returns the string high。

 And if you want to do that， you can just do that。The corresponding M code at the bottom makes you go and create some data type definition。

 In your own tags for In and string rather than the language just doing that for you。

 And then in the definition of F， you have to remember to put the right constructor in the right place。

 So it's just clumsier code。 It was more work for the programmer。

The people in favor of racket would also point out that when some user of this function F needs to use the result。

 it has nice built in primitives like number question mark that just can therefore know whether the function return to number a string。

 And this is exactly the natural thing to do， knowing that F sometimes returns a number and sometimes returns as a string。

 whereas over an M， we the program has to use this data type binding we define and then use pattern matching to get the pieces out。

 So dynamic typing seems more convenient for this sort of program。But the static type system。

 people say， now， wait a minute， wait a minute。 if you want to talk about convenience。

 what could be more convenient then we have a type system that enforces that the arguments and the data you receive from somebody already has the right type。

Suppose I want to write some simple function that just cubes its argument。Well， in ML。

 if I write fun cube x equals x times x times x， I know absolutely that anyone in the program that ever calls cube in any way will pass an integer。

 so I don't have to worry about any error checking。

 I can just do the multiplication and return the result。Whereas in rackcet。

 we know that you can call a function with any argument you want。

 so maybe if I want to be more careful if this is something the outside world might use。

 I need to put some sort of check here that I was actually past a number。

 racket actually has an entire contract system I didn't show you here for a more uniform。

 easy to document more standard way of doing this sort of error checking。

 but how could it be convenient not only that I have to do these checks。

 but I have to wait until run time for these checks to fail if someone does actually misuse my function。

So that's the argument on that site。Let's give another argument for dynamic typing now。

 and that's that all that static type checking always prevents useful programs。

 There's always some program someone wants to write that's been rejected even though it makes perfect sense。

 So I have a short example here that I kind of like just because you might think that M would allow this。

 but it doesn't。 so let me show you this in M real quick。 not there just at the Reple here。

 Sose I want to write a function that takes in， it's called F， but it takes in another function G。

 and then it makes a pair of calling G with an int and G with a bo。



![](img/b00bb983d700a48ac04827382c1a08d4_1.png)

It just doesn't touch it。Type inference doesn't work that way。 The type system doesn't work that way。

 even though it would make perfect sense， as long as G was itself some function。

 maybe just an anonymous function。 if I could pass in something that say makes a pair out of its arguments。

 this would work perfectly fine。 and ML just rejects it。



![](img/b00bb983d700a48ac04827382c1a08d4_3.png)

So that's what I have down here at the bottom， you would think this code makes perfect sense and it will not type check type system is just not powerful enough for it。

The rackcet code works just fine。 You can define a function F takes in G。

It calls it makes a pair out of calling G with 7 and G with true。

 It's exactly the same as the ML code here。 And then I can call it。

 I can call F with a function like lambda X cons X X。 And if I do that。

 I'll get a perfectly good result。 I'll get back the pair of 7 and 7 cons together with the pair of true and true。

 There's nothing wrong with that。 And so static type checking is just getting in my way。Now。

 the static checking people would say， now wait a minute。

 the only way racket was able to do that was by tagging all the data in your language and always checking before every car operation that you have a pair。

 before every addition that you have a number and so on。

We can do this in ML if you want to pass things of different types around。

 then you just have to use your own data type findings and you can now have the control as the programmer in tagging exactly where you want to tag and not tagging where you don't need to and in the extreme as I showed already once in earlier。

 you can program in an entirely racket-like way an ML if you want to by creating the one racket type with a constructor for every kind of data and do all your own tagging and pattern matching every time you need to use a value。

Now this may be less convenient than in racket， but racket in some sense。

 forces all programs to always have in check tags， whereas in aesthetic statically typed language like ML。

 the programmer is in control of where things are tagged， where things can fail。

 where things are checked dynamically。So one more argument in this segment。

Probably the best argument people usually make in terms of static checking is that it catches bugs earlier。

What could be better than catching bugs before you ever write test programs before someone misuses your function。

 as soon as you try to use the file， you get an error。😡。



![](img/b00bb983d700a48ac04827382c1a08d4_5.png)

So let me show that by actually flipping over here to SMML again。 you see I have here this function。

 Pu 1， we'll get to Pu 2 in just a minute。 And if I go to try to use this。

I get an error message and the reason is that PA1 actually expects two curri arguments。

 the recursive callar to pass them in terms of a pair。

 and it's good that I have an automatic system to catch that sort of bug。

 whereas if I'm over here in racket， I have the corresponding code here。

 PA1 it takes in one argument returns a function so this really is occurring。

 but then here in the recursive call I guess I'm passing two arguments instead of passing them in a cur way and that compiled just fine。

 and it's not till I try to go and use power1 with say three and4 that I get an error or even if I get it right here at the initial call。

 I'll get an error at the recursive call site so I have to test it to catch these errors and figure it out that way。

 So that is basically the argument in favor of static checking that it catches these simple bugs for you that are actually quite hard to find just by staring at the code。



![](img/b00bb983d700a48ac04827382c1a08d4_7.png)

But the dynamic type， people say， now， wait a minute， wait a minute。 Yes。

 it catches lots of those simple bugs for you。But it tends to catch the easy bugs。Right。

 it catches the same bugs。 the dynamic typing people would say。

 as you are going to catch later when you test your function and don't even try to tell me that static typing is so good。

 You don't have to test your function。 because that's just not the case。

 The dynamic typing people would say， okay， M L， I appreciate that your power1 didn't type check。

 So let's comment that out。 You caught that bug nice and easily。 But now let's look at P 2。😊。



![](img/b00bb983d700a48ac04827382c1a08d4_9.png)

So let's go back over here。To SMML， and let's use the file now。And Ill look at that。

 Everything compiled。 I have a wonderful power 2， takes two cur arguments。

 And if I call it with3 and 4， I get 13， which is not 3 to the fourth power。

 which is what I was trying to write。 And the reason is。😊，Car me。

 the reason is that right here I wrote plus instead of times。

And no type system is ever going to catch that because plus in times take arguments of the same type。

 and if you're going to have to test your functions anyway。

 then what's so bad about the racket code where testing the code caught my error for me and I do have here the version of PAu2 that is wrong in the same way as the ML version plus instead of times and I can just test it in the same way and if I call PA PA2 in cur form with3 and4。

 I will also get 13， which I should realize is the wrong answer。



![](img/b00bb983d700a48ac04827382c1a08d4_11.png)

So those are the first three arguments for and against static and dynamic typing。

 I believe they're all valid， it's a matter of which is more important to you and we'll continue with some more reasons in the next segment。



![](img/b00bb983d700a48ac04827382c1a08d4_13.png)