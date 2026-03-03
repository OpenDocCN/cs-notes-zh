# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p49 48_模型-视图-控制器(MVC).zh_en -BV1Lr421A75d_p49-

![](img/9105e14e9fca1e96a695a850b864716b_0.png)

![](img/9105e14e9fca1e96a695a850b864716b_1.png)

So now I want to talk about a pattern， a programming pattern that we call model view controller。

This is something that if you're going be a web application developer。

 you might well just be able to like。Be in part of a conversation about Model view controller。

 So you should just know this because everybody like I'm MV。 your MVC。

 My MVC is better than your MVc。 That's how we talk。 So MVC stands for model view controller。

 And what it really does is it breaks the request response cycle。

 at least how we kind of handle it into three basic operations。

 And it's helpful to have this terminology So I can say， oh， that's the model。

 that's the view and this other thing， the controller。 And so the basic definition。

 sort of in a pure sense。 is that we take data。 we might update the model。

 and the model's the permanent storage。 The controller is this thing that sort of decides when to do things and when to switch from one screen to another we'll start seeing that more later。

 and then the view is the next thing that you see。 So you could think of it as it comes into the controller。

 the controller updates the model， the model then is done when we read the data which is reading from the model。

 we produce a view and then the user is involved。 This notion of there is this sort of model view controller。



![](img/9105e14e9fca1e96a695a850b864716b_3.png)

It should be C called controller model view， but that doesn't roll off the tongue as well as model view controller。

 so MVC。And and there turns out to be lots and lots of different ways inside of code and if you're familiar with。



![](img/9105e14e9fca1e96a695a850b864716b_5.png)

Or if you've heard of things like cake PhHP or Angular or React or Sphony。

 these are all ways of interpreting the Model view controller differently。

 And so what I'm going to show you is one way of interpreting the model view controller and this is the way I'm going to teach you and what you'll probably find out is mine is very simple because it's all in one file。

And it's very PhP like it's very sort of first principles， but ultimately if you look in a framework。

 they will put sort of the model stuff in one file， the controller stuff in another file。

 and the view stuff in yet a third file， and then they'll knit those things together and when you learn that。

There's no right or wrong。 They're just patterns that help organize things。

 And so if you're going to use do a symphony app and you've done a bunch of symphony apps。

 you know where all the models are at。 You know where all the views are at。

 you know where the controllers are at。What I'm doing is something that's kind of a more low level than that and putting it all in one file。

 So what we do what I do is I basically make it so that when I'm writing a code。

 I break my code into two parts and what I do is in the top part I do all the model part。

 So the model is the top part， meaning that if there is incoming data， I handle it。

 Sometimes there is no incoming data and I go straight to the view。 Sometimes there is model。



![](img/9105e14e9fca1e96a695a850b864716b_7.png)

And then I always can draw a line。Between the model code， this is also silent。And I mean by silent。

 there is no output， right， there's no output whatsoever。

 It's the silent part of the your handling input data。And again， there may be no data。

 and so you skip right past it， and then you fall into the view。 So the bottom part is the view。

And it produces the output and you're basically there's some rules about what you're not supposed to do down here。

 you're supposed to pass some information down and you're not supposed to talk to the database down here。

 you're supposed to talk to the database up here because when you're talking to the database you're working with the model and so this is what it looks like right and so in this case。

I'm refactoring that guessing game a little bit where I have the old guess and the message。

 These are the pieces of data that are going to be in the view。 and so if you come down here。

 you will see that I'm going to print out the old guess andm going to print out the message。

But I'm going to start by saying the old guess is nothing and the message is false。

 and if I have some data， I'm going to handle that data， I could put better validation in here。

 but I didn't do that because I wouldn't fit on a screen。

 So I'm just going to check to see if it's 42 less than 42 or greater than 42。

 and instead of printing it out in that if I'm actually going to just have this variable message fall through into the view。

 And the data that we send between the model in the view It's called the context。

 So the view has little bits that are to be replaced with data， it's not just static HTML。

 It's dynamically generated H。 And the context is that set of things that we're sort of passing between the model in the view and the controller is making all these decisions。

 later we'll do these more complex things and these will route to other files and that's another controller activity deciding when to do stuff what to do with the model deciding when to switch to the view。

 That's all the controller and when to switch to completely different files， that's all control。St。

 okay？So a simple rule to follow is that you're not supposed to generate any HTML on the top part and you're not supposed to touch the database in the bottom part。

 any database stuff is supposed to be done before we cross that line and pass in as a variable end of the view and that's just a disciplined thing。

 It doesn't mean you can't do it just means that we're going to be disciplined and we're going to file this model view controller pattern。

 and so if you look at my code and I look at your code， we can file the same convention。



![](img/9105e14e9fca1e96a695a850b864716b_9.png)

And so like I said， this model part is in the top and again。

 there's always this line that you can draw， we're going to pass the context。

 which is going to just be two variables， old guess and message。

 sometimes context are much more complex we have an if statement and there's always an is set here and it's always looking at post and the first thing is deciding is is there any input date at all and if it's a get request because we're coming in the top once with a get request to show the page and then when the submit button is we're coming back in again。

As a post request， Okay， and so in the get request， this is false in the get request， it's false。

Actually， let me do it this way。We come in once with a get request。

 and the second time we come in with a post request。Right when the get request happens。

 it's going to set this to negative and then it's going to skip all this。

 It's just going fall through， right， So there's no post data。 But if we then have post。

 it's going to set this。 But then this is going to be true。

 And then we're going to set message to be something different。

 And then we're still going to fall through。 So in both the get。

 we come into the top for both get and post。 and we exit at the bottom for both get and post。

 But we've got a different context context。 there are these two variables that are passing between and across the magic line。

 And if we take a bigger look at what's going on below the magic line。Right， this is the magic line。

 The models above the views below， and the context is coming through。

 So the context are these two variables。 So we come in here。

 and we have to know that this view code is going to run two different ways。

 So we have to put some if code in it。 So we're say， you know， if theres something in the message。

 message false means theres no message to show。 But if there is， then we'll print it。 So this， this。

 this is going to show up on the post， but not on the get because message is going to be false on a get request。

 Conti through。This is just HTML。 And then we use the little shortcut。 And of course。

 we use HTML entities。 I'm very proud of us because we're using HTML entities of the old guess。 Now。

 remember， if this is a gut request， old guess is an empty string。 And if it's not。

 it's 42 or whatever the old guess was。 And so that's how our view constructs itself from the context that's passed in。

 And so this is just a slightly more of verbose way of doing exactly what we did before with kind of our model view and control are all mixed into one file but this discipline。

 as our code gets more complex having a discipline that puts certain things here and rules about what we do up here and rules about what we do down there。

 it's really helpful okay。😊。

![](img/9105e14e9fca1e96a695a850b864716b_11.png)

So in summary we talked about the superglobals get post， we talked about when you might use them。

 we talked about form fields， we talked about these like colors and dates and all the validation that we can put in。

 we covered a lot of stuff in this lecture， how to use HTML entities to sanitize the HTML so you don't end up with HTML injection。

 some of the functions and techniques that you can do to do data validation when data is coming into your server。

 and kind of a way to structure our server code using the model view controller pattern。

 knowing that there are many ways to do this， many frameworks， many languages。

 but we're going to start with something that's sort of very pure PhP。

 and then we'll learn more about those other evolutions on Model view controller later。



![](img/9105e14e9fca1e96a695a850b864716b_13.png)

![](img/9105e14e9fca1e96a695a850b864716b_14.png)