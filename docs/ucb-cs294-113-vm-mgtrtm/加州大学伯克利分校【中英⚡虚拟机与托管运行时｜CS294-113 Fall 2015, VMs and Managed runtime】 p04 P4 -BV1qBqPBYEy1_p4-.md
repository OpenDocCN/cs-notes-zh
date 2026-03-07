# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p04 P4 -BV1qBqPBYEy1_p4-

，有还是一样吗？Okay，1 after。嗯。就啊。Re'll see exactly who's in a room and who isn't whether taught students on the course level there are other people。

 but just in case I will mention that this is the fourth session of CS394。

 which is a new course on virtual machines。And I'm the instructor， my name is Mari Waltzsko。

ectOracles。不是清。Instructor。And today we have a little experiment。

 something I've been wanting to do for a long time。

 which is to talk about landmark papers with the authors of those papers in the room to look and face the music an answer to what they did。

I think this is going to be a really interesting experiment， it might be a little chaotic。

 we'lls see how it goes， but the idea is you should have all read the paper。

 many of you have and have submitted questions which I print ourselves Peter。

 I'll give a little bit of an introduction to the background of the paper。

One or two observations on it， and then we'll sort of send into the questions in the discussion。

And see where it leads us。This is a。Particularly。Pleasant thing for me because this is kind of the first paper I read that really made me think very hard about virtual machines and virtual machine implementation right at the beginning of my career。

In virtual machines。 And so I've been waiting do this for 30 years。 So without further ado。

 our guests are Peter Deutsch and Alan Schiffman。Psa is a legend in programming。For the many。

 many implementation accomplishments he's had in。W variety of languages， wide variety of techniques。

Was a legend， even when we started。Alan， I know much less well。

 but I was obviously doing some great stuff and we had a fun conversation of the launch as to the things he's been working on since this paper which has not been in the field of language implementation。

But they came together in some contexts which I don't know maybe they'll talk about to do this work and I think really kind of almost invented an industry around virtual machine implementation。

 and I could probably claiming the abstract。That most possibly all high performance of Vs today can trace their legacy back to this paper。

It's， it's incredible。So。Cast your minds back to 1983。Looking around the room。

 I suspect there are not many people who have memories of 1983 in this frame。Oh。

But I had a look at the Wikipedia page for what happened in 1983 and pulled out some images which jard my memory。

 so some random politicians， movies that I'm sure theyll recognized from the time and TV shows。

 the space shuttle had been flying just the year and it was the year in which the second one was launched for the first time as Challenr。

And in computing， the Free Software Foundation started the Canoe Project in 1983。

 and the Alpenet finished its conversion to TCPIP protocols， and Kiawayo started a writing。

 which has's been doing ever since。即系啊。Yes。1983 was one the work done here was conceived of。

 but I think actually to understand it better， we have to go back a little further。So 1969。

 which even I don't。Particularly well。Was where I want to begin the story in talking a little bit about the concept that led to the small talk implementation in 1969 Alan Kay did a PhD thesis at the University of Utah called the Reactive engine。

 in which he posited a future in which computers would be portable people would use them for education and communication and all sorts of creativity。

 there are a couple of sketches here which I found which I think are actually from either the thesis or a spinoff paper from the thesis and had this incredible vision of how the future would look now remember in 1969 you know computers were the size of things that filled a good chunk of a room or they certainly weret portable。

And even when this paper was published in 1984， you know。

 you couldn't buy a device that looked like that that still took another 10 years to come along。

 so it was an incredibly visionary thing and one of the things he spoke about was about how programming would be accomplished on these devices and what it would mean to be an end user programr because that was the vision of the system that kids could use and program the system。

嗯。A few years after that， so talk。Got going and Alan Ke joined and was one of the creators of the learning research group。

Gathered around a number of people who try and fulfill this vision and a language was invented。

 which was called Mortal， and the name was chosen to convey the idea of children using the language rather than being seasoned professionals。

And they started developing a number of different versions。Different machines。

 different implementations。That era is captured really well in this book。

 which I recommend Deers of Lightning， which is a history of Xerox Parks。

 a good read but I wanted to call it in particular the 1976 version of Small thought which ran on a landmark computer of its E。

 which was called a Xerox Salalto。The picture of the al on the left。

 this was what was known internally as the interim dynabo。

 so the laptop that was in the first picture was called the Dynabo。

And this was kind of how far they'd gotten onto reaching the hardware vision of that by 1976。

 so this is not still quite a long ways from a portable machine。

 but it is at least a personal machine， and it's recognizably familiar to for what we recognize as for personal machines these days high resolution bitmap display。

 single user， fast network port fast storage and the small talk 76 system was well honed and ported onto that machine graphics kind of bitmap graphics in many forms got invented at that time。

 for example， a notion of copy and past came from that era。A few years later。

 and the next machine in the succession of workstations at about one of the next machines at Saraox Kim along。

 which is the Geraldo， which is a much more powerful， bigger， faster version of the alele。

And that was also a vehicle for the then new small talkini language， and in fact， Peter Deutsch。

 who's here wrote， I believe， the microcode。Implementation of that， which is described in this paper。

 which is possible。This book right here， we'll talk about the book a little in a moment。

By then the system was very well polished and refined。

 it was a very fast perform and considered to be a very highly productive environment for doing software development。

あ。Shortly after that， Zerox made the decision to release the system to the world or at least announce the system to the world。

1981， a special issue to a bite contained many articles on the small talk system as a kind of a public revealing of it。

The issue here， this actually has a very special place in mind。

Heart and history in that not in the summer of '81。

 I just finished my freshman freshman year as an undergraduate。had built a computer in the summer。

 which is how you got computers when you were a student in 1981。

 you went out kept the soldering iron then you got on with it and was looking for some interesting literature to read that might contain programs that I could run back then the way you got program into a computer was you typed in because there was no distribution mechanism for。

So microcomputers。And sort of standards for distribution of software。

 So I was wandering through a retail store in the north of England looking for interesting reading material and saw this on a shelf and thought。

 well， that looks friendly。啊，It's colorful when。I've heard of bias。

 it may be an interesting thing that I bought this magazine the first issue of。

A bite that I ever bought， it's the only other one I ever a cat。And it was it was， you know。

 I've never taken LSD， but it was， you know。It's what I imagine it's like。

Reading something that's so far from your conception of what the current standard that it really is mindbending and one of my favorite papers was in the issue was this one by Pe which was about building control structures in small talkranes and there were other really good good articles this is now available in scan form online there's a link to in the Bliography。

Another highly entertaining paper is Larry Teslais。On modes， user interfaces。So after the buy issue。

Xerox also produced several books describing the system in detail。My copies of them from back then。

 they known collectively as the colored box for obvious reasons。

 the blue book was the one that described the programming language in some detail and also had a section on the virtual machine and what it did and the way it did that was it provided。

AnIple of the virtual machine in small talk， so by reading that you figure assuming you could figure out what small talk did from the earlier sections of the book and you could figure out what the virtual machine was doing and how to implement it in a straightforward manner。

And then the the orange book described the programming environment。

 all the tools available in the environment， and then the green book was a collection of articles by implementers from their implementation experiences and studies of the system because one of the things that。

They did was that they commissioned or sded or cajoled。

 I'm quite sure how a number of other companies and institutions to do implementations of the virtual machine from the specification and report back on how when。

 how well performed， etc， and those reports are collected in the Green Book。あまや。Master's advisor。

 visited Parker and this time saw the system thought it was great and。

Set up a project which I was the looking recipient of to do an implementation from the board。

And to accomplish that， you needed one more thing， which was a copy of the small talk world。

 the virtual image that contained all of the objects in the system。

woWould run on top of the virtual machine and so they also released the world for a nominal amount of tape back then。

Stuff was distributed to universities on tech。Individuals couldn't afford tear machines university。

And along with the tape came a little manual of describing also of the tape。

And my advisor said why don't you go build an implementation of this and we'll get a tape and we can make it work well it took it took me about four months to build an implementation。

 it took longer than that for the university to raise a check in US dollars。

And mail it to the States and get the tape back， so I basically was done and grad by the time the tape arrived。

I'd managed to persuade them that you know what I'd done was somehow plausible luckily it was because a week after the tip arrived。

 we had it working initially。Thanks。是礼物。This is the。That very implementation， which still runs。

So this is the small for system， the virtual image from 1983 or so。Running on earth。

See implementation of the virtual machine as described in this book， which is what I。

Creators my master sequences and if we refresh the display see it redraws pretty quickly。

 it's quite usable what you can't get from this is the fact that the first time I did that。

Refresh display。On a high end workstation of its era， which probably cost the region of $30，000。

 it took 40 minutes depending。いいすね。So this， I actually measure that the system runss 18。

000 times faster on this Maggala。です。So the goal then was to make this run fast on the machines of et。

Ss。いで。So now we're back up to 1983。And here are some machines of the era on the left is the IBM PCXT。

 which had come out that year， was the second version of the original IBM PC。嗯。

ATA can make process at about 5 me clock， typically。An8 two and a half megabyte of memory。The Apple3。

Is on the top right， which was the newest machine in the old Apple range that had come out。

earlier的也大是。Not quite2 megahertz Sa the machine。On the bottom right is the Lisa。

 which was the Apple's ground breaking， but commercially unsuccessful machine of that year that was to be folded for one year by the Mac。

I was running a 68，0005 megahertz。But for the purposes of this talk。

 the one we want to focus on is this machine in the middle， which was the Sun Juan workstation。

W whichch was a 68000 investment chain at 10 megaertz with between according to Wikipedia。

 at least between a quarter and two megabytes of memory。

I've never actually seen one of these machines other them in a museum because they were not made commercially available in。

In the in the UK。So one question I actually have for you guys is tell us more about this machine and what was the motivation of doing a pause of small talkti to this specific machine obviously you should talk entirely about the hardware。

 but I'll tell you I I it here。So吧不去。呃，在这块。So， I did。Right。呃。As you may have gathered。

 Alan and I kind of divided up the work Alan mostly did Alan did。

Basically all the hardware work and some of the software work and I did most of the software work but helped from several people。

And I can tell you why the someone interested me when I saw the announcement of its specs。It was the。

 as I recall， the first。Mass market， 32 bit microprocessor。

And we've been working before that with Intel 886， 888。And my instant reaction was， wow。

 this is the first machine that I think we can actually get to run small talk at a reasonable speed。

And so that's why I was so interested in it。So something you have to know about Xerox Park。

 where I wasn't working there。 Peter， of course， was。

 is that along the lines that you were saying if you wanted to have a computer at some point。

 you had to build it。 there were all sorts of rules inside of Xerox。

 So I understand you can clarify some of this。 But when Park first started。

 they wanted to have a computer made by the then digital Cer Corporation called the PD10。

 And since Xerox made its own computers at the time。

 There rule was that Park could buy computers made by Xerox or no computers at all。

 So since the people at Park1 the PD10， they had to build one themselves。And so that's what they did。

 Similarlyly， then， the machines at Park， they were really remarkable things。

 and you showed pictures of the alto in the Dorato。

 And so nowadays when you say it had a bitmap display and it had a mouse and had a network connection you have to understand that no other machines。

 I mean， remotely had any of these things and they didn't basically for nearly a decade after the people at Park used them routinely and you really have to understand how staggering that is as a thought。

 the only people， I mean， people didn't even understand the concepts of that unless you visited park。

And you saw them famously， by the way， Steve Jobs visited Park and saw us for the first time Big map display mice network connection。

 stuff like that and decided， you know， I want some of those things。Anyhow。

 so I heard about smallt 80， I worked across the street at a semiconductor company at the time their research lab and I actually designed micropossors for living but went I was working in the AI lab and I was interested in machines for the same reason as Peter was although I I was hang out with a bunch of list people but I said the smalltook was really cool and so I called across the street and I met at Deug Goldberg and I said。

 " gee， could I be one of these five people like take Ts and Appleel and UC Berkeley and stuff like that to have these initial machine implementation she said。

 no the contest is closed basically。So I said， no， no， no， don't say no。

 I'm sure I can do all kinds of cool things and she basically had me talk to Peter and Peter talked about one of his ambitions。

 which was to basically stop putting things on special purposese Xerox built microcod machines and put small talk on a machine that was I don't know。

 not the Xerox style of doing things。 everybody else is style doing 68000。

 I basically opened my off I said I can do that。And so I built boards。

 there was a kid at Stanford kid my age。Andy Mesherhe and he was building this thing called the Stanford Uni Network workstation。

 and I knew that I met him a couple of times I went over there and I told them that I would help them build some of those machines。

If I could get a couple， and so he built1 for Stanford and I built T for Fair other。

 I brought two of them to zeroerox。And that， I mean。

 and I built them when I mean with a side So did it look like that It looked actually substantially uglier。

 Peter， do you remember， I think you were Peter。I gave him a bare computeruter a multibu crate。

 I gave him a bare multibus crate。 And if you weren't careful if you like Peter knows more than about Ac electricity and microphones because it was like bare Ac connections on the back of the power supply and stuff like that。

 So it looked nowhere near that neat， but I did finally put some of that in the sheet metal box so that people at park who really weren't that hardware s mostly wouldn electric use themselves。

And then we worked together for a while on Blackboards and stuff like that， got some initial stuff。

 half of the assignment， we tried to divide up to work。

 half of the things that Peter gave me to do when I went back to my lab， I would do one a cross 68。

00 cross development system that I cobbled together and with really halting work and Peter basically decided you guys know what a cross development system is。

They don't across the other system is one where you know you start out with a big computer and then that's where the assembly。

 the linkers and loaders and stuff like that are made press with an emulator right and then you you know use that big machine to do the compilation stuff the program preparation stuff and then you downloaded into this other machine that's the way I did it and Peter did the same thing except I started with other people's software for the 16000 and Peter developed it all his own from scratch。

And so his work， he did that and I was using other people's software and he still beat me to almost all of my assignments and I hand do the microphone at that point。

I don't know I have that much to add to what Alllan said。系 the。Yeah。

 sort of the cool thing the cool thing that I did in developing you know cross development environment was you know we had this。

 we had， you know we had the small talk browser and we had。

 you know we had this development environment already existing。

 written in small talk it was quite a nice environment in many ways。

 but the only language that you could develop in，Under it was small talk， right so。

In the course of building development tools for 68，000 assembly language。

 one of the things I started doing and discontinu continued into my research for some time after that was to take the small talk development environment。

And generalize it to multiple source languages and multiple target languages。

And I don't remember how much of that ever got distributed。

 I don't know that I don't even knowing whether any of it got published and of course many other people had done similar things。

 but that was one of the fun parts of that project was just building the developing tools。So。

Just to make clear， you basically started with a bear machine Yeah with story from bear but basically from a pile chips and by that I mean。

Int surface and no development software at all and bootstpped away from there。

So quite a few of the questions were of the nature of。You know。

 the papers talks about code noting page。Other things which you think of normally as OS capabilities and they were there because there wasnt it wrong。

Actually， it was Dan Eagleggs right， who had the famous phrase I think saying。

 I don't know if can people hear me by the way because I don't have the microphone good。Digle said。

 an operating system is all the things that you forgot to put into your programming right。

And so so right that was stand it may well did。 and like many things that Dan said it was very clever and it was very insightful and it wasn't entirely correct but there was very much the style in Xerox at the time to not fetishize operating systems at all they were sort of a immune and they weren't very important things they were down there in the guts of the machine somewhere and basically didn't worry about them because they weren't very important。

 What was important is what the developer used because Park was just a place full of software developers And so yeah。

 inofar as there was an operating system there was just a pilot device drivers at first because we had a mouse and a keyboard in a display and we had to write stuff for that。

 So you might have thought that's an operating system and mostly wasn't there was just primitive for all of these things and then later there was a network it was first a serial port driver to download stuff into the machine and it was a network。

Although I didn't do anything Mike had me。嗯。And then later there was a disk driver。

 so if you want to call that an operating system a pile of drivers that at the virtual machine could basically read a block from the disk then it had an operating system。

 I don't think it was anything that you guys would recognize in the operating。

if I may show a little bit to that， a lot of the functions of an operating system have to do with basically with resource management。

 protection， scheduling， allocation of resources， small talk was conceived really as a single user and for a very long time single threaded language。

And so many of the functions in operating systems simply were needed。And as Ellen said。

 you know we added device drivers， but the higher level Chs， for example。

 for the network were all implemented in smalltop。And if I'm not mistaken， the first。

 at least the first disk file system was also implemented absolutely absolutely and know again。

 if you don't have to worry about resource allocation protection。

 a lot of things become simple Yeah and that's why then was basically half rank namely that if you had a simple enough problem then in fact。

 almost all those things and although it admittedly it was it was signal threaded。

 there in fact was of course some mechanisms for scheduling that was the language at the language level for user visible multiple threads of control and so on again。

 these are very visible in the language and by visible。

 I mean that if the user didn't like the schedule scheduler， they could change it。

Can you tell us a little bit about the architecture of the processor？

And the available resources you had。How much memory was there， for example。

 in the systems that you were using because that the description of the machine that I found on Wikipedia has this fairly wide range of memory that you could plug in and it seems like you'd need to max it out Yeah that so we did it was again these are boards that basically ice stuff luckily you probably didn't know this but Fairche was still in the memory business at that time So for me memory was free not memory boards but memory chips This is the era of physically you're going to find this really。

 really hard to believe。16 kilobit dynamic ras were the sort of thing of the day。

 and you can get larger things than that。 Fairchild actually sold 64 kilobit dynamic ra as well。

 So this is and basically a one mebyte thing basically crowded up a whole board right That's1 MBbyte。

 So anyway， I'm not trying to sound like and we like you know lived in dog houses or whatever。

 But it's just really the way it was And so there were multiple。

 So this was an memory bus of antibe designed part of the Sun1 had a prize that very fast memory。

 unusual for the time。 was it was really an unusual， very economical design。

Andy was really quite I shouldn't speak of the path fence， he still the same stuff。But right。

 so there was two megabytes of memory。 The machine clocked in about。

 I think the first boards clocked at 10 and the ones that we all didn't use for a while were clocked at 12。

 You got to understand there was no cache memory， there was no nothing that you would recognize as modern computer architectural features that you worry about in the school like you know pipelineing branch prediction。

 all this kind of stuff wasn't necessary because these machines basically didn't have these sorts of features don't any branch prediction。

 if you don't have pipelines， you don't need cache and validation techniques that you don't have a cache the machine didn't have any didn't have a memory management unit。

 although Andy had， in fact， done a memory mapper， you know if you guys know about this noclature。

 but basically there still is a purpose why you might want to dynamically map some of the bits you might be you want to be able to still have even if you don't have virtual memory。

 you still might want to have flexibility about mapping the。

Processses address space to physical memory。 turns out they' be convenient to do that for a bunch of reasons I won't go into So there was that kind of stuff on the board。

 but in particular， the 68000 wasn't a virtualizable architecture So what that means is I don't know many you guys take like computer architecture courses but instructions weren't interruptible which modern machine I mean it' really would be hard to find a processor nowadays which doesn't have that So in other words you might take a page fault namely in the middle of a memory reference。

 you say well that page isn't there for non page and you interrupt you supervis space and then you pull a different disk。

 all this kind of stuff which you guys take quite for granted。

 the 68000 simply didn't have So the issue of saying virtual memory the sun won and until the 68020 which was like several years later the 68020 until the 68020 this architecture was not you couldn't do virtual memory except in a very unusual way if you want to find out unusual way you can Wikipedia Apollo computer system like amazing they actually。

what they do is they free， put one processor suspended that and make sure boot up another processor and have it pull the page in and then resume the first processor that was their trip So until then yeah so you do know that so anyway very by today's standards。

Amazingly prim and as far as the instruction set architecture goes。

 there was nothing really really startling about it machine had 16 central registers。

Petitioned actually the eight address registers， a data registers。

 more or less a one and a half address architecture。

No floating point and no floating point in the 68，000 although there was a provision in the instruction space for。

How many clocks to memory？Yeah， that was an interesting point you know essentially it was a way state kind of architecture what they normally expected was that memory couldn't keep up with there was essentially architecture where at the minimum there would be two clocks to do a bus fetch right but they didn't ever expect anybody to be able to build memory they'd be fast enough to do that。

 although Andy Bes on the designer actually managed to do it by pulling a bunch of really weird tricks。

 one of which Id suggested to it， so but in practice it took somewhere on the order of 10 clocks to have an instruction that referenced memory took something on the order of 10 clocks。

So。说。So啊。Let's point to a little bit about the paper and the implementation small talk。

So I pulled out in four。Main contributions from the front of the pay。The first one， I think。

 is the one which is the。The standout of the form， which is I believe this is the first true just in time translate。

In that it took small talk bycode， which is compileed ahead of time in the programming environment and sort of persists and generates a machine code on demand at the point at which that bycode was needed to be executed。

And cash the resulting machine instructions so that they could be reed later。

 we were having a conversation of lunch around this and no one can think of a predecessor that had those characteristics。

 although there were systems that did some amount of dynamic compilation， for example。

 there was a terminal done by。Bell Labs called B and Rob Pike did an implementation of a graphics primitive called Blipbl generated machine code on the fly to run this primitive but the machine code was then thrown away after each what wasn't a general purpose this for one specific primitive so it wasn't a general purpose compiler and the other one you mentioned was the regular expression compile done by 1 times as5 and it would just take regular expressions it would generate the DFAs and convert the DFAs to。

Machine company was pretty impressive， but again， not a job focused programming language and only done once and thrown away。

Can you say something about the。The structure of the compiler and the kinds of transformations that did。

 if any， or what the general organization was goodness well so。I'm going to preface this by saying。

 you know， this all happened over 30 years ago， I'm almost 70。

 I'm not going to remember everything and I'm going to get some of it wrong。

Just deal with it so the thing that made this task relatively simple。

Was that the translator just worked on one method at a time？That was all it had to do。

The way that control throw out into the translator was a method lookup happen。Various ways。

 everybody's hip to method the small quiet method。Yes。

 so a method lookup happened and there might either be a cash miss or there be a cash hit。

 but what was in the cache was not had not yet been translated。

 so control control would come into the translator and basically you know，So know here's a method。

 translated。So。The translator worked in a very， very straightforward way。It basically。

It had a little， you know， it had some internal bookkeeping that emulated the state of the runtime stack。

It basically worked its way through the bycode sequentially。And generated code。

Nearly bycode by bikecode。Also， at the same time， building up a。A table of any。

Literal object reference is needed by the code， that is any literal object including numbers that was referenced from the bike codes。

 that literal would also have to appear on a table to the side of the translated code。

UThe one really significant optimization and it didn't make it did so so it could have generated。

 you know， completely， completely naive code， that thecode， thecode is for stack machine。

And so the translator could have。Eulated the virtual machine stack in an native machine stack。

 you have a push local variable by code， well you pick up the local variable bag when you push it into a runtime stack。

The one optimization was that there was basically a one element cache for the top of the runtime stack in a dedicated dedicated machine register。

 so for example， if you wrote you know A assigned B， it didn't push A and then pop it into B。

 it just loaded A into the register store。Let's see what other interests to reference cap yeah well so right right so that really wasn't an optimization of the translated。

 it was an architect， it wasn't an optimization of the whole system。

The microcoded smallhawk implementations all did reference counting。Piod。

So that method every time you loaded a local variable。

 well you know you were creating a new reference， you know you were copying the reference into the stack frame so it had to increment the reference count。

 whenever you stored the local variable， well that reference went away so you had to deccker with the reference count that isn't quite how it worked close enough so Dan Barbara and I published this paper in 1976 which。

It wasnn't a bad idea， it hasn't turned out to have a whole lot of staying power。

 but the idea was if you have a system in which computation is going on in the stack。

Rather than do reference count operations every time you load and store。

 change the valuable local variable。You only maintain reference counts for references from offstack storage。

What's the problem with this， Well， the problem is then you can have objects whose reference comes to zero because they're only referenced from the stack。

So in order to deal with this， you have the table maintained at run time called the zero pound table。

Of objects that have or might have zero reference counts。

And then the idea is that you periodically stop computation。

And you basically run the stack against the zero pound table。

 anything that's in the zero pound table and not referenced from the stack you reclaim。

We call this transaction reference counting because I thought of the epochs between。

Instances of this operation do sort of like transactions in a database system。

 which in retrospect shows me that I didn't really understand transactions at the time。

But so that was the idea。And。And so we used that approach。In the translating small talk system。

So that the normal things that happened in the course of computation didn't require a fussing around with reference counts。

And that actually was necessary to make。A production machine code， really， really practical。

I mean you can see what the consequences of not doing that is right because basically what ordinarily would be ignoring the register copy and optimization would ordinarily just be a memory store with an order incremented registers how the  think8000 accomplish stack pushes would become something much more complicated where you have to do with dereference and indirect reference to some object table thing where the reference counts are kept and things has to be incremented and possibly tested to make sure they don't overflow and stuff like that so every I mean you can't imagine a simpler operation then simply pushing something onto a stack right each one of those stack pushes or pops would be like five instructions。

Right so that's a pretty significant thing to optimize even if you had this you this cost in the endway every so often you to wake up you have to run a couple hundred instructions to fix up something。

 save you know turning something that might be one instruction。

 not turning what instructions into five is pretty significant and so perhaps when we get further down the list I can say it a little more about some of the trade offs gone in this deferred reference county。

One question I had was the paper calls this as one of the sort of the four features the from。

 was this the first implementation that you had done in a kind of a production system of this technique or had it been used in earlier systems？

这个。Because I know this is seven years after the original paper。And if that's the case。

 what moves eed the original paper？i。Dontz。Recall。I don't， I。We， we， at part， didn't。

Didn't do any implementation of deferred counting。I don't know whether anyone else used the technique。

 what motivated the paper was a bunch of benchmarking and profiling that had been done on the microcoded implementations of smallpox 76。

 and we discovered the reference counting overhead was very， very substantial。啊。

But but to the best of my recollections， we didn't actually implement。

 we didn't actually go back and change the small talkx 76 micro so you with this idea you wrote a description of it and then kind of kept it in your back pocket。

And some time is wrong to apply it It does seem a little plaus， doesn't it， buts Well。

 it's actually not as good to do it in microcode actually because when you do it in a microcode。

 there' still， in fact there's a substantial overhead microcode overhead。

 you have to keep a table of the stack state to know when in fact it was going to transition in other words you don't really have this additional step the sort of a compile time step when microcode。

 you basically only get to look at one instruction you keep a table to sort of memorized what's going on I mean we could we could have read the Dorato I see have done bycode to bycode translation or something like that Well we wouldn't have to do that because I mean the push and bycodes with our own bikecodes we just could have written the microcode in a way that just didn't do reference counting and then every so often or whatever it probably would have fallen out to to microcode called to to do the。

So that's what my memory is telling me。我 so the the差 about。

The language that the system was written in and so dealt with that so the system that was described in the 1984 pople paper。

It was written in Motorola 68，000 December。And you know。

 I was thinking about that as I was driving here。And I don't honestly remember。

My favorite unit of measurement my guess was inches of listing。My guess is that it was。

Perhaps tens of thousands of instruction Yeah， and I actually do remember each of listings。

 so because do remember it was printed in one of those remember the Xerox books we perfect bound。

 you do know that， I mean it might have been recipe if somebody had done that right and I had one。

 and it was like that thing。So right。That might be 150。 Yeah， I think it might be pages。

In some cases yeah low tens of thousands of the structures。I don't remember how many comments it had。

But was the motivation to use assembly simply that you had no best tools and you didn't want to port them or did you were you were trying to deliberately squeeze everything never would have occurred to us to do it in a different language Well actually did it did occur to me to do and see and I looked around at what was available and I said you know the language the compilers。

 they're not stable enough。 they're probably not going to generate very good code I actually remember having Yeah so we talking about the same thing。

 but I mean but it occurred to us， I mean seemed to me that perhaps we had a discussion that lasted all of 10 minutes so I talked about the I mean because you may or may not recall I had like Steve Johnson's C compilers in the 68000 I mean I had all this stuff I knew what the code was generated I showed it to you yeah。

 this conversation did not take very and we were going it would have really been。

It would have the system got rewritten and C yes， I know that was different that was a different year like different many。

 many things were different and we could talk you know it really was almost 10 years later sorry seven years later because really this work honestly started in 82 that you say the paper was written in 84 was it was published in 84 it written in 83 yeah and you know so when we when we took another one of the problem it was like nearly 1988 right so from8。

7Yeah， I guess late in7 right so for going from 82 right five years right so there's a lot of lot of compilation technology into the dam at that point yeah so and also。

We were kind of choosing into microco。 We had something to beat， right， we were， nobody at park。

I mean， I thought this was doable because thats a Mi Roger everybody in part thought this was this is tilting and windows right。

 I mean this was a pointless exercise， it was impossible and so our role at。

One of our goals was to beat the Dorado microcota implementation。It was pretty it was。Yeah。

 because there are a lot of makeayrs and Xerox really had a internalent part。

 they really thought that microcoded implementations of these bycoded virtual machines was the only way to go basically doing other things was crazy and there were commercial companies that believe the same thing。

 I'm thinking the list for example， There are lots of people say that's the only way to build and in fact the future of such machines you got to realize and I think one influence of the paper which you may or may not agree。

 but I think that our paper actually resonated into the risk work that was here because people might have said。

 well risk work is ridiculous and anything architectures are going to have to get more complicated because instead of just having C like languages we're gonna to have super cool with any languages like Li and Smallf and they'll be really important and simpler machines won't work have be more complicated machines and you know Berkeley professor like Patterson and students like under you took our thing。

An inspiration， I think， I mean， maybe I'm looking in from too much of a。Small tug perspective。

 but I think that had a big influence and they had a way to shut down the SAR project here。

 totally anticipated that by saying， no， could this is a simple machine。

 but you could implement a small talkg on it perfectly well。Sma as an amusing Cy。

 small talk small talk in aarrithmetic was the motivation for the attack integer instructions on the spot。

Which in retrospect implemented were not。合来て。这是。Okay。

 so the second listed contribution is the on demand conversion of context。

 our activation records from ont to hybrid and then ealliated forms， something which。

I think I had to read the paper many， many times originally to understand the mechanism of what was going on and perhaps。

Ha't had。As wide impact as it might have simply because the language is that I can't think of any of the languages that would require this in any serious sense。

But clearly an important technique to gain performance in small。Well， so， so。Actually。

 I think that wouldn be the clever we're seeing in paper。嗯。It was the inspiration for was it Dan。

 Inngs who said the implementer was cheap but not yet caught so one of the remarkable things about the smallhawk80 system was that it has complete reflectivity for its execution state。

So what you would think of a stack frames。Not only by compiled code。

 but stack frames are defined as objects in detail。In the in the system， you know。

 in the system description and the system made use of it。 and the system made use of it。 I mean。

 the debuer was written entirely in small talk and it did all the things by manipulating manipulating these contexts。

 I people made cool distributed small talk systems where they would package up existing running objects and ship them over the network and let it know you have a subrt in mid execution。

 you ship it over to another machine that would execute and you wrote that description in small talk right And so so to make all of this possible。

As I said， there were specifications for the execution state。Well。

One of the big challenges in doing translated code。Was to maintain。Excuse me。

 complete faithfulness to that aspect of the system description。And。In order to do that。

We needed to come up with a way。Such that when a context。

 small about terminologies what everyone else calls a stack frame。

 when a context was actually being used for execution。

It would be sitting there actually on the machine stack。

And its format would be governed by whatever it was that made execution work best。

But when you look at it as an object。It had to be an object。And in particular。

 what that meant was that execution contexts had to， at least in principle， had to。

Behave when necessary as being heat allocated rather than stock allocated。嗯。

I don't think I want to try and take the time even to summarize how we went about making this work。

Because it was kind of complicated and tricky， and I think the paper describes it。嗯。

The basic idea was that。对。When a context was created， it was created for execution。

And so the issue was， so there were two issues， namely what happens？

When someone tries to reference a context as an object。

And then what happens when a context that has been referenced as an object is needed for execution again？

So what a context is needed as an object。Basically。What happens？What happened is that。嗯。That。

That context。And。That context。An operation called stabilization occurred。

 so the context was copied into an object。And。And it was probably on an execution stack somewhere。

So the return address in the frame that would return into that one was changed for traveling。

So so that when you were going to return into that context。

 the context just haul back from the heap and put eye confidence this。Oh。

And you want to explain what they're trapoating this or anyone tra， oh， come on they。So。

So that's kind of the 30 second summary and it's a little tricky to make it all work。

 but it really worked。And it wasn't very fast， but it hardly ever happened。And and。嗯。

Yeah so so you know we have to do it and so that's and you know it's really hard to understand even in modern even the languages that you know came well after small talk。

 this idea that you could refer， you they had reified execution state is a very。

 very strange one it's small there's a pseudo variable called this context and that's basically the way that you get a handle on it but imagine if you're a C programmer that there was a variable called register one and any that you wanted to you could like take a peak and register one and assign into the variable A right imagine you could do that you know because the machine dynamic state is part of the language definition and that's really a very。

 very strange idea of people coming from ordinary languages。

 but then it made it unnecessary to write system code in languages outside of small talk I mean that's the trick essentially So this whole idea that you can sort of step back and look at your own execution context as objects that idea generically。

called reflection and there is a there's a massive thesis on the subject of reflection。

 it' list oriented， but it it has a lot of ideas ideas in it behind Brian Cantwell Smith I don't remember the title of the thesis but it's sort of the the V big thesis on reflection interestingly I think most of the languages。

Of providing some kind of ref kit that and still haven't gone all the way of giving you full。

Intertrospection on stack frames， or sometimes they've allowed you to look at stack frames。

sell瞓 job板。Right， often what people mean by reflection is being able to look at the say the class or an object going to language to be able to examine the class structure right that's considered to be a big deal reflection has and I didn't realize this a many years later。

 Ref has security consequences and that may be one of the reasons why people haven't pursued it though even though it greatly simplified some of the programming。

So the other one contribution I'll mention because we've already talked a little bit about differential reference counting is the in caching the passage and tele。

And the paper describes， I think， the technique in。Good。

 comprehensible detail and the motivation for it。 One question I had was what。

 what had triggered the observation of。The behavior of message send， where had that come？

The thought that oh， maybe the type is constant and we can exploit that you know。

 I don't remember it wasn't me。 Alllan says he thinks it was weather lamp maybe maybe thist a reconstruction of something I seem to remember something along the lines of us writing send sequences on the board with you know checks you know the usual hard work of checking to see you know what the class is and you know do you have a one word cache followed by a larger cache and things like that and but looking at the code that we wrote very cursorily and he said well。

 the silly thing is it's probably the same damn type every time around the loop。

And then walks out of root basically right so you know。

 like you guys are wasting your time because butler really wasn't a fan of dynamic polymorphphs and wast anyway。

So that's the way I remember it， but I you say 35 years ago， so I do know， however。

 that the original idea of doing dynamic translation was also Butler's idea。

When I said that I was thinking of doing a compilation on theth of the 78，000。

And but I said that I was very concerned about the code size， you know。

 this is just a casual conversation with the corridor， but we said， well， you know。

 why don't you just cache the compile code？That should have been an acknowledgegment of the paper you probably should have guessed。

 but but it's famous for so many others exactly， it doesn't deserve more credit than the。Okay。

So looking through the paper， I've found a few other things which I think have had some lasting impacts。

And I've certainly been used in other systems， so one is the idea that you only get to look at ST at certain welldefined places and so you only need to maintain the reverse mapping from machine sta to abstract sta only in welldefined places and that's been an enormous hammer that's been applied in many systems。

Since then。' anything you want to comment on that only only that the fact that those are the only places that you can see the state was almost。

 as I recall， that was almost almost a side effect of the fact that we had to make some decisions about where you could do thread switching。

Can we decided that the only places that you should be able to do freight switching were basically at calls and back were branches。

And so you know， once we had that， then the mapping tables if we had to tap onto translated methods。

 you do remember we almost didn't do any of the factors。

We said wait you're going to need need a table that's going to map every instruction right。

 every native code instruction， every decocode instruction right that was the first thing and then we said。

 oh wait， no we won't， right right？I mean， it lasted like a minute and we can't do this at all it's crazy right and then you said。

 no actually I didn't remember that then you explain exactly。

What did you have to do in terms of the interrupt？To make sure that this。Invariing was maintained。

Presumably you could take an interrupt from the keyboard of a mousea or some external device。

 but that was all handled at the device driver level， okay。

 interrupt you couldn't interrupt a small talk thread at an arbitrary place。

What we actually did in App pound， you're going to correct me if I'm wrong。

What he actually did was the phone。under 60来。One of the machine registers。Was dedicated。

For the stack limit yeah， that's right and so part of the part of the I remember that I can't believe you remembered that you've been smashing the stack limit。

And so you remembered that， I didn't remember that since you talking。Boy， what he。

But it was a good hack was Oh sorry I thought you It was a great idea so we didn so because it wasn't a page system and we wanted to have very clean。

 you know， we wanted to have a very clean handling of running， you。

 of being about to exceed the stack allocation。So as part of the preamble for every translated method。

There was a simple two instructional sequence that compared the stack pointer against the stack limit that was held in a dedicated machine register。

 we had enough registers that that we could do that and if we were about to exceed the stack space。

 you know we went off to line coat。So what and the stack grew down。So all any interrupt。

That might result in a small context switch。Smed。ThatThat limit registered and set at the the so call exceed the any call would exceed the stack limit so you would go out to the context which go to the next call that must have been your idea never would have thought I think that was my idea。

It's so wrong。😀や。😊，Did you do anything special with backward branches， let me think。You know？嗯。No。

 the same check would is if I think we made the same check that except there what we did was we checked the stack limit register against the distinguished values was so in effect in a backward branches。

 it was a flag it was just a flag check method calls。

 it's a combination stack limit check and flag check。

 which is the music if one instructor does't work too right when comparison does the work。嗯。

So intercepting that we returning I'd seen that I'm trying to remember why I'd seen that before I had used that before in other systems too yeah is not that one of those things that's been invented you know six million times and we used it in more than one place so we we used it actually for two things that I can remember one was to detect returns into context that it turn into objects the other was that because the allocated space for linear stack was a segment。

In P， it wasn't segmented。Oh I remember HP as a hell about so when we were about to overflow this back。

What what we would do is we would take some initial segment of the stack and just stabilize it know we have the machinery already and then I think we'd move the rest of the stack up or maybe we would stabilize the whole stack I don't remember and then the return address in the root train of the stack would go off to say。

 oh you know you've got to go and revvolivize the context so we use that basically for those two things。

Okay， number two on this is sort of a similar trick。

 which is intercepting making fake objects with sort of stuffed out classes that only intercept messaging right。

 reason the reason that we had to have those those objects，Was that once you。

It takes for moment referred to this context， stuffan somebody could go okay were cases where you might have。

 you might be holding a reference to a context object and nevertheless be able to you needed to be able to execute in that object and so in both PS and HP objects were all reference in directly。

And so there was this funny state of context where they had an object allocated。

 but their real data was still on the hardware staff。And I don't remember the that was。

The paper mentions that there was a。AClass provided for these fake objects called du provided some That's right。

 Did that if you reflect it on the system， because you know， see no。

 it was not visible at the system level。 Now， the reason why you do that is because you have a debugger and you have to have some class for it because the debugger。

 you can actually sit there and you'd see something in the frame and you didn't want somebody to look at it and see something weird。

But， but。At the if I recall correctly， at the small talk level。

You never saw that them in contact in class but any attempt to actually guess in any way。

 even to ask it's if even to ask its class that I didn't remember real because that wasn't really nice I think I think。

I think there wasn't actually a dummy context class， I think there was distinguished I suppose。

The hardest part is always double equals with the fake thing on the right side of the equal Well。

 except that because we had this way of comparing object to identity。

 because we had this interaction people， the double equals check was the check on the address of the s in the interaction。

And then。Hiding representation changes by having the compiler admitcomp code。

 So if you have an actual method on contexts， it says in the paper you compile the special erosion number。

Paragraph， just yesterday。是。就是 paper人。还可以 yeah。We'll move on all right。

It brings a think bill but I don't remember what it was if we had to do so before we go to the question there was just one last slide which is influences on the work so you meant there are a number of things referenced。

In the paper and a couple of things that aren't， and I wondered to what extent these have influenced the design of the system and you know versus being references that were found while the paper was being written。

USo it's Jim Mitchell's 1971 PhD thesis in which he described the idea of。

Let's see if I get this right deriving the compiler from an interpreter。Right。

Right basicallyically by expanding the routines of the interpret and I was tremendously impressed by that thesis。

 I think it's one of the great great CS great CSphass， it was not as far as I can recall it was not。

You know， kind of in the front of my mind when I was going the slide。O。

Then there were the precursor of bike coated machines and threading machines， BCPL， Pascal。

 fourth and less。Any particular。not really relevant， I mean they probably were。嗯。

had a strong influence on the choice to use Bcode as a small hub of implementation。

certainly you at the time， you the P machine was had whatever you call commercial。

 it was certainly state of the market， lots of people use Pascal and so P machine implementation is very。

 very common and there certainly were people who said that you you might translate know as a matter of practice。

People just had P machine interpreting。But there could have been something in the air where you said。

 well， why don't you translate that to machine code and throw the P code away I certainly talked to people who were talking about doing it but that's not the same thing really dynamic translation that's kind of using P code as an intermediate representation the generate code and that's what what's in the executable file that's not done in runtime necessarily。

And then the last thing was the work on APL done in the early 70s and late70s。

Kind of on demand dynamic conversion of representation， I'm not sure I would call it compilation。

 but there were some interesting tricks proposed。I don't remember that particularly being influence。

That talked about。A change of data representation， right？I think phs is just talk about compilation。

In response to interactive sorry， but I don't know whether pick ever whether it was。

I think it was actually。Okay， so we have a bunch of questions that came in via email so we can go through those and then open it up to the floor。

We haven't exhausted everybody by these so I'll take these in no particular order。嗯。一。Well， Patrick。

 you asked about assembly。So are there any additional software engineering techniques available for dealing with such large codeverse using a low level error prome or language do any of these techniques over when managing modern software projects or are they hub videos in my home？

InIn 1981。I was。Still capable。Of fully mastering。Several tens of thousands of wine。

Assembly code in my head and remembering all the details。嗯。And by today's standards。10 or 20。

0020 or 30，000 lines of assembly code is not a large project。So。はい。就。

I guess I don't think that question is entirely relevant。

So there was a question about discrepancy in the paper。

 there was a performance prediction made which。Was no。Understood at the point when paper was written。

 was there subsequent insight as to why where the discrepancy arose between I mean。

 why we can get as much speed up as wed hoped basically。

It says hand analysis was performed and estimated the performance improvement due to any light catching。

 which suggested 20%。But there was discrepancy and it turned out to not be as much as that。

I don't remember being particularly puzzled by it I just so shrug saying， you know， like， you know。

 what you get a fact being off by a factor of two and then back to the envelope kind of saying isn't so bad。

 I guess we commented in the paper and what makes it sound。

I guess I remember feeling faintly embarrassed that don't you remember that that we thought that you catch would pay off a lot more so I guess that's why we mentioned it and maybe if we'd known that it was going to be under1 this and maybe we wouldn't have done and I'm speculating how analysis was basically writing that machine code and Captain so。

Yeah，小明你刷。Let's see a section on different concepts and one of the things that you know。

 when you think about that， that's not enough because you have to know what the ratio of sends are to totally I mean's I mean。

 there's a lot of coefficients difference I mean that kind of analysis would be correct。

That wouldn't be the thing that' would be wrong know I mean you might be off Icycl too because you generated slightly different code than you originally planned。

 but the thing you could be really wrong about is in fact whats the mix was by the benchmarks you ran and stuff like that you could be off by quite a lot so I think that was good freeze。

The section of different context representations mentions that the concept starts in volatile mode is converted to hybrid mode and etc cea。

Will the context be returned a volatile mode if the reference to it as a last or is this such a rare occurrence not like 5？

I I don't think that okay， I have to sort of reconstruct what that means certainly what happens is a reference to a context that was you know。

 that was reified。It can resume execution later， that's the whole point and。

You should think in terms of kind of two state transitions， from volatile to hybrid。

 and then from hybrid to stable and to stable back to hybrid。

So when a context goes from volatile to hybrid。An object is allocated。

An object idea is allocated basically。But when a context is in hybrid form。

 the state of the context is still in the stack。So a context that can then go from hybrid to stable in which case its state is transferred and then can go back from stable to hybrid。

 in which case the object reference still exists， but all the state of the context is' on the stack。

 so a hybrid context is an object all right。But。It's， you know。

 and it's managed with deferred reference kind of just like any other object。

 so if that object ever is ever freed。Then yesD， there there's no reason why。

The context you know shouldt have any machinery in for being converted to object form。

 what I don't remember is whether hybrid context。I think hybrid contexts did have something special in their return slot。

So that their state would get poured into the object， when they returned。

And if a hybrid context was free。I think。We had to do something about that return address and I don't remember what it was Well why would it be free you do a stack scan and surely no's a reference to there's a reference to the hybrid context from the stack but what I'm saying is if the context the context became hybrid because somebody did this context or whatever then no further reference then that reference just got dropped on the floor so that there weren't no longer any actual references to the hybrid context then at some point a deferred reference context we would would free the hybrid object。

The heavy content object， right there's a point here from the staff。

So what you're saying is that from the sta when you're trying to do the when you're doing the reference count suite。

 you're looking at the stack to see and why would you count that。

 maybe is essentially the equivalent of being on zero cap here。Right， so for hybrid context。

 there was， in fact a reference to the hybrid context from the stack。

And once once the schar returned then then it could then then could be because really really in fact。

 hybrid context by definition was in fact there because you'd be perfectly free to say this context again in the running code so and they would have to refer to the same damn hybrid context there before so so yeah。

 so so in fact it can't be free while there's while it's still in the s there's one more question I want to take a break。

Object table， you had an object table， we did， and you maintain the object table。

 even as the system evolved later on。嗯。Despite the fact that。

Generation scavenging came out and people found alternate representative direct points represented each force。

So， so why， why keep that Well， the reason that we had the object table in PS in the original 68K implementation was number one。

 all previous implementations had it， that's the best reason right and it just makes some things simpler。

And you know what they were so yeah there's an inside thing and small talk about switching the identities of objects and people every so often would use them and benchmark that use that that's called to come by it's a code word the small talk for switch swapping the identities of two objects and if you don't have an object table typically the performance of a benchmark that does that thing would fall completely off the cliff I mean talking about order of magnitude orders of magnitude inferior performance and our benchmarks in fact did have becomes in it。

So you know， as far as generation scing goes， you know。I have to confess that I feel。

A little bit about scavenging。The way that Einstein felt about quantum。😀ははは。😊，好。I know it works。

I know that there are lots of reasons why it's a good idea。

And it always makes me feel a little queasy。So， so。But in fact， HPPS。

 the retardgeable implementation that we did later on in C， they use generation scavenging。

I't it used everything period Well， it had the most postponern baroque memory management system is that right。

 I mean， of course it had a classical garbage collector， but it it was incredible。

So we guarantee that we make赚。That mean it like this whole hypermodern baroque gun right there were papers on it。

 they were very proud and so so much of the Einstein thing I mean。

 you had know there were all these got other guys interview and lots of among them were David under by the way。

 who worked he and Frank Jackson spent years of their life working on H so the best answer is that's the way they did it before and it was。

おかじゃ？I think we should take a long pause now。A not classmate。This gave marble the bathroom break。And。

不 you。嗯，参与的。One interesting is whether that' the subsequently system anybody has any remaining question。

Should be done with the section value。 So I think， so。So one question is， is Bt basically？

At the time， the battle between special purpose hardware and general purpose hardware was。

Still open in some ways。A victory in the whf for commodity hardware。

 but is there a fundamental reason why commodity hardware。

 general purpose hardwares won over the special purpose hardware that preceded it？

Helen and I both have answers， but Helenlen's answer is better， so I'd like him to answer it。Well。

 assuming that you mean by special purpose hardware。Yeah， language specific yeah。

 language specific hardware。 you think that it's sort of axiomatic that a processor that's built to only work on particular languages is of less general applicability than the processor that's built to work with every sort of language and generally a higher volume processor with more general purpose application will have more and better solid state physicists working on the semiconductor processes that lead to it is called learning curve economics in the semiconductor business。

 So basically what happens iss more popular processess get built on more expensive semiconductor product lines which have smaller geometries and better speed power products and so they are a faster processor So even if there's some theoretical advantage to making some cool architecture if it's not if it's got one small volumeing economics。

 Yeah， but it's volume economics， that's what counts the most and I have a different answer。

 which I think also has simplicityity to it the reason that people think。

IfThey want specialized hardware for languages is because the elementary operations of those languages are in some way more complex than the ones provided by lowest common denominator hardware。

 they might have type checking or reference count or goodness knows what。So。You know。

So they say well， you know you're doing harder well， so if you step back。

What you see is that when you execute a programmer in a language like that。

Each of those elementary operations involves extra work。

So you're effectively doing something that's sort of like interpretation on an operation by operation basis。

Now the magic of compilation as opposed to interpretation is that basically you can step back and look at something more than the individual operation that you're executing in any given moment。

 and so you can float things like type checks and you can float。You can float。

Executionional overhead out of the context which it appears， so for example。

 if you have a language in which in which the elementary arithmetic operations work equally on tag integers and tag floating point in general objects and whatnot well if you're executing those operations in special purpose armor。

 those checks have to occur at every operation whereas if you can step back and look at a piece of code and say oh man。

 this thing's doing a matrix multiply， you know I only have to check the inputs once and then I can just go ahead and do floating point。

That's the stroke of genius in Jimtal thesis。嗯。And so I have an aphorism for that。

 which is compilation beats interpretation and it's because you can take things that。

Might have to be done at an atomic level and you can float them out and have the operations that are actually doing work execute with much lower overhead on simpler hardware right and then hence the aphorisms that are more concrete never put off into runtime。

 what you can do at compile time which you could also say never do inside the loop what you could hoist at the beginning of the loop and so and so forth and so that's exactly the steps that complicated hardware tries to save from the poor compiler developer who doesn't want to be saved because he's got a very expensive Berkeley education teaching in how to do exactly all those cool things。

可。It seems that memory constraints were an important motivation for all of this system。

 if memory had been cheap and plentiful at the EE time。

 how do you think things would have been done differently？嗯。

I'm going to give a slightly snarky answer， which is we would have run bigger and more complicated problems。

嗯。啊。But but actually。You know。Memory constraints come back in a different form。If you have。

If you have an enormous amount of RAM， yes， indeed。

 there are many things that you don't have to worry about。But。But， you know。

You knowWhen used to thinking， well， you know， if you only have a limited amount of RAM。

 then your system performance is is going to basically be be。You know。

 have it ceiling imposed by the necessity of swapping stuff in and out of a Ram to disc SSD or something？

And so you have lots of gram and that problem goes away， but it comes back again。

Because now you have the level one and the level two cache the system and programs are going to execute more efficiently if they're executing out of the cache。

 the instructions were the data。And people who write really high performance numericalmer graphics and database codes actually have to worry about that。

 they have to worry about the cache size。So。So I don't know the paper may allude to this。

 but it would be interesting to ask the question， okay。

 which way do you get better performance out of a system？Do you compile everything？And then。

 just let the code come out of RA。Intoto the cash。Or are you better off doing dynamic translation and limiting the amount of code that you have in the code buffer in the code cache to some substantial fraction of the size of the hardware cache？

I don't know the answer。You know， yeah， that's a good answer。

 but you know one of the things that people forget about the G Am is one of GA Do is。呃。

computer architect who was heavily involved the creation over the most successful architectures of all time in the IBM 360 series and he had a phrase called the balancedanced Comp Architect and his point was there isn't much point to having more memory than sayNow this is a rule of thumb he had at the time that it wasn't much point for computer to have more memory than it could set the zero in one second。

So and if you think about it， you know that might not be the right constant。

 but you know how about a computer that had so much memory that it would take it 100 hours to clear right So you really have to ask yourself what's useful ofable that memory if as a matter of practice loading programs into that memory or whatever just takes too long。

 So there's always that speed space tradeoff actually extends quite some distance。 And so yes。

 you can imagine what if you had two times as much memory or something like that Some thingss become easier。

 but it's very unlikely with that with the processor of technology at a time。

 that it would have been all that useful to have memory thats 100 times bigger。

Do you think you could adapt the inline caching technique to assist system them with read only code pages？

Yes， of course。we nearly had to do that right because we had to be catching validation right。

 so what was described in the '84 paper was on implementation of a 60，000。

 we actually did the second implementation later starting in 1987， 88 in C。

That was designed to be instruction set retgetable， and we actually wrote code generators for。

 I believe， six different license。And some of those Is required。

Executing instructions to invalidate conflicts between the， instruction and data caches。And on。

I don't remember whether we actually did this。But I remember I certainly remember thinking about it。

On those architectures， rather than putting the cache in line in the instruction stream。

 which was put in line in the instruction stream was appointed to it an allocated sell off in data memory。

And that basically solved a problem。 Yeah basically assist in direction it's not that hard right so the short answer is any place in the very few places where we get overriding in instruction instruction screen we just replace that with the level of indirect up to something in the data this thing about the in validation weighed very heavily on our minds at the time。

 because even if the machine had an instruction for that in some cases there was a supervisor mode destruction and simply not available to so this is a very real prospect that we couldn't write to code space at all in some architectures。

 although I don't actually recall whether we targeted any machines we actually except except of course to make runtime codegen work at all。

 we had to be able to execute on memory I mean I having some dim memory that on machines where you had to do a supervisor call to do that some things change。

 we use an extra level of the direction。I think the idea and the answer to that is that again。

 I don't think we actually had to live through this problem。

 But the idea where you have to go and do some memory mapping thing where you said， okay。

 this segment is now datariable， and then you could like And then so you don't want to do that as a small grain size。

 You want to do it the largest possible grain size。

 And I think I'm pretty sure we had planned what the heck we were gonna do if that happened。

 remember there were these weird supercomputer manufacturers like art and stuff like that。

 guys who said， yeah， you have to design for our weird machines and you could only do cash and validations or or executable and writeriable under very heavy trap to supervisor nonsense。

 like I said， remember we actually had to live through this。

 But we were living under the threat of having to do it。 So we worried about this quite a lot。咁两个分。

Before floor now， if anyone feels like the question hasn't been asked or answered。

Mambers of your checks。Reman question。我是说了。Ler， sorry，This paper。Publish like。よしやそ。

And I feel like when you think of a CS major。LikeT shirt。Chil， right， and back then。Professional。

 and now。这个是。I really。Take out。There types of people joining in C us， right，Main about it。And I also。

Why you thoughts。Like， this is like great。I don't know。

I think shes said the impression that we were a lot more professional than。likeYeah。Yeah， so yeah， I。

 I want you to take that I want you to take it first， I really do because I what you were to say。😊。

So I'm sorry I have a little bit of hearing loss， I'm not sure I've heard every word of your question。

 but people were so straight or nowadays they sort of open and you more so what was the name of what was the title of Steven Levy's really infamous article on Park？

Remember the the， was it the rollingll Stone article？So， so but of course is what the doormat said。

 for example， right of John Markco's book right so so the short answer is that I think there was there was quite a spectrum then and I think there's quite a spectrum now although I think I think the distribution along the spectrum has shifted a good deal。

嗯。From my memory， the 60， 70s，80s。The， the bulk of。Computer。Related work。

 which I think then was probably classified free in our engineering。

 the term computer science was relatively new， was in fact。

 done by people wearing white shirts in big companies。嗯。I Xerox's part？Was。

A bit of a departure perhaps。And Silicon Valley more and Silicon Valley more generally。

 and there have been a lot of books and articles written on kind of the rise of the Silicon Valley culture。

And I think it's fair to say that we were we were you know we were among the you know kind of the early early instances of it right with more bohemian than you think basically Oh yeah。

 oh， a lot more bohemian than you think， I mean you know if if I think of the people who were around in the 70s and 80s。

 I mean， you know， just sort of locally in the valley， I mean， you know， there was us。

 there was the Stanford AI lab fact。Those were so you're wearing their t-shirts basically you're under a misapprehension for how you're thinking about TJ。

 Watson labs and you're thinking of the East Coast rather than the West Coast Yeah and in fact。

 there was a considerable East Coast West Coast divide on the East Coast I guess the one really notable exception perhaps with the MIT AI that's very notable Yes。

 that's right they really lived on the they really。Be asked people were kind of streak， I mean。

 lot of them it wore ties to work， right？Youけで。So。There's a book I will recommend。

 I guess you haven't read it。 John Marco what the dormmouth said and basically claimed that the modern computer industry basically is straight outgrowth of the hippie movement。

 So so I hear you that you think things have changed and things always change。

 but but I think you may be imagining sort of that there was a different race of people back then who did things like that。

And that they didn't smoke to open have sex and you whatever this is the attitude that children have about their parents。

 and I understand that。So I really wanted to bring in。

 I really wanted to bring in my Xerox ID badge from 1970， which I'm pretty sure I still have。

 I just wasn't able to find it， I looked like Uhannes Browns here out to here I had a beard down to there and I looked anyway and I looked like I smoked a lot of dough。

だめ。Right， so this isn't to criticize your point there' things have changed。

 but maybe not as much as you imagine。Mario， do you have that video of somebody demonstrating either sell or small talk？

I do， yes have。I have a couple of videos I don't know whether you're thinking about the self video with Dave Ongar and Randy Smith or Randy Smith's Arc video。

okay， I actually had the homework。s show。 It's just a window into that。 Well。

 so that was already the 90s。 exactly。 But yeah， you could see like a thing lab demo。

 I mean there was a lot a lot of stuff that you could probably still see video of people at park and mind you。

 it did annoy you know， the， you， sure enough Xerox was an East Coast company And people would use the phrase Webster and stuff like that。

 right， they would talk about Xer headquarters And when the Xerox guys in their suits would come and visit Park and they would see all these people dress sort of not as differently as you might imagine to where people dress today and have And then remember bean bags that's right。

 And they would be annoyed。 But in fact， it was。😊，The West Coast was。

Created the culture that you inhabit now， the Hilick book， I think， speaks to this。

And talks about that east West divide。And some of the incidents that were born common。

Quite memorable I really thank you for the question， though。With questions。

Tring it back to something more technical。😀Yeah。So going back just to the memory usage aspects of the。

We can show on really big commercial software the eyeC becoming a real。Even like Linux， for instance。

 famously somebody decided to alias the inline keyword to not do anything。

 and then all of a sudden Linux ran am bastard。Because they were just aing work。Like。Was it，Yeah。

 it was a pretty much。They。Yeah， so。系す。This is as much for anybody that knows Mar and Jtting as well。

 is that is this eyeCache usage really taken into consideration because when you're Jting。

 you can just， you know as you guys saw you just blow up the size of the code。

 is there a tradeoff where how much is it just that you take a cache。

 you pick a number and you say I'm only going to have this volume of Jitted code at any given time or is it a more wishywahy sort of line where you decide how much you're going to Jit before you start blowing up here？

You know。I mean， I'm going to start with the customary weasel words。

 which is that it depends on the workload， you know。I。

I haven't been doing work in this area for close to 30 years。

And I think you should ask that question of somebody who has been。Because I mean。

 it's a really good question， it's a good research question。I have no clue about the answer。嗯。

The the only place that I've ever。You know， encountered。Or even addressed this issue in my own code。

 I had nothing to do with code generation it was when I was writing some graphics code for ghost Sc。

And the the。And the way in which it partitions and loops working over bit mapps were optimized according to what it thought the size of the data catch was。

And that's something that people do all over the place now on high performance programming。

 and I just have no clues to what's happened in the last 20 plus years。Yeah， I don't know either。

 but you have to be careful when you do when you do an analysis。

 when you're trying to think about the problem， You shouldn't be comparing the。

Space explosion that occurs from the intermediate representation to the native code representation because you're comparing apples to oranges。

 one has nothing do with the other。 the intermediate code representation if it was kept and interpreted wouldn't be what was in the eyec at all right what would be in the eyecash would be the interpreter which has whatever code path it has and you might speculate that' smaller than the dynamic code that you're generating。

 but you don't know that with respect to loops， it might very well be a lot larger right namely that there's all this overhead stuff that we happily limited。

 say for example， dynamic method lookup with its little hash table routines and stuff like that And if you if you've done these clever tricks and you're in inner loop。

 you have a whole bunch of a very long possibly interpreter code path which now is completely obvious so I'm not saying that I'm giving you the answer I'm just saying that be careful。

Where your analysis begins and so for example I might speculate that if there's a really large gap between the RAM and the cash。

What you might find is that it shifts the balance between bycode interpretation and code generation so that it now becomes because the hot paths for the bycode interpreter are certainly going to fit in even the hot the furthest in eyeCash。

 it may very well be that，Dynaically generating compiled code for anything other than the hottest methods is simply not worth it。

You know it may just not be worth it and again it depends on workload and you know there's lots of research papers waiting to be written if they haven't already。

All right， so looking at the future of computer architecture is more toward all。

 that there's going to be reprogrammable fabric， hardware fabric like such as FGs。

 what techniques do you think that can be learned？From the just time compilation for software that could be used as safe or hardware。

One idea being。As I'm running software I can。Then port it on to say an FPGA and run that bit more efficiently on。

techniques do you think might come out that are also applicable from your own work you know we just before starts。

 some of the versions of the Alto and the Dora that we work with actually had dynamically loadable microco。

And something that。We speculated the about but didn't go very far with because the microcoat space was so small was the possibility of perhaps not compiling。

 but dynamically loading hot code into the microcoat store on the fly。

And that was just a segue to whatever Yeah， well I was basically going to say that I think that not so much our work but the immediate successes to or the near term success basic custom compilation。

 namely that if and there are people who are doing this work as well're making a very specific point when you're talking about FPGs and that I'm afraid I can't be certain to what to say but just generalizing from your point namely where there's a lot of dynamism in the hardware that it's somehow reconfigurable and the software can get hooks into that。

 I think the stuff that I know about that I find very interesting I just brought up the gl today was speed power tradeoffs and that's really quite common namely should you power up a couple more cores you know。

 should you increase the clock rate on some of the cores so on and so forth that I think this is interesting and and not really our work so much。

 although our work pointed to that， the custom compilation work where you look at。ically。

 what's really going on the machine and use the knowledge of what the possibilities are in the architecture and that's underus to date。

 I think there's some real prospects there， how that plays the really special purpose hardware but tuable hardware which already exists out there。

 if you have a laptop nowadays Intel is given you stuff where really is multiple cores。

 you can power them up power them down you can change the clock rate on some of those chds。

 you can change the cache out of patients， there's an amazing number of knobs that they give you。

 And I think there's speaking of lots of research papers。

 There's involves lots of research papers on generating code that decides how towi twirl those knobs。

 So I hope that answer your question。😊，So， I don't。Mis this way。You did that the work。

Paper represents how closely you get to the Dorado。They keep asking us this question。So。

My recollection is that。无一。When we got to HPPS on the sparkar。

That we were sort of in the Gerrato pla to within a factor of two in either direction。

I definitely remember people subjectively by way of complimenting us would say this is easily a snap as。

 but people would say that， whether it's true or not with respect to the implementation of the 68K。

My recollection。Is that it was in the range of one fifth to one8 of a dorato。

So we didn't get very close。Does anybody want a hazard guess of how much it do costs internal cost for xerox to build？

I'll give you a hint if you know anything about hardware architecture of that era。

 it was built out of ECL SSI chips， in other words individual chips inandgate chips。

RightIt was built from N gates What's that for N gate on chip， Yes。

 exactlyre on wire wrapped boards and a power supply with a blower and the company disk drive that was so large that when you first went into the park。

 you noticed that nobody actually wanted these personal machines in their office。

 And so what they did when they drilled holes in the wall and they ran the display cables into your office and the duras would be sitting outside the office making making the hallways very noisy because of the fan noise So anybody went guess how much these machines cost。

Internal transfer cost was in excess of $100000 each and they would get they goal at park。

 as I recall， I wasn't an employee at park， wasn't the goal they were say eventually they' going to give one gi to every researcher was right and so that would have been quite。

 they never quite managed that but no but。We had a lot of them Yeah。

 so so one fifth of Dorado on a machine， I know how much it costs to build a sun one because I bought the parts and it cost about $1500。

What was clocking。The clockrick of the Dorado。That's a really good question， but I think I can guess。

The clock rate of the dura， the microco clock rate。That wasSo of 16 megas， 16 nano a secondnd clock。

 Yes，16 nano3， that sounds right， Yeah， sorry yeah，1%。Right。That it was a very， it had， I mean。

 it had the memory。 It had God's own memory bandwidth with the machine of that area。

 It was an amazing。😊，Had an amazing amount of memory that。

It could like do four things at a time and like， right， I mean， it had， it had。

 it could refresh and display， right， micro it had， it had， it was a cool machine。

 really it was It was a really cool machine。 It had micro It was really an incredible topic。😊。

That election is the terms。Complexity you just measure。

Number of gates that you needed to report about how to。200。Number of gates。

 you know I think as a processor complexity， it probably was quite similar but the differences with the A was dynamically micro so it was much more expensive it was built in ECL right so that's a physics argument right there because you got a 16 megahertz 20 odd megahertz clock versus the 10 odd megahertz clock so you know in a very expensive technology versus a very cheap one NmoOS versus ECL。

But they also spent a lot of money on memory right， in fact。

 I would dare say that the majority of the money the Doronto went into memory so because it was the microcode memory which clocked very fast that clocked it right it was made from static static Ram basically flip flops right and clocked at 169 secondcon ramp right and it had a prefetch and it had four you know banks of registers I mean it was just a tremendous amount of Ram sorry very。

 very fast Ram in the machine。And it was like 2，56 bit wide。 It was ridiculous， ridiculously overme。

 right， I mean， they really should have put four processors on one memory bus because。

That was really over engineerineed。So you made a point about generalized hardware winning over specialized hardware in this kind of scenario。

 but are there like tiny extensions you could make to general hardware to make this kind of runtime system work better。

 for example。Did you had like various support， for example， to replace the redirection table。

 for example。Well。He doesnt like he doesn't like things like generation values but he wouldn't want I'm not going to speak to things like a。

read right areas because those are common on mass market processors today。

 I mean I think the Intel X86 architecture has those these days。

 the one attempt that we made at that was to add support for tagged integer arithmetic。

Which we talked the designers of the spark into putting in。And it probably wasn't a good idea。对没说。

I know that Well， you know， I think there's a lot of blame to go around not get particular case。

 because who asked them to decide that when the check fails to trap it to no there were there was there were versions of those instructions that that did not trap。

 There were versions of those instructions that simply said overflow And so you could do the overflow and tag check the single test and it still wasn't worth it。

I was just saying you made the point of how comp always been on interpretation。

 but then the issue is that sometimes like so the tag check is like an example where with enough perspective you can get rid of all the tag checks。

 but then there's other things like the checks that you have to do on the you branches and things like that。

 maybe，Or the garbage collector support， where it's kind of harder to compilation get rid of。

So like if there's like support to facilitate this Jit compilation， you know。

 that's like like a constant overhead that is there and I know that like people have been getting to like reduce that overhead。

 but it's still a real overhead。And it's an opportunity to make me speak。喂。I'm sorry。

 I guess I'm not sure I'm not quite sure what youre。 I'm just following up on Martin's question。

I'm just wondering whether there are things that are less amenable to using。

Compilation and remove that like part of your runtime know so memory management memory management is a really good example because it's one that just keeps coming back over and over and over again。

 you know the tension between people who want the absolute maximum amount of performance and are willing to pay with the fragility and the unreliability of manual memory management to gain it and the people who say you know we can we can push the runtime overhead of fully fully safe memory management down pretty much as far as you want and at the cost of some additional complexity and some perhapss。

 you know additional static whatnot， we can even do that in environments that need relatively demanding real time response。

And。I again， you know， I actually sort of dropped out of the field about 20 years ago and so I don't know what the state of the art is in terms of you know。

 kind of what the the minimum hardware support would be for scavenging that，That would buy you。

That would buy you a reduction in things like barrier testing， and as I said。

 it's my impression that intel processors may even have something like that in them。嗯。

I don't give the impression really usable maybe not。 the get well， there's all the operating so。

 but but in general。If you step back far enough and you look at almost any source of overhead。

In the execution of a program。I'd say kind of as a broad statement。I don't see sources of overhead。

That can't be addressed by。Some combination。Of。You know。

 of floating operations out to a larger context。And doing。Dynamic specialization。Based on actual。

 know actual data configuration。Um， that， you know， if I was going to put my money somewhere。

 that's that's where I would put it doesn't mean that you。

 it doesn't mean that you can do that for everything。

But I think we'd have to drill a little deeper into specific instances。Before。

Before ideal be persuaded that there's some area where you can't do that。

Over follow question on that was like。And these systems like you have to spend a lot of time tuning the J compiler to make it around as fast possible because that's an okay。

Take a pause when you do the translate。 I know you said you like did he very straightforward。

As you do more specialization it takes more time and so I'm wondering。You know。

Did you measure the differences for to C implementation I'm sort of going towards like。

 well maybe that's where like actually hand writing the assembly might be worth。

 it's almost like writing hardware but you want to write the little code to make the compile around。

possible like how how much overhead did you see from writing end saw we saw we saw we did see when you were。

 you know， when you were switching tasks。In some large I mean。

 when you're switching tasks kind of in a large brain so that all of a sudden。

 you know your hot code paths， a lot of the hot code paths moved somewhere else。

 we did see there were human perceptible pauses in the order of what fractions of the second。

 while code was being generated for the new path， if we had been more concerned about that？

What we would have done。Was would be to。Would be to schedule or interlea co generation with interpretation。

You know， we used to talk about that having a hybrid strategy where we use an interpreter until it was worthwhile。

 you know you know especially when you talk about coldstar。

 you'd imagine where there's some reason that it was important to do something really quick for specialized applications。

 maybe more realtime or something like that we couldn't tolerate with cold star clauses。

 the same issue would come up with garbage collection pause so but I do it does occur to me this is something I've observed more than once is that that when I was using the system that we created all the way back then under certain circumstances。

 I'm a really fast typist， I know you' a slightly faster typus but I at least used to but I was pretty damn fast。

In 1982， I could type faster sometimes when the P system was in a bad mood。

 I could type faster than it could echo my characters on the screen， but you know what？

On my Mac nowadays， which runs about 2。5 gigahertz and write as code's all written in some weird dialect of C。

 the same thing happens。And the machine is being sped up by fact of 2000 and so on and so forth。

Apparently pauses are tolerable in interactive systems and people keep on adding and crap into these systems until people start noticing the pauses and then they speed them up after that。

 So I think that's what we did。 We we just better our system up until stop being so annoying and that's probably what people are going continue to do and as machines get faster and implementation get better as Peter said。

 we'll tackle harder problems always at the hairy edge where the poor pauses are just kind of getting annoying So I really in my career。

 I really haven't noticed the difference systems are always on the hairy edge of about to be annoying until they're actually annoying because something's broken I meanre actually annoying enough and enough but I mean on the hair edge of being annoying because system software is a little bit slow and it's always been that way it's been that way for 40 years so I don't expect it's going to change in the future either it's more to do with people with technology。

I mean， currently I think the problem right now is with the JBM。This is Sir。

I know they work real hard on these BMs that are。For like JavaScript。

Where they have really fast streo times。A lot of times you just ask kids once。What's the job here。

Yes， I've noticed。Yeah， that's right。It's just，' it's the same phenomenon。

 it's just there's a massive amount of code on that。If you look at。a long time ago。

 I actually looked at how many classes were loaded before howo world started before being were executed。

 and even then I think it was in a couple hundred。啊，我也听。

buy comess running before you got the name and I'm sure to。

And people will just keep shholing more stuff as the speakers up we can squeeze more stuff a hire physicists。

Okay， so continuing the question about user experience。 I noticed a trend from。

But I'm going to call the good old days。A small talk image or a listen image。To nowadays， where。

UX and the user experience is actually much less integrated， much less unified。对啊。And before。

You think we'll ever get back to。Integrated development。No。

Because and it's not for a technical reason。Your opinion're if you look at the way that software gets created these days。

And you look at people's expectations of what software。

 what a software application or software environment brings with it。嗯。

The number of different players and the number of different sources that that contribute to software。

The total user experience of the software that you have in front of you on your screen。

Is so large and so dispersed and answering to so many different， so many different missions。

 so many different。You know， criteria。翻啊。It's。It's。好。

It's a constant struggle to keep any standards alive and working and usable at all。

 let alone trying to create a fully integrated。Create and maintain and develop a really fully integrated user experience environment。

嗯。And。I could actually rant about this at considerable length because I am temperamently a pessimist。

 but I think。调解。嗯。You know， maybe you guys all know this paper。

 in which case I shouldn't raise my breath， but I'd say the single most important paper to read。

To understand the， I mean， they might be more profound ideas， but nobody's written them down。

 I'm about to tell you about Dick Gabriel's worst is better。 So do you all know that paper。

 Does everybody know that Dick Gabriel's paper， which is quite old， at least 10 years old。

 called Wor is better。I people know that， Okay， Well， I think that's basically most of the answer。

 namely。 And Peter used to say this and be， you know。

 you don't give yourself enough credit because you anticipated that paper。 But you。

 you had a shorthand for saying that you said first to fill an unoccupied niche。

You used to say it all the time Yeah， but that wasn't even more my idea No。

 I suppose I suppose that I for sure。So what happens is we get these agglomations of systems and it's not just in computer systems。

 I mean， the way we have shift gears in a car and steering wheels and the layout of keyboards on it I mean。

 basically what happens is the first system that's good enough for doing something complicated that has a network effect basically is going to be with humanity forever as long as the problem that it's solving continues to be right right Well。

 apparently keyboards is so important for example So right so what you have in real systems。

 whether they're automobiles or you know things that lets you type papers or whatever it is is some agglomeration of these kinds of solutions that you know got put together and you don't get to change some piecemeal because you're locked into that and you don't get to change in an integrated way because the piecemeal solutions are adequate so。

No， and and know I don't want to make parks on like Camlo。 Oh I didn't want to say this。

 So you may not know this， Mario， what this picture is up。

 Yeah I know you castle Can everybody see this。 I know with a caption and so on， Oh， you do。 Okay。

 So then you know， it's important。 So what you see here。 And maybe that was a close enough。

 I hope I'm not tear it covered too badly。 There's a balloon taking off from a lofty castle that's on a mountainous pinnacle。

 And so the interesting thing about this is this is a elaboration of an earlier cover of white magazine。

 It's a zoom in on a particular feature。 And that was called the land of programming languages or something right and what it was into the landscape of programming languages。

 And it tried to show a continent where there was you know。

 the land of Fortrann and the issle of snowball and so and There was a fanciable picture of lots of languages。

 But all of these languages were heavily populated and had their a rather large piece of。😊。

fAnd in the corner， very， very small。 There was a tall pinnacle of a mountaintop with very few people on it。

 And it had a fortress like Red， a castle right， that was clearly unreachable。 It was in the clouds。

 And it was clearly unreachable by anyone else from these other places and and it was labeled small talk。

😊，And that was the time saying that small talk to Greta Garor were programming languages right it wanted to be left alone。

 the only place you ever got to see it was in Xerox Park right And so the interesting thing about this was that it was leaving the castle right So that was important。

 So the answer was yeah， there had been some weird congruence of events some weird thing where people had been kept in deliberate isolation and some weird experiment where they wouldn't be contaminated by the rest of the world by all practical considerations and they built a system like this。

 but that really can't happen unless it's done by crazy impractical people And so no。

 it's not very likely to happen again。😊，不そ。O。So modern Jits are like kind of viewed as like a black box you kind of put your code in and it optimizes it hopefully fairly well so like like with having written an early Jit。

 what do you think is like kind of like the right level of like information return to the program or like。

You had small talk Im assuming it wasn't a language designed to be jitted in the first place。

You're doing this optimization on it and now people are saying， oh， my code's faster。

 but like they don't have feedback on it potentially or you know they're doing something like looking at the stack。

Are they being told or how are they being unknown like told like this is a really slow。

 terrible operation to do， don't do it or so like what's the right like amount of information or like like how should the J communicate back to like the users like this is where you should be doing or like。

How do you push language， I mean， that isn't just an issue issue for Git。

 that's an issue for everything。Yeah， but I mean， just。I mean， I guess not like。

They kind of do like multiple optimizations over time， so it's even。Jid can do that too。You know。

The the whole question about， I mean， what you're asking actually of is a large and interesting question。

 which is kind of of the information feedback loop between programmers and implementation technology。

 know， and the two always are in a feedback loop。嗯。You know。

 I don't know that I have that good an answer to the question， and here's the reason why。嗯。

What executes faster and what executes slower。going to be affected pretty heavily by the specific implementation technology。

So for example， I mean， to I'm going to take a really stupid example。

 but it'll exemplify the reason that I'm hesitating a little。嗯。

If you have a compiler it that the strength reduction loops。First the compile it doesn't。

The compiler that doesn't is going to complain that you've got this multiply inside the loop。

 and that's really slowing things down。A compound that the strength reduction may be able to remove that multiply replace by hand。

So that's a really simple example。But， I guess， I'm。I'm a little wary of。打。

Kind of feedback coming out of the implementation technology。Now， this may just be because。

 I haven't worked with state of the art program development environments for a long time。

And because every time you need one， you write your own。Well， it's happened more than once。

But I'm a terrific believer in dynamic profiling。And， and I've。And you know。

 I have to credit someone for that， someone who was a manager of the computer science lab at Xerox Park。

For a relatively brief period was Jerry Alkind and he was a great， great believer in measurement。

And he really changed my whole outlook。About measurement as a way to understand what's going on in especially in more complex systems。

And so to my way of thinking that the most valuable kind of feedback that I could get from a programming system。

嗯。Is feedback that will tell me things about the behavior of my program。That。are。Perhaps not。

Tremendously that are perhaps less tightly coupled to the implementation technology。

But then there are things that are on the borderline， for example。

 my language of choice these days is JavaScript。You own my desktop programming JavaScript。

And there are differences of opinion about。There's a good idea not putting else。

 so one of the things that has gotten added to JavaScript。Is a getter and setter functions。

 so you can do something that looks like a reference to a property of an object and it triggers a procedure。

No。That's a really powerful idea and it makes expressing certain kinds of things a lot more convenient。

嗯。But。It's。That's an example of something which in。Almost any implementation。

In almost any reasonably straightforward implementation that I can think of is going to come with a pretty substantial execution cost。

So something that I would， for example， want to know out of an implementation is how much is this feature actually getting used in the code that I'm running？

Now I'm going to turn around and contradict my own argument by saying。

 well you know I said a moment ago and many other people here said the same。

 which is that by doing by doing dynamic profiling at runtime。

 but having that profiling be done by the implementation。

 you know it can see where where these things are being used and whether or not and whether or not it can avoid the overhead of checking for them。

 so。I know I'm talking around your point and that's because I don't have a good answer to it。

It's not，'s not something。That I've ever missed， but maybe I don't know what I'm missing。I have four。

 I them go go for it one of them is and this is going back in history， Alan Pes said。

 list programmers know the value of everything but the cost of nothing。嗯。

And that was to your pointed by Can and incentives right so you look at a piece of code。

 you think you understand it perfectly well in the case there people know about list namely S expressions all have value so the value of everything is the cost of nothing。

 namely that one given you know token and list might take no time at all execute or everything's in long time so the value of good。

But get gets it to be there anyway。That was one of the as。 The other one was it's not an aism。

 was the joke I read quite recently and the most recent gore notes and it really hit home because you may or may not remember that one of the last things I did with Park was work with Frank and Park plates I mean was work with Frank and David on making this heavily instrumented garbage collection system where you could change。

 We made for the last generation of the small talk system I worked on a very baroque memory management system where everything was tuable and available to the to the programr。

 So did you ever use it you weren't silly enough to。😊，KNobs up the was itself。

 only imagine David but David， exactly。 And so， you know。

 and we're talking about the size of all the there all these spaces。 there's large space。 And， and。

 you know， new space and all these different kinds of spaces And you can tune everywhere these sizes the ratios And how often you look at them and bla。

 blah， bla There are lots and nots and does and they're all home default values。 But who knows。

 you know， you might change it And your program might speed up。

 you might not have these dreadful positives and so on。 right So。😊，The most recent， like， go 1。

5 or whatever said that as， as an advance， they say they've eliminated all the knobs in their garbage collector and they say。

 they know that they've damaged the prospects of the。

 what was it the professional storage management knob Tddlers union。

 but they couldn't care less is what they said。 So， so the point is that you're now saying that gee。

 I would like a lot more knobs， right， I mean， the thing I'd like to be pointed out when you know。

 maybe of your own program， right， that you started having knobs and start moving code around and saying this is。

 but， you know， probably， I think the advantage of profiling is。

Since there's no substitute for thought， the really interesting thing about profiling is what it tries to do is it tries to eliminate the vast majority of your program for being worth paying attention to。

 right， Not that it tries to tell you what the answers are where you what you should do to fix the problem。

 But basically saying these are where this is what takes on most of the time because surely you shouldn't be wasting a lot of brain sweat on speeding up the parts of the program that don't take much time。

 But then the next thing where it says this is a part of the program which takes much time。

 and here's why， but I won't fix it for you。 you go and fix it。

 but I know exactly what your problem is。 So I think there's a gap。 if the program knows。

 I mess the custom compilation part。 if the implementation system knows what to fix。

 then it should fix it and then beyond that， you need to know。

Where you should be spending your brain power， figuring out how to speed the program up。

 I think I'll remember two of my four athlete。That's a great question。

 I think we'll be returning to this topic indirectly。

Through the rest of the course as we get more and more sophisticated optimizations。

The combination goes optimization。Removes increasingly predictability of the behavior。

Its definitely topic。I to try and redeem myself for。Spoil like that。Conversation。With a joke。

 which is how you piss off a computer scientist after？In hears of the。

Somebody asked to raise your hands， say， Did't X Sp do this in the7？

Because there's so much came out of there， nobody can quite remember alls。え。Yeah， well， well。

 you know， you don't have to be final them because they can say， yeah， probably。

 I the standard or false to that was didn't IBM do it for 60？So the point of telling this joke is。

Like this paper for instance very influential I'm sure there's just a bajillion things that came out of Xer's park that was super influential and yet if you tell anybody on the street about Xs they're like。

 oh， don't they make like cops or something？So like， do you have any insights， you know。

 so many years later about how an industrial research lab should work to bring value to a company while still having impact？

What did the guys in suits， I think you piss him off by wearing T shirts。

 but did you piss them off by spending a lot of money and not actually making any money？

Or was it sort of accepted the book actually talks about this the deal is the there there have been a lot of books written about Sirerages Park and no answer the light would give would be better than what Daniel Hilsick and other people have written。

The other the first one I guess was fumbling the future， the future that's right。

 so fumbling the future is probably still worth reading dealers of lightning is certainly worth reading。

系。Do you know I was at the national Comp conference when when the Xerox Star was released for the initial show。

 it was really quite an amazing thing because no one had ever seen anything like。

 This is I guess it was 1982 I was in the audience and they had the national computer conference was big conference and they had so you have to understand like nothing like nothing like that。

 unless you'd ever been to park， you'd never seen any of Bimap displays mice。

 know networks laser printing desktop metaphor and the started to be drag things to put in a garbage pail and stuff like that And so I was in that room like it wasn't in the hall。

 I guess and they were shouldn't start， know， they had a laser printer and they had a file server。

 I mean this is 1982 for say nobody even understood what these people were saying the local area network and stuff like this guy with a microphone standing up doing this stuff I had known a little bit about this because I had just met Peter and I knew this was amazing。

 You could find this。right， and so， you know， it really was interesting。

That Xerox actually did have this stuff。 It was there。 They were selling it。So by the way。

 before I complete that story by standing there， I will say that later when I got back to the office I said I'll buy one。

 what the hell right and I called Xerox and I basically said I want to buy one and their answer was no。

😀。No， and they said， well， you know， you add， you said how many people were in your work group and stuff like that。

 Our system is only for work groups of 50 people in larger because and they had I didn't profile properly。

 And so， and I just want to buy the machine I saw。 and they said， no。

 so that might be one reason why they。So but I want to finish that particular story。

 So I'm standing there。 And this guy is waving his army。 He's dragging documents from a file。

 he opens this file。 I mean， they still don't have this action。

 Do remember you would drag a drawer open and youd see files and a filing And you open the file folder and a piece of paper would come。

 I mean， it was like anamorphic up the woo right You remember this。

 It was like it was all seeing demos。 Yeah， it was just amazing。 And they did this。

 And I'm just watching。 I mean complete as is everyone else in the audience。

 right And we're just hanging on this guy to everyone word。

 It's using words with donation locally Are file server you know all this stuff， 1982。

 and I'm saying there。 But there this guy standing next to me。 And I proan except。😊。

Because I'm just the guy says， guys's going shit。Really loud。 It said， fuck me， God damn。Shit。Okay。

It's like， and you know， this guy's here， and I'm really hanging on every one of his words， right。

 I'm really interested this guy and this asshole next to me。

 he's like standing there and he's right in my ear and he's going， fuck me。So you know。

 I'm going to turn this guy and say，S the hell up， it's Steve jump。だめな。いちとす。发来他的。你去。

I think we should handle on that。Thank you very much for come back。

I don't remember you telling that story。あす。So down is her version that Steve Jobs seen this stuff。

 but Steve Jo also saw the stop and this is while he was working on the reason he saw the star。

For the students， please don't leave it， I have your well guys。Okay。

 your assignment here so I can come up and'll get them。😊，他会。

