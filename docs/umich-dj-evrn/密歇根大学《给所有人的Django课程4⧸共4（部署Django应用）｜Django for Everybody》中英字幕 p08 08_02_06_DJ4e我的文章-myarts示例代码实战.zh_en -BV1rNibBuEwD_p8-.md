# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p08 08_02_06_DJ4e我的文章-myarts示例代码实战.zh_en -BV1rNibBuEwD_p8-

![](img/be22e7f381c283e91cf00876c37f4d57_0.png)

Hello and welcome to a walk through for Django for everybody。

 So the walkthrough that we're going to be doing is the walk through for the my articles。

 which is really focusing on the notion of owning rows。



![](img/be22e7f381c283e91cf00876c37f4d57_2.png)

![](img/be22e7f381c283e91cf00876c37f4d57_3.png)

In a model。 And what I've got going here is I've got， I'm logged in twice。

 I'm logged in one with a user I of one， and the other is a user I of two。

 So let's just do a quick demonstration。Of what really owning rows in a model is。

 So here I'm logged in as my first user， and now I'm logged in。

 I'm using a separate browser because this is safari， and this is Firefox。

You can't just do this with tabs because the cookies are shared between tabs and so you cant you can log in and log out。

 I want to just be logged in simultaneously。ok。And so。These tabs。Refresh， so you'll notice that。

The edit and delete buttons show up differently for different users and that' because this row in the table lawnmwer belongs to this user user number2。

 and this row these two rows belong to this user。 So if I take a look at administration and I go down into groups。

 oh not groups， not groups。

![](img/be22e7f381c283e91cf00876c37f4d57_5.png)

Users。

![](img/be22e7f381c283e91cf00876c37f4d57_7.png)

Now I can kind of hover， figure out that C7 is two。

 you can kind of see the bottom there and DJ furry is user one and C7 is user number two。

 so those are the primary keys in Janjango's user table and now if I go and I take a look at these articles。



![](img/be22e7f381c283e91cf00876c37f4d57_9.png)

![](img/be22e7f381c283e91cf00876c37f4d57_10.png)

You will see。 And this is looks a lot like if you were looking at， say， your autos。

 here's the brose or the models in articles。

![](img/be22e7f381c283e91cf00876c37f4d57_12.png)

![](img/be22e7f381c283e91cf00876c37f4d57_13.png)

And if I look at lawnmer， you see that there is a title， some text， and the owner is a drop down。

 And that's because this is a one to many field。 This is a one to many field between the articles and the users。

 And then if I switch to a different。 So so that so that's。



![](img/be22e7f381c283e91cf00876c37f4d57_15.png)

![](img/be22e7f381c283e91cf00876c37f4d57_16.png)

![](img/be22e7f381c283e91cf00876c37f4d57_17.png)

Cive。

![](img/be22e7f381c283e91cf00876c37f4d57_19.png)

So C7 owns the lawn。Yes， Caones the lawnmower。 I must be unlockgged in as DJ free here。 Nope， here。

 that's my name on DJ free。 And if I switch to trombone， we'll see that that one belongs to DJ free。

 Now， I can sit and edit this in admin。

![](img/be22e7f381c283e91cf00876c37f4d57_21.png)

![](img/be22e7f381c283e91cf00876c37f4d57_22.png)

![](img/be22e7f381c283e91cf00876c37f4d57_23.png)

But that's not the point， the point is to build software。



![](img/be22e7f381c283e91cf00876c37f4d57_25.png)

If you'll notice when I create a new article。It doesn't ask me what user it was， right。

 So this is where you would say dodge or whatever when you were doing cars。

 So this is like a race car。Slightly used。呢啊。So now I have another one， right。

 And so the key thing was is it looks like a create from things we've done before。

And if I look at my articles， here's this。 But somehow magically， this owner field is populated。

 And that's the essence of owned rows。 as we've got a row， a column。And we these are marked。

 and we know in all our code， we know the difference， for example。

 between things we own and things we don't know things we own and we don't own。

 So if I hit refresh over here， there's a slightly used race car， but。



![](img/be22e7f381c283e91cf00876c37f4d57_27.png)

Yeah。Slightly use race car， but I can't edit it， right， so that's the ownership。Now。

 I don't know where to start。 There's a lot to cover here。 Let me show you。Let me show。

 I I don't know。 Okay， I'll just start with where we always start。 Let's start with。

I' running this locally。 I know if that bug is there。 that's not a bug。

So this is just looks kind of like your autos。 If you look at it。

 it looks pretty much like the autos， am might then a mileage or price in there or something。

 The only thing that's really different at all is this。 There's a foreign key now。

 in your autos you got a foreign key to makes。And the key difference here。

 the only thing that's new is this idea of where the foreign key is pointing at。

 Now the problem is in Django， there is actually a table that all these users live in。

 and I can probably come over here and type tables。



![](img/be22e7f381c283e91cf00876c37f4d57_29.png)

And I can see it。 I think it's probably here。 So let's just try saying select。Star from off user。



![](img/be22e7f381c283e91cf00876c37f4d57_31.png)

So we should see a bunch of rows。And so they're my users， C。

 you kind of it's all jammed together in DJ free， So this is row 1 for DJ free and CE。

 So there is a table in a model。 The difference is is we're not allowed to know that this is the user model in the off application。



![](img/be22e7f381c283e91cf00876c37f4d57_33.png)

And so what happens is we have to let Django tell us what the name of that model is。

 and so we go into settings， which is settings。 py actually， and we're going to pull in the settings。

 py and the default is off user model and that's the name of the model。

And so this is the foreign key to a place that we don't exactly know。

 But Django will tell us and put in a string here。 if we were to print this out。

 we would see what that is。 That's just a string， but it's not a string we mess with。

 un deletete cascade， that's just normal， the kind of apparent row， the one row is in users。

 And if you delete a user， that means that all of the rows that belong to that user will get deleted because on deletete cascade。

 I'm choosing that as the as the model。 And so you see。

Created a if we go into back into the you see all of these things now created it。

 admin doesn't show it it's pretty smart knowing about C a and update so it doesn't bother the doing that and it actually upts them automatically so it knows something about created at and updated a in admin。



![](img/be22e7f381c283e91cf00876c37f4d57_35.png)

![](img/be22e7f381c283e91cf00876c37f4d57_36.png)

![](img/be22e7f381c283e91cf00876c37f4d57_37.png)

![](img/be22e7f381c283e91cf00876c37f4d57_38.png)

Okay。So。

![](img/be22e7f381c283e91cf00876c37f4d57_40.png)

That is our model。If we were to take a look at。

![](img/be22e7f381c283e91cf00876c37f4d57_42.png)

Why arts article。You will see that there is a foreign key right there， there's a foreign key。

 and if we say select star from my arts。

![](img/be22e7f381c283e91cf00876c37f4d57_44.png)

Article。You will see that there is a foreign key in there， So this row belongs to user 1。

 This row belongs to user 1。 that row belongs to user 2， and that row belongs to user 1。

 which is perfectly reflected here。 So now I am user 1 so I can edit three of them。

 now I am here with user 2 and I can edit one of them。 So I'm editing the ones or I own it。

 So ultimately we're going to write a bunch of code so that these numbers are properly updated。

 So when you add the article， it works the way you want it to work。



![](img/be22e7f381c283e91cf00876c37f4d57_46.png)

![](img/be22e7f381c283e91cf00876c37f4d57_47.png)

Okay， so let's just take a look at URLs。pyy。

![](img/be22e7f381c283e91cf00876c37f4d57_49.png)

It's pretty boring， it looks just like autos， I probably hoisted up success URL here。

 put that in the as view as a parameter， and so that makes my views even simpler。嗯。

My arts colon all points to that view。 I think it actually kind of preier to put it in here because this is sort of a URL place。

 And so it's not in my view。 So that makes my views。Release aint。And so。It's。

 it's like what you did once you got your。Auttos down to like just using the generics。

And so I have a list a detail a C and update and a delete。And I have a model called article。

 which I just showed you。 and I am going to reuse some general purpose views for owner kinds of rows。

 Now， these are not from Djanangle。 These are from me。 I made them。 and now I'm using them。

 So article list view extends ownerless view。 and then I can put all my things in there。

The the success URL， actually， I don't need that here， but for create view， I do need a success URL。

 but for create view， that success URL comes right from here。

 So I could have put it either here or I could have put it here for me。 just kind of after a while。

 I think this is prettier because now I can look all all the names of my arts， et cetera。

 So that's kinda nice， okay。So。So here's views。 we're going to come back to this。

 All the brains of this operation are in ownerless view， owner detail view， create view， update view。

 and we'll look at that last。 So that's where the hardest part is。

But let's first look at the template。So here's the template。This looks a lot like your autos。

 The only real difference here is that that this edit and delete button is inside of an Ist。So it's。

 you know， article update， article ID， article delete， article ID， that's the same you've done that。

 right？But if all it says is if article dot owner is equal to the current loggged in user。

 article dot owner is one of the article list， and that's just one of the fields in the model。

 which happens to be a number。But。We are given this user for free， right， It just hands us user。

 And so we can compare it。 So if this is one that we own。

We show this link and if it's not one we own， we don't show the link right。

 so we don't show the link for the ones that we own now。I hope by now you realize that merely not。

 we have to also protect。Right so if this is number four。Right， and if I click edit number five。

 but what if I just change this to four， we still just just not putting up the link does。

Does not mean。That we can't have someone go to that link， so I'm cheating by putting in this link。



![](img/be22e7f381c283e91cf00876c37f4d57_51.png)

But this is going to blow up， right？ And so we'll show you how just by just because you don't put the link up doesn't mean that people can't go to the link。

 They can guess what the link is。 I just did that。 I went to an article I could update。

 I noticed the primary key of 1。 I could not update to be 4。 And then I went to 5。

 And then I just edited， changed it to4。 And I attempted to update 4。 So it's not good enough。

 just to not show the link。 That's actually not security。 That just is prettiness usability。

 Don't show a link if it's going to blow up。 If you click on it。 So this's not really protecting。



![](img/be22e7f381c283e91cf00876c37f4d57_53.png)

Us， this if statement is not really protecting us from clicking on or attempting to go edit or delete is just not showing it if it's not going to work。

Okay。And again， article。 owner is just a column in this model and user is the current loggedin user。

Okay。😊，ok。So。What we'd seen before is I would create a view and then use it in my URLs dot P Y。

 and they would extend another view。So now it's time to take a look at where this view is being defined。

And so here's our view， generic view， the generic lists view， delete view。

 These are the generic ones。 And all I'm really doing here is I'm creating a class called owner list view that extends listist view。

Now。It pulls in everything that list view is， and you'll notice I've added nothing to it。

 And I really could， because the list view doesn't really care。

 It's not really doing anything other than the fact that that value is in the models。

 so it's going to come in right so I could have made this be list view。

 but I just want it to be create。 I want to make it so that I could just say ownerless view。

 owner detail view。

![](img/be22e7f381c283e91cf00876c37f4d57_55.png)

And so you'll notice that I'm not making any changes at the moment of inheritance。

 I'm not changing owner。 So owner list view is exactly the same as list view and owner detail is exactly the same as detail。

 I just did it to make it pretty。 In case later， I maybe I want to add some。

But now we get to owner create view， owner C View is something that matters a lot。



![](img/be22e7f381c283e91cf00876c37f4d57_57.png)

So there's two things we've got to do for owner create View。

 so let's go ahead and start to add an article。So the first thing is， is there is no field here for。

Which user it is， it would be kind of silly， and I can actually mess this up。



![](img/be22e7f381c283e91cf00876c37f4d57_59.png)

So if I go to create View here。And I add。User。Then if I hit refresh on the create view， come on。

Make back up。

![](img/be22e7f381c283e91cf00876c37f4d57_61.png)

Oh， it's not user。Owner。

![](img/be22e7f381c283e91cf00876c37f4d57_63.png)

So if I add it to that list and part of this， what's going on here is there is both a model and a form。

 this field equals is informing the form， and the form is the user interface。 So look at this。



![](img/be22e7f381c283e91cf00876c37f4d57_65.png)

I， I'm allowing the user to specify it。 And now they can set the owner pretty convenient。 Well。

 that's not what we want。 So that's why in this create view， you say， don't let them set the owner。

 I don't want them to see the owner because it takes a little while for this thing to restart。 Okay。

 now it's restarted。 And I can hit refresh。 So it is blowing up。

 It was just because I was coming here too fast。 What is that。



![](img/be22e7f381c283e91cf00876c37f4d57_67.png)

![](img/be22e7f381c283e91cf00876c37f4d57_68.png)

![](img/be22e7f381c283e91cf00876c37f4d57_69.png)

I know what that is。So。So go back to the views。I must maybe I have some tiny little bug。

 I'll dig through that bud later。It's working。And it's probably passing the autogrator。

 so I'm pretty happy。So。Remember that there are two sides to this。 One is the database side。

 and that's what the model deals with。 And then there is a form。 So these views， this list view。

 if you recall， once we tell it。Once we tell it the model， it actually makes a form。

 So in this create view， it's making a form from article。

 copying all the fields in article or the fields， according to this little list。

 And so that's why we're doing it。 So the key there is we're explicitly not putting owner in there。

 and we're not putting created at or updated at。 If I wanted to put created at in here。Id say， hey。

 let's show I created at。 Okay， let's refresh， refresh， refresh， okay。哦 ok。So， again。

 is trying to take a mo trying to go to from the article model to make a form。

 And it's not an editable field。 So it's mad at me。 So I'll go back and fix it。 I'm sorry。

You get the idea it uses this list of fields to make a form。The same for article and for update。嗯。

That fact。The update and the create are so equivalent that the template for them is shared。

It's basically。We'll talk about crispy tags separately in a different little video。

The form is the same。 The difference is when the update comes， there is already data in it。

 That's the only difference between a create and an update。It looks exactly the same。

 but update has data in it。 a create has no data in it。

 so the code between create an update is super equivalent。Very， very similar。

 And the template is similar as well， okay。So there we go， so we got create view， delete view。

 etc cea now。I want to focus on create for。And the key to create view is now in owner dot P Y。

 here's our form that's pretty straightforward in owner dot P Y。



![](img/be22e7f381c283e91cf00876c37f4d57_71.png)

This create view now has a little bit more to it。 The list view and the detail view just inherited。

 So the first thing is that create view has a login required mixing。

 And that's because if you're going to create it， you need to be a logged in user。 But to view it。

 you don't actually have to be a logged in user。 or if I was to。



![](img/be22e7f381c283e91cf00876c37f4d57_73.png)

Okay， let me log out here。So non lock logged in as anybody。 And so I can see all these。

 I can't edit any of them。 I could log in if I want， and a detail view also works。

 So I'm completely logged out here， but I。Oh， add article。 Yeah， so add article is protected by。

An article is protected by login。So owner create view。Wna create view。Loin required mixing。 And I。

 I do this because I don't want to trust the user who's writing this view to put the login required mix in here。

 because I am writing code right here that depends on the fact that this person is logged in。

 So this is like a guardian pattern。 if I'm putting this in here。

 So I don't end up with tracebacks inside my code。 I don't want， if I didn't put this in owner。

 if I didn't put login required mix in and owner create view， then。

They forgot to put in the views dot Py they forgot to put it in an article create view。

 Then this code would blow up， it would trace back at when I tried to set object owner to self request user。

 it would just blow up， okay。十。🤧嗯。So I'm extending create view。

 which is inheriting all the functionality。 and I'm only going to override one method。

 This is object orientation。 the and you got to go read all the documentation。

This documentation right here。Show you that documentation。Do。ピ。So， you know。

 this documentation is hard to find， and I'm sure I helped myself by doing some stack overflows。



![](img/be22e7f381c283e91cf00876c37f4d57_75.png)

So that's why I put little notes at the bottom of the file。

 the things that took me a long time to find。

![](img/be22e7f381c283e91cf00876c37f4d57_77.png)

So this form model mix in。 and that is what they're really doing is they're giving us for these editing fields。

 like the update， they're saying。They're saying， these are the functions that are in this。

 and I can override them。So the one that I'm overriding is the form valid。

And what that does is it basically says here's your form。

 save it to the database and set the current object for view and then redirect to get successs URL。

Okay， that's its job。Except that right before it's going to save the form instance。

 I want to do something myself。Okay， so what I'm doing here is I'm saying。

 and the form is what's being called as the parameter。

 which is the form that has been pulled in from the post data and handed to me。

And so what I'm going to do is I'm going to say save it， but don't save it to the disk。

 That's what commit equals false means。 Don't save it to the database。

 Just save it into this variable object。 And then I'm going to set the object owner。

 I'm simply going to copy the current logged in user into owner。

And then I'm going to set it to the database。And then what I'm going to do is I'm going to call the original form valid passing formin as a parameter that's in。



![](img/be22e7f381c283e91cf00876c37f4d57_79.png)

This class。And that's really not going to do much， right。

 because I it's it knows that it's already been saved。 So it's not going to save it again。

 And then what it's going to do is。

![](img/be22e7f381c283e91cf00876c37f4d57_81.png)

It's just going to do the redirect to the success URL。

 So this is rather late in the process of create view。 It's been validated。

 It's checked for band data， et cetera， et cetera， et cetera。

 And so this is like right before the redirect happens， okay。And so the at a high level。

 my whole goal was to pause the saving of this data to the database and sneak the action current login user into the owner column and then be done with it。

 And so that's the basic overr。 I'm really extending form valid to cause my code to be or to be called right before the default code is called okay。

Okay， so that's owner create View， and that's how once I add an article。And put some stuff in。

 and I submit right as I submit it。 And right before it saved。

 there is a little field called owner that's going to be updated。 and it's there。

 And so that's the owner field came from this code。 Now， I don't have to。 I could have put this。

I could have put this in this view dot Py， but no， I got this really awesome， crable thing。

 I can write really cool code I'm going to make hundreds of views that and we will through the rest of the semester do this over and over and over again。

 we're never going to change this file again。Okay。😊，So now let's talk about edit。Okay。

 so so there's two things。 So here we're going to load Article 6 and then we're going to put out a form that has all this stuff。

So the first thing that's got to happen。In owner update view is we got to check to see if。



![](img/be22e7f381c283e91cf00876c37f4d57_83.png)

This belongs to the current logged in user。 Remember when I tried to go to whatever it was for here and it blew up。

 this is the moment where I'm going to protect it。

![](img/be22e7f381c283e91cf00876c37f4d57_85.png)

So if we take a look。

![](img/be22e7f381c283e91cf00876c37f4d57_87.png)

At the moment where it's loading the model， I I have a link to that。Anangle populate。

 Let's go to a stack overflow here。 That's what I got from stack overflow。



![](img/be22e7f381c283e91cf00876c37f4d57_89.png)

Been there 10 years。 Probably a good one。嗯。

![](img/be22e7f381c283e91cf00876c37f4d57_91.png)

Middleware。Someone here， I should make that link be a better link。Oh， I like this one。

I'm going to put a link in just to this one here。

![](img/be22e7f381c283e91cf00876c37f4d57_93.png)

![](img/be22e7f381c283e91cf00876c37f4d57_94.png)

I straight to that one。It's telling us what to do。 You see， I just borrowed this right there。



![](img/be22e7f381c283e91cf00876c37f4d57_96.png)

Form valid over Oh， wait， no， that's the， that was the create。 Sorry， sorry， sorry。嗯。嗯。Yeah， okay。

Can't find quickly where I can do this， but query set。So query set。Very set is called。



![](img/be22e7f381c283e91cf00876c37f4d57_98.png)

When it's loading I D number4。

![](img/be22e7f381c283e91cf00876c37f4d57_100.png)

Okay， so it's going to do a load。So query set is not the actual load。

 but it is the query to the database that we're going to do。

 So what I'm going to do is I'm going to tweak the query set。



![](img/be22e7f381c283e91cf00876c37f4d57_102.png)

And this query set is probably going to say show me where ID equals4 right so I'm say it's going to say something like select from articles where ID equals4。

 And if I just did the normal query set it would work。 but I'm going to change the query set。



![](img/be22e7f381c283e91cf00876c37f4d57_104.png)

![](img/be22e7f381c283e91cf00876c37f4d57_105.png)

嗯。I'm going to change the query set。 So what I'm going to do is I'm going to call the default get query set in the super class。

 which is the delete view class。 And that's going to say。Qury where the primary key equals4。

In this particular case。 But then what I'm going to do is I'm going to add another filter。

 This is like and。And owner equals。The current log in user， so。



![](img/be22e7f381c283e91cf00876c37f4d57_107.png)

So， number4 is。Owns by user2， but a logged in user is one。

 so this is going to be and logged in as user1。 So when it does the query。

 it says give me the thing that's ID equals 4 and user user ID equals1。

 it's going to get no records And so as the delete code or the update I looking at delete update and delete are the same here。



![](img/be22e7f381c283e91cf00876c37f4d57_109.png)

嗯。Before it does an update， it has to load the old data。

 and I have made it so that if you're not loading data on something that you that you that you own。

 then it's going to give you a 404。 So it's like that wasn't found。 No，4 does exist。

 It just doesn't exist for the current logged in user。 but 5 does。 and it does belong to me， right。



![](img/be22e7f381c283e91cf00876c37f4d57_111.png)

![](img/be22e7f381c283e91cf00876c37f4d57_112.png)

Now， the other thing is。Is when I it' going to call， it's going to call getQurry set again。New stuff。

X， Y， Z，1，2，3。So when you submit it。It actually is going to call get cr set one more time。

Before it actually stores the data。 And so let me show you this will be kind of tricky。

 So I'm going to try to mess with it on4。 I'm going to change， try to change4。

So I'm going to edit screen。And I'm going to inspect element。And I am going to somewhere in here。

Find。Wheres that hidden， Where is a hidden？How input type hidden。So。

That is the input type equals hit。 No， that's the middle word token。

 that's not the1 I want to change。Oh， this is going out where is the I would think that。Oh。

 it's because it's in this URL。 I don't know I don't think if I change this to four。

 it's actually going to order。But let's try。 It's probably not going to work。还在中。Okay。

 but the idea is eventually someone could mess with that post。

 so you still got to protect it right when that data is being modified。Yes。It actually does。

 it runs this code again and it won't it reads the thing and if it can't read it。

 then it won't let you update it and so that protects you from people breaking in and attacking there。



![](img/be22e7f381c283e91cf00876c37f4d57_114.png)

![](img/be22e7f381c283e91cf00876c37f4d57_115.png)

And the owner delete view is the same thing， so if you go into delete。It does a get。



![](img/be22e7f381c283e91cf00876c37f4d57_117.png)

Get quarry set and I add this filter to say， and it has to belong to the right person。

 So if I try to delete Article4。 it says， I can't load article for。 What if I come over here。



![](img/be22e7f381c283e91cf00876c37f4d57_119.png)

And I'll got to log back in。 So this one， I think was。CA。哦。Yeah。

 so now I can I so I can't delete number。But I can delete number four here because it kind of hides it。

 which is graphpy， but there it is， it's deleting number four and a away I go。So。



![](img/be22e7f381c283e91cf00876c37f4d57_121.png)

ok。lott of stuff， a lot of stuff。 Okay， so here's the thing。

We're going to use owner dot P Y over and over and over again。

 We're going to write simple and elegant views。 And all we have to do。 ultimately。

 any model that we want them to have this owner feature with， we add an owner column to it。 then we。



![](img/be22e7f381c283e91cf00876c37f4d57_123.png)

![](img/be22e7f381c283e91cf00876c37f4d57_124.png)

Have the views， extend an owner view。 And then everything's taken care of after that point。

 So it's really， we are not going to change a line to this。 It's really cool。

 We're going to use in project after project on table after table after table， right。

 Because this can apply to different models。 It's just this one happens to be applying to article model。

 So I've built a super generic。Owner capability that I can use over and over and and just take your time。

 Watch this more than once。 review object orientation， figure this out。 It's hard。

 It's hard for me when I'm teaching。

![](img/be22e7f381c283e91cf00876c37f4d57_126.png)

![](img/be22e7f381c283e91cf00876c37f4d57_127.png)

To explain how object Y object orientation is cool。

Object orientation is cool because it can let you write these super elegant and very reliable。

 the fewer lines of code you write， the more reliable it is， but the harder it is to understand。

 because the magic is here in this object or。And again， it took me a long time to write this stuff。

 but now it's really gorgeous and really reusable。

![](img/be22e7f381c283e91cf00876c37f4d57_129.png)

Keep thinking about object orientation， we're going to be doing a lot going forward in terms of object orientation okay。



![](img/be22e7f381c283e91cf00876c37f4d57_131.png)

So hope this helps cheers。