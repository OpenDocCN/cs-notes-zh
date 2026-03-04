# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p101 31_代码详解：登录与注销3.zh_en -BV1Lr421A75d_p101-

Hello and welcome to Web applications for everybody this in this little bit。

 we're talking about some of the routing， the redirecting， the post redirecting。

 the no refresh on the posting。 we did all that before。

 Now we're going to actually sort of talk about the log in function where we're talking about all these things together。

 And so here we have this application。 And this application is pretty smart。

 It detects that you're not logged in。 and then it sends you to a login screen。

 And so you can log in on any account as long as the password is UsI。 And now we're logged in。

 and there's a little success message here。 and then you can log out。 and now you're logged out。

 so there's several files。 There's app dot PhP。 This is made up of app dot PhP login do PhP and log out do PhP。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_1.png)

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_2.png)

So log in。

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_4.png)

At leastas so far， this application doesn't do much。 It actually doesn't have any post handling。

 So the model part is just get the session started。 and then we drop into Hm。 blah， blah， blah， blah。

 blah， we'll come back to this success bit in a second， This is what's called a flash message。

 But what we're doing is we are basically using as the indicator。 whether you're logged in or not。

 the key account being present in the session。 So if you're if the account key is not in the session。

 which it is not there when you first start out， it says， please log in。 But if the account。

 if you have logged in， then it then the account is in the session， and that's where we say， hey。

 here's a cool application and go ahead and log out。Okay， so it comes in， starts a session。

 there is no account key in it so it says， please log in and that's just a standard Hre so we go over there。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_6.png)

While we're doing let's look at developer console， get that start up。

 get that ready for us because that'll be so much fun。 Now， login is where the fun begins。

 So here we have login。😊。

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_8.png)

We have model code up here at the top session start of Co。

 and here is our postcode and we'll come back to that really quick and so now here is our body。

And the first thing we're going to do is these things we call flash messages。

 And so I'm going to put errors in the session under the key error， and I'm going to put good。

 good things that happen to us in the key under the key success。 and so at the beginning of this。

 please log in right here between those two things。

 I'm going to check to see if there is an error in the session。 And if it is。

 I'm going to print that out red， and I'm going to unset it。

 And that's why we call it a flash message。 And so in this case。

 and the same would be true if there's a success， except I print out green and then I unset it。

 So right here between login in the start of the form， there might be a message or may not。And so。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_10.png)

If in the case now where I have a bad login， right？



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_12.png)

Right and I press login iss going to come up here。 It's going to see the post and it's going to un the session sub account。

 that logs out the current user。 Remember I said that when the account key is in the session array。

 then we're logged in， So that's kind of a log out。 If the password is equal to Usi。

 then you're good and we're going to log in and if it's not， we're going not log in。

 So we're going to do this code first。 we're going to set the error to incorrect password and then we're going to redirect back to ourse。

 We are in login do PhP and we're going to redirect back to ourse。 So we did a post。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_14.png)

That's opposed post。

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_16.png)

And then a redirect back to ourselves。 But we also sneaked into session this little thing。

 So after the redirect a get comes back in。And this code triggers and runs and outcomes incorrect password。

 Now， the interesting thing is because we have removed it。

 if I refresh this page and is legit to refresh it， cause I'm sitting on a get request。

 If I reset it， that password， that error is not there。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_18.png)

It only showed up once。 It's a flash message。 So' why we call it flash。 It flashes on this。

 But then if I do another request response cycle， it's not there。

 And we achieve the flash by getting it out of the session once we've displayed it。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_20.png)

Okay。😊，So now let's talk about what happens when you have a successful password， so we'll go。

 you know， Sarah。

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_22.png)

And then U M I as the password iss going to come up here。

 And this is now really starting to get very compary feeling because the controller routes。

 in this case， it decided to route back to the existing script that we are coming from。

 But now once the password matches， we're going to put up a little cute little success message in the session。

 and we're going to set the account。

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_24.png)

And this account signals to app。tphP that login worked。

 so we're sending a message in the session from one script to the other script。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_26.png)

So this redirect is going to happen， so I'm going to log in correctly。

 so login is a post and then it redirects， but in this case you see that redirects to app dot PhP and then it does a get and so this is the response that comes from that get but then if we look at app dot PhP we see it checks to see if there's a success success message in the session and it prints it out in green and then it unsets it so it's a flash so if I refresh it that's no longer in the session okay。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_28.png)

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_29.png)

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_30.png)

And this is where we would have some cool application stuff playing a game or something。

 And then we're going to go to log out dot PP。 So logout do PhP is always my favorite script to write because it all pretty much has three lines。

 We start the session。 We wipe out the session， removing the account。

 And then we redirect back to A dot PP。 So let's clear this bit out。😊。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_32.png)

And I'll press log out and we're going to do a get request to log out this's not a post request to log out。

And it clears the session。So it was a get request and we sent a 302 as a result of a get request after having wiped out the session and then said go back to at PhP so then it goes back to a dot PhP and it runs through。

 there's no success message and there is no key in their account key has been gone it's been taken out and so we just logged out。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_34.png)

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_35.png)

Okay， so I hope that's useful to you。It gets kind of brings all this stuff a model view controller and post redirect and all that stuff is now working quite a bit in this particular small application that just has three files。



![](img/4bd0eea3c6da28ebe084bc3c94401a3c_37.png)

![](img/4bd0eea3c6da28ebe084bc3c94401a3c_38.png)