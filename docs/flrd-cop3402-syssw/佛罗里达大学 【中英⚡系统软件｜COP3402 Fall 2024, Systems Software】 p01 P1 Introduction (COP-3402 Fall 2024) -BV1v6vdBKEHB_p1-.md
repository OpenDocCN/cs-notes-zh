# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p01 P1 Introduction (COP-3402 Fall 2024) -BV1v6vdBKEHB_p1-

So welcome to System software。My name is Paul Gzlow。

 actually now I'm an associate professor of computer science here at UCF I do research thank you you I do research on software engineering and programming languages and security。

 this is linked to my webage if you're interested in research or graduate school or anything like that feel free to reach out I have lots of undergraduates who come through the lab and if you find anything in this class interesting we do a lot of work that's very relevant to the stuff that I'm going to show you in this class。

Okay， so why are you here， I know this is a required course， but why bother studying system software？

Does anyone have a reason to be here besides？You have to be here。

Is there something you want to learn？You got to learn how to process files do the command line。Sure。

 yeah， yeah， we're going to go over a lot of that file systems command line。

 some of these lost stuff that you don't necessarily get at school and maybe you see someone next to you just blazing away at the command line you're like。

 what are they doing？You're going to get a crash course in about a week on how to use the command line。

 so good， yeah。Here。Yeah exactly right so actually you've led into my segue into my next slide which is know Your tools。

 this is really probably one of the most important reasons to take this class and hopefully learn something from this class and so this is an example of Isaac Newton everyone knows Isaac Newton right。

 the founder of sort of modern science and developed all these physical models， mathematical models。

So what you might not know is that he made telescopes， he studied optics。

Is that he actually ground his own lenses， so this is a notebook of his where he learns how to actually grind lenses。

 you know he wasn't just sitting in an ivory tower theorizing。

 he actually built stuff and built tools to help him do science。I mean。

 so this is true of all technical workers， if you're a pilot。

 you go to a flight school and you learn about the plane， you learn about physics。

 some carpenters even build their own tools， not everyone can go to a store and buy a tool。

 somebody had to make that tool。So that's one of the important reasons to take this class。

And the reason to know your tools is if you ever heard this proverb， a poor workman blames his tools。

 you don't want to be that person who's stuck suffering on their machine， not knowing what to do。

 not knowing how to use it， and then if you're at a job or，doing research。

 you're in a lab and your work is suffering for it， no one's going to help you。

 you're going to lose your job， so knowing your tools well is going to help you in your job。

 your career， I think。And there's a more philosophical reason that I have this quote。

 I thought I made this up， but I didn't， is that tools are made for man， they're made for us， humans。

 we're not made to serve these machines， at least in my view。

So if you've ever been stuck in a machine and saying， well， why is it doing it this way。

 or I want to program it this way， but it's not working the way I want。

 oh well that's the machine the machine decided for me。

 I want to try to get you out of that mindset that you as we as humans have control over these machines and by learning how they work learning them under the hood。

 you'll have a little bit more of that control and you won't be driven by whatever the machine or the designer of the decided for you。

I thought I invented this quote I didn't， this is actually Als Hudxley and Thomas Merton。

 these guys actually came up with this as well， technology is made for man not made for technology。

 little philosophy that I have。And then another illustrative quote，'s from my dad。As a kid。

 I would try to do something， build something， or hammer something， and you would say。

 don't use your hands， use a tool。And not just use a tool， but use the right tool。

 so don't use a screwdriver as an all， or don't use don't try to because you'll break the screwdriver。

So I think it's important to learn why these tools are useful， how they're designed。

 in order to be effective at using them。And get you out of this mindset of just thinking that if you use a certain tool。

 you're got to be really good at programming， so if you buy a really fast car。

 you're not necessarily going to be a great race car driver， right？

Professional race car driver may beat you in a slower car。

And also really importantly is that you can actually modify your tools。

 these aren't just given to you from on high， these are tools written by people and the software we're going to look at this class。

 the system software。Is I think entirely open source， you could actually open up the hood。

 you can modify it yourself， you can build it yourself。Okay， so that kind of begs the question。

 oh yeah so my course goal here is you know the kind of academic course goal learn to use and create system software and that's what we're going to do in this of course。

 and that kind of begs the question is what is system software？

Theres this is a very fuzzy area so if you've I'll give some examples of why it's fuzzy。

 sort of hard to define what system software is， but here I give a kind of functional definition about what it's used for。

 and to me anything that's bridging the kernel which is the lowest layer of software on your machine and applications could be considered system software。

 the stuff that connects the applications that we all want to use every day on computers with the actual hardware as abstracted by the operating system。

So here's a diagram of what that looks like。At the bottom。

 we've got the hardware and me as a software guy， this is just given to us from electrical engineers。

 I don't know how it works， I don't know how to build it， I take it for granted。

 they've documented it， they tell us how it works， they tell how to use it。

And right above the hardware is the lowest layer of software called the kernel。

You may not you probably haven't taken operating systems yet。

 but maybe in computer organization they talked about this a little。

 but the kernel is you can think of it as a kind of idealized hardware。

 it gives you this abstract view of the hardware that makes it so that you as a software writer don't have to worry about distinctions between say a flash drive an SSD drive or a hard drive or a network socket。

 the kernel just provides this kind of idealized layer of hardware。

 and at the top of the stack we have the applications， everything you want to do on the internet。

 we all look at TikTok videos or whatever。Whatever you kids do these days， write other software。

 do data analysis， listen to music， and it's the system software that really bridges this gap。

 and it's a wide expansive， sort of ill definedfin layer。In the 90s， Microsoft， yeah， go ahead。あ。

Driver as well that also kind of depends， so in a monolithic kernel that theyd be considered part of the kernel you could consider than part of system software and a different type of kernel design for this class we're going to consider those part of the kernel。

 not part of system software。Oh， yeah。I think VM is system software yeah。

 so we'll actually go over them in this class， so to give an example of where these definitions kind of。

Got into legal and kind of political territories decades ago in the 90s。

 Microsoft was competing with what Netscape use or what Firefox used to be， Nescape browsersry。

Many of you are probably too young to remember this， but Microsoft， according to rulings。

 use anti competitive practices to shut out this browser and their argument is that well the browser is。

Part of the operating system。It's like system software， like a print dialogue or a file Expr。

 and you can decide for yourself whether that argument holds water。

 but just to illustrate that the definition of system software is kind of a little blurry。But okay。

 so for this class， here's some examples， we'll kind of just be example driven in this class about types of system software。

Libraries are one， so if you've ever used printnt F or MalLEC。

 these are all part of C standard libraries or Uni standard libraries。Programming tool chains。

 so all of the programs that take your software into machine code。

And programming environments like editors like ViIm and EMAC。

 building tools like make and version control like Get。

So these are the tools that we're more or less going to cover in this class， you'll use libraries。

 we won't write any libraries in this class， but we'll actually write some of these pieces of the system。

Questions on this， arguments， thoughts， different thoughts， yeah。Well我我 is a。That wasn it wasn。Oh。

 we'll go over that near the end of the course， it combines multiple binary if you compile your program it's in machine code and then if you have two different C files。

And if you want to combine them into a single program， use a linker。We'll go over that a little bit。

 yeah， actually， we'll go over that near the end of the course when we talk about compilers。

Any disagreements with this definition or examples？Okay， so by the end of the course。

 and some of you actually pointed this out already。There's a few things。

 like five kind of competencies that I hope everyone will walk away with。

And one is understand the file system， so too often students go through computer science without a basic understanding of hierarchical file systems。

And partly is because modern OS is just kind of hide this complexity from you。

 you know you just search for things， that gives you to finder。

And so some of you may be looking some of you might be thinking oh this is easy。

 I'm gonna to ace this class is is no problem and other you might be thinking。

 yeah you know I've never actually looked at the command line and found my file。

 I let my operating system do it for me but the important thing to learn here is that this file system was not found in nature is developed by people and the homework you're going to do tonight is you're going to read about the development of of that file system and so you have to learn it so you can't take for granted that you just have to know it in computing and so we're going actually learn the hierarchical file system in this class。

 so some of you might find that easy， some of you might find that perplexing but I want to make sure everybody's on the same page and that you don't leave computer science thinking where my files on my machine so again it's like my machine does it for me I'm at the whim of whatever my machine does instead if you know this you'll be able to understand what the operating system is doing under the hood yeah。

I remember， you know， in security。Particularly as he is when I have felt trouble and finding my plot。

Dctory is。And。あす。Exactly so we will learn how to use the file system one of the first things we'll do secondly is the command line so just like with the file system you've probably seen people next to you are just like ninjas on the command line and youre like oh man I'm doing really bad in this computer science but it's not really taught you just sort of expected to know it that to be proficient of it so we'll actually go into using the command line and along the way we'll learn about the kind of system software and operating system design that you're exposed to with the command。

So if you've ever wondered like why bother or the command line。

 well it exposes you to really almost the full power of your machine and the operating system。

 there's a lot more you can do in the command line than you can with special purpose applications。

And we'll see that in starting next week or in a couple weeks。

 there's also a lot more software probably that does not have a graphical interface。

I hadn't measured that， but I'm pretty sure it's true。

 and using the command line allows you to download and run just a lot more software than other people have written。

You can also do massive amounts of automation， so something where you sat down and said well。

 I need to write a C program or a Python program for。

 there may be a bunch of tools that already exist that you can glue together kind of like LeGgo blocks。

To make。Programs that are as powerful or more powerful and faster than you could just write by hand in like Python and we're actually going to use this in this course for grading。

 we're going to automatically grade your programming projects and my graders and TAs will write software that automatically grades it so that they're not downloading。

 building， testing 290， 290 projects every couple of weeks。

And so just to give a little illustration about how powerful the command line is。

 who's heard of the Linux kernel？Probably have a device that uses it。

 it's over 20 million lines of code and thousands of thousands of developers and you can actually develop for that。

 you could contribute to it， you could get the code， build it， run it， modify it。

 you could send emails to the developers， you can patch it。

 you can submit it entirely on the command line， yes even email， even calendars。

 there are command line tools for doing this and many Linux developers do it this way。

 they do things entirely on the command line。And so that's where we're going to learn in this class。

 we're actually going to learn how to do the entire software development lifecycl。

 just with that maybe esoteric to some command line。Okay。

 so this was the file system in the command line。One thing that goes together with the UniIX command line is the UniIX philosophy and we're not going to go too deep into this。

 but one of the reasons that we can build up complicated tools without having to write new software is because of this UniX philosophy。

 this idea of having welldefined small tools which we'll see starting next week that you can cobble together to make solve larger problems without having to actually reinvent the wheel or write code。

 and I put some links here if you're interested in reading more about in the notes。And similarly。

 in order to do all all your development on the command line。

 the development environment I've picked is the Goe Linux。Controsially， some people like to call it。

 but the Gnew development tools like GCC make， which are developed by this Gnew organization。

And used on Linux operating systems。And so I want to make sure everybody knows the kind of classic development workflow and sees how to do it on the command line because you know when you go to a job they're probably not going to use you know unless you're lucky I think you're probably not going to be using all command line depending on where you go you probably have to use an IDE and you don'tan to go into the internet and say like yeah I'm really good at eclips oh but oh but you're using Microsoft yeah I don't know that instead you want to say well yeah I understand the development process I know all these lowlevel tools I know how to fit together and it'll make you able to learn really any development process because they're all。

Largely the same， and you can put them together with these low level tools。And lastly。

 I actually want everyone to build， get their hands dirty building some of this system software。

 we're going to build a very simple shell， we're going to build a command line tool。

 so you'll see how it actually works under the hood， we'll build a other command line utilities。

 and we'll build a lowleve compiler， you'll see how linking works。

 you'll actually be able to write C code and code in your language。And have them call each other。

 have them run each other。Okay， any questions about that。

 those's kind of the five competencies I want everyone to walk away with。Yeah。You could with WSL。

 that's why I told the difference in this one I didn't put it here。

 but I'll show when I go to the syllabus， everything will be on Eustace。For better or worse。

 so that will unify everybody's development environment。

I haven't actually used uses for class before， I have heard issues people have it of like if everyone's using it。

 but I think they've upgraded some of their machines， so hopefully it'll work out yeah。

you was just reading using for course0 task because like I remember， you。

 like the spring 24 or up then。Yeah， I required everyone to use virtualization。

 but there was a lot of people with machines that were like older and I felt like I was like shutting out people who couldn't afford like a $3。

000 laptop or something， so I figured the way to equalize it is use use this because everyone don't have the same system。

And that's kind yeah for what your colleague asks。Yeah。

 that's got of a matter when doing systems programming， there are like minor differences。

 even in C libraries like N see development tool chains， but so yeah。

 everything will be standardized by using Usetace。All right。

 so I'd like to give a little kind of change log in the software development style from previous courses。

So this course is a complete redesign from last year。

I've expanded content on the actual core system software stuff， which is the namesake of this course。

呃。As one of my GTAs pointed out it's kind of broader instead of deep into compilers as a little ad for my class which I teach in spring。

 I teach graduate compilers， which undergraduates can take。

 and that will kind of dovetail into this course if you want to learn more deeply into the compiler world I love compilers。

 but not everyone does and there's a bigger role of system software。

That that I think you can all benefit from。Programing projects are a little easier because they're sort of more well defined。

 but there's more of them。And I also have a very lenient late policy for projects。

 I've modified this a little bit to not just let anyone turn it in at any time before the MSMS。

 which you have to turn in the project first， even if you completely fail it。

In order to resubmit it and the reason for that is some student it is meant to like help students organize their time。

 but some students were like waiting sometimes still after the class is over to like start their project。

 so I want to make sure everyone is just like on time and even if。

know you actually like made the effort of just like pushing the project。

 even if it doesn't work at all， just submit something so that you you stay aware of the class。

So those are the big changes。So from the previous offering。

 so I have some other past change logs here， students were asking about sort of comping competency questions for the class。

 so I've turned this into homework。And homework is not meant to be hard。

 it's not graded for 100% accuracy， it's like effort。

 but every single class will have a homework and it's meant to take an hour or less。

 I hope maybe the readings might be a little more， but they're meant to be ideally pretty fast but they're for basically every lecture。

To keep everyone on topic， make sure you're aware of or trying to learn。

And then from the previous one， all the stuff's been incorporated already。

Not really that relevant anymore。Okay， so my actual kind of like secret motive here is to make everybody good at programming to give you all those tools that you need to be good at programming。

 and it turns out that a lot of it really has little to do with the actual coding。

 has a lot to do with your workflows， knowing the coding environment， knowing your tools。

And so to kind of and also there's a philosophy about developing software that I want to kind of imbu in everyone。

 especially when you're doing large scale， complicated projects that you can't just hack together overnight。

 I know maybe many of you can just like hack together a 200 line program and it works。

 that's much harder to do when you're dealing with say a 20 million line program like like Linux。

 it whatever strategy you have is probably going to break down at 20 million lines。

So to hopefully not infantilize you too much， I have a little allegory that I'd like to use to illustrate。

This software development philosophy is based on。But I think everyone knows the tortoise in the hair。

So these two characters of Tors and Ha， they're both giving a challenging programming project。

So what does the hair do， the hair starts coat， right， it makes sense。

Because the faster you finish the code， the faster you're done， right。

 you just got to get through it， you know， stay up overnight。

 get those 200 lines out and you're done。What the tortoise does is the tortoise doesn't even write code。

 the tortoise starts writing planning documents， they start writing tests。

I don't know how you write tests without code， can you write tests without code， tortoise does。

Writes comments before even a single line of code gets written。

And it may seem so slow that the hair actually just finishes coding their whole project。

The problem is， is that after the code is done， that's when all the real hard work begins in software development。

And that's because when the hair is given one of the tests from me or the GTA， the program is。

 of course going to break。I don'tHa anyone ever written say 2000 line program that had zero bugs？

Probably not， right， some people may I think N， but 20 million lines probably not。

So it's going to break。And so what does the hair do？You got to go fast， you know move fast。

 break things， right， they start guessing， changing code。

King it running the test again and okay okay， I got it to work。

But now another test is breaking and actually fixing that bug actually has broken another test frustrated。

And so the hair might just be thing back and forth for a while， and if they're lucky。

 they might actually get all tests working and some of you I know I' done this， I've done this。

So everyone's done this。but the hair is going to be surprised by a bad grade because we keep secret test cases that we don't share with you。

And in all likelihood， they will break if you've developed things in this way for a substantially large program。

The tortoise instead， before they even code， they start breaking the problem down into simple pieces。

So for instance， when I have to write a new program。

 I literally write Hello world because I'm almost 90% sure I can get that right， and if I break it。

 it's pretty easy to debug。So the de breaks things down into simple pieces and will' show software architecture a little bit in this class。

 but it's not really a software design class， you'll see that in like OOP。

The tortoise writes simple examples， they write tests， even before you have code。

 you can actually write tests and you can at least write specifications of the input and output。

Trtoise takes some easy piece of the problem like hellello world or reading a file。

 it doesn't write code， they write comments to say， okay I've got to read the file in here。

 okay how do I handle the path， let me write a comment there and only then does the tortoise start writing line by line little by little in the tortoise way。

 little bit lines of code testing as they go。Every line testing。

And the sorts makes sure that simple things work before moving on。

 you know you don't want to be the person contact support and they say， did you plug it in。

 you want to handle all the simple stuff first， right。

 you want to make it easy for you rather than fast。

So the tortoise doesn't make for granted that the code works because the tortoise knows debugging is really hard。

 especially when you have lots and lots of bugs as the hair discovered the hard way。

So it seemed like the hair took a lot longer to get code out and they did。

 they took a lot longer to actually get a line of code。But when he got there。

 the code was much easier to write， much easier to write correctly。And。

It probably works in most cases。So to reiterate this。While the hair was just coding。

 tortoise was writing tests， writing comments。You can think of it as pseudocode。

 but doesn't have to be that formal， can you just like comments about what's supposed to happen。

And carefully thinking about each line of code testing。All along the way。

 and so when the tortoise gets the big test cases that we have。They're probably going to pass。😡。

But they're not all going to pass， nobody's perfect。So the ones that don't。

 he isolates the test case， he makes a small version of the test case， as small as possible。

 it's called test case minimization。And he uses that to actually isolate where the problem is in the code and because the code is well documented。

 you had comments before you wrote and organized， it's much much easier to find where in the code it's broken。

 and this feels a lot slower and a lot more kind of cognitively demanding because you have to kind of consider each line of code it's a little kind be frustrating and feel slow。

But overall， amortized over the time of coding， the tortoise is actually faster。Four， I argue。

 a large enough and complicated enough code base， of course everyone can。Hack together， small code。

 but 10 million lines of code， probably not。So my ulterior motive here is be the tortoise when you're coding。

 especially in this class， because when we do this low levelvel system software it's not easy。

 it's not easy like Python， no error handling is happening for you。

 you have pointers to deal with it's tough coding， you know a 49 piece of C code is going to be。

Tough to get right。So one caveat here as I said is you know there are cases where you hack for sure。

 I'm not saying never hack， I do all the time right you fast test cases。

 you don't want to do it on like the airplane you're flying on。

 but you know on your own code if you're just，Like organizing your music library or something。

 hack things together， hack away。Okay。Thoughts on the allegory that？

Hint at something or make seem kind of clear。Okay， but that's all well and good to have this allegory。

 how do we actually do this？So。First thing you can do is know how your programming language works。

 don't just guess。😡，What the code is going to do I mean sure if you're uncertain you can write a little test and figure it out kind of empirically。

 but one benefit of this thing is we're going to dig into how programming languages work a little bit and so you'll have a better understanding of how your programming language actually works for instance pointers you'll understand at the machine level what a pointer is in C。

So this is the key one that I see a lot in students who feel like they're struggling is knowing the programming environment。

 so coding is not all about C， it's also about the environment you use。

 so being having really fast workflows to run tests and then modify code run tests。

 if you feel like you're slow spending a lot of time typing on the command line。

 there's lots of tricks for making that fast that you'll look to your neighbor and say wow。

 they're really fast， but they learned it， they learned it somewhere and I'm going to show you some of these tricks in this class。

So just like the tortoise said， break the problem down before coding。

Just like you tools were made for man， man was not made for tools。

 use the programming language tools to help you， you don't have to write a function just because functions are there and then be at the whim of whatever that program does。

 use it for the right purpose which is to break your program down into useful chunks。I mean。

 as you'll see in later classes， you'll learn about refactoring and other techniques。嗯。

This is a critical one， make sure simple stuff works before moving on。

 don't be lazy in the way that says， why I don't have to test this because you know this is just reading a file。

 what could go wrong， it can go wrong for sure， trust me， I make lots of buggy code。

Write your own tests， save your tests。Don't overwrite the same file with your new test because then you lost all that work you did making a test。

And there's a technique called regression testing where you can take old tests at work， rerun them。

 and make sure they you know。Don't break again because what happened to the hair。

 some of the fixes he made actually broke old old tests and part of this is a programming environment workflow issue。

 like if you're not fast at say making new files or opening up editors or switching back and forth between your compiler and running。

 then you can feel like it's really slow to make new files and will hopefully help solve that。

And finally develop good debugging skills， so I have a little schema here for debugging and we'll go over it again in the class。

 but the schema for debugging is just like with coding， you don't start with a code。

 you start with a test。And you try to narrow the test down as small as possible。

 especially in programming languages， narrow it down to the smallest test that will still trigger your bug。

And that will make it much easier to identify where the bug is in your program。

And understand why the bug happens before trying to fix， don't hack fixes thinking。

 I'm guessing this is going to work， let me just test it， it'll be slower overall。

 it'll work in some cases， but I argue it'll be slower overall。So this is not me inventing。

 this is not my wisdom， so Brian Knahan， one of the original AT&T Unix guys。

 wrote this in elements of programming style， something like half a century ago at this point。

 I think everyone knows debugging is twice as hard as writing a program in the first place。

So if you're as clever as you can be when you write it， how are you debug it？

So if you're hacking together in the most clever， fast way possible。

 you've given yourself a rat's nest of a debugging problem。So take your time。

 be the tortoise and do things the simple， easy， slow， clear way。

 the right code and then debugging will be that much easier。Okay。

 so just to kind of drive home a couple more points。Systems programming。

 which you're going to do in this class， will help you become a better programmer because you're got to understand how programming languages and their environments are actually implemented。

 so you'll know what the tools are doing。You'll know how the programming environment works。

And we have very light theory in this class， but if you have ever struggled with discrete or computational complexity and wondered why do I have to learn this or any math really。

 theory is a tool that makes programming easier， so functions are probably easy for you now because you've used them。

 but that's a theoretical tool， there's no actual function implementation in the machine code level。

 I argue， can argue with me if you want， but the machine does not actually run a function。

 there's no command at Intel that says run a function， there's a call command。

 but it's not actually a function。Okay， and so I just want to leave you before we get to the syllabus。

 leave you with this kind of classic。

![](img/2766ad3b86cbd21a98822aceef29c055_1.png)

Three virtues of a great programmer。By Larry Wall。

![](img/2766ad3b86cbd21a98822aceef29c055_3.png)

So some of them might surprise you， laziness is one and it's not the laziness that the hair did。

 the hair actually spent more work， it's the laziness that the tortoise did。

 doing simple things first， reduce energy expenditure， use automation。

 which is why knowing your programming environment。Inpatience。

If you feel like it's really slow to use your tool chain， find a faster way。

 there are faster ways and hubris。This is a tricky one because it's the bravery to let someone else look at your code。

 which you may think I don't want anyone look at my code。

But it's good to do that because just like any writing。

 you'll write it in a way hopefully that someone else will be able to look at it and understand what your code does。

Okay， anyway， all the stuff is linked in the introduction， so before I move on to the syllabus。

 questions at all about。Introduction so far。Okay， so let's go over。The syllabus and the course。

In detail。All right， so just make sure everyone's the right， oh yeah， yeah， go ahead。I'm sorry。

 please say。Oh yeah， absolutely， you can connect through the VPN。

 there are instructions on the syllabus， I'll point you。To them。

 you can absolutely contact U from outside with the VPN。

So I I've tried to give you all the tools you need， try to leave。No。

 as few assumptions as I can in actually completing the course， so yes。

 you can access usetace from outside。All right， so just make sure everyone's in the right place。

 this is section one， there was a long late list and the department added a lab。I think so that。

Everyone on the waitlist at least as of several days ago would be able to access the course。

 I don't know how it works， I don't know the registration system as I said。

 how you actually do the registration but from my understanding everyone that was on the wait list several days ago there should be room for them now I don't know if other people signed up for the waitlist if you have any questions ask the department。

嗯。Yeah， or your academic advisor。For questions so yeah， we're in section one。Yeah， prerequisite。

 I'm assuming you all have the prerequisites。I'm assuming everyone knows where we are。

 where we meant to be， here's the final that that date was already defined by the UCF calendar。呃。

Yeah， there's information about instructors and TAs。

 we'll use a discussion board called Ed STEM for discussions in the course。

 if you have anything more personal or private to talk about you can email me。

 but I'll be much faster to respond to course related content on our discussion board。So labs。

 there's a fourth lab added， so Brent， my magnificent graduate student， willll be teaching that lab。

 he is in the VIMC while I' am in the EMX camp we'll talk about that later， but he's also a very。

 very good programmer， he'll be covering the labs where we'll just review the material in this course。

Oice hours will be manned by me and my other graduate students， Son， I have not made these yet。

 just to take a little quick poll， I'm thinking of doing them after the class Tuesday。

 Thursday at 130， who cannot come to that。Pretty small number navy。Pretty small number， okay。

 of those people who can't come to that， can you come Wednesday can you not come Wednesday at 130？

But you also can't come Tuesday and Thursday。ははは。Because I write down。I'll send out a poll。

You it was it was a you're right。Okay， so it seems like so there'll be some combination of officers where。

Ideally， almost everyone will be able to come-， I don't know if I can get every last person。

 but I'll send out a poll on a discussion as well， since there are some people who may not be able to go。

Ed discussions， yeah。We haven't done。Yeah， it starts in the second week。

 but there's no office hours this week。You can email me if you have questions。Okay。

 here's the schedule。Grouped to very much cover the goal and cover the stuff that I talked about in the introduction。

 so this is the introduction from today。I want to point out that I will strive to record。

Every lecture， I can't certainly guarantee that this is not an online course。

 but I do that for convenience so if you miss a class or I'm not taking attendance but。

You should be coming to the class， it's in person class。

So this video what' up will be linked here on YouTube， I'll have a digital whiteboard， which I have。

Here， and if we do any stuff in class， I'll put a PDF to that here。

And then every lecture's homework assignment will be given here。

So I'll go over it more in the assignments， but this homework is due the following lecture。

 so this is the assignment date or the assignment schedule。

So this one is due Friday for the academic activity requirement。

 but all the other ones will be do the next lecture。

 but I made this align the homework one align with the academic activity so if you're on financial aid this is the homework to do it's supposed to follow the academic activity requirements。

 but all other ones will be do the following lecture。Yeah。Oh。

 that latest I'll do it during the lecture or by the end of the lecture if that seems fair。Yeah。

 or maybe the beginning of it。Yeah， does does that seem fair？

Are you looking for like getting ahead of the homeworks？

If you're interested getting ahead of homeworkmark yet， let me know。

Maybe I should take a poll on that as well， let me take some notes here。

So most people can do Tuesday， Thursday， office hours。Most of those can do Wednesday， who can't。

Can difference say。いまで。Well， I' send poll out， I'll send a poll out for this。

And homework ahead of time， so I'll put some homeworks out， try to put some out。

A little more ahead of time， and you can give me feedback if it's too little or doesn't matter。Okay。

 sure。呃。Okay， and then as we projects are not do for a little while。

 but this column will be the assignment date so that's when。I guess just like homework。

 that's when it'll guarantee to be published to do the homework。

 I guess some people may want to get ahead of this as well。

 and so I'll yeah if I get feedback on this，Let me know， I'll try to strive to get these out earlier。

 but these are going to be the latest date that you'll get the assignment。

And this column is the do Day。Or due date and the time will be listed below this is the due date so the hellello World project。

WIt sounds like an easy project right，Hello World is assigned here and then you've got like two weeks to turn it in here about or。

Two weeks of lectures， I think it's not a full two weeks， right？12 days。

Okay so that's the schedule or that's the way the schedule works I've grouped this into the kind of areas that we're going to cover so we're going to cover the file system in the abstract kind of academically next time and then we're going to dig into use the command line some of this might be simple for many of you I'll put some sort of hopefully some more fancy stuff in here that you can try out that you haven't seen I'm always learning stuff on the command line。

 new tools， new techniques so hopefully there'll be something for everyone even if you've done this before。

And then we'll learn about the programming environment， I suspect。

 even those we are go to the command line may have less familiarity with， say。

 writing make files or using Git。AndSo so we'll learn all about that here， how they work。

And we'll actually build a hellello World program， so it'll take all the difficulty of writing code out and put it all in the program environment so you'll actually have to use a command line editor and you'll have to record yourself using it to make sure everyone actually uses it and there's surprise surprise a command line tool for recording command line sessions called Scri and so we'll use that a little trick if you've never seen that before you can actually record your command line sessions。

And that's what you'll submit， you'll submit this complete。

Developed project with version control with a build system for a simple lowly hell world program。

Then we'll learn about systems programming， so this is the real kind of building system software part。

 we'll learn about actually using files at the system level Oh yeah go ahead。

It records the text and the timings。Yeah， so it's not a yeah。

 so that's the benefit of it is it's very very parsimonious compared to like an MP4 file or something so it is a text based recording system。

 I guess if you're really clever you could， you might be able to svert us but。If you're doing that。

 then you might as well just record it。Okay， soll actually get into systems programming so how you actually use your operating system。

 I think O this sort of overlaps with O， but this is more from the view of actually trying to build some systems software。

 So we're going to build a command that will list files that'll have some extra bells and whistles so it's not just a pure LS or DIR command。

We'll learn about process creation and process IO and that will help us actually build a command line shell so you'll actually build a very simple command line shell and you'll see it's not much more than like 50 lines to build a command line processor and so you can see how it uses the kernel and the access to kind of the virtualized hardware that the kernel gives you to run a command line processor and that's why the shell is。

 I think it's why it's called a shell because it's a very lightweight interface over your operating system。

 but it gives you exposure to lots of the functionality of the operating system。Which we'll see here。

 we'll see here all the functionality of the OS that you can exploit from the command line。

There will be a midterm in this class， I can't remember my rationalization。

 I think I just wanted to break up the class a little bit。And it's in person， it'll be in the class。

 it'll also mean you don't have to remember so much for the final， I think that's why I。

I strategically added it both exams will have a review session so the lecture before will have a review session I'll give you the format of the tests。

 I'm not trying to trick you with formats or anything they have a limited number of notes you can bring with you you know if you need SAS I have those emails that'll be set up for you。

嗯。Yeah， so we'll have a midterm exam。All right， yeah， go ahead。It's paper， it'll be paper， yeah。

 I can't think of a good way to do。Yeah， digital。I know there are techniques。

 but invasive techniques。I'm just going back to old school paper and pencil。Okay。

 so the first half is kind of using and building system software and the second half preserves this system software history of compilers。

 which I love I love the compiler world， but here we're going to focus on more the back end。

 the low level parts of the compiler。In particular we're going to see how source code actually not just gets turned into machine code or intermediate code or virtual machine code。

 we're going to see how it actually goes through the operating system because the operating system is involved in invoking programs。

And we'll see how some of these kind of classic programming tools work like functions， library calls。

 how they actually work at the systems level， and we'll build tools that will spit out machine code that will interoperate with the rest of your system you'll be able to use GCC and other tools to combine your software with other C software and other C libraries so I think that's pretty cool to look at because you actually see how this works under the hood。

 it is a little complicated but it'll be a kind of simplified version of this。

 we're not going to deal with some of the more sophisticated techniques like dynamic loading and things like this。

And then it'll be a pretty straight ahead。Compils courses at this point where we're going to see how each of these language features。

 which I'm sure all of you have used in C， actually get implemented at the low level。

 particularly pointers， So pointers are I think always mysterious for students at the beginning。

 We'll actually see how these translate into。And we're going to use Intel because we're on Ut。

 we're going to use Intel and machine code， we'll see how these actually translate Intel Ma code。

 how functions work， and hopefully that'll open your eyes a little bit to how know they're actually they're simple in a way that makes them hard to use。

 but they are fairly straightforward in their implementation。

 they're just kind of complicated to think about。And then yeah we'll have a final exam review。

 so this is Thanksgiving week so I'm going to put a special topics class there that。

Probably's not going to be on the exam I don't know yet。

 but I'm guessing people will be out so I put the review the week before in case people are out and then the final exam during the final exam period and there'll be more details about the final exam I have not written these yet。

 but they'll be based on the homework， the projects and the lectures and you'll have some limited amount of notes that you can bring but I'll give you a practice exam before both of these so you'll have some expectation about the content。

Questions about。Schedule。It's pretty intense， you know。

' we're going through a lot of topics pretty fast， but I'm trying to go a little more broad。The deep。

This is the first time I'm offering this， so I haven't calibrated pacing yet。

 you can give me feedback on the project submission。

 remember the project submission is a very leient late policy and homeworks。But yeah， you can let me。

 I haven't calibrated exactly yet the pacing of the course。

 but I think we can get through all of this。Okay， so let me tell you about the grading structures。

 so this is all the kind of mechanics of the course， so it's very。

 very clear to you exactly how you're got to be graded。

So one thing I like to do is make a point in the class on any assignment one percentage point of the grade so you don't have to like play with web courses or ask me what's my grade going to be。

 you can very easily compute your own grade so you just see how many points have been given so far so if there's 10 homeworks in one project that's like 20 points and you've got 15 and you have an estimated grade right if you've got 15% or 15 out of 20。

So hopefully that makes things more straightforward。

These are all the categories of things that you get grades for， so first is homework。

There'll be roughly one per lecture， one for all the lectures that have content。

There's eight projects。There's a midterm and a final and this mysterious participation category。

All right， so let me go over each of these， what they are when they're due， how they're graded。

So yeah， okay， so homework is due before the following lecture。1159 a。

I sort of like 24 hour time because it makes this less confusing， but this lecture is at noon。

And before the lecture， in my definition means 11，59 a， so get it in web courses。So for example。

Here's a lot of numbers here homework 15 is assigned in lecture 17 on 1015 and it's due the following lecture 18。

 but let me show you the schedule which will make it allows user to see that so homework。😊。

I'm kidding myself now， so homework 15。Homework 15 is here。Orwork 15 is assigned。After this lecture。

 so it'll be a homework about parsing。And it'll be due the following lecture before the following lecture。

Questions on that， does that make sense？So whatever the following lecture is， so that includes。

 say the review。So whatever the following class that we're meeting， this is going to be due。

So webCses does have all of these deadlines already set， so you should see them in web courses。

Questions about that。There's no late for homeworks。Sadly。

Because I'm just going to go over the homework in the next place。

 it's meant for you to like keep up with a class， but they're not graded for correctness。

Not 100% correctness。 They're grade for like a genuine effort to do。

To do it to read or answer the questions so you know don't。Freak out like， oh。

 you know I'm going to wait and try to argue for getting late because I don't want to lose points because it's like not complete。

 just submit it， submit what you have yeah。Oh， that's good well， I guess if you get it wrong。

You'll see homework two， maybe I'll put homework two up。So homework one is due Friday。

 homework because it's the academic activity， homework two， I'll show you next time homework2。

 so it's a little complicated you have to figure out a file system andfer a file system tree。

 and so if you just get it wrong you make like a little mistake or you make a couple mistakes。

 you're still going to get the point。So for example， I'm going to list I'm going to give you。

 I mean I feel like publishing it but I'm going to give you a list of file paths and then you have to construct the tree out of the file paths so it's a little puzzle solving exercise but you might get something wrong you might forget something you're still going to get a point if you just submit that broken。

Result。If we just submit like a blank thing， we have graders are going to check those。

 so don't try not to subvert。Yeah。一しは？Yeah， yeah that would be example so the homeworks are going to vary quite a bit。

 so some are just going to be like so one of the homeworks is do the EMX or Vm tutorial。

AndSo it's very hard to check that， so I have a little question survey question。

Some some is like this file system exercise or it's a very concrete answer some are like readings and then like tell me what you learned kind of things so there's a variety of them and we're just you know we just want to make sure people aren't。

you know trying to subvert the grade you know like actually keep up with the course。

 they're meant to be an hour or less so I guess if if you're taking a genuinely working at it and it takes you like three hours don't do that you know take an hour the reading might be a little longer。

 I haven't calibrated the reading but。Just generally try to do it and we're going to have a little sanity check to make sure nobody's completely like。

Just putting blank stuff or copying yes or something， unless I ask for just say yes。

 some places I may ask you do that， but just so you're not just putting the number zero and saying。

 oh， I got it wrong。You so。Just try to you know academic code read the rest of syllabus。

 academic integrity， actually try to do it， we're going to have a little sanity check。

 but I don't want this to be like a big headache for you。

 I know anything requiring punctuality is annoying but these are not meant to be like hurting you on your grade these are meant to be kind of freebie points actually。

Like。Unless you really messed up your schedule or you have a legitimate like you're out for medical reasons or something。

 this shouldn't be an issue， I think it's really just planning and I hate kind of grading people on their ability to be punctual because I was never good at that but these are like meant to be really easy things are meant to be easy but you can let me know if it's like you're spending three hours on it know don't do that let me know it's like this is harder or come to office hours or lab。

To get feedback on it。Questions， questions on homework。So because we go over it， you know。

 I don't know how to do late for that because we're just going to go the answer next time。

But the way I compensate is it's not created for。You're not going to get zero if you actually tried to do it。

Okay， projects， projects are quite different， so these are due on the date in the schedule by 1159 pm end of day。

's because the lecture happens to be at noon。That's why we have this。You know， same looking number。

 but that's why I bolded this to make it clear that the projects are due。The end of day， 11， 59 pm。

So for instance， this Hello World project， you'll get it on or before September 5th in a couple of weeks。

And it'll be due September 17th at the very end of the day， 11， 59 pm， Eastern time， you know。

 Florida time。That makes sense。Okay。Okay， so this is the change from previous years。

 you must make some submission by the due date， something。

P something put something in the repo to see that you're like alive and you're doing the course you haven't completely dropped out or something。

 if you don't do that then you can't resubmit， but if you do that， even if it's like very very basic。

You can submit as often as you like for regrading， I mean， you have to ask the Ts to regrade。

But you can resubmit and retry。As much as you like so that way you'll see the grade and you'll say okay。

 I got some private cases wrong， let me go to office hours because I really want you to actually like finish the project and not just like be incentivized to cheat or rush through it because you're like。

 I got to get the grade。So I want you to actually try to finish these projects because I think they're fun。

 I think， outside of the class context。呃。But I think they're also valuable and they're not that big。

 and you'll be able to resubmit them as much as you like。knowIn the kind of behavioral economics。

Way I'd like to make it you know no penalty for late。

 but then like everyone's just going to turn in late， and so there's a very， very。

 very tiny point deduction， 0。5 of a point。So you can still get an A if you turn everything in late。

And there's opportunities for bonus projects to kind of compensate for that。

 but this is really just kind of a。Bevior hacking to say like， oh。

 you're going to get a little penalty， so try to turn it into with that。Yeah。

 so there's eight projects and so you can you'll receive a maximum of four points deduction。

 eight deductions， you won't get it every time you submit it it's a one time penalty for resubmitting so yeah here's an example here here's a couple of examples。

So somebody submits this My LS project on 103 after the due date， that's their first submission。

 they receive no points and they can't resubmit。As soon as submit missed the project on 101。

 by the due date， but they totally crash and burn， they fail it。

But then they submit a fully working project 119 well before the final deadline， and they get 5。

5 out of six because it works perfectly but they get a 05 deduction。

And they can resubmit as much as they want and then the rock star student who's like hacking away all night long。

They submit it on the due date and they get a perfect score and you know that's where you'll get six out of six So this is not meant to be like killing your grade。

 this is meant to be you know hack your behavior a little bit to say like you get a little penalty for late yeah。

Yeah， yeah， so so we don't have like， it' would be nice if we had sort of continuous integration setup up。

 we do have Git set up on use thanks to Stephen Dick and the ITP people at CS。

 they've actually set up a Git server for us and the classes。嗯。

It's feasible to have a continuous integration but instead you'll like ask a GTA and say。

 I need you to regrade this， please regrade it， and we'll try to do it， I don't know weekly。

 something like that or try to do it on demand， I'll talk it depends on how much demand we get for it。

 but we'll try to get it this closing response or you can come to office hours and I'll try to rerun it。

Yeah down。No， no more GiHub， so another big change in this class is no more GitHub， thankfully。

 too many students were dragging and dropping to the website， giving themselves merge conflicts。

And this way， Git is entirely on the command line you have to use。The command line。Or or less。

 there are ways around it。We'll， we'll learn， we'll learn how to submit it。

 so right here we're going to go reverse version control。

 that's why we have a hellello world program。So a program that I know everyone will be able to write correctly。

 including myself。But you'll learn here how to use Git actually。

 and so you'll know if you've successfully done it and I have code or commands that'll show you how to actually check yourself。

So that's the beauty of this kind of DIY。Open source world， you know。

 test everything yourself is you can actually just grade yourself except for our private project。

 our private test cases， but in the real world you're not going to have some。You know。

 authorityuthity on high who knows all the test cases you're going to have to develop in yourself。

 but I'll show you how you can actually check yourself。

That you've submitted it properly and that it's working properly。

 will'll show you basically the commands we run。Degrade it and you can just run those yourself Probably we should share the automation script too。

 but we haven't developed them yet， I haven't figured it out。

 but I'll give you the commands you can run to actually check that you've submitted your project via get properly so you won't yeah so you can always kind of it's like I say it's my student that's kind of like you know you're in a forest you don't have a map it's kind of how make your own map if you just run through the forest and circles you gonna like。

Get dehydated and maybe die， but if you make a little map and record your steps along the way。

 then it'll look like you know what you're doing， you know it'll look like what you're doing。

 but really you're just using these cognitive tools to not rely just on your own kind of。

Iy memory and iffy abilities， so that's what these tools。

 you know that's the tools made for and not for tools。

 so these tools will help you verify yourself that your code is working。And that makes sense。

 we'll see when we get there， we'll see we get there， I'm seeing some puzzled looks。

 but we'll see it when we get there。All right， other questions， other questions on projects。Yeah。No。

 they're all individual， did I put this here？I didn't put this here， they're all individual。

 let me make a note to clarify that。Actually， maybe。I don't remember if I say that。

 but yeah they're all individual products， no group projects， I tried that once。

 but I won't do it again。Yeah， no group ro not for this class， not for this class。

You'll do group projects in like when you actually do softwarefur development where you actually need separation of labor。

 but this class， everyone should be competent at the projects yeah。Oh yeah。 This is hard。

 I don't have I've seen other syllabi and other schools where they really clearly articulate this。

 I'm just going to kind of defer to the。What do they call the golden rule or the golden rule。

 I'm going to defer to that about academic dishonesty， so there's text here。

That describes unauthorized assistance。know do it yourself。

 but a lot of the material is going to be like documented online。Like how do I read a file in UniX。

 there's like billions of examples-， chatTT can write it。

I probably can't write the examples we're going to give， I think GTA is actually testing that out。

 but I think the examples， they might get you part of the way there。

 but then you'll have trouble with the exams， that's why I did the exams in person because。

If you don't know how the system works， then you're not going to pass the exam。

But this is like common enough tools that there's like voluminous open documentation about using stuff and examples。

So yeah， I'm going to just defer to the policy statements here about unauthorized assistance so use your best judgment don't share like code。

 I mean some of the documentation just has code in it， like here's how you open a process。

 the book will have it and so you can use that that's not unauthorized assistance so I've given you the book。

It's putting it together that is the real challenge。

 the kind of Lego building and the puzzle solving that is the challenge。And if in doubt， you know。

 ask me。Or come to off hourss with your friend or something。Maybe I can supervise or something。

 but use your best judgment in this， don't cheat basically。All right。Other questions on projects？

So it'll hopefully become clear when we get there。Okay， so final， midterm and final， yeah， go ahead。

ててい対策さけな。Aha， there's no Gitthub。Gitt is not GitHub and GitHub is not Git。So yeah。

 GitHub is one of the more popular。嗯。Cralizers of a decentralized version control system。

 but Git is a decentralized tool that anyone can install， you can install it on your own machine。

Be the official and there's no one official。It's on useless already。It's already there。な。じ丈位ぞ。

It's going to be， it's not going to be hard， I'm going to walk you through every single command that you need to run。

Just practice， it'll be like muscle memory， you've got to practice a little bit。Okay。

 midtorman final， it's got to be taken from homework projects and lectures。

 so projects so that you're not just like。Blatantly cheating and not understanding what the code does。

 so I'll ask you stuff， you know about writing code maybe there。

There's certainly electronic ways to cheat on paper tests， but they're I think a little bit harder。

 but yeah， if you know the stuff from the class and you can kind of at least know the concepts of the system program。

 if not the specific details， it should be final on the final。

 but there will be questions from the projects as well。We'll do it in Cl review， as I said。

 there'll be very limited open notes。The in class review will have like a version of the test with different questions。

 but a similar format so you don't get， I'm not measuring format like leakage of format understanding。

 which is a real thing in testing。Okay， in participation， this is the fluffy one。

 so I don't really have。Any specific thing to do for participation。

 but some examples of participation is showing up to class。But attendance is not taken。

 but a short class。I sort of can match the face of the name。

 asking or answering questions during class， participating in class discussions on EdTEM。

 our discussion board， coming to office hours。Just be present， you know。

 be physically here if you are physically able to and always of course let me know if there are sort of administrative or medical or other issues that are preventing this kind of participation。

 but that's very small， it's like four points。So now all the numbers are nice。You know。

 binary style style numbers， so that's why the participation kind of works out that way。

Are you taking attendance no， I'm not taking attendance， I'm not taking attendance。

something I also have done in the past， which is。Very， very hard。You can do it through quizzes。

 actually， it's one way to do it。All right so bonus projects so this is even more fluffy and more vague I'll kind of pepper projects with like bonus things to try so I kind of give the it's kind of like a video game you know like a Nintendo style video game where it's like there's like an easy way through it and then there's more challenges in there so I'll throw sprinkle some extra challenges for you to try the kind of harder versions of the shell or extra things you can do with LS or more complicated things you can do with the programming language。

But really this is on you， you know this is not formalized。

 so propose it to me or come to office hours at some point before the final exam。

 before all the projects are due up to six points because it'll recoup。

Actually recoups more than the bottom but more than the it's eight projects， yeah。

 so it'll recoup a little more than the what you would lose from late projects so it's one way to kind of compensate the late penalty。

Questions on that， I know these are more vague， it'll be more clear as the class goes on if you want to。

 and if you have an idea yourself， they just hey， I want to implement so I had students that like I want to implement a raise in this language which we don't have and they're like。

 okay， yeah try that， that sounds good then they did it。Questions questionsions on this。Okay。

 so this is a letter grade scheme that I've used for many years， I haven't had an issue with it。

 and anybody have an issue with letter grade scheme。I sort of reserve the right to use a minus。

 but I don't know if I ever have。Maybe， but this is the scheme。

 I think I just took it from a prior instructor。Okay， so I think this is the last part。

 so let me go over logistics， so this is a guide that will show you everything you need to complete this course。

 all the tools， where to find them， guides on using things。So。For the syllabus。

 I know there's a syllabus on the web course as well。

 I'm going to keep the syllabus here as kind of the up to date one for everyone。Lecture notes。

 so every time I have a class I'm going to publish the slides in a lecture notes format， the videos。

Homework assignments， they actually will like descriptions of the homework assignments。

 project descriptions。These will all be available on this website。Which is linked from web courses。

So basically everything， all the kind of textual content you need to complete the course will be here on the website。

So for projects， I let to go to homework first， actually。

 so homeworks to make it a little confusing is on web courses。So they're kind of。

 if you've seen web courses like homework 1 through 24。

 and you'll have to do a little matching exercise to make sure you put the right homework in the right spot because I just open them all up。

That's on web courses， so that's like the only thing you need web courses for。

Is submitting homeworks？And just like the links to the syllabus and the discussion board。

That's all you'll need web courses for。agree。Your grade is also yes。

 your grade is also there so grade but I mean for the interaction that you guys have to accessing the course and contributing good course that's all you need web courses for so yeah we will use that that is the official system we use it'll go to your grade eventually so that's all Web courses is for。

😊，Project submission and implementation will be on usetace for the implementation。

 so everyone should have access to useT now。And we're going to test on Useustace as well。

 so if you want to go use a virtual machine or test on your own machine kind of at your own risk。

 you can certainly like come to us and say， hey， and know I want to regrade it。

 you can also it's gi so you can also just clone it。

Back to EtAs and try it there you can test it out there so feel free to you know develop on the command line if you really want to go that route but I expect project implementation be Eust so that's the service that UCF is providing for the project implementation。

Project submission will be via the Git server。And I'll talk about that in a second。

 we'll actually do that through Eustace on the command line entirely。To submit。

The code to get so if you've never done this before， which many of you I think haven't。

 know you probably wouldn't have had to do this， not for class usually yeah we'll have。

Very careful set of instructions on how to actually do this and then hopefully you'll get good at it and you'll learn I've had a lot of students say I'm really glad I learned Git know I went to an internship and they were using Git it was like no problem for me even if you used the git like UI。

Git has very kind of little some esoteric parts to it， so even if you have a UI。

 it's not going to help you understand what Git is doing。

 but if you use the command line very fine grainined， it'll show you exactly each step。

Using version control on the command line， at least get it version。Okay。

 and then for all questions and discussions， aside from， you know。

 that you can send private messages on Ed discussions。

 me and the TAs will be more likely to answer questions there or faster， my inbox is very large。

 but if you have like personal or other kind of procedural issues can of course send me an email。

And you know， send me an email again or come to office hours so we can discuss。

 but I expect that all questions and discussions， announcements will be on a discussion has anyone used a discussion before who's used it。

Very cute，Okay， so that's the overview of the logistics。So computing resources。

 because I don't want to assume you can have a laptop or a computer or even one that works really effectively。

UCF actually provides loaner equipment， right？Do I have this right， I think they do。

 they actually provide loanner equipment。And there's computer labs that I think you can go access EustAace and complete the programming and assignments with。



![](img/2766ad3b86cbd21a98822aceef29c055_5.png)

![](img/2766ad3b86cbd21a98822aceef29c055_6.png)

And you can actually borrow laptops。Wwhich I found out。

 so you can actually do this course without you know very minimal cost besides like tuition or if you're on a scholarship。

 very little equipment cost。Here's web courses I assume everyone kind of knows this already。

 so I just linked to their support， so if you haven't used it let me know if you have questions but you can check out the support。

Online。Okay， so here's the useless this instructions。So this is the server， you put your NID。

 your password， who's not used， Eustace。OhOkay， so in some number yeah。

 I don't know how prevalent it is for like CS1， CS2， maybe some people use itIS。Oh， justin CIS。

YeahPeople used to use it and actually there's a guide here from。P offering of the course。对。



![](img/2766ad3b86cbd21a98822aceef29c055_8.png)

Well， Jimlaskey， when he was here， had a guide。

![](img/2766ad3b86cbd21a98822aceef29c055_10.png)

Where you guess it。Okay。でいいす。Okay， so's。Kind of professor dependent。

 so it least seems like a lot of you did I'm kind of reviving it using use this again。

 I think they've upgraded hardware， I don't know use this， but。At some point over the years。

 and they've added other servers。The good server， the machine that the good server is running on。

So this is how you'll connect。Now you're probably wondering why do I do that。

 where do I type that in， we'll go over that in class， I'm not going to go over all systems。

 I'm going to put guides here for each operating system how to run this command。

So if you're on Linux， it's very easy， you just open the terminal， if you're on Mac， it's very easy。

 you open the terminal application。And you can run this command， replacing your NID。

And if you're within。The campus， firewall， you'll be able to access Eustace。

 if you're outside of campus， you can use the VPN。So I put a link here to the instructions。

 they might be out of date。Oh yeah， I put into the search results because they recently。

 I think they changed how the connection works。At some point over the past years。

 but so I've put a link to tech support on that。And also some guides here from other professors。

 Zmlansky and。

![](img/2766ad3b86cbd21a98822aceef29c055_12.png)

this is Kevin， Kevin Moran。

![](img/2766ad3b86cbd21a98822aceef29c055_14.png)

And if you really want to get fancy and not have to take your password every time。

 you can check out this guide on setting up an SSH key。Okay， so this is the Gi server。

And we will go over how to use Git， we'll go how to actually make repositories on this。

 great thanks to Stephen Dick and CCS who set up the Gitservver and we worked out how to configure it and everything。

 and so you'll just be able to create repos under your name sorry repositories under your name at will for all the projects。

Okay， and this is Ed STEM， so I'll just send you guys an invitation on EdS STEM through your NIDs。

Okay， five minutes left and we're almost on the syllabus has a lot of content。

 I just want to make sure everyone is clear on all accounts。

So these are required textbooks that are free for you to access。

So also special thanks to Lily Duba at the university libraries who got this book for us。

 this is a really nice more modern Cbook and the first like five chapters are not about C code but about programming environment which is perfect for this class we'll learn about make and auto tools and stuff now there are some。

Pretty wonky instructions for actually getting this material which I will go through briefly now for both of these actually look over these instructions very carefully there's a little illustration here the one thing to not do is read online if you read online your institution has one copy you will block other students and make them very unhappy and then we'll have to go to the library and get them to like unlock it do not read online。

The thing to do is to download chapters and you can download PDFs there a not DRM or anything。

 you can download up to a certain amount per day， I know it's very wonky licensing and this is how we got free textbooks for you guys。

And so these set of chapters for this book can all be downloaded in a single day。

By a student so you can download all these in one day if you mess up or download a different chapter。

 you just wait till the next day， I know it's a little wonky。

 but follow these instructions and it will give you access to digital free copies。

 do not pirate them， but digital copies of this textbook。And same for this， same for this book。Okay。

 and questions。Yeah。Curve， no， no curve， I don't believe in curving at least at least not now so my goal is to have a kind of well definedfin absolute set of competencies and abilities you should have and you should meet those and I try to make them reasonable for all people taking this course so no curve and also means cheating doesn't hurt your picture your colleagues yeah。

we know assignments for the lab， there's no lab this week。And lab will just be reviewed。

Of the material， so Brentt will prepare some material and then you'll be asked questions。

That I don't know。I guess if there's space， but I would ask the department if that。

It will be the same teacher though all right everyone。

 have a good one and see it Thursday homework is up。



![](img/2766ad3b86cbd21a98822aceef29c055_16.png)

あては？