# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p05 05_02_03_Django中的所属行-通用视图回顾.zh_en -BV1rNibBuEwD_p5-

So now we're going to take a look inside of a generic edit view and we want to look at how it functions internally so that we can override and extend some of those functions so we can take the generic edit view and turn it into a edit view that supports an owned row。

So this is a review we' we've gone back a couple of lectures。

 this is the edit form flow right and I went through this in great and great detail so I'll just review it really quickly right so you're going you've hit the edit button right so you do a get request to like slash1 or slash 15 you're going to grab that data。



![](img/1d64e293d63e1ca22bb49165fd11d16f_1.png)

Oops。YouYou're going to go in， you're going to load。The primary key1 or2 or 15。

 if you didn't find it， you're going to send in 404 error and then you're going fill the form with old data。

 the user is going to edit that data， they're going to post the good data。

 then the form is going to be validated of course according to the form rules remember the model kind of deals with the backend and the form kind of deals with the front end So the validation is a form aspect and then if there's an error it goes back and allows you to redo it and then if there's no error in the submitted data then we load a new model up。

 but we reload the model， check to see if that model is accessible and accessible is going to matter to a lot to us in a second can if it's there and you can read it and you're legally allowed to read it great otherwise we're going to give you a 404 as you're submitting the data and that has to do if they messed with the form or something or they're submitting it to the wrong wrong URL。



![](img/1d64e293d63e1ca22bb49165fd11d16f_3.png)

![](img/1d64e293d63e1ca22bb49165fd11d16f_4.png)

But if we can get the data， we change the data and we store the updated data and then we do the success URL right and so that that's the basic form flow。

 we did that before we did that with every one of our cruds。



![](img/1d64e293d63e1ca22bb49165fd11d16f_6.png)

And we also looked at this documentation in the generic list view。

 it could be in some of the edit views。

![](img/1d64e293d63e1ca22bb49165fd11d16f_8.png)

At some point you will see in the Django documentation。

 it's telling you how this class is functioning internally。How it's。



![](img/1d64e293d63e1ca22bb49165fd11d16f_10.png)

Working its own magic inside itself and this is method flowchar。 First。

 it's going to call setup and it's called dispatch， check to see if the methods allowed。

 get its template name， get a query set， load the data from the database。

 get the context object name， get the context data， and then render to response and so。



![](img/1d64e293d63e1ca22bb49165fd11d16f_12.png)

You might say why are they showing us all this and the answer is because we can get our hands in and mess with these things and these are like our access points into this generic list view class that allow us to dig in and make changes and so if we are to look at that same picture and think of it from the point of view of which methods are being called。



![](img/1d64e293d63e1ca22bb49165fd11d16f_14.png)

At the moment where this generic edit in this case it's going to be an edit view。

 this generic edit view is happening， so here we go。



![](img/1d64e293d63e1ca22bb49165fd11d16f_16.png)

So the get request comes in， it's got some primary key so it does a get query set and it reads this thing and then it reads it using getque set。

 it's still reading it， but it happens to be doing it in a method called getque set and if getquery set works or doesn't then it keeps on going then as it's rendering the template it's going to get the context data by calling a method called get context data that's another place that we're going to play with and we're going to inject ourselves into get context data then we'll do the edit。

 the post will come in and then it's going to do validation。

 but it does it in a method called form valid， so the first thing that happens upon the receipt of post is it checks to see if the form is valid we're going to add our own little code in form valid as well。

If it goes back， it does a render so it's going to use get context data， if it is good。

 there's no error， then it's going to actually call getQu set again to get the data and then it's going to modify the data and then it's going to store the data there's some name for this but I didn't put it in The point is each of these moments where there's something critical going on。

Form valid G queryrry said， that's a place where we can extend the behavior of this built in class without knowing too much about the class。



![](img/1d64e293d63e1ca22bb49165fd11d16f_18.png)

And I showed you at the end of a few lectures ago， this crazy override。 I did this crazy。

 crazy override where I made this weird equine view and I have a model a car and a template name。

 and then I'm overriding getque set So this is extending generic list view。

 But instead of using the getQu set that's in generic list view。

 we're going to call our own getque set， So instead of reading car objects we're going to read horse objects。

 and then we're going to return a list of them， and that's what the getque set has to do。

 the rule of getque set is you get called， you have to return a list。 If we didn't write this code。

 it would do this except with car， but we did write this code Why because。



![](img/1d64e293d63e1ca22bb49165fd11d16f_20.png)

![](img/1d64e293d63e1ca22bb49165fd11d16f_21.png)

We want to override it。Was there any logic to it note just because I wanted to show you crazy things right and so because I've overridden in the generic listist view。

 it's not calling the generic list views query said at all， which would look at the model car。

 but instead it's calling mine that's in wacky equine view。



![](img/1d64e293d63e1ca22bb49165fd11d16f_23.png)

![](img/1d64e293d63e1ca22bb49165fd11d16f_24.png)

And so when it prints out， you see a list of horses， not a list of cars。

 because I overrode what behavior was inside the list view class。

 which normally would be informed by that。 But my code in here ignored it again。

I have no purpose for this other than showing you that I can change the behavior of the parent class while creating a derived class。

Now sometimes in this case， I'm just completely overriding it and it's like。

 I don't care what you were going to do before。 I'm going to do something completely different and you have to know what the rules are。

 I had to know what the return。 It took me a while to write this。

 and I might even even looked at some djago source code to figure this out。

 but eventually through stack overflow I figure this out。

 So this is not trivial to write and I'm not expecting you to write this。

 I just want to show you the technique like this keyword args thats that's something。



![](img/1d64e293d63e1ca22bb49165fd11d16f_26.png)

![](img/1d64e293d63e1ca22bb49165fd11d16f_27.png)

I'm sure at some point I knew what it was， but I just stole that off a stack overflow like everybody does。

So。In this de get query set， you'll see that I have just overridden and ignored the de query set from generic list view。

 that's one way of overriding a method。 Another way of overr a method is this get context data。

 So what is get context data going to do。 Well， at some level。

 get context data is what puts in this crazy， this list ends up going into horse list right。

 So that's that's somehow this variable that I return here in query set ends up being put in to my context is horse list so then I can write this loop that prints that stuff out。

 And that's by convention， right， It actually looks at the type of this thing and says， oh。

 that's a list of horses So it makes up the variable and puts it in the context。 Now。

 where that's being done。

![](img/1d64e293d63e1ca22bb49165fd11d16f_29.png)

In generic list view is in a method called Gt context data。

And so I actually don't want to completely replace get context data。

 although I probably could if I want because this is so simple。

 what I actually want to do is I want to augment the context and I want to throw something else in it。

 so what I want to do is I want to run the code from generic list of you first I want to get the context back from that and then I want to add something to it and then return sort of like this composite context okay。



![](img/1d64e293d63e1ca22bb49165fd11d16f_31.png)

And it's not the syntax is a little scary， but it's okay。Let's take a look at get context data。

 just like anything self is the instance， self is always the instance KW Args is a just a way of taking all the parameters so I can pass them in。

 So what I'm going to say is I'm going to say hey， super super is like calling get context data in generic list view。

 so go into my superclass。Wacky equiquine's view is a subclass， list view is my superclass。

 super get context data and pass whatever arguments we're going in there， we're all good。

 so just call that， do it and pass in all the arguments and do whatever and that's what ends up putting in horse list and so at that point context is going to be a dictionary that has horse list in it。

But then I want to put some more stuff in， so then that goes into generic list view and then comes back out of generic list view and gives me and if all I did is return to context。

 then I really wouldn't have changed anything， but what I'm going to do is I'm going to throw in this little extra key called crazy thing and put the string crazy thing in it。

And then I return all that， and then eventually it goes into the template and this context finds its way into the template。

 And again， that's all inside of generic list view。

 And eventually horse list is there because of the call to the super and crazy thing is there just because I explicitly put it in。

 and so I have。

![](img/1d64e293d63e1ca22bb49165fd11d16f_33.png)

Augmented。Without replacing the first one I completely replaced getQu set and the second one I called the parent and then I augmented the return value and then returned kind of the combination of what the list view did and what I want to add to the list view so we're going to use both of these techniques coming up when we start talking about the owner list。

 the owner。 py code and how we can then jack in to this generic code and implement our owner field so that's the next thing that we're going to do。



![](img/1d64e293d63e1ca22bb49165fd11d16f_35.png)