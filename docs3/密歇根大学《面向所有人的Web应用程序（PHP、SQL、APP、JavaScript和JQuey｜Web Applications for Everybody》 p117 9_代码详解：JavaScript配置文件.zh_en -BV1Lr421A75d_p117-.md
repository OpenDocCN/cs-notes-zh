# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p117 9_代码详解：JavaScript配置文件.zh_en -BV1Lr421A75d_p117-

Hello and welcome to web applications for everybody in this walkthrough。

 we're going to walk through the assignment that's associated with the basic jascript lesson Here it is。

 It's the auto it's the。

![](img/8063c5fe03b3c761859a2a7b6173a14e_1.png)

The assignment is to basically build a profile database Now part of the philosophy of this assignment is I assume that you just finished the autos credit assignment with a autos table and a user table。

 and I I want you to。sortrt of build a second credit application you can really look back at your old one for inspiration but this this is going to be the basis for the next couple of assignments for this course so you ought to get this right and if you just barely got it working in the previous assignment then you should sort of take this opportunity to really understand what's going on so。

Let's play a little bit with it， it's got some JavaScript in it some in browser JavaScript data validation。

 so let's take a look at this actually I'm going to show it to you on my local host。



![](img/8063c5fe03b3c761859a2a7b6173a14e_3.png)

Okay， but before I do， I want to set up my tables and I've got some tables here in my MIC database。

And I'm going to just drop those and show you how I have to start with tables。

 obviously if I run my code now I think blew up right， but I give you some code to set this up。

 we got to create table for users。Copy that over。Create the table for the users。And。



![](img/8063c5fe03b3c761859a2a7b6173a14e_5.png)

table for profile you've got to create these in the order because there is the foreign key constraint。

 so if the user table doesn't exist， you won't be able to create the profile table。



![](img/8063c5fe03b3c761859a2a7b6173a14e_7.png)

Kumloi， there that goes。

![](img/8063c5fe03b3c761859a2a7b6173a14e_9.png)

So that makes that work now。And if I go back to the assignment， I got to insert。

These hashed passwords， so I'm going to insert UMSI and the hash password。

I explainplain all this stuff， but then I kind of give you。

Cchey steps that make your life a little easier so now。So here we are at the resume。

 I'm going to use my local host one here， not the global ones so you can watch what's happening in the database。

 I've got a profile a table and a user's table。

![](img/8063c5fe03b3c761859a2a7b6173a14e_11.png)

![](img/8063c5fe03b3c761859a2a7b6173a14e_12.png)

So the first thing is that。You're supposed this is the JavaScript bit。

 you're supposed to do in browser validation， and so if I do a view on this page。

You can see what I've got I've got to on the click of the login button I've got I'm going run do validate Okay and it's either going to give me a true if it's valid and then actually submit the form or it's gonna give me a false and blow up and so you see this return true and return false etca。

 etca， etc ce Now the interesting thing about jascript is I can't hide it from you。

 I mean the jascript runs in the browser And so you know deep in the request response cycle。

 this is out here in your browser， no server actions going on at all right now And so。

You know I can't hide it from you so I even show you all this I give you all this code somewhere in here here JavaScriptscript validation。

 so I'm going to might as well tell it to you because I'm going to show it to you if you're smart enough to do view source you can figure it out so what happens is when I type this stuff。

So I typed this with no a sign them， hit login， JavaScript is going to run and now what's going on is。

This alert invalid Val email address has popped up if I blank them all out。And I hit it。

 the JavaScript。We'll stop and say both fields must be filled out now if I get it right。

So let's just put in like。The wrong stuff， that's going to be a server side check， No。

 that was a client side check。Service now it's a server side check。

 that's a server side check with a redirect with a flash message。

 the whole thing right and so if I take a look at login。phP。嗯。

You know this looks a lot like the login that PP you've been doing all along。

 you know this is a redirect and then here is the do validate and then there's the script code so I put that all together in the login that's very similar to the login that you've been working in。

Before。Okay， so let's log in successfully， UsI。That's really the JavaScript here。PHP 1，2，3。So again。

Add a new entry。There's no JavaScript in these although soon we will in the next assignment we'll be going crazy in these addd things this we'll be changing the ad and edit more in the next few assignments let's do a ventine there you go yeah and this is just crud right we're just we're just going into like the profile table and。



![](img/8063c5fe03b3c761859a2a7b6173a14e_14.png)

Got first name last name email summary it's a little different than the previous one that you did。

 but not not that difficult to do And so there's no real JavaScript here you just got to make the edit work。

 you got to do things like。

![](img/8063c5fe03b3c761859a2a7b6173a14e_16.png)

You know。Be able to put dance characters in and do validation。No。Drop。Drop table students。Right。

 so you've got to be able to put evil characters in and not have anything go bad。

 either of course SQL injection is not going to happen because we're using P。

 but also not HTML injection either and of course if we take a look at this， we just see， oh。

 that's what's in there。

![](img/8063c5fe03b3c761859a2a7b6173a14e_18.png)

![](img/8063c5fe03b3c761859a2a7b6173a14e_19.png)

Okay， and， and then。And then away we go into and so that's pretty Elella and then a delete just has a verification。

Don't only make sure your HTML entities on this stuff as well and there you go and then you lock out。

So now I want to log back in and show you a little bit about how the foreign key works。

 so let me get logged back in。Mbinian。Okay， so let me start by showing you something about login。

And it's in the assignment， so it basically says。When you're logging in， you're supposed to put。

You set up the session we've been doing this before where you put user ID in into session so if we're in the login right we have the user ID。

 we do a select for user ID and what user ID of course is is the primary key of the user records so in this case it's one for this one that I just inserted right？



![](img/8063c5fe03b3c761859a2a7b6173a14e_21.png)

And so the idea is that you're going to take this， pull that out of the database。

 and then we're going to store it into the session， we're storing the user ID which is the number。

 the primary key of the current user and we're going to use that later and then we redirect back to index。

phP so now we are logged in and we're at add newent and so this。



![](img/8063c5fe03b3c761859a2a7b6173a14e_23.png)

And add new entry， of course， we're using these pieces of information to tell whether or not we're allowing the ad to happen。

 we've been protecting these this way for a while and basically if there is no user ID in the session that die with access to N okay。

So now let's go ahead and add the entry。Now， part of what it says is when you add this， you need。

To have a foreign key， so let's go back to the foreign key。

 the foreign key is the pointer in the profile that goes to user ID。

 so this is the profile ID is the primary key in this table。

 user ID is the foreign key in this table。

![](img/8063c5fe03b3c761859a2a7b6173a14e_25.png)

And so you're supposed to when you're adding a record there are no records currently in。

 you're supposed to set this user ID to the current Loggedin user。

 the current Loggedin user's primary key is sitting in session because you put it in session in the login code。



![](img/8063c5fe03b3c761859a2a7b6173a14e_27.png)

And I give you this I give you most of it in the handout right so the user ID which is going to be inserted into the user ID with a little placeholder UID and then that's going to pull it out of the session。

 so that is creating a new record in profile that has a foreign key into the user table that has the user ID。

Okay。😊，嗯。And so lets's that's pretty much it right， so here's that code， here's this code in here。

We're going to do the insert and we're going to pull this number out and so I'm logged in as user number one and so now when I run this thing successfully I'm going to do an ad and it's going to run that insert。

 but if I go look in my table right now in the profile table you see that there's that foreign key and because we told MyQL that that's a foreign key。

 it actually is a hyperlink and we can jump into the user table to find the corresponding record in the user table。



![](img/8063c5fe03b3c761859a2a7b6173a14e_29.png)

OkayAnd so that you have to do and in an upcoming assignments。

 you're going you have to be creating these foreign key links。

 the next assignment is going to be a many many to one relationship and the last assignment is going to be a many to many relationship。

And so that's an important part of this assignment and so I hope that you pretty much I think I covered most everything I wanted to cover good luck in this assignment and I just want to emphasize that。



![](img/8063c5fe03b3c761859a2a7b6173a14e_31.png)

![](img/8063c5fe03b3c761859a2a7b6173a14e_32.png)

Do this one really well， take your time， understand every landing code I know I say that in every assignment that's because it's the only way we can build to increasingly difficult assignments okay。

 thanks for listening。