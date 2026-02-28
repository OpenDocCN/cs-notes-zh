# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p03 -03-MIT web.lab (6.962) - Day 1_ Git Basics.zh_en -BV12Ux5zTE9p_p3-

![](img/968a87c49f9b7ef9972cd42992d1558e_0.png)

Alright， can everyone hear me， okay。Can y'all hear me in the back？Allright， amazing。And Zoom people。

 let me know if you can't hear me or anything。Okay， first off， welcome everyone to Weblab。 I am so。

 it makes me so excited to see you guys。😊，I'm Abby。 I am the academic chair for Weblab。

 which means I am in charge of coordinating basically everything that you。

 all all of the academic lecture content that you see over the next two weeks。

 So if you have a problem with the lecture content and you're like， oh my gosh， this was terrible。

 or please help。 then come ask me。 Any questions are okay。😊。

So we're gonna start by learning about Git。 If you have a C， S background。

 you probably already know Git to some extent， if you do feel free to tune me out。

 but hopefully this lecture will be helpful。😊，It is。

 So Weblab is designed to be friendly to people who have no coding experience whatsoever。

 which is why we're starting from ground 0。 However， it does go fast。

 So if we're going through Gi stuff or whatever and you don't understand and you get lost。

 please just don't worry about it。 Take a breath you can come to office hours and we'll help you learn the concepts。

😊，And also， you'll just get familiar with it as you keep going on and doing more of it。

 So don't worry if you cannot pick up 100% of it。At the very beginning。So yeah， before。

 without further ado， let's dive into it。

![](img/968a87c49f9b7ef9972cd42992d1558e_2.png)

So the main question for today is， how do we collaborate on code， This is Tony。

 who was coa chair with me last year。 This is TA。 You'll meet him soon。 And that's me。

 And we're working together on a coding project。😊，So how do we work together？Well， you might think。

 let's do something like Google Docs， but Google code。And it'll live update。 So any changes I make。

 everyone will be able to immediately see。 That's great， right。😊，Well， not quite。

Consider the following。So let's say that Tony and Nick are working together on this project。

 and Nick is working on the homepage while Tony is simultaneously working on another part of the website that the homepage needs in order to run。

😊，And then。Tony is working on it。 And then the thing that he's working on goes down as he is making his improvements。

 And Nick is like， bro， what happened。 And Tony is very happy about the upgrades that he's making。

 But Nick is not as happy about the upgrades Tony is making。😊。

And so the basic idea is we need independent copies of the code so that both Nick and Tony can work on the code or like Nick can work on his part。

 Well， Tony can work on his part。 but if Tony breaks this thing as he's making his upgrades。

 Nick still has a copy of the old working version of whatever Tony was working on so that he can still work on his homepage。

😊，But then if we have independent copies of the code， that creates a lot of problems for us。

 because now， typically， when we're coding， we don't have just one file， we have a heck ton of files。

 And so there are all these files that Nick has a copy of， and Tony has a copy of。😊。

And let's say they're making changes。 Maybe they're making changes in different parts of the files。

 but。If you notice， both Nick and Tony have made changes in the same file。

And then in order to merge those changes together， one of them has to do the hard work of copying over the changes 1 by one。

 And that's really sad。 So an hour of copying and pasting later。

 after making 10 gazillion changes to this file。😔，Tony realizes， oh， crap。

 I just needed those lines that we just deleted。And so when I see this slide， I imagine like the。

 the du du du， like like suspenseful movie music playing and everyone like typing furiously on their computers。

 But let's just say， okay， for the sake of example。

 that Nick and Tony are just really good at collaborating。 Nick is a beast with a copy and paste。

 They're so good at communication。😊，But then， I come in。And I'm like， hey， guys， what you doing。

 can I join， can I help you guys， And then I don't know what the heck is going on。So。

To summarize the problems that we just described， there's a few things that we need in order to collaborate on code 1。

What makes this different from document editing is that we need independent local copies of the code base。

 So I can work on stuff on my computer without breaking anybody else's code。

We also need to be able to merge the changes that I'm making with the changes that someone else is making pretty seamlessly。

😊，We need to be able to keep track of versions。 So if I realize that I broke something and I don't know what the crap has happened to what what I just did to my code。

 I can roll it back。And we need to know， obviously， which version is the most up to date。

So we could think about all these problems and do all of this ourselves。 But thankfully。

 some really smart people have already thought about this and solved it all for us。

 and they made git。😊，So what is Git exactly？At a core level。

 it basically just tracks changes in files using some fancy math。So if I am editing a file。

 I type in like Corgis at the bottom of this dock， and I delete the line and about cats。

 Then the core functionality of Git is just keeping track of these changes that I made。

 So this information that I added this and deleted that is what Git stores。😊。



![](img/968a87c49f9b7ef9972cd42992d1558e_4.png)

Oops。Oh， yes， we are gonna see an example。 Okay， so before we go on any further and explain what's going on。

 we're going to。 I'm gonna show you how to create a git repo and also show you a few basic terminal commands in the process。

😊。

![](img/968a87c49f9b7ef9972cd42992d1558e_6.png)

![](img/968a87c49f9b7ef9972cd42992d1558e_7.png)

So。If you have done the homework 0 setup， then you will have Git installed on your machine。

 It should be already。 if you have a Mac， but if you have a Windows。

 you might need to install Git bash。So I'm going to open up my V S code。

 and I have a folder called Weblab that I'm gonna put all of my Web labb stuff in。And here。

If I go to terminal and then new terminal， then I can open up this guy。 If you're on Windows。

 then you might need to hit the plus down arrow button in order to get the terminal here to be git bash and not like something silly like command prompt。

Or you can also alternatively open up the terminal or gi bash。In your。

 like just in your computer as a whole， this and this are the same thing since I'm on Windows。

 I'm using Git bash。 But if on you're on Mac， you would just use terminal。



![](img/968a87c49f9b7ef9972cd42992d1558e_9.png)

![](img/968a87c49f9b7ef9972cd42992d1558e_10.png)

And the terminal is basically just a way for us to interact with our computer。

 So I can interact with my computer by clicking and dragging things if。

 by going to file Explorer or finder。 And this is just insanely more powerful way of doing that。😊。

So some basic terminal commands you'll probably need are L S， which means list。

 So it's just going to list out everything that I have in the directory or folder that I'm currently in。

Another command you'll need A C， D。 So that stands for change directory。

 So let's say I want to go into my catbook react directory。 You'll see what that is later。

Then I go inside， and now you'll notice that I'm inside my capbook react directory。 And if I L S。

 I can see everything that's inside of there。Let lets say。

 I want to go back out of catbook react back into my Web folder。 I'll do C D dot dot。

 And that just stands for the directory。 That's one directory back from where I currently am。Okay。

 feel free to follow along， but you don't have to。 I'll give you time to try it out on your own。

And then another command that I'll use is make directory， M K DIR。And。That will create a new folder。

 So I'm gonna create a new folder called Git demo for this lecture's purposes。

And I hate these zoom floating meeting controls。All right。And so。Now that I have this new folder。

 I'm going to go into it C， D into Git demo。And issue this command called Git in it。

 And that just creates a new Git repository within that folder that I'm currently in。

So now we have this file called Dockitt and Docket is the file that we don't need to worry about。

 but Git uses in order to track all of the changes to any files within my Git demo folder。

 and so now my Git demo folder is a git repository。



![](img/968a87c49f9b7ef9972cd42992d1558e_12.png)

Cool， alright。 so now I'm gonna give you guys a chance to try that yourselves。

 So I'll give you like two minutes to try creating a new directory， seating into it。

 calling get in it。😊。

![](img/968a87c49f9b7ef9972cd42992d1558e_14.png)

![](img/968a87c49f9b7ef9972cd42992d1558e_15.png)

I'll give you like one minute and then we'll see where people are at。And I need my phone to time。

And if you're having any technical issues， feel free to add yourself to Webla do is slash Q。

 and a staff member will come help you。 You're free to add yourself to the queue even while I'm yapping and people can come help you。

And let me know if you have any questions。Alright， if you think you need more time。

 please hold up a finger，1，2，3，4， etc cetera。 for how many more minutes you think you need。O。

You've got a few people。I'll give you guys a little bit more time。Alright， if you're having trouble。

 I'm gonna move on， but if you're having trouble and you need to reference the commands to run。

 you can either look on with someone nearby。 Or if you go to Webla do is slash schedule。

 all of these slides are linked there。 So if you just go to Webla is slash schedule， find my lecture。

 Gitbas。 click on the Google docs， Google Slides link。

 and you should be able to pull up the slides and reference anything that you might be behind on。😊。

Okay， so now we're going to talk about what we actually as programmers do with Git。

 and that is make changes to our code because we're productive programmers。😊。

So the basic idea of Git is that it keeps track of a history of all of the changes that we've made to our code and the individual sort of units of changes that we make。

😊，Are called commits。 And it's almost like there it's a package set of code changes。

What do I mean by that？ Well， let's say we're making， we're。

We're here and we're editing a bunch of our files。 We delete the line I like cats from one file。

 we add the line I like corgis to another file， add more lines， make more code changes， etc。😊。

And then once we're ready to sort of package those changes up， then。And add it to our commit history。

 Then we have something called the staging area。 And this is basically where we put all of the code changes that we're going to want to package it up into our commit。

So the command we use is called Git add and then we put in the name of the file。

 So let's say we do Git add Woftop pi。 that will add all of the changes we've made to Woftop pi pi to the staging area。

And then if we add cast dot pi as well， then we're adding the change we made there also to the staging area。

 And once we're ready to commit， we do git commit dash M with a message that describes what that commit is。

😊，Oops， that slide is not right。 There should be the cats thing in there， too。

And let's say we call it dogs and cats。And then what that does is it takes all those changes that were in the staging area。

 boxeses them up， slaps on a label that says what the changes are about。

 and adds it to our commit history。And so then。The staging area is refreshed， and there's a new box。

 and we can do Git add more to add to our next commit。



![](img/968a87c49f9b7ef9972cd42992d1558e_17.png)

A， so I'm going to demo what that looks like in RV S code。

 And why do I keep having the floating meeting controls。Oh my gosh， okay。

So we have our gi demo folder。 and let's make some changes。 I am going to。Add a new file。

 and I'm going to call it。Abby dot T X T。And。I am not going to use Copit to write something。

 Im gonna say。Abby likes cats。 I'll just type that。

And then I'm going to use a command called Git status to just see where I am。

 And it tells me that I'm， I don't have any commits yet。

 And there's one file that they call untracked that has not been added to the staging area。

 So that's why it's red。Get recorded that I made this change， but it's not in the staging area yet。

 So I'm gonna add it。 So I'm gonna say gi add and then Abbbby dot T X T。And now if I did get status。

I can see that it says changes to be committed new file A dot T X T。

 So that means that Git says that this file is in my staging area。And if I want to commit it。

 then I can do Git commit， Abbby or whatever I want to call it。 And it created my commit。

And now I can run a command called Git log。And Git log just tells me all of the commands。 sorry。

 all of the commits that I have in my history。 So when I say git log。

 now there's one commit that I just made in my log。And if I want to make more changes。

 make more commits， then those commits will show up in my commit log。



![](img/968a87c49f9b7ef9972cd42992d1558e_19.png)

So now I'm going to give you guys a chance to try that in your own repos。

 So I'll give you like two to three minutes to play around with it， make as many changes。

 make as many commits as you want。 And again， if you have any questions。

 let me know or add yourself to the queue。Also， zoom people， you can also add yourself to the queue。

 You can just put a zoom link for like。Your own Zoom room， if you need technical help。

How's it going over here。Oh wait，Alright， same as before。 Give me 1，2，3，4， etc cetera， fingers。

 if you need more time。Alright， cool。 I see a lot of hands。

 So I will give you guys a couple more minutes。😊，Alright， hopefully， that was enough time。

 We're going to。Move on。O。So in Git， once we've made our commits and everything。

In the previous slide， we were showing commits as a package set of code changes。

 And we were using these little package things with the labels as our picture。 But in typical， like。

 whenever you， if you look up anything about gi， they will typically use graphs that look a little bit more like this and。

😊，These are， basically， each circle just represents a commit。And。Each circle。

 each commit has a unique I D， which is going to be if we。



![](img/968a87c49f9b7ef9972cd42992d1558e_21.png)

Look in our Git log， you'll notice that。There's the commit message here。

 but theres also this gigantic， redonuls looking string。And that's the I D for a commit。

 So any time in Git， if we want to do something and refer to that particular commit that we made。

 then we're going to use this I D。

![](img/968a87c49f9b7ef9972cd42992d1558e_23.png)

And so this slide is just to familiarize you with the notion of having these graphs where each circle represents a commit。



![](img/968a87c49f9b7ef9972cd42992d1558e_25.png)

And so this represents the history of all of the sets of changes that we've made。



![](img/968a87c49f9b7ef9972cd42992d1558e_27.png)

Okay， so now consider the following。

![](img/968a87c49f9b7ef9972cd42992d1558e_29.png)

We have a scenario。 Tony is working on his new and approved homep page to his website。

And then Andrew comes along， Andrew was one of our staff last year。And hes like。

 can you help me fix this bug on the homepage？And Tony's like， I got you bro。

And then Abby comes in and she goes， Tony， we need a weblab tinnder feature to be added to our website tomorrow and you need to do it right now。

And so now Tony' is a little bit confused because he was working on his homepage。

 He was trying to make a new version of the homepage。 And so he was。

Changing a ton of stuff in the code， deleting stuff， adding things。 And then Andrew comes along。

 and he's like， can you help me fix this bug on the original homep page？

 So now Tony has to somehow like， go back to the code on the original homepage in order to fix the bug on that。

And then Abby comes along and is like， we， we need we need you to work on this。

 And then he somehow has to like revert again in order to work off of the original working code to make this new Webla tinnder feature。

It's kind of， it would be kind of a mess。And that's where。Dit branching comes in。So basically。

 what we can do is。Earlier I mentioned how each of these circles represents a con。

And it represents a series of like package code changes。

 But if each circle represents a series of package code changes。

 then it's kind of also represents a version of our code。

 like a snapshot of what our code looks like at any one point in time。

So you can think of this as the， the version of the code after we've made this set of changes。

And so if we want， so in order for Tony to work on all of these different things。

 kind of simultaneously。Then he could branch off。 So let's say that this is the last working version of our home page。

 That's the standard one that everyone's using right now。

Then he's branching off from that and making changes to make his new homepage。

 But when he wants to fix this bug for Andrew， he's going to go back to the last working version of the homepage and Git。

And then start making new changes for his bug fix for Andrew。

 And then he can go back again and make new changes off of that for Weblab tinder。And so the。

 the benefit of briding is just that。He can make all of these changes。

 and Gi will remember that he's made all of these changes to the homep page。

 So once he's finished Weblab tinder and this bug fix。

 then he can go back and just keep working where he left off on this branch。

So now I'm going to demo how to create a new branch in Git。



![](img/968a87c49f9b7ef9972cd42992d1558e_31.png)

Okay， so we have our， there's a command called get checkout and gett check out。

 The purpose of it is to switch from one branch to another。😊，So if I do Git branch。

 then I can see all of the branches that I have right now， there's only one。 that's main。

 But if I do Git check out dash B， D B says create a new branch。I'm going to call it。Cat。

 I don't know。Now， I created a new branch， and I switched to it。 So if I do git branch again。

Then I can see that there is the main branch， and now there's a cat branch and the current branch I'm on is the cat branch。

And so let's say I'm going to make some more changes。To my file。And I'm going to do Git status。

 check out Yep， Gi notices that I made those changes， I'm going to add Abby。

ttXT to add that change to my staging area。So now you can see it's in the staging area。

Im gonnata commit。Lots of cats。And so now， if you think in your head about what the object diet graph with the git graph for this is going to look like。

 if I gi log here， I see both my original change that was on my original branch and then the new change that I just made on my new branch。

But if I go back， if I get check out back to Maine。And then， I。Get logged here。

 Then I only see the original branch。 And so my object graph looks something。A little bit like this。

Where I have my original commit on the main branch， and then this is my cap branch。

 And then I have a new commit on my cap branch。

![](img/968a87c49f9b7ef9972cd42992d1558e_33.png)

O。Same as before， going to give you a chance to try it out yourselves。Add yourself to the queue。

 if you get stuck。Actually， before I go on， does anyone have any questions or confusions about what I was just talking about。

I can't tell if the silence means that y'all are all confused or y'all are all good and just like working。

嗯。All right。If you got losts or confused， feel free to add yourself to the queue。

 And one of our amazing staff members could help you。 even while I'm yapping。

 you can ask the other staff for help。😊，And also， if you got completely lost。

And don't know where we're going now。Please do not stress out。 You'll be fine， and we can。

Get you caught up on whatever you got confused on， either after lecture or at office hours。

 or you can。 your friends can help you as well。So。Unfortunately， I have to keep us moving along。

So what is happening in the object graph when we create a branch well。What。

 whichever commit we were on when we created our branch。

 that's gonna be the one we're branching off from so I can create new commands in the Web lab dinnernder branch。

 I can commit， or I can switch back to the main branch and create new commits there。😊，And then。

 let's say that。I was working or Tony was working on the Webla Tider branch。

 and he was making his commits。 And then someone else was working on the main branch。

 and they were fixing some bugs or something like that。

 And now we want to put these commits back together and merge Webla Tider and bring all of those changes into Ma。



![](img/968a87c49f9b7ef9972cd42992d1558e_35.png)

How do we do that？That's something called merging。

![](img/968a87c49f9b7ef9972cd42992d1558e_37.png)

So。Basically， if I want to merge off my commits from。



![](img/968a87c49f9b7ef9972cd42992d1558e_39.png)

My cat's branch into my main branch。Then I hate this Zoom thing。Then let's see。 So right now。

 I'm on main。If I were on。What did I call my branch cat。I'll do Gi branch to see。I called a cat。

 So if I check out cat and I'm on cat， then I can't merge cat into main。

 I need to be on main in order to merge cat back in。So I'll check out Maine。

And you'll notice that when I check out different branches。

 the version of the code in my VS code window will change based on whatever the most recent commit in that particular branch is。

So now all I can do is all I have to do is you get merge cat。

And that will merge the changes from cat into Maine。 And so now you'll notice that I'm in Maine。

 but I have all the changes that I made on the cat branch。And then typically。

 good practice is just shut up。Good practice is to delete。The branch that I was on。Before。

Now that I'm done with it， now that all the changes have been merged into Ma。



![](img/968a87c49f9b7ef9972cd42992d1558e_41.png)

Alright， same as before。 Oh， wait， sorry， I am not going to。Okay。

 I'm not gonna give you time to work on that yourselves because it's pretty quick。

 And we're going to actually go into more detail on merging in the second Gi lecture that we have at the end of this week。

😊，Okay， so when we put them back together。The object graph looks something like this。

 It's not quite the same as this。 We'll go into more detail on that later。

But then the question that we have finally is。Well， how does collaboration work then。

 Because we did all of this stuff with Git， branching， creating new Git repos， creating commits。

 etc cetera。 But all of that was locally on our own computer。

 How are we supposed to share this and collaborate with other people。😊，And that's where a server。

 such as Github， comes in。So GitHub is just a giant server somewhere that hosts all of our code。

And so there will now be a version， how this works。

 is there will now be a version of our code on Github。

 a version of our code on our own computers and the computers of whoever we're collaborating with。😊。

And so this introduces interesting complexity because now we have another independent local copy of our code on Gitthub。

😊，So let's say that Nick is working。 and there's a copy of his code on his computer。

 and the Github is updated with what he's got on his computer。And now， Tony wants to join in。

He's going to do Git clone on the repo in Gitthub， and we'll show you how to do that pretty soon。

he's gonna get clone that。 And now there's a copy of the object graph。

 like all the commits that have been made， the full history and all of the files， of course。

 on his computer， that exactly matches everything else。 Now。

 if Tony wants to make some commands some commits。 Sorry， I some changes。😊，He'll make his commit。

 and then he'll use a command called Git push to update whatever Github has with whatever he has with the commits that he just made。

And if Nick wants to take， the commit that Tony just pushed onto the remote server。

And bring it on to his local development environment。 He'll use the command， Gi fetch。

 And that basically just looks。And updates whatever he's got on his computer with。Whatever was。

Added to the remote server。But then he can do something called Git pull。

 And how that's different from Git fetchtch is that Git pull actually merges the command。

 the commits from the remote server into what he has locally。😊，So if he does get pull。

 then it will actually update his V。 S code with the commit that Tony had made。

So the basic commands that you need to know are。Get cloned to take a repo and bring it onto your computer。

 And then you can make your commits， and then you push。

 get push to bring those commands to update their remote server with those commits that you made。😊。

And then get pull to pull those commits that other people have made and put onto Github onto your local computer。

 your， your local development environment。And then another command that we'll be using a lot in Web lab workshops。

 which you actually should never use in practice。 But for our J weblab workshop development setup。

 we use this。 It's called git reset dash dash hard。 There should be two dashes there。

 And that wipes all of the uncommitted， unstd local changes that you've made。 So if you were coding。

 And then you were like， oh shoot， I don't wantan to do that。 You do git reset dash dash hard。

 And that just wipes everything except what has been committed already。



![](img/968a87c49f9b7ef9972cd42992d1558e_43.png)

OK。That was it for Git， please， everyone。Stand up。 It's been a long time of sitting。

Get a good stretch and go to Weblab dot is slash feedback to give me feedback on that lecture that I just gave。

 It's like super quick。 It'll take 30 seconds。 And we'll be doing this after。😊。

Every single lecture so that we can get good data on what you guys liked and what you guys had trouble with。

Alright， take a two minute break before we move on to our next lecture。



![](img/968a87c49f9b7ef9972cd42992d1558e_45.png)