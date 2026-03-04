# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p115 17_15_delay-and-force -BV1bw4m1D7MM_p115-

So now I want to continue our discussion of avoiding unnecessary computations by showing how we can use this idea of delay and force to get lazy evaluation implemented ourselves。

 so we're trying to get this best of both worlds where we have some expensive computation。

 we don't want to compute it unless we need it， but if we need it more than once。

 we want to store the previous answer so that we can use it again。



![](img/b789f0704e1cd4ef413a8d15fb067cdb_1.png)

![](img/b789f0704e1cd4ef413a8d15fb067cdb_2.png)

So here in one slide is how we could do this。We're just going to use a technique of a little bit of mutation to get what we want。

So we're going to define two functions called my delay in my force so that we don't conflict with the notion of force and delay provided by the standard Library of rackcet。

 And here's how they work。 If you want to delay a computation， call my delay with a thk。

Because it's a thk。 Whatever body is in there， Fortunatelyly， has not been evaluated yet。

 And then let's return a mutable pair of false and the thk。 So we never called the thk。

 There's no parentheses around this T。 So that's going to happen very fast。

 And we're just going to return that pair。 So we haven't done any expensive computations yet。

Then when you want to use the thunk， when you need the result， you weren't able to avoid it。

 you're going to have to do it。 then you call my force on the thing return for my delay。

 and we'll call that thing a promise。 Racet calls them the same thing。 This says。

 I promise if you need this thing。 You can force me to give it to you and I will。

 You just do that by calling my force。😡，Here's what my force does。If the car of the promise is true。

Then just return the cutter of the promise。Now that's not going to be true the first time you call my force with a promise because you can see right here。

 the first thing is false。 So all the action is here in the false branch。

 We use this begin construct that does a sequence of things and the result is the last one。

 So here's what we do in the false branch。 We do three things。First。

 we change the car of the promise to be true， indicating that we have now evaluated this thunk。

 we're never going to evaluate it more than once。Then we're going to change the cutter of the promise so that it does not hold what it used to hold。

 Instead， it holds the result of calling the thunk。

So let's look at these parentheses when you call M coter of P that gets out the thunk。

The next set of parentheses， calls the thk。Then we take that result and we put it。

In the cutter of the promise， we don't store the thk anymore because we don't need it anymore。

 We just have the result of the call。 So after we've done that， when we look up M cutter of P。

 we have the result of calling the thk， and we return it。😡。

If anyone ever calls my force on this promise again？The M car will be true。

 We won't evaluate the thunk。 We won't have the thk anymore。 We'll just return the M cutter。

So all that's really going on here is this is a little one of type where the car is true or false indicating whether or not you have to evaluate the thk or the thk is gone and you have the result in its place。

AndIally， this would be a little abstract data type that you would hide in a module。

 but I haven't shown you Ra's module system， so we'll avoid that and I'll just show you these functions as they are here。

So this is the implementation of force and delay， how would you use it？Well。

 the simplest thing to do is if you had some function somewhere that maybe needed some computation。

 maybe needed it multiple times， maybe didn't need it at all。

 is you would just call F not with a funk， but with this pair that my delay returns。

And then anywhere you needed the computation， you would write my force。😡，And by writing my force。

 that would either evaluate the thk that happens the first time or just look up the answer that you used mutation to store。

 That's what you do every other time。

![](img/b789f0704e1cd4ef413a8d15fb067cdb_4.png)

So now let's go back to the example that we had in the previous segment where I had this multiplicationcation that took in a thunk where I was passing in very slow ths。

 and I don't need to evaluate the thk for zero， I do for one and if it's greater than one。

 then I need to multiple times and now I'm going to do a little trick。

 here's the implementation of delay in force， I showed you on the slides it's exactly the same。

And now I can use these to call my malt in a better way in a way that even if I didn't know what the first number was。

 I would never have to evaluate the thunk more than once。 So that's the idea。 Okay。

 so here's what I want to do。 I'm going to just run this and do this in the repple for you。😡，Okay。

 so first， suppose we don't know what the number is。

 I'm going have to replace this because I don't have an X。

 Okay but what I want to do is I'm going to create a little let here to create。This delayed thing。

Okay， so this delayed thing。This promise。All right， is now held in this value x。Alright。

 and now what I need to pass into my malt， It doesn't expect a promise。

 I wrote it in the previous segment when we didn't have promises， it expects a thunk。

 So I'll just pass in a thk that when you call it forces X。In fact， instead of calling it X。

 how about I call it P to emphasize that that is a promise。

 so I create a promise that when you force it we'll add3 and4。

 which remembers this very slow operation。 And now I'm going to pass into malt a thunk that says。

 if you call this thunk， okay， I'm going to force P and then whatever that result is， I will return。

 But notice if you call this thunk more than once。 It's going to force the P more than once。

 the P will therefore the force will therefore return very quickly and will be fine。

 so that's the idea。 it just you know don't have an X， we need to try this for different numbers。



![](img/b789f0704e1cd4ef413a8d15fb067cdb_6.png)

So it turns out that if you try to multiply by0， this is very fast。

 but it's not due to any of our finess。 This is because we never evaluate the funk and we never evaluate this slow ad。

 And so， you know， everything's very fast。If we do this one time， if we multiply by one。

 then we are going to end up forcing this promise one time。And it takes a second。

 and then we get seven。But if we multiply 107。Thanks to our lazy evaluation。

 the fact that after the first time we forced the promise。

 we updated the promise to have the answer 7。 So it's just sitting there。

 The next time we call my force。 it just says， oh， the car is true。 I'll return。 the cutter。

 The cutter is 7。 and we get the result immediately。 So we didn't have to slow add 3 and 4100 times。

 we had to slow at it one time。😊，So let's review the example。

 I know I split it across two segments in the interest of time。

 but we basically called myMt three different ways。

The first time we just passed in the normal thunk for the second argument， delaying evaluation。

 and that delayed evaluation was great when we were multiplying by zero。

 It was fine when we were multiplying by one， we delayed something we were going to have to do。

 and then we did it。😊，For greater than one， it was terrible because we ended up slow adding three and four multiple times。

 even though it would have been better to not use sts at all and just do it once。

The second version I showed you， this was also in the previous segment。I pre compute it。

 I passed in a thunk that just looked up a variable that already had the answer to 3 plus 4。

Now that precomputation was something I paid once regardless of the other argument， so that's okay。

 I only did it once， but I didn't get the great thing when I was multiplying by zero this was just the normal well let's evaluate everything once and that's as best as I can do and that's okay。

Now with promises， I'm getting the best of these two worlds。😡，That when the first argument was zero。

 I never forced the promise， so I never did the slow ad。If it was one， I did do the slow ad。

 that's basically as good as I did in the first version， but then thanks to how promises work。

 I stored the result。Okay， so if it was going to be called again， I would have it。 And in fact。

 that is what happened when I multiplied by 100。 the first time I did slow a and the other 99 times I just looked up the answer that was stored in the promise。

 So that's our example of how we can use mutation and thking to get this idea of lazy evaluation。

 which can be the best of both worlds in terms of delaying computations you might not need。

 but making sure you do not do them more than once。



![](img/b789f0704e1cd4ef413a8d15fb067cdb_8.png)