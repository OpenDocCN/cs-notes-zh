# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p07 P7 Programming environment： Editor (COP-3402 Fall 2024) -BV1v6vdBKEHB_p7-

Welcome back to System Software。So last time we looked at advanced usages of processes on the command line。

 namely piping and other tricks we can do with。Multiplexxers。So today we're going to look at。

Go over the editor， which is a critical part of the developed environment because it allows you to actually modify text。

 And as we'll see today， we can use editors for， for other things like。

Building software using version control。But before we get into today's lecture。

 I'd like to go over the first。Programming project。

So I've released the instructions for the First programming project。

 which is just writing a Hello World program。It's here on the schedule。

But there's a few wrinkles too。So rather than just writing a classic H world。

 I'm asking you to go into Eust， use one of the two text editors that you picked for homework today。

And either EMX or VIm。And write the Hello World program entirely through the command line with that text editor。

 so this will help you practice using your text editor。

 and I'll expect you to use the command line for the entirety of your project development in this course。

So here are the instructions for。嗯。Entering Useust and creating the hellello World program in your editor。

One additional wrinkle that I'd like you to do。Is to record yourself using either Vim or Emax in Eustace。

 And there's the utility that is standard in Unix installations called script。

And script will actually record。Your terminal session so that we can play it back。

So let me show you what this looks like recording this。

 and this is something that you'll submit with your project once it's due in a couple of weeks。

 so it's not due until 917。 so there's almost two weeks。Or more to submit this project。

And we'll go over the several pieces of the Hello World project over the next couple of classes。

But the first step is to write the Hello World program itself。

 so writing itself I expect that everyone can be able to do should be able to do and probably has before many times。

 but here you'll record yourself doing it in EmX or Vm。So let me walk through what this looks like。

 so I've already SSd into Eustace。And so you'll。Make。

Move my old coloror directly out of the way here。Oh， I don't have hellello world yet， so I'll make。

My hellello world application and we have my Ho world folder。And enter the folder。

PWD print working director to see where I am LS to see what's here。 There's there's not no。

Non hiddend files here。So here's how you use the script command。Script。Space dash， capital T， space。

Hello dot timing， so this is a file that will record all the timings between keystrokes。

 space Hello dot script。And this will record the text of your terminal session， so hit enter。

It'll tell you that it's starting to record and what files that it's storing to。

 until you just get the same batch prompt。 So you'll start editing your program here。

 I'll use Eax to create this hellello world program。And then just type out the standard。

Tello World program。Can leave the argument empty。We'll just do printf。Hello， world。

And that's all you need to do so in emX we'll go over editors today。

 but in EX you do control X control S。To save your file， control X， control C to exit。

And that's it to stop recording， you just exit the batchsh session。

And so what script did is it created a new batchsh session， so when you exit that batchsh session。

 you're back into your original session that you SSHd into。

And you can double check that everything has been recorded correctly。Using this command here by。

Using the script replay command。 so I'll give it the timing file， the log file。

 and the number at the end is just a multiplier for time so I can。Run back。

 replay this session three times faster or two times faster or four times faster。

 So I'll replay this back three times faster。 and you'll see as soon as I hit enter。

 I won't be typing anything instead， the the terminal will be replaying。

 the script replay command will be replaying all of the commands and keystrokes that I've entered on the screen and all of their results from Bsh。

 So I hit enter。So it looks like nothing's happening and now here is what I typed。

 it's three times faster than I typed it。But there it is， and so there's the exit command。

 there's the end。And yeah， so thats one of the that's what you'll produce and submit once you submit the final project。

 we will go over how to submit it in two lectures。So you'll have to submit it via Git。

 but we'll go over that in the version control lecture。

So that's the first thing that you'll do so once not so hopefully by today by the time you watch this you'll have learned。

 at least gone through the tutorial of one of the editors EMAC or Vim and be able to complete a pretty straightforward hellello world program so I designed this to be a very。

 very simple programming exercise to give it the opportunity to get comfortable with command editing and command line in general。

Over the next week or so， we will go over how to create a make file and also how to use version control。

 but we'll leave that for the next couple of lectures。

Okay so that's the beginning of the Hello World project。

 this is the first project that you'll submit， remember everything will be submitted on Git and we will go over how to submit things on Git next week。

So that's hellello World program， if you have any questions。

 please feel free to come to office hourss or go on Ed STEM to ask questions， but that's your task。

 first task for the Hello World program。For today's homework do next time， it's largely reading。

So homework six is， so it's up on the website here。Under our lecture for today。And for homework6。

 you'll just read the first couple of chapters of 21st century C。

So you can follow this link to find a link to the digital book remember you don't have to buy this book。

 this book is provided free of charge to UCF students from the UCF library。

And remember to reread these instructions on how to access this book， importantly。

 do not click Read Online。Instead。Download chapters individually， so download the chapters below。

 let me show what that looks like。So when I go to this link here。

 you have to be logged in in the UCF EPN or logged in via UCF somehow and you should see。This page。

So do not click Read onlineline。Instead， scroll down and you'll see all of the chapters available and a download PDF link。

Click on that link。

![](img/983a7cf789b676647890e109ef6dfed7_1.png)

To get access to a PDF version of that section of the book。



![](img/983a7cf789b676647890e109ef6dfed7_3.png)

You should be able to download。The entire all all the first five chapters in the preface in one day。

 you should have enough pages remaining for that one day。

 If you make a mistake or download something else， you can just wait till the next day to download the rest of it。

 but for today's reading for homework 6， you'll only need the preface Chapt 1 and Chapt 2。

 it's about 60 pages give or take I've made most of the preface optional'll just read the first couple pages of the preface and it's about 60 pages so it may take a little more than hour。

 but hopefully it's an easier hour and easier read and then in web courses just write one thing you learned about C programminging from this book because a book takes a kind of a unique approach to see development of modern approach but mainly I want you to get the content of the book for the homework。

Okay， so that's the project， the Hello World Project。And the homework for next time。And as I said。

 the Hello Award project is not due for 12 days from this lecture， not due till the 17th。

 and we'll go over the rest of the tools you need in order to finish and test this project。

I'll finish and submit this project， I should say。Okay， so let's get started in our。

Editor learning about our editor， one of the key parts of our programming environment。

So the first thing I'd like to go over is a development workflow that should make it a little easier to use the command line we talked about terminal multiplexors last time when we went into advanced uses of processes。

And if you recall， a multiplexer is a tool that will let you。Create multiple。

Bash windows or terminal windows， so to speak now they're not windows like a graphical user interface Windows。

 but here I've typed Bobu to enter a Bobu session。And I can use so this is my。First， the Ou window。

 I can use F2 to create。Another window。And each of these batchsh sessions is running simultaneously and you can switch between them using F3 and F4 or alt left and right。

Arrow keys。嗯。So you can use this。 This development workflow is convenient because I can keep。

An editor open。While also keeping a terminal window open for。Compiling to testing， using Git。

 using other tools。At the same time。So for instance， if I had。A bug here。

I can easily switch back and forth using alt left and right or F 3 and F 4， switch back and forth。

Between my editor and my compiler， and using。The bash history。

 I can just hit the up arrow to repeat the compile command until I。

Get this program to compile and I think it's correct and that I can start running and testing it you can even keep a third window open for running and keeping tests open。

 you can have another window open for writing and developing tests if you want to keep that separate。

 although Emax as I'll show you later does help you does allow you to have multiple files open。Okay。

 so that's the multiplex survey development workflow that I encourage you to use it will help make you a little faster when working with projects。

 especially since you often need to switch back and forth between compiling。

 running testing and editing and you can actually keep。

Separate windows for each of these or several of those tasks at the same time。All right。

 so the first editor I'm going to show you is EmX and this is one of the two editors that I am requiring for projects in this course Emax is the editor I use the most for development。

 for note taking for web page creation even。And Emax is a little bit more than a text editor。

 It's not just for editing text。 It has lots of。De has a design philosophy that allows it to be more than a text editor。

 according to its manual， it's designed to be self documenting so you can actually access its help manual。

 its help manual is built in， you can ask for the definition of certain key commands。

 you can ask for how to use certain functions。It's designed to be customizable。

 so it comes with a set of key bindings， but you can change these， you can modify these。

 you can make your own key bindings， it's also extensible。

 so it has a language emX list that you can actually write new packages and really fully featured applications within the EmX editor。

 so it doesn't exactly fit the Uni philosophy of one tool that does one small thing but。

Understandably， this is a programming environment tool， this is a programming tool。

 and it can do lots of other stuff that can support programming and other types of text editing work。

So as I mentioned， it's more than a text editor， you can actually invoke processes from it。

 you could run make， you can run a terminal shell， you can run other programs from EMX。

 I've heard people call EMX something like an operating system on its own。

 which is a bit of an exaggeration， but you can absolutely invoke other processes from it。

You can do email IRC， there are packages for doing all these communication tools within the EMX editor。

 one thing that I use all the time is Git integration。

 my projects I use Git the version control that we're going to learn next week。

And there's integration and Gi to make it easier to commit and inspect differences in your files。

 write commit messages and update the software to its remote repository。And of course。

 you can manage files， you can manage directories， you can move things。

 you can change their permissions。There's also a form of windowdoing in EmX。

 which like Bbu is not windowing in the graphical sense， although emX does have a graphical version。

 you can create， you can open multiple frames of。Of or open multiple tiles of files at the same time。

 and there is this really useful package called org mode， which I'll show a little bit later。

 it's basically outlining and note taking and I actually use this to create the class's website。

Just to illustrate。

![](img/983a7cf789b676647890e109ef6dfed7_5.png)

U。How much more you can do with EmX， the fact that it's so extensible。



![](img/983a7cf789b676647890e109ef6dfed7_7.png)

You can actually run。Somebody wrote a Teettriris port。For emax。

 So here's my emax window on the right here。If I type load the EX command or the Tes command。

I'll get a built in Tes game just to show that you can write fully featured programs within the EmX editor environment。



![](img/983a7cf789b676647890e109ef6dfed7_9.png)

Okay， so I've opened the tutorial here on the right， and I'm just going to go through quickly。

 hopefully went over the tutorial if you chose EmX。

 and even if not it's useful to know some of the EmX commands because in Bash。

 a lot of the commands in Dash are similar to the EMX commands， at least the default key bindings。

So with EmX， you know， if you get stuck in Emax in Eustace。And you。Don't know how to escape。

Use control X， followed by control C。 This will。This will exit emAC。

 so here I am in the Eustace version of EX control X。Control C will exit。

 can remember that control C kills processes in bash， so control X control C will exit your。

So just so you can see what commands I'm running， I've turned on a mode that will show all of the commands that I'm running inside of Vmax。

So let's take a look at this tutorial a little bit。

 So there are two modifier keys that are used when running Emax key bindings。 So one is control。

So that's the control key， CTRL on your keyboard， one is called meta in the Emax world。

 but for most PC users or PC keyboard users this is the Alt key。And at least on my Cuword。

 you can use either side， left and right for ergonomic purposes。

 I strongly recommend have one hand hold the modifier key and the other hand hold the keyboard key。

 so for control F， for instance， use your right hand for control your left hand for F doing it with the same hand can get quite fatiguing very quickly。

Alternatively， you can use escape instead of meta so you can say escape。F。So I've used。

MF versus escape F， they're both metaF。So this tutorial goes over some useful commands here for。

Csor movement。To get started， one reason that makes Eac。

 one reason to start with Eex is that you can use the kind of conventional arrow keys。

 page up and page down keys home and end。 So you can see on the right here。

 my which keys I'm pressing， those will work in。In EMax as well。

 they should work even through your terminal。When you're in the terminal。

 you won't be able to use the mouse， so resist the temptation to try to use the mouse。

 although the version windowing version of EMX will it use the mouse button？

We'll be using the Eustace。Terminal version of EmX。Where mouse will not help you do anything。

 you won't be able to move the cursor with the mouse here。

So I've kind of summarized some of the commands you'll need to use EmX。

 they highlight here in the tutorial， the kind of EMX way of moving the cursor。

And they all start with， they all work by holding down control。

And you can kind of remember these with a mnemonic that B is for back。F is for forward。

P is for previous line and is for next line。So you can see here on the right。

 which keys I'm pressing order。The personor and just like C L will clear the screen in bash。

 control L here will center the screen。So the first time you hit C L。

 it'll center the screen on the cursor， so if I move up here to basic cursor control and hit L control L。

 it'll center basic cursor control if I continue to hit control L。It will'll rotate between center。

Top and bottom of the screen。So they highlight this early， it's a useful， useful command。

 they also highlight the way to do page up and page down， which is control V andt Alt V。

 control V is page down， Alt V is page up。Other useful commands are home and end。

You can use home an Androidroid your keyboard， but the UX way is alt control A and control。

So I don't know where they get to it if they get to it here in the tutorial button one useful。

Command is to be able to search for text， so I use these all the time in development。So Cl S。

 and you'll see at the bottom of the screen， it'll bring up this prompt for the search keyword so I can type in bring。

And I can just hit S， hit control S to keep finding more instances。Control R will work backwards。

 starts the same thing backwards。And if you want to stop and get out of this， you can just hit enter。

To end。The search， or you can hit C G to end the search。

 but stay in the same location that you started the search from。

So here's a more sophisticated navigation if you remember。These。Csor movement， keywords。

 you can use alt for them to make them word level for forward and back。And for A And E。

If you use alt A， it'll bring you to。Previous sentence， so beginning of the sentence。

Rather than the beginning of the line。Control A goes the beginning of the line。

 Control the end of the line。Beginning of the sentence， Al E。End of a sentence。嗯。

These planss are also useful being able to go to the top and bottom of the entire file。

 So this is alt。Left angle bracket and alt right angle bracket， so on a PC keyboard。

 this would be alt shift。Left ankle。Because you need the shift to get to the left angle bracket and alt right。

So alt left， angle bracket， alt right angle bracket。To go to the top and bottom。F。

So if you don't want to have to leave the。Editor to open a new file。You can use control X， control F。

 you'll see you're prompted for。The name of a file to open here。Control X。

 control S will save a file。 Control X， control W will save a file to a new name。 It's like save as。

So there's some useful。Features to Emax， for instance， I can。Open， let's go here and use this。If I。

 instead of opening a file name， so here I could open， say hellello script and view that Hello。

script file we created earlier in the lecture。If I instead open a directory。

 it will bring me into a directory browsing mode， where I can。呃。Graphically， more or less。

 select different files。To open。You can close a file with。Control X。嗯。Control X， control， control X。

 K。So that will kill what they call a buffer。 So here if I open up some。New file。Control X， K。

We'll bring up。A prompt to kill one of the files， one of the buffers that I have open， but hit enter。

 it will。Kill that file。So you don't need to open EMX for each new file you'd like to edit。

 you can use these additional commands to open multiple files at the same time。

If you want to view what files you have open， you can use control X。Control B。

 Let me show that with the。Key command。 So controlr X， control B。We'll open a window。

That shows you all of the。Fileles that you have opened。Can switch between windows with C X。

So I you don't have to remember all these commands。

 I just want to give you a kind of highlight some of the useful things that you can do with Eex。

 It gives you really this environment， really kind of like an I DE command line I DE that you can use to manage lots of files。

So at the most basic， if you choose EmX as your editor。

 the most basic things you need to know are to use EmX and then the name of file to edit。

You can use the arrow keys page up page down home and end as normal on the PC。

 but also use the control N， control key， control F control B to move around。Your file。

And then control X， control S will save your file。 Control X， control C will exit。So that's。Really。

 all you need to get started on theello hellello World project。

But I'd like to show you a couple of other more extensive fund usages of EMX。So for one。

 you can do so called window management。 Let me show this with the so you can see the。

Commands that Im mentoring。So in the tutorial， they show you control X。1。Which if you do control X1。

 it will。Kill all other windows you have open。 So if you， for instance， in their case。

 they ask you to open up the built in help for a specific command， so control HK。

We'll let you type in an Emax command， so for instance， I'll type in Cr F。

And here it shows you a help document to explain this keyboard shortcut。

 So if you want to get back to a state where you only have a single window open， you do control x1。

And it will kill all other windows except the current one you have。This won't actually。

Kill the help file。 So you can see here， it's still。Open。

But it'll just close the presentation of that file。We can so just like you have。

 control x1 control X2 and control X3 will do other things。 Control X2 will open a new window。

It'll divide your current window into two， and in this case it's just duplicating the same file。

 but then we can use control XB or control X。trol X B or control X control B in order to open a different file in a different window。

So go over that again， controlr X。2 will divide the window into two。And then， you can open。

A new buffer with control XB， so here it's defaulting to openingedor。org。And now I can view two。

Windows at once， two files at once and two windows。 If I keep in and control X2。

 it'll keep subdividing whatever window I have open into two。

So control X1 will bring us back to a single window。 and similarly。

 C X 3 will give us a side by side set of windows。 So here I've got two windows side by side。

 and similarly， I can keep dividing those， if I like。

If I don't want to have to go back to a single window， I can use Control X0 to kill。

One specific window。Control X 0 will kill one specific window。 can even combine control X1。

 control X2， control X3， sorry， Control X2 and control X 3 to divide up。The windows， however， I like。

 I can divide up each window vertically or horizontally。

Can use control X O to switch between windows。The letter O。And control x is0。

Will kill whatever window I'm currently in， so control x0。Will kill that left。Window that I had open。

So let they get back to the tutorial and use control X1 to kill all other windows。

 so that that's window management。So with file management。Let me go to Uis here to show this。

The file management， if I open up a directory。There's several。

 I can do a lot of the bash operations that I could do。InIn Bsh， I can do this in。Eax。

 so capital R will rename a file。Capital C will copy it。And so for instance。

 if I copy hello to hello2。c。I can move this file with rename because remember rename。

Is the same does the same thing as move in the UniuchX world。I can rename this， too。Say new hello。

I can also create directories， so with plus I can create a new directory。With R， I could move。

Hello into。A new directory。And with this direct review， if I hit enter on a folder。

 it will take me into that folder。It actually creates a new buffer window so I can always return to。

The parent directory that way， or I can use the dot dot Foer to return to the parent。So again。

 this is more advanced users of EX， just want to show you what's possible。

 so if you decide to learn EMX， this is the type of functionality that you can ultimately learn gradually with EMX。

So org mode is probably one of the most powerful parts of Emax org mode is。

A outlining and note taking tool that is extremely extensive。 You can do you can keep to do lists。

 You can make calendars and agendas and reminders。 you can attach files。 But at its core。

 it's an outlining tool。 so I can make a。An outline for talking about editors。

And so the commands for doing this， there's lots of shortcuts for doing this。 So if I do alt。

Or meta return， it will just make a new heading for me。

There are shortcuts for demoting and promoting。Headings， so alt arrow keys will。嗯。

The right arrow will promote demo and the left arrow will promote headings。And I can even use tabab。

To close and hide， hide and open。Headings， including ancestors。

 So I'm just kind of obsessively saving as I， as I go。So org mode is how I actually generate this。

Course web page。 So here is index dot org。 This is the file that。

The org mode file that I use to generate this HTML page， so you can actually see it has a table mode。

Create tables in org mode and each of these sections here is actually a heading in org mode。

It'll create a table of contests for me automatically if I so choose。

 I have the title and everything。So， yeah， this。This org mode has exports where I can export it to various different file formats like PDF for LoT。

 plain textex， I think there's a markdown， there's a markdown export。what I use for lecture slides。

Is I also use workload for that。 So here is the。Introduction。Slides that I created。

 and it's really just work mode。 It's a set of headings and subheads with。Content。

And I can export this as an HTML file。So here I've exported org Mos in the HTML file。

 and this is exactly what's used to generate the online notes。On the webp page。 So here。

 if you go to introduction。This is the HTML file generated from my org mode。呃。Introduction。Notes。

But what's even more amazing about this is I can use。A tool that will export it to a presentation。

 So this is revealed at JS。 It's a jascript based library for making HTML based presentations。

And I can use the same org mode file to generate both。An HTML file that is for notes like this。

 and I can also use it to generate a set of slides。All from the same original board mode file。

So this org mode it's super， super powerful， I'm always learning all the time how to use this。

Benefit from it， but that's one cool part of using Es。And so I just。

 I already showed the class that I actually used this to generate the entire。Webage。

 this entire webage is generated from org mode content。

So something that's probably a lot more useful to as developers。

Is I can do version control and software development in。This in Emex。 So we'll look at Git next time。

 but here's an example of using a tool called Mag， which is Emax is built in Git integration。

So here I've。I've edited this source file that is part of one of my research projects and I had to make a small bug fix to it。

And you can see in the magic， it will show me all changes that I've made to the file so far before since the last time I committed the file we'll see more about this when I do gi。

 but I could make。A new branch like。New， which is used for。Submitting updates to source code。

I can make a new branch， and I can even。Stage these changes to be committed。And actually commit them。

So now I've made an update to my software I can push it to remote repository and we'll see more about Git in next week。

 but VM also has this kind of integration， but it makes development much， much faster to use。

This kind of tool。All right， so let's take a look at VIM。

 the other option for doing projects in this class， now I'm much less familiar with VIM。

 I don't use it for development but it is also a very popular choice。

 it also has some extensibility similar to EMX。But its good it's good to know because a lot of other tools use Vm type commands like the less command。

But one of the most sort of unintuitive things about it。

 especially considering modern editors like Emax and other other editors。

 is that it has multiple modes。 So I when you first open up Emax。

 so let's say I want to make a fresh。The version of。Hello world。

I open up a new file if I I start typing text or start typing keys。

 I can't actually start editing the file， I can't start inserting text into the file and that's because it starts out in normal mode。

So normal mode is where you can navigate text， you can edit text， you can save and quit。

 And so if you ever get stuck in FI。You can always type colon Q or colon Q exclamation point to get out of them。

So one thing to be careful of when you're using VI。So if you want to use VIm。

 I strongly recommend going over the VIm tutor， it will walk you through all of these details to make sure you don't。

呃。Get stuck or get stuck in vi。So that a呃呃。So， I put some hints here for exiting vim。Here， okay。

So what are the benefits of？Of having these modes and one reason that I think it Vm is probably still very much lasting is this separation of modes makes the keyboard shortcuts much more straightforward than something like Emax with Emax。

You always have to hold down alt control or some several combinations of keys。

 and that's because in EMX and other modern editors。

 when you start typing you immediately start editing and inserting text into the program so those keys cannot be used for commands。

But in VI， they can be used for commands。And so the vimway of navigating instead of using arrow keys。

Is to use。H and L。For left and right。And J and K for down and up and this is not unlike the WasD keys that like First personson shooter games use。

 it's sort of sort of in that vein where it's a somewhat graphical representation of an arrow pad。

 a little different J& K go down and up but once you get used to this it is pretty efficient because you don't have to move your hands to do a separate set of arrow keys。

 you don't need to double down control or anything， you can just move around。The screen。So there are。

Just like in E Max， there are ways to move forward by a word， so W and E will move forward by a word。

 W moves the beginning of word。Through the end of the word and B will go back to word。

So in contrast to the EmX， where I have to do this with say alt back here I can just type B。

The commands for doing all their kinds of navigation are。Fairly esoteric for a modern editor。

 but also very simple and short because of these two mos。

So I can go to the beginning of a line with zero， think of that as zero。

 can go to the end of a line with money sign， which is the。

End of string Sentinel in like classic string matching theory。G G will go to the beginning of a file。

 capital G will go to the end of a file。One convenient shorthand is to type。

A line number like 43 and capital G， and it'll jump immediately to that line number。

Likelay an EX I can search， so this was somebody asked about how I searched in the less command in class。

In an earlier class， and it's the same as in Vm if I do forward slash and type。A。Stng and hit enter。

It will match， jump the cursor to that match， and I can use lowercase N2。

Cycle through all of the matches and uppercase and to go backwards through the matches。

So in this normal mode， you can also delete characters and cut and paste。

So the then way of doing this x will delete the character in front of you。

 x will capital X will delete the character behind you。

You can combine D for delete with these word movement keys， so DW will delete a word。

 DE will delete a word till it' end。Instead of the capturing the space。

DB will delete a word behind you。Any content that I deleted can be pasted with P and you can undo with U。

DD will delete an entire line， so I don't use Vm very often but。

It's useful to know some of these also one of the arguments is that VI or Vm comes pretty standard on UniX distributions where EMs is usually someone has to install it。

Okay， so that's only a normal mode， how do you actually enter text？So， let's go to our。Hello， world。

Program and start actually entering text the way to enter there are several ways to enter insertion mode。

 I is how you start inserting text on the current cursor。

So here I'll just type in how a World program， so now that I'm in insert mode and it actually tells me at the bottom hopefully that I'm in insert mode。

And with Vm VIm means VIm improved， you can actually still use arrow keys to move around in insert mode。

 I don't know if that was possible historically in VI。

 but the improved version of VI is a little bit more convenient in this respect。So if I。

 for instance， if I。And back in normal mode， I use escape to go back to normal mode。

 I can't enter text here。But I want to go to start typing at the end of the line here if I type I。

 well it's kind to be insert at the cursor， which is before this curly brace。

So if I want to start editing text on the end of a line editing text。

 I you can use capital A for a pen and then continue。太平了。Programmed。Okay。

 so now that I'm in insert mode， I can't do any of the commands that I need to do in order to save the file or quit。

So to get back into normal mode， hit escape， you can always hit escape a couple of times to get you back into normal mode。

 there are other modes besides normal and insert mode。To save a file， you can use。Colon W。

If I try to quit now without saving the file， it'll warn me it won so you don't lose work so you can use colon W to save the file if you want to save and quit immediately you can use Col WQ which will run the W command and the Q command one after another and whileil I've got my Hello world program。

Let's see if it。 Let's see if it builds， and it builds。So that's Vim。

 I'm not a big VIM user but go through the tutorial it's useful to know the commands I recommend DMX I strongly recommend using that。

 but pick whatever you like， ideally pick both， go through the tutorials for both。

 they're not super long。It'll take some practice， I would recommend sticking with one for at least a couple weeks before switching。

Use one of these， at least one of these editors， one or the other when doing all of your class projects。

And so just as a reminder for your Hello World project。

I'd like you to record yourself using the script command using the editor。

 so record yourself and use this as I showed you at the beginning of class and it might be a little bit of a struggle little learning curve。

 but it's just a hello world program it's not a hard program to enter so take that opportunity to get a little muscle memory in using this editor and then you'll be well on your way to doing all command line software development and then once you move on if you move on to IDs or want to use GuUI they'll be that much easier once you're able to do everything on the command line。



![](img/983a7cf789b676647890e109ef6dfed7_11.png)

All right， everyone， talk to you next time。