# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p110 12_10_mutation-with-set -BV1bw4m1D7MM_p110-

In this segment， I'm going to admit to you that Racet actually has mutation。

 in fact it has assignment statements， because we need them for some of the idioms we will be studying later in this section。

 but in this segment I'm going to show you how they work and some of the problems they cause because if you use mutation in places you should not。

 bad things happen to your software。

![](img/b1dc13266de5eaebe0791ee2da576345_1.png)

So racket really does have assignment statements and we use them only where appropriate people generally programming and racket do not use them a lot。

 but when they need them， the racket construct is called set B。

 It's spelled SET exclamation point and everyone pronounces it set Bang。

And the way it works is set B takes a variable that should already be in the environment and an expression E。

 it evaluates E to a result， and it updates， it actually mutates what x is bound to。

 so anyone who's using that X in their environment after this set B will see the updated value for x。

Al right， so any later lookup for x by anyone who's using that x， they'll see the later value。

 if they already looked up X， well， they saw the value before we did the set bang。

 and this really is like the assignment statement in languages you may have seen before Java C。

 Python and so forth， the syntax is just set bang with parentheses around it。

Now once you have side effects like this， sometimes you want to do a bunch of things in order。

 I'm not going to use this in this segment， but I should show you that rackcet in general has this form where you say begin and then some sequence of expressions。

 and this is the sequencing operator， you do each of these expressions in order and your overall result is just whatever the last one evaluates to。

 so these earlier ones are useless except if they do any set banging。

 they do any updating or any printing or anything with a side effect then we need to execute those just for their side effect。



![](img/b1dc13266de5eaebe0791ee2da576345_3.png)

So let me show you an example using setBang that's actually mutating a variable。

 so imagine this is a file， and I want to sort of emphasize to you why this sort of assignment statement is probably a bad idea。

So let's go through this line by line。 On the first line。

 we create the environment where B is bound to3。Now in the second line。

 F is bound to a function that if this were M L， I would say F always， always。

 always adds3 to its argument， because given x， it does multiply by one and the addition of X and B。

 Allright， So I made this big point that Ml thanks to closures。

 this function will always add 3 to its argument。Now， what I have to say is， in fact。

 we still have closures， and this function will always， when it looks up B， get this B。

 we still have lexical scope。 But when it looks up B。

 it will get whatever the current contents of B R， because with set B。

 we have to start talking about current contents。 If you don't use set bang， you can forget that。

 The initial contents or the contents for all time。Okay， line 3。

 when we look up B for this expression， B is3， so we get7。 so in the environment， C is 7。Period。

 I have it here in the comment。 C is 7。At this point， we set B B to 5。 so henceforth。

B in this environment is5。So now when we call F with4。When the body of this function is executed。

 it looks up be in the environment and it sees five。So we end up with 5 plus 4。

 That's the plus Xb multiplied by one。 We get 9。On this last line， however。

 where we just look up C and put the result in W。C is seven。

We already did this plus before a long time ago， three lines ago。

And what's in our environment is C is7， having done that edition。

 any subsequent changes to B are not relevant。So that is why Z is bound to 9。

 because the call to F saw the new value for B。 but W is bound to 7 because C。

What holdsolds the result of adding B and4 where we looked up B before the set bank。



![](img/b1dc13266de5eaebe0791ee2da576345_5.png)

Okay。So when you can set B， when you can assign to top level bindings。

 a lot of things can start going really wrong。So suppose that we thought that function F really was supposed to always add three to its argument。

 how could we fix that？Well， no one programs this way in racket， do not do this on your homework。

 but I want to make a point about how if you had to deal with the potential of set bank correctly。

 you'd have to do a lot of extra copying of bindings。

So a general principle in software development is if you're worried something might change。

 make a copy of it before it can change， and we can do that with our example function F if we wanted F to always add X to the value of B when F was defined rather than the updated value of B。

 when F is called， then what we can do is we can make a local copy。😡。

We can define F to be the result of this let expression。

And what this lead expression does is it initializes some local Be that the outside world cannot get to and therefore cannot set bang。

To be whatever the outer B currently is。 So we have that3。 And now this function， whenever called。

We'll look up B， find this local B。 We already copied the outer one， and we're fine。

So you normally use the same variable when you use this technique， but if it confuses you。

 this inner B does not have to be the same as the outer B。

 we could have said let C be B lambda x times 1 plus x and C。

 and that would have still made an appropriate local copy that would make sure that this closure is unaffected by any later set bang of this top level B。

But it turns out that wouldn't necessarily be good enough。



![](img/b1dc13266de5eaebe0791ee2da576345_7.png)

In a simple， elegant language design， we wouldd say， wait a minute。

That function also uses addition and multiplication。 And those are just variables bound to functions。

 And if we have setb， we have setb， what would stop someone from set banging the plus variable to be bound to some different thing。

 no longer the addition function。 So now for our function F to be safe。

 we'd have to make a local copy of B and a local copy of plus and a local copy of times so that we know that this function body down here when it looks up times and plus and B will get the code we want even if there's a later set bank。

😊，Nobody programs like this， don't worry about it， but semantically this is what you would think you would have to do and in older racketlike languages like scheme。

 this would actually be a problem if someone did a set bang of plus all sorts of code would start breaking because they all assumed it was still the addition function。

So the designers of Racet decided this was just too much。

 we don't want to have to have these sort of problems creeping into our software。

 so in racket you cannot set bank things like plus they made kind of a strange compromise that if the code if the file that defines something。

 does not set bang it in that file， then nobody else can either and since the file where plus is bound to the addition function does not have any set bankss for addition。

 we don't have to worry about anyone else assigning to it either。



![](img/b1dc13266de5eaebe0791ee2da576345_9.png)

Okay， let me be clear about this。 I do not want you on the homework making local copies like this。

 It's a strange idiom。 It's not necessary。 What everyone does in racket is just assume that no one's going to do set bang of top level bindings。

 So why did I show this to you。 Because I don't want you to use set bang on top levelvel bindings in any language。

 assigning to top levelve things that lots of your code might be relying on is just a bad idea。

 And if you don't mutate things， then you have a much simpler semantics。

 and it's actually quite dubious whether in your language。

 you should even allow tople bindings to be mutated， And that's why we have set bang。

 but racket went ahead and had some reasonable compromises about what you're allowed to set bang and what you're not。



![](img/b1dc13266de5eaebe0791ee2da576345_11.png)