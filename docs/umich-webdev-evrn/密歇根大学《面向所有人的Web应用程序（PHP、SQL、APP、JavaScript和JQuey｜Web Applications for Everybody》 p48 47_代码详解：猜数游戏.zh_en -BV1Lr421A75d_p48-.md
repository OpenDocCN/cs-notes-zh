# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p48 47_代码详解：猜数游戏.zh_en -BV1Lr421A75d_p48-

Okay， so welcome again to Web applications for everybody。

 we're doing a bit of code walk through right now we're on talking about the forms topic。

And so what I want to talk about is this model view controller pattern。

 but I'm to start with some code that sort of I've used before this guess code， guess do PhHP。

 where we're supposed to guess play a guessing game， guess equals 14， it's oops。

 I did a minus sign there。

![](img/77eb364cf79ccf0bfe9380087c3af294_1.png)

Guess is too low。 So I want to take a look at this code。

 And so this is kind of a typical crude basic PP script， a bit disorganized。

 It starts with some Hm because that's what they are。

 It's a template and it drops into Pp and then does some logic and then puts a bunch of echo statements and what it does do well is it's structure overall top to bottom is not what I like。

 And I'll show you in a second。 how I want to restructure it。

 but it does do a pretty good job of checking to see if there's a guess parameter and complaining if there's not checking to see if the guess is too short。

 this is all input validation that's doing a pretty good job of in my next application。

 I'll have it better structured， but I won't do this validation。

 And then I once I know by the time it gets to here。

 I know that I've got at least s data and it's a number。's not it's the right length and it exists。

 And then I can say if it's too low or too high。 And otherwise if it's equal then I say congratulations。

 So this is nice little error checking here and I structure with Els。 I like that。

 But the fact that I just sort of like intermingle my PP with。My HTML。

Gets a little bit sort of confusing after a while。And this is not either the greatest application。

 but it demonstrates quickly and simply this notion of what I call， well。

 what the world calls model view controller， and this is my really simple implementation a model view controller。

 You can go Google model view controller。And you can。



![](img/77eb364cf79ccf0bfe9380087c3af294_3.png)

View controller。And you can read so much stuff about model view controller。

 I even use that slide in my talk。 And the whole idea Model view controller is。

 is that when you're doing the request response cycle， there are three basic things that happen。

 One is the data model gets updated， the database， the back end， et cetera。

You generate a new page and there's this thing called the controller which decides what to do with the model data。

 what next screen to pick， what how to respond to the incoming post data。

 and so I would call it controller， model view rather the Model view controller and that's kind of like the picture that Wikipedia is showing you here。

 and you can read and read and read and read and read more about model view controller and there's whole frameworks that do model view controller。

 but what I do。

![](img/77eb364cf79ccf0bfe9380087c3af294_5.png)

To keep it simple so that you know model view controller in kind of this low level sense。

 And then when you move to a framework that's more advanced。

 then you can just use the framework to do all the model view controller magic。

 So in model view So this is kind of like the model。

 And so what I do is I always start my PhP files that are going to do data processing in PhP。

 not an Hm。 And the model is handling the incoming data。 And the view。

 there's always a line in every one of my scripts where you see， oh。

 I've switched from the model to the view。 at least the ones that process data。 So above the line。

 the idea you talk to databases and do your data processing and handle post data And below the line you just mostly generate output。

 That doesn't mean you don't sneak a little PP in here。

 because PP is both a programming language and a templating language。 And in this case。

 I'm just deciding if the message is not false print it or print out the old value in the form using the H entities and less than question mark equal for the echo。

So。So the idea is there's always this line above which we are completely silent and below which we don't do any major data operations。

 We can do loops and whatever， but we don't talk to the database。 we don't do that thing。

 so that's my discipline。 and controller is the whole script。

 And if we get later in more sophisticated things we'll see that we're doing routing decisions were sometimes moving after we process the data we send them to a different script。

 And so orchestration in routing is the function of controller。 So this guessing game， guess MVC。



![](img/77eb364cf79ccf0bfe9380087c3af294_7.png)

This guess MVC is going to look like every other guessing game we've made。 So if I say 12。

 now it's a post， if you look it's going to be a post。 it's not going to show up here。

 So the old guess was 12 and it says too low and guesses 12。 Okay， and then I can change it 123。

 It's too high。 How about 121。 So all this stuff is working。



![](img/77eb364cf79ccf0bfe9380087c3af294_9.png)

![](img/77eb364cf79ccf0bfe9380087c3af294_10.png)

But if you look at it， what's happening is。Old guest， if and a get request。

 So let me do a get request by just hitting it and hitting enter。 So I do a get request。

 There is nothing in post。 So old guess is false and message is false。

 And there is a thing that's passed between the model and the control and the model in the view。

 I call that the context。 And that's really， in this case， it's just two variables。

 Old guess and message are set and then fall into the template past into the template。

 In other frameworks were more explicit about constructing a context and rendering a template with that context。

 But I'm keeping it really simple by saying context is what falls through from here to here。

 And we have to do it in a get request because it's going to run these two lines of code。

 and then skip all the way down to here。 So old guesses nothing and message equals false。

 And that's why there is no guess here。 and there's no message。 But then when I say 12。

 and I hit a post request。 it is going to be， this is going to become true。

 And now there's no error checking。 I'm sorry。

![](img/77eb364cf79ccf0bfe9380087c3af294_12.png)

![](img/77eb364cf79ccf0bfe9380087c3af294_13.png)

![](img/77eb364cf79ccf0bfe9380087c3af294_14.png)

I'm trying to keep this simple so it fits on a screen， so error checking would go up here。

 this is actually the logic of the guessing game。I'm just converting this to an integer by adding a 0 to it。

 That's kind of quick and dirty。 And then I'm checking to see if it's 42 or less than 42。

 But what I'm doing is I'm not putting echo statements here。

 I'm setting the message and then letting it fall through into the template， so。



![](img/77eb364cf79ccf0bfe9380087c3af294_16.png)

There will be silence up here。 There will be a bit of silent work that you don't even see up here where message and old guess are being set right here。

 And then it falls in， and then it renders it And away you go。

 And so that's the basic idea of model view controller。 And we'll talk about this a bunch。

 especially when we have more interesting stuff to just looking at the guess。



![](img/77eb364cf79ccf0bfe9380087c3af294_18.png)

And especially when this we get like two to three pages of code up here。

 it's important to really mentally separate the brains of your code from the look of the code。

 so model at the top view at the bottom Okay， so I hope that has been helpful to you see on a nap。



![](img/77eb364cf79ccf0bfe9380087c3af294_20.png)

![](img/77eb364cf79ccf0bfe9380087c3af294_21.png)

![](img/77eb364cf79ccf0bfe9380087c3af294_22.png)