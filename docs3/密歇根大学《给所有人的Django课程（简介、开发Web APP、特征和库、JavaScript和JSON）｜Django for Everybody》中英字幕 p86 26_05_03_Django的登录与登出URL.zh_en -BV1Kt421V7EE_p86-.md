# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p86 26_05_03_Django的登录与登出URL.zh_en -BV1Kt421V7EE_p86-

SoNow we're going to take a look at what we do with Django to handle logging users into and out of our application。

 So just we talked about sessions recently and making a session is not the same as being logged in。

 Loging in actually changes data in the session Loging in in general。

 the most basic way of logging in depends on the existence of a session and logging in is putting data into the session about the current user in their name and their email and then logging out is removing it。

 And the session you could have multiple users log in with one user log out。

 login with a different user log out。 if you're just in the same browser。

 you're going to end up with the same session just associated with different users。 So remember。

 Sessions and login are not the same thing。 just like cookies and Sessions are not the same thing。

 Sessions in login are not the same thing。 but they all build on each other。

 Sessions built on cookies and login builds on sessions。



![](img/ee877b3568cfa7b85846ea19318d7c98_1.png)

So to make this all work， you have to add to your installed apps。

 all the Djago support for all this login and log out stuff。

Now if you automatically built your project and you've got a settings。

pyy that they're going to just put this in automatically。

 so this is just till you know when you're looking at it。

 where it is that all this magic functionality comes from， it comes from this installed apps。

Also for the login and logout you're going to have to add a path to your project wide。

 so DJ4E samples DJ4samples URLs。pyY this is not in any of your applications。

 this is in your Django project and you add a path and there's a bunch of URLs and that gets all registered and a whole bunch of wonderful magic happens at that point。

And so that's how these URLs are activated in your Django project so the applications。



![](img/ee877b3568cfa7b85846ea19318d7c98_3.png)

So the way we get the URLs to the。The login and logout features as we use the reverse we've been using reverse all along reverses the way we look up for a particular view and in some URLls py matter of fact in that django contri off URLs in that there is a name equals and so there's a view in there that they've got that we didn't write and it has a name equals and has name equals login and a name equals log out and so we can do a reverse lookup like we would have any of our views that we might have and say what is give me the URL in this django project for the view named login or the view named log out and as's pretty simple you could even probably hardcode these but maybe the route isn't exactly a count slash right and so maybe you call them something else and so that's why we use the reverse to look these things up and and so that's just a convenient way of doing it。



![](img/ee877b3568cfa7b85846ea19318d7c98_5.png)

Now one of the things about logging in is sometimes you have an application and there's like a login button。

 but sometimes you just have pages that are protected by login and then when you go to a page it says。

 oh wait you got to log in first and then after you log in you'll notice it typically just takes you right back to the page that you want to see so you might bookmark a page when you're logged in and then you log out and then you click on that bookmark page but that requires that you be logged in。

 so you're going to go to the page and then when you're done logging in that when you want to come right back to that page and so that's using redirecting。

 but it's redirecting after login is successful or after log out is successful。

Lgouts are almost always successful， and so there's a parameter that we can add。

 a gap parameter that we can add， and it's the next equals and what we do is we give it a path。



![](img/ee877b3568cfa7b85846ea19318d7c98_7.png)

And so here's a little bit of code that we're going to play with in my sample codes under the OZ application。

And so I got a bunch of views and I'm going to give them some names so that we can play with them so these are just the URLs。

pyy So if you take a look in this main do HtM template。

 you see a whole bunch of things you see this next feature in action so here's a couple things we can do so there is this user object that in a sense is passed in you don't have to do anything to pass it in there's this user object that sits there in your template context that's automatically we'll talk later about how you can sort of inject into every template certain little miniature certain little things that you got to inject but the system injects this user there is an attribute called is authenticated which is true or false to say whether you're not logged in or are logged in。



![](img/ee877b3568cfa7b85846ea19318d7c98_9.png)

![](img/ee877b3568cfa7b85846ea19318d7c98_10.png)

![](img/ee877b3568cfa7b85846ea19318d7c98_11.png)

And so if we see it， we say， oh what's their person's full name， user。email， user。id。

 this user ID is the primary key， we might actually have a later we'll have a foreign key that goes into the user table and we need to know what the primary key of the current user is so we can populate our foreign key。

 so when we like have a row and it's owned by such and so we're going to actually put a foreign key into a table that we didn't even create。

But the thing I'm talking about now is you can get a URL。

 that URL tag that's looking up the name of a view， log out as the name of a view。

 log in as the name of a view， and then we have this question mark next equals。

 that's the parameter to say when you're all done with that login or log out。

 go back to this particular URL okay and so。嗯。And so that says go to the URL that's in the authorZ application。

 the viewte named open and so that's one way of doing it another way。

 let's say and login we're going to get the login URL and send ourselves back to the request path requestquest is another one of these things that's dropped in automatically for us that is the current URL of the view we' at so in a sense this is a contraction that says go ahead and go to login and when you're back come right back here so login will log in and then redirect back to this page that we're on whatever the page is because this is going to be this little main dot HTMLml is in a couple of my different views so request out path is like come back here so that's a good pattern to know to just say login and come back to this current path when you're all done。



![](img/ee877b3568cfa7b85846ea19318d7c98_13.png)

![](img/ee877b3568cfa7b85846ea19318d7c98_14.png)

And so here's just a bunch of connections to this thing and here's just all my links and I have a couple of things I have some no login required pages just to play around and then I have one that's protected by a hand in Python and then once required by a login mix in and then I sort of dump all that data and I think I showed you that one already。



![](img/ee877b3568cfa7b85846ea19318d7c98_16.png)

So here is one of them， right， I showed that。That's what this all looks like。

 you can see that these links have the next in there， you can， this is how it turns out to be。

 get accounts log in， oops， come back， come back。You go to a accounts login next equals AZ open and that's basically I'm in this file right now。

 I'm in that URL and that says， go ahead and log me in and then come back to this URL to the AZ Open。



![](img/ee877b3568cfa7b85846ea19318d7c98_18.png)

Here's an example of the logout URL with the next setup in it。



![](img/ee877b3568cfa7b85846ea19318d7c98_20.png)

And so up next， we're going to talk about not just how to get the users to go to the login page。

 but how to configure the login page。