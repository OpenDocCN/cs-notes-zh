# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p85 84_07_mutual-recursion -BV1bw4m1D7MM_p85-

This segment is about mutual recursion， it's a small topic that we just didn't need before。

 but it would be a mistake to move on from ML without discussing it。

Mutual recursion is just when you have two or more functions that need to call each other。

 So what if you wanted to have F called G sometimes and G call F sometimes Now is this useful。 Yes。

 it's useful in a number of idioms and patterns that come up and we'll show a particular example in this segment where we're going to implement a little state machine。

 but there's a problem。 And that problem is that we've seen in M that you have to introduce bindings in order that the only functions in your environment are things that were defined earlier in the environment and yourself for recursion。

 So how are we going to get F to call G and G to call F。 Well I'll show you two ways。

 The first way is M does have special support for this and you should use that special support because it's good style when you want mutual recursion。

 And second I'll point out that we don't actually need the special support。

 there is a work around with higher order functions and it's just another example of using high order functions to accomplish something useful。

So here is the built in support I just never showed you before。

 it turns out that if you have a bunch of function bindings in a row，And if for after the first one。

 use the word and instead of fun， so it's fun F1 in F1's definition and F2 definition and F3。

 and you can have as many of those as you want， then this is all in some sense。

 one bundle of mutually recursive functions， they are all allowed to call each other。

 they are all added to the environment for all of the others。

 and they're type checkedcked and evaluated as one package， if you will。

So that is all we really need to have F called G and G call F。

 we just have to put them next to each other in our file and use the keyword and。Now interestingly。

 we can also do this for data type bindings， this is really a separate construct。

 but suppose you wanted introduce two types that referred to each other。

 so one of the constructors of T1 holds a T2 and one of the constructors of T2 holds a T1。

 we also have not been able to do that before and it's the same idea where we replace the keyword data type with the keyword ant。

Okay， so that's the kind of it for the language construct。 Now let's see this thing useful。

The idiom I want to show you for using mutually recursive functions。

 Its just one of several things mutual recursion is useful for is implementing a little state machine Now in case you've never seen a finite state machine。

 it's a very important concept in computer science。 I encourage you to learn about it。

 but the idea is that we want to process some input of unknown length。

 So some list of input that can have any size and as we process it we're always in one of a finite number of known states and we read the next level of the input and that tells us what state to go to next。

 and then when we're all done with the input， certain states are true， yes。

 we accept and certain states are false。 No we reject。

 That's the idea of a finite state machine that come up all the time in computing。

So the way we can implement a finite state machine with mutually recursive functions is we just have one function for each state。

 so we could call those states， state 1， state 2 and so on。

 it depends what kind of state machine we're implementing。

 they would all take the remaining input they would all look at the first element of that input。

 and then they would just call whatever function represents the next state。

So let me show an example of that since I don't expect you got it from the slide。

 here is a function match that takes in in this case an int list。

 and what it does is it only accepts list of ants that look like one， two， one， two。

 some number of times。

![](img/ab179b3cef4735f15bfa1aaec5507b6b_1.png)

![](img/ab179b3cef4735f15bfa1aaec5507b6b_2.png)

So the empty list would actually pass because it has one two zero times。

 but if it's anything other than a one or a two， it's going to reject and otherwise it's going to be 1。

 two， one， two， one， two， and it has to end with a two。



![](img/ab179b3cef4735f15bfa1aaec5507b6b_4.png)

So all I'm going to do inside my body of match is call this helper function I defined S need one on the whole list。

 these are my two states need one is the state that says I better have a one next if I have anything and S need two is I better have a two next if I have anything So here's how it works S need one looks at that list if there's nothing left。



![](img/ab179b3cef4735f15bfa1aaec5507b6b_6.png)

Then I'm before when I need a one。 So that's true。 I saw a two last。

 or I started with the empty list。Otherwise， if I have a one first。

 and I don't think I ever showed you， you can put integer constants in patterns。

 but that really is an orthogonal issue， not particularly relevant here。

 then what I want to do is switch to state 2 with the rest of my list。

Now in general for finite state machines， I could have other possibilities where I go to other states。

 but this' is a particularly simple example where I just have two states I go back and forth between。

 in any other case I'm going to immediately reject and return false。

S need2 takes in the input list if there's nothing more。

 it says false because whenever I call S need2， I need another two because I just saw one。

If I have a two at the beginning of my list， then call S need one with the rest of the list and so on。

 we go back and forth if I see anything other than a two。

 I return false Now let me be honest with you， this is not the simplest way to implement this particular function。

 but this is a particularly simple problem that can be answered with a finite state machine anything anything function that processes a list of say integers or strings or whatever by looking at one element of at a time and moving between things that don't need to keep track of any more state than a finite number of possibilities can be implemented in exactly this way and you could actually even automatically take a description of a finite state machine and translate it down into a collection of mutually recursive functions。

 so I thought I would show you that idiom as a general phenomenon in computing。All right。

 let's do a second example， this example is going to be silly just to keep it short。

 but what I have here is a mutually recursive data type binding。

 so type T1 is either a fool of ant or a bar of T2 and data type T2 I really am defining two data types here is either a ba of string or a quas of T1 so each of these data types refer to the other one。

All， now suppose I wanted to write a function that took either a T1 or a T2。

 these will be different functions and made sure that there were no zeros anywhere in it and no empty strings anywhere in it。

Okay so here's how I would do it。 I would write a function。

 No zeros are empty strings T1 that took n in x。 If it's made out of the fu constructor。

 I need to make sure I is not0。 if it's made out of the bar constructor。

 then what I have here in Y is a T2。 So I want to call this other function I wrote for no zeros or empty strings of a T2 with that argument Y。

And here is that other function。 I've made these two mutually recursive because that other function。

 well， if x is a ba， then just make sure it's non-empty， its size is greater than0。

 But if it's a qua then I want to call the first function I wrote。 So there's no good order here。

 I really do need them to be mutually recursive。😊，Okay， so that works。 That's fine。

 It's not a particularly interesting example。 I thought I would use this example to show you a different workaround。

 So a workaround if you did not want to necessarily put these next to each other or if you were in some setting for some reason that you really could not use mutual recursion。

So the idea is to use our old friend the higher order function and have one of these functions take in the other one as an argument。

So here what I've done。Is I've written a version where they are not mutually recursive。

 so this thing takes a T2 and makes sure that it doesn't have any zeros or empty strings。

 so the BS case is still the same， make sure you don't have the empty string for the other case。

 I want to call this function up here Now this function up here is not going to be able to call this function directly because it's not in its environment。

But I could still pass it as an extra argument。 So what I've done is I've made my function over T 1。

 take not just an element of type T1， but also take a function。

 This function F happens to have type T 2 arrow bo。Alright so I could pass in any T2 arrow bowl。

 but the one I'm going to pass in right here is the function I want to call So one way you can get an earlier function in your file to call a later one it's to pass it as an argument and once we can do that everything works out just fine and this is an equivalent solution to the one that use the built-in support for mutual recursion by the way。

 this is a slower implementation， the built-in support will implement this in a much more direct and efficient way but I just thought I would show you this as a technique and flip back to the slides quickly to show you in general what we do that if you want to have some earlier function。

 call a later function， change your earlier function to take in an extra argument F and then when you call the earlier function pass in I'm sorry not F here I'll fix this after I finish the recording pass in later so call earlier with later and y and everything will work out great and that's really everything I have to。



![](img/ab179b3cef4735f15bfa1aaec5507b6b_8.png)

![](img/ab179b3cef4735f15bfa1aaec5507b6b_9.png)

Tell you about mutual recursion。

![](img/ab179b3cef4735f15bfa1aaec5507b6b_11.png)