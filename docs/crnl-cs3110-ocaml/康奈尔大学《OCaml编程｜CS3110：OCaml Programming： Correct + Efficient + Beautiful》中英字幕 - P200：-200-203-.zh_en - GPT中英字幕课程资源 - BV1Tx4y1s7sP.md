# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P200：-200-203-.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We started off with a language that omitted let expressions。 Let's go back and add them in now。

 As I said before， it turns out they're surprisingly tricky。The rule that you might start off with。

Is that to infer the type of a lead expression， you first infer the type of its binding expression E1。

So that gets you a type T1 and some constraints C1。

Then you can add X to the static environment under that type T1。

Infer the type of the body expression， E2。Getting a type T2 and some constraints C2。

And then conclude that the type of the entire lead expression is T2。

 along with those two sets of constraints。

![](img/fe0e81048cc39cfeff4310b382a16224_1.png)

This is a reasonable rule， and it gets many cases right。 For example。

 suppose we wanted to infer the type of let X equal 42 in。X。Well。

 we would go ahead and infer the type of the binding expression 42。

 that's a constant of type int generates no constraints。

We would then add the name X to the static environment under the type that we had inferred for the binding expression。

 so that's int here。😡，And we would go ahead and infer the type of the body expression， which is X。

Well， of course that's just the name rule that we need to use for that。

 so that would have type int because that's what the name is bound to in the static environment and generate no constraints。

So at the end， we would conclude that this lead expression has type int and there are no constraints。



![](img/fe0e81048cc39cfeff4310b382a16224_3.png)

It's an easy case where the rule does work， correct。The problem comes with polymorphism。

So suppose we were working with the identity function。

And then we applied the identity function twice。😡，Once to an int another time to a booleion。

Now we ought to be able to do that。 that's the nice thing about polymorphic functions。

 you can use them at many types。😡，That means we want the type of that polymorphic identity function to be alpha arrow alpha。

😡，We don't want it to be just int arrow end or bool arrow bo。😡，Either of those would be too specific。

Well， the problem is that the naive let rule we just gave doesn't let the identity function be polymorphic in that way。

Here's what happens。It will go to put the identity function under the type alpha arrow Al in the environment。

 But then later， when it is applied。Well， when you apply it to an integer。

 that generates a constraint。That the type of that function needs to be the type of its argument。

 arrow something else。 So the argument there is known to be an int。 Therefore。

 that's going to lead to a constraint eventually， that alpha equals int。

But then when we apply it to true， we're going to get another constraint。

 which is that alphapha arrow Al equals bo arrow something else。

 So the bo thereby is because we have a Boolean constant that we know。

And that will lead to an additional constraint during unification of the form alpha equals bo。

So now we've got an inconsistency， we need alpha to equal both int and bo and that can't happen。😡。

So what went wrong here？Actually is something that is so subtle that it seems right when you first see it。

The problem is what we put in the invite。We said that Id has type alphaphaarrow alpha。

It means that there is a single unknown type alpha that it takes as input and returns as output。

And unification， then will， of course， go ahead and solve for that single type。But really。

 what we wanted was something different。We wanted there to be many unknown types， alpha。

 and every application of ID ought to be able to use a different value for that type。😡。

So the solution to this is inspired by universal quantification in logic。You know。

 you can write expressions in logic like for all x， it holds the0 times x equals0。

 so we've universally quantified that variable there to say， hey。

 this can range over any value that you want it to take on， apparently from some set of numbers。

In type inference will have the same thing。Willll have something called a type scheme。

Now this is going to be written alpha dot T。 and now in textbooks。

 you might actually see this written as for all alpha dot T using the for all quantifier from mathematical logic。

 I'm going to omit writing for all here， but you can think of it。

So alpha here is going to be a type variable that is in scope in that type T。😡。

We can also extend this to allow more type variables as part of the syntax。

 so you could write alpha 1， alpha 2， alphapha 3， all the way up to alpha n dot T。

And this is just like how in logic， you can quantify over multiple variables too and say things like for all X。

 Y， and Z that there's some property of those three variables that holds。Guess what。

Type schemes are part of Ocael and always have been。 You just haven't seen them until now。

 How about the link function from the list module。List dot length has type alpha list arrow in。

 You knew that， right。Well， guess what。 I can give it a different type。 In fact， a type scheme。

Let my length of type alpha dot Al list， arrow int。E list dot length。

And that has type Alpha list arrow in， but Ocamel accepted my type scheme。

So what's going on here is that implicitly the type scheme is always there When Ocal outputs something like this with alpha list arrow ins。

 implicitly any type variables that are showing up there are really quantified as part of a type scheme that Ocaml just doesn't bother to print and it doesn't bother to print it because it would just be extraneous information It's always there。

 Most programmers don't need to know about it so there's really no reason to print it out。😡。

But if you ever want to manually put it in like I did here， you actually can。Here's another example。

 Suppose you have the function that takes in two arguments and just returns the first one。

So that has type alphaarrow betaarrow alpha。Well I could give that a manual type annotation。

 that's the first of two， I'll call it that takes in an alpha and a beta。

 so I'm going to quantify those variables as part of the type scheme。

And the type is actually alpha arrow， beta arrow。And that's going to be fun。 X， Y， arrow X。

So Ocaml accepts my typekin as an annotation there， it is correct。

 but then just doesn't bother to print it back out as part of theL。

But it's always there and always has been。So here's how OcaML and HM type inference uses this idea of type schemes。

😡，When you get to a polymorphic function like this， sayID， which has type alphaphaarrow alphapha。

The type inference algorithm will actually generalize that type to a type scheme。

So it'll take that alpha arrow alpha and generalize it to alpha dot Al arrow alpha。

Think of that as generalizing in a sense of universal quantification。 It's say， for all alpha。

The function has that type。Then at each use of the function， at each application of it。😡。

Type inference will instantiate that type with a new type variable。😡。

So it's like filling in that universal quantification with something more specific now。

At the application of idD to0， we might instantiate it then to say beta arrow beta。

 assuming beta is a fresh type period。And then later， at the application of idD to true。

 it would get instantiated with a different type variable， say gamma arrow gamma。Now。

 each use of the function is independent of the other uses of the function。

 so each usage can end up having its own type， whether that's arrow int or rule arrow bo。😡。

To make use of generalization and instantiation， we just need to update two rules in little ways。

So the naive let rule we gave is almost correct。 It's just we need to generalize a piece of it。

 So when we go to put the type T1 of the binding expression E1 into the environment。

 we generalize it to create a type scheme。😡，Now， the slight complication there is we need some additional information in order to do the generalization correctly。

 We need to know the constraints that were generated， the environment and the name of the variable。

 So that's why the called to generalize occurs outside of all of those。

 I'll show you what that looks like in just a。The name rule is the other when we need to update here we need to instantiate any type scheme we discover。

😡，When we use the name of a variable。 So instantiation， then in more detail。

If you apply as instantiate to a type， strictly speaking， a type， not a type scheme。

 so there's no quantification going on， it doesn't change it， just leaves types unchanged。😡。

But when you instantiate a type scheme， you're changing it back into a type， you get rid of the Al 1。

 Alpha 2， alphapha n， whatever however there are dots in front of it。

And you substitute a fresh type variable for each of them。

So if you had something like the identity function， which would be alpha dot alphaarrow alphapha。

 that would become beta arrow beta for a fresh beta。Generalization is the harder one of the two。

 so it takes these three or maybe four inputs here， a constraint set， a static environment。

 a name of a variable and the type that was initially found for that variable that we now possibly going to general。

Here's what Generalize does。It fully finishes inference of that binding expression。

 so it's like we're going to stop here， we're not going to worry about the rest of the program for a minute。

We're going to take that constraint that C1 and unify it。That'll get us a substitution。

We then apply that substitution to the environment。

 so we're sort of mining that substitution for all the information we can get out from it。

We also apply it to the type T1。😡，So that gets us a new environment， let's call it N1 and a new type。

 let's call it U1。Now， we generalize U1。So we had fully finished inference for it。

 we look at it and say， are there any type variables here we could generalize and turn this into a typescape？

Now you might start off by， well， I could generalize all the type variables in it， in fact。

 there are some that maybe should not be general。😡。

And those are any type variables that also show up still in the static environment。

And the reason for that is they come from surrounding code。

 code outside of the lead expression that we're currently working on。

It must be nested inside something else that itself bound some name。

So we don't want to generalize those because the outside environment already has some assumptions about those type variables。

 maybe it's going to use them someplace else， maybe there's constraints that are going to emerge about those someplace else。

 so we don't allow those to be general。Generalized then returns that environment that had the substitution applied to it。

As well as the binding of X to this generalized type scheme， S1。

This is what makes polymorphic type inference work。 This is， in a way。

 the essence of H type inference that it does this generalization to type schemes at let bindings。

And so sometimes this way of doing type inference is referred to as let polymorphine。

Before we leave the topic of type inference and polymorphism。

 there is one more complication we need to discuss。It has to do unsurprisingly， with mutability。😡。

Mutability always makes your life worse。What do all of these expressions have in common？Well。

 they're all refs。And they're all refs to something of a polymorphic type。What type is none。

 it's an alpha option， what type is the empty list， it's an alpha list。

 what type is the identity function， it's alpha arrow alpha。

But something unexpected happens when we put each of these into Utah。 So what is ref none。

It's not alphapha option ref。It's tick underscore week1 option ref。Isn't that weird。

What's a ref to the empty list？Takeick underscore week two list。

Let's refer the identity function on x arrow x。Oh my。

 So what all these have in common is weak type variables。

 You saw the word weak showing up inside of each of those type variables。

So what I want to do next is to explain to you what weak type variables are。😡。

But you're going to understand first the problem that they solve。 So let's turn to that。😡。

Here's the problem。 Suppose you have this code in which you bind the identity function to the name Id。

 and then you create a reference to that identity function。

Update the reference and then try to use the reference。Let's focus in on the second line。

What should the type of the reference R be there？😡，Well。

You might initially think it should be an alpha arrow Al ref。

Because it's a reference to a polymorphic function that takes in an alpha and returns an alpha。Okay。

 we know now from type inference that we would generalize that to a type scheme。

So R would get generalized to alpha dot， Alpha arrow Alpha R。Now that it's been generalized。

 each time it's used， it gets instantiated。So here， when we update R to be the successor function。

 that's actually a function built into OcaMl， it's just the function that adds one to an integer。

Well， then we'll instantiate the type of R from that type scheme。To a type in arrow and ref。

 because we're going to discover that needs to be an integer function。

At the point at which R is dereenced and applied to true here， during type inference。

 we'll again instantiate that type scheme， but this time we'll instantiate it and figure out that it needs to be a bo or a bo ref because it's been applied to a bo。

Oh， something bad just happened， though。If the successor function is stored in R and we dereference R and get that successor function out。

 it's a function that expects an int as input。But we just applied it to true， which is a bo。

So the world's going to blow up here。 We just did something that's not type safe。 Oh。

 Caml is never supposed to allow us to do this。And indeed， Ocael doesn't allow this code。

Let's try this out in Utah。So we have the identity function。Which we can then store in a ref。

And update to be the successor function。Now if I try to dereence that ref。And apply it to a boolean。

I get an error。 This expression has type bo， but an expression was expectedul of type int。

So OKML doesn't allow this code to run， and in fact， there is a type error that occurs。

The solution that Ocael is using here to prevent that kind of explosion from applying successor to a boolean is something called the value restriction。

The value restriction is something that shows up in many languages。

And it says that a mutable polymorphic value can never hold more than one type。

You can only stick an int into it or bool into it or an intarrow int function or whatever it might be。

😡，OCM currently implement the value restriction with weak type variables。

 which are what we've seen showing up a couple times now already。

A weak type variable stands for a single unknown type。

 which is exactly what our type variables did before we introduced generalization for polymorphism。

Eventually a weak type variable is instantiated with the actual type。

 and from then on is not a type variable anymore because it's been instantiated once and for all。

Going back to our code here， let's look in more detail at something that happened with the types。

So when I bound R as a ref to ID， it got a type involving a weak type variable。

 That's what any type variable showing up here with underscore week means。

 So here we got the type tick underscore week2 arrow tick underscore week to ref。😡，So this is a ref。

To something that is a function。And that function is going to take the same input and produce the same output type。

But that function is not polymorphic。It's just there's an unknown type here that hasn't been solved for yet。

 essentially。Okayel doesn't know whether I'm going to stick an int arrow end function in there or a bo。

 arrow bo or something else。😡，But then later on， I do put such a function in。

So I can take the successor function， which is an inter int， and I can store it in that reference。

Gives me back unit。But look at what happens now to the type of R。

It's no longer involving weak type variables that weak type variable has been permanently instantiated at int。

And from now on， we're never allowed to stick a different type of function in there。

 So we couldn't stick a bo arrow bo function in there， for example。

That doesn't work because not test type bo， arrow bo， not in arrow in。

So it kind of looks like the type of R is changing when we do that mutation and there is a small sense in which it is it's that there was an unknown type before when we hadn't yet instantiated that weak type variable but when we do the mutation to store successor inside of R then that weak type variable gets instantiated it's finally known and that's what we used from now on so that's the value restriction。

 it's possible you've even seen it crop up in your own code before now that we've studied type inference you can appreciate why it's there As I said before O well currently implements the value restriction with weak type variables but other languages have played with different ways of enforcing it and languages continue to play around with relaxations of it because it turns out there sometimes you can get away without requiring it completely。

It's not just an Ocal thing， though， by the way， and it's not even just a functional programming thing。

 Even Java has to deal with the value restrictionsion。

 Suppose we open Jhell and create a class to represent animals。



![](img/fe0e81048cc39cfeff4310b382a16224_5.png)

And then two other types of animals， elephants and rabbits。Now let me create an array of rabbits。

So I have an array here。Its type was declared to be animal array。

 but I'm allowed to store a rabbit array in there because rabbit is a subclass of animal。

That's subtype polymorphism at work in Java。What if I tried to put an elephant in this array？

Should that code work？Well， the first element of that array is according to the type of the array。

 an animal。I just happened to stick a rabbit in there before。

So could I stick an elephant in there now？No。That compiles there's no type error there。

 Instead it gets past the type checker and to the runtime where I get an array store exception。😡。

What's that about？An array store exception is raised when you try to store something of the wrong type in an array。

Now， in this case， the array is an array of rabbits。 that's what it was created as。

 and so it can only ever hold。Objects that are of class rabbit。 Now。

 maybe you can have a subclass of rabbit。 that would be fine。

 but you can't stick something that's not a rabbit in that array。

 even if you have a reference to that array as an animal array。So Java disallows this because， hey。

 maybe someday you're like writingging a loop over that array and it's assuming every element of the array is going to be a rabbit。

 that would be violated if you allowed it to be an elephant。

You wouldn't want an elephant to sit on a rabbit。 Poor little bun bun。



![](img/fe0e81048cc39cfeff4310b382a16224_7.png)

So Java prevents this with an array store exception。

 It's really just the value restriction in another guise。We have a mutable polymorphic value。

 In this case， the mutability comes from the array。

 and the polymorphism comes from subtype polymorphism， where a class extends another class。

But it is the value restriction again， because you're not allowed to change the type of that mutable polymorphic value。

😡，Once it's become a rabbit array， it can only ever be a rabbit array。 You can't stick an elephant。

So I hope that learning about type inference and polymorphism and mutability has helped you understand not just Oaml better。

 but Java and maybe many other languages better as well。



![](img/fe0e81048cc39cfeff4310b382a16224_9.png)