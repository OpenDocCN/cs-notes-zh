# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p82 81_04_type-inference-examples -BV1bw4m1D7MM_p82-

In this segment we're going to work through a couple examples completely to show type inference before we get to the examples。

 let's make sure we remember the key steps here right the idea is to just collect all the facts we need all the facts that have to be true for something to type check and use those to constrain the type of the function so we're going to do two examples neither of these examples will involve polymorphism and then I'll change one of the examples so in fact it doesn't type check at all and we'll see how type inference can figure that out as well。



![](img/4d6864c11f443ed90cdc21aafd658038_1.png)

So for the rest of the segment we'll just do this over here in the EmX buffer and here's our first example it's a fairly silly code that just takes in a pair of ints and adds them with absolute value and whatnot of course T inference doesn't really reason about what the code does it just collects facts for type checking so it sees a function binding F and the first thing it realizes is for some types T1 and T2 F has to have type T1arrow T2 why well it must be a function and we know all functions。

Take one argument。 So that just has to be。 And in fact， if we look at the pattern。

 which is just a variable here for that argument， X has to have type T 1。

 There's no other way this function binding is going to type check。

So now we can go on to the function body to start gathering additional constraints and we first see this binding here and we say。

 okay， I have two other variables I'm going to have to figure out T for。

 so Y is going to have to have some type T3 and z is going to have to have some type T4。

And now we can start looking at all the expressions and patterns in our program to come up with additional constraints among these types T1。

 T2 and T3 and T4。 so the first thing we see from the pattern match is that T1 has to be T3， star T4。

 there's no other way for this pattern where we match X against the pattern Y comma Z to type check。

 so else pattern match。Does not type check。 We can write down these reasons as we go just to keep track of what we're doing。

So the next thing we could look at is this function call here。

 Now remember we've already type checked all earlier binding。

 including things that are built into the environment。

 and so we already know that abs has type int arrow int。And so for abs of y to type check。

 y is going to have to have type end， which means T3 has the equal endt。 T3 being the type of y。

 T3 equals int。 and that's everything we get from this construct here， fortunately。

 we get an int back because plus will require that。

 and that means that this expression over here will have to be an int。 And since that's Z。

 we know that T4 has the equal endt。Aha， this is because。We added Z to an int。

So given those three constraints。T1， our argument tied to our function is in star nt。

 and we've already inferred the argument type。Now， in terms of the result type。

 we have that abs of y plus z。Plus Z has type int， so the let expression has type int。

 so the body of our function has type in and we know that T2 has to be the type of the body of the function。

 so T2 has the equal int and once we've constrained T1 and T2。

 that's the type of F which is what we were supposed to be inferring and we have our result。

So we just gathered facts and continued to propagate those constraints until we had the type we needed for F。

So now let's go on and do a more interesting function function that's actually useful for something and that's summing all the elements in a list。

 So it's going to start the same way。 sum is a function。

 so it has to have type T1 arrow T2 the argument has to be that T1 and now we're just going to look at these three lines which actually have quite a bit of information about what T1 and T2 need to be。

So first， because we pattern match a T1。We know that these other variables。

 x in that pattern has to have type T3 and x is prime has to have type T3 list。And the reason why。

 sorry， excuse me， is that if we have this pattern here， it can only match lists。

 We know the second thing has to be some list and the first thing has to be an element of the list。

 So they have to be related like this and in fact， T1 because we are pattern matching against x's has the equal T3 list。

 There's no other way for just the patterns， just the things on the left of the arrow to type check。

So now we can look at this first branch here and we can say， oh， in fact， since zero has type int。

 and that has to be the type of a case expression， the case expression is the function body。

 we can know already that the return type has to be int because zero might be returned。Okay。

 so we know our result type， now we just have to look at this other branch and figure out what's going there。

On there。So we know that T3 has the equal int y， because x has type T3， and we add x to something。

Okay， so we see that just from here。 I'm ignoring here， by the way。

 that plus works on type real as well。 That's an issue I'm going to ignore in this segment。

 but that's okay。 So we have quite a bit here， and we just have to deal with this sum of x's prime。

And in fact， everything we already know is enough to type checkck this。 So we know T3 is int。

 We know x is prime is a t3 list。 So this has to be an int list。 and int list is T3 list。

 which is T1， that is the argument of sum。 So this recursive call already type checks。

 This recursive call has to give back a T2， we know T2 is int and that's good because that's the argument to plus。

 So it turns out we don't get any new facts here， we already had all the facts we needed。

 and it turns out that just from T1 equaling T3 list and t3 equals int。

 We know T3 equals int list and from that and T2 equals int we know that F has type int list arrow int just like we need and just like we want some to have。

So that's our second example。 And now what I'm going to do is break this example so that nothing I did here is wrong。

 This is correct。 Now let's go and change our code and see what type inference would do in that case。

 So I'm going to make a mistake here。 a mistake that will not type check if I make this mistake it will type check it will just be an infinite loop I'm more interested in this mistake but I try to recursively call some with the head of the list。

 and this is in fact now not going to type check so let's see why。

Everything starts how it did before， some still has to be a T1arrow T2 x is still has to be that argument type。

 x and x' is prime still have to have the form T3 and T3 list for some type T3 because they are part of a list pattern。

We still have that T1 has the equal T3 list， and that's because of x's being pattern matched against x colon x is prime。

We still have the T2 as equal int because of this zero here that's returning it。

We still have to have the T3 is in because we're adding it right here。

And now we're in a very interesting situation。 So let me delete this and just focus in on this sum of x。

 So we know from T1 equals T3 list and T3 equals int that T1 has the equal int list。Right。

We also know that T3 equals int。And that is the type of X。

So now I have to try to call something that needs an int list with something of type inth。

And that cannot type check， there is no way to set up additional constraints so that's going to work out。

 And so I would expect an error message from the type checker something along the lines of。

 I think X has type int， and I think some needs an in list。Now that's how we did type inference here。

 and that's the sort of error message we would get if we went in this order。

But the type inferencer sometimes has a bit of a mind of its own， if you will。

 in the sense that it can gather constraints in any order it likes that will not affect its final result。

 which is a deep property that's very cool。 but it will report an error as soon as it gets to a situation where it reaches this sort of contradiction。

 the sort of thing where it says int has the equal int list and I know that's impossible。 So in fact。

 when I try this out， I think we'll see a different error message in a different place in the code。

 and that's okay。 I mean， you might not like it。 but in some sense。

 there are too many facts here for them all to be true and the type error message is just going to tell you about one of them。

 So if it goes in a slightly different order， I think it actually complains about case object and rules don't agree。

It says that the。I think what it's saying is that it thought this was going to be a list and something else was an ant。

 honestly I'm not really sure I can try to fix that by putting in type annotations or whatnot。

 but it's actually complaining up here that it figured out。That x is。

Is going to have to have type int because of how we called it down here。

 But now you're matching it against an int list。 So all it really did， if I had to guess。

 was it worked on these facts before the pattern matching facts。

 So you got a different error message。 But it always the text。

 because this is how type inference works。 that there is no way for the entire thing to type check。

 And so it gives you one error message about where it ran out of room to try to figure out a good answer。

 Okay， so that's our examples of working through type inference。

 We'll see more examples next where we're going to end up with polymorphic types for the results of our function。



![](img/4d6864c11f443ed90cdc21aafd658038_3.png)