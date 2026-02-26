# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p02 -02-COMP1531 22T2 - 1.2 - Git - Solo Usage.zh_en -BV17RXGYuEaM_p2-

![](img/44e78d5ea582b3033206b30524834892_0.png)

The first git lecture， which will probably run till a little bit after 7， where we'll take a break。

And this is a particularly。Interesting piece of content to go through。 It's quite a， it's quite a。

 quite a heady idea to tackle right at the beginning of the course。

And what I would just preface the next couple of lectures with。For everyone is that git， which is a。

 which is a， you know， it's a program we're about to talk about。

 It is a difficult topic to grasp fully。 I want to describe it to you a little bit like it's kind of like playing the piano。

 Most of you have probably like played a piano at some point in your life。

Playing a piano is a really easy thing to do some basic stuff on。

 Many of you might have had family members who show you， you know。

 you tap a couple of keys and you make a cool sound。

 And then you've also seen some people do some absolutely insane things on a piano。

 Git is very similar to that， you will find it relatively straightforward to do some basic stuff very quickly today。

 and you'll find that very easy to do throughout the course。 But if you feel。That you。A。

Don't understand something perfectly。 or there's a lot of things that you don't know。

 That's actually totally normal。 Git is a lifelong lesson， a lifelong program to learn。

 So don't feel stressed if it feels like a lot because we're throwing a lot at you。

 But at the end of the day， this course covers it very basically and you're only ever going to get comfortable by doing。

 So give yourself the time。 If you get to week 8 and you're still a bit confused， then you know。

 let's support you。 but if you're a bit confused today。 It's like that means you're totally normal。😊。

嗯。Jen says after the lecture should we start lab 1， lab 1。

 which if you haven't already looked or read the notice， has three activities in it。



![](img/44e78d5ea582b3033206b30524834892_2.png)

One of those activities is based on Git。 The other two activities are based on Git and JavaScript。

 which we do tomorrow night， So you can kind of easily do this one。

After tonight and then the next two I'd recommend you wait until after tomorrow。

 So let's get into it。

![](img/44e78d5ea582b3033206b30524834892_4.png)

嗯。There is a problem。 Let me set the landscape。 The problem is that to effectively work on large projects and group of engineers。

 Imagine there's 12 of us， you know， you me and 10 other people。

 We need a more complex method of managing all of us trying to write code。

 and we need it to do two things。 The first one is version control。 We need it to track history。

 If you've got Google drive1 drive dropropbox。 You will know that sometimes you can get an older version of a file。

 Google sheetets does this。 Google Docs does this， right， like history。

 We need a way to kind of be able to go back in time or log what is happening so that it's easy to unwind if things go wrong。

 and it's easy to see the steps that got you somewhere。

We also need to be able to program concurrently， as in we need multiple people to be able to work on the same project at the same time。

Without having to kind of share files or not。嗯。Programs like Dropbox and OneDrive that you've probably seen。

 they maintain a history of files pretty well。They help you sync between multiple sources。

 But you know that if you have a word document or something like that on Dropbox or Onerive or Google Drive and two of you edit it。

It gets really confused and it doesn't know who's like how to push those things together。

 You have other tools like Google Docs， which are really great for。Keeping track of history。

 to some extent。And Google Docs or Google sheetets or of these other tools。

 And there are many of them now。 they allow you to work together with people in real time， right。

 where you can kind of actually， you know both work on the same document。

 You can't write on the same line of text， you know， like if someone's writing a sentence。

 you you don't get in and write the sentence with them， but they can write a sentence up here。

 You can write a sentence down there and it figures it out。

Programs like Google Docs kind of solve a lot of these problems we have as programmers。

 but in many ways， they're too simple and they're not specific enough to the challenges that we have as programmers。

 So we need a better solution and that solution， or at least a popular solution is Git Git is a program。

 Git is a program just like Ged VS code Gcc。 These are all programs that you can run if you're here。

 you've come from 1511， and you know that you can use D Dcc。 I think you're using 1511。

 You know that you have a Dcc program or a Gcc program Git is just another program on the computer Git is a version control tool。

 That means like a history tracker that enables people to work concurrently on the same code base。

 So if you mean 10 other people working together we can all maybe not the same lines of code but within the same files and the same collection of files we can all。



![](img/44e78d5ea582b3033206b30524834892_6.png)

Work together concurrently without having to wait for the other person to finish their work before we start。

Gitt， unlike lots of other tools you might have used， is built for programmers。

 and it is designed for managing code。😡，It's kind of specifically built for this problem We want solve as programmers。

 There are other solutions out there。 If you're interested， you can go look at。

I think it's material or Z SVN。 Oh my God。 I've forgotten already。 I think it's SVN。Yeah， S VN。

 these are other tools。 and some companies use these， but Git is generally the most popular。

I don't really have an opinion。On things， but Gi is generally the most popular。

 That's a big part of why we teach it。One really important thing about Git is that Git is what we call a distributed version control software。

 And what that means is it's actually a little bit like again。

 Dropbox or onrive or something like that。 If you have three computers。

 a desktop and a couple of laptops in your phone。 That's four computers。 Okay， three desktop。

 laptop phone。And each of them has Dropbox。And you sync with Dropbox。

 They've all kind of got a copy of it， right？ You could argue that's another distributed form of thing。

 You're not all relying on the cloud。 If， if the Dropbox cloud explodes and disappears。

 you still have a copy of all your files。 So does your laptop。 So does your phone， right。

 So Git is a distributed version control software that always relies on the fact that you have all the latest changes in theory。

 you can't kind of choose that as easy。 But， you know， that's， that's how it's set up。

Gt is a command line program。

![](img/44e78d5ea582b3033206b30524834892_8.png)

And what I mean by that is as we do a lot in this course。

 we're going to be doing things with the command line on Linux， you know。

 in the CSE machines you might have used， you know， the terminal， that's where we use Git， however。



![](img/44e78d5ea582b3033206b30524834892_10.png)

To make our lives easier and to make everyone's lives easier。

 there are some websites that essentially exist that are。

Kind of user interfaces that use Git underneath to do things。

 So instead of you having to always learn every single git command。You know， you can actually go and。

Use these websites that help you out a little bit。And we're going to be using both in this course。

 we're going to be using the websites that make your life a bit easier and we're going to be using the command line。

嗯。So， yes， they're， they're essentially front ends to git that are where they're all stored。

 So it's kind of like a， you know， Dropbox is a website。

 but it's got software underneath that actually does the complicated stuff。

 These git websites are kind of the same。There are three major Git software tools that implement the Git language。

 They are GitHub， Bi bucket and Git Lab。They all kind of do the same thing。

 Githour is by far the most popular， and it's probably the main pick that people would choose these days。

It's owned by Microsoft now。Bit bucket is owned by alassian， which is an Australian tech company。

 They are both private， kind of， you know。Sort of profit， I don't wantan to call them for profit。

 But， you know， they're they're owned by like for profit companies。

 Bit Bucket hasn't gotten as much love recently by Lassian as as Github has from Microsoft。

 So the gap between those two has certainly increased in the last few years。 Github did not create。

 sorry， Microsoft did not create Github。 They bought it at one point。

 And then Gitlab is kind of like your open source friendly， you know， like chilled out。

Pie of software that you can。 you can actually like take your own copy of。 It's open source。

 Like it's， it's literally just the friend of， you know， the community。 And what that means is that。

Organizations like UNSW can actually take a copy of the Git software because they give it out for free and we actually run Git on our own systems at CSC。

 In fact， you would have seen that already。 This is the Gitlab website。

 This isn't this is different from Gitlab do com。 Gitlab dot com is like Gitla's website。

 the company itself that manages the software。 But computer science and engineering at UNSW。

 we take a copy of the software and we' run it ourselves。 this is like our Gitlab。

 This is yours and mine and everyone else in our community's Gitlab。

 So we will be using Gitlab throughout the course。😊。



![](img/44e78d5ea582b3033206b30524834892_12.png)

![](img/44e78d5ea582b3033206b30524834892_13.png)

![](img/44e78d5ea582b3033206b30524834892_14.png)

![](img/44e78d5ea582b3033206b30524834892_15.png)

We won't be touching the other two， though We might talk about them anecdotally at some point。Now。

Learning get。Which is what we're here for tonight。 it's going to be a bit of a slog。

 But the the good thing about Git is that while we talk about the git lectures tonight。

 we actually use Git all throughout the course。 It's why it's the first lecture。 So again。

 if you're feeling a bit overwhelmed tonight， just remember。

 this is just the theory and then we actually practice it every single week for 10 weeks。😊。

We're going to learn Git in three stages。 The first stage is learning how to use Git or version control on a single machine。

Right， oh， I need to yeah， next lecture。 this should say this lecture， not today。

 So we're gonna learn how to use Git if it's just me on just my computer。

 then we're gonna learn how to use Git。 if it's just me on a couple of my computers。 For instance。

 maybe like the CSE machine and your personal laptop。 and then the next lecture tonight。

 we're gonna learn about how to use Git across a team of engineers。😊。

Most of what we do tonight will be practical。And that means it'll be fun。 mate Jay says。

 can we use git for windows on our local machines or is WSL mandatory？😊。



![](img/44e78d5ea582b3033206b30524834892_17.png)

In the course setup。😡，嗯。Most of the stuff we have here， like， you know。

 in terms of running on Windows， you can do things a few other ways if you'd like。

 We just tell you the ways that we will support as in if you have problems doing it your own way。

 which is fine。 it might be harder for tutors to help you out with that。 So get for Windows is fine。

 but for everyone else who's never heard of these things before and doesn't know what they're doing。

 you can just follow the setup instructions here or if you're using the CSE machines。

 which we will use tonight， you don't need to do any setup， and I I still love the CSE machines。

 I think they're great。

![](img/44e78d5ea582b3033206b30524834892_19.png)

So that's what we're going to be doing， so we'll be starting with the first thing。Now。

Learning Git on a single machine。

![](img/44e78d5ea582b3033206b30524834892_21.png)

What I'm going to do。Is I'm gonna step you through some processes。 And if you have questions。

 you can just kind of ask one thing I will skip tonight。



![](img/44e78d5ea582b3033206b30524834892_23.png)

Abdul， the the reason your comments's not on the screen is'cause I I pick the comment that comes up。

 That's why they stay there for a while。 I put yours up four years ago。 It's right here。嗯。

Jen has Jen's asked a good question。 I'm sorry。 I'll do that your question was short， short lived。

When I when we say CSE machines， do we mean ti V andC， yes， we mean ti V and C。

 tiger VNC is the way you connect to CSE machines。嗯。Now， in terms of getting set up。

There's so much helpful knowledge inside of your first Git labb。

 It's one of the best labs in the course。 It's one of my favorite labs in CSC。😊。



![](img/44e78d5ea582b3033206b30524834892_25.png)

This git basics here will get you set up with Git。 There's quite a lot of things involved in it。

 And oh just for simplicity I'm going show you because otherwise we're gonna get a bunch of foreign posts。

 Let's， let me just show you， so。

![](img/44e78d5ea582b3033206b30524834892_27.png)

![](img/44e78d5ea582b3033206b30524834892_28.png)

Let's imagine I'm on Gitlab and all of your labs and all these other things on Gitlab are a series of projects。

 right Now project is just an idea。 It's just it's just a bucket of code and I'm just gonna make one tonight called lecture test and it's going be it's going be you don't need to do this because you don't create these in the course。

 but I'm just gonna make one now for our purposes in this lecture。

 This is a Git repository on Gitlab。 It's a collection of more specifically it's a collection of files。

 but often it's a collection of code for us。😊，Now， this is just a U I。

 There's a lot of information here and a lot of it。 you don't need to be concerned about。

 The most interesting thing for you， though。So， I might make a I might make another one without a file。

 So give me a second。 I'll call this one lecture  one test。 That's gonna be our thing tonight。

Now this is our repository here。And this is sitting up on Gitlab。

But what I want to do is I want to kind of， I want to get this on my own computer。

 I would like to interact with it on my computer。 So the very first thing we're going to learn about is getting set up。

 which is git cloning。

![](img/44e78d5ea582b3033206b30524834892_30.png)

Now， before we get clone。You have to set up your SS SH key。 Actually。

 I'm I will skip that because there's quite a lot of involved instructions。

 but you can go and follow the lab。 You'll see the lab at some。



![](img/44e78d5ea582b3033206b30524834892_32.png)

You can get the link on Gitlab， but。This is the lab here。 It's the very first lab in the course。

 And there's a lot of instructions about how to get set up and dealing with keys and adding your keys and using Git and just tons and tons and tons of stuff。

 right It could take me like 10 minutes to go through it。 And I just be following the steps here。

 So follow the steps。 We've spent a lot of time writing them。

 and then you can move on to the next bit。 The next bit is cloning a repository。 So in this course。

 you have you have these repositories of code。 these buckets of files which are of code。

 And there's one for each lab。 So you have a few of these a week。 There's one for the major project。

 They really are just collections of files。

![](img/44e78d5ea582b3033206b30524834892_34.png)

![](img/44e78d5ea582b3033206b30524834892_35.png)

And I'm gonna clone that to my own machine。 Now， if I want to clone this to my own machine。

 I can click on the clone button on the Gitlab user interface， and I can copy。



![](img/44e78d5ea582b3033206b30524834892_37.png)

The URL to this git repository。And then what I can do is I can go and open up and I might do this in。

 I'll do this in the CSE machine just to help you all out。

 So some of you might use VS code in this case， I'm using tiger V and C to kind of remotely connect to。



![](img/44e78d5ea582b3033206b30524834892_39.png)

The CSA machine。Right， and what I'm going to do is I'm going to open up a terminal right here。

 and I'm going to make a new folder called 153，1， which probably exists。 Let me just remove that。

I'm going to make a new folder called 153，1。 I'm going to go inside that folder。

 and then I'm going to write git clone。 That is a command。

 and then I'm going to paste that URL that I copied here that I let me copy it again。Paste。

 and I'm going to paste that URL。Jack says，So if I'm connected to the CSE machine via VS code。

 I don't need to download Git right， that is correct so I'm using the Git program here on the CSE machine but I haven't had to download or install anything and that's because I'm on the CSE machine if I'm using my local machine I would need to install it and we've got those instructions for you up in Web CMmS3。

So I'm going to clone this repository and that's going to take what's on the internet up on Gitlab and put it on my own computer here Now I've got some of these this says X11 forward request failed you can ignore that it's a stupid error that comes up just on the CSE machines and this warning here is basically saying。

 hey， we noticed that you cloned you copied things from you know Gitlab。嗯。And there's nothing there。

 That's okay。 Jess says， are we supposed to be doing this right now。 No。

 you get to just sit there and watch me do it。 You can do it， too， but。

I'm mostly going through things you learn in the lab anyway。

 It's just we understand it's week1 and a little bit of hand holding is really helpful for people。

So I've cloned this repository。 And if I type in L S to look for my files。

 you can actually see there's been a new folder created。 and inside that new folder is nothing。



![](img/44e78d5ea582b3033206b30524834892_41.png)

Because if we go back to Gitlab， it says that it's empty。 I've kind of created a project。

 I've created a bucket of files， but there's nothing in that bucket。Buck it is empty。

So maybe I want to add a file to it。 Maybe I want to add something to the bucket。Right。嗯。

So how I'm going to do that is I'm going to learn a little bit more about some Git commands。



![](img/44e78d5ea582b3033206b30524834892_43.png)

And I'm going jump to this doing work column over here。



![](img/44e78d5ea582b3033206b30524834892_45.png)

So the way Git works is quite interesting， I'm going to create a new file here。

 I'm going to use Gedit， a really simple editor and I'm going to create a file called namess。

txT and in that I'm going to put it name here which is Hayden。😊。



![](img/44e78d5ea582b3033206b30524834892_47.png)

I'm going to save the file， I'm going to close the file。



![](img/44e78d5ea582b3033206b30524834892_49.png)

Right， if I type in LS， I've got the file there now， it's super interesting。



![](img/44e78d5ea582b3033206b30524834892_51.png)

But。I'm going to use some Git commands to have a look at what Git is paying attention to。



![](img/44e78d5ea582b3033206b30524834892_53.png)

Right， so the first command I'm going to show you is Git status。 Now， what git status does。

 there's a lot of information here that is kind of a bit distracting。

But the main thing it's saying is that there are untracked files。 And what this means is that Git。

You're in this bucket of files right now in this lecture test repository， this Git repository。

And it says that it can see a new file has been added， which is names do TxT。

 but Git is not tracking this file。 Git is kind of like I see that。

 but I'm not going to pay too much attention to that until you tell me to。So if I want to say。

 add this file to my bucket。What I'm going to do now is I'm going to write Git add。

 and then I'm going to write names dot T X T。Gitt is the program Add as a command and the names is the file I want to add。



![](img/44e78d5ea582b3033206b30524834892_55.png)

So add is one of the next commands we're looking at。 Git add here。



![](img/44e78d5ea582b3033206b30524834892_57.png)

And now when I go to Git status， I type that again。

You'll see Git has changed its what it's displaying。It's now not saying that the file is untracked。

It's saying changes to be committed。Whatever that means， is my file up on Gitlab yet。

 If I refresh this page， No， it looks the same。 It's still only on my computer。

 or more specifically on the CSE computer。

![](img/44e78d5ea582b3033206b30524834892_59.png)

![](img/44e78d5ea582b3033206b30524834892_60.png)

And the reason it says changes to be committed is because the way Git works is it essentially lets you work on your code as much as you want。

And then when you're happy with your code， you essentially take a snapshot of it。You save it。

There is no auto save。 It's like back in the day when， you know。

 if you didn't save your work and you lost it， it was gone， right， you have to kind of save it。

 And that saving process is what we call committing it， because you are committing。

To some changes that you've made， Ive made some changes。 I added a file。 It was a one line file。

 I've made that change。 Let's commit to that change。 So now I'm going to look at the next command。

 which is Git commit。

![](img/44e78d5ea582b3033206b30524834892_62.png)

![](img/44e78d5ea582b3033206b30524834892_63.png)

And what Git commit does is Git commitit。Says everything that Git is looking at。

 everything Git is watching。Let's take a snapshot of it。The one thing about Git commitmit， though。

 is that it wants a message。 It wants a description of what's happening， which is good practice。

 And you do that by using dash M and then inside some apostrophees。

 you write the message and the message can be anything。 It's totally up to you。

 It's a very human experience。 And that message in this case is going to be created a new names file like this。

And I'm going to hit enter。Great， it says that it's done some kind of commit。



![](img/44e78d5ea582b3033206b30524834892_65.png)

Is it on Git Lab yet？No， it's still not there。 Okay。

 And the reason it's still not there is because whilst we have taken a snapshot。

 whilst we have saved it， we have only saved it locally。 We've only saved it within my CSC account。



![](img/44e78d5ea582b3033206b30524834892_67.png)

![](img/44e78d5ea582b3033206b30524834892_68.png)

So， you know， it's like， I've got my CSC account down here。C， S E。

 And then we've got Gitlab up on the cloud up here。

 And everything I've been doing is just sitting down here in CS C。 So to get that up to Gitlab。

 I need to push。 I need to do Git push， oops。

![](img/44e78d5ea582b3033206b30524834892_70.png)

![](img/44e78d5ea582b3033206b30524834892_71.png)

Push means push to Gitlab。 So when I do Git push。It pushes it up to Gitlab。



![](img/44e78d5ea582b3033206b30524834892_73.png)

A。Now， when I refresh the page。The whole screen looks different。

 and you'll also see down here that it shows me my file， names do TXT。So my file is now on Gitlab。

 It tells you how long ago since I made the commit。And a few other pieces of information。Now。

 if I want to change that file， if I want to modify that further， it's quite simple。

 I can open up that file again。

![](img/44e78d5ea582b3033206b30524834892_75.png)

![](img/44e78d5ea582b3033206b30524834892_76.png)

I can add another line。 Let's add。Fulway， asked a good question we'll get to in a sec。



![](img/44e78d5ea582b3033206b30524834892_78.png)

I can close that file and when I do Git status again。

 you'll see the Git here is like you've changed that file since the last snapshot。

 So Gits always keeping track of what you've done since the last kind of snap。

 the last commit you took of your files and in fact， another useful Git command is this Git log。😡。



![](img/44e78d5ea582b3033206b30524834892_80.png)

![](img/44e78d5ea582b3033206b30524834892_81.png)

Gt log like Git status will show you the files that have changed。 Oh， sorry， not git log。

 I meant git diff。 My apologies， git diff this one here。



![](img/44e78d5ea582b3033206b30524834892_83.png)

![](img/44e78d5ea582b3033206b30524834892_84.png)

Git diff will show you what's actually changed。 So when I run Git diff。

 you actually see here it says you know what， you've changed names dot TxT。

And this was the original file， just Hayden， but you've added a line。So these。

 these are all like ways you can learn a little bit more about what's going on。

So what happens if I want to commit that to， Well， I want to turn that from red to green， right。

 because right now， it says these changes are not staged for commit。

Because before you can actually take a snapshot of your files。You need to add it like this。

 Git add names do TXc。And by adding it， I tell git to like not just like keep an eye on it。

 but get this ready to take a snapshot， get this ready for the commit。So now when I do get status。

 you'll see that it's gone from changes not staged for commit to changes to be committed。

 And now at this point， I can commit again， and I can say added。An awesome person。

And then I can push。 So I've committed it。 Nothing's on Gitla yet。

ca I've just taken the snapshot locally。

![](img/44e78d5ea582b3033206b30524834892_86.png)

But I can push that up to Gitlab。

![](img/44e78d5ea582b3033206b30524834892_88.png)

Now when I look at names。txd on the website， it has both there。Now here's。

 here's like here's help to help paint this understanding between the local and when I say local。

 I mean CSE'cause I'm on， I'm on the， you know， VNC。The lab。When I go to Gitlab。

And I go to repository。And I go to commits， because normally I've been looking at files。

 files is the files， right all the files I have there， But if I go to commits。

 you can actually see the two commits or snapshots I've taken and Gitlabs very， very helpful。

 You can actually click on those and it will show you what each of those commits consisted of the first commit out of this line。

 the second commit added of this line like that。

![](img/44e78d5ea582b3033206b30524834892_90.png)

嗯。And if I look locally on the command line， I can do Git log and Gitlog will actually show me the same thing。

 It'll show me the two commits。 It'll show me who did it。That's a fake email。 Sorry。

 it'll show me when it happened。 It'll show me what the description was。

 And just to show you further， let's say for a second that I modify the file further， and I add。



![](img/44e78d5ea582b3033206b30524834892_92.png)

Im I going to add someone random。

![](img/44e78d5ea582b3033206b30524834892_94.png)

Jess， there you go。 I add Jess to the file， and then I'm going make a new file。 And that new file。

 I do this one with Nno might be called。Drinks dot Txt。And I'll put， you know， coke and water here。

And now when I run git status， you'll see this， you'll see that git says， hey。

There's a file that I'm watching called names。t TXT， that has changed。

But you haven't gotten it ready to be committed。 You haven't gotten it ready to take that snapshot。

 So I have to add that file。 And now when I get status again。

 it's like this file's ready to be committed。 But I also see that there's a new file that I haven't seen before that I'm not tracking。

 I'm not kind of。Keeping tabs on it as much。 It's not kind of in the port。

 It's like that little step further out。 And I'm like， I know Git。

 I would like you to track that file， So I will get add that as well。 Git a drinks。 Now。

 you'll see that both of those files， both of their changes are ready to go， so I can commit that。

Get commit。Added。2 drinks。 And a new name。And then here's the interesting thing。

 When I run Git Logged now， which shows me those commits， you'll see that there's 3，1，2，3。

 But when I go to Gitlab， there's only two because I have like as far as Gitlab's concerned。

 it hasn't gotten any new updates from me。 I haven't pushed at all recently。



![](img/44e78d5ea582b3033206b30524834892_96.png)

![](img/44e78d5ea582b3033206b30524834892_97.png)

So now I need to push， right？

![](img/44e78d5ea582b3033206b30524834892_99.png)

And when I push， Gitlab will now have three things on it。 So there's this kind of， you know。

 pushing is how you keep updating Gitlab with your changes。Now a good question that was asked。

From foul ways， foul wayss is why do we use a command line to do all this instead of a goy。

 Why are we bothering to use a command line？ That's a great question。

What I would say is that without kind of going into a lot of examples that might not make a lot of sense yet。

嗯。There's a lot of stuff you can do on command line that there just isn't a way to do on the GooeI。

Using the command line is actually a lot quicker， a lot of the time for a bunch of different reasons。

 but a good programmer will use the UI and we use the command line both for different reasons。

 So being comfortable with both is important。嗯。Alex says， why would you wantan to only up。

 Why would you want to only locally update your repository instead of also committing it？ Well。

 sometimes you work on things that aren't really ready to be saved yet。 Like they're essentially not。

 you know。Sometimes things have to get worse before they get better， you know。

 like you ever drawn on something。 You don't want to like save a copy of your drawing when you're like two lines in or three lines in or you're not even sure what you're doing。

 Sometimes you just want to get just a little bit more into it。 And then you're like， okay。

 this is a moment Now let's save it。 Bob says， what happens if two people pushed to Gitlab at the same time。

 we will get to that in the next lecture。 That's what the next lecture is about。

 I think that's all the questions。 yeah mate Jay asked a good question。

 says if we clone will we get names do Txt。 So this was also a question asked earlier。

 let's imagine for a second that I just delete this folder。 It's gone。 Thankly。

 I pushed everything before I deleted it。 But because everything's up on Gitlab。

 I can now just go to Gitlab and I can just go and copy the URL and I can go Git clone and then。



![](img/44e78d5ea582b3033206b30524834892_101.png)

![](img/44e78d5ea582b3033206b30524834892_102.png)

![](img/44e78d5ea582b3033206b30524834892_103.png)

Paste that in。Oh， that's the wrong thing， whoops。get clone and then paste that in and then it will clone it and I will have all my files here。

 I will have my history here of commits as as you'd expect。



![](img/44e78d5ea582b3033206b30524834892_105.png)

So we just touched on all those commands， right， log di status add commit push clone。The next thing。

 before we move on to the end here。 So we'll probably run another 10， I don't know，5 or 10 minutes。

 then we'll take a break。 Then we'll get on the working in a team thing。

Part 2 is version control across multiple machines。So what I mean by that is like， this is just you。

 So forget about like other team members for a minute。 We're just actually talking about like。

I have a laptop and I have a desktop。Or if you have a laptop and you use VLb。

 these are all different software。As far as anyone's concerned。

And we're going to look at how can you actually like just yourself work between two different devices。

 which helps it like it's like a baby step into the next topic two last quick questions here from people before we move on。

My software hasn't updated for some reason， so I can't select them。 But Ran says， if you gi add。

 but delete the file from your machine， does that mean that you can't get the file back using Git。

 I really like that question。 I'd actually like to answer that before we run out keep moving。

 So let's watch this here。

![](img/44e78d5ea582b3033206b30524834892_107.png)

I've got my names。 Let's say I didn't like the drinks file。 I'm going to remove the drinks file。Now。

 when I get status， you can see it gets like， okay。I you haven't。

 You haven't gotten anything ready for committing。 so I can add my drinks file。 Now。

 that might be like a weird thought because you're like。Extraitiont even work。 I think it does。

It's a bit complicated。 you add it because you're not like adding the file。

 you're adding the you're adding the changes to the file to the staging area like you're adding is in get ready。

 So by add it's like get ready to delete that。 And now when I commit it and I do deleting drinks。

And then I push that and we go to Gitlab。 You'll notice that the file is gone。 It's not there， but。



![](img/44e78d5ea582b3033206b30524834892_109.png)

The history of it there。 If I go to commits here， I can actually go back to the previous commit on Gitlab。

 and I can see the files or even better on Gitlab。 Let me get rid of mate Jay's。Comment。On Gitlab。

 for every commit， you can actually go and look at what all the files were at that moment in time。

 So let's say someone did something silly。 You can go back and say， you know what。

 I'm going to go look at what everything was during the last commit。

 And then you can see the files there。 So it's all preserved。 the point of Git。Is that in theory。

 it's meant to be like somewhat immutable， unchangeable so that， you know， if you delete something。

 it's you're always moving forward， even if you're deleting things， it's always a step forward。

 you know， and that's really good because it means you're preserving history and everyone's kind of familiar with that。



![](img/44e78d5ea582b3033206b30524834892_111.png)

So if I move on to working on multiples of your machine。嗯。



![](img/44e78d5ea582b3033206b30524834892_113.png)

This gets a bit interesting。 And what I'm going do here to demonstrate this is I'm going to use my local machines。

 This is the computer I'm lecturing on at the moment。 And in fact。

 let me change the background just so it's really， really obvious。 What colour do people like。Green。

有eller。Yeah。B back， black red。

![](img/44e78d5ea582b3033206b30524834892_115.png)

Purple。That's， that is painful blue。

![](img/44e78d5ea582b3033206b30524834892_117.png)

Oh，All right， let's。饿。No， how do I change the let's make it a light colour。 How do I change the。😊。



![](img/44e78d5ea582b3033206b30524834892_119.png)

Screen text， black， perfect。That's better， Isn't that nice， isn't that nice。

 So what I'm going to do here is I'm actually going to get Vlava side by side。



![](img/44e78d5ea582b3033206b30524834892_121.png)

![](img/44e78d5ea582b3033206b30524834892_122.png)

🎼Like this。 So we've kind of got like， So here's what I want you to imagine。 In reality。

 you'd be doing this on different computers。Right， like over here， over there。

 you'd be doing it at different times。 Like， you might go work on one computer here and you go work on another computer later。

The right hand computer will call it yellow， and the left hand computer will call it black。

 Black is my CSC machine。Yellow is my local machine。So so very， very fun。

Let's imagine that you've been working on lecture1 test on the CSE machine and you want to go work on it on your local machine。

 So what you do is you get home from the uni you log into Gitlab you go and click on the clone button you copy it and then you come over here and you get clone and then you clone it on your own local machine just like you did on the CSE machine and you clone into that and then I can go into that folder like this。



![](img/44e78d5ea582b3033206b30524834892_124.png)

Got to mute this computer。 lectureture one test。 got to move this。Can't see anything。There we go， So。

 you know， there's my lecture one test now in there I have。Names dot T XT。 And over here I have。

 you know， names dot TXT。 And if I get log。There's my four commits。And if I get log。

There's my four commits， right， everyone's in sync。



![](img/44e78d5ea582b3033206b30524834892_126.png)

So now you've got kind of a model where， you know， Gitlas up here and I've now got my local machine God the writing is horrible。

 I've got my local machine。 and， you know， you know。

 CC talks to Gitlab and my local machine talks to Gitlab and they talk together like that。

 So these things are all kind of linked up。And what we're going to do is we're going to imagine what it's like to make more changes on CSE。

And to try and sink them up。So。Let's now imagine。嗯。



![](img/44e78d5ea582b3033206b30524834892_128.png)

Let's now imagine。That on the CSE machine， I'm going to make a new file again。

 right that new file can be called food food。 TX。嗯。Where I have， I'd， Id rice paper rolls for lunch。

 And for dinner， I had a sandwich。Bit of a weird combination。 I've created that file。 I gi status。



![](img/44e78d5ea582b3033206b30524834892_130.png)

I get add。So let me move that above that silly thing。 I get add food dot Txt。I get status。

 I get commit。Adding food。I get push。Now it's up on Gitlab。

 You can see that because I've got five commits and I've got two files， but locally。I only have。

F commits， and one file。We want to go to Gitlab here。There's two things there。

 So I've made the changes unlike my machine 1。And then I've gone to push it up to Gitlab。



![](img/44e78d5ea582b3033206b30524834892_132.png)

So now Gitlab has it too， but my other machine doesn't have it。

 and that's why we need to look at this really important。😊，Command， get pull。



![](img/44e78d5ea582b3033206b30524834892_134.png)

And what Git pullol will do is Git pull is like the opposite of Git push instead of you pushing your stuff to Gitlab。

 you are pulling down from Gitlab right instead of syncing upwards， you're sinking down。😊。

Now I get pull on my local machine， and that will pull it down from Gitlab。

 and it tells you a few things， you know， like oh。You have。Your food dot T X T file was created。

 and two lines were inserted， you know， and now when I do L S， I have my two files。

 and when I do Git log， I have my five commits。Similarly， I can do something on my。

Local machine here。Right。I can add a new file， or I can modify a file。 like let's modify food。

What I have yesterday。 I had Zeus。 Anyone know Anyone knows  Zeus like that。Greek style。

 mid market food place and。I don't remember what else I had。Doesn't really not aki or something。

 Yeah， sure， that's good。

![](img/44e78d5ea582b3033206b30524834892_136.png)

And， you know， I get status and I'm on my local machine， I add food， get commit， adding more food。

And then I push that up to Gitlab， okay？Then Gitlab has。3fi it has， you know， the updated files。

 and it shows you， right， Like names was last modified 11 minutes ago and food was modified 15 seconds ago。

 But again， similarly， if I open food on on CSC， it's not up to date because it was just my local。

 which is pushed to Gitlab。 So if I want to get the latest changes， I gett pull。



![](img/44e78d5ea582b3033206b30524834892_138.png)

And there's the gi pull。 And now I have those latest changes inside of。对。That is the latest changes。

Right。嗯。Now， three of you ask the same question at the same time。 Great job。

 Simon said what's the difference between pullingey and cloning？😊。

Clonning is creating the repository。 It's kind of like a first pool， if you will。

 You only clone at once。Once you clone and it exists， pulling is just about staying in sync。You know。

 it's kind of like the difference between creating a dropbox account and syncing it constantly。

 you know， you only create it once and then you're just sinking forever。Now。

 the last thing before we have a break is the eternal question。Of what happens？

If two people modify the same line at the same time。 And， and this。

 this doesn't really happen with you as much。 But like this is a preface into to what happens next。

 So let's imagine that me over here， me version 1 on the CSE machine。 You know。

 I'm working at uni today and I go and modify this file。 And I say， you know what， it was。

 it was a ham sandwich。Okay， yeah， it was a ham sandwich。 Yeah， ya， yeah。 Okay， get add， get commit。

Ham sandwich addition。Get push to get lab all of that。 Okay， cool。 And then later on。

 I come home and I forget that I fix that。 This happened sometimes。 I was like， oh。

 I've totally forgotten that that happens。 So I， I open it up。 and I think， sorry， I open it up。

And I go， oh， oh， oh， I swear I did that。 Okay， okay， maybe I'm crazy。 And then I， then I， I'm like。

 I was a ham and cheese sandwich。 Okay， great。😊。

![](img/44e78d5ea582b3033206b30524834892_140.png)

And then I come here and I say， all right Well， I'm going to add my food。

 and now I'm going to commit and say， you know， ham and cheese， sandwich。Description added。

And then I go to push。And then it goes， no， you can't do that。 I'm like。

 why it's given me all these very scary errors and red and some yellow errors。

 And it kind of makes sense because on Gitlab right now。

What's happening is that this says ham sandwich， but locally I've got a file that says something slightly different。

Now， the problem here is not necessarily that the line says something different。

 The problem is actually to do with。

![](img/44e78d5ea582b3033206b30524834892_142.png)

What we call the Git tree， which I think， I don't think we talk about much in this lecture。

 We talk about it a bit more in the next lecture。 And what I mean by that is like。

 what's actually happened here， What's actually been happening this whole time is that Gitlab。

 the website。

![](img/44e78d5ea582b3033206b30524834892_144.png)

嗯。Is sitting here。In the middle。Right， and it's got a bunch of commits。

Let's just imagine that there's only been three commits so far。And the way Git works。

 And this will start to become a bit more clearly as we go on。

 is that whilst you might think the git is really something that is like tracking your files。

 Git more specifically。Is actually tracking your commits。 Git is a commit。

 Traing tool is a very helpful way to think about it。

So what happens is when I go and make another commit。Right。

 let's imagine that these commits are all joined together like a， you know， like a long chain。Right。

 so let's imagine we've only made three in reality， we'd kind of done five commits。

 but I'm too lazy to draw more stuff。 So what happens is that you make it a commit on CSC like this and you go。

 okay， there's my commit。That's what happens。 What I'm just doing here with the circle on the line。

 That is the Git commit command。 You are adding another commit in the chain。What Git push does。

 and this is really important from like a theoretical understanding。It doesn't push your files。

 It actually syncs your commit chain。 Its it syncs your commit history。 It actually says。

 hm hey Gitlab， I've actually done some stuff since we last talked。😡，This is what I've done。

 There you go。 Now you're up to date。 You're pushing those new commits to Gitlab。Here is the problem。

 though。 This， this blue one over here is the is the， you know， it's the ham sandwich edition。

 but then locally。Locally， and I didn't do any git pulls， right。

 I came home and I didn't do any git pulls。 So as far as my local computers concerned。

 that's all that's happened。 I go and make a commit locally， like this。And that commit is the。

Ham and cheese sandwich。Now， here's the problem。 The way Git works， it does not。Just automatically。

 when you push， jam things together for you like that。

 So when I'm over here on my local machine and I go， hey， get。

Let's make sure that we've done the same stuff。 Git just won't be like， yeah， sure。

 I'll just like shove this somewhere。 Git looks at it。

 And it's like your in my definition of history is not the same right now。 This isn't good。 You。

 you are missing something and you've got some stuff。 So the way。

 the way you then manage this with Git。It's a little bit weird because Git Git can deal with these what we call conflicts in a way。

But。It， it only does it on the pulling when you pull in。So when I try and push， it fails。

 but watch what happens when I try and pull。When you pull。What Git will do is it will basically say。

 all right， all right， all right， I'm going to take this and it kind of like tries to jam them together for you。

And then you， you go and fix it on your own machine。 Basically， get can。Merge stuff。

 Git can shove things together， but it doesn't want to do it on the Gitla server。

 It wants you to do it on your own machine and then push the new stuff to the Gitlab server。

 So when I go to my CSE machine and I look here， the last commit was ham sandwich， The blue 1。

 When I come here locally。

![](img/44e78d5ea582b3033206b30524834892_146.png)

My last commit was the green one ham and cheese sandwich description。When I did that pool。

Getit pulled the files。 And then it said conflict， merge conflict in food Dot T X T。

 And when I open food Docs T X T， you'll see that Gi has this really ugly。

 awful looking thing here where it's basically just said， hey， Hayden。

 these are the two things that I've seen。I see that you had ham and cheese sandwich and other you had ham sandwich。

 I don't know what to do。 So here's the stuff。Heres I'll put some equals between it and a few lines so you can see where it is。

 And this point is where a human， you， me， anyone else， comes in， looks at it。

 talks to people and says。What should this be， now， Obviously。

 this should probably be ham and cheese sandwich because it's more descriptive。Right。Oh。

 have I been a first silk sandwich， sandwich。I'm really worried， did I spell that wrong？No。

If I did that's hilarious sandwich。Oh， I have。Oh， which。 Oh， yeah， Of course。 Not which。

 That's funny。W which sand witch。I was like not sure if there was。

 I was like I'm pretty sure there's a D right， anyway， let's whatever。 So we've done that correction。

 And it it't。 this is a good example。 It doesn't have to be one of the two。

 It can be anything new there。 And what happens is when I save that file。

 Git wants me to add that file like this。 and then I can commit that file like this。

 say sandwich resolution。

![](img/44e78d5ea582b3033206b30524834892_148.png)

And then I pushed that。Now here's the interesting thing when I push that。



![](img/44e78d5ea582b3033206b30524834892_150.png)

You'll see that it is updated on Gitlab， but now let's have a look at the Git histories。

On my CSC machine， it's still just those commits， those five commits in the new sandwich edition。

 just the blue commits。 But on my local machine， it's a bit more complicated。They have my。

 they've somehow shoved in my blue commits， then my green commits， and then another commit。

 which we call a merge commit。

![](img/44e78d5ea582b3033206b30524834892_152.png)

So what's basically happened is when I did that pull from Gitlab， it said， all right。

 let's go and take what was on Gitlab。 Let's shove that down here。 Let's shove your thing on top。

But then it's kind of complicated because there were problems there。

 So let's actually make another commit。Yeah， like that。And then when I push to Gitlab。

 you'll notice that the difference now is that my local is now literally just an extension of Gitlab。

 like that's that's kind of what Git wants when you push it wants what you have to just be an extension of what's on Gitlab。

 not something different。So now when I push to Gitlab， it looks like that。

What I have locally though is still behind because again what I have on CSC is behind because CSC doesn't know any of this happened。

 so on the CSC I now have to pull and that will pull the new stuff from Gitlab like this。

So Git is essentially just a a history of chain commits。

That is constantly trying to stay in sync with the devices that use it。Now， the very last thing。

 very last thing before we take a break。 and it's a really good question。Is from。Paerrce or petrce。

 or。I'm sorry again， your names。Oh， maybe it wasn't。

 Maybe that wasn't quite what I was thinking it was。A。

I've actually shown you the absolute worst case because Git is pretty smart。

 Git will figure this out if you don't touch the same line。 Basically， if Git can be like， hm。

They've edited different things。 It will。 and I'll show you what I mean。

 Let's imagine that a similar thing happens now inside of names。

Where I come along and I had a last name to Hayden。 Okay， I had my last name there。And I go and。

 you know， I go and get at that， and I go and commit that。Adding last name to Hayden。And I push that。

 So now Gitlab， my local machine， push those changes up。So now my local machines， you know。

 it has like a。It has like another commit here， like this。



![](img/44e78d5ea582b3033206b30524834892_154.png)

And then Gitlab has that exact same commit。 But then locally I come sorry。Locally。

 I have that commit。 Gitlab has that commit。 But then on the CSE machine。

 let's say I open up names and let's say I update Jess's name。 and Jess's name on YouTube was。

What was it L， great。 So it Jess has a last name。 L。 And now I do the same thing。 onm like， you know。

 get status， get add like this， get commit， adding Jess last name。And then I go to get push because。

 you know， I've added this， I've added this new commit on locally here like that。

But when I go to push， watch what happens， gets like up， the history is different。 Again。

 it's like stop trying to。

![](img/44e78d5ea582b3033206b30524834892_156.png)

Stop trying to update me when the history is different， right， gets like。

 I want what you have to just be an extension of what I understand。

 It wants to see this Sorry that the colours are so similar， I should。Do a different color。It's like。

 I just want to see that like what you have is just this plus more。

 So I do what I did to solve it before， which is that I do a gi pull。



![](img/44e78d5ea582b3033206b30524834892_158.png)

And you'll see when I do a Git pull that I get this weird message here and this this is kind of something you can just close。

 I'm going to close it with controltrl X， but if it comes up another way。

 you can close it another way and what Git has actually done here is it's done that merge part automatically for you because Git was smart enough have a look to realize that those two changes happened at different parts of the file and it just kind of mixed them together。

😊。

![](img/44e78d5ea582b3033206b30524834892_160.png)

So now I don't need to do anything except push it。So it's like what happened was Gitlab had one version。

I had on my CSC machine another version，1 I pulled， I pulled that in and Git was like， blah。

 like figured it all out。 And then it's like， here's the new like Frankenstein code。

And then it's like， can you push that back up to Gitlabs and Gitlab has that and to Maggie's question。

So we could get pulled frequently to avoid such a situation。 Yes。

 so one of the best ways for any team to work together。

 which we'll get to in the next lecture after the break， is to pull。

 to push your code frequently and to pull frequently。

 The more often you are in sync with your team members， the better。

 But everything I've showed you today applies without a team。 It's it's every kind of。

 it's the experiences you could have just working by yourself on a lab on the lab and locally or on locally on two devices or anything like that。

 So let's take a break。😊，And then we are going to have a look at a little bit of an extension of this where it might be a little bit painful in terms of。

You know， understanding， but we'll try our best to understand how this works when you're then working with multiple people。

 And just to summarize before we do the feedback screen。

 this is a summary of all the commands we've looked at today。Cning status log add a di commit push。

There's a few nuances here that I'm not going to talk about tonight because it's the first lecture。

 but we will come back to them and we'll talk about them a lot throughout the course And then lastly if again。

 just for this particular lecture， if you wanted to leave some feedback。

 you'd be more than more than welcome App it， but let's take a。Let's take a five minute break。

7 minutes。 Let's do 7，27。

![](img/44e78d5ea582b3033206b30524834892_162.png)

And then we'll keep going so。Thank you。