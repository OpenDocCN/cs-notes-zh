# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p24 -24-MIT web.lab (6.962) - Day 5_ Git for Collaboration.zh_en -BV12Ux5zTE9p_p24-

No。Why does it not work？There we go， okay。So the reason why we're taking a break from our usual web development。

 react， etc cetera， content is because you guys might be starting your project soon。

 The skeleton is released。 There's nothing stopping you guys from continuing to work。

 Although there are a few things related to off skeleton that we haven't covered yet。

 We'll cover that on Monday。 But just in case you guys are starting to code， We want to give you a。😊。

Brief rundown on how to use Git when you're collaborating with your team on your project。

 because this is going to be very important。I'm going to speed through this stuff just a little bit。

 We're not gonna go through many examples， but the slides are here。

 We also wrote really nice speaker notes in the slides so that later on。

 when you're working on your projects， you can go through the slides and just use them as a reference for how to do things as you're collaborating with your team because Git can get kind of messy sometimes。

 So we want to show you all the best practices for when you're doing Git。😊。



![](img/bf926d5fe922dcc28a5218e407ec31b9_1.png)

So what we're going to go over today is we'll re go over some of the stuff we talked about at the very beginning of the class about how to make commits and how to branch。

 and then we'll talk more about merging and merge conflicts。

 which you will probably encounter a lot as you're working and then finally we'll dive more into the details of how a remote Gi works。

😊，So let's recall how we make commits in Git。So as we recall。

 a commit is basically just like a set of code changes that we package up and put a label on that's all probably relating to some kind of category。

 some kind of big fix to our code。😊，And we can think about it as representing this whole history of commits that represents sort of like our version history。

 And then we have this thing called the head pointer that basically represents where in where our current working directory。

 that is like our V S code window is representing。 So if our head pointer is at the topmost commit。

 that means that whatever we're looking at in our V S code is the most recent commit。

 this styling comments block with C， S S， the most recent version。😊，So how do we add a new commit？

Let's say we want to add a commit to add the post comments functionality。

Then we're going to make all of our code changes in our various files。

And then if we're thinking about commitment。We're going to get add and then the file path for the files and the changes we want to add to our staging area。

We do GitAd with our files， those changes get added to the staging area。

And then add whatever other files we want to add。And then once we're ready to commit。

 we'll do Git commit with a certain commit message。😊。

Those get boxed up and added to our commit history。So that's a brief recap of how commits work yeah。

嗯。Gosh， da it。Allright， whatever。 I guess I can't walk around。 That's sad。 al right。I will。

Make sure that on Zoom。You know， I'll just。Go like that。哎。So we just committed， and then。Now。

 recall that we also were talking about Git commits as this object graph representation where each commit is represented by a circle。

 also known as like representing a version of our code。And each commit has an I D。

 which is some big long string of characters， and then a message。😊。



![](img/bf926d5fe922dcc28a5218e407ec31b9_3.png)

Which is what the commit is about。

![](img/bf926d5fe922dcc28a5218e407ec31b9_5.png)

So now we're gonna briefly review branching that we talked about on Monday。

So the basic scenario that we were talking about with why we need branching is。

 let's say Tonys working on implementing a new feature for his app。 And then Andrew says， oh。

 can you help me fix this bug on the original homepage， And he's like， oh， okay。

 then he has to move and start working on that。 And then I come along。 and I'm like， Tony。

 we need this feature tomorrow。 And you have to do it right now。

 And then he has to change what he's working on。 So he needs to work on all of these different things at once。

 And so if we didn't have。😊，Branching， let's say task A， B and C are the things he has to do。

 He's making his code changes， making his commits for task A。 Then Andrew comes along。

 He has to make some more commits for this task and then more and more。

 And then I come along and he has to start working on this。

 And then he's keeps adding commits working on all these different tasks。😊。

And it's kind of a little bit of a mess。 But then。Here's the problem。I come along and I'm like， hey。

 there's this bug on Webla Tinder， on Ca C， where to come from。

And he has to look through his commit history to figure out when in the in the versions this bug got introduced。

 The only problem is。In real life， these， tasks are not color coded。

 All of the commits look exactly the same。 And so he's looking and he's looking， and he's really sad。

So what we need is a way to isolate working on one task versus another versus another。

 But then once you finish a task and have a version of the code that you like。

 being able to merge those things back together。 So that's why we need branching and merging。😊。

So now I'm going to show you an example of emerge。😊。

And there's a couple things that can happen when you merge。

 one is that you merge really smoothly and it works great。😊，So。



![](img/bf926d5fe922dcc28a5218e407ec31b9_7.png)

I'll show you a quick example。Let's say。This is my Git demo folder。And I am going to。

 I have this thing that says Abby is wearing a party hat， and I'm going to create a new branch。

 I'll do gett checkout dash B。 You'll be using this command a lot in your projects。😊。

New hat or something。And so now I'm on the branch， new hat。

 And you can see that because it says it here。So now I'm going to make some changes。And save them。

 Git status to see， yep， I modified this。 I'll do Git add dash A that adds everything。

 All of the changes I've made。😊，And get commit。Dash M。呃。Birthday， whatever I want to call it。

And now I'm done making my changes in my new hat branch。

 and I want to merge these changes into my main branch。 So I'm going to do check out back to Maine。😊。

I notice that now that my head pointer is at main， I no longer see the changes that I have made in my branch。

But now I'm going to do gi merge。And then what did I call this branch new hat。Yeah， that's amazing。

 It just merged the branches that I made in new hat that commit into my main branch。

 Now see I see the change here。😊，And it says emerge successfully。 great。 This is a smooth merge。😊。

But what happens when the merge isn't quite so smooth。I'm going to do get check out a new branch。

Let's call it bucket hat。And then on my new brand， I'm gonna make some changes that actually conflict with the changes that I have in Ma。

 I'm gonna say Abby's wearing a bucket hat instead。Like this。

So now I'm going to check out back to Maine。And try and。 oh， wait， wait， sorry， I need to。

Check out Back to Bu Ha。And make sure I have committed something。Okay， so get status。

Get add my change。Get commit。Okay， so now I've committed this change on bucket hat。

 and we can see it。And then I'm going to go back to Maine and try and merge the changes from bucket hat into Maine。

 You'll notice that Maine still says Abby is wearing a party hat。

So I'm going to get merge bucket hat。Go to merge the changes from buckethead into main。And， oh。

 why did that work， I was not supposed to work。I think I accidentally edited the thing on Maine。Okay。

 well， either way， for the sake of time， I'm not going to do another example for the merge conflict。

 but basically what happens is if I have a something conflicting when I merge it in。

 then I'm going to get this error message that says， oh， no， merge conflict。

 fix the changes and then commit the result。 And so I need to go into my editor manually choose what I want to change and what I like what I want to keep。

 whether it's the version from main branch or the version from my new branch。

 and then close out the editor and then。😊，Merge those things together manually。

 So that's what happens when there is a merge conflict。



![](img/bf926d5fe922dcc28a5218e407ec31b9_9.png)

![](img/bf926d5fe922dcc28a5218e407ec31b9_10.png)

O。Now I'm going to go into talking a little bit more about how we use remote。

 because this is going to be very important for your projects。



![](img/bf926d5fe922dcc28a5218e407ec31b9_12.png)

Earlier， we talked about how we have a local copy of the code that I'm working on。

 and we have a copy of the code that's on the remote server， in this case， Gitthub。

 This is where our code is hosted。😊，And if Tony wants to work with me on this code。

 he's going to have to use Git clone So get clones。

 And now he has a local copy of the code of the whole repo on his computer。Now。

 Tony's going to make his changes， gett ad， get commit， etctera， so that he's editing the code。

 Then he uses Git push to push the commit that he made here onto remote。😊。

And then if I want to see what kinds of changes he made， I'm gonna do Git pull。

 and I will take any new commits that are on remote that I don't have and bring them over to my side of things。

So the basic workflow， if you're just doing a very simple remote workflow。

 working on one singular branch， is any time you start working pull， always， always。

 always always a pull。😊，And then you're gonna work on stuff。 you're gonna to add。

 you're gonna make your commits。 and then you need to pull again to make sure that nothing changed on the remote server in the meantime while you're working。

 And then once you've successfully merge any changes in。

 then you can push everything back to the remote server。

 and now everything will be up to date and clean。So that's one way。

 the most simple way to work with remote。

![](img/bf926d5fe922dcc28a5218e407ec31b9_14.png)

But the more sophisticated way to work remote。 And this is how I would recommend doing for your projects and how you'll definitely be doing in any industry setting is using branches。

😊。

![](img/bf926d5fe922dcc28a5218e407ec31b9_16.png)

So let's say that Tony is working here and his copy of the code of mainine is up to date with remote。

And he's going to make a local branch。 He's going to call it Weblab Tider， and he's making a branch。

 but it only exists on his local side。 It doesn't exist on remote yet。And so he makes a commit。

And then he's going to do get push。 He'll try that。Oh， shoot。 He got cockbed。 What happened。

 It says the current branch has no upstream branch to push the current branch instead set the remotes upstream。

 You get push set upstream origin new branch。 Okay， what theck does that mean。😊。

What this means is this concept of upstream basically means that。Every branch， when you get clone。

 basically has this little link that Git keeps track of that says， oh。

 this branch that I'm working on on local corresponds to this branch on remote。

 And there's this link between the two so that when you do get push， get knows， oh。

 I'm gonna move this to this particular part of remote。😊。

But since Tony just created this new branch web lab tinder。

 it doesn't have one of these little like links to it。To something on remote。

 So what he's going to do is he'll do Gip set upstream origin， which just means remote。

 And then whatever he wants to call his new branch on remote。 So let's say he wants to call it Tider。

 It can be the same name。 It can be different doesn't matter。

 But now that he called Git push with this set upstream flag Now Gi knows， okay。

 I'm going to set up a link between this Weblo Tider branch that I have locally。

 And the Tinder branch that I'm now creating on the remote server。😊，So now he's making his commits。

 He's doing his stuff， more stuff。And then now he can do Git push。 And since this connection exists。

 Gi will know， Okay， I'm going take these commits and move them to the Tinder branch on remote。😊。

And now， once Tony's like， okay， Web Labtender is ready， we're all set to go。

 He wants to merge it back into Maine。😊。

![](img/bf926d5fe922dcc28a5218e407ec31b9_18.png)

![](img/bf926d5fe922dcc28a5218e407ec31b9_19.png)

So how do we do that？Well， he's going to check out to Maine to make sure that he is currently looking at the main branch because remember。

 if you want to merge a branch into Maine， you need to be on Maine and then merge the other branch in。

And so he's going to type in the command， get merge Weblab Tider。

 He fixes an merge conflicts that arise， does whatever he needs to do。

 And now there's this new merge commit that he has locally that merges whatever hes merges all of the commits he made with Weblab Tider into the old version of Ma。

😊，Putting them together， great。And now he wants to push this to remote。

 because remote has to get merged to Github， etca。He's like。

 I'm so excited to publish Web live Tinder。 It's almost done。

 Now I can be done with this weird project。😊，And so he does get push。 And， oh， no。

 he got cock walked again。 What happened。Here， it says updates were rejected because the remote contains work that you do not have locally。

 This is usually caused by another repository pushing to the same ref。

 You may want to first integrate the remote changes。 E D Git pull。Before pushing again。Okay。

What does this mean。Well， it says the remote contains work that he doesn't have locally。

 That probably means that there were commits on remote。

 on Github that he doesn't have in his local copy。So he's like， what just happened。

 why did I get cop book？So， he does get fit。And that basically looks at remote。

 checks what's going on， updates what he has locally to match it。 And he realizes， oh。

 there's a new command sorry， a new commit on remote that Abby had made and pushed onto remote main while he was working on his webtender that he didn't realize was there。

😊，So now he asked to take care of taking this commit that he that that was in remote here and somehow merging that into his own diagram。

So what he's going to do is he's going to be on his local main。 So his computer。

 and he's going to do Git pull。 That's going to take the commit that he doesn't have yet locally and merge it into the main branch of his local repo。

And then he might need to fix some merge conflicts， do some stuff， whatever。

And then once that successfully emerged， now that the bottom of。

His object graph looks the same as the bottom of the remote object graph。 Now。

 he's finally ready to make the merge of Weblab Tider public on the Github remote server。😊。

So he does get push， and it finally works。He's happy。Okay。

 and then also good practice is once youve successfully merged all your changes in。

 just delete that local branch so。😊，Once。Once you merge this in。

 Github will automatically delete this branch on remote for you。 But locally。

 you might still have this Web lab tinder branch。 And it's a good practice to just delete it once you're done merging that feature that you are working on on that branch into the main branch。

😊，Okay， this slide I won't go into in super detail。 You don't need to read it all right now。

 but this is gonna be good reference for you when you're going through your project that basically if you want to add a new feature。

 one of the best workflows is to create a local branch， create a new local branch， do some work。

 whatever you need to and then create a remote branch that corresponds to a local branch。

 setting up that link， then， you know， continue doing making whatever changes you need to。😊。

Then when you're ready to merge your branch， you're going to need to get pull。 Make sure you always。

 always， always pull。Make that merge commit。 and then we push the merge commit from local to remote。



![](img/bf926d5fe922dcc28a5218e407ec31b9_21.png)

![](img/bf926d5fe922dcc28a5218e407ec31b9_22.png)

Okay， just decided denim is that what we just did is we。Had this merge commit。 So Tony had his brand。

 He made a merge commit here， and then he pushed that merge commit to remote main。

This will work fine for our projects。 But in any industry setting。

 when you're actually doing software engineering， you would not be doing this because typically。嗯。

Sorry， typically， when we're in an industry setting， we， as a regular entry level。

 software engineer or inter or whatever， don't have access to push anything。

 even a merge commit to remote main， because everyone's working on remote main。

 all of the developers， if we mess something up on there， it's kind of screwed。

 So what we would typically do in an industry setting is instead of merging and then pushing the merge commit。

 we make sure that the remote branch has whatever commits that we want to have。And then。

We do git pull origin main to make sure that any new changes from。

From main on remote are pulled into our branch。 This is to avoid any unnecessary merge conflicts and things。

And then make sure that our branch matches whatever changes were made to remote main。

 And then we do something called a pull request。So this is going online on like Github or whatever software that your company uses。

 And then it's basically a request to your manager or whoever's in charge。

 whoever has admin permissions on the repo。To merge this branch of changes that I made in this case。

 Web live tinnder into remote main。So it's just an online interface where the manager or other software developers can review your code。

 Check it off。 Okay， that looks good。😊，And then GitHub will automatically merge it for you。

 So that's how you would do things in an industry setting。

And then we would go back to our local Gi pull。 and then we have everything that is on remote。

And then， of course， we want to delete our branches。



![](img/bf926d5fe922dcc28a5218e407ec31b9_24.png)

Okay， this is a reference for the workflow that we would do if we were in an industry setting。

 And now we're just going to briefly do a little adddenum on a tool that you will use。Probably many。

 many， many times throughout your projects。 And that is Gi stash。



![](img/bf926d5fe922dcc28a5218e407ec31b9_26.png)

It's also useful for the workshops。 So let's say that Tony is working on his code。

 and this is in like dotted lines because he hasn't committed this yet。

 He's just making some code some changes in his VS code。

 He hasn't staged changed staged or committed anything。 He's just got his changes in his VS code。😊。

But let's say he wants to get check out Maine。 Let's say he wants to go back and see， oh， what was。

 how do we do that in the main branch again， What did I change there， something like that。

 He wants to just check it。And then， oh， he got co fucked again。 What happened。

So it says your local changes to the following files will be overwritten by checkout。

 And then whatever this file is， please commit your changes or stash them。 Oh。

 what does that mean before you switch branches。So basically。

 what Git realizes is that if he checked out to to Maine。

 then that moves the head pointer to mainine。 What does that mean Well the head pointer basically just says where in my gi object graph is my current V S code。

 like state of the files representing。So if he checked out to Maine。

 that would change all of the files in his V S code to match whatever whatever this last commit on Ma is。

 which means that all of the changes that he made and didn't commit would just be wiped out forever。

 Get knows that you probably don't want to wipe out changes if you were working on stuff。

 And so that's why it gave him that error message。So what he can do instead is get stash。

 And that takes all of these changes that he used to have。

 that he didn't commit or anything that he had just in his editor。

And it's almost like it sticks it off in a box to the side。And it's just like， okay。

 I'm going to hold on to it。 And now head represents whatever the last committed version was。

And now he can get check out Maine， he can check out whatever other branches he wants。

 he can change up whatevers going on in his VS code， look at this， look at that。

 anything he wants to do， he can even pull from remote if he realizes there was stuff in remote that he needed that he didn't have。

And then once he's ready to bring those changes back and keep working on it。

 he does get stashed pop and that will take the changes that he was making before out of the little box and reimplement them straight into his V S code editor so he can just pick up right where he was working before。

😊，So Gi stash， that doing whatever you want， and then Gi staash P allows you to hold on to changes that you're working on。

 but haven't committed or anything yet。What about the orange circle。

Between the second yellow circle and the orange circle。 So it's basically like。

Tell me if this answers your question，Basically， what happens is if he pulls， so he。

How does head here。Then he stashed all of his current working he changes。

 And now he's pulling from origin Ma。 So basically， this just takes whatever changes。

 whatever updates were made and applies them to the version of the code that he has currently。

 that might cause merge conflicts。Depending on if this is different than this。

But he can just resolve those merge conflicts， figure it out， and then get stashed pop。

 We'll just take those changes that he had made before and apply them to this version of the code。

 yeah。Got it。Okay， workflow is good yes question。We wouldn't call it merge conflicts per se。

 because it's not merging， but like。It's a good question。

 So if you pop off of the stash and that make some changes that are like different from what was in the orange circle。

 then it would overwrite the changes that were in the orange circle because that's as if we had the orange circle。

 and then we just like went in and edited things。😊，Cool， so basic workflow， get stash。

 do whatever you want， get stash pop。Okay， I am for the sake of time not going to。Go over the recap。

But a couple recommendations。 there's this website called Learngit branching。

 which is like a kind of gamified Git practice website that is pretty nice。 And we also have。

 there's a git sheet sheet that you can look at if you want to reference commands。 Also。

 just in general， I literally just stack overflow。 I have to look up the commands for anything anytime I do it。

 But you just like， have to do this on Git。 And then it'll just tell you。😊。



![](img/bf926d5fe922dcc28a5218e407ec31b9_28.png)

Okay， last bit of feedback for today， If you could take one minute to fill this out。

 and then we'll move into final announcements。😊。

![](img/bf926d5fe922dcc28a5218e407ec31b9_30.png)