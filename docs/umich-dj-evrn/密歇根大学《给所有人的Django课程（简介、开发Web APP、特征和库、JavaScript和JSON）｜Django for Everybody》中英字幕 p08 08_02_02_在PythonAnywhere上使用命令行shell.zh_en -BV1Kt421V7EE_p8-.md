# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p08 08_02_02_在PythonAnywhere上使用命令行shell.zh_en -BV1Kt421V7EE_p8-

![](img/fea183fa5643c97927caeb145f0717b8_0.png)

![](img/fea183fa5643c97927caeb145f0717b8_1.png)

Hello and welcome to Django for everybody。 Today， we're going to talk about using the shell。

 It's one of the early assignments in the class。 and I just kind of want to walk you through things。

Now， you might ask yourself， why are we using this old fashioned command line interface。

 Everything And I do is pointing quick， clicky， or I just move my finger and things work。

 And the answer is， yes， friend end users， we try to make things as easy as possible。

 but saw there's always a server behind that kind of cool stuff that you're building。

 And that server，99 per cent of the time doesn't have a clicky graphical user interface。

 It has a command line interface， a textual interface where it gives you a prompt。

 you type some stuff in you hit enter。 You type some more stuff in you hit enter。

And Linux is by far the most popular server system on the planet。

 And so if you're anywhere near the server。Its doesn't hurt to understand a little bit how this works。

 You don't have to be a wizard， but the whole idea of this assignment is to give you some sense of what you're dealing with and weird things that might happen。

While you're using this command line。 So we're going to use Python anywhere as we do in the class。

 But the concept of the shell and the Linux user interface， that's universal across servers。

 Python anywhere just gives you a free one。 Otherwise。

 you'd get one from Amazon or Google or a Windows Azure。So here you are。

 You're logged into Python anywhere。 you go to the consoles tab and you can start a new console in the console。

 you can just run Python interactively if you want。

 you can run a mysql shell that connects to your mysql database， which we'll have later。

 I prefer to not use any of these things except the bash shell。

 The bash is just there's variations in the Linux user interface and bash is just one of them。

 And so you may not use bash you may use the S or S or something else。

 but they all kinda have common things with little tiny subtle differences。

 So I'm going to start a bash shell。 and it's going to take a little bit here to go do its little thing here。



![](img/fea183fa5643c97927caeb145f0717b8_3.png)

And it's setting things up， part of this is that there are hundreds of thousands of people using Python anywhere and it has to build you your own interface now。

The dollar sign prompt is traditionally the prompt that says it's waiting for input。

So I can type a command and then I can hit enter and it says that is not a good command。

There is a help， it's called man。Man LS that tells you， so that's the LS command。

 like what is in the LS command？And then it goes into a page。 Now。

 you'll notice that we're not scrolling here。 It pauses at the bottom。

 And I'm going to hit the Q key to get out of that。 Okay， so man is kind of like your help。

 And man stands for manual back in the days when you had big books。 right。

 You had these big books that were the manuals that you would reach up on your shelf and open it up。

 This is an online version of a great big book。 So the first thing in this class in particular that you have to learn how to do。

 And there's a whole assignment to set up your django environment with the right version of Python。

 And so I'm going to just。

![](img/fea183fa5643c97927caeb145f0717b8_5.png)

Activate what's called a virtual environment that I've already got set up。 The rest of these。

 many of these commands would work without that。 but here on Python anywhere， we tend to build that。

 and that's a separate assignment where you set that up。 So I'm going to do work on Django4。



![](img/fea183fa5643c97927caeb145f0717b8_7.png)

Okay， now that means when in the prompt， you see changes to say you're working in a Python virtual environment named Janjago4。

 The first thing you want to do to verify that things are working well is check the version by typing Python dash dash version。



![](img/fea183fa5643c97927caeb145f0717b8_9.png)

![](img/fea183fa5643c97927caeb145f0717b8_10.png)

And that tells you what version of Python at this point。

 you should be using a relatively high version of Python Python， say 3。8 or later。

 and then a relatively recent Django version。 and so this is my system and it's running Django。



![](img/fea183fa5643c97927caeb145f0717b8_12.png)

![](img/fea183fa5643c97927caeb145f0717b8_13.png)

Version 4。0。17。 I 4。0。7。 So that's just a typing command。

 And you'll notice I'm hitting the anarchy at the end of these things。 and then something happens。

 And so now I'm in my virtual environment。 and that's good。



![](img/fea183fa5643c97927caeb145f0717b8_15.png)

嗯。😊，And this talks about that。 So let's talk about some shell commands。



![](img/fea183fa5643c97927caeb145f0717b8_17.png)

So the first shell command is LS。 I showed you the man page for that。

 and that lists the current files in the current working directory。

LS minus L lists them with some detail， including the size and last modification date and the owner of the file。

 and that little D RW X stuff on the left。 Well， that's the permissions。 And there is R W X， R W X。

 R W X， and one is the permission that the owner would have fellow members of their group and then anyone。

 including anonymous users。 And so you notice that we have more permission。

 we have lots more permissions than。Than others。 So the next top command is PWD。

 PWD print working directory。And so what happens is Unix Linux is a multius system and our account name is DJ4E。

 and so slash home is where all the home directories are。

 and home DJ3 is the home directory for the user named DJ4E so CD。



![](img/fea183fa5643c97927caeb145f0717b8_19.png)

Is change directory。 Now， if you type CD by itself， you go back to your home directory。



![](img/fea183fa5643c97927caeb145f0717b8_21.png)

So if I go C D space Django project， Oh， and this is another thing。

 There is what's called command line completion。 So I know that I'm typing a directory here that exists。

 DJ A N tab， underscore， tab。 and then I don't have to know all the names。

 So you see that Django projects is one of my folders。 And if it's unique。It completes it for it。

 so as I'm hypping if I need to complete a file name or a folder name， I can use the tab key。

The other thing about this is if I do with PWD， you can see now I'm in home DJ for each Dgo projects and it's given me a context right I'm still in my home director。

 but I'm going down into folders and directories and files。Now， if I type the command CD。

It will go back to my home directory because now I'm down in a subdirecty。

And I do a PW and you see I'm back in my home directory。

Here's another trick that I really want you to learn。Up arrow， you can scroll up arrow， down arrow。

 up arrow， up arrow， up arrow。 I can scroll up to a previous command and then hit enter and then run it again。

 This will save you a bunch of time， okay。So I'm sitting in this folder。

 so let's go back and take a look at the other things I want to cover。



![](img/fea183fa5643c97927caeb145f0717b8_23.png)

You can use the Tild on a CD command。

![](img/fea183fa5643c97927caeb145f0717b8_25.png)

And you'll see that it's showing this Ted in the current prompt， CD Ted slashjango。Undersco projects。

 and that will go all the way up to the home directory and then work its way down。 So if you're like。

 where am I， you can say go to Tild slash and then then you know what that folder name is。Let's see。

 do I have any files here I can remove， let's go back into my home directory to an LS and see some files。

Db。zap， let's just get rid of it Rmdb。zap。Boop， it's gone。Now when we didn't put it in the trash can。

 we removed it。 It does it， so you'll notice that DBdos app is no longer in my list of files。

So be careful with the RM command。

![](img/fea183fa5643c97927caeb145f0717b8_27.png)

But it's quite powerful and useful。U。So there's grip command。Grep。



![](img/fea183fa5643c97927caeb145f0717b8_29.png)

Is searches all the files。 So if you look I've got lots and lots and lots of files。

 and so I'm going to say。

![](img/fea183fa5643c97927caeb145f0717b8_31.png)

Grp minus R。 that means recursive for a string autos create star in all my files。 Now。

 I got a lot of files here。 So this is going to be a long G。 but sometimes。

 and it works from the current working directory。 Let let me go into CD D E Django projects。



![](img/fea183fa5643c97927caeb145f0717b8_33.png)

And then let's go into let's see if credit， no， let's go into my ads。Chucklist。

 I think it might be called chlist。 Yeah， so this is my one of my， you know later we'll get this。

 but I'm going to run this grab command and it's going to find every example in every file in this folder and below。

Where the string autos underscore create exists， so that means G。

Minus star means recursively go deep and down the tree。

 Auto underscore creates whatever string you want to put in， and then star means all the files。

 but then it recursively goes through all the files。And so you will see， oh， I didn't have that。

 let's see autos create， let's look for the word I don't know， model。

Let's look for the word model in all of these files and below。 So there you go。

 So now I can see that。This is the file， some of these files like PiCash or junk。But， you know。

 let's see where I've got a model on my right there。Adds four。

 so it shows me the file name and the string。And usually what you're looking for is maybe a typographical error that you've seen in the may message。

 So that's the shell interface。 And again， part of what I'm going to want to show you is for you to know when you're talking to the shell because you're not always talking to the shell if it ends in a dollar sign prompt。

 usually you're talking to the shell。 so let's take a look at what it might look like in different situations。



![](img/fea183fa5643c97927caeb145f0717b8_35.png)

So sometimes you just run Python interactively and if you've taken a Python course， this is the。

Repple the reed， evaluate something loop。

![](img/fea183fa5643c97927caeb145f0717b8_37.png)

So you just type Python and it's running Python interactively now you're still sitting in a prompt。

Okay。And so now that's not the same thing。 That's not Linux talking to you。

 That's Python talking to you。 You're running the command Python on Linux。

 and that Python command is asking for input。 so it expects you to type Python。Hello world。

 of course we're going to type Hello world， and that reads the Python， parsees it。

 and then executes it。Now， if you're in this and you type LS， it's like I don't know what to do。

 I have no idea PwD， I have no idea what you're doing'ca you're not in the shell。

 so students come to me and go like I keep typing PWD and it's given me name errors like well。

 that's because you're in Python not in the shell。 so you have to know how to exit。

And you do that with quit open friend closeb enter and now you're back to the happy little dollar sign prompt and now you can say PWD and it will work right so part of it is recognizing what you're interacting with based on what the prompt looks like。

Okay， so that's the Python interface。

![](img/fea183fa5643c97927caeb145f0717b8_39.png)

Now， if you end up with a。More than one line Python statement that that the three Chevrons prompts turns into a dot dot dot。

 Let me show you how that works。 So I'm going to run Python again。 I'm just cursing up Python。



![](img/fea183fa5643c97927caeb145f0717b8_41.png)

And I can say four I in range。5。Coon， now you see that the prompt is turned into a dot， dot dot。

 and I have to do it in then， of course，1，2，3，4，5， print I。

And it's still thinking that I'm in this for loop。 and so it's saying are you still doing more stuff in the for loop。

 I could put another line in this for loop， I could say print。Second line。

And then I can hit the enter and say， I'm done with the forlo and then we'll actually read the for loop。

 Run the forlo， Ex it five times with I being 0，1，2，3，4。 But the body loop has two things。

 And then when it's done with this sort of continuation。 dot， dot， dot is like， more， I need more。

 I'm not done yet。 whatever you typed， it's not finished。Now I'm back to the standard Chevron prompt。

 at which case I would type quit。And now I'm back to the shell prompt， see。

 the whole idea is to be able to recognize like， don't get lost because it's asking youre not。

 you're talking to the wrong thing。

![](img/fea183fa5643c97927caeb145f0717b8_43.png)

Okay， so that's that's one thing now later we'll have you talking to your database and SQLI is one of the databases that we use。

 and so we can I'm going to go back into my home directory， CD， PWD。



![](img/fea183fa5643c97927caeb145f0717b8_45.png)

Ls。And so we see this file Db to SQLite 3， that is where Ssqueolite stores its data。

 so all the command is SQL I3。And then you give it as a parameter， the name of the file， Db。sQLite3。

 right？So that's going to read that。And now you see the prompt is changed to SQL light。Greater than。

And that's because I can't say LS here。Like what do you mean this also shows the continuation prompt because it expects commands to stop what？

Is happening to me。It just stays in this dot， dot， dot arrow。 and that's because。All S。

 Q L commands and in semicolon。 And so it's just like， I haven't seen a semicolon yet。

 So you must still be typing。 Now， it's like， oh， you just not only did you do semi I finally got a semicolon。

 but it's still terrible S Q L structured query language， okay。

So this SQLite or the dot dot dot arrow， right， that is SQLite or the SQLite continuation because that's what we're dealing with with the dot dot dot。

And a lot of students get confused when they see that dot dot dot arrow and then I'm like。

 just type a semicolon and they're like， yeah， I was just trying to get it to stop asking me stuff。

Okayay。But so that's not what you type。

![](img/fea183fa5643c97927caeb145f0717b8_47.png)

What we are going to type is a command， there's two kinds of commands。

 dot tables is one kind of command， the commands that start with dot are actually commands to SQL light。



![](img/fea183fa5643c97927caeb145f0717b8_49.png)

To itself， and that dot table says， what tables are in this database？Oh。

 and this one doesn't have any tables。So I'm going to get out of this one and go into a database that has tables because this is the one in my home directory。

 and so I'm going to say dot quit get out of this。

![](img/fea183fa5643c97927caeb145f0717b8_51.png)

![](img/fea183fa5643c97927caeb145f0717b8_52.png)

How do I get out， right， you'll notice I even had， I don't even remember what this is。

 so I'm going to go into Dgo projects。I'm going to go into my site。

Which is the place you're going to be working。 and I do an LS and you'll see that I got a DSQite here as well。

 It's a different one because。It is just a different one。

 I had one in my home directory now I got one two folders down in Janangle Project my site。

Id keep in tab and then Dv dot SQ light。 Now I'm going to say dot tables。

 and I'm going to have a bunch of tables。 Look at that。 I got a whole bunch of tables。

 And this is not exactly your code。 This is my code。 This is later in the semester。

But I can say select star from polls。To underscore choice。

Now that is an SQL command and you'll learn about that later， it does end in a semicle and it's got。

 you know select is one of the things I could type update， delete， you know。

 we'll learn a bit of SQL as the course progresses。Oh， I didn't type it right。 but watch。

 I'm going to use the up arrow key。 up arrow， back， back， back， back， back， back， back， back， back。

 back。Oh， for polls，2， choice， boom。 So that's the two lines that are in there。 And again， later。

 you will understand what that is。 And then to get out of this， I typed dotqui。

 which is different than the Python， which is quit open pre and close forn。

 So you got to remember that if you're in one of these things， youre you got to get out of that。



![](img/fea183fa5643c97927caeb145f0717b8_54.png)

Okay。So that's another thing。Then there is the Django shell and we'll use that later。

 and you can say， and so this has to work in a folder。



![](img/fea183fa5643c97927caeb145f0717b8_56.png)

That has the file managed dot pi in it。 And that's basically a Python project。

 And you have to run the managed dot pi。Python manage pi that says run the managed P file。

 and then I'm going to give it another command called shell。

 so that says load up managed dot PY and then drop me into a Django shell。

So you'll do a lot of things to say Python manageage P and like Python manageage Py check。

 which we check to see if there's something broken in our configuration for this application for this project and the answer is oh you're not broken so that's good。

 but I want to show you the shell because I'm trying to show you user interfaces that you might get stuck into and how to get out of those。

So now you notice that it looks exactly like the Python shell and I can type Python commands。

And you might say， O， what's the difference。 I can type print hellello world。

 and it says hellello world， I can say quit open print to close print。

But what's happened is Python has run managedage at Py and loaded your entirejango application into this Python instance。

 And so there are commands like， let me find a command here。



![](img/fea183fa5643c97927caeb145f0717b8_58.png)

Now， this is a Python statement。

![](img/fea183fa5643c97927caeb145f0717b8_60.png)

Now I think I got to change this in this particular thing to be poles to， for your， it'll be polls。

Yeah， so that ran a Python， but it imported a bunch of code from my Modeltop Pwifi again later in the course。

 okay？And then I can run a command to create an in memory model。



![](img/fea183fa5643c97927caeb145f0717b8_62.png)

To create a brand new question in this model。

![](img/fea183fa5643c97927caeb145f0717b8_64.png)

Oops， it didn't mean to do the quit。And so that actually， I mean， we can print Q。

To see what's in queue。Yeah， it's a question and it's got the text of hellello world in we could save it。

 and so there are things you can do in the Django shell that you can't do in the Python shell。

 but it's a Python shell plots a bunch of preloaded django stuff。

So you might have a continuation line， but then you leave by quit open print， close print。

 and now we're back to the Linux command prompt because there's a dollar sign there。



![](img/fea183fa5643c97927caeb145f0717b8_66.png)

LS minus L PwD， all that Linux stuff is working。 And so that's basically my quick introduction。

 Again， you know， you'll learn all this as we go。 There's a lot more to it。

And we'll give you each of these commands， you'll have whole sets of commands to do。

 and I just wanted you at this beginning to get a kind of a picture of what's going on in the command line interface。

 okay， cheers。

![](img/fea183fa5643c97927caeb145f0717b8_68.png)