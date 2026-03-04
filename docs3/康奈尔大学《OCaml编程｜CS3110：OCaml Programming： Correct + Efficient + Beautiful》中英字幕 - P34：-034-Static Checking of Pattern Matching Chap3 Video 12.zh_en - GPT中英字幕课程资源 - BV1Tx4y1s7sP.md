# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P34：-034-Static Checking of Pattern Matching Chap3 Video 12.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've talked about static semantics a lot already。One of the things I mentioned upfront was that statictic semantics generally involves type checking。

But there can be more to static semantics than just type checking。And with pattern matching。

 Ocamel does a bit more than just type checking。Let me show you some interesting examples。

Here's a piece of code that is supposed to determine whether a list is empty。 I've called it bad。

 empty。And indeed， Ocamel is going to give me a warning That little curly underline there。

 I hover over that and it says warning this pattern matching is not exhaustive。

 Here is an example of a case that is not matched。 Underco cons， underscore。The Merlin， after that。

 of course， is just to referringring to the fact that Merlin is the I D E plugin that helped Ocamll show this to me。

So there's a case for the expression being matched， which is LST list。That I haven't covered。

My coverage of the space of possible shapes that this data could take is not exhaustive。

Or to put it more simply， I've left out a branch。Right， match list with empty returned true。

 But I forgot to put in the branch for false。Why is that problematic？I have buggy code here。

This code is， in fact， going to raise an exception， if I'm not careful。

Let's look at that happen in a terminal。Let's use that matching code。

You can see the warning occur there again， but I'm going to proceed。

 throw caution to the wind and ignore that warning and try using this code。

What is bad empty on the empty list？True， it is empty， but what's bad empty on a list containing one？

I get an exception， a match failure exception。We don't want exceptions at runtime。

 They cause our code to die， and then our clients are not happy with us。

So we need to pay attention to the warning that the compiler is giving us there and fix it。Here。

 I should realize， oh， yes。 I meant if it's any other list that I should return false。

 And now I have a good implementation of that function。 Let's look at the next example。

Here I'm trying to sum up the elements of the list， but I've gotten it wrong once more。

Oca will give me a warning with the pattern match。This match case is unused。

What Ocamo means by that is it's been able to figure out that that particular case is never。

 ever going to get matched against no matter what the value of the expression being matched。

 LST happens to be。Okay， so why is that never going to get used here？Let's take a closer look。

If the list is non empty， so there's a head cons a tail。

 we're going to go ahead and add the head into the sum of the rest of the list。

 That seems good so far。 If the list just has a single element。

 then the sum of the single element list is X， That seems right。 If the list is empty。

 the sum of it should be 0， Like that all seems right， too， Why is this case unused。

 Why is it somehow redundant。Well， remember that the square bracket notation for list is really just syntactic sugar。

 I could have written that as X cons nil， in fact， as a pattern， still redundant。 In fact。

 that match case is unused。 But now maybe it's a little clearer why it's redundant。

Think about what's going to happen up here in the first case。

That pattern will match any list that has a head element， as well as a tail。

 It doesn't matter how many elements are in the tail。 It could be 10。 It could be  one。

 It could be 0。And that's exactly what the second branch is considering。

A list that has a head element。No't matter what we call it， whether it's x or H。And then empty tail。

So when you try to match the list that just has a single element in it。

 the first branch is always going to be triggered there。

 we're always going to match against it and recurse with bad sum。Now， in this case。

 that doesn't mean the code is especially buggy。If we look at it in U。What's the bad sum of the list。

 the empty list at zero， what's the bad sum of the list， one， two， three？At six。

 the code's still producing the right results。But it's not great code in the sense that there is some code here that is。

Never going to be used。 It shouldn't be in our code base。 There's no need to have it there。

 or to maintain it。Often， that means we haven't considered something carefully enough and need to rethink our code in this case。

We could just get rid of it entirely and simplify the function by deleting the whole line。

As a third example， let's look at some code that doesn't even have pattern matching in it。

Here's another implementation of some。Let's try running it。We have bad sub primeme。

If I try to sum up a list containing 1， two，3。I get a failure， an exception。What's going on here？

The implementation of this version of some uses two library functions。

It's from the List standard library and they're called HD and TL。

 which as you might guess stand for head and tail， they're meant to give us the head and tail of a list。

So you could take the head of a list  one， two， three and you get one out。

You could take the tail of a list 1，2，3。And you'd get two， three， the tail。Now。

 what are those functions going to do when they're applied to the empty list。

 There is nothing you can return for the empty list to get its head。

 There is nothing you can return for the empty list to get its tail， either。

So the standard library raises an exception called failure in the case of both of those。

 we're going to study exceptions in more detail next week。

But the implementation here of bad sum Prime is using head and tail。 instead of pattern matching。

 It's saying take the head of that list and add it together with the recursive call on the tail of the list。

Now， in essence， that's what Bad sum is doing here。

 it's trying to add in the head of the list together with the recursal call on the tail。

But by doing it without pattern matching， by doing it with head and tail。

Whoever wrote this code actually missed a possibility for what the list could be。

They forgot that it might be empty。Which is sort of the opposite of the first example we had up here where the programmer forgot that the list might be non empty。

So this is the danger of using head and tail。😡，They can cause an exception to be raised on an empty list。

And that's why it's better。As a matter of practice to use pattern matching to access the elements of the list。

 than to use the head in the tail function。Now， that static checking that O Caml gives us through pattern matching is therefore an advantage because it helps prevent buggy code。

Once in a while there may be cases where you want to use the head or the tail function from the standard library。

 this is not one of them。

![](img/69c8fb6452ace38d41db91b3bf16a25f_1.png)

So this is one of the brilliant things about OAl and about pattern matching is that the compiler checks for your errors。

Statatic semantics recall is more than just type checking。

 and the Oaml compiler here is checking for exhaustiveness of patterns as well as unused branches。

So please， please， please do not ignore these warnings。

 The compiler is finding your heirs for you and giving you a chance to fix them。

 Take advantage of that。

![](img/69c8fb6452ace38d41db91b3bf16a25f_3.png)