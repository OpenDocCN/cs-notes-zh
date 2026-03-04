# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P40：-040-An ADT for Pokemon Chap3 Video 18.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

For another example of algebraic data types， let's take a look at Pokemon。

Perhaps some of you have played Pokemon before， if not， here's all you need to know。

Pokemon do battle against one another， and Pokemon have types。They could be fire type， water type。

 bug type， and so forth。For simplicity， let's just assume right now that every Pokemon only has exactly one type。

When Pokemon attack against one another， their type can determine whether they do more or less damage。

So this is known as being a normal attack， a not very effective attack。

 or maybe a super effective attack。And so we can look at tables like the one on here a。

Water Pokemon attacking against a fire Pokemon does twice the damage as's a super effective attack a fire Pokemon attacking against a water Pokemon does only half damage that's not a very effective attack。



![](img/84f73b9121db162c1428b1849eb7e421_1.png)

So let's write some Oaml code to model these Pokemon， so let's build a type for Pokemon。

So what is their type， I don't want to say that their type is named type because types already a reserve word in OKl。

 so we'll call that their P type， say。And their p type could be either normal or fire or water。

 let's just use those three as examples。And the effectiveness of an attack。

Let's call that the Pokkemon's effectiveness could be either normal or not very effective or super effective。

Now let's pause just for a second here。If I had a value X， which was normal。

What is its type going to be， which of these normals does X refer to？😡，I can ask VS code。

It's P effective， P。So just like any other kind of situation in Ocael or really any other language。

We have shadowing going on here。The second definition of that name normal shadows the definition of the first one。

And we can't really get back to it in this case， not with O constructors。

There are some ways of getting around this， we will actually learn about them next week when we learn about modules。

But for today， let's do something simple。And let's just prefix each of these so that we can disambiguate them by their name。

So that could be the type normal， that could be the effectiveness normal。

 and now for consistency I'm just going to put in a T in front of each of these and an E in front of each of these。

This is an idiomatic way in OCel of dealing with constructors that are both defined in the same file and happen to have the same names。

Again， when we look at modules， we'll find a little bit better of a way of handling this as well。

Okay， so x now could either be t normal in which case it's P type。

 or it could be E normal in which case it's Pf。Next。

 let's write a function that gives us the damage multiplier based on effectiveness。

What the multiplier of effectiveness be， let me pause here。

It's idiomatic in OHaml to name functions that transform one thing into another in this form。

Here I wrote multiplier of effectiveness。Because I want to produce the multiplier out of a given effectiveness level。

You might also have functions， for example， string of int。

Which gives you a string representation of an integer。So usually in Ocal we write of rather than two。

 we don't write effectiveness to multiplier， so the multiplier of an effectiveness。

 we could use pattern matching to do this。Immediately pattern match against an argument。

 and if it's normal。The damage multiplier is one。If it's not very effective。

 the damage multiplier is one half。If it's super effective， then the damage multiplier is two。Okay。

 so now we have a function that takes in a Pf and gives us back a foot。Remember。

 that keyword function there is actually syntactic sugar for taking in an effectiveness here and immediately pattern matching against it。

But we get to remove all that boilerplate code and just say。Fction。Next。

 let's encode the table of effectiveness of attacks。Okay。

 we're done encoding that table and now we know if you attack fire versus fire。

 it's not very effective， but if you attack water versus fire。

 it is super effective and any other combination so I've used that wild card there at the end to say everything else is just a normal attack。

One way of simplifying this code would be to use some advanced pattern matching syntax。

 which uses or patterns。What we now have is a function that takes in a pair of types。

And gives us back an effectiveness。We could put that function to use。

What is the effectiveness of fire？Versus fire。Not very。

You might also want to write this function in a different way such that it takes in those two arguments not as a pair。

 but separately as it were Now we know there aren't really multiargument functions in OcaMl but this is close enough。

To write the function that way。You could go back and modify the code a little bit。

Now we have a function that takes in those two separate arguments。

And we could apply it to each of them individually， but not as a pair。

So the difference between these two different versions of this function， which either take in a pair。

Or take in two arguments and then match against them simultaneously。Is not so big。

 is one of the versions of the function better than the other？Not really。

I guess it all comes down to which form you're going to find more convenient for the code that you happen to be writing around it in the file。

 that's how I would make the decision。If you take a look in the textbook。

 there's a discussion of a topic called Currying。In which you'll learn more about this。

Let's finish up by introducing a record type for Pokemon。And now we could model an actual Pokemon。

There you go， now we have Charmander modeled as a Pokemon。



![](img/84f73b9121db162c1428b1849eb7e421_3.png)