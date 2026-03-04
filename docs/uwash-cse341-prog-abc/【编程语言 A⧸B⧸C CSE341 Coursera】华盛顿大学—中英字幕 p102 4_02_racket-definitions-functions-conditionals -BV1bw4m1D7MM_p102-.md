# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p102 4_02_racket-definitions-functions-conditionals -BV1bw4m1D7MM_p102-

So let's now jump in and get the racket basics out of the way。 Let's learn how to define functions。

 variables， conditionals and so forth， covering a lot of the ground we already did in Ml。

 I have a few slides posted with this lecture。 but I think I'll primarily just stay over here in Dr。

 racket and write a bunch of code with you。 So already have hashling racket and this thing so that I could test in a second file if I wanted to。

 although we'll just use the repel here。 and now let's do a couple of variable definitions。

 So parenthesis define the name of the variable you want to define and then an expression that you evaluate to the variable。

 So this is really like val x equal3 in Ml。 Okay and now we can do another one。

 So definition can use x。 So suppose I want y to be x plus 2。

 So what I do is I call the plus function with X and 2。

 the way you call a function in in racket you write parenthesis the function you want to call and then the arguments。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_1.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_2.png)

So plus really is just a function。 So plus is a function。 And we call it here。

 So this variable Y is being bound to the result of this function call。 And in general。

 function calls are written with a parenthesis before the function you're calling Then the arguments than a parenthesis after the arguments。

 different syntax than in languages you may be more familiar with。

 but that is a function call calling the plus function with X and 2。

So now let's define our own function。's I'm going to write a few versions of the cubing function。

 so I'll call this one cubebe1， and now I'm defining a function。

 So what I'm going to do is I use this keyword Lambda。 Its spelled like the Greek letter。

 racket and earlier dialects of this language like scheme have been using that Greek letter for decades。

 It's a bit of a strange choice。Then the arguments in parenthesis。 So this will take one argument。

 So lambda is a keyword that says I want to define find a function， put the arguments in parentheses。

 and then you have the body， and the body I want is to call the multiply function with two arguments with X and with the result of this other call X and X。

 and then and that call， this call， the lambda form and the defined form。 So this body。

 the just the body here， this part here would be like in other languages writing x times x times X。

But in racket， everything always has the function first。 Then all these operators are just functions。

 And so it looks like this。 We get very used to en racket ending things with lots of parentheses。

 I'll talk more about parentheses in a future segment。 But for now。

 notice all I did was introduce a Val binding。😊，Right for cube 1 and bind it to this anonymous function。

 So Lambda is like Ml's Fn right takes in。 this is an anonymous function that takes in one argument X。

 and has this body that ends up cubing X。 Let me write a nicer version。

 It turns out that you don't have to write it that way， because the multiplication function。

 which is provided to us already by racket， can take any number of arguments and it returns their product。

 So we really can just write it like that。 So multiply in this language is a function that can take any number of arguments。

 There is a way in racket to define your own functions that take any number of arguments。

 But I'm not planning to show that to you。 You can consult it the guide。 if you need it。

 you won't need it for any of our homeworks。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_4.png)

The other thing I wanted to point out here is that this really is just a function call。

 And so it makes sense that we're calling it that way。 Our function cube 2 takes one argument。

 Multiply it takes any number of arguments。 Unlike an M， I'm not lying to you。

 This is not syntactic sugar in racket functions really do take 0，1，2，3，4。

 or any number of arguments。 It's not syntactic sugar for toppling or for curing。

 Okay Let me show you something that we do have syntactic sugar for， though。

 You do not have to write lambda every time。 If you want to do this。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_6.png)

This is exactly like the previous version。 So what you can do is instead of essentially defining a variable and binding it to this anonymous function。

 you can use this syntax instead。 But it's exactly the same thing。

 This is syntactic sugar for define the variable cubed 3 to be bound to a function that takes one argument X and returns。

 has this as its body， X times x times X。 If you had multiple arguments here。

 you could just do like that before that first right parenthesis。

 So there are three versions of cubing functions。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_8.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_9.png)

Now， let's write some recursive functions。 It turns out that unlike in M L。

 we don't need anything new to do recursive functions that you can just use the lambdas like we have been doing or the syntactic sugar I just showed you。

 So if I want to define the exponation function。 I'm going to do this two different ways。

 So I'll call this p 1， the purpose here is X to the。😊，W power。

 and I think my solution only works if y is non negative。All right I just need a body here。

 and now I need an if。 the way you write an if and racket is you write left parenthesis if and then three expressions。

 E want E2 E3， and that is the thing to test for the true branch and the false branch so we don't use keywords then and else。

 they don't exist in rack， we just write the three expressions in a row and then end with a right parenthesis。

 So the way I want to do this is I want to say if y equals 0 equals is a function that takes two numbers returns true if they're equal。

 then one， So I've written two of my three expressions for if and now my third one can be times x。

 and then recursively called poweru1 with x and y minus-1 notice that like every operator in racket minus goes first and。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_11.png)

There it is。 So power 1。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_13.png)

Is a function that takes two arguments， X and Y， and its body is this if expression。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_15.png)

This sorry， if expression， if expression has equal y 0 for its first sub expressionpress。

1 for the second and multiplying x by the result of this call。This call P1 with x and y minus-1。

 So this is the exponentiation function。 you'll notice that we every time we have a function called its parenthesis function you want to call arguments。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_17.png)

So this will work fine。 Why don't we go ahead and run this。 I haven't been running much for you。

 So I just clicked run。 Now I could say power 1， how about three to the second power right。

 so it's a function call。 I pass into two arguments。 I get9。 And if I asked power 1。

3 to the zeroth power， I would get one。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_19.png)

Great， okay， so let's define just a couple more functions。

 Let's do another version of PA that's cured。 So cur has nothing to do with anything other than an idiom with closures。

 And so we can we can do that in racket。 it's not as common in racket because racket is built in support for multiargument functions。

 but there's no reason why we can't use cur。 So。😊，Let's see。 Well， here's a simple version。

 I could just call poweru1 with the two arguments， right？

 So this pu 2 is a function that takes in one argument X。 its body is this lambda。

 which returns a function that takes in an argument Y。 And then I just call poweru 1 with x and Y。

 Of course， I could have my own conditional down here。 if I preferred。 And now that I have this。

 this poweru 2， I could partially apply it， And I could say something like poweru 23。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_21.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_22.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_23.png)

And if I save all that and run it， I could say3 to the with two， and I would get 9， right。

 because I end up taking this function that Pu2 return， calling it with 2。

 that ends up calling poweru1 with3 and 2。 and I get 9。 So it's occurring exactly like N Ml。

 because it's less common if you're not partially applying things。 you know， so if I wanted 16。

 it's quite convenient to call PAu 1 with 4 and 2。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_25.png)

But if I want to do it with PA2， well， what do I need to do， I need to call PA2 with4。

 that gives back a function。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_27.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_28.png)

And now I need to call that function with two。 These parentheses matter。

 parentheses always matter in racket。 If I want to call power 2 with4， I have to write it like this。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_30.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_31.png)

Then that gives me back something that is a function。 And if I want to call that function with  two。

 I need this parenthesis to its left。 and then here。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_33.png)

So it turns out that in racket there's a little bit of syntactic sugar for defining curried functions。

 The code posted with this segment will have that。 you don't need to use it。

 We're actually not going to use cur so much in racket there is no syntactic sugar for calling a cured function。

 this line that I have here really is the best that you can do。

 I bring up cur here both because it's something familiar and I wanted you to see it in multiple languages。

 and also because it emphasizes that we have anonymous functions。

 firstclass functions and whenever you want to call a function， it's always E0 so parenthesis。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_35.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_36.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_37.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_38.png)

E0 for the expression that evaluates to the function you want to call。

 then E1 up to E N for the arguments， then the other parenthesis。

 This is what function calls look like in racket。 Now， if E 0 is not in expression。

 if it's something like if or define or lambda， then those are not function calls。

 Those are other constructs in racket。 We'll continue to see those and understand those in the segments ahead。



![](img/b2359fcaa144d5860558aaccfb7a8fa3_40.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_41.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_42.png)