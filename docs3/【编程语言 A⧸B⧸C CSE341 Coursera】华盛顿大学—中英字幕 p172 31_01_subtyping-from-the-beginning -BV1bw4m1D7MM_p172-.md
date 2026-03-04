# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p172 31_01_subtyping-from-the-beginning -BV1bw4m1D7MM_p172-

This is the first of several segments where we will study subtyping。

 which we've mentioned only briefly so far when considering interfaces and I want to do this to build up the key ideas from first principles。

 to maybe the last major topic of the course and I think it really finishes our foundation of the main ideas that we use to create programming languages。

 I'm going to do this all in pseudocode， you're only going to see PowerPoin slides because we don't have time for another programming language and even if we did real programming languages always handle subtyping in a more complicated way。

 then the core ideas underneath what's in actual languages。

 So I'm going to show just subtyping first， then after we understand subtyping using just PowerPoint。

 then we can relate it back to some important questions like how statically typed object oriented programming languages use subtyping how subtyping relates to the generics and polymorphism we saw in M。

 how they have complementary。

![](img/0ff00c92a4f7e169109068a3f2a63c8c_1.png)

And in fact， at the very end， how you can combine them to get something that's actually greater than the sum of the parts。

 So we're going to start from the beginning。 We'll get all to that later。

 And what we're going to do is cover most of the ideas by just imagining a small language that will have functions and addition and arithmetic and all that。

 But the key thing it is going to have is records。 Those were those things in M that had fields and contents。

 They are a lot like objects。 If objects only had instance variables， but not methods。

 But we're going to make those fields mutable。 so a record is something with mutable fields。

 You can get the fields， you can set the fields。😊。

![](img/0ff00c92a4f7e169109068a3f2a63c8c_3.png)

We will make up our own syntax because none of the languages we have studied would be appropriate。

 M has records。 so our syntax will be most like M， but it doesn't have subtyping。

 So I would confuse you if I used actual M。 and it doest not have mutable fields。

 fields are immutable in M Ra and Ruy are dynamically type languages。

 and this is all about static typing。 So that would be weird。 And even if we all knew Java。

 which we don't。 it uses class names as types and I don't want to do that for understanding what subtyping is really about。

 So I have to take a little bit here to just explain to you my language。

 So here are records in my language。 There are three constructs related to records。

 The first one creates records。 So this one actually does look just like M。 you write curly braces。

 you write a field name， equal and expression。 You separate those by commas。

 So the Fs here are just names of fields like fo bar X， whatever。 and the。



![](img/0ff00c92a4f7e169109068a3f2a63c8c_5.png)

These are expressions， and the semantics of this syntax is evaluate each of the expressions to values。

 then return a record value that has all of these fields holding the contents of the results of the expressions。

That is exactly like an M。 The second concept we have is field access。 So if you write E dot F。

 what that means is evaluate E to a record to a value V assuming assuming that it's a record that has an F field retrieve the contents of that field。

 Otherwise， it would be an error。 but in fact， our type system is going to make sure that that never happens that E。

 in fact， if type checking succeeds is always a record that has an F field。

 So E dot F just retrieves the contents of that field in M， we actually wrote this hash F space E。

 but E do F is much more common in programming languages。 it looks more like a ruby getter。

 So I'll write E dot F。😊，Lastly， we have record field update here we write E1。f equals E2。

We evaluate E1 to a record with an F field just like we did for accessing。

 but now we update the contents of that field to be the result of evaluating E2。

 So the semantics are evaluate E1 and E2 to values。 E1 should be a record with an F field。 update。

 mutate its F field to hold E2。So that is our syndax and our operational semantics for records。

 because we're studying typing， we also have typing rules。



![](img/0ff00c92a4f7e169109068a3f2a63c8c_7.png)

So it turns out we have a special kind of type for records。And this also just looks like an M。

 So we write curly braces， field names， colons and the types。

 So this record type says this describes records that have a field F1 holding type T1。

 a field F2 holding type T2 up to a field Fn holding type T in。

 So every record in our language will have some type that looks like this。

 if it has an X that holds an int。 and Y that holds a string。

 then the record type would be X colon int， Y colon string。Now that we have these types。

 we can use them to have type checking rules for the three kinds of expressions I showed you on the previous slide。

Let's do each of them in order。 So the way you type check a record creation function is you give it a record type that has all the same field names。

 And field1 has type T 1。 If E1 has type T and field 2 has type T 2， if E2 has type T2 and so on。

That much is， again， like an ML for accessing the contents of a field。

If E has a record type containing a field F that has type T。

 then E dot F has type T so E has some record type。

 that record type tells you the type of the F field that is the type of the record access expression E do F。

If there is no F field in the type of E， then this shouldn't type check。

 and that's exactly how the type checker prevents reading fields that are not in records。

 which would be a runtime error， we're going to prevent those errors with our type system。

And finally， record update works basically the same way。 the way you type check E1 do F equal E2。

 you make sure that E1。Has a record type that includes an F field and whatever the type of that F field is。

 E2 better have that type so that when you update the contents， the record still has the same type。

Okay， so those are our typing rules。

![](img/0ff00c92a4f7e169109068a3f2a63c8c_9.png)

So let's put it together with a small example that will mostly look like ML。

 but this is really pseudocode， you couldn't type this in because it uses this dot notation。

 which is not ML。So here's a little program where a function dis the origin takes in a point as an argument。

 so we're not doing anything OOP here。 there's no method called this is a function。

 It takes in an argument P， and that argument has to have type x colon real， Y colon re。

 a point with an x coordinate and a y coordinate and the body of this function returns the square root of p dot x times p X plus p dot y times p dot y。

 so we get the contents of the x field of P。 we get it again， we multiply those together。

 we get the y field twice and so on。So we could use this function by calling it dis the origin with some argument like pag。

 which is a variable of type x colon real y colon real。

 and it can have that type because this record expression x equals 3。0 y equals 4。

0 would have type x colon real y colon real so this all works you make the call the dis the origin disor returns something of type real because that's the return type of math dot square root and we would presumably get the value like 5。

0 because the square root of 3 squared plus 4 squared is 5。So this is using our language。

 and this should all type check。 We haven't seen any subtyping yet。

 We're finally ready to motivate some subtyping。Let's look at this slightly different example。



![](img/0ff00c92a4f7e169109068a3f2a63c8c_11.png)

In this code example， it's exactly like what I had before。Except。This I'm calling disk origin with C。

 where C is this color point that has a X colon real， Y colon real and color colon string。

 And C can have that type because the record that it is bound to has an X field that holds a real。

 a Y field that holds a real and a color field that holds a string。😊，But now。

 in the language as I've described it so far， this function call should not type check because when you have a function that expects an argument of a certain type。

 you have to pass an argument of that type。And this the origin expects an x colon real Y colon real。

 and C is an X colon real Y colon real color colon string。 If they're not the same type。

 the function call doesn't type check。But we would like this to type check。

 There's nothing wrong going on here。 C just has a type that has some more fields， some extra fields。

 It's not going to bother disk origin that there is a color field。

So we would like to make our type system more flexible， such that this function called T checks。

 just like you see here on the slide。And that's a good idea。

 and the easiest way to do that is to add subtyping into your language。



![](img/0ff00c92a4f7e169109068a3f2a63c8c_13.png)

So this is a fairly natural idea， which is that if you have some record type。

So some expression in your language has some record type with some fields F1 of type T1。

 F2 of type T2 up to FN of type TN。Then let's let it also have that type with some of the fields removed。

So if you have an x colon real Y colon real color colon string， let that also have type X colon real。

 Y colon real。And that's what we need to make code like this type check。

 I have a different example here to emphasize that we with this rule。

 it's not just that we can take C and call dis to origin with it like I wanted to on the previous slide。

 we could also call another function that just requires its argument to have type color colon string。

 a record that only has one field color in that case。

 it's fine that it also has an X field and a Y field and maybe make purple updates the record so that its color field is now purple it would be perfectly fine to pass C to that function。

 and then after we called it a C would not be a green point anymore， it would be a purple point。

 So if we want these things to type check， we need a type system that allows this sort of you can forget fields and as we'll see in the next segment subtyping is a very elegant way to add this kind of flexibility to your type。



![](img/0ff00c92a4f7e169109068a3f2a63c8c_15.png)

system。