# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p54 53_04_anonymous-functions -BV1bw4m1D7MM_p54-

In this segment， I'm going to show you a new language construct。 Ml has anonymous functions。

 These are functions you can define without using a fun binding， but to do that。

 I want to motivate why we would want such a thing。 they work very well。 They're great style。

 They're more convenient， usually when using high order functions。

 So I'm going to sneak up on this a little bit and show you a few versions before I actually get to anonymous functions。

 I have a similar example we've been using in the past。

 I have this function n times we're now very familiar with。 And then I have a use of it。

 This function， triple n times that just wants to take n and x and return3 to the n times X。

 So it calls its body is just n times with this helper function triple n and X。

 And this segment is really all about that helper function。

 And the first thing I hope at least a few of you noticed。

 is that it doesn't make a lot of sense to define this helper function up at top level。

 This is really only a helper function for triple n times。



![](img/a8f89aff072e8b6609a9fcea49e960f6_1.png)

So it would be better style unless we needed triple somewhere else in our program to define it as a local helper function like this。

 And that's the second version I want to show you。 Okay。

 so this second version is better style than the first version。😊。

But now we might go even further and we might say， you know。

 triple isn't really needed in this entire body， if we want to give things the smallest scope they need。

 we only need triple right in there。Okay， so let's try that。 This is going to look a little silly。

 but I promise you it's going to work just fine。Okay。

 what I'm going to do is right here in the first argument to n times， I'm going to put。

The entire let expression。Now let's just make sure we understand what's going on here。

 I have a call to triple n times。 I have a function。 I'm defining triple n times。 This is its body。

 It's a call to n times。 n times takes three arguments。

 The first argument is the result of this lead expression。 The second argument is N。

 the third argument is X。 So how do we evaluate this lead expression。 Well。

 what we do is we define a local function。 triple。 And then right here。

 we return from the lead expression。 The result of the lead expression is that function we define。

 And so that's what we end up passing to n times。 This works great。

 and it actually indicates fairly nicely that the only place we need this function is right here。

 All we're doing with it is passing it to n times。 So this works。 This is not good style。

 but it's only because Ml has a construct that I've never shown you。 that I'm about to。

 and that is better than using a lead expression in。😊，Strange way。

 So I really like the function is only to find right where we need it。

 I just have a better construct for it。 And that is to not give it a name at all。

 So one thing you might think you could do would be something like this。Allright，That looks great。

 I want to call n times with this function defined right here。 N and X。

 Who needs a let expression just to return the variable。 And this is the right idea。

 but this will not compile。 And the reason why it won't compile is this is a binding。

 not an expression。 What we need is some expression that represents a function that is a function as an expression。

 not as a fun binding。 So it's a little bit different syntax。 but the idea is just right here。

 So here's the difference in syntax。 The keyword is FN， not F U N。 So you get rid of the U。😊。

We do not write a name for the function。After all， we had this name triple。 we never used it。

All we did was to a function and pass it to n times in n times it's called F。

So if we don't need a name for the function， let's not give it one。 And with FN bindings。

 these function expressions， excusecus me， They're not bindings。 They're expressions。

 You cannot give a name。 These are for defining anonymous functions。

 It's actually rather clever name。 Anonyous is an English word for does not have a name or is has an unknown name。

 instead of writing equals， we write this double arrow。 It's just syndax。

 That was the choice of the people who designed Ml and then the body。 And for some clarity here。

 how about I put this in parentheses。 And now this is the version I like the most。

We now have an anonymous function defined right here。 This is the function that takes an argument。 X。

 X is not the name of the function。 It does not have a name。 It's the argument。

 and it returns three times x。 That's exactly what I want。

 I want the body of triple n times to be a call to end times with this function is the first argument and is the second X is the third。

 And so that is a sneaking up on anonymous functions and seeing what they're really great for。

 which is when you're using first class functions。 and you're only ever going to use this function in one place right here。

 So why bother giving it a name。 let's just define it right where we need it。

OkaySo let's go back to the slides and see that progression one more time and then talk a little bit more about the difference between these anonymous functions and the bindings we've been using previously。

 So we started with this version where helper function triple was defined at top level。

 I said a much better way would be to at least put it inside the definition of the function inside the body of triple n times。

 And then I said we don't need it for the entire body of triple n times。

 We only need it right in that first position。 So I move the function definition to exactly where I needed it。

😊。

![](img/a8f89aff072e8b6609a9fcea49e960f6_3.png)

Then I showed you that you cannot just get rid of the let。 You cannot put a function binding here。

 You have to put an expression。 Let expressions are expressions。 function bindings are not。

 but what we do now have new in this segment is the expression form of an anonymous function。

 And that's what we finally saw in that last version I like the most。 The syntax is very simple。

 You write Fn。 You write the argument， which can be a pattern in general， here。

 we just have one variable for the one argument。A double arrow， if you will， equal greater than s。

 and then the body of the function。 So there' is a function that takes one argument and returns three times that argument。

 There is no name for the function， just the argument。

OkaySo the most common use of anonymous functions is when we're passing an argument to a high order function。

 there's no reason to give it a name if this is the only place we're going to use it。

 but the one thing you cannot do with anonymous functions is define recursive functions。

 If you need a recursive function， then you have to use a function binding with either a lead expression or a top level。

 And that's exactly because the way we define recursive functions in M is by calling the function itself using the name of the function。

 And if our function doesn't have a name， then we don't have a way to call it recursively。

So that's pretty interesting。 Anymous functions do everything other function bindings do except recursion。

 and that is interesting because if it were not for recursion。

 then fun bindings would actually be syntactic sugar。

Let's look back again at a very simple function like fun triple X equals 3 times x。

We could have even at top level defined that as v triple。 I just want to introduce a variable triple。

 and what that variable will be bound to is this function that I've defined via an anonymous function。

That makes perfect sense。 And we could think of this first function binding as syntactic sugar for this second variable binding。

 as long as triple is not recursive。 If the body of triple itself calls triple。

 Then this unsuged version won't work because we won't have the name to do the recursive call。

 And in fact， over here in the code， I showed you， I have another example of this that I can write out real quickly。

 I could actually write triple n times the same way。

 I could make this a function that takes in one argument that matches the pattern N comma X。

 and then calls n times with。😊。

![](img/a8f89aff072e8b6609a9fcea49e960f6_5.png)

Fun why。Three times y。And and X。 Now， this de sugaring is poor style。 Okay。

 There are reasons not to do this。 It's much easier to read the function binding version。

 They happen to mean the same thing since triple n times is not recursive。

 But most people find it easier to read the function binding， which is actually shorter。

 the same way that we use and also and or else， instead of if then else。

 even though we don't need to。Anyway， the high levelve takeaway point is if you only need a function in one place。

 an anonymous function is usually the way to go， just like we don't make up variable names for intermediate computations that we only need only need once。

 we don't need to come up with names for functions that we're only going to use in one place。



![](img/a8f89aff072e8b6609a9fcea49e960f6_7.png)