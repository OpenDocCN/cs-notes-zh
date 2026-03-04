# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p36 35_PHP函数.zh_en -BV1Lr421A75d_p36-

![](img/161d268f65aabb177c6a7fd28d6ce0f0_0.png)

![](img/161d268f65aabb177c6a7fd28d6ce0f0_1.png)

So now we're going to talk about writing functions and how we can break functionality into multiple files。

We need to learn about functions partly because we're going to write them。

 but mostly because we're going to use them and PhP is a less object orient programming language than some are and so we use functions all the time but we write our own functions as well we're going to cover both of those things a lot of times programming initial programming tells you you're supposed to write functions for everything I'm not such a fan of writing functions until you feel the need if function is a great way to see this work that you're going to do over and over and maybe change a little tiny thing that's when it's time to do a function when you're say know I'm doing the same thing over and over and over and don't repeat yourself you make it work once sometimes with parameters and then do that over and over again。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_3.png)

![](img/161d268f65aabb177c6a7fd28d6ce0f0_4.png)

![](img/161d268f65aabb177c6a7fd28d6ce0f0_5.png)

![](img/161d268f65aabb177c6a7fd28d6ce0f0_6.png)

Now。I find that I actually have an offline documentation viewer for PhP because I don't memorize all the functions and there are so many functions。

 So for example， I never know what the replace function is for PhP I know that I got a string and I got to replace something in it so I'm like well is that replace function again so I typed that into Google over and over and over Google is my best friend when I'm coding a PhP Now once I've been in PhP for a day or two then I kind of remember the main things but the documentation that they have online for PhP is outstanding and very good at getting you what you need the other thing that's really cool is if you scroll down on these pages you'll often find sample code that the users have provided and so the PhP documentation is great but you can also download case you're on an airplane or don't have a good network connection you can download a PhP documentation viewer and so that's quite useful。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_8.png)

![](img/161d268f65aabb177c6a7fd28d6ce0f0_9.png)

So here's a couple of samples of functions that we're going to use。 These are string functions。

 Strs are not objects oriented in PhP。 and so we sort of follow the pattern of passing a function in and getting a function back。

 And so this is the stir rev and PP is pretty good at prefixing all these with STR is a way to tell you that they're about strings。

 So this is reversing why you need to reversing， I don't really use it， but there you go。

 it's very exciting because it reverses the thing。 stir repeat why we want to do this I don't know。

 but we're passing in a string and saying repeat it twice。 I put a space here So it's hip hip。

Translating something to uppercase that I do do all the time， Hooray and Stlin。

 which is how long the string is， so that's just an example of some of the string functions that you might use。

To define your own function， we use the keyword function， followed by the name of the function。

 followed by optional parameters， followed by curly brace， and of course。

 there can be further indenting and further curly brushes that going on here。

 And then this is the body of the function。 and like in all function situations。

This code is not executing。 It's being remembered and effectively expanding the language with a new。

Keyword。So it copies all this into greet somewhere。 And that's kind of like a variable name。

 as it were。 And then you can call it。 So this function is defined once。And then invoke twice。

 so it runs it， goes up and runs it， comes back down， runs it again， so it runs twice， run， run。

 so there's no output from this because that's the definition of it。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_11.png)

You can choose function names， they don't start with a dollar sign You can start it with the underscore again。

 we tend to reserve underscore for sort of library like things don't we tend to avoid underscores in our main code。

 You can start with the letter underscore letters and numbers so it's pretty much the same avoid built in function names the case does matter。

 but I think it's a mistake to treat the function called you know Zap。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_13.png)

And zap differently， so don't take advantage of that， but it does matter why I don't know。

Return values， much like C based languages， use the return keyword。

 And so it basically says if this function gets called in the evaluation of an expression。

 So in this case， it's a concatenating whatever the function greeting returns with the string gl。

 And so it comes in， it returns it。 And so this expression here becomes the residual value that is in that expression。

 So it just means that once greeting runs， hello is here。And then this concatenation runs。

 and then that goes hello Glen， and then it runs again， greeting returns， and it's hello Sally。

 So the concatenation thing is hello Sally。You can also pass parameters in。

Pramers have the dollar sign， the function name doesn't have a dollar sign， but the parameters do。

 and like all parameters and functions。The normal thing is that they are sort of temporary copy of the incoming and that dollar lay only exists while the function is running。

 And so in this case， we're going to do this concatenation of howdy Es to Glen So howy starts running。

 So E is somewhere out here and layng points to Es then this code starts and so now。That instance。

 that execution of the function， we're going to see Spanish return Ola。

 then it's going to be done and then the next time。It runs it again， and in this case。

 FR is out here and laying points to FR and runs again。 That's false， but this is true。

 So it returns bojoure， and so we get the residual value here。

 goes back here and we cancatetennate that bojuur Sally。Okay。

 so this variable is effectively an alias。Another really elegant bit of PhP that I really like is the concept of optional arguments。

 and if you put an assignment statement here in the function definition。

 this becomes the default value。So in this case， if you don't specify it。

 then it assumes Es as the value for Lng， if you specify it， then it points to FR and runs again。

 so that's a default， I think it's as beautiful and elegant a syntax for defining the default of an argument as any programming language。

This is emphasizing the fact that sort of this variable alias only lives inside the function。

 and it's an alias of the original value。 So we have value equals 10。

 And so there's dollar Val out here。In the outside world and has a 10 in it。Okay。

 and then we pass v into the function。 So the interesting thing is the way this really sort of works is it kind of makes a copy of the 10 over here。

And then it points alias to it， meaningan alias is not pointing at that 10。

 It's pointing at that copy。 So now I can actually change it。 So I say alias equals alias times 2。

 So that puts a 20 in， and that puts a 20 in here。 So there's a 20 in this little place。

 but there's no 20 here。 This is separate。 So it kind of keeps it separate。

 It it really isolates firewall， stove pipes。 It keeps this function from messing with things outside of itself。

 including its arguments， its parameters。 So there's this is called copy。

So the parameters are copied rather than actually referenced Okay， so in this case。

 if we have v equals 10， we pass it in and we see this DV， which is the return variable， so DV is 20。

 but the original variable came back out of that， which is unchanged。Call by value。Now。

 lots of programming languages that you use are called by value。

 although some programming language kind of like if it's an array。

 it's called by reference and if it's a scale or， it's called by value。But。😡。

PHP gives us a call by reference capability。To say that we don't want this parameter to be an alias。

 we want it to point to the original， And we do that by simply adding a little ampersand。

 So the function， in effect， declares its intent to be able to modify that。

 There's nothing we change in the calling sequence。

 So what happens here is there's a dollar vow out here。And then we stick a 10 in it。10 in it。

 And then we call it triple。 And then this says， instead of making a copy。

 real thing is a second alias to that variable。 So when I am going to multiply it by 3。

10 times 3 is 30。And I put 30 in the real thing， I'm really changing this variable。

 this variable is outside the scope of this function。So we sort of have a wall around the function。

 oops， but there's a little tiny break in the wall， a little tiny doorway in the wall。

 and we're going out and changing this variable。 We can't like sneak into other things。

 but we can touch the actual contents of the value。 So that's called call by reference。

 because this actually refers to the original variable rather than previous example。

 it's call by value， which means we're getting a copy and we're getting the value in the variable。

 We're not getting a reference to the variable itself。 And so when we come back。

We're printing out the 30 because it's been triple Call by reference。

 That's a kind of a more advanced concept。A lot of languages don't even have that。

 the Ampersand came from C。 that's how C used to do it。

 The syntax for call by reference is a little bit different because you don't have variables that start with dollar sign。

And actually how you use it inside the functional liver， but this's not a C class， it's a PhP class。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_15.png)

Now the reason this is important is as you read documentation。

 you can read through the documentation and you find if you see this ampersand， you're like， oh。

 that's interesting， that means this ampersand means it's going to change the array。

And the interesting thing is， if you pass an array in to a function， the default is to call by value。

 and actually that's different in a lot of languages， meaning it's a copy。 but if you say Ampersand。

 then it's an actually call by reference， and you can decide that this function inside this sort function is going to do something to the array。

In some languages， you actually return the new array in this。

 you're going to sort it and sort it right there。 and so it just is a reference。

 and so you've got to be able to read when you see that， see that epic like beep beep， beep， beep。

 they're going to change that when you pass an array in。



![](img/161d268f65aabb177c6a7fd28d6ce0f0_17.png)

It's going to take and change it， so just you need to know what that ammp percent is just so you can read the documentation。

So up next， we're going to talk about variable scope。

 we've been talked about things that can be inside the function and then outside the function。

 and that's what we're going to talk about next。

![](img/161d268f65aabb177c6a7fd28d6ce0f0_19.png)