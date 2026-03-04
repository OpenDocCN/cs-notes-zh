# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p73 3_PHP中的面向对象库.zh_en -BV1Lr421A75d_p73-

![](img/0bf08dd6bfbaad60f56ab61f61600cda_0.png)

![](img/0bf08dd6bfbaad60f56ab61f61600cda_1.png)

So now that I've showed you a little bit about how you might construct an object。 I mean。

 the person one isn't all that amazing。 but you get some of the mechanisms of it。

 I think it's going to help as you want to read documentation。 So to review。

 we're going to see two new operators。 The one we've seen already is the thing that basically says within。

 So I'm looking for the function name format within the object name Z， right。

 and the same is true for variable like Do Colleen。

First name that's the first name variable within the Colleen object。 That's the within。

 I think of that as within。Okay。It turns out there are things that are in classes that we can access。

 So even though there are templates， there's certain code that's so static， it doesn't change。

 And so it's not dynamic。 And so we can say， you know what， I want to pull the code。

 I just want to pull that code out from that template and run that code。

 The key we'll see in a second when you're doing a static item。 There is no dollar this。

So this is the class。And this is object。So some things can only be run in when there's an object that's been populated。

 but some things are really simple。 It's a way I like putting old library code。 And in this case。

 it's a constant。 So date time， Col and colon RF 822。

 So that says there's a thing that statically defined inside of date time。 pullll it out。

 I want to use it。 It'll be easier when weve see an example。 So this is within a statically within。

 So this is。Let me just draw this better。This is within。Object。And this is。Within。Class。

This is static。And this is a dynamic。Meaning it's got to be in an instance or an object Okay。

 so here we're looking at some object oriented documentation， right？



![](img/0bf08dd6bfbaad60f56ab61f61600cda_3.png)

So you have constants in there and in this case these are just statically defined constants and you say。

 hey， I would like the RF 822 variable constant， which is this guy right here inside of date time and so that's how you pull this string now these are just different date formats that you're going to need for different situations of formatting dates okay so that's one thing Conss within classes that's what you need to know and you need to know how to use those。

Then there are some special methods inside the class and we'll talk specifically about constructing。

 but you don't see a thing that shows the documentation for what you're allowed to do in all these。

 the creation， the new operation。Somebody might argue that this should have been called new。

Say like under under new that says when I'm running new， this is it。

 but you just have to equate new with construct because the construction of an object is kind of the generic00 notion of take the template。

 make an instance right？ And so this is that's the act of constructing。

 And so new is the operator that caused the constructing to happen。

But when you're reading the documentation， you have to go read and find the underscore underscore construct to tell you what you're allowed to do in those parentheses。

 And so what this really says here。Is is really just a function call。 It's saying this is optional。

 right， These are two optional parameters。 The first optional parameter is when。And that's optional。

 And if you don't specify it， that means the default is now。

 And then the second parameter is a time zone。 But I haven't got it in any one of these things。

 So I assume it's the current time zone。 that's the server's time zone。

 And so you can read and understand what you're allowed to do on the new calls by looking for the underscore underscore construct method。

 Oh， and look at that right here。 It says methods。An hour ago， you didn't know what a method was。

 Now， you do know what a method is。 It's a bit of code that lives inside of a class and instances of that object。

Okay， so sometimes we have static methods and theyre methods that we can access from the class itself。

 So here's an object X equals new date time that's making a regular object。 but this get last errors。

 if we read the documentation， it says static here， and that means it doesn't depend on this。

 that's the dollar this。But it also means that you can just call it and call the class directly。

 so we're saying， go into the datetime class and call the get last errors function。Okay。

 and so that's what this colon colon is It says go into the class and get that code。

 And this is a way in this case to go get the errors that might have happened upon constructing。

 because when you're constructing using a new， it either gives you back good stuff or an empty thing。

 If you want to see the errors went wrong， you got to call the class and say， hey class。

 last time you were constructing what errors might you have encountered。Now， a normal variable。

 the normal method is doesn't have the word static in it。 And so that we've sort of done。

 we make a new class。 we have the class， and we're going to access this format method deep inside the class。

 And so that's inside the class。 So this， I mean this is inside the object。

 Z is an object and format is a method inside the object。

 So that you'll see most of the things are not static。 you know， you got one static， one static。

 most of things here are just dynamic。 And that means the only way you can access them is with the error arrow notation that's within。

Now， there's a whole bunch of things that are really very cool。

 and it has to do with the fact that PhP came to the object oriented pattern late so they were able to take and look at all the other languages that I talked about a few lectures back and steal all the best stuff。

 And so you see these things that have to do with underscore。

 and they have to do with sort of the lifecycl of objects， which we'll talk about in a bit。

 But in some ways， there's a lot of really cool stuff。

 And like this wake up is when something comes out of the session back into PhP。

 we don't even to talk about the session yet， this method gets called。

 So you can build an object that asks to be called and consulted at the moment that it's being reloaded and woke back up into memory。

 So up next we'll talk in some more detail about what I just got done talking about。

 And that is the lifecycl of the objects。

![](img/0bf08dd6bfbaad60f56ab61f61600cda_5.png)