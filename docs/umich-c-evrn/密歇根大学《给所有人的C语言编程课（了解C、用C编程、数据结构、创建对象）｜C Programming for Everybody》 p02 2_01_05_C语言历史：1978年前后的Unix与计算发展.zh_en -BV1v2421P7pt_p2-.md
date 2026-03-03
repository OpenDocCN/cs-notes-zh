# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p02 2_01_05_C语言历史：1978年前后的Unix与计算发展.zh_en -BV1v2421P7pt_p2-

![](img/953b895853090bb820963d396d92b8be_0.png)

Hello and welcome to C programming for everybody。 This lecture is putting C in a bit of a historical context。

 Now， if you're watching this lecture， you're probably familiar with some of my other classes。

 I just want to kind of let you know that I've been building a lot of classes。

 Most of you probably took Python for everybody available on courseursera at X and many other platforms。

 but I have a series of classes that are designed what I call the path of the master programmer where I try to start people that no matter where you start。

 I want you to be able to learn to be a really good programmer and you follow along as far as you want。

 These are all my materials， they're all 100% free open and online。

 and they're really aimed at teaching everybody how to program。 I mean。

 I started doing this back in 2012 with Coursera。And。

I have dedicated myself to making all my materials free and to create a path that anyone can take anywhere in the world。

 regardless of economic challenges or other things in your life。

 I want everybody to have an opportunity to be a professional developer， so I encourage you。

And frankly， if you haven't taken Python yet like my Python for everybody class。

 this course is going to be a little bit difficult。So let's start with a history of C。

The book we're looking at， the Carnegan and Richitchie。C programming language by Brian W。

 Carian and Dennis M。riie was published in 1978， and the key thing is that it is a moment in history where everything changed。

And， and so we're looking at this textbook and the text in this textbook and the language itself in the context of how it is impacted history。

 The C programming language itself has a long history。 There was a language called B。

 and they were using it at A T and T of Bell Las to build utilities and operating system stuff。

 But it was a little too word oriented。 And so they this language C was as new。

Computer hardware came out that supported byte addressing and the ability to load a string of bytes and store a string of bytes rather than a set of words。

 words being larger than a byte and more than one character were packed into words and kind of like the 60s and early 70s。

C wanted to make a character a sort of core low level v kind of data that the language would happen。

And from the early and mid-70s， the C and UniX kind of co- evolvedvolved。

 they wanted to build something that would make UniX work well on a PDP 1120。And at the same time。

 make it so they could port Uniix to other systems。

 but really it was about PDP 1120s cool memory architecture having to do with byte addressability。

And what happened was is they were carefully rewriting Uniix in C， but then fixing C。

 laying the groundwork for UniX portability。And so by 1978， this KNRC book was published。

 and at that point you could think of it as a summary of over a decade of research in how to build a portable programming language and then use that portable programming language to build a portable operating system C in UniX。

 of course。By 1989。TheC had become popular and there was a need to standardize it。

 so there's a variant of C called C89 that is the anNI。

 and then that same version was called C90 is ISO， ISO， the International Organization of Standards。

 also standardize that and so that was our first version of the C that we could all agree on the AnNSI did not intend to go too far away from what we call KNRC it but instead it just sort of nailed down a few things that by then werere important to nail down。

And C has continued to evolve from sort of 1990 to the present。

 and there's a number of major revisions， but the key thing that these revisions don't do in the modern version of C is they do not attempt to make C easy to use language。

 say like Python or JavaScript， and they C knows its place in the panoply of languages and does a good job of that。

So if we look at sort of what's the future？C is a difficult language to use as a general purpose language。

 Python is a great general purpose language， but it's not a great systems programming language。

And the two things that are missing from C are the lack of really solid dynamic memory support in the core types and libraries。

 and then there is no safe string type， strings are not， there's no string in C。

 it's character arrays， and arrays have sizes。 and if you start putting stuff beyond the boundary of that array。

 things just blow up。And C+ plus is， to me not the。The sort of future version of C。

 it's really a more powerful， intricate and flexible version of C for programmers who are doing really professional intricate systems applications。

 writing Good C++ in some ways is more difficult than writing Good C。The languages that sort of。

Take on in the seas mantle in the general purpose are things like Java， Javascript。

 C sharp or Python。 The key thing with these languages is they don't。

Give you sort of strings as just raw bite arrays。 and they。

 they give us a simple object oriented layer that keeps us away from the metal。

 The goal of C is to get close to the hardware， close to the metal。And so Java， JavaScriptscript。

 C Sha， Python are all great languages and they're great for what we use them for。

 they're just not well suited for writing an operating system kernel。

The most likely language that is。Like C， like the next C is probably rust。

 The idea of rust is that it stays close to the metal。

But then gives us some simple and safe core data types and recently Linux is starting to accept some rust in Linux。

 and so that means that rust has to be mature， it means that rust can't be like evolving rapidly。

 I've seen situations where operating systems like MacOS like decide to depend on Python。

 so there's parts of Mac OS that depend on Python 2。

 but then they can't really upgrade to Python 2 because their operating system blah。

 blah blah so for an operating system to depend on a programming language like rust。

 it really has to be mature and even more importantly stable。

 you can't have clever innovations in the programming language causing regressions in an operating system。

 say like Linux so look for rust。Now， C has been around a long time before C。Called C starting in 72。

 the book is published in 78 before C， most of us would write a similar language or Fortrann。

 Some people wrote P1 that's not on here。 Fortrann is not really a general purpose programming language。

 You wouldn't write command like Cat in Fortrann。 Fortrann was really for scientific computations and the earliest of computers in the 50s。

 60s were。Either sort of。Really specialized toward like payroll and HR systems。

 or they were really specialized to doing computations and the ones that specialized were the science ones were used forran because it was just the right language for those computers that were aimed at doing scientific calculations。

See as a language。Was kind of none of the above in that it was aimed at writing system code。

 a kernel， an operating system and the utilities around it， including like other languages。

And so C is kind of the mother tongue of all kinds of other derivativeri languages and things like the bashell。

 Pearl， Python， PH P， C plus plus Javascript， Java and C sharp and objective C just kind of were derivatives of this beginning of C。

 And that's why you see a lot of patterns in these other languages that are similar。

 And that's because Javascript and Java， both inherited their for loop syntax from C。

On top of this history of the C language， we can look at a brief history of computers。

 and I have a whole。Course called Internet History Technology and security that really starts in the 1940s with a focus more on communication rather than computation。

 even though communication and computation were very much connected throughout the 40s through even today。

In the early 1950s， computers were you'd best think of as like a multimillion dollar strategic asset。

 every single computer， and a lot of them were custom built。

 the first computer at Michigan State University where I went to undergrad was built by the electrical engineering students of that university based on some designs that they borrowed。

 I think， from Iowa。And so things like the programming language， the operating system。

 you didn't have a lot of generalization， you didn't have a lot of sharing。

You tended to write code and put it on a paper tape or later a mag tape and loaded it in run it。

 And so you were just pretty happy if the code worked， you didn't need an operating system。

 these weren't multiprocess computers， and so the software environment was very minimalist。

But in the late 50s and early 60s， you saw companies like IBM and Digital Equipment Corporation began selling general purposese computers。

 they just could make them， and they started selling them and they still were expensive and they were only in like a business would have a couple of computers to help them do payroll perhaps or something like that。

 something that was really， really important because the computers were expensive。

But in the 60s we really got to the point where the computer componentry， the chips， etc。

 were becoming commodities。 You could just go to a place and buy chips。

 and then you could make a computer by buying a bunch of chips and putting those things together and because you weren't building everything from scratch。

 the cost got a lot lower。 the other thing that these less expensive computers or they were a little slower。

 but by the end of the 1960s， there was a lot of computers， there were some super expensive。

 weird one offs small production computers。 There were computers that had there was like the previous generation in many computer where there were lots of them laying around old computer science departments or a businesses that there weren't sure what they did with to do with them。

 they wanted to buy a new one。And then there were just innovative new low cost computers coming out and in the 70s in this milieu of just lots of new and old computer hardware。

 the question was is is there a way we can do things with all of this old hardware。

 and is there sort of one solution and that's where UniX and C came？And certainly after the '70s。

 we look at the '80s and that's where microprocessors and personal computers。

 and so we went from computers that were sizes of refrigerators or desks to the size of a computer could be on a single chip。

And in the beginning， those personal computers like the IBM PC or Commodore pet。

 they had really bad performance， but that performance。

 once you could get everything on a single chip， that performance could get faster very quickly and because。

Personal computers became a mass market item， a lot of money could be invested in personal computers。

By the 1990s， personal computers continued to grow but the need to communicate and talk and exchange information became important。

 and so in the 1990s we saw really an increasing focus on connecting computers with the internet and other kinds of networks and the performance of these computers and the price kept going down。

 the performance kept going up。And then by the time we get to the 2000s。

 Amazon's AWS was founded in 2002， and it used personal computer microprocessors like from Intel and produced computing as a commodity。

And so you don't even buy computers anymore， you just go to Amazon and say。

 I'll rent a computer for $7 a month。And so。We see in 1978 we see this moment where we are going from the computers were becoming more common。

 they're going down in price and there's getting to be more and more of them and there was a diversity of computers these days there's actually less diversity so let's take a look at the operating system Mux is the operating system that is connected with C。

In the 1960s， there was a multiuser operating system called Maltics。

 and then in the 1970s they wanted to come up with yet another operating system and they called it eventually called it UniX and the deck PDP 1120。

 which was one of these new commodity part based computers that was coming into the marketplace。

And so in 1973， UniX was rewritten in C， but it only was there on the PDP11。

 although they had laid the groundwork for portability from the beginning。

 they knew they wanted to have everything be portable， they just couldn't make it all portable。

 the first version， they just had to make it run on the PDP11 and then by 1978。

 the UniX the second computer that UniX had run on was an Inda 832 and that was quite a different computer。

 and so it was good， so they really learned a lot about making UniX a portable bit of software。

In the early 1970s， C was evolving in a way so that the UniX could be ported right so it's like we got this problem between。

 let's just say the PDB 11 and the In datata and how can we fix this and we can both change how the operating system works。

 we can change the operating system code and we can change the C compiler and then we can rewrite the operating system code。

To get less and less assembly language and more and more see language。

 And so the idea was to get to the point where there was a very。

 very small amount of assembly language in Uniix。 and over the years， that's gotten lower and lower。

Unix was rewritten， a number of versions came out in the 70s having to do with their portability。

 so by 1978， the UniX version 7 could also run on a whole new architecture from deck called the VX Systems。

The University of California， Berkeley had their own distribution of UniX called BSD。

 the Berkeley softwareft distribution， and that was really cool because universities often pushed things like networking。

 TCPIP， ARPt， BSD UniX was the first place some of us saw TCPI。1982， a company based solely on Unix。

Called Sun microcro systemsytems was found。 Sun was some work at Stanford， some work at Berkeley。

 all based on Unix。 And they created what， in effect。

 was the Unix workstation marketplace At this point。

 you could imagine that the world was about to just。Adopt Uniix。 Unix was the greatest thing ever。

 Computer science departments were。Teaching UniX and their operating systems classes in the mid '80s。

The problem became A T and T had never come up really with a business plan for what the purpose of Ex was。

 And so there was。Some fits and starts as to how they could monetize this extremely popular thing。

And。TheyThey didn't do a great job， and it took them a long time to figure out what was going to be successful。

And by the time。ATT& T sort of figured things out。The market had moved on and so。

Mix is an operating system that was developed in the Netherlands by And Tanbaum。

 and he built a completely free and open source operating system that was used for education。

 He built a textbook around it， and it was very popular。But he didn't want。Commercialization。

 at least not that point in time。 So he sort of， he sort of held on to it too tightly again。

 kind of an intellectual property mistake。 And in 1991， a program called Linus Tvalds。

 He decided he was going to build a fresh ground up implementation of the Ex kernelel。

 That was 100 per cent free。 So he wasn't going to use Ex。 He wasn't going to use Minx。

 He wanted to create another thing。 And originally， it was just like a hobby。

 I'm going to try to see how far I can go By 1992， Linux started to work。

 and it adopted this license called the the GL， which is called the Gnu Public Library license。

 which is a strongly open source license in the way that it's difficult to take。

Linuxinux out of open source， which meant that people could then invest in Linux。

 And so Linux has become Uniix， right， Linux in the modern world is the Uniix like system。

 and Uniix tried to hold on for a while， but they really， really couldn't。

 And so the remaining Unix distributions are a tiny， tiny fraction of the marketplace。

 and Linux is the marketplace。So I'll lay on top of all this。

 remember that 1978 is this moment in history where I claim like everything changed。 Now。

 I've been a computer scientist for a very long time。 I started in 1975。And in 1975。

 I learned things like Fortrann on a computer that CDC 6500 computer。

 it ran a special operating system called Sco Pler， I knew how to do assembly。

 I needed Fortn and even Pascal。So Pascal in the '70s was one of these languages that。

 and I've got a video for Pascal as well， one of these languages that was sort of like saying look。

 here's the future now Pascal was really aimed at teaching and so I used Pascal in educational context。

And as I became a professional programmer in the 1980s， I was using a bunch of stuff。

 assembly language， coball， a little Uniix and C here。 it wasn't like by the early 80s。

 Unix was everywhere。 at least not in the professional world because the PC revolution was happening so we had Do。

 We had early Windows versions。 I used things like Dbase and Turbopascal。

 I taught classes of the IBM 360， and I taught assembly language。

 I used the deck Vx and I used the VMS， not Unix operating system in Fortn。

 and I also then taught in the mid-80s on AT& T Western， I think it's called。G E1 A T 3 B2。

 I taught Unix， I taught C， and I taught Fortran。 And so even though we can trace back to like 1978 is the moment that everything changed。

 it's not like the market changed the thing that happened in the 1990s， though。

 is that all these older computers and older computers vendors like。

Boroughs and UniIsys and IBM and Cray and control data。As microprocessor speeds increased。

 all these little companies would create UniX workstations that were faster and faster and faster and because they could build new hardware that was fast and then grab the UniX operating system。

And make their operating system work on their new hardware。 It allowed for some amazing innovation。

 So I was using Sun Ardent， stellar， these are all gone now， IBMR 6000， convex C22400。

 I had a next on my desk， I use C， but TCPIP Windows， HttP， the web， you know。

 and Windows and Mac OS were're all kind of in the mix。

But the innovation was really happening most rapidly in the Uni space。But by the 200s。

Everything that I touched really had some aspect。 I'm not a Windows person。

 So everything I touched had some aspect of Uniix in it。 Mac Os still has Uniix in it， Linux。

 and my languages were sort of narrowing back down to Java， P， H。 P and Javascript。

 And then in 2010s， right。Linux Mac S， Python， PhP， jascript。

 So things really have settled into a world that my own software development。

 where I'm pretty much using Unix like systems all the time and。

C based or C derived languages because Python， Java， PhP and JavaScriptscript are all based on C。

 and that's why it's so important to understand C。 I'm not writing C as a profession professional in any way。

 but I am using all my C knowledge every single day。

And so that's a sort of a picture of me in my office， that's an IBM PS2 in my office。

 I was registering in 1989 I was registering with punched cards when I first started I was using a line printer and punch cards and so there's my history。

So on to the course， C programming for everybody， I'll just say that C is the most important programming language you're going to ever learn。

It should never be the first programming language taught to any students。

You will likely never write a line of sea in a professional context。In your career。

I'm not teaching a C so that you can go be a professional C programmer。

I'm teaching UC see so you can be a professional Java programmer， really。But if you learn。

 see at the right time in your learning journey。It's a necessary step on the path to becoming the master programmer。

 but it's important step。Because I can't teach you Java if I hadn't already taught UC。

I have to explain how Java works in terms of what you're going to learn in this class。

So this class is not just like get a C certificate， go make lots of money。

Because I don't think that this certificate' is going to make you a lot of money。

 but I do think this certificate is going to unlock the future of you as a programmer。



![](img/953b895853090bb820963d396d92b8be_2.png)

So。Please be patient with this material， do not rush， It's an online class。

I guarantee that you can search for solutions to every programming exercise that I create I don't change them that much so the solutions are out there and if your goal is to game it and just search for solutions to programming。

 go ahead， finish the class congratulations。But you have just taken the opportunity to learn from yourself。

 right， you didn't trick me。I didn't lose anything by you searching for and just pasting in solutions to programs。

Each exercise。From beginning to end is trying to take you a little tiny step further down your understanding。

And the easy exercises in the beginning， even if I have a bunch of them。

 they are there to prepare and strengthen you for something much more challenging in the course If you start pasting in solutions in the beginning of the course。

 you have no chance in the end of the course。And you're just going to be pasting in solutions and when you do that。

 you have only wasted your time。So。I look forward to you taking the rest of this course， of course。

 I look forward to you telling me if I'm right in my instinct about how important this is for you。

 especially after you take a few more classes and then find your way to being a professional。Yeah。



![](img/953b895853090bb820963d396d92b8be_4.png)