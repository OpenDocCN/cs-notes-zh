# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P6：-06-.Lecture 6_ Version Control (git) (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

All right let's get started with today's lecture so actually before we get started one quick note about office hours。

 it seemed from the poll that some people were under the impression that the office hours that follows each lecture is just about that day's lectures topics and this is not the case you can come to office hours and ask us questions about any lecture whether it's the previous day or from the previous week or even things not exactly covered in this class that you're just curious about so yeah。

 come to office hours with questions about anything。Office hours are in the 32 G9 lounge。

 so  building 32 also known as the status center has two towers， the G tower and the D tower。

 so we're in the Gates tower on the9th floor so if you take the elevator all the way up。

 there's the lounge right in front of you。Okay， cool。

 so today we're going to be talking about version control systems。

 so I just want to get a sense of whether you guys have used version control systems before。

 so could you raise your hand if you have any experience with Git or any other version control system like subversion or Mer or anything else。

Oh great， so that's a good number of you。So I won't talk about version control systems in general way too much then we'll pretty quickly get into the details of Git and like its data model and its internals。

 but just as a quick summary， version control systems are tools that are used to keep track of changes to source code or other collections of files or folders and as the name implies these tools help track the history of changes to some set of documents and in addition to doing that。

 they facilitate collaboration， so they're really useful for working with a group of people on a software project。

Vierin control systems track changes to a folder and its contents in a series of snapshots。

 so you capture the entire state of a folder and everything inside， like a software project。

 and you have multiple of these in a series of snapshots。

 each snapshot encapsulates the entire set of files and folders contained within some top level directory。

And then version control systems also maintain a bunch of metadata along with the actual changes to the content。

 and this is to make it possible to figure things out like who authored a particular change to a particular file or when was a particular change made。

 and so version control systems maintain metadata like authors and commit timestamps and you can also attach extra messages to these snapshots and things like that。

And so why is version control useful Well it's useful even when you're working on projects by yourself so you can use it to look at old versions of code you've written。

 figure out why something was changed by looking at commit messages。

 work on different things in parallel without conflicts by using different branches of development or be able to work on bug fixes while keeping work on different features independent。

 things like that， and so it's an invaluable tool， even if you're working just by yourself。

 even on a small scale project， like I think the instructions of this course， use Git。

 even on things like homework assignments or class projects， even small scale things。

 in addition to our research or larger software projects。And then of course。

 version control is a really powerful tool for working with other people。

 so it's useful for sending patches of code around。

 resolving conflicts when different people are working on the same piece of code at the same time。

 things like that。It's a really powerful tool for working by yourself or with others。

 And it also has neat functionality to let you answer questions that would otherwise be kind of hard to answer。

 like who wrote a particular module in a software project or who edited a particular line in a particular software project。

 Why was this particular line changed。 When was it changed by whom things like that。

 and version control systems also have some really powerful functionality that we might cover at the end of today's lecture or you can find the lecture notes if we don't have time to do things like suppose you have some project you'd been working on for a couple years。

 and then you notice that some funny thing about the project is broken。

 Like you have some unit test that doesn't pass anymore。

 and it wasn't broken just now it was broken some time ago and you don't know exactly when this regression was introduced。

 Vi control systems have a way of automatically identifying this like you can take it and give it a unit test that's currently failing but you know passing it some point in the past。

 and it can binary your search your history and figure out exactly what changed to your code made it break。

 So lots of really。😊，Powerful fancy features if you know how to use these tools properly。嗯。

There are a number of version control systems out there。

 and Git has become kind of the de facto standard for version control。

 so that's what we're going to be covering in today's lecture。One comic I want to show you。

 which was on the screen beforehand， let me bring it back up。

So this is an XKCD comic that illustrates Git's reputation。 let me read it out loud for you。

 This is Git。 It tries collaborative work on projects through a beautiful distributed graph theory tree model。

 Co， how do we use it No idea Just memorize these shell commands and type them to sync up If you get errors。

 save your work elsewhere， delete the project and download a fresh copy。😊，So。



![](img/4a8b0912b0402741368096f70687a362_1.png)

Maybe some people may not want to raise their hands for this。

 but raise your hand if you've ever done this before。 I certainly have when I was learning this tool。

 So good number of you here have done this before。😊。

So the goal of this lecture is to make it so you don't have to do this anymore。😊，Unfortunately。

 as this comic illustrates， Git interface is a pretty terribly designed interface。

 it's a leaky abstraction， and so for this reason， we believe that learning git top down。

 starting with the interface is maybe not the best way to go， and it can lead to some confusion。😊。

It's possible like this comic show is to memorize a handful of commands and think of them as magic incantations and when everything's working all right。

 it kind of works out all right。 But then you have to follow the approach of this comic whenever things go wrong。

So while Git has an ugly interface， its underlying design and ideas are actually pretty beautiful。

An ugly interface has to be memorized， but the beautiful ideas underlying Git can actually be understood。

 and once you understand Git's internals， its data model， which is actually not that complicated。

Then you can learn the interface to get。 you'll have to memorize some things。

 but you can understand what exactly certain commands do by understanding how they manipulate the underlying data model。

And so the way we're going to teach Git today is first talk about the data model， almost in abstract。

 talk about how we might model files and folders， snapshots of history and how they relate to each other。

 and then after that we'll walk you through some Git commands and then finally in the resources and exercises we'll link you to tutorials that will teach you all the specifics because there are lots of different commands that you will need to learn eventually。

Any questions so far about our teaching approach for today？Cool， great。 so let's get started。

There are probably many ad hoc approaches you could take to version control and I'm guessing some of you may have done this before like say you have some file or folder where you have a bunch of different files corresponding to some software project and you want to track changes。

 you could just say every day make a copy of that entire folder and give that folder timestamp when you want to do things like collaborate with other people you could take the entire folder turn it into a zip archive and email it to somebody and then whenever you and your buddy are working on two different features of a software project you can work on them in parallel。

 then one of emails the zip file to the other person and then you manually copy and paste the appropriate segments from their code into your code so that eventually you end up with one piece of code that has both of your features in it。

 This kind of sort of works raise your hand if you've done this before， I certainly have。

Still a decent number of you。Gt lets us not do this sort of thing。

 It has a well thought out model that kind of facilitates these sorts of interactions。

 things that you might want to do like tracking your own history on your own project or collaboration or things like that。

So Git has a wealth out model that enables things like branches and collaboration and merging changes from other people。

 all sorts of neat stuff。Gt Model history is a collection of files and folders within some top level directory。

 so you're probably familiar with this abstraction just from files and folders on your own computer。

 And so here's one example like you might have some top level directory。

 I'll just call this like root and parentheses。And this directory might have， say。

 a folder in it calledF， and this folder inside of it might have a file called bar dot text。

And this might have some content in it， like say this saysHo world。

And then maybe this top level directory， it has one folder in it。

 it could also have another file in it， so say there's some other file。

And this file also has some content in it。All right， simple enough。

 The terminology get uses for these different things for files and folders is。

This and the top level thing are called trees。So this is a folder。And then these things。

 what we normally call files， are called blobs。All right， okay。

 so now we have a model of files and folders。And this is a recursive data structure。

 trees can contain other trees， and then trees can contain both trees and files。

 Obviously files can't contain trees。All right， so now we have a model of files and folders。

And the kind of top level of this thing， the thing I've just labeled root。

Is the directory being tracked like you might have some folder on your computer corresponding to a software project？

Now， how do you model history once you have a model of files and folders， Well。

 you can imagine one way of doing it， which is you take a snapshot of this entire thing。

 And then history is just a linear sequence of snapshots。 like you might imagine that it's。

You can almost think of it like you have copies of the folder which are dated and timestamped。Well。

 Git doesn't use a simple linear model like that。 It uses something a little bit fancier。

 You might have heard this terminology before， but Git uses a directed acyclic graph to model history。

 and this might sound like a bunch of fancy math words， but it's actually not all that complicated。

So in Git each snapshot has some number of parents and basically want to know like what change preceded。

 what other change， so suppose here I'm going to use circles to refer to individual snapshots。

 this is the entire contents within this tree so all the files and folders in my project。

My entire project may be in some state。And then I edit some files， and now it's in some other state。

And then I added some more files and I in some other state。

 and every state points back to which state preceded it。This so far is a linear history。

 but Git lets us do something a little bit fancier than this。 you can also。From a certain snapshot。

 fork your history and say， I want to base changes off of this version。And。

Create a new snapshot like this。So this way of modeling history allows you to do things like。

 okay I'm working on my project。 This is my main line of development。 I go up to here。

 and now I have two different tasks I want to work on。 suppose on one hand。

 I have some fancy new feature I want to add to my project。

 And so I'm gonna to be working on that for a couple days。 but separately from that。

 somebody's reported a bug to me and I need to go chase down that bug and fix it。

 Well instead of working on all that stuff kind of concurrently at the same time in the same line of development get has this way of branching the history into two separate forks and working on different things in parallel temporarily in a way that are unrelated to each other。

 So I could take this base snapshot， like my project is in some state where it works。

 And then from here I could implement a new feature that creates a new snapshot。

 So this has the base project plus a new feature So I'll do like plus feature。And then similarly。

 separately from this， I could go back to this original snapshot because I don't want to do bug fixing while implementing my new feature。

 go here and then work on my bug fix and create a different snapshot。 So this has only the bug fix。

But not the feature。 And then finally， once I've done these two separate things in parallel。

 eventually I want to incorporate them all into my common source code that has both the feature and the bug fix。

 So eventually I might author a new snapshot by merging the changes present in these two different snapshots。

 And so this one will have both of these snapshots as parents。😊，And this version here will have。

Both the feature and my bug fix。So does it make sense why Git models history in a way that's a little bit fancier than just a sequence of snapshots of my files and folders。

 why I want to be able to support branching to work on things in parallel and then also merging to combine changes from different parallel branches of development question？

When merge things， it seems like you could create errors。That weren't anticipated。

So that's an excellent point。 It seems that when you merge things。

 you could create errors that weren't anticipated。 You could imagine here that this feature actually changes something that makes this bug fix redundant or you could imagine this bug fixed。

 breaking this feature or something like that。 That's a really good point。

 That's something known as merge conflicts。 And this is something that Gi will try to do like when you merge to parallel branches of development。

 it will try to automatically combine the changes in a way such that it retains all the important changes。

 But if it gets confused。 it will report a merge conflict and then leave it up to you。

 the programmer to figure out how to combine kind concurrent changes to the same files or things like that。

 and the Gi has some tools for facilitating this。😊，Any other questions？Great， okay。

 so now we have a model of files and folders， and then we have a model of history how different snapshots of our code relate to each other。

 One little detail here is that。😊，Each of these circles。

 so they kind of correspond to a snapshot like a tree with files and folders。

But they also have a little bit of metadata。 So like inside here， we might have。

Like the author of this commit is niche。And we may have other metadata。

Like some message associated with this commit。And I might describe what kinds of changes I've made that are present in this snapshot。

 but not the previous one。嗯。That was not related to class。

So next we're going to talk about kind of one level lower than this。

 like how exactly is this represented as a data structure inside Git。

 and so I'm actually going to write down pseudocode because I think it's actually easiest to understand this way。

So first we have files， so a blog。Is just a bunch of bitetes。

 So I'll say this is an array of bitetes。Okay， then what is a tree？

Remember that this is just a folder of what are folders， their mappings？From。

The file name or directory name to the actual contents and the contents are either another tree。

 like a subtree or。The file。And then， finally， we have。The last thing there。

 what I've been calling snapnapshots so far， in Git terminology， those are called commits。

And so what is a commit？It's a bunch of stuff， commits how parents。That describes what precede them。

 So in the case of most normal commits， they have one parent， like what they came from。

 but merge commits can have multiple parents。Parents are an array of commits。

And then I have some metadata like the author。And maybe a message。And then， finally。

The actual contents， the snapshot， which is a tree that's the top level tree。

Corresponding to a particular commit。So this is a really clean， simple model of history。

 and this is basically all there is to how Gi models history。Any questions about that？All right。

 so now we have that going a little bit deeper。 Let's talk about how Git actually stores and addresses this actual data。

 like at some point， this actually has to turn to data on disk right， so Git defines。An object。

Kind of a big sounding term。 but an object is any one of those three things。 So it's a blob。

Or a tree。Yeah。Te or a commitit。And then in Git， all objects are content addressed。

 So what Git maintains on disk and you can actually we can look at this later。

Is a set of objects maintained as。This content address store。

 So if you have any one of these objects， the way you。

Put it into the store is its key is the hash of the object。 So like in pseudocode， I might say that。

To store a particular object O， what I do is I compute its I D by taking the Shawa hash of O。

 and then I。Put it into my objects map， store it to disk。quick show of hands。

 Who here knows what a hash function is。All right， so I'll quickly summarize basically a hash function is you can think of it as like this magical function that takes a big piece of data and turns it into a short string。

😊，At a high level， these are used to。Or maybe that's like a sufficient explanation。

 I won't go into too much more detail here， but you can ask me afterwards if if you're curious。

 So basically， they give you a way to name a thing in a way that's kind of deterministic based on the contents of the thing。

 It takes in a thing as input and gives you a short name for it。

And then the opposite of store load the way we can load things from this store。

You might have just guessed you can look them up by their I D。 And this is just。呃。

We retrieve it from the object store by ID， and it gives us back the contents。

Any questions about this so far？QuestionWhat languages that's all written？That's a good question。

 What language is this all written in， It's written in the language I just made up。

 So it's pseudocode。 The git implementation itself is a mix of C。

 It's mostly C and then some bastion pearl scripts， I think。😊，Any other questions？

Is this made up language clear enough or do I need to explain any aspects of it？Great。Okay， so blobs。

 trees and commits in Git are unified in this way。 They're all objects and。Also。As you might think。

 given my description here， like， it looks like commits contain a whole bunch of other commits and contain a snapshot and things like that in practice。

It doesn't actually work that way。 Instead all these are pointers。

A commit will be able to reference a bunch of parents by their IDs。

 So this is actually not an array of commits themselves， but IDs。 and similarly。

 the snapshot inside a commit is not the actual tree object。 It's the ID of the tree。

 And so all these objects are kind of stored on their own in this object store。

 and then all the references to different objects are just by their ID by their Shawa hash。😊。

Does that make sense， You can almost in your head map it to like。

 these are objects in a programming language like Java。 And then this is a reference to a tree。

 So it's like a pointer。 And then that is your Ramm。 Maybe this analog helps maybe it doesn't。

There's a memory model for storing all this stuff that they're not telling us about。

It' an object store that inible by。You cash。Yeah， exactly。

 so I'll just repeat that for everybody to hear and on the microphone， this gets on disk data store。

 It's a content address store where objects are addressed by their hash。All right。

 any questions about that so far？Okay， so now we have a way of identifying。呃。

We've we've unified all the different types of objects into one type of thing we call object。

 And we have a way of identifying objects by their Sha one hash。

 What do these actual Sha1 hashes look like？ Well， they're hexadecimal strings that are 40 characters long。

 like Sha 1 is a 1，60 B hash。 and so。One of the actual I Ds returned by that Shaoan function is going be a really long string。

And so given that， we'll have ways of identifying these different things like this will have corresponding to it。

 an I D like 4， A F 3，2， C， E， B， something， something。

So now we have a way of naming everything in this commit graph。

 But these names are really inconvenient because they're super long and they're like text strings。

 They're not meaningful to humans in any way。 So Git's solution to this problem is one other thing。

 So Git maintains a set of objects。 And then it maintains a set of references。

 What are references here El race this bit on the left since this parts。Pretty logical。

Let's see in time。So references。All right here。So this is another piece of data that Gi maintains internally。

 references is a map。From。String to string。And you can think of this as mapping human readable names。

 like I might have a name like。Fix encoding bug。 F dash encoding， dash bug。Is a human readable name。

 and this would be maps to that long hexadecimal string there。And so with these references。

 and you can imagine how we might have ways of。Creating new references and updating references and things like that with this。

 I can now refer to things in my commit graph by name， so I might have the same be called like。

Fix bug。Or I might have a name for something over here， things like that。And so yeah。

 with this Git can use human readable names to refer to particular snapshots in the history instead of these long hexadeadecimal strings。

One other thing to be aware of here is。Given Gis designed for history。

 this entire graph is actually immutable。 You can add new stuff to it。

 but you can't actually manipulate anything in here。

 I won't go into the details of exactly power or why， but just assume that that's the case。 However。

 references are mutable。 So as you're updating the history。

 like suppose you keep working on this piece of software， you create a new commit。

 So I'm representing that by the circle。 This points to the previous commit。 I can actually have。

 say my fixed bug reference was pointing here。 I can update this reference to now point over here。😊。

However， I can't， for example， make this point over here， that's not even a meaningful thing to say。

 because this is just the hash of this object to change this hash。

 I'd need to change the contents of the object， which doesn't really make sense。All right。

 any questions about that so far， that's basically it for Git's data model。

 and then we'll go into actually interacting with Git via the command line and we'll see how Git commands correspond with manipulations of a graph data structure。

So any questions about modeling history as？Trees of trees and blobs。

 and then snapshots these things called commits being chained together。

 And you have references that can point to particular nodes in this graph。Cool， no questions。嗯。So。

Basically， once we have objects and references。Like that's basically all there is to a Git repository。

 those are just the two pieces of data that it stores。And。At a high level。

All git command line commands are just manipulations of either the references data or the objectss data。

Okay， so for the rest of this lecture， I'm going to go through some Git commands。

ItBas going to be an interactive demo similar to the VIm lecture。

 and then you can refer to the notes for full information on these commands because of course this is a really powerful tool。

 we can't cover everything in what 20 minutes。All right。

 so I'm going to go over to this folder called Playground。

 and I'm going to make a new directory called demo， CDD into demo。

 and this directory is going to represent the top level of my project。

 it's currently empty because I just created it。If I want to turn this into a git repository。

 I use the git init command， Git in it stands for Git initialize。

 and we see that it says initialized empty git repository in blah， bh， blah slash dot git。If I do LS。

 I still see nothing， but if I do LS dash A。There's a hidden file in this directory called dot Git。

 if I do LS dotgit， there's a bunch of stuff in here。

 this is the directory on disk where it Git stores all of its internal data。

 namely the objects and the references。 And you actually see here objects and refs is two directories in here and all the repository data will be stored underneath those two directories。

One other command to keep in mind as we're going through these is something called Git help。

 Git helpp takes a sub commandd as an argument and gives you some help on it。

 So if I do Git help in it， for example， it'll tell me about the Git in it command。So now。

There are some commands for figuring out what's going on with a Git repository。

 like Git status at a high level says what is going on right now。And we see here。

 let's ignore the first line for now。 the second line says no commits yet。

 That's because we just initialized a fresh repository。 And so there is no history yet。

I'm actually going to。Does anybody still want this or kind of clear this part of the board？

I'm going to， as we go along， draw how the underlying objects and references data is changing when I type in certain Gi commands。

So right now， this picture or lack of picture represents the current state of our repository。

 It's empty。 There are no snapshots。So let's fix that。 let's add something to our history。

 Here we have no files。Let me just go ahead and create a file Ho dot text with the content Ho world。

Normally you'd have your source code with actually useful stuff in it。Now。

 what I want to do is I want to take the current contents of this directory and turn it into a new snapshot to represent。

 say， the first state my project was in。You might imagine an interface for doing this where there's like a Git snapshot command or Git something else command。

 which takes a snapshot of the entire state of the current directory。For a number of reasons。

 Git doesn't have a command that works exactly like that because Git wants to give you a little bit of flexibility as to what changes to include in the next snapshot you take。

 This is something that's kind of confusing to beginners sometimes。

 So I'll try to explain it right now。 Git has a concept of something called a staging area。

 and at a high level， its。A way you tell Gi， what changes should be included in the next snapshot you take？

If we do git status here we'll see that Git says no commits yet like it said before。

 and it says untracked files， hello dot text， so this is saying that Git notices that there's a new file in the current directory。

 but it is not going to be included in the next snapshot， Gits kind of ignoring it for now。

 but if I do Git add hello dot text。And if I do get status again。It says now changes to be committed。

 new file hello dot text。 and so now if I do the Git snapshot command， which is actually Git commit。

 which creates a one of those circles I drone the board over there。

This file will be included in that snapshot I take。 So let me go ahead and run Git commitit。

What this does is it pops up my text editor and it lets me type in a message that will be associated with this commit。

 and it's really good to write high quality commit messages because then later when you're looking back at your product's version of history。

 you'll know why you made certain changes。I'm going to add this relatively useless commit message。

 but we have a link in the lecture notes for a guide on how to write high quality commit messages。

So now that I've done that， get prints out some output。 master ignore that bit for now。

 this thing is the hash of the commit I just created。 So now I have in my history， a single node。

This has in it a tree that has a single blob， a single file hello dot text with the content's Ho world。

 and then this has the Shawaan hash。4，2， FB。Something， something， something。

 It's actually truncated in the git interface as well。

This is just printing out my commit message again， and it says， as a reminder。

 I had just added Ho dot text。And so now if I use the Git log command。

 so the Git log command is really useful in that it helps you visualize the history。

 the commit graph， if I do question。42 F number。Is that for the entire tree or just for the？

Function hell。That's a great question。 So the question is， what exactly does this hash correspond to。

 So this is the hash of the commit， The commit contains inside of it。

 the hash of the tree along with whatever other information So I can actually use git cat file dash P this number。

 This is kind of like a gi internals command that will print out the contents of this commit。

 So you can see this kind of maps to that data structure I on the board over there。

 So this commit has inside of it， this tree。 and then I'm the author and this is the commit message and so on。

 And I can continue digging down here。 So I can take this hash of this tree， and you get cat filep。

 this hash here it says that this tree has inside of it。

 a single entry hello dot text and that file has it's a blob and it has this hash。😊。

I can do Git cat file dashP this thing， and it will show me the actual contents of that file。

So these are internal git commands to explore objects in the object store question。

Why do you have to add files？That's a great question。 So the question is。

 why did I have to use Git add。 Why can't you just commit all changes。 And the answer is， well。

 there kind of is a way to commit all changes。 if you do git commit dash a。

 this commits all the changes that were made to files that are already being tracked by Gis。

 So anything that was included in the previous snapshot but has been modified since then It doesn't include new things。

 There's also variants of Git add like if you do Git add colon slash this will add everything in the from the top level down of your repository。

 But at a higher level， the reason we have the separation between Git add and Git commit and why Git commit doesn't just snapshot the entire directory。

 is that there are often situations where you don't want to include everything in the current snapshot。

 Like here's a couple examples。 One is that I might be hacking on my project。

 and I go ahead and implement two features。 Maybe I don't want to have a single snapshot that comes after this one。

 that's like I implement feature A and feature B。 Maybe I want to create two separate nodes in the history so that it looks like first I implemented feature A。

😊，And then after that， I implemented feature B， so I have one snapshot that only includes A。

 and then the next one includes both A and B。Gt add is a tool。

 and like the staging area in general is a tool that will allow me to do that sort of thing。

Another example is suppose I'm working on a bug fix and I have print f statements I've put all over my code and then finally I find the bug and there's a plus one somewhere where there shouldn't be a plus one。

 so I go to fix that。 and then I want to take a new snapshot with my fix。

 but the snapshot probably shouldn't include all of my print statements。

 It just needs to include the fix of removing that plus one。

 So one way I could solve that issue is I could go and manually remove all the print statements but Git has a much better way of doing that。

 There's actually a way to specify that I only want to add the change of removing that plus one。

 Then I can commit that take the new snapshot。 and then I can throw away all the other changes。

 their commands for doing that and some of them are linkeded in the lecture nodes。

 So those are two ways in which you can use the staging area to help you and why there isn't just like a snapshot everything command。

There's another example。Yeah， so yeah， John points out that yet another example is you might have log files in your current directory that your program runs when you run it。

 and you probably don't want to include those when you take a snapshot。There's probably other things。

 like if you compile your project， you end up with a bunch of dot O and dot F files。

 you probably don't want those to be part of your history。嗯。

So going back to what I was showing you before， I'm going to clear the terminal screen and then show you the Git log command。

 So Git log lets you visualize the version history。 and this is an incredibly helpful command。

By default， Git log shows you a flattened version of the version history。

 So even though the version history is a graph， this will linearize it and just show things in order。

 I personally find that confusing。 So I almost never use Git log。 And instead。

 Git log takes some arguments that actually show the history as a graph so。😊，You can treat this as a。

Magic incantation for now， and you can read the documentation if you want to figure out exactly what each of those flags does。

 but for now this doesn't look all that different because we only have one node in our graph So visualizingizing it as a flattened thing versus a graph doesn't look all that different。

Let me go ahead and create a new snapshot。 and then we can run this command again and then see exactly what it does。

 So I will。Put another line into hello dot text， and so if I cat Ho dottex。

 it has the thing it had before， plus this。I can do Git commit and notice this doesn't do anything。

 It just says no no changes staged for commit。 Why is that。

 iss because I didn't add this to the staging area。

 I didn't tell Git that this is something that should be included in the next snapshot。

So if I do get add Ho。t textex。Get status， it says， okay， this change is ready to be committed。

 this modification to this file。And now I can do Git commit。

I'm going put in a useless commit message。And the new changes have been made。 And so now。

My history has another note in it， and then this note has some hash that's shown on the screen。

And now if I rerun that command from earlier， the Git log with all these arguments。

 it actually starts looking more like a graph here。Notice that this is like that graph turned。

This way， the more recent， so it's shown vertically not horizontally。

 and the more recent commits are shown at the top。This is showing one commit。

 it shows this commit hash shows a bunch of metadata， including the commit message。

And then this is the part I want to talk about next。 So remember。

 we talked about objects like the actual contents of your repository。

 and then we talked about references， ways of naming things in the repository with human readable names。

So master is one reference that's created by default when you initialize a Git repository and by convention it generally refers to like the main branch of development in your code。

 so master will represent like the most up to date version of your project。So here。

 you can think of master as a pointer to this commit， and as we add more commits。

 this pointer will be mutated to 0。2 later commits。And we also see here head。

 this is a special reference in Git， it's a reference like master， but it's special in some way。

 and head basically is used to refer to where you are currently looking right now。

Any questions so far？Yeah， question。It had to do with GitHub and it was like a part。

Is that like a separate thing？That's an excellent question。

 so the question is worked with GitHub before and you have to create an account to do that。

 how does GitHub relate to Git and the answer to that question is GitHub is a repository host for Git。

You can create an account on Gitthub and store a Git repository there and use that to collaborate with other people。

 But Git as a command line tool is just independent from Gitthub。

 So you don't have to use Gitthub to use Git。 You don't have to use Gitthub to collaborate with Git either。

 like there are other providers of Git repositories like Btbuyt or Gittb or things like that。

 And so yeah， Github is a host for Gitthub repositories。Any other questions？So after we make the。

You have to commit and make this GiHub。un down we make this get like ahead in the master。

 and we have two things that are shown in the graph。If we want to put it up on GitHub。

 that's the separate set of command。Me a login。Yeah。

 so the question is if you want this repository to end up on GitHub， how do you do that， Yeah。

 there's a separate set of commands for doing that's so that concept of having your local copy of version history interact with another copy So the other copy is called a remote and then there's a set of commands for interacting with Git remotes and sending data from your remote or from your copy to Git remotes and getting data from Git remoteotes into your local copy and we'll cover that later in this lecture or maybe in the lecture notes Dr might make a supplemental video to go along with this lecture。

Any other questions？Okay， a couple other basic commands to show you。 So so far。

 I've shown you a version history， and we've taken a file and modified it。

But we haven't really made use of the history in any way besides reading the messages。

 So one useful Git command is something called Git checkout。 and this is a kind of wacky command。

 it lets you do a bunch of different things。 but one thing it lets you do is move around in your version history。

 So one thing I can do is give git check out the commit hash of a previous commit and I don't need to type the whole thing I can give it a prefix and it's smart enough to figure out what I'm talking about。

 And what this will do is it will change the state of my working directory to how it was。

At that commit。So here， if I do catHlow。t text， recall that I had only one line in here before at the first commit。

 and later I added that second line。Now if I do that Git log command and this command is super helpful like it shows you all of the things if I do this command。

 notice that this output looks a little bit different than before。

 like my actual history contents that commits themselves and the way they relate to each other and all that have not changed but the references have so notice that head is down here。

 even the master is still up here so at high level what this is telling me is this is what I'm looking at right now。

If I want to go back here， I could type gett checkout and this commit hash。

Does anybody know a different thing I could type here instead of this long hash in order to go back to this commit？

Yeah。You can give it the name of this is a branch colored in green here。

 and it refers to this commit so I can give it the short name or the human readable name instead。

And now if I do catHlo dot text， notice that it has that second line。So when you do check out。

It is actually replacing the file。Current。TheThe file。哇。Yeah。

it's like you can change a whole bunch of files without even realize life。Yeah， so to repeat that。

Get checkout actually changes the contents of your working directory。

 and so in that way it can be a somewhat dangerous command if you misuse it， for example。

 you can see if I modify Ho dot text。And then try that Git checkout command from earlier actually notice here that it says error。

 it says there's a file that's been modified and the Git checkout would destroy your modification。

 you probably want to do something about that， but there are flags like， for example。

 Gi checkout F does this forcibly and now it's thrown away my changes。

 So Git checkout has the potential to well it certainly does modify things in your working directory and it can actually destroy changes if you're not careful。

Question。In the lingo here， check out moves we headed。Exactly。Yeah。

 this is exactly what I want you to be thinking about。

 how these the crazy Git interface commands correspond to mutations to this graph and mutations to the reference or like additions to the graph and mutations to the references map。

So yeah， exactly， get checkout moves the head pointer and then also mutates the contents of your working directory with the contents that the head pointer now points to。

 corresponding to that commit。Any other questions？All right。

 so one other basic command I want to show you is the Git diff command。

 So I'm going to modify this file and put some changes in it。The Gi diff command。

Can show you what's changed since the last snapshot。

 It's just helpful for knowing what's going on with your project。

Git diiff can also take extra arguments like。You can do gitDff and say compute diff not with respect to the last snapshot。

 the last commit， but with respect to this， and let'll say， okay。

 two lines have been added since this point to Ho dot text。Question。

So if you don't supply like a hat。我来。Of what if。So the question is。

What does this command do without this extra argument here？That's a good question。

 So what this does is it computes a diff with respect to head。And。Looking at my get log。

 head is pointing to here， so it's doing a git diff with respect to this commit。

 and you can actually specify that explicitly， you can do gitD headHlo dot text。

And it will do the same thing。Wherever head is， isn't it going to like modify hello？

I guess I don't understand how head can be somewhere。Hello。Different from me。That。I okay yes。

 so that's a good question。 It's like how can hello dot text be different than head because head refers to where you currently are So to clarify head refers to the last snapshot so like in my picture here had。

😊，And master。Are both here and the current working directory is kind of independent of this like you're going delete all the files in here。

 doesn't change the history graph or the references。 And so yeah。

 you can have differences between here and here and at a high level。

 this is how you work on a project like you make some changes here。

 you get add them to stage them and then you get commit and that creates a new snapshot here。

Good question。 Any other questions？Yeah， so is Git actually saving all of these different versions like the way I would if I you know save version one。

 version two， et cetera， or is it somehow just？So the question is。

 does Git actually save all this stuff kind of in the obvious way or is it doing something fancier。

 The answer is is it is doing something a little bit fancier。

 but you can it has an interface that lets you think of it like it's stored that way in practice Git uses deelta compression it also does some other stuff。

 but yeah the on disc representationation is actually reasonably efficient。😊，Question。

Still like this was that example you had there say I want。

To were different between two different things that are somewhere back up my history。

I think there too any other points。Yeah， that's a good question。

 So the question is here we were comparing the current working directory with a particular snapshot in the past。

 can we compare two snapshots with each other like two different points in the history and yeah getDff can take yet another argument here so I can for example。

 compare head with I did it in the wrong order I can compare what change from here to head in hello dot text and it shows me that I added the second line in there。

Any other questions？So you're working on a project。は発こ。You want this。the nextさ。Outside of dropbox。

Yeah， so the question is you're working on a share a project in a Dropbox folder and now you want to migrate to Git。

 does it make sense to turn the Dropbox folder into Git repo。

 Do not use Git inside Dropbox Dropbox will corrupt your Git repo。

 There are good solutions to doing that。 One is just use GitHub。

 Otherwise talk to me after class and there are ways of using Dropbox as a Git remote safely。

Any other questions？Next， we're going to talk about branching and merging。

 which is another powerful feature of git that you almost certainly use。

Both when working on your own projects and when collaborating with others。For this series of demos。

 we're going to， rather than work with a simple text file。

 actually write a simple computer program because it'll better illustrate the concepts of branching and merg。

AndAs we go through this demonstration， we'll keep in mind how the Git interface commands connect to the underlying data model。

 connect to objects and references， and how these commands modify those two data structures。

Let me do a git status to see the current state of my repository here I've modified Ho dot text。

 I actually don't really care about this modification anymore。

 this is some random file if I do gi checkoutHo dot text。

 this is another different use of the checkout command which basically throws away the changes that I've made in the working directory and sets the contents of Ho dot text back to the way it was in the snapshot that head points to if I look at Git log all graph decorate。

It'll show me that here I added the initial Holot text， and I'd added that single line here。

 and so now Holoott text doesn't have that third line I'd added。 it just has the original two。Next。

 I'm going to write a very simple program， we'll call this program animal。 pi。

And let me just go ahead and write a program that prints a little bit of output when I run it。

Let's see。So when I run this program， it runs main， main calls default。

 and then let me go ahead and define default。And default is going just going to print hello。

 So this is a program that greets its user。 And so if I run animal dot pi。

 I'll see that it just prints hello。 So that'll be our starting point。 If I do a gi status。

 It shows me that。Animal dot pi is an untracked file。To begin with。

 I want this to be part of the snapshot。 So I'm going to get add animalal。

 pi to add it to the staging area and then do a gi commit。Here。

 I'm going to write yet another useless commit message。

 Don't actually write commit messages like this in real projects。 But for now， this is fine。

 So now I have this basic animal do pi。 And if I look at my gi history。

 now I have this latest snapshot。This is the commit hash。

 and this is where the master branch is pointing。 Now。

 we're actually going to demonstrate how to use git branches to have parallel lines of development。

The Git branch command or the branch subcom is used to access functionality related to branching。

 just running Git branch by itself lists all the branches that are present in the local repository。

 It can also take an extra argument， VV to be extra verbose and print some extra information。

If we do Git branch and then specify the name for a new branch， Git will create a new branch。

 which is just a reference that points to the same place where we're currently looking。

 So now there's a new reference called CA。AReence in this case is the same as branch。

 there's a new branch called Cat， which points to wherever head was pointing。

 And if I look at the git log again， I'll see that here， head points to master， master is over here。

 and this is also where the cat branches is。 So now I have two branches。

 two references that resolve to the same commit。Git is actually aware of not only which snapshot in the history you're currently looking at。

 So head points to this commit， but it's also aware of head kind of being associated with with a branch。

 So here head is associated with master。 And it's the case that if I create a new snapshot。

 if I type Git commit at this point， the next snapshot will。Be created。

 and then master will point to that new snapshot。 Master will be updated along with head。

If I do get checkout。Cat what this does is it switches to the branch cat。

 It replaces the contents of the working director with whatever cat's pointing to。

 which in this case is the same as the contents before。 But now if I look at the gi log again。

 now I have head pointed to cat instead of master and then master also points to the same place。

 the same underlying commit。And now at this point， if I make changes to my current working directory and make a new commit。

 the cat branch， the cat pointer will be updated to point to the new commit。

 whereas master will continue pointing wherever it pointed before。

 So let me go ahead and modify animal do pi to add some cat related functionality So I'm going to say that if do R v1 is cat then run the cat function otherwise run the default function and then let me go ahead and import define the cat function So cats don't say hello they meow So cat prints meow。

It'stra enough。 So now if I run animal do pi and give it the cat argument， it says meo。

 if I give it some other argument， it defaults back to the hello。Alright， so a simple change I made。

 If I do a git status， it says that animal that pie has been modified。 If I on git diff。

 it'll show me what's changed since the last commit。

 So here I've added this cat function highlighted in green and then also changed the main function a little bit。

Now here if I do get add animal dot pi。Get commit。I'm going to actually write a slightly more useful commit message this time。

 I'm going to add cat functionality。And now if I look at the Git log。I see a little more stuff。

 I'm gonna to show you one more argument to this Gi log command。 There's an argument。

 dash dash1 line， one line spelled correctly， which shows a more compact representation of the graph。

 So this itll be a more useful thing to use because we're super zoomed into the screen and there isn't that much space to show a long commit history。

So here we see the sequence of commits is still linear and we have master still pointing wherever it pointed before where we just had that basic underlying animal pi functionality。

 but now we have this cat branch， which adds the cat functionality。 We could， for example。

 get checkout master to go back to the master branch。And then here， if we look at animal dot pi。

 it doesn't have the cat functionality anymore。 And if we look at the gi log。

 we'll see that head is pointing to master。 So this where we can jump back and forth between parallel lines of development。

So now that we have the cat functionality， suppose that we want to work on adding dog functionality in parallel and suppose that in this case。

 like the cat functionality is under development or maybe somebody else is working on it。

 so we just want to start from the base master commit and build the dog functionality starting from there。

So now what do I want to do， I want to create a new branch dog for adding the dog related functionality。

 and I'll eventually merge it in later。 so I can use the gi branch dog command followed by the Git checkout dog command。

To create a new dog branch and then check it out， there's actually a short form for this。

 Get check out dashby dog。 So this does get branch dog， get checkout dog。

 And now if I look at my graph。I have cat where it was before， master where it was before。

 but now head， instead of pointing to master as it did before。

 now head points to this newly created dog reference， which is also at the same。

 so at this base commit。And now I'll go ahead and add my dog functionality。

 So let me go and define my dog function。Dogs don't say hello， they saywoof。

And then I'll add some similar functionality here to decide whether to run default or dog。

 So if the first argument is dog， then I want to run the dog function otherwise，ops。Otherwise。

 I want to run the default function。So here's what I've changed with respect to the base commit。

 wherever master is pointing。So I've added the dog function， and I've changed me in a little bit。

 So a kind of parallel modification to what I did in the cat branch。

Let me go ahead and get add animalimal。 Pius add it to the staging area。If I do get status。

 I'll see that this change will be committed when I make the next commit。And then I do gi commitit。

 add dog functionality。Now when I look at the gi graph。

It actually looks kind of interesting compared to the ones we've looked at before。

 This shows that these three commits are in common with the ones that come after it。

 but then the history is actually forked after this point。

 And I have this one commit that adds cat functionality in one line of development。

 And then I have this other commit that adds dog functionality in this other line of development。

 And then using the git checkout commit， I can switch back and forth between dog and cat and master。

😊，So this is great， I can do development and parallel on different features。

 but this is only really useful if I can eventually combine those things back into my original line of development to have both features in a single version of my source code。

So the command that's used to do that is git merge。

 so like Git branch and git merge can kind of be thought of as opposites。Let me check out。

 Gi check out master。 Let me check out my master branch。 So now I see head points to master。

 And then I want to merge the cat functionality and the dog functionality into master。

 And to do that， I can use the Git merge command。And git mergege is actually pretty fancy。

 And I can actually merge cat and dog at the same time。 But for this demonstration。

 we're going to only merge one thing at a time。 So first， I'll type git merge cat。

And Gi says some stuff。 here it says fast forward。 So what is going on here。 Well。

 this is one interesting thing that Git can do when you're at a particular commit and you merge some other branch in where that other branch has the current commit as a predecessor。

It's not necessary to create any new snapshots or do any other fancy stuff。

 basically this master branch here， this pointer to this commit can just be moved to point here instead to incorporate that cat functionality。

And so if we look at the Git log again， we see that master is basically pointing to the same places wherever cat was pointing。

All right， so now we're on the master branch and it has the cat functionality， great。

 we're halfway there。If we look at。Animal do pie， it has the cat functionality。

 but it's missing the dog stuff。So let's try Git merge Dog next。

 something a little bit more interesting happens this time。 So this time。

 the branch can't be fastfored like it was before。 It's not that one thing was just strictly older than the other thing。

 there's been parallel development that may be kind of incompatible with the current set of changes。

 And so Git does its best job at automatically merging the changes from this other branch。

 So it says automering animal dot Pi。 but in this particular case。

 theres what was what's called merge conflict。 So it wasn't able to automatically resolve on all the conflicts between these two parallel branches of development。

 this is something you'll see in practice when you're working on real software projects and they're complicated slightly incompatible changes happening in parallel。

So at this point， it's left up to the developer to fix this issue。

 And Git offers some functionality in order to help resolve merge conflicts。

 There's a program called Git merge toolol。And in my particular setup， this will launch VimDiff。

 Well， actually， this is not configured。 VmDiff， I think will start the right program。呃。Let me。

Set up my git to launch the correct tool。啊。Actually。

 let's skip that part and let's just manually look at this Vimdiff。

 So there's a program called Vimdiff， which can be set up to be launched when you type in Git mergege tool。

 which is a tool that you use when you try gett merge in their merge conflicts。

But in this particular case， we'll just manually resolve them。So let me I did get merge dashboard。

 so it put me back into state I was before I tried that gi merge。

 So this is the current state of my repository and back to the case where master is at the same place as cat。

 and I'm about to merge in dog。 So I do get merge dog。 and it says conflict。

 merge conflict and animal dot pi。 So let's just look at animal do pi directly。

So it looks like this top part looks pretty reasonable。

 it has both the cat function and the dog function， which is exactly what I want。

 but now I see some weird stuff in main and this is where I had slightly incompatible changes So here it says that in one thing like basically the branch you were on you had this content and then the branch you're trying to merge had this content and then these things here the angle brackets and the equals are conflict markers So this is where you were and this is the thing you're trying to merge in and it's basically saying that this in one case。

 this in the other case and Gi doesn't really know how to resolve these two and it's left up to the programmer to fix this problem。

So in this particular case， we can go ahead and delete the conflict markers and then。

Turns out that we can actually concatenate this code together and does the right thing。

 Maybe we want to make a small change。 like this should be an if， this should be an elseif。

 and this should be an else that might make a little bit more sense。Actually。

 I think it's necessary for correctness here。 So the programmer needed to modify the code a little bit in order to make it sensible when it's merged together。

 But once the programmer has fixed the merge conflicts。

 fixed the stuff between the conflict markers you can save this file。 and we can do git merge， dash。

 dash continue to tell Gi that we fixed the issues。

It's necessary to re add animal dot pi to tell Git that we've actually fixed these issues。

 and then when you do to get merge dash continue， it pops up an editor and we can give a commit message for this new commit that we're about to create。

 And now if we look at the Git history， we have。The single commit that represents。

Our merge commit that we just made， which merges in the dog functionality。

And here this has as parents， both the dog commit and the cat commit。

 So both these branches appear in our history from this point backwards。

 and this current commit that we're on incorporates the functionality from both of these branches。So。

 if we。Run animal pie with cat。 It does the cat thing， if we run it with dog， it does the dog thing。

 and if we run it with anything else， it falls back to the default implementation。

So this is a demonstration of how you branch and Git to do development on different things in parallel and then how you can use the merge command and Git to resolve those different branches and combine them together into a single snapshot that includes all the functionality that was developed in parallel with each other。

Then one thing that can happen when you're doing Git branching and merging is you run into merge conflicts and these conflicts show up as conflict markers and text files。

 you can manually resolve them。 and Git also has some tools that can help with this。

 though these tools are kind of advanced and will only refer to them in the lecture notes and not actually demonstrate them for you。

So that's Git branching and me， Any questions？No。Great。

 so moving on to the next topic of this lecture， we will talk about Git remotes。

 So this is basically how you collaborate with other people using Git。😊，A gi repository。

The stuff contained in this dot Git folder represents kind of an entire copy of the history。

 It has the objects and the references and contains all the previous snapshots。

 And the way you collaborate with other people using Git is that other people can also have copies of the entire Git repository。

And then your get。Copy your local instantiation of the repository can be aware of the existence of other clones of the same repository。

 And this is a concept known as remotes。 So the git remote command will list all the remotes that Git is aware of for the current repository。

 and in our case with this repository right here。 This command Git remote。

 just doesn't print anything because we haven't configured any remotes。

 Git is only aware of the single local copy of the repository that we're working with here。

But in practice， if you're collaborating with other people。

 your Git might be aware of the copy of the code that is on GitHub。

 and then there's a set of commands to send changes from your local copy of the repository to a remote that your Git is aware of。

 So sending stuff from your computer to GitHub for example。

 and then there's another set of commands for fetching changes made in a local repository to get changes from GitHub into your own local copy。

In this demonstration here， we actually won't go and configure a GitHub account and log in and create a new repository on there。

 You can find other tutorials for doing that。 We'll actually just use a separate folder on the same computer and treat it like a Git remote。

So let me I'm in the demo folder here， let me go up one directory。

 I have a directory called Playground that has this demo folder。

And I'll go ahead and create a new directory in here， and I'll call it remote。And then。

Do get in it dash， dash bear in here， This is a command that you'll probably never need to use in regular usage。

But now what I've done is made remote into a folder that's appropriate to use as a git remote。

 So now going back into my demo folder here， my main repository。

 I can do Git remote to list the remotes。 There's nothing yet。

But I can use the Git remote ad functionality to make my local repository aware of the existence of。

 of the remote。So I can do git remoteote ad and then the format for this is that remotes have names and then they have a URL。

 so in this case I'll use the name origin that's often used by convention as the name of the remote if you're only using one。

And then for the URL， normally this will be like a GitHub URL or something like that or Bit bucket URL or Gitlab URL if you're using an online repository hosting service。

 but in this case， it's just a path to a folder on my local machine。

 there's a folder in the parent directory called remote that will act as the Git remotemote for this repository。

So now once I've done that， there's a set of commands for interacting with this remote。

One command that's useful is the Git push command。This command can send the changes from your computer to the remote。

And the format for this command is that Git push takes in the name of remote。

And then it takes in a local branch name， colon a remote branch name。

 and what it does is it creates a new branch or updates a branch on the remote。

With the name specified here and sets it to the contents of the branch specified here。

So a concrete use of this might look like git push， I have only one remote called origin。

And then what should I push， Let me look at my history graph。I have a bunch of things I could push。

 let me get push to origin the master branch from my local machine， colon master。

 So I want to create a branch on the remote machine with the name master that is going to be the same as the master branch on my local machine。

 So let me go ahead and run that command。 It prints out some stuff， and it says on the remote。

 I created a new branch， remote master points to the same branch as master on my local machine。

And now if I do a Git log， it shows me so in blue is head where I currently am in green are all the branches in my local Git repository and now we see one new color here that we hadn't seen before。

 so in red Git shows references that are present on the remotes that my local copy is aware of so on the remote origin there's also a branch that happens to have the name master that points to the same place as my local branch master points。

And so now if I make updates to my local copy， like suppose here I go in and change the capitalization of these things。

And then get add animal dot Pi， Git commit。 Here's a short form for commit with a message。

 So it doesn't pop up the editor。 I'll give it a late and commit message。 And now。

 if I look at the Git graph。Now， I see that I've created this new snapshot here that has this lower casing stuff in it。

 but origin master is still back here。So if somebody else looks at the remote。

 they will only see the changes up to here， and we can actually demonstrate this functionality。

 so let me go ahead and open up a new tab here。And go into my playground directory。

The Git clone command is a command that somebody can use to start from some copy of repository somewhere and make their own local copy。

 So this is often a command to use when starting out with a Git repo。

 like there might be something available on Gitthub and you want to copy it all on your machine in order to look at it or start doing development。

 And so the format for Git clone is that it takes in a URL and then it takes in a name for a folder。

For where to clone it。So in our case here， we're just going to clone from this remote directory。

 We're pretending that this remote folder is actually a remote machine。

And then we're all cloned into the folder called demo2。So cloning into demo2 done。

And I'm going to seed into that directory。 And then now here。

 I'm going to rename these tabs at the bottom。We'll say this one's machine one and this one's machine  two。

 So you can think of these as two different people on different machines with their own copy of the repository。

 and they're both interacting with the single remote。

So if I do my Git log command that I've been doing on machine1， I see on machinech 2。

 I see this portion of the history。Master on Mach two is pointing to the same place as origin master。

And it says mergege branch dogg。 So if I look at animal do pi here。

 it doesn't have the changes that I made on machine 2， even though they're or sorry on machine one。

Where I have this new commit that is only present on this machine。

 but not on the remote and not on machine too。So if I want to fix that。

 if I want to send these changes up to the remote， like think of it as sending it up to GitHub or up to the machine that's holding or maintaining the source code。

 I can use the Git push command again， Git push， origin。Master， Col master。And this will work。

 but this is kind of annoying to type every time you want to do this。

 like this is a really common operation。So Git has a way of making this a little bit simpler。

It has a way of maintaining relationships between branches on your own local machine and branches on remote machines。

 It has a way of knowing what branch on a remote machine a local branch corresponds to so that you can type in a shortened version of GitP and it'll know what all the arguments to the expanded form would have been。

And there are a couple different syntaxes for doing this。

 One way is to use the Git branch dash dash set upstream 2 command。

And what this does is for the branch that's currently checked out， which is master。

 it will set the upstream2， and I'll type in origin master。And see。

 now it says branch master setup up to track remote branch master from origin。 Now， if I type in。

 get branch dash V V， remember this is。Tell me about all the branches that I know about in a very verbose way。

 That's what the dash V V means。I have three branches on my local machine on Ma 1。 I have cat。

 dog and master。And master on my local machine corresponds to origin master。

So now I can type in just git push without all the extra arguments。

 I could have done this as Git push， origin， master， Co and master， but it wasn't necessary。

It'll know that I want to push to Orig master and it will make that change。

So now these changes are present on the remote， we can go over to machine to pretend we're the other guy interacting with this repository and if I do my Git log command。

 I still don't see the changes， so what's going on here。

 well it's necessary in order to run a separate command or it's necessary to run a separate command in order to have these changes present here by default。

 all the Git commands don't talk to the internet， it all works locally。

 which means it works very fast， but then there are special commands for saying that you want to retrieve changes that have been made somewhere else。

And the command that's used for doing that is a command called Git fetch。

 Git fetchtch takes the as an argument， the name of the remote。 But if there's only one。

 it'll just use that。 So we can type in Git fetch。And then it's talked to this remote repository。

And it says that。Theres some update on the remote and we can visualize it by running Git log。

 and now we see here on another situation that we hadn't seen before。

 we have master on our local machine， the master branch doesn't change。

 The Git fetchch command doesn't change any of our local history or local references like our branches。

 but now it's aware that origin master has been updated to point to this new commit。

And there's a separate command。 We can do gi merge。In order to move master up to here。

Or there's another command called Git pull， which is the same as doing Git fetch， and then Git merge。

So if we just do get pull here， for example。It will say it's fast forwarding。

 it's merging in origin mastering into our master。And now if we look at the git history graph。

We've currently checked out master， Master points to the same places as the origin master that we're aware of。

 and all the changes between Ma  two and Mach one are in sync。

So those are the basic commands for interacting with Git remotes。

 So there's the Git remote command for listing remotes and adding and removing them and things like that。

 And then there's the Git push command for sending changes from your local copy of the repository to the remote。

 And then there's the Git fetch command， which is for retrieving changes from a repository that are present on a remote and getting the changes on your local machine。

And once you retrieve those changes， you can use Git merge to update your local branch to point to the same place where the remote branch does。

 or you can use the Git pull command， which does basically the same thing as Git fetchch plus Git merge。

And then of course， separate from all these commands is the Git clone command that we talked about a little while ago。

 which is for taking a copy of remote repository and initializing a local repository from that copy。

So that's a quick overview of the different commands used to interact with Git remotes。

 and now these are kind of complicated and it takes a while to master all the different variations of this and understand how they're actually used in practice。

 but hopefully this acts as a quick introduction and you can see how the different commands relate to the underlying data model all of these commands all they do is fetch new objects from other places or send objects from the local mission to other places and these commands mutate references。

So， relating these。Relating the interface of Git and some of these kind of badly designed commands to the underlying data model can help it make a lot more sense。

The final topic we're going to cover today is。It's a kind of overview of other things that get can do that we're not going to go into detail in teaching you how to do。

 but we just want to tell you that these functionalities exist in case you need to do these things yourself。

 You can look up the documentation and find out exactly how to do it。

One thing is the Gi config command。Like a lot of tools we've looked at。

 like the shell and Tms and things like that， Git is highly configurable and it's configured using a plain text file。

 which can be edited either through the command line interface。

 So Git Config can take in flags that will modify this text file。

 or you can edit the dot Git config file in the home folder。With plain tax configuration。

And so for this lecture， I've actually cut out most of my Git Config and only left in my username and email for what will go into Git commits。

 but there's a lot of stuff you can put in here， which will make Git。

Behave nicer or behave the way you want it to。 And you can look online for different ways people have configured their Git configs。

 Oftentimes people have documentation in their Git configs， which can be found on Github。

There's a couple other random commands that could be useful。

 One is for when you want to clone a repository with git clone that's really gigantic。

Getit cloned by default copies the entire version history from the remote。

 It's downloading the repository from， but there's an argument you can pass it。

 which is dash shallow， which will avoid doing that。

 So if there's some copy of some code on Github say that you want to get a copy of on your local machine。

 but that repository is really gigantic and has a billion commits。

 if you use Git clone dash dash shallow， this will be much faster。 But then， of course。

 you won't have the version history on your local machine。 you'll just have the latest snapshot。

Another command that we find really useful when doing development on real software projects is an interactive version of the Git add command。

 So to demonstrate this， I'm going to go ahead and make a couple different changes to my animal do Pi。

😊，One change I'll make。Here I'll chain some text here， and then I'll put a new print statement here。

So let's pretend that this first change was some real change I wanted to make， say it's a bug fix。

 and this other change here was a printf that I added for debugging。

 but I don't actually want to commit in the next snapshot。 If I do a git diff。

 it'll show me that yes， I've made these two changes and if I do git add animal do pi。

It will stage both of those changes for a commit。 And that's not what I want。

 And could go manually remove this debug print and then do this get animal do get add animal dot pi。

 But there's an easier way to do it。 There's this gett add dash P command。

 which lets me interactively stage pieces of files for a commit。

 And so there's some interface for working with this。 So here's thing。

 Do I want to stage both of these changes and no I don't。

 But I want to split it into two smaller changes This 1 I do want to keep。 So I say why for yes。

 And this one I don't want to keep。 So I say n for no。 And then if I do gi di dash dash cached。

This will show me what changes are staged for commit。

 So now it shows only the actual change I wanted to keep。 If I do gi di。

 it'll still show me the other change that is not going to be part of the next。The next commit。

 which is a change I didn't want to keep。 And then with this， I can do get commit。

Specify some commit message。 Now I only have this change left。

 and then I can do get checkout animalimal。 apply to throw away this change。

So Git add dash P for interactive staging is a useful thing。

A couple other commands that you can look up on your own are the Git blameme command。

So this command sounds kind of ominous， but it can be used to figure out who edited what line of a file。

 and you can also find the corresponding commit that was responsible for modifying that particular line of that file。

 And then you can look up commit messages associated with that and whatnot？

 So this is not that interesting to do in our current toy repository。

 But I'll go over to the repository for the class website and we can look at some particular file here and let me go to some particular line here And I can be looking at this and be like oh。

 why was this particular line added， what does it mean And I can look at the get blame for this。

 So if I do get blame config YML。It'll print out all the lines kind of in the right column。

 And then in the left side， it'll show me what commit that change is made in and by whom And then looking at this。

 like I can go down to this collections line。It was made in this commit。

 That's the last commit that modified that line。 And now I can use the Git show command to get information for that particular commit。

Oh， and this is kind of useful。 Redo lectures as a collection。

 that's probably what was related to that collections line。

 and then beyond just showing the commit and the commit message。

 it also shows me the actual changes introduced in that particular commit and they can go look through them and understand what's going on。

Another kind of cool command is a command called Git stash。

 So let's go back to our demo repository and demonstrate that here。 So say have some changes。Here。

And I temporarily want to put them away。 If I do gi stash。

 it will revert my working directory to the state。 it was in at the last commit。

 So if I do cat Ho dot text， that change is gone。 but it's not just deleted。 It's saved somewhere。

 And if I do gi stash pop， it will undo the stash。 So now if I look at hello dot text。

It has the changes I made， so yet another useful command。

Another really neat command is something called Git biect。

 and this has a complicated interface that we're not going to demonstrate in detail。

 but basically this is a tool that can be used to solve a bunch of problems where you would need to manually search history for something。

Suppose you're in a scenario where you've been working on a project for a long time。

 you have like lots and lots of snapshots。 youre 1000 commits in。

 and then you notice that some unit test doesn't pass anymore。

 But you know that this was passing like one year ago and you're trying to figure out at what point did it break。

 Like at what point was this regression in your code introduced。

 So one thing you could do is manually check out like go back one commit and see if the unit test is still failing and go back one commit see if it's still failing。

 and eventually you'll find the first commit where the test stopped working and that'll probably tell you what broke。

But that's kind of what I' need to do manually， get bicycled automates that process。

 and it actually binary surges your history， so it does this in the most efficient way possible。

And not only that， Git BiSec can take in a script that it uses to try to figure out whether a commit it's looking at is good or bad。

 so it can be a fully automated process， like you can give Git Bisect a unit test and say。

 find the first commit where this unit test stop passing。It really powerful tool。

Another random thing that's kind of useful is something called a gi ignore file。 So by default。

 if you have random files in a directory， like， let me create the dot D， S underscore store file。

Ohoops， create the dot DS underscore store file。And then do Git status。

 So D S stores like some nuisance file that Mac OS creates， I don't know exactly what goes in here。

 But basically once this file is in this directory， now whenever I do Git status， it says， oh。

 there's this new file that I've never heard of it before， but it's apparently here。

 like do you want to add it And this sort of stuff stuff gets annoying And there's a lot of other stuff beyond OS specific garbage that might be in a directory Like for example。

 if you're working with C code， you might compile it and produce dot o files or executable files or things like that。

 And you probably don't want binaries to be part of your commit history。

 you only want the source code。And so， Git has a way of。

You being able to tell the tool that you don't care about a particular set of files and to ignore them。

 And that's something called a git ignore file。So if I go and modify the file called do get ignoring the current directory。

 I can specify particular file names or patterns of file names， like say I can specify star。0。

 so any file ending in dot0 along with dot Ds store， and then if I touch food。

0 and now do a Git status。I'll see that Git says， okay。

 I have hollowed out text which I've modified sure， and then I have Git ignored。

 so you should track your git ignore file using Git。

 but notice that it doesn't mention my dot Ds store file or my food。

 O file that's present in the current directory because that has been Git ignored。

So that's a quick overview of a little bit of advanced git functionality just to give you a flavor of what sorts of cool things this tool can do。

And then finally， we have a couple other topics that are covered in the lecture notes in more detail。

 I'll just quickly list them here so you know what to look for。

 One is that there are many graphical clients for Git， we don't personally use them。

 We like the Git command line tool， but some of them are kind of okay and you might want to check them out just to see if you prefer using those。

Another thing is。Shell integration。 So you've noticed that in this tutorial。

 I've done Git status a whole bunch to see kind of what's going on with my repository。 Well。

 that's kind of annoying to do。 And a lot of people have their shell prompt set up so that just within this shell prompt itself like on every line。

 It will show me a very succinct summary of what's going on with my repository。

 So it might show me a summary of what branch I have currently checked out along with maybe if I've modified files or untraed files。

 And so we have a link in the lecture notes on how to get some nice shell integration for。😊。

Displaying kind of gi related information in your shell prompt。Similar to that。

 you can get integrations with your text editor。 So for example。

 I use ViIm and I have a plugin for ViIm that does all sorts of interesting Git related stuff。

 One thing I can do within this plugin is look at get blame information。

 remember we just looked at this through the command line Instead I can look at it with this plugin and it lets me work with it a lot faster。

 I can look at get blame， press enter when hovering over a specific commit。

 and it shows me that particular commit in my text editor。

 it even hides all the other files and shows me just the one file I was looking at。

 which is presumably what I care about。

![](img/4a8b0912b0402741368096f70687a362_3.png)

So we have links to that on the lecture notes as well。

And there are a couple other interesting things you could look at there if you're interested。Finally。

 this lecture by itself is probably not enough to teach you everything you need to know about Git。

 It's a good start。 We think that the right way of learning Git was to learn about the underlying data model。

 the whole objects and references and how Git Models history。

 and then we gave you an introduction to using the Git commands。

 and if you want to become really proficient at this tool in the resources section in the lecture notes for today。

 we have a link to a book called Pro Git。 So this is a free book it's nicely written is pretty short。

 And I think going through the first couple chapters of that book should teach you basically everything you need to know in order to use Git proficiently for real software projects and for contributing to projects on Github and things like that。

And then finally， just like all the other lectures。

 we have a number of exercises you can go through if you want some interesting and challenging problems that you can figure out how to do。

