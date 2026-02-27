# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p47 -48-COMP1531 22T2 - 1.3 - Git - Team Usage.zh_en -BV17RXGYuEaM_p47-

Welcome back， We back from the break for those who are tuning in live。I。

 I I wouldn't wanna listen to me at 2。5 times speed。 That sounds scary。😰，嗯。

But welcome to those whove played catch up， I guess。So for the last part of tonight。

 we are going to expand everything we've learned。And talk about how Git is now used in a team。Right。

Before we get into that， though， I've， I've got a few people already Ive seen a few tonight that are like。

 oh my God， these lectures are next level。 One thing I didn't mention a lot of at the start of the course is that this is a。

What I call a front heavy course。 And what that means is that it really feels like it kind of hits you。

 and then you settle into it。 And there are other courses in CSE that like the first few weeks are kind of like a bit of a joke。

 And you're like， yeah， get it。 And then it just like ramps the hell up。

 and then you're just absolutely drowning。 There's someone more nuance to that。

 But all I'd say is that there's quite a lot of new concepts that will come out。

Like straight out like at the start of the course so don't feel overwhelmed againca we're aware of that and again。

 a lot of this tonight is just to give you what it is knowing that it will take 10 weeks to get comfortable with it。

So let's get into this whole team usage of Git because the whole point of Git is that you work with other people。

 there's no point like， you know， there's not much point doing it by yourself so。

Let's go in this lecture gets useful primarily when you're working with others and working with others efficiently and effectively is important。

 we're going to learn about branching， merging and merge requests and thankfully we've done the harder parts in the previous lecture。

 everything we're doing is live demo。 So not a ton of theory。

 but if you'd like to go look at some more theory， Adlassian has an incredible guide that goes through gi in excruciatingly efficient detail。

 though I don't think that's necessary for the majority of you。

 only those who really want to get a bit more of an understanding。😊。



![](img/761647906d4d4747df430ce185d1d167_1.png)

![](img/761647906d4d4747df430ce185d1d167_2.png)

Now。Very funny， Angu， And so。One thing that's critical for this lecture。 Last lecture。

 we talked about how git is essentially a history of a chain of commits。

 We have diagrams like this in paint。 However， what is more critical to understand is that whilst we have these nice little chains when you use git day to day。

 you're actually dealing with something that is more treelike in structure where whilst it is like a chain of commits。

 it's not just like a line like a snake， but it actually branches off like an actual tree。

 And the way this works， which I mean， we'll get into the details。

 but it's kind of like you know every git repository will have， you know like a first commit。

 and then that might have a commit here。 And then someone might take it over in this direction and someone might take it over in that direction。

 And in this way git can kind of be very treelike。 Now。

 what this means is kind of weird and confusing。😊。

![](img/761647906d4d4747df430ce185d1d167_4.png)

![](img/761647906d4d4747df430ce185d1d167_5.png)

![](img/761647906d4d4747df430ce185d1d167_6.png)

嗯。But。

![](img/761647906d4d4747df430ce185d1d167_8.png)

Some demos will make that clear， but the most important thing here is we just understand that Git is a series of trees。

 So instead of just a line here， like the green one we looked at。

 there's actually kind of like this branching element now。Each commitit always has one parent。

 just like a tree， you know， a tree while it might branch out to a few different children out towards some leaves of the tree。

 it always has one parent， it always has one kind of origin。😡，That's really important to understand。

 but each commit can have multiple children every every commit came from only one other commit。

 but each commit might head off into a couple of different directions in terms of commits。

Every time that we。Kind of headed out into multiple commits。

 we call that process branching and every time we try and bring those branches back together。

 we call that process merging。And in a lot of ways。

 the essence of what we try to do with Git is to actually avoid this branching element。

The world's most beautiful git repository actually looks like a chain that we did in the first lecture。

 it looks like one of these。😊。

![](img/761647906d4d4747df430ce185d1d167_10.png)

So this whole idea of branching isn't actually something thats incredible。

 it's actually like a necessary evil that we try and avoid。😊。



![](img/761647906d4d4747df430ce185d1d167_12.png)

That's not the right description。 It's a necessary evil that whilst we use it。

 we don't want to go crazy with it。Now， one thing we haven't talked about on with Git is that this idea of branching and if we go back to the repositories we were looking at in the previous lecturehow。

 what you'll notice when I say git status。

![](img/761647906d4d4747df430ce185d1d167_14.png)

Is that I have a branch here called master now now master is the is the essentially the main branch in the repository that is like the primary branch you know。

 the alpha branch， the whatever， it's like the branch in charge， the main primary branch。

On Gitlab you'll see though that if I go to branches。

 there is just one branch which is master and that has my files on it here。However。

 and if I can simplify that for a second， let's just imagine to date that all of our commits。

Have been。Like this。You know， and， and like my， my master branch looks like this。



![](img/761647906d4d4747df430ce185d1d167_16.png)

Now what I can do is I can use this command here。

![](img/761647906d4d4747df430ce185d1d167_18.png)

Get checkout dash B。And what checkout means is checkout means go check out another branch。

 Go check out a different version。 and the dash be means like to create a new branch。

 The git syntax is a little bit weird。 but this means create a new branch。 Now。

 if you don't know what I mean by branches and it's kind of just like freaking out。

 think of them like， you know， parallel universes。 If anyone's seen the new doctor Strange。

 it's pretty average， I thought， But you know， it's okay。

 it's like kind of all these parallel universes operating side by side。😊，You know。

 so I've got my master branch over here。 and when I type in this command and I'll create a new branch。

 and I'll call this new branch， Brandon， you know，cause Brandon posted a comment。



![](img/761647906d4d4747df430ce185d1d167_20.png)

And I type in gett check out Dashby， Brenan。U。What I'm actually doing now is I'm moving to another branch called Brandon。

And you'll notice here that if I get status， it now has on branch Brenan in the text。However。

 on Gitlab， you'll notice that I still only have。1 branch。

 And that's because just like everything else with Git， I haven't actually pushed anything。

 right to Gitlab yet。 So I'm on this new branch。 And you'll see what happens if I do Git push。

I actually get this kind of strange error。And what this error is saying essentially is that you're like。

 hey， I understand that you want to push。But you're telling me you're on a branch I've never seen before。

 It's basically saying Gitlab doesn't know this branch exists。 you know。

 So you actually have to kind of copy and paste this command in like that。

 And you have to do that once and。Then， you know， that's like the first push you have to do。

 And then after that， you can keep pushing。 So because it's a new branch。

 you have to use that command for the first push。 Now， you notice when I go on Gitlab here。

I've now got two branches， kind of like two parallel universes of code。

And if I go and if I come back to my files here， I can see this is my master branch， okay。

 with my food， and then I've got my Brandon branch， right？Just like another parallel universe。

 And then I think， well， actually， I want to make some changes to my Brandon branch。 So I go to。

Let's go to names。Let's delete all three names and write Doctor Strange like this。Now。

 similar to before I'm going to， you know， go and get add names and I'm going to get commit Doctor Strange。

 something。And then I'm going to push that， which will push it to the Brendan branch。

 And now you notice on Gitlab that if I'm on the Brenan branch and I click on names it says Doctor Strange。

 but if I go to the master branch， it has the original stuff。

Because what's actually happened here with Git， like what's actually happened is that I've essentially gone and。

Created a branch over here。Like this。And right now， Brendan， the branch。Brenddon。

 the branch has quite a ring to it。 Brenon， the branch over here is like that commit。

 That's the Doctor St commit。嗯。Doctor Strange。

![](img/761647906d4d4747df430ce185d1d167_22.png)

And then similarly， what I can do with Git if I would like to is I can actually swap。Swap branches。

 if I'd like to， with the get check out command。 But I don't need the dash B any more。

Because I have already created the branch so I can go back to master。And like。

 this is me swapping between these parallel universes， right， dreamwalk。Okay。

That was funny And then if I go to nano names， if I open up names。

 you'll see that on my master branch I have all the original names because the master branch right now is。

 you know， it's sitting over here。😊。

![](img/761647906d4d4747df430ce185d1d167_24.png)

And it's kind of pointing to this commit。Like that。And if I check out Brendan。And I look at names。

 It's a different code， right， You can only look at。Yeah。😊，You can only look。At one branch at a time。

 this is really， really important。 Like the way the git command line works is you can only like。

 you can only be looking at a branch at a time。 You can swap between them。

 but you have to like look at one at a time。 I could go back to the master branch if I wanted to。

 and I could also modify names。2 scarlet witch， as I heard with， width， Slet width。 Okay， that'll do。

 I could modify。 I could， you know， make a commit on this branch， Scarlet width。

And I could get status it。And I could get at it， and then I could get commit。You know， S width added。

And then I could push it， and in this case， I'm pushing it to master。Right， which。

You guys are quite funny tonight。Normally students aren't that funny， but I'll give you。

 I'll give you a nine out of 10。😊，3 in a row made me laugh in five minutes。

 So now what you'll see on Gitlab is that if I'm on the master branch， it says Scarlet width。

 and if I'm on the Brendon branch， it says Doctor Strange。 And if I go to commits。Right。

 and let me just draw this out for you。 So what I kind of did here was I made a commit up here on the master branch。

Like that。's that's the scarlet width commit。You'll see that if you look at the git history。😊。

They both have a common history of this commit， this merge branch master。Right。

 but they both have like a different next commit。 So you can actually see the gi hiness happening here。



![](img/761647906d4d4747df430ce185d1d167_26.png)

So。With branching and git。 And this is， this is， this is conceptually very strange。 Like。

 this took me honestly years to kind of figure out naturally，cause I was never taught this at uni。

 like a lot of people weren't。

![](img/761647906d4d4747df430ce185d1d167_28.png)

But， branches。A really just pointers to a commit。 We call them that there's kind of two ways you can approach this topic。

 You can approach it very， like tactile。Which I like to， because I have a little brain sometimes。

 which is like， I like to think of them as like totally separate parallel universes。

It's like I've said， it's like， okay， I got my Brandrenon branch over here and my master branch over here and they're just like totally different。

Then there's the more actual， like academic， literal theoretical way to look at it。

 which is that branches are essentially just pointers to a particular commit。

 And each commit has a chain， right， Because remember how we said before that every commit only has one parent。

 That means if you can point to a commit， you can get an entire linear history because every commit only has one commit before it。

 And that's how Git gives you this。 because this is like a linear history。You know。

 so even though like so you can see there it's like master points here。

 but the linear history is there， Bon points there， but the linear history is there。

So that's a little bit of a background when it comes to。Branching。Now。嗯。To Meriddian's question。

 which is the question。What are different uses for having multiple branches。

 Well there is one use in particular， which is that when you code。And you're in a group of people。

 Let's imagine that you have a stable repository somewhere。 piece of code that works。

 And you have five people you're working with。 And each of you is working on a different thing。

You don't want to just all be pushing to the same master branch。 Otherwise。

 you're all going to be constantly pulling and getting merge conflicts and everything。

 You kind of want to be able to like go and， you know， to carry the analogy。

 You want to be able to go and do all your work in separate parallel universes。 And when it's done。

 bring them back to like the main universe of code。And a good example of this is， let's say that。

Let's say that we have our master branch here and let's forget about Brenan for a second。And。

You got your master branch and pretend the other branch doesn't exist。I'm on master。

I'm going to come along now， right， So let's， let's do this in parallel。

Let's make sure we're both on master， local and CSE。Right。嗯。And now。

Local person is gonna go work on a feature。And CSC person is going to go work on a feature。

 When I say feature， I mean code， they're going to add something to it and it's going to be really simple because we haven't done any coding in the course yet。

But the local person is going to make a new branch and they're going to call it Hayden because that's who I am。

And the feature they're going to add is a drinks drinks list， that's the name of the branch。And then。

 over here。In the same evening， same night， there's going to be another branch created called。kaai。

Slash。It's Ka gonna do cars list。 Ka Ka's gonna go do some stuff with some cars。 So， you know。

 Hayden over here works on the drinks list。 I'm gonna make a new file called drinkrinks dot T X T。

 I add Coke。 I'm like， great， okay， good job。 Like， I do this， oops。Get add drinks。

You'll see that I'm on the Haden drinkrinks branch and then you know I've made it some changes。

 I'll go and push it。But。Because it's my first push， I have to do it that way。

You'll see that I push my， my drinks thing， my drinks list。

 you'll see I've got a new branch on Gitlab with my， you know， drinks list。



![](img/761647906d4d4747df430ce185d1d167_30.png)

It doesn't seem to have the file。

![](img/761647906d4d4747df430ce185d1d167_32.png)

That hell。Oh， I forgot to commit it， okay。So what happened there was I actually made a new branch。

 but I didn't make any commits， so when I pushed it。It's kind of funny。

 So what actually happened here was like， say you're on master and I made a new branch called。um。

Hy and slash drinks list。And Hayden slash drinks list when you make a new brand。

 you actually kind of just point to the exact same commit and then once I say make a commit。

 it's like coming up here。And it's like pointing to that。

 So because I pushed without committing H and drinks list actually pointed to the exact same commit。

And you can you can kind of see that right because you'll see here that if I go to like the commit history。

 Hayden drinkrinks list has the exact same history as master。

 They're the same they're the same history。

![](img/761647906d4d4747df430ce185d1d167_34.png)

So now I'm actually going to add。

![](img/761647906d4d4747df430ce185d1d167_36.png)

That。I very oops， wrong， wrong terminal。I got to add my drinks， which I've already done。

 I forgot to commit it。First drink。And then I go push， okay， and now I've got， you know。

There's no more commits on master， but there is a new commit on the drinks listca I've made another commit up here。

 And let's go make another couple。 You know， let's go and make like， just for fun。

Another few like this。 just to just to keep the analogy going。 open up drinks at another one。

 Pepsi Phanta。Cool， get add drinks， get commit。Two more drinks。 Get push。Okay。

 and then I want to edit it further。And I make another one， like water。You know， get add， drinks。

 get commit。Forgot to add water。And then get push。So now what I have here。It have a whole bunch of。

Commits，3 commits， exactly， three new commits that have come from， you know。

 first drink to more drinks and forgot to add water。

 And this has all happened over here on a parallel universe。



![](img/761647906d4d4747df430ce185d1d167_38.png)

But separately， someone on the CSC machine might be working on that other feature like Ka。

 the Cars list， and Kai might come along and make a new file called cars with Honda and Toyota。

 and then Kai might go and add cars。And then say， you know， added first two cars。And then push that。

 but it's the first time we've pushed our branch， so we need to， know copy this。



![](img/761647906d4d4747df430ce185d1d167_40.png)

Paste it again。So we pushed that up。And now you'll see that the scar at which added。

Which is this master commit here。This branch Haden drinks list has gone and got one commit over there。

 And then my other branch， well Ka's branch， which is Car list。It's gone and got a commit over here。

So we've kind of like Kai and I have kind of gone off and done work separately。

You know I've done work over here。 Kai's done work over there。

 and this is good because our work is still ongoing in theory， we haven't finished it yet。

 so we don't want to go and add all this crap to the code base for code。

 we don't know if it works yet。But once we're happy that it works。 once we feel good about it。

 the next step is actually the first time that we use。😊，The U I on Gitlab。

Cause you'll see here that I've got these branches。Hyden drinks list。And let's say now that I'm like。

 I'm done with my drinks list。 The code I've written is finished。 It's good to go。

 I want to get it into master。Bring it back into master。

 So what I can do is I can actually click on this big merge request button。

 I'm going to use the Gitla Ui now。 I click on that merge request button。

 What the hell is a merge request， a merge request。Is a gooei based way。

To merge one branch into another， it's a way to try and。

Collapse these two things back together to get rid of my branch。

 because I only want branches to exist as long as I need to actually make the thing。 Now。

 here's my title drinks list。 I might call this like edition of drinks list。

And then I say description and， you know， added a drinks list with four drinks that were popular。嗯。

This is a good start。Okay。And what I do is I come down here now and I click createre merge request。

Now what this does is this actually creates a little visual window here。😊。

Whereby I can have a look at this。 It's like a merge request is essentially a request to merge code into master。

And it's very， very literal。 It's like request to merge my branch into master。

 Here's the title of it。 You can see the commits that were made。

 You can see the summary of the changes。 This is what's different between master and the work I've added。

 And the reason we actually have these merge requests。 It's not necessarily for you。Or Hayden here。

 Ca Hayden wrote the code。 It's for Kai。 It's for Angus。 It's for Ran。

 the other people in my team of five people。And what happens is I would typically say I do some work like this and then I'd say。

 up cool， and then I'd come down and you know I'd send this on Microsoft Teams to Kai or Angus or something and I don't know if Kai is still online。



![](img/761647906d4d4747df430ce185d1d167_42.png)

But if Kai is still online， I can add Kai to。You don't。

 you don't ever have to do what I'm doing here。嗯。Cause like we set the sort up for you。

 But let's say that I'm working in a team with Kai。

 So we're working on this little code together and， and you know。

 you'll have you'll have lots of people。 you know， you'll be in a group of five。



![](img/761647906d4d4747df430ce185d1d167_44.png)

You'll see here that what Kai might come along and do is Kai's given a thumbs up here。

 so Kai's actually kind of given a thumbs up and how Kai and I work together in our team is like up to us like Kai might hit the approve button or the thumbs up button or Kai might say looks good to me and essentially it's good practice when you write code to make sure。

That when you write code before you merge code into master。

 that someone else in your team says it's okay。 It's kind of like a simple sanity check approval。

 So Kai， by giving a thumbs up here is like， yep， this is fine。

 And then what I can do is I can click merge。And when I click merge， git， the。

 the interface will literally take this， and it will merge。These changes onto master。

 because remember the last time master was was at Scarlet Witch。 So it's now like masters now this。

So it's kind of like we collapse these like parallel universes together。 So instead of， you know。

 these two things happening separately， they're now happening， you know， it's come back into master。

Now。Literally， technically， what's actually happened here for those who are like following along with the code。

 like with the real technical stuff is that when I merged into master， I kind of technically just。

Change where master points to， becauseuse remember that branches are just pointers to commit。

So now it's like master is this whole thing and you'll kind of see if I go back into Git here and I go to commits。

And I go to master， you'll actually see that it's a little bit of a simplification。

 but you see that all those other commits are there。😊，Falway says。

 are we able to do merge requests through a command line， You can merge through command line。

 and I'll show you this。 Let's say Kai has Ka's changes here。



![](img/761647906d4d4747df430ce185d1d167_46.png)

And what Kai wants to do is Kai's got。Aam。His changes， Kai's got their changes to the code base。

 which is to add the car， and what Kai wants to do is now to merge it into master。

There is actually a command。With git。Where is it called merge。And merge does。

 What merge does is merge， merges a branch。 you tell it into the branch you are on。

Merging is a pull method。 It's a request to pull。Into that branch。



![](img/761647906d4d4747df430ce185d1d167_48.png)

So what that means is that if I'm over here， you know。

 and let's say let's say Kai wants to merge into master。So Kai goes to Master。

 checks out the master branch。Kai pulls to make sure that Kai has all the latest changes。

Which car now does。And now what Kai wants to do is to merge his branch into master。

 Kai just says gi merge。Kai slash cars list。Like this。

 And what that will do is the exact same thing as the pull request。

 it will pull those changes from Ka's branch into master。



![](img/761647906d4d4747df430ce185d1d167_50.png)

And now the problem is like that locally， Ka's got。



![](img/761647906d4d4747df430ce185d1d167_52.png)

You know， because Kaai's got like a newer version of master。

 Kai needs to push that up to Gitlab because if you have a look， you know。

 look at what Kai's got on on master at the moment。

And have a look at what's actually on Master on Gitlaub。

You'll see that on master and Gitlab it's just forgot to add water and then this merge branch here。

 whereas we don't have Kai's first two cars and then this merge here。

 why these are out of order is a very like。Who cares？ It's a long wind to dance。

 So you don't need to understand that on day one。 But essentially Kai has Kai's got his commits here。

 And then now that he's got his commits in， we push to Gitlab and you'll see those commits will appear now。

 So these are like two are Ka's commitscause the blue blue stuff is my CSC account。

 The purple stuff's my like。Local， why do we use。Merge requests if you can merge it on command line。

 The reason is pretty simple because merge requests are a really collaborative experience。

 they're an opportunity for people to comment or review your code in a visual way to approve your code and those things just really lend themselves well to a gui so we don't do merging on command line really we just kind of don't。

One place that you will do merging on command line， though。And this is， this is important is。

Let's say again that Hayden is going to work on another feature now。 So Hayden's on master， right。Os。

What am I， What branch am I on， You can do Gi status to get your branch。 I'm on the wrong branch。

 I'm gonna check out master。 I'm in pool master and make sure I have the latest changes。

 I say I'm gonna go work on another feature。 and that new feature might be， you know。

 Hayden slash dogs。And then I'll make a new file called Dog。txt， and that file might， you know。

 have like husky greyhound in it。And I'm working on that。 And then again， separately。

 Ka over here says I'm going to go work on a competing area called。Cats。

I don't know what breeds of cats exist， but let's say that Kai has。

A few guys making another file called Cats。 Sky could be editing files。

 It doesn't have to be new files。 and might have loud cat， quiet， cat， sleepy cat。

And Kai's going and working on that and Kai' is making some commits for that too。Right。

Adding three cats。Poorly named。So Ka's over there doing that and Hayden's over here， you know。

 adding dogs。Another commit name。2 awesome dog breeds。What kind of potion am I drinking， it's， it's。

I don't know。 Tell tell you next time。 So we've got these like two things happening over here。

 And if I try and push my new branch， it doesn't work，'ca it's the first time I push my branch。

 And if Kai tries to push his branch， it's the first time he's pushed his branch。 So it doesn't work。

 So Kai has， by the way， we're doing okay for time。 We will run over a tiny bit。

 but not not by a ton。 Maybe like 10 or 1010 minutes，15 max。 So we'll try and get this finish。

 So Kai pushes up here。 now， that's all fine。 master sitting there stable。 I've gone off over here。

 Kai's gone off over there。 But one thing that happens sometimes。😊。

Is that we might work on the same file or something else。 So， for instance。

 now I've gone and started to edit。Nams again， and I've created a new name called， you know。

Blinkky Bill。嗯。And then I've gone and， you know， added that names dot TXT， and then I've gone them。

 you know。Adding a cool name。And then I push that up。 And then similarly。

 Kay's Ka's over here and Kai said， you know， what I actually want to add a name to。 And that name's。

 you know， gonna be like Donald Duck。So we've kind of ended up working on the same files and that happens sometimes sometimes you're working on important files and you both modify the same parts of it。

嗯。Doc added。So now what happens？Is that？Maybe I'll come over here and I'll be like my code's done。

So I can go and I can go to save my branches。 Let me get rid of that comment。

I can go to my branches and I can go， yep， my dogs。 I'm gonna click on that。

 I'm going make a new merge request。 I'm going write some text there。

 I'm gonna click create merge request。 and then someone's gonna tick it。 I don't know。

 Quick Ka I wonder if Ka' ticked it already， probably it in a sec。

 whilst Kas ticking that if he has doesn't matter if he does or not。

 Someone asked a good question before， which was Brandon says should we be selecting the delete source branch thing。

 We don't mind is the short answer。 whether you tick that or not it's kind of up to you。嗯。So。Oops。

Doesn't matter。 So okay， Kai just approved it。 So you actually see it says here approved by Ka。

 if I put my mouse over and it says like there's Kai's name。 So Kai's actually approved it。

 And now I'm going to click merge。 So now that's merged into master。

But one thing is Kai's not finished with his with his cat's branch yet。

 So what he's actually going to do is he's going to out of good habit。

 constantly get the latest master and make sure it's merged。Merged into his code。

 So Kai is going to go check out master on the CSE machine。 Kai's going to pull master。

And then what Kai is going to do is Ka is actually going to go back to his cat's branch。

 and he is going to merge master into his branch。 He isn't trying to merge his finished work into master。

 Hes trying to keep his unfinished work up to date with master。 So this kind of merges stuff in。

 And then you can see here already， Kai， it says there's a conflict in names。

 which makes sense because Hayden on his local machine over here。

Came and modified the names file to include Blinky Bill and Kai modified it in a similar way to add Donald Duck。

 So when I open the names file after trying to merge the stuff in。There's this conflict and I think。

 oh， oh， Hayden had a blinky bill， okay， that's interesting。Oh my god。 that was unnecessary。

 So then k goes and manually just person handles that together kind of thing and like saves it and then。

Kai will go and add both names。 dogsg is already staged and then Kai will， you know。

 make maybe make another commit。calledlled like integrated names。

And then Kai might push that to his branch。 Kai Cats。 And Kai will keep working on that for a while。

 Kai might add another cat， for instance。Stinky cat。You know， so Ka' is doing more work。

 And then Kai thinks all right with the addition final cat added with the addition of stinky cat。

 Kai can go and make a merge request。 actually， wonder if if you are there， Kai。

 if you want to go make one So I won't make this one。 Kai' is just over there， probably making one。

 There is a section on Gitlab over here that says merge requests And if you click on it。

 it actually shows you all the merge request that exists So when your team members make merge requests。

 you can actually like see them here And typically like if you make a merge requestll you'll generally tell your team you've made one so that they know about it so that they can go and look at it。

嗯。And。I don't know if you can actually if Ka I can just do that， but we'll see， maybe I got it wrong。

Yes， so Zach， Zachchar， I don't know how to pronounce your name。

 So Kaai's gonna made this merge request。 and I go， look， I go， hm， alright。Okay， I can see there。

 Kaes， Scott， Donald Duck and cat and quiet cat and sleepy cat。 Okay。

 and then I look at it and I think， oh， that's all good。 And then I can click approve and then。

Then Kai will go and merge it in。 Now， the person who writes the code merges it in。

 That's really important。 The reason is that in theory， the person who understands the code。

 who understands when the code is finished， who understands when the code is safe。

 is the person who wrote it。So as a general， the person who writes the code is the person who merges the code in。

嗯。That's it。 So you can't approve your own code and other people should not merge your own code now。

I don't know if Kai merged it。 doesn't matter。There's a good question here from Zakra。

 Kaai doesn't have access to marriage， that's okay。😊，Zachara says。

 what if you didn't merge master into the branch and just did a merge request with a disputed line？

That's a good question。Let me show you what that means。

 So let's imagine that like totally separately to this for some reason。Let's just imagine that。

 you know， Hayden was really a bad person and went straight into， you know。

 names dot TXT and also added， well let's imagine that Hayden has the latest master。

Hayden went and added another line， which was like。Silly Sam or something。And then Hayden， bad。

 bad Hayden went and pushed that straight to master。Out of a silly name。And push that up to master。

 Now， we're going to have a problem， because if you go look at the code on on master inside the names file。

 there's like scarlet width， silly Sam and By Bill。 And if you go look at Kai's merge request。

 Kay's kind of tried to merge in Donald Duck here between these two lines。

I'm not sure why that isn't updated， though。Oh yeah。

 it tells you here it says here we go merge blocked， merge conflicts must be resolved。

 so sometimes if you have a merge issue that Gitlab can't figure out as in it would normally require manual intervention。

You can either resolve it locally， which is what we did before。

 I could just pull master and merge master into my branch here， or if I'm Kai。

 I could click on this resolvesolve conflict button。And I could choose one of these two。 Now。

 the reason that resolving conflicts here is tricky is because resolving conflicts on Gitlab is typically well。

You can actually edit it on Gitlab if you want， so I could actually edit it on Gitlab and just change the code like this and I could then click like commitmit to source branch so Kai went and fixed this up。



![](img/761647906d4d4747df430ce185d1d167_54.png)

And then Kai is like， alright， this works now。 And then I imagine I'm Kai for a second。

 I could go and merge that in。It's like， okay， it's merged in。 So， anyway， that's， that's。

 that's the， that's it。 That's， this is everything we've talked about tonight。 We've talked about。

Gitt in terms of commits and pushing and pulling， we've talked about how this kind of exists on multiple machines and how those machines have to stay in sync。

 And then we've talked about how when you work with other people。

 you do your work on a branch until it's done and then you merge it back in。

 and you know you can kind of just like you can hide this really beautiful beautiful is a bit dramatic。

 but。You kind of have this image。 You kind of have to imagine that Git is essentially this like。

 you know， this firm line。Moving forward through time that is always full of good。

 stable working code。And then people like you are developing something until it works and then shoving it back in and then your branch disappears and someone else in your team is working on something much more complicated。

And then shoving it back in。 And then someone comes over here and makes a quick fix on another branch and then puts it right back in。

 And you're all kind of like branching off until something's done and then， you know。

 feeding it back into the system。 So even though we say branch like a tree。

 it really is kind of more like a line that just has some things drifting off and coming back in。

And that's， that's the work flow。 That's the workflow。 Now， in terms of when you use this workflow。

 you don't really have to use it。Until the end of this week。

 because all of your labs in this course are solo。 So all of your labs。

Everything we've kind of talked about when it comes to branching and poor requests merge requests sorry aren't really necessary for your labs A lot of this last lecture about branching and merge requests is all about your project。

 which starts on Friday。Kai sent me Kaai sent a link。um。哦。Let me just。I have to log in to Gitlab on。

Kai sent a link about Gitlab has some other visual tools which are really handy。

 and this one is a visualer tool。 I just for complicated reasons。

 I need to log in over here and then。So Kas actually shown that you can see that。

 So red is the master branch here。Right， and you can actually see that like the branch is coming off and then merging back in。

 And you can see， you know， there's the Brandon staff and then。

Ki Cats and Hayden's branch over here so the。You know， it's not the smoothest thing in the world。

 but it kind of demonstrates to you that， you know， while we talk about branching。

 it really is just that line with things。Going off and coming back in。 Now。

 if we just review the lecture slides to wrap this up。



![](img/761647906d4d4747df430ce185d1d167_56.png)

We talked about merging。 let's make sure we've covered everything。 So we talked about branches。

We talked about there you go， there's your like master branch and your branch off it with your new feature and then that eventually gets merged back in。

 we talked about how to swap between branches， a lot of these slides I just didn't go to because we demoed it we talked about merging how you can merge a branch into your branch。

UAnd then we talked about merge requests as well， which is a way of doing like merging through a GuUI。

This is a summary of merging。I think this is， I don't think we'll spend a lot of time on this because I don't think it'll make sense to you if you haven't done a lot of git。

 I think this is something that you can kind of come back and look at in a week or two。But basically。

 the the summary I'll give for this for now is that there's generally two things that you do with merging。

One of them is when you merge your work into master。Which happens when you finish a feature。

 you make a pull request。So that your team can review it before it goes into master because the code in master should always be functioning finishing code。

And then。You have the other way around， which is when you merge master into your branch。

 and that's what you do regularly to make sure that as your team members finish their work。



![](img/761647906d4d4747df430ce185d1d167_58.png)

And as they feed things back into Ma that you're always getting the latest changes。

 So this person over here on the green little squiggle。Whilst they're working on it， when the red。

 they should be trying to pull from master like here and here and here and here。

 just as they're working， right， like every day or something。

 so that as their team members finish work， they can kind of keep getting the latest changes。

 And you might think， why do I need the latest changes， I'm not using Hayden's stupid dog thing。

 The reason is pretty simple。 The longer the time goes between you getting changes on not。

 The more work you might have to do resolving conflicts。

 So it's kind of like instead instead of wasting four hours all of a sudden trying to merge things together。

 it's a lot easier to do that for four minutes every day kind of thing。

 That's a very extreme example， you're not going to spend four minutes every day on it。嗯。



![](img/761647906d4d4747df430ce185d1d167_60.png)

And that's， that pretty much brings us to the end。 So let me answer a few questions。

 and then we'll then we'll shut it all up。 So Leo said。

 so the blue node is added added the so the blue node is added after the latest screen note and merge node added after that。



![](img/761647906d4d4747df430ce185d1d167_62.png)

I don't know what you mean by that。 I was that on the paint diagram， Sorry。

 Leo said on the paint diagram， what happens when Kai's branch just merged into Maine。呃。

When Kai's branch is merged into Maine， I mean， you could honestly。

 like I I don just'ca we're over time， I probably won't spend the time elaborating on it。

 but you can kind of honestly just look at the Gitlab history。 I， I'll make this repo。

 Can I make this repo public somehow。Let me see if I can make this public if people ever want to go look at it。

嗯。2。Yeah， I can make it internal。 So you can just go to this URL。

 Gitlab dot CS S C dot US W dot E D dot A U slash my Z number。/lash lecture1 dash test。

 you can just type that in and you can have a look at the commits and the branches and everything。

 Anyone can look at that now on Gitlab。嗯。The Meriddian said before is it possible to reverse merge requests so you can actually reverse things in Git。

 though it's quite complicated So in this course we mainly focus on just getting you comfortable with Git and the reason we get you comfortable with Git is so that smarter people or you in the future are comfortable using tools like Git which allow you to reverse stuff you don't actually have to do that much。

 but we actually talk about that in like week 9 is a bit of a bonus lecture。

 how to like reverse things but you won't need to use it throughout the course and we also don't like you reversing stuff because we have to assess your contributions in this course so we don't really want you like asing history because history is really important for us to assess what people have done so。

That brings us to the end。 My last comments， which I'll repeat for the third time， are very simple。

 I just threw a mountain of information at you， okay。Now。

 if you somehow watched all of that lecture and you were like， up， this makes perfect sense。I get it。

 cool。You are either a genius or you've worked with Git before， okay？

90% of you are probably in the category of people who are either like。

 I'm really confused or you're in the category who are like， yeah。😊，I。

 I I kind of get it like I get conceptually what you mean， but God。

 I hope you never asked me to do it。Right。To those 90% of people。Great。

 you're exactly where we want you to be。 You will now go and do all of your labs with Git。

 You will now go and spend the next 10 weeks。Learning in your tutorials and your labs and in the project and everything else how to you'll just get comfortable with this slowly over time。

 That's because that's that the lectures on't get done。

From tomorrow we'll talk about JavaScript and we'll start talking about some other things as well so that's kind of like get out of the way we won't have lectures on it again。

 but you will still see it in every lecture because it will just be part of what we do and it's just part of everything in the course so。

If you're feeling like this looks interesting， I kinda get some concepts。

 I'm still a little confused。 I'm scared to do it myself。 You're on track。



![](img/761647906d4d4747df430ce185d1d167_64.png)

Let's keep going。That brings us to the end tonight。I am ashamed。

 I am sad that we couldn't have a little bit more of a light harder week one， but as I said。

 we have a much more relaxed end of terms。 So hopefully that balance as well against your other busy courses。

 Here's some feedback for this lecture。 really appreciate your time。 Thanks for staying late。

 I guess we'll get to see you all tomorrow for those live 6 PM on Tuesday。

 We'll try and have a bit of fun。 programming is probably a little bit more fun than get。

 Probably easier to keep your attention。😊，And thanks for having so much fun on the chat。😊。

You're the funniest students I've had so far。You've got a lot of time to still make mistakes。

 but we'll see how we go had a great time with you all tonight please have a good evening and post on the forum if you need anything。

 we have a bunch of very loving， very intelligent tutors who can help you out with everything。

 so have a great evening。😊。

![](img/761647906d4d4747df430ce185d1d167_66.png)