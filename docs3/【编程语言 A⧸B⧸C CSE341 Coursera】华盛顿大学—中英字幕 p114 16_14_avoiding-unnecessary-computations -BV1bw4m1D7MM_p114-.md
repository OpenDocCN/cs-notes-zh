# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p114 16_14_avoiding-unnecessary-computations -BV1bw4m1D7MM_p114-

So let's now continue our study of using ths to delay computations we might not need。

 see how that's a good idea how that is a less good idea。



![](img/43d92ffd3e1754fa5dbe303ab3d1b691_1.png)

So thhunks lets you skip an expensive computation if you're not going to need it。

 So this is great in the sort of first code skeleton you see here。

 If I have some function that takes in a thunk。And I have some if that ends up taking the true branch。

 the branch that doesn't use the thunk。 This is much better than passing in the result of some expensive computation。

If I didn't use a thk here and I had to pass in the result of the expensive computation。

 I would have done a lot of unnecessary work。So that's fine and in those situations using ths straightforward。

 but what if you're more in this situation like here at the bottom where I have a bunch of separate conditionals？

I don't know if any of them are going to evaluate to true or evaluate to false。

 I don't know how many， but they do all need if they're false。 in this case。

 doesn't matter whether they're true or false。 They do all need the same result。

 So should I precompute the result of the expensive computation for all of them。

 That would be wasteful if none of them need it。But if multiple of them need it。

 this situation with the thk is actually worse because I'm going to reevaluate the thk every time one of these ifs ends up being false。

 So that's the tradeoff。 We're going end up getting the best of both worlds in a few minutes。

 But first， I want to show you an actual example。 It's a silly example。

 but it's actual code instead of something where I've left out all the interesting parts。

 So just to make this interesting。 This first function is ridiculous。 It adds its arguments。

 But I've put in enough extra code that it takes a long time to evaluate。

 So if I do something like slow ad 3，4， you see it actually takes a second before it produces 7。

 that way we can actually see the difference in in the example I'm about to show you。



![](img/43d92ffd3e1754fa5dbe303ab3d1b691_3.png)

Then I have this function that does multiplication， but in sort of a strange way。

It takes in a number X， and it takes in a thk Y that when you call it returns a number。

And here's how it then multiplies x and the result of calling Y。 If x is0。

 it returns zero without ever executing the thk because that's how multiplication works。

 We don't care what the funk is。If x is1， then we evaluate the thk， and that's our answer。Otherwise。

 we evaluate the thunk and we recursively call my malt with x minus1 and not the result of calling the thunk。

 but with the thk itself， because that is what my malt expects。

 it expects a thk for its second argument。So if you look at this。

 this is going to end up calling Y fununk。Once。Every time for x。 So if， if x is 7。

 it's going to call the thk 7 times。 So indeed， therefore。

 even though something like slow out of 3 and 4 is very slow， right。

 If I call my malt with 0 and a thunk。

![](img/43d92ffd3e1754fa5dbe303ab3d1b691_5.png)

Of slow add3 and4。That's very fast。 Want to see it again。Very fast。

But if I were instead multiplying by one。Well， this is sort of unavoidable。 I need to add three and4。

 but that's okay。 I mean， what else am I going to do， but if I called it with two。

 it's actually going to take twice as long because it's calling that thunk twice。



![](img/43d92ffd3e1754fa5dbe303ab3d1b691_7.png)

And I don't even want to sit here while I did something like multiply by 20。

So thing was great in the zero case。 It was fine in the one case。 We did have to add 3 and 4。

 but it was terrible for anything greater than one。

 because it was actually a net loss compared to the version of multiplication that just took in X and a Y。

 and therefore， the caller would have precomputd the two numbers and therefore would have already done slow add。

 In fact， let me show you that version as well。 I can actually do it with my malt。

 So suppose I passed in0。😊，But then for the second argument， I precompd SAdd。Put that in a let。😡。

And then in my lambda， just looked up x。so all I'm doing is my second argument to mymt。

 which is evaluated right away。 It evaluates x to slow add of3 and 4 and then creates a thk that when you call it。

 we'll look up x。 So this is going to call slow add 3 and 4 once before you ever call mymt。

 So now if you call it was0， it does just take a little bit because we did call slow add。

 but2 doesn't take any longer。And in fact， 20 doesn't take any longer。

 They all take about the same amount of time。So that's all fine， but I gave up zero being fast。

 it's not fast anymore。So that's sort of our motivation。

So what if we could get the best of both worlds？😡，What if we could take some computation？

They'd always returned the same result， had no side effects。 didnn't matter when it was executed。

 And we did not compute it until we needed it。But then once we did need it， we remembered the answer。

 so in the future we didn't have to compute it again。

 We would just return that remembered result immediately。Well。

 this has a name it's called lazy evaluation。And languages where most constructs work this way。

 where， in fact， all function arguments work this way are called lazy languages。

 and Haskell is the most well known， successful example around today。

But what I'm going to do in the next segment in racket is show you how we could just code this up。

Now， rackcet does not work this way for function arguments。

 Fun arguments are all evaluated at the call site。 We do not have lazy evaluation in racket just like we didn't in ML。

 but we will be able to code it up just ourselves。 Raet does have some built in support that is very slightly different syntactically in what it's doing I'd rather show you the implementation so we will use our own and then we will come back and revisit this multiplication example。

 So in our implementation， all we're going to need are thunks and mutable pairs， M cons。

 two things we've seen from previous segments。 So we're going to be able to put together some previous ideas and get this best of both worlds。



![](img/43d92ffd3e1754fa5dbe303ab3d1b691_9.png)