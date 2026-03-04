# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p24 23_13_options -BV1bw4m1D7MM_p24-

All rightIn this segment I want to introduce the last major language construct we'll use just a little bit on homework1 and that's options and to motivate this。

 I want to go back to this function we've seen before for computing the maximum of a list so this old max function old because we've seen it before takes in an int list and returns an int and we like it in many ways it's efficient and how it does its recursion and everything but I never liked how it treated the empty list there's no such thing as the maximum integer in an empty list and returning zero was always an awkward workaround now you could try to return a really negative number or something but I'd prefer to say that you should not try to compute the max of an empty list so what should we do well there's a few things we could try to do we could say that's a runtime exception and and we should raise an exception just like if you try to divide by zero or take the head of an empty list and we'll see exceptions at some point but this in this。



![](img/2139c17c3551571287e01601f9784847_1.png)

![](img/2139c17c3551571287e01601f9784847_2.png)

I want to actually try to return something useful。 So another thing we could do。

 given the constructs we already have is to change max。 so it doesn't return an int。

 It returns an int list。 And what we do is if you pass it the empty list will give back the empty list。

 And if you pass it the nonempty list， that would return a one element list holding the maximum of all the numbers that were in the argument。

 And that would work。 But it's poor style and the reason why it's poor style is this returning0 or one thing is common enough in programming。

 that Ml has a different type and a different set of language constructs that's designed for this。

 and it's better style to use it so that users of your function understand that's how it works。

 whereasas a list could hold any number of elements。 When you have the zero or one situation。

 you want to use an option instead。So。It's pretty easy to understand options。

 And the way I like to explain them is by analogy with lists。

 so we're gonna have a new kind of way to build a type the same way we could write T list for any type T we can now write T option for any type T and these are different types。

 Option are not lists lists are not options it's just an analogy to make it easy to teach。

 All right so just like with lists， we had way to to build list and ways to access the pieces。

 we have the same thing with options。 there's two ways to build an option。

 you can write none in all capital letters， and that builds an option that holds zero items。

 the same way bracket bracket builds an empty list or you can write some in all capital letters and then an expression and the way that will evaluate is you evaluate the expression E to some value and if that value has type T。

 you end up with a T option。 much like creating a one element list。

 So that's how you build it when you have。Some of something like sum of three。 That's an int option。

 And you can't use it like an int because it's not an int。 It's something holding an int。

 So when you have an option， you have to access it using these last two built in functions。

 They're really just library functions。 The first one is called is sum。

 And it takes an an option and returns true if it's a sum and false if it's a none。

 So it's a lot like null for lists， except it's actually inverted。

 We return true for the non-empty case for the one element case。Then we have one more construct。

 and that's Val of， and that's the thing that takes an option and gets the thing out from underneath the sum so that will raise an exception if the argument to Valive is none。

 if the argument is sum， you'll get the piece back。That's all there is to options。

 So now let's use this to implement a better version of Max。

 and I've actually already written it out this time， so this is I'm going to show you two ways。

 so this is the first way， so I've called it max 1。

 and this is now a function that's going to take in an int list and return an int option。



![](img/2139c17c3551571287e01601f9784847_4.png)

Alright， so if the argument x' is is null， then what I want this function to do is evaluate to none。

 That's exactly what I have here。 So I'm always returning an option。 In this case， it's none。Else。

 how about I recursively figure out the max of the tail。

 and I'll store that in tail ants because we've learned our lesson there。 All right。

 Now I need to remember that the value in tail ants is an int option。

 So the only way I can access it is with is sum and Val of。So what I could do is say， if it's a sum。

And its value is greater than the head of the list。Then that's the maximum return tail anance。

 otherwise。Either tail answer is none because tail of x's was the empty list or the head of the list is bigger than the rest of the list。

 And in either case， what I want to do is return this option。

 I want to build an option out of head of X's and construct the option itself with sum。By the way。

 this is the first time I've ever shown you。 and also this is really just something that takes two booles and computes their conjunction。

 And I'll explain that in more detail。 in the next segment。

 can't always get everything in exactly the right order。 All So this max will work。 It works great。

 we try to run it。 You'll see that I've already got the second version implemented here as well。

 So what you see in this file or three functions。 Old Max。

 which takes an int list and returns an int Max 1 and max 2 with both which both take an int list and return an int option。

 So if I call max 1， would say the list 3，7，5。 I get back sum of7。

 What I cannot do is say take that and try to add one to it。

 That doesn't type check because what I got back was not an int。 I got an int option。

 What I have to do instead is vow of max 1 of 3，7，5。😊，And then I could add one to that。

 and that would work fine。If I say max1 of empty list， I get back none。

 and if I try to say v of that， I get not a type error， but actually a runtime exception。

 just saying that unco exception option， just like if you try to take head of the empty list。

 get unco exception empty。Alright， so that was a good solution of Max 1。

 It works in a way that clients can understand。 Let me show you a second version that's a little bit better in terms of implementation。

 but where it's exactly the same way for clients。 What I don't love about Max 1， although it's okay。

 There's nothing wrong with doing it this way。 is every time I come back from the recursion。

 I'm checking whether it's a sum and none。 And that none case was only for the empty list。

 So at the very last recursive call， I return a none than one for the one element list I return a sum and then another sum and then another sum。

 And I'm checking for none every time All， So you can avoid that。

 So here's a second version of max2 that is arguably a little cleaner。😊，And what it does is。

 of course， if you pass it the empty list， we return none because that's the right thing to do。

 Otherwise， let's create a recursive helper function that will take care of computing。

 The max of what we now know is a non-empty list。 All。

 So what this function does is taken a list that it assumes is not empty。

 And this function has type int list arrow int。And since x's is never empty。

 it can just do the natural thing。 And that natural thing is to just test O。

 if it's the one element list， then return that one element。Otherwise。

 recursively figure out the max of the tail and then compare it with the head and return the right thing。

And since I only ever call max nonempty with a non-empty list either right here to start the recursion or recursively here。

 because in the case that I am almost empty， I do not recursively called it on the empty list。

 I just immediately return this will never raise an exception So when down here I call max non-empty on x's。

 I will get back an int， which is the maximum element of the list。

 but then max 2 can't just return that int。 it has to return an int option。

 so it uses sum to return the result and we can check that that works as well。

 so let's just try max 2 of 37，5， and we should get7。 you see that they're at the bottom sum of7。

 excuse me whereas max2 of empty list still returns none so either max1 or max2 work。

 I prefer max2 just a little bit， but they're both fine style and now we've seen how to use options and how they're a lot。



![](img/2139c17c3551571287e01601f9784847_6.png)

Like lists， except instead of having any number of elements。

 they just always have  zero element or one element。 And that's options。

