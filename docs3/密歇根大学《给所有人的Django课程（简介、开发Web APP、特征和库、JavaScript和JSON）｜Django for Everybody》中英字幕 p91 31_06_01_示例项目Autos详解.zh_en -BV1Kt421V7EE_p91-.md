# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p91 31_06_01_示例项目Autos详解.zh_en -BV1Kt421V7EE_p91-

Hello and welcome to another dngo for everybody walkthrough。

 So you are probably at this point working on your autos assignment。

 This is our first real create read， update and delete assignment。

 and we're going to a lot of what this assignment is is to。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_1.png)

Look at the code I've given you in DJ free samples and pull it in。

 Don't do not clone the repository for this assignment。 The DJ free samples is a monster。

 It's got all kinds of stuff in it。 that's way too complex。 And you do not want。

 You want to start with a nice， clean application。 Your previous assignment was to make a really tiny application Now We're going to extend that application。

 And that's why youve already have this DJ4 E projects in your wherever it is。 okay。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_3.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_4.png)

And so so what this is is this assignment is to evolve that using the sample code。

 but what I'm really going to do is I'm going to walk through the sample code because there's new concepts in this sample code so this is more of a lecture about the sample code than exactly how to do the assignment but importantly you need to understand every single line because literally every program that we're going to write for the next end weeks is a variation on this crud right and so these views。

 these default views， the get or 404 all that stuff a really foundational things and we're going to find is the right way to write this code like everything in Django is really small and succinct。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_6.png)

So。Let's take a look at the code，'s just well let's go ahead and run the code。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_8.png)

Go to autos and you got to log in。 and so the idea of this is there are two tables。

 There is a table of makes。嗯。So I'm going to add a make， and then I'm going to add an auto。

 And the cool thing about this is this is neon1。Mileage 12，3，4， Sakai car。

And then I have this cool dropdown And so this is theres a there's a whole bunch of forms going on here。

 there's dropdowns， there's a many to one relationship going on。

 then I have this list and I can update it and delete it So that's where our full crud is and so we can add makes view makes add autos etc。

 so that's all the samples So it's very close to what it is that you have to write It's just don't go grabing all that stuff so let's start by taking a look so I'm here sitting in my DJfr samples。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_10.png)

And if you look， you see all of my various applications under a project， and so we've got the autos。

 but I really want to start with the authentication code， the code that。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_12.png)

If I go here。Back to samples。 Let me log out the code that allows me to log in。

 So if I go straight to autos， see if I've logged out Right。

 you'll notice that what it does when I go straight to autos is it routes me to log in。

 And then with the next to go back to autos。 So， so this view in autos。

 the slash autos has protected itself with login mixing。And so。

 and later we'll do logging your your login won't quite look like this。

 but this is the one I have on samples where you don't have to make it pretty yet an upcoming assignment is going to make everything pretty。

 So now we're at autos and we're logged in。And your application has to have some more things here。

 but I'm more interested in showing you really the essence of the views in this autos right so if we just let's just review Js briefly let's just review briefly about how the auto login works right so if I look at DJ3 samples/lash settingstting。

 py。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_14.png)

You need to have this offuth plugged in right though so that basically is that's a bunch of code。

 some views， et cetera that comes from Django， and that's been there all along when you did your start project。

Of course， then yes， somewhere in here， we've got to have the autos。Wherever autos is。

YeahAuts app config， you get to pull the autos app in。And if I take a look at Djfr sample/urs。pyy。

 then I can find autos here， and there needs to be some kind of a link that basically says。

At the top level。Everything below autos is delegated to the URL's file in autos dot P Y。

 But also then there is the accounts， right， And so you recall。

 this is a bunch of views that comes from Django for us。 It's pre installed for us。

 And the thing that we've got to do is we've got to build a a。

WeWe've got to provide this a template with the name registration。

htm so let's I think I've got this in home s templates。Registration， yes， I do。

So I've got actually two logins， I've got a really simple one is login。html。

 and this is the one I recommend that you start with later we'll use the social login。

And this is very simple。 it's a login page， it uses the Django formss capability if form do errors。

 that means that there is a validation error and it came back and redisplayed this page and showed you an error。

 and then we make a simple post form with a URL that is a reverse lookup to a view with the name of login then we put the CRRf token in and then we take the form and I'm just making this with paragraph tags and so that's a simple login。

 that's not the actual one that we're showing and then the next is a hidden value that you've got to pass in so that when you actually successfully login it knows to come back to autos when it's all done it come back here after the login has been done。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_16.png)

And so that registration slash login， you can put this in any of your applications。

But you want to name it registration/log。htm。 So if I take a look real quick and I go into home templates。

 these are all the templates。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_18.png)

When I do an LS， you'll see that I have a home templates home and a home templates registration。

You can add more than one folder here。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_20.png)

And if I do look at what's in registration， you see that I've got this simple login and then later the more complex login that will give us the GiHub login capabilities so we can log in using what that means is login use social The point is is underneath this templates。

 you don't have to just have one subfolder， you can have more than one subfolders。

And so that is the necessary configuration to make it so that when we tell our views to add the login mix in。

 which we'll see in just a second。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_22.png)

we tell our views in the login to use the login mixing。

 then it knows where to get the template from so that's just part of it and your instructions tell you how to do that so any application that you're going to build or any project you're going to build you have to put those in settings py URLs。

 py and then make the template and then you have to start using login mixing and then everything just magically starts coming together so let's take a look at the actual autos application will look at a couple of different things here。

Auts slash URLs。And I'm going to do a multi， I'm going to tab。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_24.png)

So I can switch back between files really fast， you probably have a better text editor than me。

 so I've got URLs， I'm going to take a look at the views， nope， nope， nope autos。Use dot Py。

Then I'm going to look at Auto's model Py。Models do P Y。 And then I'm going to look at。Auttos。

Forms dot py。And so let's sort of work through these four files， URLs， views， models。Forms。

Probably let's do models first。So this is pretty straightforward。 we're going to make a make。

Object class， it's going to have one character field with some validators in it。

 we kind of played with that with forms， you can put validators in models。

 we've previously seen validators in form， but there's a validator that basically says。

We're not going to accept data coming into this database table unless there's at least two characters。

These underscore， underscore SR， you've been doing this for a while。

 That basically is if you take a model object on actual make and you print it。

 It says which of the fields in this case， there's only one field。

 And so that just says when we're converting a model to a string。A model object to a string。

 we get to decide how that looks。Okay， and then we have an an automobile and it's got a nickname with a in length validator。

 max length of 200， a mileage， which is an integer field， a commentss。

 which is a 300 character field， and then a foreign key。

Into this is a one to many or many to one relationship， not a many to many。

 just a foreign key and to make。 And then we're going to undlete cascade。

 which really means if you delete a make， then the corresponding auto entries will automatically be deleted。

 And so this is a pretty straightforward model， actually very， very simple。 And once again。

 we're always defining this stir underscore underscore self So that we know that we're just if。

 if you're just showing it like in the admin interface。

 or if you're just printing it or just converting the model itself to a string。

 the field among these fields that is supposed to be used is the nickname field。

 just to show to end user。 So that's the models file。Let's look at the Form file next。

 so the forms file is interesting because we've seen forms that are just forms by themselves。

 but this is a special kind of form and then it's a model form in that we normally in the other models we had all these fields right and we put them in and it looked a lot like a model file where we'd have a character field。

 a positive integer field but what we're basically saying is you know what we're going to make a form here and really。

All we are want to do is take all the fields from the make model and make them form fields。

 So a form and a model are two different things。 A form is something that goes between sort of the view and the template。

And as you'll see it also goes down into the models automatically。

 but you got to so this is just like make all the fields right let's make a form because form objects don't have to be associated with models but in this case we're going to sort of derive a form object from a model and so instead of extending form we're extending model form。

 so that's a model form must have and this is just some data that says the model that we're going to pull all our fields from is the make model。

It only has one thing， which is a name that's it Okay so this is auto generating a form that if we changed it and added another field here。

 then this make form would automatically have a field， you can give it a list of fields underscore。

 underscore all underscore， underscore is like a signal to say a just give me all of them now there might be some internal things like created a or updated at or something that you don't want to use。

So that's a form。😡，Remember how forms work？Cover that before。Let's take a look at our URLs。 Now。

 a lot of this looks pretty similar to things that we've done， right we。

We basically have a main table， which is our autos table and our lookup table。

 which is our makes table and we have we have sort of three things there is the main list list view which is list all the autos there is the main the make list view which is list all the makes and then we can make a new one which doesn't have a primary key because part of the idea is the create is making a new thing which is going to generate a primary key and then we're going to have an update and a delete and so we have a read。

Up createate， update， delete， so it's not exactly crud。

 but you see all four of these things and so we've got views and we name these views so that we can reference them in in our views themselves and in our templates so we can make links in between them okay。

Okay， so these these are pretty straightforward and not all that different。

 so the fun starts to happen when we're in the views。 py。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_26.png)

So。嗯。Login mixin， if you require remember from the author author Z walkthrough。

 you just add this to a view and it just basically says you cannot get to this view unless you're logged in and if you aren't logged in it will bounce to the the login do HTML file and then bounce back after you're done and so login required mix in is all we need to do if you go with the off Z sample。

 you'll see like I did that by hand， but you don't want to do it by hand， you just call login mixing。

ow。So this main view is a list view。 and so let's go take a look at what this is going to look like。

 This is the list view。 So we're going to take however many autos we have we're going to loop through that list we're going to retrieve all the autos from the database that we're going to have an add the auto link then view the makes link with account of how many makes there are and add a make。

 So let me also then。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_28.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_29.png)

Go into autos templates。Templates。Auttos again。 Yeah， I'm sorry about that。 And auto list。

So this is the template that makes that。 And so there's a few things that we get。

 We get an auto list。 Now， the names of these are not。Forced upon you。

 but there's conventions that turn out in a moment are going to look really useful， okay？

So we're going to get an auto list and if we go back into our views。

 we see that we say get all of the objects from the auto table， all the auto class objects。

 retrieve them all， pass them in to the context as auto underscore list。

Now we also want to be able to show that little count this number two。We're going to ask。

 go ahead to the make objects all， but don't give me a list of them。

 count them and give just give me a number， so make count is stuck in there and you'll see。

If make count is greater than zero。嗯。We can show the add an auto button。

And it also somewhere yeah shows the make count， view all the make add a make and the make count comes out here。

 so that's another thing we put in the auto list we're going to go through and that iteration variable of auto is going to go through each of the separate things and nickname make etc that's right straight out of right the models do py file there's the four things that every auto has and we're just printing all this stuff out。

You also get the primary key， and so we're going to make an update URL。

And that URL is to autos auto update so if we look in URLs。pyy。

 we see this auto updateate looks up this gives us a path to the view。

 but that particular path needs one parameter， which is a primary key。

 and so that means that this URL template tag。Auts has to have the auto ID。

 but because we're looping through the models， you got one， right？So and you do an auto create。

 that's pretty straightforward， but one of the rules is is you have to have at least one make before you can do an auto because if you recall add an auto has to have this dropdown that's poptable and that's being pulled from the make table。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_31.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_32.png)

ok。And so that's basically the way around this， that's the main view。Now。

Just like I showed you before， it turns out that there are。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_34.png)

Here we go。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_36.png)

i create。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_38.png)

Yeah that's the auto's view。And then if we do the make view。

We're doing the same kind of thing if we go and look at the make list。

 we're doing the same basic kind of thing view all the makes this is the。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_40.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_41.png)

And now we got update and delete。We are this way you don't need to count。

 We just want to grab all the lit， all of the objects。

 We want to put it in a context under make list and then。We do make list under HTML。

And this is even simpler。It's just going through the make list， it comes in through the context。

 if there's none， we don't print this out and then we put out the name of it and then we have an update and a delete button that goes to the update and delete and of course those if you look in URLs。

pyy， those also the update and delete have primary key requirements。

And so you have a primary key that you got to pass in here to make that URL the proper kind of URL。

And then just some links to go back to the various things so that we can you know， get back to autos。

 ViewMakes， add a new make， you know， cancel all that stuff。ok。😊。

So that is the views dot py for listing the autos and the makes okay。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_43.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_44.png)

Now。We want to make the make create View。O k。So if we take a look at the make create view， that is。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_46.png)

Atmic。That's going to create。This form。This bigger here。

ComCreate this form where you're going to put in a thing called Chevy。BY。

So we need to wait to make this form， right。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_48.png)

We are going to we're going to make it a login required。 We're not going to let folks do this。

 We're going to have some variables that are class wide。

 like what template we want to use and success URL is after we have done this right now。

 if you just submit it and it complains， it doesn't do it。 But once you've done it right。

 where do you want to go afterwards， So Chevy。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_50.png)

Where do you want to go afterwards， This is controller function Bo。

 I want to go back to the auto list。 And so the success URL is go to autos colon all。

 which in URLs dot P Y， is this main view。 That's the name of the main view。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_52.png)

Okay。And so if we go here， the， which template to use and which。Which success URL l。

If we do a get request。We're going to build a form for the make that comes from make form。

 but really， it comes from。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_54.png)

The make model， which is just one string field。 as simple as that， right， We're reusing this。

 We're just saying， let's make a form that pulls from here。

 We have to pass a form in because models can't be used to create this kind of a screen。

 That screen comes from a form。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_56.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_57.png)

Okay。And so if we take a look at the template。If we look at the。Make create template。Oh， make form。

So that is yeah， that's the template we're going to use to make form。

We're going to need form as table right so that that's from how we did forms， put the CSRF token。

 you make a table that could be as paragraphs or as tables， but whatever you need this form object。

 so you need to pass the form object in and so here we are we're going to make a form and then we're going to pass the form object in and then we're going to render it to self。

 template autos。make form HTML。And then we're going to return that for the get。

And then when we hit the button to submit button。At a make， we hit the submit button。

It's going to do。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_59.png)

It's coming into the post because we made a form post comes in。 We're going to take theop。

 don't do that。 Oh， that's terrible。 I hate it when VI does that， but here we go。 we're back。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_61.png)

Yeah。So post comes in， request post has all the key value pairs。

 which are these key value pairs as defined by the form。

So we say let's make a make form with the initial data coming in from request post and given that the form generated it。

 it knows what the names of these fields are， and this is something that hides behind how forms work。

 but it also checks to see if the form data is valid and that means where all these validator rules followed if the validator rules are not followed。

For if not form is valid， we're just going to send it back。 And so if I so this code here。

 this if form is not valid code， if I put in a single letter。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_63.png)

a and hit submit， it's going to come back and re rendernder the form and all that error stuff。

 all that stuff is all handled by this form code。 this Django form code figures out what is wrong。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_65.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_66.png)

Let me move this over just a little bit so I can get back to it faster。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_68.png)

There we go， it figures out what's wrong with it， makes an error message。

 the error message came from models。pyy。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_70.png)

Right here， oh no， right here。And then went through forms。

pyy because it is a form ultimately that we inherited from model form。Get it。And so that's cool。

 So that's the error condition。 And otherwise， we do form do save。 Now， the thing here is。

 it's really super cool is because this form is a model form。 it knows。😊。

And the field names are the same as the field names in the model。

 And so it actually does a save on the model itself。 So in a way。

 the form contains the model data that came from the post request， and then it saves it。Okay。

That saves the form， it puts it in， and then we just redirect back to the request URL。

So this is pretty succinct。你。We pull in the old pull in the post data， we check to see if it's bad。

 if it's bad， we send it back to send the form back to the exact same template we did。

 and then we save it if it's good， and then we pop to the success URL。That。Is a beautiful thing。

But just like injango all the time， this is a far wordier thing to do。

 even though this is super succinct。 if you did this in any other， almost any other language。

 you'd be like。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_72.png)

You know， 75 lines of code， and here we have like 15 lines of code。But it turns out in Django。

 there's almost always a more succinct way to do it。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_74.png)

We have a generic create view。 You can take a look at the documentation for this generic C view。

Chango views generic edit， let's just go and go and Google this stuff。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_76.png)

I always just put a dot here and this usually gets me right too because that's the actual package in the class inside the package。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_78.png)

Oh no， oh no， sorry。It thought that that was a domain name。 so the search didn't work。

But now I'll just say， you know， Django， something look like。

 so at least it's going to do a search for me， generic editing views jump to the C view。

So you can read through all this stuff， right， generic create view。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_80.png)

Actually， let's make a。Do I have a reference to this？So there you go， take a look at that。那。This。

 just like some of the other views that we've in inher have a ton of functionality in them。 So if I。

Want to do an auto create。This is all it takes。Now autout createate and make create for all intents and purposes。

 do the exact same thing。So what happens in auto create because we're extending create view？

We have3 bits of metadata。 We tell it which model we want to use。

Which fields from that model we want and where the success URL to go is。 And then this generates。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_82.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_83.png)

All this code。 We inherited all that code。 You'll notice that there's nothing hard coded in here。

 except the make form。 Now， we don't even have to make a form for the auto。Because。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_85.png)

This code right here builds the form。And not only that， but it uses this name Mo Auto。

To pick the template， so if I do auto underscore form。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_87.png)

I have to use this right， I use this， there's my base boots strap， don't worry too much about that。

And so it knows the name of the template that it's going to use。

 I don't even have to tell it which template to use in here because it derives the template。

Auto_form。 HTMLt is the template。Pretty cool huh， pretty awesome and cool。

So it automatically finds that。And the success of URL。

 And so this is all that's needed as a matter of fact。I could in this make create。

I could have deleted all this code from here to here， but instead just do a create view。

By extend create view。 So I'm just showing you this because I want you to see。What's really going on。

 but this is not how you write your code。😡。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_89.png)

This is how you write your code。Okay， so now I want to show you。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_91.png)

The hard way of。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_93.png)

Doing an update。 So what's an update， Let's take a look at the code。

So let's take a look at ViewMakes。Update is the thing。

That happens when we go here and that's going to go to make update。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_95.png)

So here's make update， here's URLs。pyy， it's this one main， I mean， yeah， look up。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_97.png)

Primary key update， which then if you look under here。

 it's going to be Autos lookup1 update right so I'm going to update the Chey one。

It has to read the old data， has to show it to you。And then let us update it。And then submit it。

 checking， of course， for any validation errors， and then redirecting us back to a Su URL。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_99.png)

So if we look at the views。We're going to again foreshadowing， there's a much easier way to do this。

 so we set these variables which the success URL， which template we want in the model。Okay。

 and then we have a get request and because in the URLs do py， there's this NP PK。

Were passed in this Pk value。Now， this skit object or 404 is really cool， okay？So self dot model。

 oh wait， sorry， this Git object 404， self dot model Pk equals PK， that's this parameter。

But we're passing PK equals and it's common that they are the same name。

 but this is a parameter to get object or 404， the second one is the parameter that was called to our get。

Self dot model， of course， is make。right。And get object or 404， basically checks to see if。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_101.png)

So I'll do this update， and let's go to makess。Let's do an update。

And what is's doing is is taking this number， this three here。Auttos lookup 3 update。

 and it's retrieving the old data。Now， what happens if I。

 if I inadvertently have a number that doesn't exist in database like 9999。

 and I do a get request to that one。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_103.png)

I get page not found 404。Right， and so what's happening here is somehow。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_105.png)

You say， hey， load this object and give it to me in the variable make or just blow up and send out a 404 error。

 right？

![](img/607c0b39ee9e4dd20c9c2c60affe5347_107.png)

And so this is telling you what's going on， which view you just know make matches the given query。

 Now， generally， you're not supposed to hand tight these。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_109.png)

3 works， and so it doesn't blow up。 so Git objectject or 404 is a way of loading the old data and then protecting。

 you know using that data or just blowing up。 so don't go any farther at that point。Now。

Then we're going to make a form and we're going to fill it with the old data。

 So instance what the instances make。 So that's the object。 Make a make form。Here's a make form。

 all the fields from the model make。And then pass it into the template， makeform。 HTMLtm。

 which we just looked at。This form comes in， that's all we need， this is very generic looking。

 it really doesn't care too much， it's all pretty much encoded in this form。

 which is derived from the model。Then of course， we type a bunch of stuff in。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_111.png)

Blah， blah， blah， and we hit submit。And it does exactly the same thing as the create。

And then it it does well， first it has to do a get or 404 because we post to the thing that with the primary key。

 we load it up to make sure we have an object to update。

Then we create a new make form from that database and then change it。

 So this is like this is the starting data， but then it alters it to the data。

 So in this particular case， Chevrolet is the old value in the database。 And if I say。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_113.png)

Bow tie。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_115.png)

Request post will have bow tie。 This will start a Chevrolet， but in this form object。

 then it will be bow tie。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_117.png)

Of course。If it's not valid， we're going to return an error message right back here。

And if it is valid， we're going to save it。 And so this new bow tie is going to be saved。In there。

 and so if we view our makes， we see that it's now bow tie。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_119.png)

And we're going to redirect to success URL。Now， at this point。

 I would hope you could predict about what's going to happen next。Aut to update。

Extends updatedate view， the generic editing view， it says which model it is， which fields you want。

 and where to go when it's successful。Okay。😊，And then it does everything that's in here， right。

 does everything that's in here。And literally， I could go and say the exact same words for make delete。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_121.png)

Which is what happens when you go in here and you delete。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_123.png)

And then you have a cancel。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_125.png)

There is a oops。There is a confirmed delete and the name of this template。Is not randomly chosen。

 It's got to be called the confirm delete the model， confirm delete right， and there you go。

 you got a CSRF token。 you're given you're handed to make as an object in this so that produces。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_127.png)

This output， there is no form in this one。 there's just the make that gets loaded。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_129.png)

By object or 404。And then it passes make in and renders it and then when the post happens。

 it retrieves it if it's there with a 404 again checking for bad data and deleting it and then hopping off to the Succ URL and it doesn't take much to guess what I'm going to do next and that is if you extend delete view you get all that code for free。

 you just tell which mono fields and where to go for success。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_131.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_132.png)

And so the key thing is as you're doing your homework。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_134.png)

I'm sure some of you are just going to like copy and paste all this stuff。That's wrong make create。

The make create， the make update and the make delete should be as short as auto createreate。

 auto update and auto delete because you're going to do this a lot right you're going to do these generic editing views a lot and we're going to crud over and over and over again and you really do not want to write 15 lines of codes that's unnecessary repetition unnecessary cutting and pasting and changing code if you can keep it really simple so I can basically build a full set of crud forms and crud functionality with validation。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_136.png)

For a model with this kind of code。 And then I don't even have to have a forms dot Py。

 I just have a models dot py。 So if you're doing your autos。

 you kind of would think I made a mistake if I'm making a forms dot P because if I just use this views dot Py this way。

 instead of making all of them look like。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_138.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_139.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_140.png)

Make update。Then you're going to save yourself a lot of time and energy and we have to modify these things。

 it's a lot easier to find all the changes and then modify them。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_142.png)

So that is a walkthrough of the sample code。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_144.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_145.png)

For autos and you're going to do an assignment on this， but。You know don't just copy everything。

 I set this up so that the time you spend understanding what's going on， particularly in the views。

 right URLs， you'll probably just copy models you just copy the URLs you'll just copy。

 but the views don't just copy it， figure out what's really going on and come up with the easier and more succinct way to do all this stuff。



![](img/607c0b39ee9e4dd20c9c2c60affe5347_147.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_148.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_149.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_150.png)

Because this is Djainggo is starting to look really beautiful at this point。

 so I hope you found this helpful， cheers。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_152.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_153.png)