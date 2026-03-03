# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p47 21_04_05_Python对象-py4e第14章第3部分.zh_en -BV1Kt421V7EE_p47-

Now I'm going to talk a little bit about object lifecycl and what we mean by object lifecycle is the act of creating and destroying these objects and I've been using this term constructor already。

 and so when we declare a variable whether it's a string or a dictionary or a party animal there we create them and then they're discarded and there's all this dynamic memory that comes and goes and we as the writers of objects have the ability to insert ourselves at the moment of object creation and at the moment of object destruction and we make special functions that we call the constructor。

 the object constructor or the class constructor and the deor and we don't actually explicitly call them。

 they're called automatically by by Python on our behalf。

And so the constructor is the most more commonly used。

 it's used to set up any initial values of variables if necessary， et cetera， et cetera。

 deors we'll cover them， but they're used very rarely。So here's a bit of code that we've got。

 it's our party animal and a lot of it is the same as what we've been doing so far so we have this variable X and the constructor has a special name。

 underscore， underscore a knit underscore again we pass in the instance of the object self and in this one all we're going to is print out that you're constructed and here's this code that we've had before and now we have underscore underscore Dell and then we pass in self and we'll just print out that we're being destructed and what the current value of X is for that particular instance。

So let's go ahead and run this。 And so again， this doesn't really do any code up to here that just defines party animal。

 but this is the constructing of it。 and basically that says， oh。

 and it really kind of creates these variables and then it also runs the constructor and so in this case this line right here is causing the ion am constructed message to come out。

 then we do and party A party and that says you know one and2 and here's an interesting thing we're actually going to destroy this variable by throwing away at an no longer points at that object and is going to point to 42 so we're going to sort of overwrite anN and put 42 in it and at that point Python's like oh this whole little object that I just created somewhere it's out here it's vaporizing it and throwing it away and so before this line completes it actually calls our deor on our behalf。

 and so that message comes out。 So we are allowed。As the builder of these objects to add these little chunks of code that says。

 I want to be involved at the moment this object is created。

 and I want to be involved at the moment that this object is destroyed。Now， in this last line。

 AN is no longer a party animal。 AN is now an integer。 It's got a 42 in it， it's gone。

 it's been created， it was used and then it was destroyed Okay。

 so you got to be careful if you overwrite something， you kind of sort of throw the object away。

So the constructor is a special block of code that's called when the object is created to set the object up。

So we can create lots of instances， everything we've done so far is we make a class and then we create one instance。

 one object， and each of these objects end up being stored in its own variable。

 we have a variable AN and we've been using it but the more interesting thing begins to happen when we have multiple instances of the same class sitting in different variables and it has its own copy of the instance variables so let's take a look at this。

So。This code here， I I've taken out the deor。And it shows a little bit more information。

 So now we're going to put two variables in here。 We're going to have a current score or whatever and a name。

 and we're going to start it out as blank。 And this time we're going to add a parameter onto the constructor and so the self comes in sort of automatically as the object is being constructed。

 but if we put a parameter on the constructor call， which is this party animal call。

 then this comes in as the Z variable and so self is the object itself。

 and Z this first parameter is whatever parameter we put here。

 Everything we've done so far has no parameter here。 but now we have a parameter here。

 and then that means that when we call this constructor。

 this line of code comes and then name is no longer blank name is going to be Sally in this particular thing and then'll say。

 oh self dot name， which will be Sally been constructed and so then then we have and that object is now constructed and we put it in the variable S and then we call the party method。

On that。 and we construct a different one。 And so this time it calls and Z is Jim。

 and we basically have a。Loops。Another copy of this。

 and so this is how it's going to look right as as it runs down here。As it runs down here。

 when this is called， it makes one instance and stores that in the variable S。

 and there's a variable X in there。 there's a name in there。

 there's an init method in party and that's all in here。

 right all that stuff is in here and now we say let's make and that's going to have Sally in there。

All right， Sally in there。And then we're going to do another constructor。

 and so it's going to make a whole new thing and it's going to store that in J。

 and this one's going to have gym in it。S party then this turns into a1。

 and then we going to call J party， that turns that into a1。

 and then S party will cause this to be a two。And so what happens is is we have now two objects。

 one in the variable S and one in the variable J， and they have separate copies of their instance variables。

 These are the instance variables or the object fields or whatever， but they're the variables。

 but the key is is that every time we do a new construction it duplicates this and there's another copy of it。

 So there's an x within S。 so S dot X is this variable and J dot X。Is that variable？Okay。

So the next thing we'll talk about is inheritance and that's the idea of taking one class and extending it to make something new。



![](img/49ad82d130aa99ead7c276d575e520cd_1.png)

![](img/49ad82d130aa99ead7c276d575e520cd_2.png)