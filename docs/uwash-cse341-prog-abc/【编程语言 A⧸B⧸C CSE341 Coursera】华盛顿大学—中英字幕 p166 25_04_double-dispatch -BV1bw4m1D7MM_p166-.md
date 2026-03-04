# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p166 25_04_double-dispatch -BV1bw4m1D7MM_p166-

In this segment， we're going to make the same additions to our Ruby code that we just made to our ML code。

 and we're going to end up needing to learn an OOP programming trick called Dole Dispatch。

So remember the idea is that we want to add strings and rationals to our little language the most interesting thing is that we change addition to work on any combination of strings and rationals So we end up with nine different cases because we have an int string arerations。

 the left operaan in string and rationals the right operaan and we have nine different ways that we might need to add when we have these two values in our language values are now int or strings or rationals So in the ML code we ended up with a helper function add values where we use nested pattern matching to have those nine cases in OP it's not going to work out so well。

 so let's switch over to the code and do the easy parts first。

 let's just add a string class and aration class turns out Ruby has a standard library classes called string and rational so I'm going to call my classes my string and myration but in both cases they are subclasses of value just like int is a subclass of value these are the things that eval in our language might return and for。



![](img/35d9c7069ee5fecbcd65bff429953d70_1.png)

St most of it's pretty easy。 You're going to have an instance variable S that actually holds a string。

 The way my stringing evaluates itself is just returns the entire thing。

 That's what values always do Two string。 Just return the underlying string has zero。

 no Ne constants and so on。 And each of these method definitions corresponds exactly to some line in the ML code that was a case of a function。

 One of the branches of a pattern and here they're a method。 This is all old news。Similarly。

 my rational works the same way， we have to add the same methods。

 it's a little more sophisticated to convert a rational to a string。

 particularly nodeNeg constants can to use off the screen a bit because I removed negative constants from both the numerator and the denominator。

 but adding these methods is exactly what we learned previously on how to extend an OOP program to support new kinds of data。

The interesting thing， what this segment is all about is how to implement additions EVval method。

So this is exactly where in our ML program we call the helper function add values with the result of evaluating E1 and the result of evaluating E2。

 the two sub expressionions。 And we're going to do the same thing here。 But an OP style。

 we never call a helper function。 We say， well， these things should know how to add themselves。

 Let's just send a message。 It's call a method。 So what I'm doing is I'm recursively calling E1 do eval that will get me back some value。

 either an int a myrational or a my string。What I'm going to do is then call its add values method with E2。

 eval so that will pass at the other value and then they need to add themselves together so what I need to do is go back to int my string and myrational and add an add values method and if we were that easy this would be a pretty natural OOP thing to do but it's about to get more difficult let's go back to the slides to see why。



![](img/35d9c7069ee5fecbcd65bff429953d70_3.png)

So here's where we are。 It all starts promising。 We're going to take an O style where the way we implement eval and add is we call the add values method on E1 do eval。

 which will be some value with E2 do eval， which will be the other value。

 Those are two operaran to add values。 So now we have to implement these add values methods。

 So I'm going to go to int myering and myration and add and add values methods。

 So let's just focus on how int would do this。 So de add values， take some other V。

And it has to implement how to add itself to V。And the problem is。

 what it needs to do depends on what kind of thing V is。

 the way we add to an int V is different than how we add to a string V。

So there is a solution to this that is probably the first thing you would think of and I will show this to you。

 but you're not allowed to do it on your homework and the reason is it's too easy。

 it's not OOP enough， I'm going to show you here that it's not OOP and if you want OOP。

 I'll give you OOP right there's the OOP portion of the course so here's what you could do and it would work。

We could ask is a questions。 We could take V and we say， well V dot is a int， if it is an int。

 then I'll have a branch where I'm an int， it's an int， let's add the two ints together。

 return a new int。 Otherwise if it is a myrational。

 Well then I'll make a new myrational I'll multiply myself by the denominator and do the right arithmetic。

 Otherwise， let's assume the only other possibility is a my string。

 so we won't ask another is a question and we'll just do the correct concatenation of two strings。

So I don't mind this so much as a programming style。

 I just reject the idea that it's object oriented programming。

So what we've done here is a weird hybrid that's half OO P and half functional。

 So here I have three of my9 cases。 I'm going to have another three in the add values method of my rational and another three in the add values method of my string。

 So what have we done。We picked which ad values method to call using dynamic dispatch。

 That's what we did right here。 When ads at e1 do eval do add values。

 which of the three methods we called depends on is E1 do eval and into my string or myrational。

 That's O O P。But then in those methods， we basically switch to rackcet style programming。

 right We basically switched to a con statement where we asked the type of the other thing。

 No types in Ruby the class of the other thing。 And that's where it's a weird hybrid that we decided to do half of it OOP and then switch the other way。

 and I'd prefer you either just have your nine cases together like we did in the ML code or you do full OOP and getting full OOP to work here is going to cause you to have to scratch your head a bit。

 but we can do it。 I'm going to show you exactly how it works in this example。

So here's the idea of where we're going。That in that add values is methan in int。😡。

We needed to know what kind of thing V is to do the addition we had to know is V an ant a myrational or a my string。

So in OOP， you're never supposed to ask that question。

 you're always supposed to do the same thing instead， instead of asking what kind of thing V is。

 call a method on V and have different kinds of things implement that method differently。So。

We are going to call a method on V and have it do the addition。Now。

 what we can't do is just say V dot add values passing ourselvesself because then we're going to have the same problem。

 It's going to call us。 We're going to call it。 We're going to go in an infinite loop。 No。

 we need to call a method on V and tell it what kind of thing we are。 And that is something we know。

We know that in the int in the method in int， self is an int and the method in myration。

 It's a myrational and so on。 And we're going to tell V by calling different methods on V based on what kind of thing we are。

 And this is a programming trick called double dispatch。

 And how about a next I just show you the code。 This is not something I would expect you to come up with on your own。

 But it does work。 So we are going to add to our three value classes。

 int myration and mying add values and three other methods。



![](img/35d9c7069ee5fecbcd65bff429953d70_5.png)

So what you do in add values， this is in class int。 I'm in class int right now， is add values of V。

Calls Vs add int method with self。All right， so what I'm saying to V is you need to know how to add yourself to an int。

And then do so with me。All right， so you need to know how to add yourself to an in， do so with me。

 Let's look at what the my string class does and add values。It calls V dot add string with self。

It says V， you better know how to add yourself to a string， now do so with me。😡，And in my rational。

 we're going to have add values called V dot add rationalal with self。

So what we've done here is the call to add values that was done in the class add was the first dispatch that broke it down into you know depending on the first opera end and now we're calling three different methods。

 my rational calls add rational my string calls add string and int calls add int on V。😡。

So as long as all of our values implement add in， addd rational and add string， we'll be fine。

And if three classes all implement the same three methods， that is 9 total method definitions。

 And that is where our 9 cases for addition go in a fully OP style。 So now let's see how that works。

 I'm back up here in class int Now， And I need to implement add andt， add string and add rational。

 So now with this definition。 This method does。 is I know how to add myself。To an int V。 See。

 add int is only ever called with int objects。 In fact。

 the only place we ever call add int explicitly is right here。Okay， so if I'm an ant。

 it's an ant or both ants in do new V dot I plus I， that's where this case belongs。In class int。

 the way you add yourself to a string。😡，Is V dot S plus I dot2 S。

 Now the order here may seem flip to you。 That is because the ad class called add values on the left upper end。

Then this would have gotten called on the right opera end， so self belongs on the right。

 and that's why the order matters here because converting to strings is not commutative。Finally。

 ins addd rational。Takes in a V， which we know is irration。

 and it creates a new rational dealing with the appropriate arithmetic with myself self and V's denominator and so on。

So that is the implementation in class int in string。Right。

Stringings know how to add themselves if the other operaand is an int by converting that int to a string and then concatenating on ourselves。

 If the other thing is a string， just concatenate the two strings。

 If the other thing is the rational。 do the appropriate concatetnation。 Again。

 we're writing out the same nine cases we had in M。 We're just doing it in9 different methods。 right。

 Each of int， my rational， my string has an add int and add string and an addd rational。

 I've shown you six of those for my rational， here is the add int， Here is the add string。

 here is the add rational。 So I have shown you all nine methods。 So now we have our nine methods。

 those are the nine cases。 how is it that we're picking the right one。

 We're picking the right one in a very OP way。What we did， I'm back here in class Add now。

 is EVval did the first half of the picking。It called e1。 eval。 add values。

 and depending on what the class of e1。 eval， that's going to pick one of the three add values methods we defined。

 there's an add values in ant in mying and in myrational。Then， those three methods。Pict。😡。

The second half of it and pick the right one of the nine methods we implemented by calling either a in ad rational or ad string and passing self。

And that is double dispatch Okay， so here's a slide summarizing things。 Remember。

 we have these three classes that each define the same three methods， So we have nine total methods。

 one for each case。 and now we just need to use dynamic dispatch to pick the right one。



![](img/35d9c7069ee5fecbcd65bff429953d70_7.png)

So when add's eval method calls e1 do eval do add values of E2 do eval。

 that will dispatch to either ins add values， my stringings add values or my rationals add values。

 aren me。What those methods do， they always take in an argument V an int calls V dot int add int of self that's going to pick one of our nine choices。

 or my string calls V dot add string with self that'll pick a different of our nine choices and my rational call V dot a rationalal of self and that will pick the right one of our nine choices and so we did things in two steps and that's why it's called double dispatch if you want to see a language it can do this all in one step。

 watch the next optional segment but in most object oriented programming languages you have to do this trick if you really want to program up a binary operation like our addition in an object oriented programming style。

So that's what you'll need to do on your homework， port ML code to Ruby code。

 we give you lots of pointers to get you set in the right direction。

 and you might be wondering why on Earth am I showing you how to program like this？Well。

 to be honest， partly it's to belittle people's full commitment to OOP I don't find this particularly natural or a simple way to program up a simple thing。

 I think the ML code is simple， I think you should program like this with nine easy to read cases altogether。

 but if you want OOP， this is how you get OOP。There's more to it than that。

 I also want you to understand dynamic dispatch， understand the semantics of method lookup。

 and one way to really force you to understand that is make you use a sophisticated idiom where you really have to think about how the dynamic dispatch is working。

I think it makes for a nice homework and it contrasts with the next segment where I show you how a different language construct could make this much easier。

And finally， I do have the Java code that does the corresponding thing that is optional。

 but I do find it interesting， particularly because the types make it a bit clearer what's going on。

 So in Java， you have to say that your class value， which is what int rational and string extend。

 has these methods。😡。

![](img/35d9c7069ee5fecbcd65bff429953d70_9.png)

And what add values does is it takes another value and returns a value。

 whereas a an a string and ad rational know more about the type of their argument。

 they know the other argument is an itt or isn't mying or is a myrational。

 I could call it rational and Java。 And so if you do know Java。

 you may find this idiom a bit easier to understand by working through the Java code。

 which is exactly like the Ruby code once you get down into the classes。

 but has the additional type declarations to help explain what's going on。

And that is double dispatch。

![](img/35d9c7069ee5fecbcd65bff429953d70_11.png)