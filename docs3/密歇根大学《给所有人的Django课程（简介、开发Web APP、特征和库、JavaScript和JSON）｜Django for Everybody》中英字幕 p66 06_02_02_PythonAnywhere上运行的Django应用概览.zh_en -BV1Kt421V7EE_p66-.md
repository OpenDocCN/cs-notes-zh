# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p66 06_02_02_PythonAnywhere上运行的Django应用概览.zh_en -BV1Kt421V7EE_p66-

![](img/30a594064e054ba2f5c2e079a229c4b8_0.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_1.png)

Hello and welcome to another walkthrough for Django for everybody。

A big part of the first half of this class is what I call the big picture。

 So in the big picture you are basically were trying to basically learn the ways of a Pythonjango application。



![](img/30a594064e054ba2f5c2e079a229c4b8_3.png)

Thejango application， django is an application that then you create objects and load those objects in and in those objects you achieve your web application。

 and so this is the flow where the request response cycle so we've got a browser on the left hand side。

 we got the internet very tiny in the middle and then we got Django which is running in a Linux server and a whole bunch of files that you either have or will be editing。

And the big flow is that the user requests a page in the browser。

 which gets routed into your application and your application may read database data or whatever。

Produce some output and then send it back to the browser where the browser looks at the response and showseth the user that request response cycle that is the essential engine of browsers and the internet。

Now， this picture may be the best way for you to think about it。

 or you may also just think about it as a set of folders and files because really。

 when you're developing your application， you're working with folders and files。 Now。

 the screenshot I'm showing you that has a folder， autos hello home。

 my site polls site is not like at the very beginning at this point。

 it has several application and several folders and it might be a little bit easier to understand the big picture。

 and we think about it from a point of view of multiple application。 So in this particular one。

 there are site has files in it， home has files in it， hellos an application。

 Autos is an application and polls is an application that you may have already done them。

 or they may be in the future。

![](img/30a594064e054ba2f5c2e079a229c4b8_5.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_6.png)

Ultimately， income is a request。And there are parts of your application。That。

Participate in that request。When your application is starting。

 So if your application doesn't start up very well or it blows up or it shows the the something went wrong message。

 that probably means as it was reading Se Py， and then the rest of these files。

 there was something wrong with the file。 and then you got to go fix the files。 but let's assume。

That things in settings do PY and the rest of the files at least are syntactically correct enough so that the application loads。

 Well， Django is a Python application that in a sense， is listening for incoming requests。

 and those requests come to Django， but then once it gets a request like a URL like slash polls。

Or slash polls slash2 for a detail page。It looks at URLs。pyy and that's the one that's in myite URLs。

pyy， so there's2urs。pyy， there's the polls URLs。pyy。

 and that's the second one and then there's myite URLs。pyy。In the Myite folder。

 you can see that there is Setting。pyy， which says here is how I'm going to set up my Djangu environment and also all the applications that I want to load。

And then for each of the applications， you're going to see a URLs。

 py N of views do py and perhaps as we get more advanced the forms， models。

 and then even admin py for each application。 So other than the myite URLs do py。

 the rest of it is kind of replicated as often as you want。 So let's take a look at some sample code。



![](img/30a594064e054ba2f5c2e079a229c4b8_8.png)

In。Python anywhere。So here we go， I' got my Home directory Django projects my site。Now。

 one of the things that's a little bit tricky to figure out is my site。

Is the the overall configuration for the entire Django project。 Autotos is an application。

 Hello is an application and Pols is an application。

 But my site is the configuration for the project。 But really， this actually starts。

The first thing to start your application is the Setting。 py， and this is all of your configuration。

 what applications， polls， home and autos are the three applications that I'm going to be loading here。

But it really starts before this。

![](img/30a594064e054ba2f5c2e079a229c4b8_10.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_11.png)

So if I go to the web setup。This is the configuration for DJfr do Python anywherewhere com。

 So if I go to DJfr do Python anywhere4 do com， that routes。

To my application running in Python anywhere。 So DJ freeed Python anywhere。 co。

 And so I this somehow has got a domain name and it routes into a Linux system。

 but then it eventually starts your application and routes to your application。 So from here on down。

If you put something on there。You don't really have to worry too much about the first part。

DJfred up pyth com， But you do have to worry about what you're going to how you're going to handle and how you're going to write the rest of this URL。

 right， So I just put in a bad one， and we get pages not found。

 and that's not like your your application is running。

 You requested a page that your application does not know how to respond to。Okay。Now。

If you have problems， you got to make sure that your source code and your working directory are your home directory。

 and then you want to make sure that this Wskey dot Py is properly set up。

 but that was set up in the very first assignment and you shouldn't need to change that Youve got to have your virtual environment correctly set。

 you got to have your Python version correctly set。And if you have problems。

 you can look at the server log and the error log if you're really having terrible problems debugging things。

 but we're not going to talk so much about debugging， we're going to talk today about routing。



![](img/30a594064e054ba2f5c2e079a229c4b8_13.png)

Python anywhere starts when you hit threeload button。 It reads settings dot py。

 the Wskeyconfig tells it to read settings do py。 And then all the rest of setup of your particular django instance depends on what you tell it in settings do Py。

 So let's take a look at the settings do Py because it's the beginning of your application。

 So there's a few things。 Now one of the things is this allowed host， which in an early assignment。

 I set it up so that。

![](img/30a594064e054ba2f5c2e079a229c4b8_15.png)

Told you to say anywhere。 And that has to do with the fact that there is some filtering going on about whether or not it actually is going to accept any requests from the internet to your application。

 so you can put a filter in a sense。 So we're saying with settings a La hosts equals star。

 We're saying don't put a filter in。

![](img/30a594064e054ba2f5c2e079a229c4b8_17.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_18.png)

The next thing it needs to do is where to start in terms of what applications need to start now some of the applications are built in applications and other applications are applications that you've added。

 so you'll add an application and then it'll tell you to add a line to this。

Then there's some configuration about middleware。 don't we'll change this later， but then it says。

Load up the URLs for the overall application。 Okay， and we'll see that where this is in a second。

 So it's like load up all the URLs for the whole act。 when it says root。 what it means is anything。

After。DJfree。pyython anywhereware。com/ that top part is the root of your applicationss URL hierarchy。

And then we set the database up and then some other things。 But that's about it。

 So this line here that says。My site URLs， well， that is。

 in effect importing another Python object and then running it。Doing a Python importport of this。

 now my site， my siteurs。pyy。This is what basically sets up the global URL routing or。

It doesn't have to be， but for all intents and purposes， the part， the part right after。

After the slash。So if I say right after the slash here。It is consulting。

This URLs py and it's got a list of URL patterns， if it starts withmin if it starts with poles。

 if it starts with hellello， if it starts with like autos or starts with sites。

 I know what to do with that in the second these other parameters are what to do with those things What do you do if the URL the root URL starts with s polls？

So right after the slash， well， it says， I don't know what to do with that， but if I say slash polls。

It does know what to do with that。 And so it knew how to do that based on this URLs do py。

 So it says if it's polls。 and so now I can say， Im going to say， I want to do polls slash this s。

 whatever。It will route it to the polls application。

 But then the rest of this stuff has got to be properly handled by the polls application。

 And that's what it shows It says the polls application reports back that it doesn't know anything about。

LDJ FJ， it just can't。 And so it's telling us the kinds of things it was looking for。

There was a bunch of things you can do to polls like poll slash owner， well。

 let's put that in there and see what it says， polls slash owner。

And I like keeping this debug message here。It's the 404 not found message。

 but now polls owner is routeutable inside a polls。 so let's take a look at that。So polls。ur。

 this is basically a defined import， it's been imported。Because of the settingstting。

 py that loaded up。Polls config。So if we go into my site polls。



![](img/30a594064e054ba2f5c2e079a229c4b8_20.png)

So now if we take a look at our picture。You know we just got done talking about the settings。

pyy and the URLs。pyy and now we're going to decompose one or more of the apps。

 so we have three apps here， each one's going to have URLs。pyy， each one's going to have you use。

pyy the rest of things they may or may not have but URLs is not the root URL because the my site Myight URLs。

pi is the root URL。So we're looking inside this application to route within the application。



![](img/30a594064e054ba2f5c2e079a229c4b8_22.png)

The part that's inside the application is after DJ4 Python anywherewhere。

com/ polls/ and then whatever you put in there， it looks up in the URLs。

 py in polls so let's go to polls and let's take a look at the URLs。pyy。And so what this is。

 this is really saying。The path within the application。 So this path right here is really。Slash。hos。

Comment， slash polls。With nothing。This is like。Slash polls。Two， so that's a primary key。

And let me push these out a little bit。Make them easier to see。

These are just comments that I'm adding to make it a little easier to see。So this one here is。

URs that look like slash poles。Slash two， slash results。And so what we're doing is。

The global myight Myight URLls。pyy defined find polls， but then within it we've got a primary key。

 we've got a primary key slash results， and we can do oops not that one。

I'll just add these as samples so you can see them。undSlash poles。Slash owner， which we just did。

And then。Slash poles。To slash vote。So and these are little slugs。

That are going to be passed into our view。Okay， so this is so Pk says followed by a number and then pass that number in and then the view。

The detail view is the view that we're going to use， and that's coming from views。

t Py from dot import views。So I'll just say this and just added some comments to make it a little easier to understand。



![](img/30a594064e054ba2f5c2e079a229c4b8_24.png)

So if we go back to our picture。If we have a URL that matches an application。

 then within the application， we look at the URLs。pyy to figure out the within application to route to one of the views。



![](img/30a594064e054ba2f5c2e079a229c4b8_26.png)

Okay。And so let's take a look at the views。pyy。And oh， let's go back to post stop URLs。bo。

So each of these names views。This is sort of an imported a file index view。 So we're looking。

 these things have to match index view， detail view results view。 It doesn't know what these mean。

 it could be whatever。 And there are two kinds of views there is a class based view index view is an example of a cat class based view and views dot owners and views dot vote our example in this particular case。

 a function based views。 So let's go find index view polls。Index view views dot P Y。Index view。

So see index view， this is the code now that runs if you just type。Slash pulls。

 So all that configuration conspires to get a URL running on a server to line 14 of your views do PI。

And we're using a generic list view， which means we don't have to write very much code。

 I won't cover that in too much detail， but the reason we use class based views is so that we can extend。

Views that are provided。From Django， and so from the generic views we're getting the generic list view。

And it turns out that all we really have to do is tell it what template to use and what is the context object name that we're going to put in here and then away we go。

And this query set is retrieving what we're going to show in that view。 so if you go back。

 this is a list， we only got one question so it's not very exciting and then the only thing kind of left in this picture is templates。



![](img/30a594064e054ba2f5c2e079a229c4b8_28.png)

And templates are like helpers to the view， but A of you can use a template。

 it comes up with data to paste into that template and so if we take a look at the templates， polls。



![](img/30a594064e054ba2f5c2e079a229c4b8_30.png)

TempNow， the name of this is kind of weird， just like my site， my site。

 The name of this is kind of weird polls， templates， polls。And then the index dot HTML。

This is injango template language， and this merges latest question list， latest question list。

 et cetera， et cetera。 And it loops through all those things。

 So I'm not going to kind of cover all that。 I'm just looking at the big picture about how this all works together。

T this。When when this part is all done， it returns in。

We don't see explicitly because it's just all part of the generic list view。 Eventually。

 it returns a response object。 A response object is passed back into Django。

 which is then passed down to the end user。

![](img/30a594064e054ba2f5c2e079a229c4b8_32.png)

And so that is a quick overview of kind of the flow of things going in and out。

 you may or may not have covered every single thing that is in this sample code。

 but basically I just wanted you to get us just go over one more time。

 all of the stuff that's in the big picture cheers。



![](img/30a594064e054ba2f5c2e079a229c4b8_34.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_35.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_36.png)

![](img/30a594064e054ba2f5c2e079a229c4b8_37.png)