# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P21：-021-Operators As Functions Chap2 Video 16.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we've studied functions and polymorphism， it's time to return to binary operators to see a little more about how they work。

We've already seen that we can add together two numbers with the plus operator。

 which we write as infi， it goes in between its two arguments。

If you wrap a binary operator in parentheses。It actually becomes a function。

And since it's a function， we write it as a prefixed application。

 that is the function shows up before its arguments， so I can write plus 1，2 in that way。

 and this works for any binary operator， although the one you have to be careful with is the multiplication operator。

Campbell' is like， what's going on here， I'm waiting for you to type more things。 and that's because。

Prenhesis star actually opens a comment， so El Camel pares this as thinking all of the characters to the right here are just part of a comment and it's waiting for me to close that comment。

Therefore， it's good habit when you treat operators as functions to put a space in between the parenthesis and the operator symbol itself。

Now we have a prefixed application of the multiplication operator and so honestly I should probably be writing my first application with plus there in the same way。

 sometimes I get lazy though and forget to put those extra spaces in。I can do this with any operator。

 including the Equ operator。That operator has type Alpha arrow， Alpha arrow boel。

 It is a polymorphic comparison。 It allows me to compare any to first arguments as long as they have the same type。



![](img/a00da0c835224dc8a7869a95e452f092_1.png)

So， I can compare。One to two， because these are both integers。

 but I can't compare one to false because they have different types。

 And that's true whether I'm writing that as prefix or infi， I can write one equal to。

I can write one equal false， but that won't type check。The inequalities are also polymorphic。

Less than as type Alpha arrow， Alpha arrow bo， you can compare any two values with it。

This is something to be a little careful with。Perfectly fine to use these polymorphic comparison operators to compare primitive values。

 but when we get to larger kinds of data structures。

 they aren't necessarily the right kind of comparisons to be using。

 maybe you really want to code up your own more meaningful comparison operators on bigger data structures I can define my own infi binary operators if I want to。

For example， suppose that we're working with a max function， as it turns out。

 Max has already built into the standard library of OcaMl。

 you give it any two values of the same type alpha and it gives you back the bigger one。

 according to the comparison operator。So with the max of one and two， it is， of course， two。

Suppose you wanted an inix operator for Max， you can have that。

We'll have to pick some punctuation to define it as I'm going to decide that I like。

This as an operator， in operator for maximum because it kind of looks like an arrow pointing up。

So let that operator be the max of。X and Y。Now this won't quite compile yet。

I've got a syntax error in order to define an in fixedxed binary operator。

 I actually have to wrap it in parentheses， so there's some consistency there。

Now I've got a new Infi operator and in fact Ocamll did what I should be doing and put spaces around it as well let me go back and do that just so it's a little easier to read。

And now I can use that in operator to compute Maxes so one。Max 2。Is to。

Now notice when I write it as infi， there's nohes around it， when I write it as prefix。

 as I did in the definition up here， there are parentheses around it。

The rules for how to form infi punctuation operators are a little complicated。

 they in the OCMl manual， there are certain kinds of punctuation you're allowed to use and some kinds that you're not。



![](img/a00da0c835224dc8a7869a95e452f092_3.png)