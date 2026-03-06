# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p08 P8 Programming environment： Building, testing, and debugging (COP-3402 Fall 2024 -BV1v6vdBKEHB_p8-

All right， so welcome back to System softwareware。Today we're going to be talking about building and a little on testing if debugging。

So for homework last time， I hope everyone read the book。

Because it's a pretty lightweight read who read the book。对。

What you think so what's some things you learned about C that you didn't know before， yeah？ポいつこ。Yeah。

 I mean， GDPB is one of the original or one of the earlier debugging tools and you know if you ever use an IDE and it has integrated debugging for you。

The same idea， yeah。終われた。one years。I require incorporate your body。氷りがある。嫌だらさせ。

I don like we it out there。important。Sure， yeah， so stuff yeah， gives a history of C。

And notice that the first several chapters of this book， even though it's a C programming book。

 there's no C involved， it's all about setting up your environment， doing building and testing。

 and so I hope you'll read at least the testing section so you can see some of the tools that are available for you to help you do testing so you don't have to use kind of ad hoc。

Rewrite the same file， lose all your tests there' are some really simple things you can do to dramatically improve the ease of programming and today we're going to go over make fileses especially in a little bit on kind of debugging philosophy but make files and build automation is something you're going to encounter quite a bit。

 I think as a software engineer as a software becomes really large most people are doing maintenance on software most of the work of software as maintenance and you'll be working with a large project most likely and have to contend with the entire ecosystem around that code。

 which is itself substantial software products。Okay， and before I go on。

 so questions on the Hello World project so far。make it a run。fail。出さないるんてよおえ。どもごいま。

Today why don't we playing the De replay play with you。It wouldn't replay。You问。は。そ今場。ねあ。So yeah。

 can yeah we can look at that if you come to office hours after class。

 we we can check what's going on， but if you have a long delay it may just。

If you took a long time to type when you started writing the script command。

 you have to wait that amount of time so you can try what you can try to do is put a larger number here in the replay。

 but like 10 or 20。And see if you just had a lot of time。That went by。

 so this tool doesn't cut out time there are other terminal recording tools that will like detect。

Pauses， but try this first。Yeah， yeah。Oh yeah， yeah， so next lecture。Is on version control。

 which we'll go over again。So yeah， I wasn't expecting you to try to complete this project。

These last lecture， this lecture and next lecture are really giving you the program environment tools to be able to submit this。

 what seems to be a very simple project， but as some of you probably realize the tools around software。

 version control， build automation are substantial。Well， you should record yourself typing the files。

Yeah， that's fine， that's fine， yeah yeah。内と？Did anyone so I wasn't expecting anyone to do the git yet because we're going to cover that next time but。

Did anyone try to use Git to submit their project？Did anyone have issues with it？Yeah。

What were your issues？The host did not exist。見でしょ。Okay。

 maybe so let's go over it on Thursday when we go over it。

 I'll show an example of doing it and maybe we can catch something I'd recommend like cutting and pasting from here and I'm trying to type from I mean you can try to do that but it's easy to make little typing mistakes maybe I made a mistake or I think some people were saying that they couldn't connect to Eustace at all。

So I don't know if Eustace was down， perhaps。But let's see if this server is。呃呦。That's not good。

 maybe it's only accessible on Eustace， or maybe I have the wrong name。Okay。

 so I can access it from Eustace， so make sure where you're doing this from EustAace。Okay。

 so make sure so this this little pin command is kind of useful it as long as the server is。

Supporting ping， you can see if that machine exists if it's like on。

You give the domain name or an IP address。Outside the scope of this class。ため。

You just type Ping space and then the domain name of the server or the IP address。

And it'll it'll just like。Come back if it doesn't exist。Well， so it'll say domain name not found。

 but if I give a。IP address that probably doesn't have a machine。Fine， let's guess。

So there's no machine at this address it just won't。

 it'll it'll say you know unreachable so that'll give you a good it'll just give you a little sanity check about whether the machine is there and then you can check the rest of the command。

 make sure you're doing Gitoite3 not oh so look at Brent Brent put out announcement he made the mistake of saying you should change this username。

So don't change this username， this is the username that you're got to actually access on the server。

There's a gi server there， so make sure this you don't change， the only thing to change is the NID。

Also， if you don't have any content in your in your like if you haven't added anything yet， then。

Doing get push， yeah， nothing will be pushed。Yeah， yeah。

So we'll go over this next we'll go to on Thursday I think most people haven't even attempted this yet but we'll go over Thursday in detail using version control and setting up the Git repository for the Hello World project if you have specific issues feel free to come to office hours Ill have office hours today and tomorrow and I can see if there are any specific issues。

 but it sounds like at least some people got Git submitted。嗯。So。Yeah， I don't know。

 I don't know what the issues are， maybe your name is not added。

 maybe they missed your NID or maybe the server was down temporarily， yeah， I'm not sure。

But we'll work it out， but you have plenty of time。

You have plenty of time to do this and if you've done all the rest of the project。呃。Yeah， got。

 you'll have another five days after that。To get this started。All right， no problem all right。

 other questions on so yeah the hello work part might put a plan for this。

 which I only probably outlined briefly in the lecture。

So last time going over the editor and so there's three pieces here to this project。

 one is actually using an editor that maybe you've never used a command line editor before。

 but using the editor and recording yourself doing it。

The make file corresponds to what we're going to go over today。

 so making build automation for your project。And then submitting your project via Git is what we're going to cover on Thursday。

So the homework is really light， it's just reading。

And the idea for me is the idea is that you'll work on this project incrementally， so each lecture。

You'll learn the new step you need in order to complete this seemingly simple project。

 but learn the ecosystem around this project。And that's when you're logged into Eustace。

 so you may be connecting to so I saw that comment on Ed STEM。

So the reason for this may be that your're。So this will happen on my machine。I get a window。

 so that shouldn't happen if you're log in to use this。

 but the reason I suspect it might if your terminal is is getting into the weeds。

 but you can actually it's like remote desktop， you can actually remotely。

AAUse a windowing interface on Linux。And that your terminal may be setting a flag that forwards those。

 but it basically does that remote terminal session let's see if that's actually the case。

 so if I run emX here am I going to get a separate window I might。

It looks like I am actually so I would just reconfigure your terminal to its dash y or dash x is the flag for doing it so if you find some setting in your terminal or just use emX NW and NW means no window so it'll run the so I think this is actually。

Giving me the it's very， very slow， but it is。Looks like it's it's doing the windowing interface。

 You can also check this environment variable。 Remember we talked about environment variables。

 If you print this one， the the money sign display。 So it looks like yeah， indeed， I've got a。

Remote window session going on on Eusace， I didn't know Eace supported that。

I don't know if they meant to support that but。Yeah， so apparently you can open up。

Winddoing applications on Eustace and have them displayed on your machine like remote。Yes。

 so I think that's what's going on So check check for settings in your terminal。

 I think it was Moby terminal right a Moby term check for like a setting for forwarding X 11 or。

Remote desktop or something， but it's probably like forwarding X11 is the SSH is I think of the name of the SSH command。

X114， yeah。Yeah。Well， you only need to record yourself typing the Hello World program。Not the whole。

 not everything。So。The instructions are just this part， only these five steps。

So I'm assuming you can write a hell of World program in one day。And so we。You can Google it。

 hellello world programs are not like they're not secret。

So I expect that you'll be able to do this quickly。I think。

 but you don't have to record the whole project submission only。

Only the opening the editor and typing in the Hello World program， that's it。

 you don't have to record yourself compiling it or doing make files and all that that that might definitely it'll definitely be multi day。

Does that answer your question？对。Yeah。Yeah， I mean。

 well at least the way I've laid it out is the first step is to just create the hellello world file and that's it。

So let me show this again what this looks like。think I've got a hello。

So following the directions here， so it be make Directory hellello World， change directory hellello。

And then。Start recording。And so if you've at least done the tutorial of the editor。

 you should at least at a minimum be able to create a new file， open a new file， type it。

And save and quit。So here's starting the script and so you know the timing is recording now。

 so any long pauses you have here will be replayed back in real time unless you add a multiplier and here I'm going to use EmX because I'm an EmX user。

And then you just type in hellello world。and feel free to look at， you know。

 I'm giving you the hellello world code， you can can copy what I do for hellello world。

It's no secret at the point of this project is to learn the editor。Make files。

 build automation and version control So the actual coding step I tried to give something that is。

Something I think everyone has done。So use the editor commands to save， so I did X control X。

 control S， control X， control C， and emX。And that's it， and then exit will stop recording。

And that's all I'm expecting you to record， that's just what I showed there。Okay。

 so if you look here， the scripts actually get saved here。And you can play it back with this command。

 which I'll just copy。And see there's my delay from the beginning。

 although even though I'm on 2 x times， so I'm not no hands here， it's happening automatically。

And you can quit anytime with control C， so later on when we do version control I'll have you submit those files as part of your submission so we can like check them。

Is that。Good， okay， what's going on。The make file， we'll go over that today。

 we'll go over the make file how to do make files today。

 so the good segue unless there are other questions。About this part of the Hello World project。

All right， so let's do。What I think is a very exciting part of software engineering。

 which is build automation。 I actually do research on this。

 It's probably one of the more boring parts， actually of software engineering but。In recent years。

 it's become a particularly。Particularly sensitive part of the software ecosystem。

 actually I hadn't planned to do this， but there was actually a couple of very large。

 severe security vulnerabilities related to the build system， one was solar winds， I think。

 who's heard of the solar winds attack。A couple of people。

 so this was a case this was some I don't remember what the。

What the software was it was some security management software or something。So yeah。

 they do management， you know， they're they do like organizational management。Where's the attack？

So the way attackers got it， so this software is， you it's all certified and digitally signed so that when you receive the software。

 you can be sure that whoever who you thought made the software actually made it because they have a private key that they use to sign the software and that's very hard to break。

So what the attackers did instead of trying to。putut malware on some of their target machines or try to make a fake version of this software。

 they broke into solar winds digitally， they broke in remotely。

 and they modified the build system to insert malware into the software before it was digitally signed。

So this is something that's a little tricky to detect instead of inserting it into the code where some shark programmer might notice。

 you insert it into the build automation because the build automation can do whatever at once。

To the source code during the build process。呃。否则。Yeah， yeah。So， yeah。

 this is how a huge number of organizations were attacked。嗯。

So another more recent example is the Lib XZ。Attack。Who's heard of the Libx Z？Even fewer people。

 so this one was particularly nefarious， let me see if I can get the details right。

But basically what it did is it allowed it put a back door in the SSH server of any machine that was infected。

 so this could be Eustace， this could be any server you run but have a back door that I think allowed。

Whoever created the software to access that server？

But the subtle part here is that it wasn't a direct attack on the SSH software。

 it was a direct attack on this compression library called LibXZ。

And that library actually is not linked to SSH， SSH does not use this library。Instead， it's used by。

Remember， we talked about the init process the other day。Let's see if I can bring this up again。

There's an init process， well actually I can show the process here。

So this init process on a lot of modern Linux distributions is actually a program called System D。

Which basically manages all of your background processes， including SSH servers。

 so they're not going to let me， oh， they do let me say this okay。

So SSH is one of the services that it runs， and apparently from my understanding。

 which might be a little wrong in LibxZ， that system D depended on this compression library， Li E Z。

But it also is the process that's like running SSH。

 and so apparently this person very cleverly got code into LibX Z that would。

Modify system D to put a back dooror in the SSA running process。

So it's a complicated sequence of how the attack was how it was discovered was very funny because I think some Microsoft engineer noticed their SSH logins taking like a second longer。

 which seems like， but it was like 20 times longer or something， so the second seems like not a lot。

 but if it's whatever it was 10 or 20 times or sl。But the way this attack happened was not- so this maintainer。

 there was a couple things that were at play here， this LibXZ library。

 like a lot of open source libraries was just maintained by volunteers。

And may not have a lot of activity， and so some user over some long period。

 this long con got themselves effectively maintainer status on this project they could。

Do whatever they wanted to the source code， and they didn't insert it back door into the code。

What they did is they made a test。So LibXZ has its own test being shipped with it as I hope you read about in chapterpt2。

 has a suite of tests， and so they inserted the malicious code into one of those tests。

 the tests are compressed library so they kind of look random and so from what I understand they put binary。

 remember we talked about the name what was that called masquerading names。

 you know the file system you can name things of whatever you want。

 so they named a test some compressed library but it was actually some code。

 some binary code that would be used to modify system D。嗯。

And they shipped it as part of the build system and had some complicated build automation code that would not run the test。

 but would extract this。bininary code and insert it you know actually inserted into the Lib Xy library which would then infect system D so the process is very complicated there's a really nice infographic I can't remember where it is but there's a really nice infographic on this that kind of explains the vulnerability。

I don't like live searching。

![](img/955eca6ba8e7180b915869651d1b34a1_1.png)

But there was a good。Infographic， oh， yeah， this is it。 So it's a complicated sequence of steps。

 but the。The main point here is that the malware was not just like written into the code。

 instead the maintainer decided to hide it in the build and test automation。

 basically the software ecosystem。And so while you know。

 make files maybe kind of boring and build automation is kind of this。You know。

 like a hokey part of software engineering。Because build automation is becoming so large。

 so for instance， the Linux kernel's 20 million lines of code。

 its build and configuration system is like 200，000 lines of code， so who's written 200。

000 lines of code here？I haven't， I don't think， well maybe collectively， but not in one program。

 that's a substantial piece of software in its own right。And so these are becoming targets。

 especially as software is becoming。More memory safe or better vetted。

 the build automation software is kind of a wild West。

 doesn't have as much bug findingd and capability or safety as the main programming language and so these kinds of attacks you kind of expect would become more frequent。

All right， so you interested in make files now sound fun。

 so I don't know if this actually used a make fileile， but it probably some similar built system。

 I think it is a CE program。All right， so with that impromptu prologue， let's get into。



![](img/955eca6ba8e7180b915869651d1b34a1_3.png)

Build automation。So I kind of teasse this already， but for you guys， when you， for instance。

 when you built your Hello world program， what did you do to build your Hello world program？Yeah。

 you ran GCC， right？So you just ran GCC， let's how you build a program， right？

Why do you need to do anything else？What if you have two C files that are part of the same program。

 you can write C code with separate source files， right has anyone written like separate source files for the same program？

Okay， not matter， okay， yeah。So yeah， in classroom projects they're usually like 100 lines。

 200 lines， not large， really no need why would you separate it into 10 different files。

 but for those of you who have done this， how do you compile a program that's composed of two source files？

Yeah。はい、ぐらいて。Did it look anything like this。Or use piping to actually cat them together。你怎我说。

Oh oh you compile them separately I see I see so you can do this with one line if your program is divided into two source files。

 it's almost as if those two source files are in the same file almost。Kind of conceptually， was that？

Oh no， no， no， no， no， actually what you're saying is you compile them separately is kind of what I would say the right way。

 you compile them separately and then you link them。So that I think that's the right way。

 I was hoping for the easier way。The easier way to do it， but you're actually right。

 that is the right way to do it， which is do separate compilation。Which which I'll show， yeah。呃。

It may matter for error messages， like if you have the same function defined find multiple places。

 the first one will be taken。Yeah， I can't remember， I can't remember Florida matters。

 I'm hesitant to say no， it doesn't。诶。I mean， it shouldn't matter。

 it shouldn't matter because all the function namess need to be unique。So I shouldn't。

 but I feel like I'm missing something。But this is like the kind of。Niveively to compile。

A program that has multiple source files。But what if I have like 30，000 source files。

 you have a question？Oh， okay， what if I have like 30，000 source files。

 then what your colleague said compiling them separately might be a better idea。

 otherwise you've got like this。30，000 file long GCC string。呃。So I wanted to actually show。

So taking the Linux kernel as an example here。Here's a little find commander。

 if you remember I showed it。U。A couple lectures ago。

 this will list out all of the C files that are in the Linux source code。And there's a lot。

 I can count them with WC。 There's over 30000 source files。 So if you're building Linux kernel。

 you probably don't want to have to。Buildill 30，000 files every time you're doing development， right？

So yeah， so I'm kind of answering the question already， but why not build everything。

 why not build 30，000 all at the same time， why not do that？Yeah。It takes forever。

 so at some point you're going to have to do it。嗯。But one of the more important reasons is that if you make a change to one file。

 you're now going to have to rebuild。30，000 files。Which is going to be really annoying if you're going to have to wait like an hour to rebuild because you change one line of code。

So the solution to this as one of your fellow students pointed out ahead of time。

 is separate compilation。Divide your program into separate source files。

 which the C tool chainin supports。And compile them individually。

And then link these compiled files together。So I will before when we go into the compiler。

 I'll actually go into detail about all the steps that go into turning your source code into binary and a running process。

 but today I'll just show you kind of conceptually how you use separate compilation。So let me get。



![](img/955eca6ba8e7180b915869651d1b34a1_5.png)

![](img/955eca6ba8e7180b915869651d1b34a1_6.png)

O。So the way this works is。This is not writing。Okay， that's weird。

 it won't write when I'm in full screen mode。All rightSo the idea here is if we've got three。

C files that our program has broken down into。Make up a program here， let's sense。

Content in the program doesn't really matter。Got three C files。

So instead of running GCC once to compile all of them。We run GCC three times once for each file。

And these will produce。We're called objectject files。Which are the。Compiled versions of。The C code。

So we can compile the each of them separately。And use a tool called the linker， who sort the linker。

 they talk to you about linking a little bit not much。

 so a tool a linker will take binary compiled machine code and will turn it into a single program effectively for you。

So now we've got our main。God youX see your main program。

So this is what separate compilation does for you。Its pretty straightforward， right？

You just compile your source file separately now you don't have to rebuild the whole program when you're doing development。

 you can just build one of the files at a time yeah。So it doesn't make if you're just building once。

Yeah， it's the same amount of time。Effectively， but if you're doing development。

And you're modifying parts of the code。Then you only need to rebuild the parts of the code that you've modified so this this is useful for software development。

 not necessarily software users， so as software users you don't even need the source code you can just take the binary if you want if you don't want to build from scratch。

But for a developer， if you're working on a large piece of software。

 which if you're going into software development， many of you will。

 you'll be contending with build automation and benefiting from it。

Because it will allow you to rebuild more quickly。Yeah。This one of the LD command。Name。

 the name of project。You mean， executing me like dot slashma， yeah。Yeah， yeah， yeah， yeah。

 so it'll produce the same program binary。And actually running this。

Running this version will actually do the exact same steps as running this version。The same steps。

GCC will just do those steps for you automatically， it will do separate compilation and length them。

For you。But you just don't have those intermediate files saved。So LD is the misnomer for the linker。

 LD stands for loader。I think think it's a misnomer。嗯。So the load， the loader is the。

Part of the operating system that starts running the program。

I think this was a mistake in the naming of it I'm not sure， but it's the linker。

 this is the tool that will take binary files and glue them together into a single binary file we'll talk about that in detail when we get to compilers how that works。

啊。We are， we are， so we are still ging each one of them。 The difference is whether we。

The real difference is whether we save these intermediate files or whether we save the individually compiled source files。

Or not。So yeah， GC will do the same thing。If you。Pass in。All the C files。

But it'll throw away all of these intermediate thought files， and so they have to start from scratch。

With all the source styles。Do it that way。对。Okay， yeah。Ah， so that's actually a good point。

So the compiler， and we didn't talk about compilers yet。

 but what the compiler is is it's a translator from source code to machine code。

 so these are two different languages。Actually， so this isn't a linker for C。

 this is actually a linker for assembly。Well， machine code in a particular binary file format。

 but you can think of this as。A linker for machine code。

 so any language that translates into machine code。You can use the linker for。假文。

So Java does not- well， the normal Java does not compile into machine code compiles into Java Bte code for its virtual machine。

The same linker won't work， but it does have a linker that will glue together multiple。Effectively。

 it will package them。Into intoto one binary， what's that？Dar file， yeah， exactly。

 it'll compress them into one。Yeah， question， but yeah。

 so anything that is like compiling to machine code， like rusts。Go。呃，A的。

We'll end up using the same li or a similar liing process。Good question。

 other questions on separate compilation。Any questions on why we do set for compilation or why people use？

This technique。Yeah。何です。Yeah， yeah exactly right yeah。

 yeah you just save you save the intermediate compiled code so if you think so this is more for like software engineering design when you have a large program you want to kind of chunk it up into logical pieces。

And you can compile those separately， and the benefit of that is you don't have to recompile the whole program。

All right。So that's separate compilation。at separate compilation so let's look at an actual example program。

I've got this。Set up already。Here。So this program。I tried to make it as simple as I could。

 so it's a program broken up into three different C files。One program。

 or there's one function here defined in exponent that C。

 this is supposed to compute the exponent of a。A positive exponent of a number。

So don't worry too much about the code but it's just computing the exponent x to the Y。

Square is a function that uses exponent to complete the square for some reason。

 but just an example to show you three different programs。And main call square。Yeah我塞。Yeah。

 so that's why I have this， you couldn't use header files to do this， but I just。

 I didn't want to overcomplicate the example， but yeah， square needs to be defined。

It'll still compile without it， but you'll get some warnings。So yeah。

 that's why the function prototype here is declared。No， because it's not called in Maine。

So only square is called。And we'll go into the accomplish， yeah。Exactly， yeah。

 so header files they're meant to hold these。These declarations of the functions。

I just want to keep this example simple， but yes， exactly that's right， that's what header files do。

は。Yeah， performance so compiler performance I mean we're getting into the I mean these are pretty small numbers already。

 if you have a very large program， one benefit to having a header file is that GCC has an optimization called precompiled header files。

 so if they're included in multiple programs or multiple multiple times。

 often headers get included multiple times。Just because of the way the architecture of the different libraries or different components will depend on the same code。

 and so the same headerophiles will be included multiple times。

GCC will actually compile it once and then save the compile version of that header file to improve performance。

On the other hand， the headerophiles may include lots and lots of declarations that you don't need。

And so you could kind of optimize a little bit by doing what I did here and not using that。

Slight optimization， you have to open the file， you don't have to have all the declarations being。

Yeah， I mean yeah， this is like a design choice。Yeah， the hard part here pedagogically is life。

If I give a really like an example where you really want to divide things up。

 I have to go through like explaining the whole thing， but if I make it too simple then yet。

 you probably don't need to do that。Now， one reason we may want to do this is if say exponent。

c is used。Use you know in lots of parts of your code。You may want to put it somewhere separate。

 so if you modify that， yout have to rebuild。All the rest of your code。やめる。But yeah。

 this is a totally contrived example where you don't have to break it。They can。

 so header files literally just cut and paste the code and you know think of it as cutting and paste in the code。

 I mean it actually does cut and paste the code so you can， it's just totally a convention。

So C imposes very， very little convention on you。But the way they're used， I mean。

 like it doesn't enforce conventions， but the conventions that have grown up out of the C environment are that headerophiles are like defining library or declaring library functions。

 stuff that's in a different copillation unit。Or even in a different library。

So take I would say well once you get into processes and senior design。

 there's a software engineering course here actually and that has's been restarted by a great new faculty member。

 so I recommend taking those classes and you'll see the larger software design and how you can use modules to break up your。

Your program。But you cant even do it for your， well， yeah， in this class。

 you could at least break things up in the functions。

You can decide whether you want- the programs we're going to have a pretty small in this class。

 so you may not need to use this。啊。But yeah。Other questions on this？All right。

 so there's our example program。Let's see how we separately compile it。

 so there's a flag in GCC called dash C。And what it does is it does this。Step here， so running。

GCC D C。Well do just compiling for you， and in fact。

 D C is what compiling is when you run GCC without dash C。And like in this previous example。

GCC is actually doing much more than compiling it's also calling the linker and doing some other stuff for you it's linking with standard libraries and the C runtime so if you've ever run GCC and you didn't have a main method and it said hey you don't have a main method that has little to do with compilation that's actually the linking a linker error and we'll show more of that detail once we get to compilers。

Has anyone ever seen that error， no main method， no？Okay。

 so here's how we can do separate compilation， so if we sort of agree that separate compilation seems to have some value。

Then why not actually？Do separate compilation。The problem is we have to type this three times。

If have to type G， you have to individually compile each one of these。C files。

So let me actually write out。Go through the。Trovele doing this。And now I've got my dotO files。

 and once I got them all compiled， I have to run yet another command to link them。

And so this looks very much like。Compiling them altogether， but here I'm passing in the dot O files。

 not the C files。So that process is going to be much faster。

 I think if you probably instrumented this， you would see that it's。Probably faster， well， yeah。

 we can actually see that is faster。So not much for this small program。

 but you can see that actually compiling took know four times longer than just linking。

So that's what we'd have to do if we want to take advantage of separate compilation。嗯。

And that's kind of annoying， right， so if we modify Maine。Then we're going to have to remember。

Let me modify main here。And now I got to remember which file I modified， recompile it。

Wecompil it with GCC。And then relink it again。So kind of annoying right little bit of memory stuff I have to do So this is where build automation comes in So sure for three source files。

 not that big a deal， but when you've got like 30000 and you want to have to manage this we're computer scientists so why not automate this for us Why bother。

Doing this by hand， let's use automation and this is where make files come in。

 make files are designed to do build automation， they could be used for lots of other things。

 but they're designed around build automation。Okay。

 so this is what called a recipe or a rule in make files that have this very specific syntax。

 you put the file that you want to generate here that's called the target。

You put really just bash commands or a slight list of commands， just like in Bsh。

 you put a little script here to tell you how to build the target file。

And then prerequisites set up dependencies。And we'll look at how those appendencies work。

 but the main point here is we can declare， hey， I'm generating this file here。

And here's the code to generate it。So very， very much like a ba script。

And the simplest example of this is I want to generate the main me， the main program。

And here's my command to do that here's how I generate the main program this is my non separate compilation version I can just say all right。

Gcc dashO， and then all of the three。C programs。With me so far， questions so far on this。

So this is the syntax of make one little wrinkle is that this space here needs to be a tab character。

 it cannot be spaces unless you change the behavior of make if you use a great editor like EmX that will like do that for you。

This is the final version， but EX will basically do that for you。So right， so let's。

So you can see here it'll actually show you it'll highlight for you that you've got space here。

 and if you try to save， I think it'll warn you， oh no， it doesn't warn me。Well。

 it'll show you the space， at least。All right， so here's。不し。So I don't have to type it。All right。

 here's my。Very first make file。So here's my make file here。And if you name the make file。

 one of a couple of names， if you name it capital make fileile。

 I think there's a couple of other names， all you have to do is type make。And it will。呃。

Let me get rid of the。So it's already built， so it won't build it again。

 so let me I just got rid of the file that was built so when I run make。Make by default。

 looks for a file named make fileile。This is the contents of I make file。And what it does is it says。

 all right， you ask me to build by default， it'll build the first file in make。

 you could say make main， you could say please build main for me。And it will run。This command。

But make files are make is a little smarter than that， it will。

 because this is the name of a file that you need to generate。

It will not regenerate the file if it already exists。So because Maine exists here already。

Maine will help avoid wasting time by just not rebuilding the file。You can force it。But。

I'll show you a clever， more clever way to make it rebuilt。But questions on this so far questions on。

The basics of a may call Yeah so if you were to have more， not just make or run album。

It will only run the first one。So I could have a clean script here， which removes main。

And make will only try to build Maine。So if I run make clean。It will remove， it will run clean。

 so you can tell it which one you want。And we'll see that actually all you need is to。

 if you want to build a project is to run the first one and let's see how that works。

 but questions on just this， the basics of make files。Yeah。AhaYes， absolutely。 okay。

 you're very good at segueing， segueing for you， but absolutely， yes， you can， you can。And yeah。

 we'll see that。Only with Tab。Yeah， you can configure it differently if you want， I think。

 but this is one of the annoying parts of makeF that T is like part of this index。嗯。I run make。

Oh so is this is the make file so if you look at my files here I've got a file called makeFile if I use CA to print it out。

 this is the contents of the make file think of it as a program。

And the make command runs that program， so by default it will look for a file called make fileile。

 but you can tell it which file to runs， so think of it like a Python script or a back script。

Where make files are run by the interpreter make， just like the Python。Well。

 you save it as a make fileile， like so like what we showed in file management and editing。

You save the file under a certain name， so you give it the name make fileile。

 or you give it any name you want， and then you run the make fileile using the make command。

Does thatDoes that make sense？Yeah。は？We remove。Well。

 this is what I've I said it'll just run this command and that command。No， only so only the first so。

Makeake will run whichever。Target， you ask it to。So it'll only run one recipe per execution of make。

I mean。You can， can provide multiple targets at the same time， but this is getting into the weeds。

 but basically you give it a target to。To run。So this is the name of the fakeig file I want to run and here's the target I want to build。

So name of the make command。File that holds the make script and then the name of the target I want to run。

And it will just execute the code here。の。So make has defaults。

 so running make by itself will assume we'll look for a file called make file。

And it will run the first target in your script。Yeah， so it's just defaults。Exactly。

 so we run make clean， we say the name of the target we want to。Because it'll run this command。

 which will end up which yeah we， it'll write the output。De that over。Well。

 just like in any file system if you。You know， overwrite a file， yeah， it'll be gone。

 you could make multiple make file yeah。Sa。明法我。Well， the make file， you don't remove the make file。

The make file is like a program， is like a script that you leave there。So when I run make cleanan。

It's executing this command to remove main。 So it's removing main。 It's not removing the make file。

 Does that Does that answer。No， it only does the first if you don't tell it any targets to run。

 it'll only do the first one it'll do the first so these are just defaults。

 these are just like convenient defaults。 The kind of ideal is that you just download source code and you run make and voila everything's done for you。

 but that's helped by some default so。Make file is the default name and then whatever the first target is is a default name so by convention people use all as the first target which which I'll show you。

 but yeah， so there's just some sort of defaults here。And conventions。All right， so that's。

Writing and make file， so why not why even bother do this the same same as the same as it was before。

But。We can。At dependencies here， so what these prerequisites do。

Is make will look at the timestamps of these files and say， have these changed since I built Ma？

And so right now， if I try to rebuild。If I try to rebuild main here。It'll tell me it's up to date。

 even if I go in and I say， well I'll use the touch command to edit this if I update main。

It's still not going to rebuild it for me because it's already built， so make the make file。

System will say， all right， you've already built this， so I'm not going to build it for you again。

But if I say。These are my prerequisites for building Maine。

The make fileile system will look and see if those files have changed， and if they've changed。

 it will rebuild this file for you。Makes sense， questions on that。

So we can see that in operation here。So now if I rerun mainine。It will rebuild for me。

And it won't rebuild Maine until I've。Edited。One of the files， so if I edit。

And it actually just looks at the timestamp。So here I just did minor edit。And it'll rebuild。Yeah。

Nextやです。Exactly， so the idea here is。You make so instead of building the C files。We change this。

 we want to build the dot o files， we want to just link the dot o files。

But we need to tell make how to build those dot O fileses。

So I want to build main dot O whenever main dot C changes， I want to build it。

This is how I rebuild my dot Sea。And then do this for all of my files。All right。Let me。

Let me clean out all of the stuff I built。There are not okay， so now when I run make。

The way this works is make will look at your prerequisist and say，Ha this been built yet？

If it hasn't， it will go look for a target。Let me diagram this very quickly。

So it'll take the first target we want， which is main。And it'll look at all of its prerequisites。

So we've got main。O。Square。 O。And。Exponent dotto。And it'll say， all right。

I need to go build these if they don't exist already。

 so let me go look in a set of rules and say do I have a rule to build main。

0 yes I do so in order to build main。0。I need main dot C to exist。I wrote that as a developer。

 so I don't need a target for it， it already exists。And it'll look and say， all right。

 has main dot C been modified since I built mainine。 or is Maineto missing？If so。

 it'll run this recipe， this recipe， or yeah， this recipe。Whi as long as you've written it correctly。

 it will build it for you so makeF is not going to enforce。

 you know ensure that you've written a correct build process。But as long as you have code here。

 that will generate main。0。Then。Makeake will run GCC for you。

And it'll do this for every prerequisite， so it'll do this for square， it'll look for a target here。

 it'll do this for exponent， if there is no target available， make will give you an error it'll say。

 hey， I don't know how to build this file。But if you've written this all correctly。

 then it will build all the prerequisites for you so all those files within the same。



![](img/955eca6ba8e7180b915869651d1b34a1_8.png)

Director。Yeah， so these are relative paths right now。 So you can use， you know。

 your knowledge about paths。 There are lots of designs for make files。

 Linuxux kernel has lots and lots of make files that are included inside of each other。 But yeah。

 it'll just look in whatever your relative path is。



![](img/955eca6ba8e7180b915869651d1b34a1_10.png)

All right， so what do you think will get run when I run make now， or I run make Maine。

 which is what's going to be run by default？What commands are going to be executed？Yeah。呃，我在。

So what's going to run first？Yeah， all the GCC commands we run and then the linking run。

 so exactly what yeah， exactly what you guys predicted。

And that's because it's actually building a tree of these dependencies and targets。

And it's just going over the tree， it's using a tree traversible algorithm and saying。

 is this dependency old or it's prerequisite's newer？Than the target， and if it is。

 it reruns the recipe if not。It moves on to the next trait。

 so just a basic tree traversal algorithm here。And the key trick here is if I now modify one of my programs。

Or one of my source files， so here I had a comment。So I've now modified。Exponent dot c。

 so you can see here， exponent do C。I modified it within it the timetamp is more fine grained than。

Let me touch it again so you can actually see。A change。So you can see this was modified at 114。

 whereas the dot O file was built at 113。 So when I run make again。

What do you think is going to get run？Yeah。So itll run GCCX does not see anything else？

It'll run main again。 exactly right。 So if I ask it to run main， it'll look at its。

 It'll look through this tree。 It'll look for。The dependencies and say， all right。

 exponent has been modified。But and it'll rebuild it， but because Maine depends on exponent。t0。

 it'll say， oh， your prerequisites are newer than Maine。

So because your prerequisites are newer than main， I should rebuild Maine。

And that's exactly what we get， we get exponent being rebuilt。And Ma being rebuilt。

 but nothing else because everything else is already up to date。Questions， questions on this。

Is that cool？在一错。😊，Okay， maybe not so cool， but it is really useful when you're doing large programs you can declaratively say what parts of your program to build now one of your fellow classmates ask can you do you have to like type all this out can you specify multiple targets and absolutely you can so you can do wild card patterns so we don't have to say。

Each single C file， we can use this wildcard pattern to say any dot O file with the same prefix do C file run this and there are all these esoteric built in variables for saying you know which part of the wild card you want to use so you know you don't know the name of it because it's a wild card pattern this says。

The first。This basically says the prerequisites for this。

So let me show you the sort of complete version of this you can also make variables。

These look I know these look super esoteric。This is the target name。This is the prerequisite name。

 the first prerequisite name。This is all the prerequisites。So I'll let you look at this on your own。

 but this is this is equivalent to。To this linker here。And this is equivalent to。

R writing each C file at one time， and there's all sorts of other tricks like using variables and things like this in make。

Questions， questions on us。Can these wild carts。So last thing if you want to have so by convention the first one's called all the first target' called all there's also usually a clean target。

 now these don't correspond to any files so if you want make to not check for a file and just always run it when you ask for it they're called phony targets you put this little thing here so this is the complete make file for our program and you can use this as a template for your much simpler program which only has one compilation unit so when you write your make files you can use these notes as an example for your Hello world program。

All right， so homework tonight is just reading chapter three and four of the book， yeah。

 all of office hours now， so yeah anyone anyone has questions， have a good one。



![](img/955eca6ba8e7180b915869651d1b34a1_12.png)