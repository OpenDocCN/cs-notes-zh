# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p105 7_05_parentheses-matter-debugging-practice -BV1bw4m1D7MM_p105-

Let's talk some more about parentheses， and let's particularly understand that parentheses are not optional in racket。

 They are common， but every time we use them， they have a meaning。



![](img/439d786ebc584210299519597cdeec62_1.png)

So this is a habit you have to break yourself of in languages that don't have a syntax like rackcet。

 you're used to just putting in extra parentheses to help you understand something。

 and if something isn't working， maybe you'll just put in more parentheses and then it will start working that doesn't work in racket。

 the parentheses always have a meaning。In particular， in most places。

 if you write something in parentheses， that means evaluate E to a result。

 and then call it as a function with zero arguments。

Because the way we do a function call is parenthesis thing you want to call and then arguments。

 So if there are no arguments， this is call it with zero arguments。

So look at this one with two parentheses。 This says evaluate E。

Call the result as a function with zero arguments。Get back a result and call that as a function with zero arguments。

 This makes perfect sense。 We might even do things like this。 but if it's not what you mean。

 you're going to get an error message。 You're going to try to treat something as a function that is not a function。

Now without static typing， this sort of thing will work just fine when you save your file when you click Run。

 but once you actually execute the code， maybe it's inside a function body somewhere。

 then you can get an error message， it can be hard to diagnose and your first reaction is to just start playing with the parentheses and that's only going to get you into more trouble。

So let's work through some examples to give you some practice with this。

 and the moral the story is always slow down， think about your parentheses if you're confused why they're there。

 delete them and start over， indent your code well， it'll all work fine。



![](img/439d786ebc584210299519597cdeec62_3.png)

![](img/439d786ebc584210299519597cdeec62_4.png)

![](img/439d786ebc584210299519597cdeec62_5.png)

So what I'm going to do is just show you a bunch of versions of a factorial function。

 one of my favorite little functions， for examples， and I'm going to start by getting it correct。

Okay， so so far， what I've written while I was assigned you is that fact is a one argument function。

 So these parentheses have to be here。 then I have an if and I need three arguments。

 This is the first one。 It's going to call to the equals function。 This is the second one。

 which is one， and then this is the third one， which is multiplication of n and then another call。

 always put a parenthesis before the call a fact to get the argument to that。

 I need to call minus with n in one。

![](img/439d786ebc584210299519597cdeec62_7.png)

![](img/439d786ebc584210299519597cdeec62_8.png)

![](img/439d786ebc584210299519597cdeec62_9.png)

Close， close， close， close， close。 And let's run this。 And if I do fact of 5。 I get 120。

 And if I do fact of 10， I think I get about 3000000，33。6 million。 Excus me。 Okay。

 so that version was right。 Now， let's do a bunch of versions that are wrong and try to figure out why。

 So let me do， I'll call it fact1。 and if equal and 0， then1 L N fact 1 of minus N1 close everything。



![](img/439d786ebc584210299519597cdeec62_11.png)

![](img/439d786ebc584210299519597cdeec62_12.png)

And run it。

![](img/439d786ebc584210299519597cdeec62_14.png)

It all seems to be fine。 I call fact1 with five， and I get procedure application expected procedure given one。

 no arguments。And that's exactly right。 If you look up here。

 what I did while I was talking to you in typing is Id put this one in parentheses。

 And as an expression， that means call1 as a function with no arguments。

 There's no type checker to separate our functions from our integers。

 But when we meant to execute this in the base case when n was0， that's when we got the error。

 So we had already made about five recursive calls。 and then we got the error。

 and we would fix this up by deleting these parentheses。

 We can just leave this in here because as long as we don't call that function。

 It won't be a problem。 Let me show you a small variant。 is fact 1 B。

 Suppose I made the same mistake。

![](img/439d786ebc584210299519597cdeec62_16.png)

![](img/439d786ebc584210299519597cdeec62_17.png)

All right。Just like this。All right， so you might think if you're not paying very careful attention that this fact 1 B is exactly like the first one。

 and yet it totally seems to work。

![](img/439d786ebc584210299519597cdeec62_19.png)

In fact， this will work for almost every argument。 The only argument it won't work for is 0。



![](img/439d786ebc584210299519597cdeec62_21.png)

So what's going on here？Well here I actually made a totally different mistake This is wrong if you call fact 1 B with0。

 you will try to apply1 with zero arguments， but I'm not actually using fact 1 B recursively here。

 I wrote fact here I didn't write fact1 B I wrote fact and so in fact pardon the pun when I call fact 1 B with5。

 I end up not calling fact 1 B again but going up to this first correct version and so that's why we didn't get the error unless we called fact1 B originally with zero。

Okay， good。 let's try another one。 How about fact2， excuse me。 I need this parenthesis here。

 How about if equal n0，1， otherwise n of fact 2， I will remember now to call the correct thing recursively。

And like that， and click run。And this is actually a syntax error。 So this it will not allow to start。

 I don't have to test it out to get error。 Dr。 Raet will detect that。With a good error message here。

 if has five parts after the keyword， if is always supposed to have three parts and yet clearly syntactically as 5 equal n0。

1 and this multiplication， and that makes no sense if has to have three and what happened is I forgot the parentheses around the function call to equals。

 how about if I do it this way？If。So I'm going to get almost all this right， three terms。

Multiply by n fact of。And minus n1。Just like this， click run。And I get bad syntax。

 multiple expressions after I identifyentifier， indeed I do。So if I say define and a variable。

 notice I forgot this parenthesis after the fact3， then it's expecting like a Valbin an ML。

 that I evaluate something here， but I have two things after the variable， this is the first one。

 this is the second one right， I messed up one parenthesis。

 this left parenthesis is supposed to be over here before the name of the function not before the argument list。

parentheses matter。 I know I'm typing fast in order to keep the video short。

 but you should think which concept am I using and in this case， if you're defining a function。

 you put a parenthesis before the function name， you do not put a parenthesis before the argument list。

 Look how up here in the correct version。 I have this， and then I have my function body。Okay。

Allright， let's do another one。 This one。 Oh so I need to comment these out these。

 these ones so that I can get the other ones to go ahead and click run so that I can test them out。

 Here's my fourth version of fact。 How about if equal n 0。

1 otherwise multiply n by my recursive call to fact 4 with minus n and1。Click run。

 This compiles just fine。 Call fact 4 with0。 I get the right thing one。 But if I call fact4 with 5。

 I get an error message。

![](img/439d786ebc584210299519597cdeec62_23.png)

![](img/439d786ebc584210299519597cdeec62_24.png)

And it says that star expects type number as second argument given procedure fact4。

 That's exactly right。 So it turns out that multiplication we saw back in our first or second segment on racket can take any number of arguments and here I'm passing it three arguments and the function fact4 and n minus-1 functions are first class So you can pass them to other functions。

 but then the body of multiply says wait a minute， I don't have a number， I'm going raise an error。

 a type checker in a language like M would catch this in racket。

 we have to test our functions to test this sort of error， then we need to fix up our parentheses。

 we need an extra parenthesis before fact 4， and then after it in order to call multiply with two arguments。

 not three。Okay， let's do a couple more。 Here's fact 5。N if equal n0。

1 otherwise multiply n by fact 5 minus and1。 So here we saw in fact 4， we had too few parentheses。

 It made us annoyed。 We just wanted to get our homework done。 So we added some more。 The problem。

 of course， is this still works。 but we added too many。



![](img/439d786ebc584210299519597cdeec62_26.png)

And what it says is procedure fact 5 expects one argument given0。 That's exactly right， right here。

I'm calling fact 5 with zero arguments。 Fact 5， which I'm defining recursively right here。

 expects one argument。 You are not allowed to call functions with the wrong number of arguments。

 and we get an error。And then let's do one last one。Just because it's good practice。

And times so this is a very natural thing to do because we've all grown accustomed to writing arithmetic a certain way。

And you can probably see the error this time。 I wrote star F second。

 That's supposed to be the function I'm calling。 Instead， what do you think would happen here？Well。

 again， the base case is fine。

![](img/439d786ebc584210299519597cdeec62_28.png)

But if n is not zero， then I'm going to try to treat n as a function。

 so it expects some sort of error message where the number I called fact six with is trying to be called with some arguments。

Right， when you look at your code carefully， you can sometimes come up with a better error message than you would get from a system that has no idea what it is you're trying to do here。

 I think it'll actually do a pretty good job。 So procedure application。

 expected procedure given one arguments were procedure times1。

And what actually happened is you would think this happened when n would be5 why is it a given five well。

 it never got to this call， it went ahead and did the recursion and that did the recursion and that did the recursion。

 and it's on the way back out of the recursion that it first detects the error when it tries to say one times and the recursive result one and if I'm going to write this out here in record。

 you have one times one。That's going to give the exact same error message because it's going to say that it expected a procedure in that first position。

 and you have a one。