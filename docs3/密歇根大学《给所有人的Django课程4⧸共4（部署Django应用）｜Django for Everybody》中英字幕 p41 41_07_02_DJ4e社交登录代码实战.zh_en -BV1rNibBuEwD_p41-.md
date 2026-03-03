# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p41 41_07_02_DJ4e社交登录代码实战.zh_en -BV1rNibBuEwD_p41-

Hello and welcome to another walkthrough for Django for everybody in this walkthrough we're going to look at social login。

And we're going to use GitHub to do our login and we're going to use a piece of code called social login framework and you can read this。

 this is the link documentation social login， you can read through all this stuff。

 but I've actually in my home I've already done most of this and if you' based some of your stuff on the settings。



![](img/b87ddf4170112146f702fe95f7ac038b_1.png)

So if you've been using my code for a while， every time you say manage。 py。

 it says if you want to use social login。Please see this file and then and which registration it's doing。

 And so we're actually going to not really， it's not really broken。

 but you'll notice now I'm going to show you where these messages are coming from and what we are about to change so。



![](img/b87ddf4170112146f702fe95f7ac038b_3.png)

This one over here。So first off。Where those messages are coming from is down here deep in the settings do py by line 176。

 It's going to import from Github settingsttings。 py。 and Github settingsttings。 py is a file。

 but this file doesn't yet exist。 So if you go into DJ free samples。

You will see that there is a GiHub settings disk， but there is not a GiHub settingstting Py。

 so this blows up。And otherwise， and it prints that message so there's where that message happens。

 and so if you look at the documentation， we're going to put the Github o off to backend， ettera。

 etc cetera， Okay so what we need to do basically is we need to take this file。

There is a file called Github settingstting disk do Py， and we have to make a new empty file called。

GitHub。Settings。PW， so create that new empty file。And then the first thing we're going to do is we're going to just take all of this and we're going to paste it into it So from the disk。

 So this idea of a file with a disk name that means it's kind of the distribution file is not the real file。

 And so I'm just going to save this file for now now the problem and so if I go here back here I believe that at this point it won't say anything because we have a file。



![](img/b87ddf4170112146f702fe95f7ac038b_5.png)

Right， and it says we've switched to using it was using login。 and then now it's using login social。

 and so the login。

![](img/b87ddf4170112146f702fe95f7ac038b_7.png)

Is a registration template， so this was the login that you've been using until you turn the social on and it has some rules that says you know here's where you do the URL。

 you get a form， etc cetera， so you get to set this login this a long time ago that we set this thing。

But social login， if you read all the documentation， read all this documentation， social login。

You have a different way of doing it。So this is asking if that social A GitHub key has been set properly and that's this key right here。

 and otherwise it's not set。So if it gets set， then it's going to do a link to this social begin GitHub。

 and this is something that's documented in this Django framework。

So we're somewhere in here is the begin。Yeah， so his this is an example of how you call Google。

 sorry you do this social call and begin and this social。Going back to Setting。pyy。Oh。

 we got to go into the URLls。pyy， so let me go here。And then go into URLs。tyy。

So we do add something here。And that is that we find。We switch to social login。

 We try to import that same Github settings， and if we do get Github settings。

 we switch to using the different template and we use you say。

Template name and then use that as social for our social login， okay？

And then it prints out this little error message。Okay， so that redirects to social login。

And we also have OOth， the social namespace social for the social djanangle URLs。

 Now that social dangle URLs is configured by some of those settings。几。Okay。

 so we have this file called Github settingsttings。 py， but we can't use Github yet because。

We have to get a key and a secret。 And so the instructions are right here。 So we go to Github。

Developer settings。Now I'm not going to show you the ones I'm using for the projects or the samples。

 but what you do is you just add a new OOF app。嗯。买。Cool at。Sles。

And I'd give you some example things to put in here so。This actually。

 this home page is really samples。DJ 4 you dot com samples。And then you've got to set the login。

And this is what you're going to need I'm only got to update it。The application。

 I got to change this to be。Samples do dJ4E。com。ok。And then I register the application。

And now I have an ID and a secret。Don't worry， I'm gonna to delete this later。

So then what you do is you go into settings， not settings disk。

 and then you go in and you paste that in。And then you paste this secret and I hope I got the secret。

 right？This secret， so now I save it。Right。So I save it and。

And you go into my web tab because this is my pay account。

And I'm going to samples and reload samples。

![](img/b87ddf4170112146f702fe95f7ac038b_9.png)

I'll just go over here and I'll do a managed。 Py check。And I hope everything is right still。

 but it's a good test and it is using the social login and it looks fine。



![](img/b87ddf4170112146f702fe95f7ac038b_11.png)

Okay， so I've got that。 Now let's just see what happens when I say log out。And now， if I say log in。

I get this login with Github because I set that。 So if all goes well。I should be a loger to GitHub。

 now what's happening is GitHub is asking Charles Severance， me。

 the Loggedin user whether or not to share the data to my coolol app samples。

Okay so I'm going to authorize it and then it's going to send back and then I'm logged in and interestingly now it knows who I am。

 it's a Github account and like if I go into where are we at， where's the menus at。22 menu。

Because that that is based on that email account。 that's a gravitar that's based on the email account。

 So so now I'm logged in and a way it works so。That's the basic idea。

 It really comes down to read create this GitHub settings， use the GitHub settings D。嗯。

And away you go yeah， the GithHub settings disk。And you copy that in GitHub settings。

 and then you put your real account in there。Now I'm going to go ahead go back and。



![](img/b87ddf4170112146f702fe95f7ac038b_13.png)

Delete this application so you can't use my keys。

![](img/b87ddf4170112146f702fe95f7ac038b_15.png)

Now it's not going to work anymore okay， so there I go。

So I hope this was helpful to you that you walk you through a little bit of what it takes to get GitHub authentication working。

I would observe that the reason I chose GitHub is that you can do the same with Twitter and you can do the same with Google。

 but there are a lot。They don't trust you as much and so you have to do a lot more work to prove to them that you're worthy of using Google and Twitter instead of just or Facebook those are all much higher bars to get permission to use it GitHub is really easy so hope this was helpful cheers。



![](img/b87ddf4170112146f702fe95f7ac038b_17.png)