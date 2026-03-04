# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p15 14_04_shadowing -BV1bw4m1D7MM_p15-

Okay， in this segment， I want to talk about shadowing shadowing is when you add a variable to an environment when before you added it that variable was already in the environment。

 So to do this， we're going to end up having multiple variable bindings for the same variable in the same file that can be a little bit confusing it's usually poor style to do that although it does come up with certain idioms but it's going to be a great way to make sure that we really understand how environments work So I'm not going to give you any new rules。

 there's no new syntax， no new type checking or evaluation rules here we're just going to use this idea of shadowing to really explain how environments and variable bindings work so that we have that solid foundation we need when we go to add things to the language。

 So let's just start here by adding this binding a equals 10 to our environment and so we know now that in the static environment A will have type end and in the dynamic environment a will be bound to the value 10。



![](img/b2d36fa9eff7f27e03c092daf05b6683_1.png)

![](img/b2d36fa9eff7f27e03c092daf05b6683_2.png)

And so of course， if we then continued in our file with a times 2， B would have the value 20。

 I'm going to ignore the static environment here just for expediency。

 but of course that's relevant as well。So now the interesting thing happens if we say v a equals5。

AllrightAnd the thing I really want to emphasize is that B is still bound to 20 and in fact。

 if I next said Val C equals B， even though right here。

 I had an environment where A maps to5 and B maps to 20， now I have an environment where a maps to5。

 B maps to 20 and C maps to 20， because we know that the way you evaluate this expression， B。

 is you look it up in the dynamic environment， you get 20。

 then you extend the dynamic environment so that now C maps to that result。Al right。

 so the fact that B was earlier created by evaluating a times 2 is no longer relevant that was back in an environment where a map to 10 we got 20。

 we extended our environment so that indeed a map to 10 and B map to 20。

 and that's the end of the story， the fact that we had a times 2 is no longer relevant。

 and I should emphasize as well that this value equal 5， this is not an assignment statement。Okay。

There is absolutely no way an M to mutate or change the fact that a map to 10 in the previous environment。

 All we get is in the subsequent environment。 A is now shadowed。

 We have a different mapping for a in a different environment， and a is now 5。So that's the idea。

 Let's just do a little more example to make sure we got it。 If I now say Val D equals a。

 I'm going to end up with an environment with all the things I did have and now D maps to 5 because a maps to5 in this environment where I am if I now say what about Val a equals a plus1 again。

 there's no such thing as an assignment and this makes perfect sense。

 the way of variable binding works is we evaluate the expression in the current dynamic environment So a maps to5 we add one to that we get6 and then we create a new dynamic environment where a maps to6 along with everything else we had previously。

 but we're now shadowing the fact that a map to5 and an earlier environment or a map to 10 and an even earlier environment。

So indeed， if we now say v equals a times 2， F will map to 12。

I should emphasize as well that something you cannot do is a forward reference and we know why for the same reason。

 so if I had this code here， it would not type check and the reason why is when I have to go to T check this expression F minus3 F is not yet in the environment so when I look it up in the static environment it's not there and I would get a type error message so that's the example I wanted to show let's real quick try it out。

 make sure I typed in everything correctly。啊。Semicon。Let's。There we go。 We'll try this again。

 Notice I didn't panic when I got an error message。 There we go。 And we see all the values I saw。

 But for those earlier A's， the readtaval print loop is trying to be helpful and just saying。

 you know， this value can't possibly be relevant to you。

 I know it's shadowed in the dynamic environment you now have down here where a is bound to 6。

 So rather than show you what a was back up in this earlier environment。

 I'll just print hidden value。

![](img/b2d36fa9eff7f27e03c092daf05b6683_4.png)

Allright， so that is the code example， let's go back to the slides here and show you again that in the key example here。

 when you have something like v equal a equals1， B equals a A equals 2 that in the environment you end up with B is bound to1 and a is bound to2。

 there's actually two reasons for this， either one of which would be enough。

The first reason is that we evaluated that expression we used for B。

 that expression A on the right hand side of the equals eagerly back when we evaluated the variable binding for B。

 so after we've done that expression evaluation。😡，B is bound to one。

 And it doesn't matter how we got that one。 It'll never affect the fact that we got a one。

 and that's the end of the story。The second reason B will stay bound to one is that that second value equal2 is not an assignment statement。

 The earlier A， the A that leads to the environment that is used to evaluate B is still one。

 All we did was create a second variable B that shadows it。

So it turns out this is the reason I'm so insistent on not having use commands in your Reple more than once for the same file because if you say use multiple times for the same file。

 you're going to repeat whatever bindings were there。

 the first time you said use for the file and are still there the second time you said use for the file and while it's legal and ML to have that sort of shadowing and to reintroduce those bindings。

 it can be really confusing maybe you took a binding out but it's still there because of the previous use or maybe you have some strange shadowing that makes it look like your code is correct when in fact it's wrong because of how the shadowing happen to work for the multiple use statements。

😡。

![](img/b2d36fa9eff7f27e03c092daf05b6683_6.png)