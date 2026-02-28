# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P42：8_模块2 1 2 返回函数.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 2 function types， topic 1。2 returning functions。



![](img/f130ad3bc47c00293c0078195c8702f8_1.png)

Functions can also return other functions as their return value。So why would you do such a thing。

 Okay， that's a good question。 One reason to do it is if you want to make a new function。

 that's sort of a special purpose parameterizable function。

 So you want to change something about the function according to some kind of input data。

 you want to make a new function that acts differently。 This' parameterable so you can create that。

 you can have a function， create a new function， which has a different set of parameters。

 So to give you an example of of something like this。 And by the way。

 I'll admit it took me a while to think of this example。 Okay。

 so this isn't like a common thing that people do a whole heck of a lot anymore。

 But but you know I can imagine uses for it。 And it's kind of interesting to think about it。😊。

About all the things you could do once you start thinking about returning new functions that have different properties。

 Okay， so here's my example。 I want to find a distance to origin。

 I want a function that computes a distance to the origin。 So it takes a point。 X。

 Y coordinates of a point。And it returns the distance to the origin。

 so basically it's going to perform Pythagore and theorem to find the distance， right？Now。

 what if I want to be able to move the origin， right， I remember vaguely in physics， you know。

 you might want to move the origin。 Maybe I don't want it to， you know， here。

 I want it on top of the car depending on the problem， which is moving。 Who knows。

 But I might want to change the origin。 So the distance of the origin is going to change depending on what these。

 the origin is， right。So I can think of the origin。

 the location of the origin as a set of parameters to this function。

 And I would like to make a new function， a function for each different origin。

 So maybe I want a distance to origin function that assumes one origin and then another distance function that assumes a new origin。

 maybe the origin is moving for some reason。 which actually happens in physics。

 So so let's take a look at how we might do that。😊。

So a way we do it is we can make a function that defines a function and it returns a function。

 So this function is called make dis origin， right。

 and the point of this function is to create the function that I want this distance to origin function。

 So if we look down at the bottom of this function。

 you can see it says return fn right So what it's going to do is it's going to define a function inside it。

 And then it's going to return that function as its return value so。😊，They， if you。

 let's look at the go back to the top， make this to origin。 It takes several arguments。 Okay。

 the the arguments right there are O Z， O， O， X， O， Y， right， These are two floats。

Now these two floats theyre supposed to be the origin， the O stands for origin in this case。

 so the OX and O Y are the origin locations right so if I want my origin to be0 comes 0。

 those first two arguments would be00 so wherever I want my origin I pass that as arguments to this make distance origin function。

Now the return value of this make dis origin function is a function。

 and you can see that in the second line line two funk two arguments float 64， floats 64。

 returns one float 64， so the two arguments to of this return value and those two floats are going to be the x and y coordinates that whose distance we want to compute to the origin。

And then the last float 64 is the return value， which is going to be a float。

 which is the actual distance so。Just to get this straight， this make distance to origin function。

 It has two arguments， which are the X， Y coordinates of the origin。And it has a return value。

 which is a function which is going to compute the distance to that origin that we passed as arguments。

Now， if we look into the function， line 3， we have a variable called Fn。

 and that's going to be the function that we're creating。 So Fn colon equals。

 and you notice we're defying a new function。 funk X comm a Y to floats and returns to float。

And this new function that we're creating， it returns。Maath that square root。

 So compute square root is doing Pythag theorem。 math that power X minus O O X。

 right So I take the difference between the x coordinate and the origin。 the origins X。

 I square that。 And then I do the same thing。 I add that to to Y squared。

 So it's y minus its origin with a y component of the origin squared。

 And then I take the square root of that。 So that's just Pythagan theorem。

 So it does a pythag theorem and notice that it takes the X Y coordinates that you want to find whose distance you want to find from the origin。

 subtracts the X from the origins X Y from the origins Y Does Pythagore theorem。😊。

And then it returns that function， so this make disor function doesn't actually compute the Pythagorean theorem。

 it returns a function whose job it is to do Pythagorean theorem。

 to compute Pythagorean theorem to figure out the distance from an origin OX comma O Y。

So this is a function that is made special purpose this actually creates special purpose functions。

 So notice I could use this function， this make this origin function to make many functions。

 I can make one distance to origin function that computes a distance to one origin。

 and I can make another one that computes a distance to a different origin so I can make as many as I want with different origins。

😊，And so the origin is now built into the return function。Okay， so。

Now let's look at how we might use this in my main I'm going to create two functions。 I say， look。

 I want to have two origins， I want to have origin at zero comma 0 and another origin at two comma 2。

For one reason or another in my problem， I need two different origins。

 So D1 is going to be the function that computes the distance to origin 0 comma 0。

 D 2 is going to be the function that computes a distance to origin 2 comma 2。

And you can see me defining those in the first two lines。

 I just call make this origin with zero comma 0 and then two comma 2。Then the last two lines。

 the print lines， they just print they compute the distance from tube comma 2 to the origins。

The first one uses disk1， so it computes a distance from 2 comma 2 to the origin 0 comma 0。

 which is about 2。1 something。 So that's what we print out where the second one computes a distance from 2 comma 2 to origin 2 comma 2。

 which it should be0。 so that you print that out and you'd get0 for that。

 So what we've done is we made two special purpose functions by and we need we made them special purpose by giving them parameters specifically the origins the origins of the parameters that we use to make the function。

 So this is something that's kind of a cool use of returning a function。

 a function can create a new function that serves a sort of a catered a special purpose。😊，Now。

 every function has an environment。An environment is a set of all the names that are valid inside the function。

 all the variables and other things you define that you can refer to inside that function。

 So this includes all the names that are defined locally in the function。

 Any variables that you create in the function。 But also uses lexical scoping。 Go is lexically scope。

 So what that means is the variable can access the function rather can access variables that are in the that defined in the block where the function is defined。

 So in the example code down there。 We got this function fo。

 Now the variables that I have highlighted in red， those are all inside its environment。

 So let's take Z Z is defined inside fo。 So clearly it it's within fos scope。 fo environment。

 Actually， notice how I use the word scope to refer to environment。 People do that all the time。

 It's very common。 Thiss not technically correct。 I think you're supposed to use the term environment rather than scope。

 So anyway， the variable Z is defined inside fo。😊，So it's inside F's environment。

 The variable Y is a local variable to fo。 It it's one of its parameters， right。

 So that is also inside the environment of fo。 So fo can access y and Z。 Now。

 the variable X is defined in the same block as the function F is defined。

 So fo can see that variable X too。 So let's say this whole this piece of code is all defined inside another function。

 right， This variable X is defined in the same place， the same block as fo is defined。

 And so F can has access to that too。 So all those variables highlighted in red are within the environment of fo。

 All the variables that fo has access to and can can use when it's executing。😊。

So that's what environment is， and that's important when you start passing around functions as arguments。

 the environment goes along with the function。So。This is term closure。

 a closure is a function plus its environment， right together。 In fact， and goes probably。

 I think is implemented actually directly some as a struct。

 you have appointed pointed to the function and pointed to the environment and they're put together。

 So when you pass a function as an argument to another function。

 you're also passing its environment with it。 So what that means is when you eventually execute this function that you just passed。

 it still has access to its environment， the environment where it was defined。😊。



![](img/f130ad3bc47c00293c0078195c8702f8_3.png)

So what implications does this have this makes sometimes it makes figuring out the variable values kind of confusing。

 but just remember that the closure， the environment to that function goes with the function when you pass it as an argument。

So。Let's take an example This again， is a make distance to origin function。

 right Now the function that that it defines fn equals functiont that function。 That function。

 it has an environment。 and notice that O underscore x and O underscore Y are part of its environment。

 That's important they are a part of its environment。 So when you execute that function later。

 so this make distance to origin is going to return this function。 And later on。

 when that function that you return gets executed， it still has access to the same environment。

 So O underscore x and O underscore y that it had when it was defined that were passed to make this origin。

 Those variables are still accessible to this function when you call it later。

 so that's why so basically what I'm saying is it remembers these origin values。

 the O underscore x underscore y， that gets carried with the function and so when you execute the function is still using the same origin values。

 O underscore x O underscore y when it gets executed。 So that's called a closure。😊。

When you pass a function as an argument， you pass this closure。

 the function plus this environment together， they go together So and you have to remember that when you're trying to figure out how these functions get evaluated。

 where the variables are coming from， They're coming from this closure from where where it was defined。

 because that's how how go lay a scoped is slexically scoped。

 So it gets this environment from where it was defined。Thank you。

