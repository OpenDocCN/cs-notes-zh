# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P19：-019-Partial Application Chap2 Video 14.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， a feature of Ocal called partialial application that's really cool and might be very different from something you've seen in other programming languages。

Let's write a function add， let add X Y equal x plus y。Very simple。

 just adds its two arguments together。I could add two together with three and get five。I could also。

Partially apply add。Apply it to only one of its arguments， the first argument。

That gets me back a function。You can tell it's a function because of Utop's output。

 it says that's a function value whose type is int arrow int。Of course。

 Ad's original type was int arrow int， arrow int， it took in two integers。

Now it's down to taking just in one integer。 What we've done is partially applied add to the first argument of two。

 and that produces a function that will just add two to whatever argument you pass in next。

So I could take add two and apply it to three and get five。Okay。

 notice what the parentheses are doing there。 they're grouping the add and the two together and forming a function。

A partially applied function that I can then apply to the next argument。

It might be a little easier to understand this if I break it down into a couple steps。

 I could define the Add2 function， just call it Add2 as the result of applying the add function to the argument2。

Now add to， anything I apply it to is going to add two to the argument。

 apply it to zero and you get two。Apply add2 to 10 and you get 12。

And so that's why when I said add two up there above with three。I got five as a result。

And now to explain why partial application actually works。

 I have to confess to you that I have been telling you a lie。

That lie is that Ocal has multi argumentgu functions。In truth， it does not。

All things that look like multi argumentgu functions in Ocaml are really just syntactic sugar for single argument functions。

Fun X Y R E is really just syntactic sugar for fun Xarrow fun Y LOE。

Where we've de sugaruged that multi argumentgu function into a series of single argument functions。

Add X， Y， as we wrote in our previous example， is therefore really sugar for let add equal。

An anonymous function that takes in a single argument X and returns a function。

That function is an anonymous function that takes in a single argument Y and returns x plus y。

And of course， this generalizes to any number of arguments， you could have three arguments。

 four arguments， whatever you want， it just decomposes into a series of nested， anonymous functions。

This really is just a consequence and made possible by our design decision before that functions are values。

 We can use them anywhere。 We use values。 Funs can take other functions as arguments。

 and they can return other functions as results。We're making use of that returning a function as a result in partial application。

We partially apply the function and get a result back which just another function。

This is an incredibly powerful language feature。 It is one of the hallmarks of functional programming。

😊。

![](img/e093aafa98f3f2844647a280b956fc8a_1.png)

![](img/e093aafa98f3f2844647a280b956fc8a_2.png)