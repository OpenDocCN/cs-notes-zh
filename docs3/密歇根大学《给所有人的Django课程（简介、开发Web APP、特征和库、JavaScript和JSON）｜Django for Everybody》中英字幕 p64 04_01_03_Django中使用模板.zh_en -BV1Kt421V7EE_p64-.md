# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p64 04_01_03_Django中使用模板.zh_en -BV1Kt421V7EE_p64-

Hello， now we're gonna to talk about the other half of the views。

 the templates and the templates are a way of creating HTML and again。

 just to ground everything that we've got here， know we're in the views and the views are really sort of the code the Python code that we drive。

 We're going to get the forms in a bit。 but views kind of merge stuff from the templates merge stuff from the models put you send stuff in and make pages right So this is going to look a lot like HTML。

 it doesn't have to be HTML it can be things but other than HTML。

 but templates in our class will mostly be HTML and so they're kind of the last little piece of the puzzle to start building user interfaces and from this point on we're going to be making user interfaces rather than introducing the parts of ajango application that have the user interface So this is the。



![](img/5ee9f9d6f7c269e1788997336852b116_1.png)

![](img/5ee9f9d6f7c269e1788997336852b116_2.png)

![](img/5ee9f9d6f7c269e1788997336852b116_3.png)

Text from the Django website， you know it's about convenient ways to generate HTML dynamically and there's a couple of different templating engines we're using the default one and there is some data that we pass into the template there's a process that's called rendering and then we get the HTML back and we return to the browser with that HTP response which we've already been doing it's not the request response cycle is the same the differences instead of writing Python code to concatenate a bunch of things together we are going to use a template engine so this is the kind of stuff that we've been doing all along we have a class in a view a view class rest main view that extends this view income comess perhaps the request object and then maybe even another parameter that's not changing。



![](img/5ee9f9d6f7c269e1788997336852b116_5.png)

What we're doing here is we're using concatetnation， concatetnation。

 these little plus signs escaping we're doing all the escaping and concatenating and then we are sending back a response so what goes back as a response what comes in is a request。

 what goes back as a response we're still going to do that we're just going。

Get rid of that middle bit and make it a little prettier and make it a little more sense if you look at that。

 os if you look at that。

![](img/5ee9f9d6f7c269e1788997336852b116_7.png)

![](img/5ee9f9d6f7c269e1788997336852b116_8.png)

If you look at it， youve got to get it syntactically right， youve got indentation problems。

 that's three lines of Python， I'm using triple quotes， I'm using plus。

 I've got to get all that matching together。And then like eventually I'm gonna be in the HTML is going back。

 I'll be using single quotes of double quotes and all those kinds of things and JavaScript's gonna look really ugly here indenting of the HTML kind of will fight with the indenting of the Python so this is just general I mean I've only done short ones because I only wanted to show you a little bit before we showed you templates So the basic process is a bit of software a template software that Django provides us we're using the builtin django one and basically template is some HTML with some hotspots in it that says put data here and then the rest of it is just HTML and then we pass the data in in some kind of object dictionary。

 etc and then then a bit of code pulls all that stuff together and then produces HTML with all the data placed in it often the render data that we're passing and it's coming from a model for example。

 know we might talk to a database load up a bunch of rows。



![](img/5ee9f9d6f7c269e1788997336852b116_10.png)

![](img/5ee9f9d6f7c269e1788997336852b116_11.png)

And then put it in。 But in the simplest form what we've got is got like a little dictionary。

 call this the context you could call it the render data and then you have the render template so the render template is really HTML and that's what makes it a lot easier to look at because you're not putting double quotes around anything there's no concatenation but there are special characters and what the double curly brace surrounding it says is instead of that take this bit out and replace it with whatever's in the variable do from the render data and so that's how when it's all said and done this is replaced in the fun stuff replaces curly bracece。

 curly brace dot in the final output and if you thought about it for a while。

 you could probably write a render engine they're not that hard you'll see they have some sophisticated features eventually so you probably don't want to write your own render engine but you could imagine a Python assignment where I say you take write me a function that takes a dictionary that looks like that。



![](img/5ee9f9d6f7c269e1788997336852b116_13.png)

keyey value dad fun stuff and then take some text file it has curly brace， curly brace， dot。

 curly brace， curly brace， and then find that and then replace it with that string you could write that code you don't want to write that codejago has already written that code for you。



![](img/5ee9f9d6f7c269e1788997336852b116_15.png)

So here's the code in action and so this is we're going to call this。

 we're in the application named TmpL Tle and so we have the application T we have the view game and then we have a number 200 and that's what we put in our URLs。

pyy to route the game view and take one parameter remember that slugs our a special version of strings that are letters。

 numbers and dashes I believe and so the entire request coming in from the browsers coming in the variable request。

 this number 200 is coming in the variable from the URL is coming in in the variable guess and so instead of us concatenating together we are going to create a context what I call a context was just as a dictionary of keyvalue pairs and the key for guess is GesSS it's a string that guess will matter inside the template and then we pull this number 200 and we convert it to an injure and then we pass it in and。

We pass it the request object， we pass it the name of a template， and then we pass the context。

 the key value pairs to be substituted in that， so let's take a look。



![](img/5ee9f9d6f7c269e1788997336852b116_17.png)

So if we look at this template。It has a series of curly brace like hot spots。

 places where you would replace stuff and so the double curly brace just says retrieve the string that is under gas and put it in and so that's how we get your guess was 200 in the ultimate output and then we have curly brace percent all the way to percent curly brace and this is a series of if then else so you can put logic in here too you don't have to just put take this string and put it in so what we're doing is we're basically saying if the gas is less than 42 we print out too lows if it's above 42 we print too high and of course if it is 42 we print out just right and since our guess was 200 it prints out too high。



![](img/5ee9f9d6f7c269e1788997336852b116_19.png)

![](img/5ee9f9d6f7c269e1788997336852b116_20.png)

And so basically this makes this view code a lot simpler and doesn't put a less than in greater than in concatenations it's all substituted by this render routine now the render routine returns an HP response request so when we get back we just return it so we hand back to Django the HtP response request and then the page is delayed in our displayed in our browser remember that we have a Django project and this is the Django project in my case the Django project is DJ4E samples and I have a bunch of little applications all these things is matter of fact T is the one we're working at right now those are just the different pieces of sample source code that I've built for this class to talk about and so those are applications so it' it's just that dnangle terminology project made up of one or more applications and folders okay。



![](img/5ee9f9d6f7c269e1788997336852b116_22.png)

And so the problem is is these templates， when Django starts up based on the settingstting。pyy。

 it loads all these files up， loads them all up， and so it loads them all up。

 and the templates are actually global and we'll see this in a bit。

 they're global across all of the applications。And so the problem is。

 is that if you have a template name like detailed。

ht and you have a whole bunch of applications like I do。

 all of which want to have a template name detailed。 HTMLtm。

 it doesn't work because which detailed it be template/ detail in two folders。

 it's not clear which one you're talking about。

![](img/5ee9f9d6f7c269e1788997336852b116_24.png)

So we've adopted a convention that we take the application name and we make a subfoldder inside of templates。

 that's the application name， and then we use this fs slashdetail HTMLtm or picks slash detailed HTML as the name of the template so in a sense we're introducing a subfold and it's a little jarring at first because you see it's the same it's a good convention I mean it's unfortunate we have to have the convention。

 but because these names end up being global across your entirere dangle project in each application and to get them a name to get them properly named it's necessary to introduce this extra level of redirection we get to logins' there's templates that are stored outside in other application so sometimes you want to get a template in some other application So there's all kind of。



![](img/5ee9f9d6f7c269e1788997336852b116_26.png)

All kind of reasons this is a great idea it just isn't the prettiest thing in the world so just when you see it don't freak out I try to try to call it out in the slides and so we put these paths that includes the application name twice it's weird but it is necessary to do this because of the notion that all these template names are global across the entire application but if then we called this the template name with the name of the application prefixed way it goes Jenjago could have made that a little easier for us but they basically didn't and so we have to do this but everybody does it the same same way so now what I want to talk about is the actual templatelating language itself I showed you a couple examples the double curly braces but it turns out there are lots of things that you can do with double curly braces in the template language。



![](img/5ee9f9d6f7c269e1788997336852b116_28.png)

![](img/5ee9f9d6f7c269e1788997336852b116_29.png)