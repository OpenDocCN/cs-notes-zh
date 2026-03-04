# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p106 8_06_dynamic-typing -BV1bw4m1D7MM_p106-

In this segment， I want to have our first discussion about how Racet is a dynamically typed language and emphasize how it lets us build up our own data structures without any type system or type checker getting in our way。



![](img/46f00bf95cf48dbae51921f195f04abd_1.png)

![](img/46f00bf95cf48dbae51921f195f04abd_2.png)

So this is a major topic that we'll discuss later after we're more familiar with them dynamic typing。

 I want to contrast it with static typing and discuss the advantages and disadvantages of each。

 but for right now we just to get used to the idea that racket doesn't detect a lot of things as type errors and understand what that lets us do。

Now， you may get frustrated by the lack of a type checker as much as you don't like type error messages。

 they're often better than not getting them。 So if you made it a mistake in your racket code。

 like write something like n times X instead of times N X。

 racket will let you run that code without any problem。

 And if you don't execute that particular expression， you'll never see that it's an error。

 So it's only if you have a test case that actually gets there， looks up n in the environment。

 presumably does not find a function expecting two arguments。

 the first of which is times that you will get an error message。

 so it makes testing for this sort of error actually more important。

But the advantage is it lets us build very flexible data structures without having to go through a bunch of work to tell the type checker what we're trying to do。

So the example we're going to do in this segment is we're going to end up writing a sum function that sums up all the numbers in a list。

 but it's not just a list of numbers。 Our list can either have numbers or other lists of numbers or inside those lists more lists that have more lists or numbers。

 And so what the idea is to allow arbitrary nesting of lists and numbers as deep as we want and still sum up all the numbers that appear anywhere in any of those lists。

 So you can't do this in Ml without creating a data type binding and constructors in order to put numbers and lists in the same list you can't do that according to the type checker。

 that's why you have to use a data type binding。 but in racket there is no type checker。

 So we'll just be able to do this。 So let's just go over here and explain what I'm talking about。

 So let me first define a couple example list。 So you know the sort of thing I'm doing。

 So my first list。

![](img/46f00bf95cf48dbae51921f195f04abd_4.png)

X is， I can just have a normal list of numbers，4，5，6， but I could also have a list would say。

 had another list in it with 4 and 5 and then had6 and 7。 and then I had a list 8。

 and then maybe 9 and 2 and 3。 and then list 0 and  one。

So what I've just defined and bound to Y is a list with a bunch of elements。 Here's the first one。

Second one is 6，37。 Fourth is the list 8。Then a 9 a two and a3。

 and then this list with two more elements。 And this list has a4 and a 5， and this list has a 0 a1。

 but I could nest more deeply。 Maybe here I have a list of a 5 and another 0。

 And so I can nest these things as deep as I want。 And it's still going to be the sort of thing I want my function to work properly on。

So now let's actually define it， I'm going to define two versions in this segment so we'll start with sum1 and I'll call the other one sum2 and I forgot a parenthesis here and I want to take in list let's call it x's this is just shadowing this is just a function parameter it's not the list Xs I defined above and what I want to do is if this argument x's is null then0 the sum of the empty list is zero just like we're familiar with otherwise I can't just go and add the car of x's because the car might hold another list so I better not just do that I better check whether it's a list or a number I can do that with this number function for all the built-in types and racket they all come with these functions that test at runtime do you have one of these things and a statically type language you wouldn't need this the type checker would tell you what type of thing you have where but in racket we can pass anything anywhere。



![](img/46f00bf95cf48dbae51921f195f04abd_6.png)

These functions are very useful。So if that evaluates to true， then we definitely have a number。

 So let's go ahead and add the car of x's to recursively suming the cutter of x's。

 So add those two things together。 And that's a good true branch for our conditional otherwise。

We'll assume that if it's not a number， it must be a list because the sort of thing someone is supposed to work on is this combination of lists and numbers that go arbitrarily deep。

 So let's do some car of X is So that is going to sum up everything in the car。

 The car is itself a list。 So recursively sum all of those。

 And then let's recursively sum the cutter。Of x's， Add those two things together。

 That's a good false branch that takes care of the false branch if we don't have the empty list。

 and that takes care of our definition。So let's try this out。You can see the sum function up there。

 and we can try sum1 on x's。And it works fine。 We get 15。 We can try someone on wise， and we get 45。

 And I'll hope that that's correct。 that that sums up all the numbers we have up in that long list。

 And let's try one more。 Let's try list of list of list of 4。😊。

And then a five and list of a seven and a two。And that works fine， we get 18， which looks right。

 but what won't work is if maybe deep inside one of these lists。

 we have something that's not a number or a list。Then we'll get an error because eventually we will recur to that position。

 and our function assumed that we would never hit a string。So something wasn't a number。

 so we tried to treat it as a list， we tried to take the car of a string。

 and if you take a car of high， that does not make any sense and you get a runtime error。



![](img/46f00bf95cf48dbae51921f195f04abd_8.png)

OkayOkay， so this is fine。 someone misused our function。

 When you misuse a function in a dynamically typed language， you often get these sort of errors。

 But if we wanted to support this， we could write a second version that if you hit something in a list that is not a number and not a nested list。

 let's just skip it。 you know， treat it as0， right， Just skip over it in our summing。

 Now there's probably a number of ways to do this， I'm going to show you one that is you know。

 as much like our first version as possible。 So if I have the empty list 0 as a good answer。

 And if I have a number in the car of the list， then I definitely want to add that number to recursively summing everything in the cutter。

😊。

![](img/46f00bf95cf48dbae51921f195f04abd_10.png)

![](img/46f00bf95cf48dbae51921f195f04abd_11.png)

But now let's not assume I have a list。😡，Alright，This is a matter of style， whether， you know。

 it's up to you to force callers to do the right thing， and there'll be an error otherwise。

 Or if you want to say， allright， well， if it's a list， then I'll do what I did before。

 some two car X's and sum two of cutter X's， right， So I have a list in the first position。

 So recursively add all that。 The cutter is always another list。 And so add all that。

 and then add the two together。

![](img/46f00bf95cf48dbae51921f195f04abd_13.png)

Otherwise。I don't want to touch the thing in the car because it might be something like a string。

 so let's just sum the elements in the cutter of the list。Okay。

 so that's the case we didn't have before。 We were assuming we had a list down here。

 and now we're explicitly checking。 I can run this。 if you just do alt P and Dr racket。

 you get your previous commands， you can cycle through those。

 And now this was the thing that gave us an error before。

 But now if instead of calling some 1 I just go back here and edit it to be sum 2。

 then I get the right answer。 All right， that 14， it skipped over it。

 And if this 5 where instead something like-3， or sorry， I want something that's not a number。

 or a list how about false。 Okay， then it'll just nicely skip it and I'll get 13。Now。

 sum too doesn't work for just anything。 It still assumes the initial argument is a list。

 If I tried to call it with high， I would still get a error message。

 and that's because right here I start checking the car before I even know it has a list。

 and that's a third version。 if you really wanted it to work for anything。

 and maybe for something else like this， return0。 then I'll leave that as an exercise for you。

 But what we've seen here is that we could do correct versions of some that worked for lists of numbers and numbers of lists without having to create M style data type bindings。

 There's no type declaration at all。 We can just flipping back here to the file define X's and y's to be list holding anything we want。

 In fact， you can hold have a single list， hold the。

False and high and 14 and racket has no problem with this whatsoever， we can run this。

 we can ask for the car of Z's， we get false， we can ask for the cutter of Zs。

 we get the list holding high in 14 and so on， and so this is more convenient for us。

 but of course it also makes it a little harder to test our functions and to document what type of argument they expect。



![](img/46f00bf95cf48dbae51921f195f04abd_15.png)