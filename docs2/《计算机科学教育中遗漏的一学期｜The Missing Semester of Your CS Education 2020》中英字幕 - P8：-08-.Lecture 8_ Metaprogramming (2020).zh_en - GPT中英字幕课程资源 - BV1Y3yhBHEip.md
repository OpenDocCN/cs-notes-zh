# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P8：-08-.Lecture 8_ Metaprogramming (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

All right， everyone。 let's get started with the next lecture。

 So today we're gonna tackle the topic of meta programming。 And this title is a little weird。

 It's not entirely clear what we mean by meta programming。

 we couldn't really come up with a better name for this lecture。

 because this lecture is about the processes that surround the work that you do when working with software。

 It is not about programming itself necessarily， but about the process。

 This can be things like how your system is built， how it's tested。

 how you add dependencies to your software。 That sort of stuff that becomes really relevant when you build larger pieces of software。

 but they're not really programming in and of themselves。😊。

So the first thing we're gonna to talk about in this lecture is the notion of build systems。

 So how many of you have used a build system before or know what it is。Okay， so about half of you。

 So for the rest of you， the central idea behind a build system is that you're writing a paper。

 you're writing software， you're like working on a class， whatever it might be。

 And you have a bunch of commands that you've like either written down in your shell history or you wrote them down into a document somewhere that。

 you know， you have to run if you want to do a particular thing。 So for example。

 like there are a sequence of commands that you need to run in order to build your paper or build your thesis or just to run the tests for whatever class you're currently in。

 And a build system sort of idea is that you want to encode these rules for what commands to run in order to build particular targets into a tool that can do it for you。

And in particular， you're going to teach this tool about the dependency between those different artifacts that you might build。

There are a lot of different types of tools of this kind。

 and many of them are built for particular purposes， particular languages。

 Some of them are built for building like papers。 Some of them are built for building software。

 Some of them are built for particular programming languages like Java or some。

 some tools even have built in tools for， for build。 So NP PMM， for example。

 you might be aware if you've done no G S development has a bunch of built in tools for doing tracking of dependencies and building them and building all of the dependent stuff of your software。

But more generally， these are known as build systems。 And at their core。

 they all function in a very similar way。 And that is， you have a number of targets。

 These are the things that you want to build。 These are things like paper dot P， DF。

But they can also be more abstract things like run the test suite or build the binary for this program。

 Then you have a bunch of dependencies， and dependencies are things that need to be built in order for this thing to be built。

And then you have rules that define how do you go from a complete list of dependencies to the given target。

 So an example of this might be in order to build my paper dot P D F。

 I need a bunch of like plot images that are gonna go into the paper。 So they need to be built。

 But then once they have been built， How do I construct the paper， given those files。

 So that is what a rule is。 It's a sequence of commands you run to get from one to the other。

How you encode these rules differs between different tools in this particular class。

 We're gonna focus on a tool called make。 Make is a tool that you will find on almost any system that you log in today。

 Like it'll be on Mac O S。 It'll be on basically every Linux and BSD system。

 And you can pretty easily get it on Windows。 It's not great for very complex software。

 But it works really well for anything that's sort of simple to medium complexity。Now。

 when you run make， make is just a command， you can run on the command line。

 And when you type make and this is an empty directory。 if I type make。

 it just has no target specified and no make file found stop。

And so it helpful tells you that it stopped running。

 but also it tells you that no make file was found。

 Make will look for a file literally called make file in the current directory。

 And that is where you encode these targets dependencies and rules。 So let's try to write one。

 Let's imagine that I'm writing this hypothetical paper。 And so I'm gonna make a make file。

 And then this make file。 I'm gonna say that my paper do P D F depends on。

 that's what the colon here indicates paper dot text。

 This is gonna be late file and plot data dot P And G。😊。

And the command in order to build this is going to be PDF latex of paper dot text。

So for those of you who are not familiar with this particular way of building documents。

 lateek is a really handy programming language for documents。 It's a really ugly language。

 And it's a pain to work with。 But it produces pretty nice documents。

 And the tool you use to go from a tech file to P F is P F latex。

 And here I'm saying that I also depend on this plot plot data P And G。

 that's gonna be included in my document。 And what I'm really saying here is if either of those two dependencies change。

 I want you to build paper， P D F。They both need to be present， and should they ever change。

 I want you to rebuild it。But I haven't really told it how to generate this plot data P And G。

 So I might want to rule for that as well。 So I'm going to define another target here。

 and it's gonna be， it's gonna to look like this。 plot dash percent with percent means and make is any string sort of a wild card pattern。

 But the cool thing is you repeat this pattern in the dependencies。

 So I can say that plot dash percent dot P And G is going to depend on percent dot data or debt。

 That is a common sort of suffix for data files。😊，And it's also going to depend on some script that's going to actually plot this for me。

 And the rules for to go from one to the other。 These can be multiple lines。

 But in my particular case， theyre just one line。 And I'm going to explain what this is in a little second。

呃。Alright， so here we're going to say that in order to go from a wildcard dot dot file that matches the wildcard in the target and a plot dot Python file run the Python file with dashi。

 which is going be like the way we mark what the input is in our Python file。

 I'll show it to you later， Do star is a special variable that is defined for you and make file rules that matches whatever the percentile was。

So if I do plot dash food dot P And G， then it's gonna look for food dot that and a dollar star is gonna expand to F。

 So this will produce the same file name as the one we matched here。

 And dollar at is a special variable that means the name of the target。So the output file。

And hopefully， what plot PY will do is it will take whatever the data is here。

 It will produce a P And G somehow， and it will write it into the file indicated by the dollar ad。

Right。So now we have a make fileile， Let's see what happens if the only file in this directory is the make file and we run make。

What says no rule to make target paper dot text needed by paper dot P D F stop。

 So what it's saying here is。First of all， it looked at the first rule of our file， the first target。

 And when you give make no arguments， it tries to build whatever the first target is。

 This is known as the default goal。 So in this case， it tried to help build paper dot P F for us。

 And then it looked at the dependencies。 And it said， well， in order to build paper do P D F。

 I need paper dot text。 and I need this P And G file。 And I can't find paper do text。

 and I don't have a rule for generating paper dot text。 And therefore， I'm gonna exit。

 This is nothing more I can do。嗯。So let's try to make some files here。

 let's just make like an empty paper dot text。And then type make。

 So now it says no rule to make target plot data all P And G needed by paperto P F， right。

 So now it's， it knows that it has one dependency， but it doesn't know how to get the other one。

 It knows that there's a target that matches， but it can't actually find its dependencies。

 And so it ends up doing nothing at all。It still， still needs us to generate this P G for or the input for the PN G。

So let's actually put some useful stuff into these files。 Let's say that。Luckily。

 I have one from earlier。Ploott PI to here。So that's look at what this text file is。

 This is what text looks like。 It's not very pretty。 but basically， I'm defining an empty document。

 I'm going to include graphics， which is the way you include a an image file。

 I'm going to include plot data dot P And G。 And this is， of course。

 why we want a dependency of paper dot P F to be the P And G file。

Ploot PY is also not very interesting， it just imports a bunch of libraries。

 it parses the dash I and dash O arguments， it loads data from the dash I argument。

 it uses library called Matpllootlib which is very handy for just quickly plotting data and it's just going to plot the first column of the data as x's and the second column of the data as ys。

 so we're just going to have a data file that's two columns x and y on every line and then it saves that as a figure into whatever the given dash O value is。

Okay， so we need a data file。 It's going be data dot dot because we want plot dash data dot P And G。

 And our rules said that the way you go from that pattern to the dot file。

 the dot thatt file is just by whatever follows plot。 So if we want plot dash data。

 then we want data dot thatt。 And then this file， we're just gonna put in some linear coordinates。

 because why not？ That's not linear。

![](img/7d0968740d56bc45d228becba11f1261_1.png)

All right。And now what happens if you're on make。Well。Oh。Okay。

 so what just happened We'll make first run。Ploot P Y with the correct files to generate the the PN G file。

 And then it ran P F late paper dot text。 And all the stuff we see below is just the output from that tool。

 If we wanted to， we could silence the output from this tool so we don't have to like have it mess with all our output。

 But in general， you notice that it ran the two commands。

 And it ran them perhaps unsurprisingly in the right order。

And if we now do LS in the current directory， we see that we have a bunch of files that were generated by PDF lateEC。

 but in particular we have the P& G file which was generated and we have the paper dot PDF and if we open the paper。

 PDF file。We see that it has one image which has a straight line。Perhaps in and of itself。

 not a very surprising or interesting result。 But where this gets really handy is I can do things like if I type make again。



![](img/7d0968740d56bc45d228becba11f1261_3.png)

Maker says paper do P F is up to date。 It does no work。Whenever you runMake。

 it tries to do the minimal amount of work in order to produce whatever you ask it to produce。

In this case， none of the dependencies have changed。

 so there's no reason to rebuild the paper or to rebuild the plot。If I now， let's say。

 I'm going to edit。Paper dot text， and I'm going to add hello here。



![](img/7d0968740d56bc45d228becba11f1261_5.png)

And our make， then if we scroll up， we'll see it didn't run plot。

 PY again because it didn't need to not know the dependencies change。

 but it did run PDF lateek again， and indeed if we open the paper， analysis us hello over there。

On the other hand， if I were to change， say the data file and make this point8。An hour on make。

Then now it plots again because the data changed and it regenerates the PDF because the plot changed。

And indeed， the paper turns out the way we expected it to。



![](img/7d0968740d56bc45d228becba11f1261_7.png)

So that's not to say that this particular pipeline is very interesting because it's not。

 It's only true very straightforward targets and rules。

 but this can come in really handy when you start building larger pieces of software。

 where there might be dependencies， you might even imagine that if you're writing a paper。

 one of your targets might be producing this data file in the first place。 right。

 So one of the make file targets might be run my experiment right。

 Run my benchmark and stick the the data points that come out into this file and then plot the results and then and then and then。

 and then all the way until you end up with the final paper。😊，And what's nice about this is。

 first of all， you don't have to remember all the command to run。

 You don't have to write them down anywhere。 but also。

 the tool takes care of doing the minimal amount of work needed。

Often you'll find things like therell be there'll be subcoms to make like make tests， right。

 which is going to compile your entire piece of software and also run the tests。

 There might be things like make release， which builds it with optimizations turned on and creates a tarball and uploads that somewhere right So it's going to do the whole pipeline for you。

 The idea is to reduce the effort that you have to do as any part of your build process。😊，嗯。Now。

 what we saw here was a very straightforward example of dependencies right So we saw here that you could declare files as dependencies。

 but you also want to declare sort of transitive dependencies， right I depend on this thing。

 which is generated by this other target。😊，Very often when you work with dependencies in the in the larger area of software。

 you'll find that your your system ends up having many different types of dependencies。

 Some of these are files like we saw here。 Some of them are programs。

 right like this sort of implicitly depends on Python being installed on my machine。

 Some of it might be libraries， right， you might depend on something like Macpllib。

 which we depend on here。 Some of them might be system libraries like open SSL or open SS H。

 or like low levelvel crypto libraries。And you don't necessarily declare all of them。 Very often。

 there's sort of an assumption about what is installed on the given system。

What you'll find is that for most places where you have dependencies。

 there are tools for managing those dependencies for you。 And very often。

 these systems you might depend on are stored in what are known as repositories。

 So repository is just a collection of things usually related that you can install。

 That's basically all the repositories。 and you might be familiar with some of them are ready， right。

 So some examples of repositories are pie pie， which is a wellknow repository for Python packages。

 Ruby gems， which is similar for Ruby crates I O for rust NPM for node Js。

 But other things the repositories， too， right， like the repositories for cryptographic keys like Keybase。

😊，There are repositories for system installed packages。

 like if you've ever used the a tool in Uunntu or in Deian。

 you are interacting with a package repository where people who have written like programs and libraries upload them so that you can then install them。

Similarly， you might have repositories that are entirely open， right， So the Ubutu repositories。

 for example， are usually provided by Ubuntu developers， but in arch Linux。

 there there is something called the arch user repository where users can just share their own their own libraries and their own packages themselves。

 Very often repositories are either sort of managed or they are just entirely open。

 And you should often be aware of this， because if you're using an entirely open repository。

 maybe the security guarantees you get from that or less than what you get in a controlled repository。

One thing you'll notice if you start using repositories is a very often software is versioned。

And what I mean by version。 Well， you might have seen this for stuff like browsers， right。

 where there might be something like starting like。Chrome version 64 dot0 dot 2，0，1，90，324， right？

This is a version number。 It might。 there's a dot here。嗯。This is one kind of version number。

 But sometimes if you start， I don't know， like Photoshop or you start any other tool。

 there might be other kind of versions that are like 8 dot 1 dot 7。Right。

 and these version numbers are usually numerical， but not always。 Sometimes they have hashes in them。

 for example， to refer to Git commits。 But you might wonder， why do we have these。

 Why is it even important that you add a number to software that you release。

The primary reason for this is because it enables me to know whether my software will break。

Imagine that I have a dependency on a library that Jose has written。Right。

 and Jose is constantly doing changes to his library because he wants to make it better。

 And he decides that one of the functions that his library exposes has a bad name。 So he renames it。

My software suddenly stops working。Right，Because I， my library calls a function on Jose's library。

 but that function no longer exists depending on which version people have installed the Jose library。

Versions help solve this because I can say， I depend on this version of Jose's library。

 And then there has to be some rules around what is Jose allowed to do within a given version。

If he makes a change that I can no longer rely on， his version has to change in some way。

There are many thoughts on exactly how this should work。

 Like what are the rules for publishing new versions， How do they change the version numbers。

 Some of them are just dictated by time。 So， for example， if you look at browsers。

 they very often have time versions that look like this。 They have a version number on the far left。

 That's just like which release。 And then they have sort of an incremental number that is usually0。

 And then they have a date at the end。Right， so this is March 24，2019， for some reason。

 And usually that will indicate that this is。Version 64 of Firefox from the state。

And then if they release sort of patches or hot fixes for security bugs。

 they might increment the date to keep the version at the， at the left the same。嗯。

And people have strong， strong opinions on exactly what the scheme should be。

 And you sort of depend on knowing what schemes other people use， right。

 If I don't know what scheme Jose is using for changing his versions。

 maybe I just have to say you have to run like 8，1，7 of of Jose's software。 Otherwise。

 I cannot build my software。 But this is a problem， too。 right。

 Imagine that Jose is a responsible developer of his library。 And he finds a security bug。

 And he fixes it。But it doesn't change the external interface tos library。 No functions change。

 no types change。 Then I want people to be building my software with his new version。

And it just so happens that building mind works just fine with this new version。

 because that particular version didn't change anything I depended on。

So one attempted solution to this is something called semantic versioning。 So in semantic versioning。

 we give each of the numbers separated by dots and a version number， a particular meaning。

 And we give a contract for when you have to implement the different numbers。In particular。

 in semantic versioning。We call this。The major version。We call this。The minor version。

And we call this the patch version。And the rules around this are as follows。

If you make a change to whatever your software is and。

 and the change you made is entirely backwards compatible。Right， like， it does not add anything。

 It does not remove anything。 It does not rename anything。Externally， it is as if nothing changed。

Then you only increment the patch number， Nothing else。 So usually security fixes， for example。

 will increment the patch number。If you add something to your library。

 I'm just gonna call them libraries because usually libraries are the things where this matters。

 So for a library， if you add something to the library。

 you increment the minor version and you set the patch to 0。So in this case。

 if we were to do a minor release， the next minor release version number would be 8，2，0。

And the reason we do this is because I might have a dependency on a feature that Jose added in a 2，0。

Which means you can't build my software with 8，1，7。 That would not be okay， even though if you。

 if Id written it towards 8，1，7， you could run it with  a 2，0。

 the reverse is not true because it might not have been added yet。And then finally。

 the major version， you increment if you make a backwards incompatible change。

 where if my software used to work with whatever version you had。

 and then you make a change that means that my software might no longer work。

 such as removing a function or renaming it。 Then you increment the major version and set minor and patch to 0。

 So the next major version here would be 9，0，0。😊，Taken together。

 these allow us to do really nice things when setting what our dependencies are。 in particular。

 if I depend on a particular version of someone's library。

 rather than saying it has to be exactly this version。

 What I'm really saying is it has to be the same major version。And at least the same minor version。

 and the patch can be whatever。This means that if I have a dependency on Jose software。

Then any later release that is still within the same major is fine。That includes， keep in mind。

 an earlier version， assuming that the minor is the same。

Imagine that you are on some older computer that has like version 81，3。 In theory。

 my software were just fine with 813 as well。It might have whatever bug the Jose fixed in between。

 like whatever security issue。 But this has the nice property。

 that now you can share dependencies between many different pieces of software in your machine。

 If you have version 8，3，0 installed， and there are a bunch of different software that like  one requires 8。

1，7，1 requires 8，2，4。1 requires 8，0，1， all of them can use the same version of that dependencies。

 you only need it installed once。😊，One of the most common or one of the most familiar。

 perhaps examples of this kind of semantic versioning is if you look at the Python versioning。

So many of you may have come across this where Python 3 and Python 2 are not compatible with one another。

 They're not backwards compatible。 If you write code in Python 2， and you try to run it in Python 3。

 it might not work。 There are some cases where it will。

 but that is more accidental than anything else。And Python actually follows semantic versioning。

 at least mostly。 And so if you write software that runs on Python 3。5。

 then it should also work in 3。6，3。7，3。8。It will not necessarily work in Python 4。

 although that will hopefully be a long time away。But if you write code for Python 3。5。

 it will possibly not run on Python 3。4。😡，So one thing you will see many software projects do is they try to bring the version requirements they have as low as possible。

If you can depend on major and then minor and patch 0，0。

 that is the best possible dependency you can have because it is completely liberal as to which version of that major you're depending on。

Sometimes this is hard， right。 Sometimes you genuinely need a feature that was added。

 But the lower you can get， the better it is for those who want to depend on your software， in turn。

 when working with these sort of dependency management systems or with versioning in general。

 you'll often come across this notion of lock files。 You might have seen this where， like。

 you try to do something。 and it says， like cannot reconcile versions or you get an error like lock file already exists。

 These are often somewhat different topics。 But in general。

 the notion of a lock file is to make sure that you don't accidentally update something。

The log file at its core is really just a list of your dependencies and which version of them you are currently using。

Right， so my version string might be 8，1，7， and the latest version。

 like on the Internet somewhere might be 8，3，0。But whatever is installed in my system is not necessarily one of those two。

 It might be like 8，2，4 or something like that。And the log file will then say dependency Jose。

 version a24。And the reason you want a lock file， there can be many。

 One of them is that you might want your builds to be fast。

If every single time you tried to build your project。😡，Whatever tool you were using。

 downloaded the latest version and then compiled it and then compile your thing。

 you might wait for a really long time each time， depending on the release cycle of your dependencies。

If you use a lock file， then the version， unless you've updated the version in your log file。

 it'll just use whatever it built previously for that dependency and your sort of development cycle can be a lot faster。

Another reason to use log files is to get reproducible builds。

 Imagine that I produce some kind of security related software。

 and I very carefully audited my dependencies， and I produce like a signed binary of like。

 here is this like a sworn statement for me that this version is secure。😊。

If I didn't include a lock file， then by the time someone else installs my program。

 they might get a later version of the dependency。 and maybe that later version has like been hacked somehow or just has some other security vulnerability that I haven't had a chance to look at yet。

Right， and a log file basically allows me to freeze the ecosystem as of this version that I have checked。

The extreme version of this is something called vendoring。 When you vendor your dependencies。

 it really just mean you copy pasteed them。Ventoring means take whatever dependency you care about and copy it into your project。

😡，Because that way， you are entirely sure that you will get that version of that dependency。

 It also means that you can like make modifications to it on your own。

 but it has the downsides that now you no longer get these benefits of versioning， right。

 you no longer have the advantage that if there are newer releases of that software。

 your users might get them automatically， like， for example， when Jose fixes his security issues。

 Not that he has any， of course。嗯。One thing you'll notice is that when talking about this。

 I've been talking about sort of bigger processes around your systems。 These are things like testing。

 They things like checking your dependency versions。

 There are also things like just setting up build systems。 And often。

 you don't just want a local build system。 You want to build process that includes other types of systems。

 or you want them to run。 even when your computer is not necessarily on。

And this is why as you start working on larger and larger projects。

 you will see people use this idea of continuous integration。And continuous integration systems are。

Essentially， a cloud build system。 The idea is that you have your project stored on the Internet somewhere。

 and you have set it up with some kind of service that is running an ongoing thing for your project。

 whatever it might be。 and continuous integration can be all sorts of stuff。

 It can be stuff like releasing your library to pipe pie automatically。

 whenever you push to a particular branch， it could be things like run your test suite whenever someone submits a pull request。

 or it could be check your code style， every time you commit。

There are all sorts of things you can do with continuous integration。

 and the easiest way to think about them is that they're sort of event triggered actions。

So whenever a particular event happens for your repository， for your project。

 a particular action takes place where the action is usually some kind of script。

 Some sequence of programs are gonna be invoked， and they're gonna do something。

This is really an umbrella term that encapsulate a lot of different types of services。

 So some continuous integration services are very general。

 Things like Travis C I or Azure pipelines or Github actions or all very broad C I platforms。

 They're built to let you write what you want to happen。 whenever any event that you define happens。

 very broad systems。There are also more specialized systems that deal with things like。

Continuous integration， coverage testing。 So like， annotate your code and show。

 you have no test that test this piece of code， and they're built only for that purpose。

 or they're built only for testing browser based libraries or something like that。And so often。

 you can find C I tools that are built for the particular project you're working on。

 or you can use one of these broader providers。 And one thing that's nice is that many of them are actually free。

 especially for open source software。 Or if you're a student。

 you can often get them for free as well。😊，In general。

 the way you use the CI system is that you add a file to your repository and this file is often known as a recipe and what the recipe specifies is this sort of dependency cycle again。

 sort of what we saw with make files。It's not quite the same。

 The events instead of being files might be something like when someone pushes a commit or when a commit contains a particular message or when someone submits a pull request or continuously right？

 One example of a continuous integration service that's not tied to any particular change to your code is something called the depend bot you can find this on Github and the depend bot is something that you hook up to your your repository and it will just scan whether there are newer versions available of your dependencies that you're not using。

So， for example， if I was depending on 8，1，7 and I had a lock file that locked it to 8，2，4。

 and then 8，3，0 is released。 The depend about will go。

 you should update your log file and then submit a pull request to your repository with that update。

This is a continuous integration service that's not tied to me changing everything。

 but to the ecosystem at large changing。Often， these C I systems integrate back into your project as well。

 So very often， these C I services will provide things like little badges。 So let me give an example。

So for example。Here's a project I worked on recently that has continuous integration set up。

So this project， you'll notice it's readme。If I can zoom in here without。Crombing o。O。

 that's much larger than I wanted here。 you'll see that at the top of the repositories page。

 there are a bunch of these badges， and they display various various types of information。

 You'll notice that I have a depend about running So the dependencies are currently up to date。

 It tells me about whether the test suite is currently passing on the master branch。

 It tells me how much of the code is coverage by tests。

 And it tells me what is the latest version of this library and what is the latest version of the documentation of the library that's available online。

😊，And all of these are managed by various continuous continuous integration services。

Another example that some of you might find useful or might even be familiar with is the notion of Github pages。

 So Github pages is a really nice service the Github provides。

 which lets you set up a C I action that。😊，Builds your repository as a blog essentially it runs a static site generator called Jekyll and Jekyll just takes a bunch of markdown files and then produces a complete website。

And then as a part of Gitthub pages， they will also upload that to GitHub servers and make it available at a particular domain。

And this is actually how the class website works。Cost website is not a bunch of like H M L pages that we manage。

 Instead， there's a repository。Missing semester。So if you look at the missing semester。Repository。

You will see if I zoom out a little here。嗯。That this just has a bunch of markdown vials。

 right It has。 let's look at 2020。Meta programming dot M D。 So this is the， if I go to raw here。

 this is the raw markdown for today's lecture。So this is the way that I write the lecture nodes。

 And then I commit that to the repository we have， and I push it。 And whenever a push happens。

 the Github pages C I is going run the build script for Github pages and produces the website for our class without me having to do any additional steps to make that happen。

😊。

![](img/7d0968740d56bc45d228becba11f1261_9.png)

And so， yes， sorry good。Changing the markdown file to an ACML file。 Yeah， so， so Jekyll。

 it's using a tool called Jell， which is a tool that takes a directory structure that contains markdown files and produces a website。

 It produces like HL files And then as a part of the action。

 it takes those files and uploads them to Github servers add a particular domain。

 And usually that's a domain under like Github dot I O that they control。

 And then I have set missing semester to point to the Github domain。😊，嗯。

I want to give you one aside on testing because it's something that many of you may be familiar with from before。

 you have a rough idea of what testing is。 you've like run a test before， you've seen a test fail。

 you know， like the basics of it or maybe you've never seen a test fail in which case。

 congratulations。But as you， as you get to more advanced projects， though。

 you'll find that people have a lot of terminology around testing。

 And testing is a pretty like deep subject that you could spend many。

 many hours trying to understand the ins of。 And I'm not gonna go through it in excruciating detail。

 But there are a couple of words that I think it's useful to know what mean。

And the first of these is a test suite。 So a test suite is a very straightforward name for all of the tests in a program。

 It's really just a suite of tests。 It's a large collection of tests that usually are run as a unit。

😊，嗯。And there are different types of tests that often make up a test suite。

The first of these is what's known as a unit test。 A unit test is a often usually fairly small test of self contained tests that tests a single feature。

What exactly a feature might mean is a little bit up to the project。

 but the idea is that it should be sort of a micro test that only tests a very particular thing。

Then you have the larger tests that are known integration tests。

 integrationegration tests try to test the interaction between different subs systemsstems of a program。

So this might be something like an example of a unit test might be if you're writing an H parser to the unit test might be test that it can parse an H L tag。

An integration test might be， here's an H document， pars it。

So that is going to be the integration of multiple of the subsystems of the parser。

You also have a notion of regression tests。 Reion tests are tests that test things that were broken in the past。

So imagine that someone submits some kind of issue to you and says your library breaks if I give it a。

Marquis tag。And that makes you sad。 So you want to fix it。

 So you fix your parser to now support moreque tags。

But then you want to add a test to your test suite， the checks that you can parse by key tags。

The reason for this is so that in the future， you don't accidentally reintroduce that bug。

So that is what regression tests are for。 And over time。

 your project is going to build up more and more of these。

 and they're nice because they prevent your project from regressing to earlier bugs。

The last one I want to mention is a concept called mocking。

 So mocking is the idea of being able to replace parts of your system with a sort of dummy version of itself。

That behaves in a way that you control。 A common example of this is you're writing something that does。

 Oh， I don't know。File copying over SH。This is a tool that you've written that is file copying over Ss H。

There are many things you might want to mock here。 For example， when running your test suite。

 you probably don't actually care that there's a network there， right。

 You don't need to have to like set up TCP ports and stuff。 So instead。

 you're going mock the network。The way this usually works is that somewhere in your library。

 you have something that like opens connection or reads from the connection or writes to the connection。

 and you're gonna overwrite those functions internally in your library。

 with functions that you've written just for the purposes of testing where the read function just like returns the data And the write function just drops the data on the floor or something like that。

 Similarlyly， you can write a mocking function for the SH functionality You could write something that does not actually do encryption。

 It doesn't talk to the network。 It just like takes bytes in here and just magically。

 they pop out the other side。 and you can ignore everything that's between because for the purposes of copying a file。

 you just wanted to test that functionality。 The stuff below doesn't matter for that test。

 And you might mock it away。😊，Usually in any given language。

 there are tools that let you build these kind of mocking abstractions pretty easily。

That is the end of what I wanted to talk about meta programming。 But this is a very。

 very broad subject。 things like continuous integration， build systems。

 There are so many out there that can let you do so many interesting things with your project。

 So I highly recommend that you start looking into it a little。 The exercises are。😊。

Sort of all over the place。 And I mean that in a good way。

 They're intended to try to just show you the kind of possibilities that exist for build working with these kind of processes。

 So， for example， the last exercise has you write one of these continuous integration actions yourself。

Where you decide what the event be and you decide what the action be， but try to actually build one。

And this can be something that you might find useful in your project。

 The example I give in the exercises is try to build an action that runs like right good or pro slint。

 one of thelins we for the English language on your repository。😊，And if you do， like。

 we could enable that for the class repository so that our lecture notes are actually well written。

 right？ And this is one other thing that's nice about this kind of continuous integration testing is that。

😊，You can collaborate between projects。 If you write 1， I can use it in my project。

 And that's a really handy feature where you can build this ecosystem of improving everything。

Any questions about any of the stuff we occur today， yep。In my experience。

 it often I make along with CMake and they like do different parts of building on program。I there。叫位。

Min to talk about sure。plays with make So， so the question is， why do we have both make and See make。

 What do they do and is there a reason for them to talk together。So， so C make。

I don't actually know what the tagline for CMake is anymore。

 but it's sort of like a better make for C as the name implies。

 CMake generally understands the layout of C project， a little bit better than make files do。

 They're sort of built to try to parse out what the structure of your dependencies are。

 what the rules from going to one to the other is it also integrates a little bit nicer with things like system libraries。

 So CMake can do things like detect， whether given libraries available on your computer or if it's available at multiple different paths。

 It tries to find which of those path it's present on on this system and then link it appropriately。

 So CMake is a little bit smarter than make is。 make。😊。

Will only do whatever you put in the make file。 Not entirely true。

 There are things called implicit rules that are like built in rules in make。

 but they're pretty dumb whereas Cm tries to build be a larger build system that is opinionated by default to work for C projects。

Similarly， there's a tool called Maven。 So Maven and Ant， which is another project。

 They are both built for Java projects。 They understand how Java code interacts with one another。

 how you structure Java programs。 And they're built for that task。 very often。

 at least when I use make。 I use make sort of at the top。

And then make my call other tools that build whatever subsystem they know how to build。

 right Like my make file might call cargo to build a rust program and then call C make to build some like see dependency of that。

 But then at the top， like， I'm gonna do some stuff at the end after those programs of built。

 And that might just be like run a benchmark， which is in the rust code and then like plot it using the C code or something like that。

 right， So for me， make is sort of the glue at the top that I might write。 Usually。

 if your make file gets very large， there's a better tool。😊，What you'll find like big companies。

 for example， is they often have one build system that manages all of their software。

 So if you look at Google， for example， they have this open source system called basil。

 and I don't think Google literally uses basil inside of Google。

 but it's sort of based on what they use internally。

 and it really just it's intended to manage the entire build of everything Google has。

 And basil in particular， is built to be， I think they call it like a polyglot build framework。

 So the idea is that it works for many different languages。

's like an there's a module for basil for this language and that language in that language。

 but they all integrate with the same basil framework。

 which then knows how to integrate dependencies between different libraries and different languages。

Do you have a question you back to when you were doing something？A little bit harder。

Expressions like where you got them。Sure， so when you say expressions。

 you mean the things in this file。 or yeah。 So these is it its own language way to。

So make files are their own language。 They are it's a。Pretty weird language。

 Like it has a lot of weird exceptions。 In many ways， it's weird， just like bash is weird。

 but in different ways， which is even worse。 Like when you're writing a make file， you sort of。

You can sort of think like you're writing bash， but you're not because it's broken in different ways。

 but it is its own language。 And the way that make falls are generally structured。

Is that you have a sequence of， I think they call them directives。 So every like the this thing。

 oops， this thing is a directive and this is a directive。

 and every directive has a colon somewhere and everything to the left of the colon is a target and everything to the right of the colon。

 I guess right of the colon is a dependency。And then all of the lines below that line are the sequence of operations known as the rules for once you have the dependencies。

 How do you build these targets， Notice that make is very particular that you must use a tab to indent the rules。

If you do not， make will not work。They must be tabs。 They cannot be4 or8 spaces， must be tabs。

 And like， you can have multiple operations here。 right like I can do He go hello or whatever。

 And then they would first run this and then run this。



![](img/7d0968740d56bc45d228becba11f1261_11.png)

There there's an exercise for today's lecture that has you try to extend this make fall with a couple of other targets that you might find interesting that goes into a little bit more detail。

There's also some ability to execute external commands to like determine what the dependencies might be if your dependencies are not like a static list of files。

 but it's a little limited。 Usually once you start needing that sort of stuff。

 you might want to move to a more advanced build system。

we have two dependencies and both of them depend on a common library， but they have conflict me over。

Yeah， so the question is， what happens if I have？嗯。Let's say that I have library A and library B。

And they both depend on library C。But library A depends on like。4 dot 0 dot1。

 and library B depends on3 dot。4 dot 7。So they both depend on C。 And so ideally。

 we'd like to reuse C， but they depend on different major versions of C。 What do we do。

What happens in this case depends entirely on the system that you're using。

 the language that you're using。 In some cases， the tool will just be like， well， I'll just pick 4。

 which sort of implies that they're not really using semantic versioning。 In some cases。

 the tool will say this is not possible。 Like if you do this， it's an error。

 And the tool will tell you you either need to upgrade B， like have B using a new version of of C。

 or you need to downgrade A。 You do not get to do this。 and compilation will fail。

 Some tools are gonna build two versions of C。And then like when it builds A。

 it will use the major four version of C。 and when it builds B。

 it will use the major three version of C。One thing you end up with is really weird conditions here where like。

 if C has dependencies， then now you have to build all of C's dependencies twice 2。

1 for3 and one for4。And maybe they share， and maybe they don't。

You can end up in particularly weird situations。 if imagine that the library see like。呃。Imagine that。

Library C like writes to a file。Like write to some like file on disk， some cash stuff。

If you run your application now and like A does something to call like C dot save and B does something like C dot load。

 then suddenly your your application at the bottom is not gonna to work because the format is different right。

 So these situations are often very problematic。 And。

 and most tools that support semantic versioning will reject this kind of configuration for exactly that reason。

 that it's so easy to shoot yourself in the flu。All right。

 we will see you again tomorrow for security。 Keep in mind again， if you haven't done the survey。

 the question I care the most about in the survey is what you would like us to cover in the last two lectures So the last two lectures are for you to choose what you want us to talk about and to give any questions you want us to answer so please like add that if you can and that's it see you tomorrow。

