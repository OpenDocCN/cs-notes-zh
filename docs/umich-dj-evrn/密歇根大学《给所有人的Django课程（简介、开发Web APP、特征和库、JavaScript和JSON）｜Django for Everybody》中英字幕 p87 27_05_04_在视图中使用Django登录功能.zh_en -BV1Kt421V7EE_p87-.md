# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p87 27_05_04_在视图中使用Django登录功能.zh_en -BV1Kt421V7EE_p87-

So now we've kind of understood a little bit about the user object and how we it do things in templates and how we get at the URLs for login and log out and then how we redirect back to ourselves。

 let's talk a little bit about the login page itself。

And so the login page is something that's provided by Django。

 but it needs a template and so what happens is is we get to control the template and we're going to go to this URL。

 the code behind the views， the code that looks up the password， the codes that gives you errors。

 that's all taken care of all the viewss are taken care of and what we get to do is we get to describe a template that controls our look and feel and so we can have a simple login thing or a pretty login thing and we can have links to the rest of our application。

 and so we want control over our login page so it looks like it comes from our application rather than having it look like it came from Django。



![](img/779aa11569bb5ae4f967c575b4820733_1.png)

![](img/779aa11569bb5ae4f967c575b4820733_2.png)

So I'm not going to go through in much detail about how this works。

 you have to create a template that can be accessed as registration slash login do HTMLt And remember that no matter which application in a Gengo project you're working in。

 those names are global。 so for example， this。This name right here， registration login。ht。

 the fact that it's in my home application doesn't matter。

 and that's why we have this extra slash in here， so just because it's in the home application doesn't mean it has to be the home in the registration don't have to be the same in this particular case and so this is a template that if they just do a render so in their view in the login view that's somewhere deep in Django。

 they're just going to do a render to registration slash login。

html you have this somewhere in some application because the templates are global it's going to find your template and put that in so within this template。

 there's a few rules that you've got to follow。

![](img/779aa11569bb5ae4f967c575b4820733_4.png)

![](img/779aa11569bb5ae4f967c575b4820733_5.png)

They're going to send use they're going to send some errors and there's errors if the form has errors。

 you have to have some output that deals with that if next that's actually that next equals parameter okay and so if the next is there and you come into this log and this one's a little bit weird if you have a going forward page that means you came from a page and you're going to go back to a page if the authentication happens that means。

You've been logged in， you went to the page， the page kicked you back because it's protected by more than just logged in user Okay。

 so this little bit right here， this is a little bit subtle If you're not logged in that's kind of the normal case。

 please log in to see the site。And then we basically create a simple form we're going to post to the login URL that just looks up the login URL and we've got this context variable called form and we can print that out that form has the key that form has all of the input stuff in it。

 we're going talk about forms coming up soon， and so that that's what generates this form here generates all this stuff right here and so there could be a bunch of things in there but the form is created is a variable created by the view that has all the input names and areas。

 etc cea that it wants， so we didn't have to actually construct the form we do have to submit。

 put the login button we could put a cancel button and we do have to pass。



![](img/779aa11569bb5ae4f967c575b4820733_7.png)

![](img/779aa11569bb5ae4f967c575b4820733_8.png)

The next back as a hidden field， No a hidden form field is just like a text field。

 except that it doesn't show up here。 And so that's in there。 And if you were to view source。

 you would see that。 so that's after you submit this form。

 it needs to know where we're going to go next。 So then if you're successfully logged in。

 it's going to log you in， say yay， and then it's going to redirect to whatever that next value is。

 And that's our way of。goingIt's going to give us the next value inside this template。

 but we have to give it back to the view when we post back to into the view。



![](img/779aa11569bb5ae4f967c575b4820733_10.png)

So like I mentioned there's a whole bunch of data that we can get。

 there is this user variable and that user variable has their full name， their email。

 and very importantly the primary key of the Loggedin user。

 but these things are only defined if user is authenticated is true。



![](img/779aa11569bb5ae4f967c575b4820733_12.png)

You can access this user data in Python， it's in a little different spot， it's in the request。

 so this I just changed the name of request to REQ， that's just a variable name you pick。

I will even generally always write it as request or REQ。

And so the user information that is pretty much the same as what's in the template tag。

 well template context user user is authenticated， their username， their email I could have had rec。

user。 ID if I wanted here and otherwise it's not logged in and then I just throw this back as a simple HP response。

 this isn't all that useful， it's just showing you how to get your hands on those values。

 if you're in Python， so sometimes you're in Python， sometimes you're in templates。

 quite commonly you're you're in templates。

![](img/779aa11569bb5ae4f967c575b4820733_14.png)

So I've been talking about a view that requires a logged in user and so again。

 imagine something where you're sort of reading your messages on an online system and you bookmark the message reading URL。

 and then you shut your browser down which logs you out of the system and then you click on that bookmark straight to the messages my inbox or whatever。

 and then inbox looks at you and says you're not logged in so I' going to send you to the login。

 you finish logging in and then you come back。That's what the next equals does Now there's a couple of ways in views to write that kind of feature that basically says this view is fine but only fine for Loggedin users so let's take a look so one of them is checking to see if user is authenticated so I have two views in here one is I'm going to protect it manually and that's so you can see how it works but it's really not the right way to do it I mean you can do it this way but it's like there's always a better way in Django。

 always a better way in django。

![](img/779aa11569bb5ae4f967c575b4820733_16.png)

So here we have a class based view。And we ask， is the user authenticated？

If the user is not is authenticated， we just do whatever now there might be a whole bunch of stuff in here。

 there might be a whole bunch of， but I'm just going to render the thing so that that's a view so I'm protecting this particular manual protective view。

 but if you're authenticated， you can see it。

![](img/779aa11569bb5ae4f967c575b4820733_18.png)

It doesn't do anything in particular rather than dump a bunch of data out。

If you're not authenticated， then I'm going to construct a login URL by calling reverse。

 say look up the URL for login， add a question mark and then add the request path。

 which means wherever we're at， come back to it so that's the next and that's going to put next equals blah。

 blah， blah blah blah， blah and then instead of returning a render we return a redirect and say okay go to the login URL so the way this is going to work is it's going to come in once。



![](img/779aa11569bb5ae4f967c575b4820733_20.png)

You're not logged in， so it's redirecting， it's going to go out。

 but then it's going to come in back again and this time the user is redirected in so it's going to show you the page。

 so you end up going through this twice。

![](img/779aa11569bb5ae4f967c575b4820733_22.png)

Now， that's the bad way to do it or the or the wordy way to do it。

 I mean it's only five lines of code， but I don't like five lines of code。

 so there's this thing called a mix in and a mix in is a class。



![](img/779aa11569bb5ae4f967c575b4820733_24.png)

The idea of a mixing is that， you know， we have kind of inherited class。

 we inherit things that are like。Just a feature almost。

 So what we're doing is we're going to take our protective view。 It really extends a view。

 but it's going to also add the capabilities of login required mixing。

 So login required mixing basically says to Django。 if this is here。 Hey， I want to do this。

 don't let the user into this particular view。 Proect you protect the view。

 So this is another protected view， but by simply including this little signal that says login required mixing。

 I've mixed this into my view。Then it does all this work for us。

So what'll happen is it won't even come in， right， it won't even come in if the user's not logged in。

 it will redirect and then come back and then let this code in the get run only when the users logged in。

And so this is by far the most common way to do it is just called login requiredd mixing。

 saving you from writing all these lines of code right， so all these extra things。

 because do I remember how to do this， what if I write that 5。

000 times in an application it's really kind of silly when we've got login required mixing that takes care of all this stuff。

And just to review this as what that view looks like， it just sort of dumps all that stuff out。

I use the same view for I mean， I use the same template for all of these views。



![](img/779aa11569bb5ae4f967c575b4820733_26.png)

So login like many things in Django is simple， it's easy。

 you add the things to install apps and URL patterns， you make yourself a template。

 I didn't go in great detail， Django has great documentation if you want to get really sophisticated what I tend to do is I get one or two templates working for login I'm like I want to use this one today or that one so this is where like the sample code has two different logins that we're going to use one is a simple local login and the other one actually is a login when we're going to use Gitthub to do our logins you can get yourself get your URLs for login with reverse reverse lazy or the URL template tag and then if we want to come back we add an X parameter to those URLs and then when we have a view and we say look I'm not this view is going to depend on request user or the in the user template tag just add login required mix in and then django takes care of making sure that you can't get to the view unless you're logged in and if you try to get to the view it tries to let you log in。

And if you are login successful， you come back to the view and it's all transparent to you and it's literally just one little comma thing in the Cate So it's pretty simple。

 it's pretty awesome， I just want you to understand what's going on because again sometimes the fewer the lines of code to write the harder it is to understand chairs。



![](img/779aa11569bb5ae4f967c575b4820733_28.png)