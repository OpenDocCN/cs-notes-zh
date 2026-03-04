# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p53 52_03_polymorphic-types-and-functions-as-arguments -BV1bw4m1D7MM_p53-

In this segment， I want to talk about the type of the end times function we wrote in the previous segment and more generally talk about the types of these high order functions that are taking other functions as arguments。

So often the higher order functions we write end up being polymorphic。

 they end up having those type variables， a quote A。

 which I pronounce alpha and often also a quote B or a quote C or even a quote D where multiple type variables in the type So that can make them seem a little more sophisticated or inscrutable but it's actually really helpful it shows that these functions are so reusable that they can often take function arguments of various types。

 the same way we saw n times work over numbers when we are doubling and we saw it work over lists when we are taking the n to tail。

 but the notion of polymorphic types and the notion of functions taking other functions as arguments are actually separate issues。

 there are higher order functions that are not polymorphic I'll show you an example。

 and there are nonhighor functions， first order functions we call them that are polymorphic and I'll show you an example you've actually seen before so I'm really just reminding you of this。

 in general， I think it's worth focusing on this。Because it's always a good idea when you write down a function to understand its type。

 What sort of arguments does it work for， And that's especially true for higher order functions。

 because the functions themselves and their types are more interesting and complex。

So now let's look at this n times function。 The type it actually has is here on the slide。

 It's alphaarrow Al for the first argument， int for the second argument， Al for the third argument。

 Al for the result。 So it works for any type alpha provided that the first argument takes and returns Als second is an n third is an alpha。

Result is also an alpha。 Now， to understand n times， it's often helpful to simplify at first。

 we could have given n times a more restrictive type。

 We wouldn't have been able to use it as generally。

 but we could have given it a type where all those alphas are replaced by ns。

 and this simpler type says if F is a function that takes an int and returns an int。

 N is an int and X is an int， then it returns an int。 And if you look at the code up here。

 that makes sense。 N has to be an int because we compare it to0。

Whatever the type of x is has to be the return type of the entire function。

 because we sometimes return x。 so if one of those is in， the other has to be in。

And then the return type of this recursive call n times has to be an argument to F。

And the result type of F has to be the result type of n times because the result of this called F is what's returned。

So it turns out that the argument to F has to be the result type of F and that has to be the type of x and that has to be the return type of the function。

 but we don't actually care as the writer of n times what that type is and that's exactly what this polymorphic type with the alphas in certain positions is say it's saying all of these alphas have to be replaced by the same type。

 but it works for any type。So type inference figured this out for us。

 but once we have this and we can see it from the read ofval Pri loop， as we'll see here。

 it's extremely useful to look at this， understand this and say， a， I see。



![](img/7b05b7e45b677fcdc1da37d28c4f6e95_1.png)

F has to be a function with the same argument and return type。 That has to be the type of x。

 And that's also has to be the return type。 So if we look at how we used n times。

 we actually did instantiate the type alpha or quote a differently for different uses。

In this call here with double 4 and 7， we let alpha be int in every position。

 Do right here is a function from int to int。4 is an int。 that has been an int here。7 is an int。

 That's the third argument。 and indeed the result type is int。 for increment it was the same。

 We also instantiated alpha with int。 but for nt tail， we actually instantiated with int list。

 we can see that most easily with this argument here。

 the third argument that alpha before the arrow is clearly an int list and tail is its selfpolymorphic。

 it can work for any type of list and returns the same type of list。

 So it is correct as a function from int list to int list which is the correct type for the first argument here。

 and the overall result ends up being an int list。 So that's just polymorphic functions。

 it's not really anything new。 It just sometimes looks a little bit more mysterious once you start seeing these function arguments。

 but it makes our code a lot more reusable。 If we didn't have polymorphism here。

 we would have to write one version of n times for integer arguments and another version of n time。

For int list arguments， and that would make the whole idea of reusable code and first class functions a lot less persuasive。

Okay so that is n times。 That is the reason why we saw the type we saw from the readdevelopval print loop。

 Let me now try to convince you that there are higher order functions that are not polymorphic and polymorphic functions that are not higher order。

 So I have an example of each here。 The first is this function called times until0。

 Let me tell you what it does。 It takes in a function F and an argument X。

 and it counts how many times you need to do F of F of F of F of x until you get 0。Okay。

 so what's the first time， the first number of F's at which the result is 0。

So I've implemented that right here。 If x is already 0， then we need 0 fs。 Otherwise。

 we need one plus the number of times to get to 0 from f of x。

 So we're going to now start with F of x for our recursive call using the same function F。

 And since that's one extra step of F that adds one to the result。 Okay。

 And so that is a nice function。 And it turns out that its type is。

 let's see F has to be an int arrow int。😊，And x has to be an int， and then the result is an int。

 and y is that Well， x has to be an int because we compare it to 0。

F has to take an int because right here we call it with X。 X has to be an int。

 We call F with x F has to take an int， and therefore x has to return an int because it's passed as the second argument to times until zero。

 So it turns out that this high order function， which is convenient and reusable you can imagine using it in many situations for seeing if some function converges or something only works with integer。

 that just doesn't make sense otherwise， you can't say how many times do you have to convert a string into a different string until you get zero。

 that doesn't make sense strings will never be0， you cannot compare them with 0。

 So not a polymorphic function， but nonetheless a useful high order function。

 conversely here's a function we've seen many times。 It computes the length of a list。

 and its type is it will take a list of any type and return an integer doesn't care what the type of the elements are。

 It never looks at them In fact， we could replace this pattern here with a wild card that would arguably。

Be better style。 So it has a polymorphic type， but there's nothing。

 there's no first class function inside。 It just takes a list and returns an integer。

 Okay so that is our contrast。 Hopefully now we understand the type of n times better。

 and we understand the relation between polymorphic types and functions as arguments。



![](img/7b05b7e45b677fcdc1da37d28c4f6e95_3.png)