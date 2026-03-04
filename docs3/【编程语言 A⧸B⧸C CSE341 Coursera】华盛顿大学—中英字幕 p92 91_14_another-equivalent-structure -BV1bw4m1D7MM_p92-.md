# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p92 91_14_another-equivalent-structure -BV1bw4m1D7MM_p92-

In this segment， I'm going to show you a third implementation of rational numbers that will be equivalent to our other two as long as we keep the type abstract。

 and what I'm going to do here is actually change the implementation of the type rational in order to emphasize that when a type is abstract an equivalent structure can go ahead and change how the type is implemented。

So given a signature that has an abstract type， different structures can have that signature while implementing the type in different ways。

 those structures or might not be equivalent， I'll show you an example where they are so I'm about to show you a third implementation rational3 and in rational3。

 the type rational is going to be implemented as a type synonym with intstar in。

 so let's go over and see that。

![](img/654d272ab43141e1e83f2b1eb3ee212e_1.png)

Here is my structure。 You'll see I have a type synonym here。 So in the rest of this module。

 rational and instar int are the same type。 The outside world， however， does't have to know that。

 So before I show you these functions， how about I just show you remind you what the three signatures look like。

 Now， signature rational A requires the module to implement rational as this data type。

 Since our module does not rational 3 does not have this signature。

 If we try to give it this signature， the type checker will reject it。

But it does have this second signature rational B， As we'll see。

 we already saw it defines a type rational， it defines it to equal instar int。

 that's a fine way to implement type rational， but given that definition。

 it's going to have to have these three functions where rational is in star int。

 the outside world as usual will not know that rational is in star int。And then for rational C。

 it can have this signature provided it has everything it had before as well as a function of type interrational。

 and I'll show you that at the end， so let's see howstructrational 3 is implemented and the fact that it can have type the signature rational B。

So rationals are now just pairs of ints in all cases。 So here's make frac。 If the denominator is 0。

 raise an exception。 If y is less than0， then produce negative x comma negative y。 just like before。

 but now it's just a pair of ints。 There's no frac constructor involved， otherwise return x comma Y。

 notice we're not treating hold numbers any differently。 So if this denominator is one。

 then we'll just return x comma 1。To add two fractions。

 we'll add needs to take two rationals and each rational is an instar int so this pattern will do well。

 and we're not going to reduce things， that's an orthogonal choice， but like rational 2。

 we're just going to wait until two string to reduce things。

 so we'll just return a times d plus c times B in the first position and B times D in the second position。

And then finally， to string is a little more complicated because we still want to return everything in reduced form and treat whole numbers。

 especially here。 So here's what you need to do。 If x is 0， you have a numerator of 0。

 you better return the string 0， otherwise。We have some more work to do here with GCD and Red so here's a let fund GCD equal this in let's convert to a string。

 the numerator concatenated with if the denominator is one， then don't do anything。Else， a slash。

 and then to string of the denominator。 So I didn't emphasize as up here。

 I've computed the numb and the denominator by dividing both by the GCD of the absolute value of X and Y。

 So a bunch of arithmetic， But the point is to not print the denominator。

 if the if the numerator is 0 or if the denominator is one。And so overall。

 if we go back up here to the signature rational B， we provided everything at the right type。

 make Frac， returned an instar int， add， took to intstar int and returned an instar int and two string。

 took an instar int and returned a string， and then the outside world does not know that rational is instar int。

Now， if we want to implement rational3， we also need a function whole of type int arational。

 This was this cute thing where for our other structures。

 the data type binding was providing this function。

 and then we are exposing just that part of the data type binding to the outside world。

Now in our new structure， we don't have a data type binding。

 we don't have such a function being defined by it。

 but we can still implement this signature provided we have this function and so again it's a little cute。

 but down here at the bottom I just defined a function hole you're allowed to start functions with a capital letter if you want to that just takes in an eye and returns this rational。

 this intstar int of I comma 1 and it works great。So that is our third implementation。

I want to emphasize that when we do signature matching of this structure against either rational B or rational C a couple interesting things are going on。

 so let me emphasize those for you the first is make frack internally as type instar int arrow instar int and so that does match a signature where we'reing exporting it as instar int arrowration because rational is Instar int and the client will never be able to tell that we're actually returning something of the same type we're taking in because the client doesn't know those are the same types。



![](img/654d272ab43141e1e83f2b1eb3ee212e_3.png)

Now what's interesting is we could， if we went back here to rational B， we could say that make Frac。

 instead of being int star int arational， it's actually rational arational。

 Now this is a very bad signature。 the structure has this signature。The type checker will accept it。

But。The structure will be useless。Because if all the outside world knows is that it can use these bindings。

It's never going to be able to call make Frac Add or two string because it can never get its first rational to get started。

 There's no way it can call any of these functions。

 So there are programs out there that type check and are not useful。 Okay。

 so we really want to expose here that make Frac does take two ins as arguments。

So that's the first interesting thing。 The second interesting thing is this function whole。

 So let me go back and show that to you here at the bottom。



![](img/654d272ab43141e1e83f2b1eb3ee212e_5.png)

Based on what we know from type inference。😡，This is going to have type alphapha arrow。Alpha star int。

 and that is indeed what the type checker will give this function internally when it goes to type check it。

 but in our signature in rational C， we said this had to have type int arrow rational。And so somehow。

 the type checker， which is fairly sophisticated and fairly smart。

 has to get from this first type to this second type legally。

And it turns out it can because the rules of signature matching let you take a polymorphic function and instantiate it to a nonpolymorphic function。

 So the first thing the type checker has to figure out to do for signature matching is to realize that alpha can be int and therefore this could also have type the less flexible type intarrow in star int。

 We have to replace all the alpha consistently。 and now we see that indeed。

 since rational inside the module is in star int， we can is we usually do match this type against this type in the signature。

 and it's pretty neat that Ml does that for us。 Not that this does not have something like the type Al arrow in star int。

😊，Or， you know， int。Arrow。Alpha star end。When you take a generic type。

 a polymorphic type and make it less general， you have to replace all the alphas with another type。

 this function hole does not have these bottom two types。 That doesn't make any sense。

 It is not the case that if you called hole with a string， you would get back in and start int。

 So these types are just wrong。 and I will delete them。

 It is interesting to me that inside this module， we actually could call hole with a string for I。

 but outside the module because of what the signature says we can only call it with an int。

 and therefore it will return aration。

![](img/654d272ab43141e1e83f2b1eb3ee212e_7.png)

So that is the more sophisticated and interesting details of this third structure。

 but the high level point is that under rational B or rational C。

 this structure is equivalent to our other two structures。

 even though it implements the type rational in an entirely different way。



![](img/654d272ab43141e1e83f2b1eb3ee212e_9.png)