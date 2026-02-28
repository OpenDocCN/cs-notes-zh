# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P41：7_模块2 1 1 一等值.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 2 function types， topic 1。1 first class values。



![](img/d8f7942dd734e0cdd7a7337b53a1da49_1.png)

So we've been talking about functions in this class already。

 you can't really program and go without using function。

 So you've always got to have at least the main function。

 and we've had that in all the examples that we've used。

 But what we're going to talk about now is the ways in which go allows you to treat a function as a first class value。

 So there's this term first class value， treating functions as first class values and it's associated with functional programming functional programming。

Is a way of programming a programming paradigm， Let's say that is different than what people usually use。

 Let's say。 So if you've ever programmed in scheme or something like that。

 that's a functional programming language。Ml， there are a bunch of these languages。

 And so it's a different way of thinking。 and we're not going to really do a lot of programming。

 a lot of functional programming。 but there are some features of functional programming that can be very useful。

 So go implements some of these features and we'll talk about how to use those。

So treating a function as a first class value generally means being able to treat a function like any other type。

 like an integer， a string， a float， all the things that you can do to one of those types。

 you can also do to a function。So as an example， variables can be declared to be a function type。

 so you can always declare a variable to be an integer type， a floating point type， things like that。

 you can also declare it to be a function type。😊，And you can then set a variable equal to a function。

You can create them dynamically， so in your code。You can create an integer on the fly， right。

 You just in the middle of your code， you can create a new variable。

 know x colon equal whatever and x colon equal 3， whatever。

 And that creates an integer on the fly at runtime while you're running the code。

 So that's creating a variable dynamically， creating some type dynamically。

 You can do that with functions， too。 Now， up until this point， we haven't done that。

 We create them statically。 just at the top level， you say funk main or something like that。

 But we want to be able to create them dynamically too。 Sometimes that's very useful。

 So inside a function， you can create a new function right inside。😊。

Functions can be pass as arguments to other functions and returned as values from other functions。

 So just like an integer flow to something like that， you can pass it as an argument。

 you can pass a function as an argument to a function or a function can return a new function as as its return value。

Also， it can be stored as a data structure in a data structure。 so you can have a data structure。

 maybe a slice。 you can have a slice of integers or something like that。

 You can also have a slice of floats。 So in all these ways。

 Going is going to allow us to treat a function as a just like a regular type。

So let's talk about how to implement these things and go start off with variables as functions。

One thing you'd like to be able to do sometimes is declare a variable as a function。

 So the variable basically acts as an alias， Another name for that function。 in this case。

 if we do this the way we're doing it right here。So。😊，If you look at the example code。See in red。

 we got that variable that we're declaring right at the top called funk var。

 and that is going to be my new variable that I'm declaring to be a function type。

 So if you look at the top line， var funk var， and then to the right of it。 I give its type。 I mean。

 that's how you do it。 So that's how you declare variables of certain type。 you say var funk var。

 Let's say I want it to be an integer。 I'd say var funk var int。 So now I want it to be a function。

 So I say var funk var funk， and I give the argument type integer， and I give its return type。

 So that right there funk int and parenthees and then int to the right of funk var。

 you'd call that a signature， a function signature。

 And so you have to put that to the right of the the variable name in the declaration。

So that first line just declares a new variable called funva。

 which will be able to be assigned to a function。 Now， then right after that， I declare function。

Ink function， ink F N， and it just does increment， right， It takes an X， It takes a value X。

 and it increments。 It returns x plus 1。 So it's just a function。 Now in the main。First thing I do。

 as I say funk var equals ink fn。 So right there， I am assigning funk var to be that function ink Fn。

 Now， notice in that assignment there， I don't put the parentheses to the right of ink fn。

 So normally when when you write a function when you call a function。

 youd put parenthees open print close to the right of it。 So if I wanted to call ink fn。

 I'd say ink fn print close put put some parameters inside the parentheses but that's how you call it。

 you put those parentheses。 We are not calling it here all we're doing is we' saying funk var is basically a points it to the same function to ink fn。

 So we just do an assignment just as shown And then once I've done that。

 I can use funk var just the same as I would use that function name。

 So you can look at the last line。 I'm doing a print。

 I'd say print funk var 1 that's the same as saying print ink fn1 pass one to the function。

 It executes it increments it， it should print out a2 So in this way the variable is now can be assigned directly to a function。

 So this is。😊，Treating a function as a first class object。

Functions can also be passed as arguments to other functions。So you can see that here。

 I got this function calledApp it， and all it's supposed to do is apply a function to an integer。

So it takes two arguments， my function apply it。 The first argument is a function。

 I call it a functiont and its type is takes an integer and returns the integer。

 The second argument is a value which I'm calling an integer and the whole point of this function this whole function apply it should basically take that function of this argument that is its argument。

 apply that to the v argument and it should return an integer and if you look at what the function does in between the curly bracket it all you have is return a functiont vow so it takes whatever that function is that you pass passes the value to that function and returns its return value。

So in this way， we're passing a function as an argument to another function。

 which is useful sometimes and we'll talk about that。So。Here's sort of a bigger example。

 a slightly bigger example where we're passing a function as an argument。 Again， at the top。

 we've got that apply it that I told you about， right。

 So we're just going show how how you might use such such a function。 So apply it is a function。

 It takes a function as an argument， and it applies the argument function to the other argument。

 the vow argument。Now， then right after I define that， I define two other functions。

 an ink function and a deck function， increment， decrant functions。

 and they do what you would expect， return x plus1， return x minus1。

So we got those two functions then we look at the main and there are two print statements。

 I call apply it both times， apply it with the ink function as the argument and then apply it with the deck function。

 So when I call apply it with the ink function， the other argument is two right so an ink function should increment that so it should print out a three。

And then the next print the next print statement says calls apply it with the deck function。

 decrement function， it passes it a two， so it should return a one and so one should get printed so if you run this code。

 you should get a three and a one。Anonymous functions。

 So anonymous functions are basically functions without a name。

 So you don't actually need to name a function if you don't want to。 Now。

 it is usually very useful to name functions。 If you want to call them， you need a name for them。

 right But if you're going to pass a function as an argument to another function。

 often you don't need to give it an explicit name。 So you saw on the last slide。

 set last slide just now。 I had this ink function and deck function。

And I gave them names and I passed them to my apply it function。

 but can I don't have to actually give them names in order to pass them as arguments。

 I can just make the function right there in the call。

 they call this Lada calculus this is a Lada and it comes from Lambda calculus but we won't use those terms。

 but that's a math term to people where this actually came from because these ideas of passing these functions around came from Lambda calculus。

A long time ago。 But if we look at the function。

![](img/d8f7942dd734e0cdd7a7337b53a1da49_3.png)

We still got the same apply it。 But if you look at the main， I call apply it。

 and the first argument is a function definition So without a name， there's no name for it。

 but it is otherwise a function definition。 So I have it highlighted in redk takes x integer as an argument。

 returns it int and in curly brackets， return x plus1。 So that's the increment function。

 but I never gave it the name ink function。 I don't have to。 I just define the function right there。

 Def it without a name。 So it is now called it an anonymous function。

 and I can just pass it directly to apply it。 and I didn't really need the name'll apply it will just apply that function。

 the name names are more useful。 if you're gonna call this function directly in your code。

 you want a name to associate with it。 but in a case like this， you don't need a name。

 you can just make the function and just pass it as an argument。Thank you。

