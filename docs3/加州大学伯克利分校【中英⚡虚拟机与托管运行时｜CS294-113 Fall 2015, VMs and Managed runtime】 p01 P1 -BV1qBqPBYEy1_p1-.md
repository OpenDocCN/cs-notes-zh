# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p01 P1 -BV1qBqPBYEy1_p1-

It traditional to tell jokes or anything like this。M。😊，Hey。Iice said with you desk。嗯嗯。こちは？ですけど。

Everyone knows it。I21。で。大けです。あてげね。S the on you can pull that chair up。我かな。我想。

I'd like to go and to a more what I to。あざある。考同佢啲。this。大家好。Yeah， that's where。I last I in a guilt on。

正解。're to。のよ。就噶。I just this。second point that yellow one 。ね。他这个是。It off share。😀。Mmhmm。😊。

Maybe the trick is to leave the chair open and whoever sits in head Gu or on the AV。Yeah。や我。最こ家この。

这个业务钱可能优一点。we should than I think it's un minutes。はそ。Hi。I。系然。Yeah you know。でまあず。先生もや。嘅。有远都冇关。か。没有。嘢。

あすね。は。そうそじゃない。Time。Okay。It going。So welcome to the first run of this new course on virtual machinesch and manage runtime。

 my name is Mario Walchko， I work at Oracle over the other side of the bay。嗯。

And I'll be teaching this cho Patrick here is the T A who you'll see a lot of and he'll be helping you with the exercises and other stuff。

 and I have only one slide of legal nonsense， which I have to put up because my lawyer made me put it up。

So， you know， don't buy oracle stock based on this coer or if you do， and it goes down。

 don't sue me or anyone else。Or， you know， product decisions or anything like that。

 What having got that over with。 Okay， so what， what am I trying to accomplish。In this course。

 basically I want to get you through the course of this semester to understand enough of about virtual machines to have a pretty good map of the territory and also to have enough practical experience in implementing mechanisms that are common in virtual machine design and implementation that you feel confident of building around that's kind of my overarching experience this is a very practical course and the material that I'll be presenting in the lectures is intended to get you to the point where you can do your own thing in the labs。

How are we going to get there？So I'm going cover。Literature and history。

 I think it's important to have some of the scholarly background here and know what the landmarks are in the field rather than just the of current snapshot of the state of the art and it's helpful to know why particular techniques were developed and what problems they were solving the context of those solutions to understand where they fit in the bigger picture So we're going to definitely look through the history of the field and the literature and well there'll be some some amount of paper reading and study offline that I expect you to do。

Having done that and walked through some of the examples in the class。

 I'll also be giving lab exercises where I you know which will be assigning examples for you to implement and the progression of the exercises is such that you will implement increasingly advanced techniques in the context of a simple or simpler invented language of Patrick's design called Fi which he'll be talking about later。

 so it's meant to have kind of just enough。To require you to understand the main techniques in implementation。

 but not so much as to overwhelm you with detail。 And you'll see as the course progresses being overwhelmed with detail is really easy in this field。

 So I'm going to try and avoid that and concentrate on the ideas and the principles and hope that when you are faced with the situation with lots of detail that you can see way through the detail to the underlying ideas and apply the right techniques。

So we'll start with this language。 We'll do a number of implementation exercises of progressingly increasing sophistication to illustrate problems and maybe fiddle a little bit with the language designed to pull in。

Areas that we think are are useful for， for exposition。

What will happen each week is there'll be about two hours of someone standing up here and talking to you。

 mostly me。I have some guest speakers lined up to come and present some very eminent people actually coming in the field to come and present on landmark papers or to be here for a Q&A around the landmark paper and we'll spend the rest of the time reviewing the assignments。

 results that you get from your assignments we'll discuss the literature that's been assigned for reading。

 and occasionally I'll ask you to prepare some material for presentation and kind of call on。Someone。

 there's too many here to do like everyone present。

 but I'll I'll pick out some that I think are interesting for presentation and we'll discuss。

This week's going to be rather presentation heavy because you know you haven't done any labs or any exercises and you't ready anything so it's just unfortunately me and for a break you get to hear Patrick in the middle。

And。You know， I hope I don't put you to sleep because we're in a small room with a lot of bodies。

 and sometimes my voice can get a little soorific， so。

So I'll try and snap you out of it with occasional changes of tone and the odd spontaneous question and we'll see how it goes。

From the point of view of assessment， most of the assessment comes from the lab exercises and that will be Patrick's department grading and assessing with my assistance you'll see there's a detailed scheme on the exercise for how points are assigned it's kind of not really why I'm here to do that kind of thing I'm here mostly to get you to learn about VM。

 so I don't kind of really care that much we have some amount of schedule and deadlines for the exercises because this is the first run of this material。

 I really don't have any idea whether that's schedule realistic like whether I'm just overloading you with things or whether it's really easy So we're going try and tune up that schedule as we go on。

 So if everyone is behind I'll adjust the deadlines backwards to give you more time but please just you know don't just give up if it seems impossible come and tell me or Patrick that you know it seems like way too much work for。

Amount of time。 And if we hear that enough， we'll， we'll dynamically adjustment。 You know。

 my goal is to get as many of you through this as possible。

ThereSome things I'm not going to attempt to do。 I can't be exhaustive here。 It's a pretty big field。

 I certainly don't know everything about it。 you know。

 even limited subfields like garbage collection would merit 14 weeks of discussion because there's probably 1 thousand00 papers in the field。

 you know， and a lot of ideas and some of them are really。

 really tricky so I just can't go into that level of depth。 It's not exhaustive。

 It's not a compiler course。 I'm not a compiler guy and I know there are a compiler people in this audience。

 So I'm not going to attempt to go there。 I hope you've all taken some compiler courses。

 So will be some compiler related material， but I'm kind of more assuming you have an approximate idea about compilation and again。

 in this amount of time， I can't go into huge amounts of detail in compilation。

The last point you should probably apply to everything you hear， which is， you know， it's not。

 I make no claims for objectivity here。 I have a particular view of the world and my history and a slice of the world and experience。

 and it's going to appeal to that。 And yes， I can read and summarizeise。 But， you know。

 it's not going to be everything in particular， there's going to be under you emphasis on things I'm familiar with。

 simply because， well， it's me here。 And if you want something else， you need somebody else。 So。

 for example， this is a pretty big field。As you'll see shortly。

 there is a distinction into language VMs or process VMs and system VMs。 I touch on system V Ms。

 There's some material here on that， but I'm by no means an expert。

 I don't have a lot of internal detail。 I have some pat excuses as to why I don't have that detail。

 which we'll cover later。 And I'm just not going go there in any great detail。

 If you want to know more about that， you'll need to read the literature。

 I'll find someone else to talk to。So who the heck are you or who the heck am I and why am I here。

 So I work for Oracle。 My title is architect， which is a technical grade and not a function bizarrely enough。

U。I've worked on virtual machines on and off for about 30 years。

 My first virtual machine project was my master's thesis， which began in 1984。

 which was building a small talk virtual machine。I've done a whole bunch of stuff mostly at sun on a variety of virtual machines。

 the self virtual machine， which will figure prominently in this course from in the mid-90s and then a variety of Java systems since then。

 and I've dabbled with stuff like binary translation as well。 So I know a little bit about that。

 I'm currently employed in Oracle in the research lab which was founded when Oracle acquired Sun from Sunlabs。

 and I founded and championed the VM research at Oracle after the foundation。

 which is now a healthy and thriving organization， and we'll see some of the work that's going on towards the end of the course。

 when we'll get sort of closer。To the state of the art， my。

 my intention is that by the time you leave here， you have a pretty good understanding of the state of the art。

 But to do that， I have to。 I think my belief is， I have to take you through the historical。

Background and kind of take you through the steps of how we got there。

 If I just give you where we are right now， it would be。Puzzling， I think， to say the least。

Why am I doing this？Well。More people need to know this。By any reasonable metric。

Virtual machines and managed languages are a very large part of computing today。 If you look at。

 for example， any of the indexes of the world's most actively used or popular languages。

 there's really only one family that isn't based on some kind of underlying management or a VM。

 And that's， you know， C， C plus plus objective C， the things that were derived from C。

Most of the rest use some kind of underlying managed system or runtime or a virtual machine。

 and yet my experience from industry is trying to find people who know that stuff to hire them to work on things is very。

 very difficult。 very few people seem to know their stuff despite the fact of it's ubiquitous。

 And so I want to increase the size of that population and it starts with you。

So this is a first step in that direction。U。Besides which it's actually a pretty fun and interesting subject。

 very practical， very applicable。 if you do anything with language implementation or you work with programming language implementations。

 understanding this， I think will help you。😊，A more tricky question is。

 why is Oracle Ping me to do this。 And it's the same reason more people need to know this stuff。

 right， we， we have， we don't just do databases。 V Ms are a core technology。

 We have V M groups doing all sorts of different language implementations and systems We need to get people who know how to do this to hire them to。

 to have our customers understand the technology The candidate pool for this is desperately small to give you some indication。

While I am certain there are at least a three digit number of people who I would say are VM experts。

 I am also certain there is not a four digit number。

 So we're talking about sub 1000 people in the world wide candidate pool to do this kind of work。

 which is kind of amazing， given the ubiquiity of the systems。 So again， this starts with you。😊。

So what are you going to get out of it， well， you'll join that elite club。😊。

Of people who know V M internals。And you can come and， you know。

 plausibly speak in a job interview or some other forum about what's going on inside of the M。

 which is， as I said， desperately for people。 And you know。

 there are the usual corporate reasons here。 We have interns。

 we need people to work on stuff as interns。 you might get inspired by some of the topics here and the challenges and do PhD in this area or some other activity。

 and we hire those people。 So think of that。 But more most of all。

 I hope you will do it for the same main reason。 and I do it， which is it's fun。😊，Okay。

 enough about me。 before we go on， I would like to know a little bit about you。 And so quickly。

 I would like to go around room and have you say your name。

Which three programming languages you feel most proficient in。

Which is your favourite programming language。 It need not be one of the first three and give me one sentence describing the program or part of programme of which you are most proud。

 so。Patrick， I will start with you。Patrick， Im your T for this course。And'm best at。Gva risk。Standza？

My favorite language is stands。The program I'm most proud of is that？Okay， easy。I'mJame。

 three most proficient programming languages。Prof I Hakell。Python and C。

program I'm most proud of is probably。I have very large number。哎。うんだが。嗯。

Faculty here sponsoring the class。3， wow， I guess。Sttanandza。Is one language。Schola SequL plus。

 favorite language stands up。あはい。😊，Program most proud of。I was throwing out jizzle。Okay。

I'm Yole Huntchlyersmith。First year。And my favorite programming or my most proficient programming language is our Java C。

S amazingly。使か？PeoplequalActually might be my favorite because I'm not。Okay。that I am。

Out of is probably this little database relay piece that helped us scale up a very large social networking。

My name is Liang Gong， so three most proficient language for me is Javascript， Java and。

And my favorite language is JavaScriptscript。And the program number。Most the problem。I mean。

 Alice this is the framework for checking backward。交。はいア Ben。First fourth year。

my three most pro languages。C slash C plus plus sort of in the same category。 go along。

The reading is among them so far。Okay。诶么。The program of most problems so far were kind of a collection of tiny programs。

Sstem。Charles， I an O PhQ student here， the three most proficient language is probably C Python and Pel。

I'm most proud of this。Programs need to extract traces from。Okay。have to run more than。

You found out for a senior Ph student。My three most proficient program language will be C。

 Python and go， and my favorite language is go。AndThe program was。Theres probably a。

A piece of code I wrote。That basically。With a lot of。Thequest stream。Hi， I'm Julie。Professionally。

Lguages are probably。Python， JavaScript。I guess。Pro I'm most proud of is probably。

Mashley I worked at in theAP lab， which was a genomics。And then。you聞してまroom。

My favorite language was plus。而行我证。There one can be。I down and Javava I guess are also there。

Most of my that were just second。呢个啊。I guess my favorite project was Altor。啊，我知。Okay。Hi。

 my name is Jack， so I'm a first year master's student here。In the fixed and master's program。

To be overlook the under。And the three most proficient programming languages I say Python。

 Java and C pass。 and so from my favorite language is Pyon。Okay。Favorite program。

That was from the last。Dbut， he me。Okay。Hi I'm Frank， I'm a third year at PCU student here。

 I actually have the same set of programming languages。あじか。I thought its my favorite。

And I guess the program was proud of。Probably the library that does work。Okay。Hi， I'm Rohan。

 just joined here last week of my firsthand PhD program。

 three most proicient languages for me would be Java。Javascript。

And CDC+ plus major my favorite language is hasto， although I would't be proficient in。嗯。The program。

 which I'm most proud of could probably be a chess AI engine that I wrote one summer just a bit and everything time。

Hi， I'm Vdia， so I'm a third year case student here。

 so the free language should be like say Scala and JavaScriptscript and I think my favorite would be the Scala and I think the program。

I'm part of the big mark project， so that was a S DSL。

 which used for GPU computation and for machine learning。呃，他难。Parttition in Python Java， C+。

It's probably steep bus。And I guess the program that。Mospart was。I did an internship two years ago。

 that I kind of just took it data from the database and I distributed it。Orizing。I'm Sheey。CC++。

 Jala， I。Java， the Lo。嗯。programgram I wrote for doing design Spaces。Generating。哈国人。喺我人。这样子。My agree。

Java and Scala， my favorite language is Python。Like functional languages。The program at most。

Pa check service for。Basically， just automatically。あ。Nathan， three most proficient languages。Well。

 so C is。A easy one， then kind of a big gap in Python， and then a really huge gap。I wrote something。

😀嗯。😊，You're an expert， then， yeah。Yeah， 99% of things I've written is。The program I'm most proud of。

 probably a little sort of like operating system I wrote for a Motorola 68。

000 based board that I built in a classroom。I'm a settinging year PhD student。Probably jealous。あ会談。

question probably in Java。Of course。And probably my favorite program I've written was a little compiler。

私た？And Martin， female Pro languages says C++ Java and Python private languages。Probably use Sc。

And problem was product， I went with a minimal job version machine， but nobody committed。

venova great。Michael。See Python Java。Fer language is， I meany。う。Right。Fudian slip。

Program on most part of。Oh， I wrote it like Python to Kudes C training。Okay。Okay。I'm Raphael。はすか。はい。

My favorite。ポスちード。They're lot interesting program。十三。😀H。😊，Okayなた。My name is Larry Ro， I'm also。

I was thinking if I really honest， I would say the light。Profiated their for track。はは。I' most proud。

the pilot I wrote when I was。as an undergraduate。Actually。

 the one I think I'll say is what I've been working。Six months， which is。A program to sample。

Bending for。嗯。And the color。Okay。My name is Chris。没月份。this。😀Mm。😊，My second one here。once这个3。对？

Programing probably。Okay。いうあ。テパ。こはい。嗯。Hi， my name is Adam。やつは？

The program I was proud of is what I'm writing right now。Like。Okay。Hi， I'm S。Languages are Python。

 JavaScriptscript and to see， most favorite is Python。

I was proud of is read autograator slash submission software used by， I guess， a0 plus undergraduate。

当日。Okay。I'm forward。这个是你自己。My favorite language is SL plus。I'm most proud probably of my nail。

My name is。でのかな。い配が。My。We'm most proud of the。And Cambridge。Program， I most part。他这。交。就一条。That how。

じゃ可ね。How we。I'm a second year PC student。まピ？Most efficient programming languages are C， Python， Java。

 my favorite language is O Caml。😀。Wouldn't that be professional of came away？Yeah。

My favorite program， which I've written is links kernel schedule that I work for an office。Pson。Mmhm。

Okay， so my answers to these questions， I think probably most proficient in C。Small talk。Maybe south。

 my favourite was probably fairly， certainly south。

And the programme of which I'm most proud is probably a tiny little implementation I did of a longest common subsequent algorithm in small talk。

 This is like， if you're familiar with di， it computes what di computes。

 and it was kind of nicely written and picked up by quite a few people imported to other languages based on that implementation。

 which is not。That common。Okay， so one other question， which we can do with a show of hands。

 Well actually， I'd say it's a multipart question， who here has written an interpreter， Ra your hand。

A compiler。And a virtual machine or work to a virtual。 You're not written the whole thing。 but okay。

 alright。Okay， so。😊，That's the meta materialal over。We'll dive into the real material now。

 I also wanted you to mention the slides I have put on Piazza。

 Feel free to download and follow along。 Please don't read ahead because what I'm going to do occasionally is ask a question。

 and I want you to think about the question before you see the answer。 if you just scroll forward。

 you'll see the answer and then kind of youll lose you'll lose part of the value so。Alright。

 so this is today's fairly gentle introduction to the area。

 we're just really going to look at terminology， some background material。

 and I want to look at some VMs you'll see that the terminology and the definitions are not crisp There are very blurry lines in this area between the different subfield and so rather than spend a lot of time。

😊，On something that I think is of limited value。 I'm gonna spend。Most of the rest of this。

 this first section on looking at a handful of different VMs from a very high level。

 just to give you a sense of the diversity of what's going on in these systems。They all use。

 you know， common techniques that we'll cover in the rest of the course。

 and may pull some of those out as we go along。 But just really to give you a sense of where we're headed。

 what we're trying to cover。 And then after that will will start going into interpretation for for the first technique。

 So I have some terms I'm going use and definitions。 Some of these I just made up。

 So feel free to argue with them。 because as I say。

 there are there are sometimes there are no real good definitions available。

 Some I still from this book by Jim Smith and Ravenir came out 10 years ago， Virual machines。

 This is a good book。 I haven't found anything in here that's wrong or false or that I would particularly take issue with。

 it's not a handson approach。 It won't teach you how to do things。

 It's more a survey of the state of the art and the history as of 10 years ago。 So it's a little。

Dated now， there are some developments that aren't mentioned in here， but it is a good book。

 and it's very scholarly。 It has， you know， very authoritative list of references and。

And all of that stuff that you want from a book。 So highly recommend it。

 Chapter 1 is kind of the big overview of the field and the terminology。

 and they try to do the same thing， which is break stuff down into a classification and different kinds。

 and I'm stealing their classification， but I'm also going to raise some some question marks over the boundaries and the blurry parts as we get into the techniques。

 I'll introduce other papers and the odd book as appropriate。So the generic VM architecture is very。

 very， very simple。 This is about the only thing you can say that applies to every VM， I think。

 which is， you know， there's something above it and there's something below it。

 And there's there's an an interface between them。 Now。

 I've drawn this using instructions set architecture as as the interfaces that also is not necessarily correct。

😊，And I've drawn this with a guest， the one above and the host， the one below。

 And I've drawn them in different colours to indicate that they're different。

 but they need not be different。 They can be the same。So picture aside kind of what is a VM Well。

 so I would claim it's a software implementation of some kind of machine architecture we can now quibble about what that means。

Now， because it's software。 that's why it's virtual。 You can't have virtual hardware。

 You can only have virtual software。 So it needs it's made of software。

 but obviously software needs hardware to run because software without hardware is just a pile of bit on a storage medium doesn't do anything。

 So you need hardware underneath。 So that's imply too。 And as I showed you on the picture earlier。

 there are two architectures involve the guest and the host。

 although they might be the same as I said。The guest， the thing above might be an abstract machine。

 something that doesn't really exist in any other incarnation。

 or it might be an emulation of some other real machine thats I。e。

 something that's available as a piece of hardware that implements the same interface either of those it's still a virtual machine in my book。

 The host， the thing that sits below the virtual machine is usually hardware。

 but it need not be right So you can write a VM for a language in Java。

 and that VM will run on the Java Vm so you can stack Vms。

 and I'll show you a kind of semi-rious picture of that later on。

 but we do we do do the stacking thing Why might we have the same architecture above and below what benefit does that bring。

 that really takes us into the area of system virtual machines and the idea of being able to run something either in a sandbox to be able to monitor and confine it or to pass。

the underlying resources in some way and yet present the illusion that the thing above has access to an entire system。

So a typical VM might look like this has some kind of virtualized application running on top of the virtual machines instruction set architecture and then some software。

 and then some hardware below。And it all fits in with what I said on the previous slide。

So let's look at a smattering of VMs and their properties just to see what the variety looks like so I've picked five here that I'm going to present a few slides on the Java virtual machine。

 virtual box， Rosetta， dynamo and Crusoe， you may or may not have heard of some or all of these and they're all different in some interesting aspect。

And I'll explain the terms as we go along。 So let's start with the Java virtual machine。

 I'm pretty sure that you've heard of it and I hope you've used one because otherwise life is going to be difficult as we go through this course and this is a good example of a language VM Ie a virtual machine that that was originally designed to run a single language。

 obviously Java in this case。 Now this particular one has been repurposed for a whole bunch of languages so you can run all of these things and many more scholarlarthenclosure Jruby Javascript on the JVM but that was not the original design point and you can see when you look at some of these implementations that have been done of language VMs on top of the JVM that some fit better than some of very awkward and ill-fitting and have to go through contortions to make things work or lose large amounts of performance。

 Now there are many other language VMs and there's a very big。

R of sophistication of the implementations inside those VMs。

 And one of the things we'll cover over the course is that range of sophistication starting with a simple progressing to the complex。

 So you can see all of these languages， which listed in the I think the top 10 or 20 language index。

 you know， they' all are based on some kind of VM or managed runtime technology。 So you know。

 most of you had， I think some one or more managed languages that you regularly programming。

 thankfully， many of you also said you were proficient in C or C plus plus because these have to be implemented in something that isn't managed below it。

 And so we need that knowledge too。😊，嗯。So the language VMs really sorry the Java VM was first developed in the mid-90s kind of Java was invented as part of another project at Sun in the early 90s and it's very reminiscent of earlier language VMs from the 80s and the late 70s in particular Pascal had a particular VM。

 the P machineach VM which I'll talk about a little bit probably next week and small talk which was a landmark VM for its time I'll cover in a little bit more detail。

 but it's very similar to those， it didn't really add anything radically different to those ideas。

 however it did get massivefully adopted unlike the predecessors and that resulted in a huge amount of industry investment into developing and refining implementations of the Java VM。

This kind of big watershed in VM language VM development in the mid-90s where it went from a minor discipline in which you know you could kind of get all the experts in the world in a room this size to you know a massive thing with hundreds and hundreds and hundreds of people implementing VMs and millions of dollars being poured into R&D for VMs and that was the big change eye witnessed that sun in the mid-90s。

 for example。It led to there was kind of an big outgrowth of research in the late 90s and early 200s on a lot of implementation techniques。

 particularly around things like garbage collection。

Whi before that was limited in sort of scope and ambition and suddenly had to expand that scope and ambition and especially in concurrency。

 because Java was really the first very widely used language with any kind of concurrency facilities built into the language。

 and so that was important to get that right。It's been deployed at a huge range of scales。

 so the smallest Java VMs that you could plausibly call a Java VM run in tens of kilobytes of memory on sort of sensor platforms。

And they go up from sensors through things that are modestly bigger than that feature phones。

 You remember the old phones before they were smart。

 where all you could do is like make a phone call and wear your thumb out texting。

Used on those smartphones，'s every blueray player has a JVM in it because the blue Ray standard requires Java Bcode as one of the ways of building an interactive blueray application。

 many other appliances of JVMs in it， the original Kindle had a Sun JVM in it that was before they switched to Android tablets。

 laptops， desks ups， you know。I'm pretty sure most of you。

 if not all of you have a JDK installed somewhere on your laptop to run random things。

 but it's not just like C S students do that。 You know， most of the world has a JVM in it。

 And then much larger systems， servers， clusters and cluster applications that are written in Java are based on JVM。

 So it's this huge。huuge range of coverage。 and we're we're kind of going to do a dissection of the JVM architecture in in a later lecture to look at the properties of the architecture and the design and try and understand how the pieces fit together and why they might be like they are and maybe how they could be made better。

This isn't the only thing at this scale right， you've got things like Microsoft's common language runtime。

 which is also widely deployed， perhaps not quite in this range。

 but also millions and millions and millions of instances running with many of the same properties one interesting kind of blurry example of the blurry distinction is is the Microsoft C a language of VM。

 I mean its runs C sharp and it runs a bunch of other languages。

 it was intended to run a bunch of other languages。

 but it seems very C sharp centric and so it's not a crisp yes or no。

 it's a language VM or not a language VM it's a little blurring。So here's my sketch of the JVM。

 There's an instruction set architecture which involves Btecode。

 we're look to Bcode a lot more next week， you hopefully are all familiar with know writing applications in Java compiling them to Btecode and then running on the JVM and the JVM runs on some underlying platform and typically the JVM is written in some other language like C++ the main VM that Oracle ships is the hotspot JVM which is written in C++ it's 3ishhm lines of C++。

And that compiles down to the hardware ISA that runs underneath。 Actually。

 that's sort of a little bit of a cheat， more accurate picture in most cases is that there's an O S in the picture。

 And so the JVM runs on top of the O S and uses a bunch of O S services。

 but not necessarily there are JVMs that run directly on the on the hardware and do all of the management。

 So that in those cases， they are their own O S。嗯。So as I mentioned。

 it was the first widely adopted language with built in concurrency。

 and we can probably quibble about that too， but it depends on your definition of widely adopted。

 I guess。U。The early JVMs ran on a single O thread。 The very first one just used one single thread。

 and it multipleed the thread level execution of Java onto that one underlying implementation。

 So it didn't matter how many threads you wrote at the Java level。

 you only ran one thread on the underlying hardware and that was done mostly for simplicity at the time。

 And the way it happened was that the thread switch took place at a bycode boundary。

 So it ran one instruction of the ISA and then decided at some point whether it was going run an instruction from another thread。

 And thats that implementation is sometimes known as green threads from the original name that was given to that technique in Java green was the name of the O underlying the internal sun Exp implementation。

 The language then was called O。 And but the more general term for this is cooperative multithreading。

 So each thread。Yields to other threads。 There isn't a notion of preemption。嗯。

Certainly not hardware level preemption。 current G VM's map， typically， anyway。

 map Java threads onto the underlying OS S threads。 So you get to use whatever the O S。

 whatever concurrency the OS S provides in terms of exposing the underlying hardware。Okay。

 so that gives you one thing。 hopefully nothing。New and strange there in the course。

For the exercises， you'll be running within a virtual box image so that you don't have to do any software installation other than virtual box。

And Vit B is an example of a system VM that runs X86。OS S is and applications on X 86。

 which you'd think， why would you need a layer of software when the hardware already gives you that。

 Well， it's because you want to do something different， right。

 The classic example is you're running on a Mac and you want to run a Windows application。

 Do you really want to install Windows and partition your disk and boot into Windows。 No。

 you really would like just an application that you fire up that gives you the ability to run Windows。

 and that's that's the main use in this particular kind of system。

 it's to run multiple guests simultaneously so that you can run the one that you do most of the time。

 but you're not hugely inconvenienced when you want to run something different。

And there are a whole s product from a whole slower companies in this space and open source implementations。

 too， I think I could fill a slide with the names of systems that do something like this。

 But the big ones， some of the big ones at least haveve listed here。

 V Mware was the one that really kind of。Got this commercial enterprise of virtual machines revived in the 19 late90s。

 early 2000s， I guess we're going to the history of system Vms in the later lecture we'll we'll go back into the 60s where where they had their origins。

嗯。So what does the system VM do， this is your normal picture applications in an OS and a hardware with a hardware ISA and what you do is you take away the hardware and you slide in another application which is a system VM that runs now on some other hardware or maybe it's the same and now you get the opportunity to run two OSs and if the VM does translation between ISAs。

 you get to run a different ISA So virtual box in particular looks kind of like this。

 you have an X86 underneath you have some host operating system and virtual box and on top of that you get to run multiple guests which can have their own Os in their own applications and virtual box partitions the world up for them and gives each of them the illusion that it's on a computer of its own when in reality it's sharing the computer with other applications and systems。

And note that， you know， the red is the same because the ISA interfaces above and below are the same in this particular case。

If you go back to the 60s and 70s where system VMs really got going IBM in particular。

 you have a slightly different picture in that there is no host of S here。

You have a thing called a virtual machine monitor now often called a hypervisor running on top of hardware directly and what the virtual machine monitor doing is slicing up the resources of the hardware into partitions and then presenting those out to guest operating systems using the exact same interface。

 So you can have multiple O Ss running on the same machine as peers。

 noticeice there's no kind of none of them as privileged in any way above or special compared to the others。

 they're all on an equal footing。 And the reason for this particular arrangement was in the 60s。

 computers were very big and very expensive。And。You know。

 different departments in the same company might want to run different applications。

 and those applications might only be available on 1 O S。 and IBM at a range of O Ss。

 So how did you run， How did you show your computer between two applications for different O Ss。

 This was their solution they came up with the virtual machine boundary that SAT above the physical machine boundary。

 but mimicked it and partition in the world so that multiple O Ss could run simultaneously。

Like I said， it began with system 360 in the 1960s as a kind of an afterthought of the design。

 and they identified a number of problems with the 360 ISA that they had to overcome and then in 370。

Which was in the 70s they sort of fixed those problems and the I SA is sort of cleanly designed for this point of view。

Time。From one0。That's a good question。 And I would have to look at the literature to see if there was a mechanism。

 I think they did have。Some kind of。Sudo networking。 So。

 so you opened something that looked like a network connection。 But in reality。

 it was implemented as maybe a shared page or something like that。

 I think they did have some high speed communication。 but the communication， I believe。

 was such that。It was the same interface as if the two applications in OSss were on different systems so that you didn't build in a dependency on the underlying V VMM technology。

There's a whole bunch of papers from the late 60s and early 70s from IBM on these things。

 and they they make for interesting reading， although you have to。

Sort of warp your minds to put yourself back in the days of card buttonttinges and stuff like that。

Okay。Another kind of。VM， like a little bit like virtual B a system called virtual PC that came out in the late 70s in the late 90s。

And this is similar to virtual box， except the the big difference I want to emphasize here is the。

The instruction sets are different so the idea here was that you could take an X86 OS designed to run on a PC and you could run it on a Mac by having virtual PC do all of the mapping and translations down and so implied in this is that code running here in the X 86 ISA has to be translated on the fly or interpreted or some other means down to PPC and that translation technology even though the context I will describe it in is a language context rather than a system VM context is basically the same in these kinds of systems。

So some， some definitions that come from the book。嗯。

The book divides the world into process VMs and system VMs。

 and the distinction is that a process VM implements the application binary interface whereas the system VM implements the OS hardware interface so if we go back to a picture like this。

 the application binary interface is this part of the line between the application and the underlying hardware and this part of line where it's talking down to an OS and if you sort of compose those two things you have an interface that the all applications on Windows and X86 have to run on So when you name an ABR you always name an OS and hardware piece of hardware。

And so a process VM is something that implements an ABI whereas the system VM sits and implements the hardware interface this is typically the instruction set architecture in both user and privilege mode because the privilege mode is the thing that the OS expects to run on and that's the distinction between those two。

 and then the world under system VMs divides into those that have an underlying host OS like virtual box or virtual PC。

 or the classic system VM it's old， and so couldn't come up with a better name than classic which is the kind of the IBM style virtual machine monitor。

 which isn't a full OSt you can't run applications on a virtual machine monitor。

 it just looks like a bear machine。Even though there's a piece of software on top of a bear machine。

And just to make the contrast。Really explicit。 So a hosted VM has an operating system that is the host and therefore is going to be。

 in some sense。Preferred more perform and， and likely to。

To to work better than applications running on the guest VM。 So here we've got an X 86， a Mac。

 in fact， running MacOS and of course you can run MacOS applications on MacOS but one of them you can run is virtual box and on top of virtual box you run Sa Linux and even though youve got two Oss here this one will run at full native performance and this one probably won't because there's almost always some kind of loss of performance as you go down this translation as you go down this stack。

What about stuff that's accelerated？to run directly on。

Then you have to emulate whatever interface is provided in the accelerator。So so yeah。

 so you either have to map stuff down to the underlying hardware and pass things through or you have to provide your own implementation。

 if for example， you had an accelerated feature on MacOS， which wasn't available on Linux。

 then you'd have to map whatever it is that's available there down。

 So so if it's just a straight pass through， then there's minimal less of performance。

 but the more you have to fake what's going on in the real hardware the sort of the worst things tend to get。

Okay， so number three。嗯。Is a system How many people remember this or is thatta on the Mac。Yeah。

So back in 2005， Maxs were all based on power PC chips and the decision was made for whatever reason to switch from power PC to X 86。

And then they had a problem， which is you introduce a whole bunch of new machines。

 They put their O S。 They put their own applications。 But what does the installed base do， right。

 I you have a。A machine running a set of applications， and I give you another one。

 and it won't run those applications。 You might not be so excited in buying it if you have to buy all the applications again all at once at the time that you buy the machine。

And so as a bridge to soften the blow， they introduced a binary translating virtual machine called a Rosetta。

Which would run power PC applications on top of。An X 86。 and it it looked like this。

 So you had your power PC application with a Rosetta underneath that Macs underneath that and the X 86 at the bottom。

 And they did it in a way such that you weren't really even aware that this was present。 You。

 you invoked your binary as if it were just an X 86 binary and the O S ensured that this layer got slotted underneath so that you couldn't。

 you couldn't tell that it was there。 And and that that was an effective bridge。

 It was actually an instantiation of a binary translator called Quick transit。

That was developed in the UK by actually at My Alma matha。

 Manchester University and then spun out as a company。

 and they did a general binary translation system from any ISA to any ISA， yes。Yes。

68000 per power PC。 That's right'。Yes， that's right。 That's right。

So this system instance to this binary translator that the company subsequently got acquired and well how did it work when you invoked your power PC binary。

 the Rosetta layer was inserted by the OS and that performed some combination of interpretation of the instructions in the binary in dynamic binary translation。

 taking a chunk of machine code from the running application and translating it from power PC to X86 and running it inside the Rosetta running process and because the new machines were faster than the old machines the applications ran about the same as they did as the old hardware so what you gained in machine performance was lost partly by translation。

 but it meant that your applications didn't feel any slower running on the new hardware so people were comfortable buying a new machine running their old applications and then waiting for。

The ISVs to provide new versions of those applications on the new hardware。

 so that was a very practical usage of a virtual machine and binary translation and as I said it was a sentence such thing as you mentioned and they used a dynamic binary translator earlier to do the same trick from 68000 per PC and there's a description。

On Wikipedia。About that。So is it a system Vm or a process V M question。Who thinks system V M。

Who thinks process vanm。Well， does it implement the A or the API？ABI or APII。It's the API， right。

 because it just runs an application directly above it。 It's not running a guest O。 It's running。

 And so therefore， it's a。It's a system VM。 sorry， it's a process VM right runs the A， the A BI。

 not the API PI。Okay。Number four。Dynamo， not to be confused with dynaite。

 which was the research publication version of the quick transit。

Binary translator Dynamo was a system developed HP research。

And that ran binaries for P risk for a particular range of machines。

 And what it did was it dynamically reopimised hot parts of those binaries to run faster。

 So the idea was that you would run your program。On this。Reopimr。

 and it would run faster than if it didn't run on the re optimizeimer， but on the same hardware。

 So the the goal was to make things faster。And this this particular system was an example。

 perhaps the canonical example of a particular compilation and optimization technique called trace driven optimization we'll have probably a whole afternoon devoted to trace compilation much later in the talk I'm not by any stretch of the imagination。

 a trace compile or expert and I have a guest lined up to come and who is who'll talk to you about the state of the art。

 but we'll cover some of the literature of this。 But this was in some ways。

 the canonical example in that it was very well documented in the literature even though it's not by any stretch in the imagination。

 the first such thing So a unit of optimization when doing trace driven compilation is an instruction trace which can span sort of an arbitrary part of the binary。

 it's more than a basic block， it can even be more than a single procedure or function it's just a list of instructions that as they were executed by the program at some point。

In the history of its execution。And so。What this compiler。

 this optimizer did was it gathered traces while interpreting and then analyse the traces and emitted an equivalent。

 but hopefully more efficient。Trace that the program could execute thereafter and then attempt to make the program faster。

 And what they report in the paper is that they made unoptimized programs faster。

 but optimized binaries not so much。 Now， you might think， well， what's the point of that。

 But the reality is most binaries that are distributed in the world by independent software their vendors are unoptimised binaries because they can debug them。

And so there， there was some utility to this。 So let me draw you with the schematic。 So this is the。

 the before picture with an application running on H P U X on a P 8000。 And you can see the。

 the US interface and the the hardware interface here and what you do as you。

Slot in implies the application an instance of Dynamo and now your application runs on Dynamo。

 it passes through the OS calls to the underlying OS。

And the hardware instructions are mapped onto more efficient hardware instructions。

 but from the more efficient sequence from the underlying system。Okay， and to round out。

The collection I'm going to say a little bit about Transmeters Crusoe processor。

 So this is an example of another flavor of VM known in the book as a co- designedigned VM。

 which is that the VM was designed in conjunction with a chip。

 a microprocessor And the idea was they always went together。

 you never used the processor without the VM or the VM couldn't run on anything other than that processor。

 And the idea was that we there would build a VLIW architecture。

 is everybody familiar with VLIW or at least what it stands for anyone。Okay。

 so very large instruction word， basically a very unusual take on instruction set machines。

It would implement this VI W architecture， which was kind of in fashion at the time。

 and through binary translation would mimic an X 86。 And so when you got the combination。

 the chip and the and the virtual machine， it would have all the behaviour of an X 86。

 and they would compete with X 86 is， at least on。Power efficiency。

 So the idea was to be performance comparable to an Intel or an AM D X 86。

 but use less power and and therefore get adoption in mobile devices where power was important。

 And and the goal there was to eliminate the power hungry hardware from a standard X 86 implementation such as the sort of the very complex X 86 instruction decocode unit。

Do that in software once rather than in hardware on every execution。

 saveve that power and run as fast， but with but with less energy usage。 And it was actually。

 you know， it became a product。 and it was adopted and used by a variety of companies。

 There are pictures at the top picture on the left as the chip itself。Taken from， I think。

 Wikipedia page and the on the picture on the right is an actual shipping laptop that had that had this chip in it。

 So it， it did have some amount of success。 and it certainly was real。 There are a lot of V Ms that。

Whose reality is questionable？Um。So this actually shipped， it was introduced in 2000。

 they built a follow on in 2003。嗯。This is kind of the architecture of it。

 They called the VM a code morphing system。s on term has only ever been used for this system， so。

Probably not something you should spend a lot of time memorizing。

And it presented literally a hardware interface， so not just the OS and the applications。

 but the bioOS， everything was standard X 86 software。And。

It would boot and run the O S and all the applications。

 and the code morphing system would map the X 86 code down into the V I W。 And it is， again。

 many of the techniques that we'll cover later feedback driven optimization and speculation being the main。

 too。 It's also fairly well described in the literature。

So they also interestingly provided hardware support for the translation system to try and make it more efficient。

 so there were microarchitectural features such as extra registers and a kind of almost like a transaction function where you could speculate and assume a particular transaction could be used but you wouldn't know for sure whether it was valid until some later point and then sort of the transaction。

 the gated store buffer and the rollback would save you in the event that your speculation was wrong and we'll be talking a lot more about speculative optimization in a future lecture。

Okay。So here's the taxonomy from the book redrawn slightly from their presentation。

 so we have process system VMs， same ISA and different ISA。

 if you're a process VM and the host and guess of the same ISA then you're a dynamic binary optimizer or if you're unlucky you're a dynamic binary deopimr and you make things slower。

 not quite clear why you would want to do this if you're making it slower other than perhaps instrumentation or monitoring tracing。

If you're a process VM and you have a different ISA， then you're a dynamic translator of some kind。

 And that's sort of what language V Ms do。 They don't really implement。An A B I。

 There isn't a Java A B I that exists independently of the JVM。 So again。

 it kind of gets blurry here， the， the， the the， the categorisation。

 but that's the best place to fit those。Then on the system VM side where you're implementing the machine ISA。

 you have the classic system VMs with a virtual machine monitor， the hosted VMs。

 those are mapping the instruction set onto itself。

 and then you have below that the whole system VMs and co-designed VMs that are mapping to a different ISA。

 the co-designed ones have some special hardware stuff to make them more efficient。

There are a bunch of other terms that are thrown around in this field。

 And I'm going to mention some an attempt to give some idea of what they mean。 But， you know。

 the usual thing from these is you'll sort of recognize them when you see them rather than。Finding。

Of precise definition。 So emulator is a word that's used a lot。

 A machine emulator is typically something that mimics a real instruction。 set I。e something that's。

Also implemented in a piece of hardware， physical thing sometimes it's just the user mode and not the OS mode and usually they're not anywhere near as fast as the original system if they're slower or if they emit some level of detail or they're there to allow extra observation they're often called simulators so you know the classic classic definition simulation is in a simulated rainstorm no one gets wet。

So a simulator has to emitm something from from the detail and not， but not everything。嗯。

So they might， for example， emitm side side effects， right， a real system has a screen an output。

 and you see those things where a simulator might just that screen might be just a thing in memory with no actual visible representation。

Or it might have a funny sloppy accounting of time relative to the real thing。

 and it can allow for know all sorts of other observations or or measurements。

 Q mu is a good example Ss is another good example here of something that can be used as a simulation framework for an IA。

 note that the term emulation isn't confined to this field。 You can emulate anything right。

 You can emulate the Windows API code weavers crossover， emulates the Windows API on a Mac。

 but it's not really a virtual machine。 And you can have something called an in circuit emulator。

 which is a physical device。 you know you pull out the chip。

 You plug in this device it has a bunch of wires that go off another piece of circuitry that mimics the original thing except it allows you to you patch it or stick in oslloscope probe in it places that you couldn't do that on the original hardware。

 So emulation isn't more general term。 But you'll see often used in conjunction。

With virtual machines。Interpretation interpreter Jt will get onto that。

 That's the subjects of the upcoming lectures。 virtual machine monitor we've already mentioned。

 A hypervisor is kind of like a virtual machine monitor。 It's hard to find a real distinction here。

 hyperpervisors seem to be more associated with partitioning i。e。

 kind of splitting up the resources and then getting out of the way and let the instruction map onto the underlying hardware and they may provide some kind of a virtual device interface rather than a real device interface So an abstraction of a device rather than the real one。

Soce and Taet are sometimes used as alternatives to guest and host。

 you'll see that especially in conjunction with translation。

 So So is a confusing term here because it you know there's no text here。

 there's nothing you can read， it's still a binary。So， you know。

 one one person's source is another person's binary in this case。

And then native and virtual instructions that architectures correspond to host and guest and that also is used more in the the language of E M context。

 and the hardware ISA is the native ISA typically。是。Before you get into this。

 you often say virtual machine and manage on time system as if they're different。Yeah。

 I'll get onto that。 I have a slide。So you can stack these things， as I， I said。 And here is a like。

Realistic。 Well， it's， it's not realistic。 And I'll explain why。

 but a plausible picture of a stack of virtual machines。

 I have a ruby application running on top of J Ruby。

 which is an implementation of ruby written on in Java running on a JVM in Linux。

 which then is running on an underlying Windows system using virtual box。

 And then that's running on top of a Crusoe processor with a code morphing underneath that right this there's no reason why this wouldn't work。

 the reason it's not real is because Crusoe and transmittter went out of business before J Ruby was around。

 So you'd have to do a little bit of archaeology to actually get these things together。

 I'm doubtful that anyone actually ranm this exact stack。

 It's no reason why it wouldn't couldn't run。 might not be a good idea to run it。 But you know。

 if you had， if you were， you know， on your desert island with a transmittter laptop。

And a Ruby application。😊，You know， what would you do， So， so the。

 the point of much of this and of virtual machine technology is。Sometimes functionality。

 but often just convenience， right， I have machine X。

 and I have an application for machine Y or OS X and OS S Y。 How am I going to bridge the two。

 Do I go buy another copy， Do I recompile it。Do I buy another machine？

Sometimes the answer is you just slip in this layer of software in the middle that bridges between them。

And the presence of the layer of software is usually indicative of the commercial value of that bridge。

 You have a big application base for this kind of machine and a lot of these machines。 and you want。

 you want to match them up。Okay， so managed runtime。

 you probably won't hear this term very much in the rest of this course。

 but I'm using so runtime for a managed language is the definition。

 Well that doesn't really help you much。 So a managed language is one in which the compiler produces code that doesn't have unfetterted hardware access it's not just running directly on the hardware。

 something intermediate between the code that's running and the underlying hardware。

 and it could be for a variety of reasons， the most common one is to constrain what the software does so that you know it can't address arbitrary memory of something like that。

 So it could be a VM， but it doesn't have to be。 so managed code sometimes means something that doesn't look like an instruction set。

 even source code can run in a managed runtime or compressed abstract syntax trees。

 The term really seems to。Originated with dotnet and the common language runtime。

 I couldn't find any mention of it predating that。The funny part is dontnet is of VM。

So they call it a managed runtime， but by this definition， it's not a managed runtime。 it's a VM。

 So again， terminology here is not so helpful。 I'm going to use virtual machine more or less universally throughout this course。

 even though sometimes you know the languages running you distribute source and it's not clear that there's anything that's really a virtual machine because there's no machine instruction set or even pseudo machine instruction set。

um。Well， I said， I've mentioned some of the reasons why you'd use a V M。 The most important。

 in my opinion， is that it decouples the guest from the host。

 You now have a layer of independence between those two。And you can do something in that layer。

 You can either map from two things that are different one to the other。

 You can attempt to improve security by sandboxing the thing that's running above you and constraining its access to the underlying platform。

 you can virtualize the hardware and the virtualization usually means that you take one piece of hardware。

 but you make acts if there are many identical pieces。

 you know you partition up the memory and you give everybody a chunk。

 you partition up access to the processor you give everybody a chunk。

 but they all think they're running on a full system。 and that has its own utility， right。

 You have consolidation where you take I have three computers running three different applications。

 I just want one computer running all three， but I can't just put them all on the same O。

 I want to run the Oss independently。 So that's one reason why you might want to do this。

 You might want to do version management。 You know， I have two Java applications that run on。

Different versions of the JDK。 Well， I have to run two JDKs there， right on the same system。

 there's a good use of virtualization。 Youre a partition， the resource。

 you want to run different flavors of O S simultaneously。 all these are good reasons to use a VM。

Another thing that some V Ms give you is a degree of persistence via snapshottting。

 which isn't available on a hardware machine。 So what I mean here is you can take the stays of the machine。

In the middle of the execution of something and you can take that state and write it to a file and then restart it later。

 And it's as if the machine never left off。 it would just continues to run from the exact state it was in at that moment and that has a lot of utility。

 for example， if you're in a data center and you want to do load balancing。

 you might want to snapshot a virtual machine and move it to another piece of hardware and run it where it will more usefully use the resources。

 So you maybe want to turn the first machine off and save some power。So the persistence。

 something in principle you could implement in hardware， you know。

 to save the state of a machine in a file， But， you know， no one does， right， it's，'s。

 if you want it， you have to get it via VM。You might want to do some level of instrumentation or observation in software that you don't have available to you in hardware because the hardware capabilities aren't there。

It gives you this thing that I mentioned earlier， cost saving， time saving。

 some degree of convenience。 It saves you having to buy something you would have otherwise have to buy。

 In fact， I heard once that the the the the business case for VM where when it came out was that it would save it would save companies from buying so many piecess and they priced it such that half of that money went to them。

Grrant business model。So you basically got an extra instance for half the price of the hardware。

 which， you know， hard to hard to argue with unless you need， you know。

 a full machine and all those resources separately。

And then on some some systems they will actually give you performance， but with less effort。

 so if you write， for example， Java programs and you want them to run quickly。

 you don't have to worry about compiling them an optimizing them in a detailed way for the underlying hardware。

 the VM does that for you。 so I would argue it saves you some effort。

In performance tuning by having it done automatically for you。 Sometimes some do， some don't。

 So let's let's rank these systems on these dimensions and see have this score。 So virtual box。 Yeah。

 absolutely gives you port the ability to run to Linux on Windows or Windows on Mac。

 improve security via sandbox， yes， the VM that you're running isn't， you know。

 it might have access to the underlying file system。

 but you're supposed to be able to manage that right if if you if it breaks through despite that。

 that's a bug。 But in theory， you're supposed to be able to put you run like some ancient buggy in theec version of Windows in a VM and and it won't get out to the rest of the machine。

It allows you to do know some number of these。Things with virtualization of hardware。

 It gives you the ability to persist your virtual machine and move it to other systems。

 There's some amount of instrumentation and observation that you can do on the running virtual machine that you couldn't easily do on the hardware。

 I won't go into detail there。 But I did look in the manual。 There's some good stuff。

 Certainly scores on well on on convenience， but it isn't gonna make your under your guess any faster unless you run on a faster V M with a faster underlying hardware。

 of course。Okay， how about the JVM portability Well you know portability was sort of the reason for its existence right once run anywhere was the original slogan for Java so that's sort of its men reason for existing as well as security。

 sandboxing of applications in applets doesn't really do much for you in terms of virtualizing hardwareca there isn't a scenario in which you tend to run Java on hardware without a VM it doesn't give you persistence。

 although there's no reason why it couldn't and in fact numerous experimental attempts to provide this but they didn't make into the the standard other language of VMs do offer this so it depends on your choice of language and underlying implementation whether you can do that it does give you some capability for instrumenting and observing in a way that you otherwise couldn't for example。

 you couldnt you can run a Java application and debug it。

And observe it without having to compile a special version for it。

It give you some convenience and it does give you performance。 I would argue with a less effort。Okay。

I'll do for now。What's coming next we'll take a short break after the break Patrick will introduce Fi which is the toy language which is the basis of all the exercises After that I will talk about abstract syntax tree interpretation and we'll actually look at some code an interpretation code and then next week we'll go on to more VM internals designs of bycodes and such like later weeks we're going to do a dissection of the JVM spec to see kind of you know the guts and how bad it smells we're going to look at memory management in some detail I have actually two separate sessions scheduled for that so we'll do an initial look at the basic memory management techniques。

 reference counting and simple marking garbage collection and then we'll look at some of the more sophisticated techniques later。

Just in time compilation。I a big section of the course and the variance of that and then once you have a dynamic compiling system。

 what kinds of optimizations you might do with that。

 and we'll end up by looking at what it's like to use a VM construction kit that gives you kind of all of the capabilities of these things sort of with a nice abstraction layer to implement the language。

And then somewhere in here， I'm not exactly sure of the schedule yet。

 we'll slip in material on tracing and what's called meta tracing compilation。

 system V Ms and something about the tooling that's associated with virtual machines for things like debugging and profiling。

And there's one last FAQ。Which is， you know why am I。

 why is the emphasis here on language VM as Well， let's goes back to what I said at the beginning。

 It's because I know a lot more about language VMs than system VMs， but practically speaking。

 it's it's sort of a more， it's a more useful subject。

 I think kind of anyone can invent a language and build a VM for it， hardly anyone。

Outside of this building anyway， gets to invent an ISA that matters。 So。

 so usually there's kind of just a crossproduct of ones that matter that doesn't change very quickly。

 And once that's fully populated， you know， than making a faster one。

 There isn't really much scope for anything interesting to do there。

 Most of the complexity of system Vms， is's just kind of ugly detail。 You know。

 the bitten codings and the strange instructions and the weird semantics and all of that stuff。

 It's not hard。 It's just detail。 And rather than then work through all of that kind of detail。

 which I think were occupied far too much time。 we're just going to focus on the higher principles。

 and you can you can look into these things for yourself。

 underlying underlying techniques are often common。U。You know。

 so the first implementation of an native ISA is usually in silicon and it's hard to do better than that with a VM I actually think it is possible at least in limited circumstances。

 but you know it's kind of more a research topic than a tutorial kind of thing。You know， and I。

 I wrote this thing， which is you can argue with me if you like about it。 But basically。

 sort of language VMs create an opportunity。 you get to put something new in the world that may provide some capability that wasn't there before system V M's usually just like patch over some inconvenience。

 I have an X。 And I really wanted a Y。 And I'm just going have an X to Y adapter。

 It doesn't sort of get people excited， right， It's， it's just kind of solving some irritation。😊。

Co designed VMs。Being the the counter example。 and actually。

 I was involved with the co design VM project。 And that's really funny。

 If you want to talk to me about that， we we can take that offline。U。Yeah。

 and I sort of alluded to this earlier。 but you got to invent a U ISA here recently Rik 5。 and。

 you know， I'm hoping someone will take up the challenge of doing， you know。

 a risk 5 binary translator or a back end for， for one of these interesting VMs and take that on as a project。

 I certainly have a number of project ideas if anyone wants something fun to do outside of the confines of the class。

And that is it for now。 We shall take a break。10 minutes， 10 minutes， 10 minutes。

 so back at quarter two。90 hello。Okay， let's start talkcamp about the lab portion of this course。

So I'm Patrick， that's my email， which is where you'll be sending all the assignments。

I'm a PhD student here， my interests are in PL design， type theory， compiler implementation。

 and my thesis topic is I'm working a new programming language called StanNSza and if you guys are like that sort of thing you can visit the website。

Okay， now a bunch of you guys said that you've already implemented interpreters before。

 How many of you guys have implemented an interpreter for a G C to language。Raise your hands。

Like a garbage collector language。Oh， interesting。 Oh no interesting。That's very interesting。

It's interesting because typically when they teach you they you implement GC languages before you implement interpreters for non GC languages。

Okay， so the goal of the lab portion is。We designed a programming language called FNI and you're just going to implement higher and higher performance implementations of FNI okay。

 Los are there's this website called Piazza， which you guys should get an account and sign up to for this course and all the assignments。

And all the test harnesses will be posted there， and you can ask questions on it and I'll try and answer as often as I can。

And eventually， there will be a weekly discussion section when we start needing it。

 We won't need one for， for the beginning。So。Okay， so that's enough about the logistics。Okay。

 so from this P L survey， every one of you has like some either Python or Pearl or Ruby or Lua or Javascript or scheme or Lsp experience。

 And I pretty much group all those under the same language， okay。😊，And。😀Yeah。And Fi。

 we pretty much designed it to have pretty much the same depth as all these languages。

 So what we restricted mostly was breath。Okay， so is designed to have the same features as all these modern。

 popular scripting languages， it's designed to be very easy to implement。😊。

But quite hard to optimize， just like all these existing same languages。It's imperative。

It's dynamically typed like Python Ruby Li Woodless， Small Do， all that stuff。

The object system is a little bit weird。 It's like jascript yourself。

 It's what's called a prototype object system where you don't declare a class first。

 You just directly create objects as you need them。 Okay， so self was pretty much。

This idea carried to the extreme。Like I said， it's a garbage collected language。

And we restricted in scope by limiting the numbers of types of data types you create。

 So you have objects。You have a raise。And you have integers。And that's it。Okay， there's no strings。

 There's no characters。 There's no true。 There's no false。 This， the these are the only things。Okay。

So。I have a video on how to pronounce Fii properly。 Does anyone get this reference。

 Does anyone know why it's called Fii。就是。Okay。や不是六。Okay。Oh really， so no one knows this。 Okay。

 I must be dating myself。 This from This is from boyeses world。 It's what I grew up with。😊，S。Okay。

Fenney was a science teacher in the school， in the school， yeah。Alright。

 so the lab structure for the first assignment， which we'll be due a week from now。

 is just going to be some exercises just getting familiar with Fi， Okay。

 so you'll be writing Towers of Hanoi， a stack library。And a better towers of Hanoi implementation。

 okay？After that， we're going to write the first limitation in Afini as an abstract synttry interpreter。

 okay？After that， we're going to implement a Bcode interpreter。

And then you're going to implement a Bco compiler。And all of this is going to assume that you just don't run。

Programs that run long enough to blow out from memory。 Okay， because after that。

 then we're going to implement the garbage collector。う。Yeahep。

And then so that's our the garbage collector is gonna to be pretty hard。 That will take a while。

 And then the dynamic compiler is probably the one that'll take the longest。

 And that's when you actually。Read in the bycode and generate assembly instructions on the fly to execute。

 Okay， And then after that， we put in more and more optimizations。

So this is kind of following the Sa at School of Pedagogy。

Step 8 is we're going to use a framework called truffle and Grl， which is developed by Oracle labs。

 specifically for developing high performance。VMs very quickly。Okay。

 so theres some programs that's included with the test package。There's a binary search。

There's Fibonacci。There's a library for doing complex numbers。Which is interesting。

 which is it demonstrates a particular feature of Fi。

And then there's an example of using the prototype object system and how you do inheritance with it。

There's a live for lists， a library for vectors。 And then the longest running one is a program for selling Sudoku puzzles。

 Okay， so that one will probably be the one that you measure the performance of your implementation on。

Okay， so let's just look at some code。So like I said。

 I developed a language called stanza and I didn't want to reimment a Leer。

 so I just borrowed stanza's Leer。So this is gonna look a lot like stanza。

 So there are some caveats to be aware of。 Okay， so this is what the code looks like。

Is dynamically type。 So you see those arguments。 They don't have types after them， okay。There's no。

 there's no curly braces。 Okay， so it's indentation structured。

 So every time you see a colon at the end of a line， specifically a colon at the end of a line。

The next indentor block forms a scope。Okay， like Python。All right。Comas are just white space。

So you can type space， you can type comma they're exactly the same thing。And。

Tokens are white space delineated， so this is in space minus space in one。If you type in minus in1。

That is a identifier in dash n1， and there's no variable called in dash N1， okay。

So these are just some cave you have to be aware of because I'm reusing Stanzas Lexir。Okay。

 so a quick run through through the basic semantics。

Nll and integers are data types you can create just as literals， so if you type null。

 you get the null object， if you type 42， you get an integer object that represents。42。嗯。

Print F is very important， and I'll just mention that as you do your assignments。

 I strongly recommend that this be the first thing that you implement because otherwise there's no way for you to see what your program is doing。

Okay， so this is the only way to get stuff out of Fi。So print F， you give it a string。

 This is the format string。 So this will print on the hello world。It's a format string。

 And the convention is you put little tilties to splice in the arguments afterwards。 Okay。

 so this will print 2 plus 3 equals 5。Okay。Arithmetic。

 So there's a few standard operators plus minus multiplied divide and modulo。

And you write them like this。Now， all of these are syntactic sugar for a method call。 Okay。

 so these are completely equivalent to this。Okay， you can type one or the other。

And this will come into play when you implement the libraries。Comparison operations。Less than。

 less than equal， greater than greater equal equal equal。Are syntactic sugar for these method calls。

 okay？One thing to point out is that。Is 10 less than 23。This will return。0， the value 0。Okay。

And is 10 greater than 23。This will return the object， no。Okay。So， false is no。True is zero。嗯。So。

For people familiar with like Python or perarl。The null kind of makes sense， right。

 That's the null object， and it's often used to represent false。呃。What do people。

 what do your languages typically do for returning true， Does anyone know。Raise a hand， someone。嗯。

They just do the odds。They just do， yeah。 So like dynamically time languages， they。

 they usually have a distinguished object called true or something that they returned instead。Right。

Yeah， true is a singleton。 Okay， but we're limiting the number of data types。

 So we didn't want to introduce another data tech。 So we return 0 for true， okay。All right。

 so these are the comparison operations。there all numbers to interpret is true。呃。

Let me get back to that。Let me get back to that， okay。Okay， how do you declare a variable？

You say var x equals some initial value 23。So at this point， you can print it out。

 print F x is equal to tilde x。 This will print out x equals 23。So this is a variable definition。

 this is a variable assignment。 These are two separate concepts in Phi。

 so this is assigning 10 to an existing variable called the X。Okay。

 and now if you print out the value of x again， it will say x is equal to 10。

This is all standard stuff。If expressions。Ask per James's question。This is if upon some predicate。

 okay， if the predicate is no。It evaluates the alternate。If the predicate is not null。

 then it evaluates。The consequent。Okay， so this is like typical Python semantics。

Okay so so your question， are all numbers regarded as true， Well， there's no concept they're true。

 there's no and there's not no， that's it。If you emit the El branch。

It's totally equivalent to just typing noll there。Okay。Similarly， here is a while expression。

 so you can declare a variable I is equal to 0， while I is less than 10。

 So same rule applies for while。 So while goes， it takes a predicate， evaluates it。 If it is null。

 then it does not evaluate the body， It's finished。 If it is true， Sorry， if it is not null。

 then evaluates the body and then does the test again。Okay， standard。Python， semantics， basically。

Whileils and ifs have their own scope。 So if you declare a variable， variable J is equal to I plus 1。

Within the scope of the while。This ja is no longer visible outside of the while。O。Yeah。No。

 this one's fine。So， okay， so let's walk through this one。 So this one declares I equals 0。

 Test if I is less than 10 and loops if it does。 So then prints out I and then creates a variable called J within the while。

 So J is equal to I plus 1。And then it assign I 2 J。So， you can。

This reference of J is within the same scope。 so you can see it， right。It's making a copy of J。Sorry。

 what do you mean by that。The value that's being transferred or is it？It is。I don't know the term。

To to make呃。I can tell you the answer is it's a pointer。But。什么。Okay。Once again。

 all of these constructs are syntactic sugar for methods。

 so this notation is syntactic sugar for calling the set method。

With the first argument is the index 0 and the second argument is1。Okay。

 so you're getting to see that almost everything is a methodical in this language。

 And that's what makes the implementation a bit easier for you guys。Okay， finally。

 we get into functions。So here you can define a function called double。

 and it takes a single argument called X。And you can define a local variable called Y。

 Y is equal to x plus x and can print it out the argument and you can print out y。

What the function returns is it automatically returns the last。The result of the last expression。

Okay。So there's no return statement。don question， there's no need for space because。This one， sorry。

 what。Do call it。Oh yeah， sorry， this space is necessary， yes。Yeah。Yeah。

 so this is explain the assignment essentially。If you follow an identifier with an open anything。

This is entirely different than if you don't。Okay， so there's just two different things。

 So you have to be aware is， yeah。Okay， so you just have to be aware of that。Okay。Allright。

 so functions have scope。 You cannot see why once you're outside of the function。 Okay。

 so var 20 is equal to double of 10， and I could print out 20 is equal to。20。Okay。

Some other things to be wary of， you cannot define functions within functions。Okay。

 so that makes things a bit easier。So in this case， the last thing is the。

So is there no way to return？There is no way to return early。Yeahep。So。

 and there will be an assignment question about why this is。は今は。mYeah。That's know。Okay， so。

So like I said， there's this special object called null， which is the empty T object。

 The empty T object is。😊，Nothing， essentially， you can't call any functions on it。

And it doesn't have any slots， so both of these are errors。So that's all null is。

Here we can create objects with slots。Okay。An object inductively， is either the null object。

Or it's an object or it's a set of bindings attached to some other object。Okay。

 it's like a link list。So this says attach to this object， which is the empty object。These bindings。

 x is 10， y is 20。Okay， so this creates P。 P is the object。So to access the slot。

 you can type P do x。And Peter why？Okay。To assign to the slot， you can go P dot x equals 30。

 P dot y equals 40， and you can print that out。Okay， so these are thoughts。Does that make sense。No。

A syntactic sugar。Typ。Noll is the parent object， so if you don't write it。

 it just assume it's noll by the false。Okay， so this is an example of using objects without the inheritance system。

 So this is like a C struct， for example。Okay。Okay， and then the big meat of it is methods， okay。

So there are two types of slots。 There's variable slots and method slots。 Okay。

 so this defines an object with two variable slots。

 X and Y that you can just assign to and retrieve directly。And a method slot called the print。Okay。

 so the print method takes no argument。And the special thing about a method as compared to a function is that within a method。

 you have access to a distinguished variable called this。And this refers to。

The receiver object in the methodical。 Okay， so let me explain what that means。

So this creates the object called P。And then the syntax for method called P dot print。Okay。

 so what this does is it looks up in the set of bindings in the object for a S call print。

 it finds it。It is a method slot， so you can call it Okay。

 So you're calling the method print on the receiver object P。Okay。So within the body of the method。

 this refers to P。Okay。So if you do this dot x， it refers to the slot accessed in P， which is 10。

 Does that make sense。Yep。Yeah， yeah， you can refer to global variables， global functions。Yeah。Okay。

Related to that。The method scope is a little bit different than。

Is a little bit different than other language so you have to pay attention for this part。So。

 the method scope is。Its own scope on top of the global scope。 Okay。

 so you can access the global variables， global functions， but you cannot access your lexical scope。

 So you cannot access。PX and PY。Okay。So， this scope cannot see。PX and PY。

And the reason we make this limitation is because we want you guys to implement objects。

 not closures。Which is good。Which is just， it's pretty much the same thing， but it's just more code。

Okay， so。Here is a function called pair。 You give it initial X value， an initial y value。

 and it creates an object with two slots， X and Y。 And they're initialized to the initial values you gave it。

 Okay， and it supports a single method called print。You can call print on it。 Okay， so to use it。

 you can go pair 20 and 30。 So this creates a coordinate，20 and 30。And then you can call print on it。

 dot print。Okay。Okay， first of all， is anyone confused at all about this farcause now we're gonna go into inheritance。

人年度。そいうには？Good question， okay。Yeah， right so。This， this call， this object， this is。

 this is a key word。 It creates the new object。 It doesn't have a name yet。 Okay。

 the object doesn't have a name yet。But I can give this object to a variable。

 So P is a regular variable and now holds an object。Does that make sense。So。

 whole is this whole thing is one expression， yeah， okay。So here， this is a function。

Has only a single expression within it。 And like I said。

 the last thing that gets returned from the function is the result of the last statement， right。

 So this returns an anonymous object， essentially。There should be。你说。Yeah。So this one not run。

I there a or no， no， there is a specification， Yeah，ax。😊。

And I guess James wrote a synyntax highlight for Stannza， which would kind of work on this。

 I guess yeah。Okay。So now we're going to go into inheritance。So like I said。

 an object is basically a set of bindings attached to another object。

 it's a big linked list of bindings， okay。So this function called pair 2。Also， accepts。

Two initial values。And you're going to have to stay with me here。

 The first thing it does is it calls the previous pair。Right。So this call。Already creates an object。

Okay。And now we're going to create an object out of that。So pair is the parent object。

 now I'm going to create a new object out of it。I'm going to attach a new binding called print twice。

Okay， and what it does is it simply calls this dot print。This thought print。Okay。So if I call pair2。

With one and three。Thiss all great。This link lists the bindings。And when I call print twice on it。

What it's going to do is it's going to go into the print twice method。And then call。

 try to call the print method on the receiver object， which is P。Right。Now。

 does it have a print method？ Well， it's this big length list of bindings。

And you can find the print method in the parent object。 Okay， does that make sense。Okay， great。So。

 you know， you can also call print directly yourself， which also search of the linkless of binding。

Okay。So this is one use case for inheritance that you see often。

Another use case for inheritance is something called late binding。So here's how that works。

So there's no new concepts here。 This is just a method of。Particular way of using the system。Okay。

 so we're gonna create a function called maxer， which is something that can take the max of things。

 Okay， so it creates a new object and it has two methods。Max and。LT， okay。Alright。

 so if you call max on two arguments， X and Y。What it does is it calls。This dot。

LT less than on the two arguments。And if it is， if x is less than y， then you turn y。

 otherwise you turn x。Okay， what is the implementation of L T。It just calls less than。Okay。

So if you create a maxer object， call it M。This should be N R， actually， Rar M。Okay。

 so if you call M do max 30 and 40。This will return 40。

It's going to go in here and it's going to call LT。On the two objects， which is。

 and the default implementation is just the integer less than operation。Okay， so this will return 40。

Now。Here's the late binding part of it， if we want to。

Have a special type object that can take the max of pairs。 right， So here's a pair maxer。Okay。

So maps there is the parent object。It's something that supports Mac and LT。

But now we can attach a new binding for LT。Okay。So the new binary fty also takes two arguments。

 A and B。And then it says if a dot x is less than B dot x。B。😔，The result is A doy is less than B doy。

So this basically says if a is closer to the origin than B。Their return true。Return， return0。

 otherwise false， okay。Alright， so here we create our pairaxer。And now we can call M max on pairs。

 So here's a pair，10 and 30 and paired 2 and 5。 And this should return。10 and 30。

So does' a function just return not if it doesn't get a return value， like in this case here。

 there's something anywhere else。ジト Texas。いただす。Yeah， so， so if you omit the else branch。

 it's always equivalent to Elsenol。What the method of failure say that you gave it something that wasn't fair？

Well， okay， so what happens if you give it something and that's not a pair， so。Great question。

 If you pass it a 10， dynamically type language， it goes into。M dotm。Which is here， right。

 so x is 10。And then this we'll call L this do LT 10 and a pair。K。Which we'll then go into here。

 so this is 10。And then it will go to here， retrieve the slot X from 10。And at this point。

 the language will crash and tell you， there is no slot called x in the value 10。A you stack trees？

Exception。2。So。As I define in the assignment， I said， when stuff like this happens。

 the language is considered stuck。And you're supposed to handle it gracefully。 Okay。

 which means just print out an error message。And do that okay。Okay。So， that's。Basically。

 all the semantics。Basically， it's Python， but the scope for methods is a bit weird。Okay， yep。Yeah。

要对。I'm sorry， second again。Can you change the method？这个第二。Yeah， so this is an example of doing that。

 right。You're like overriding it。Oh， you mean like directly replace， no， can you can't do that。 Yeah。

 you can't do that。Yeah， that opens up a whole other kind of worms。Yeah。Okay。

 so those are the sematics that you'll be trying to implement in the second assignment。

 So the first assignment。You'll be implementing three things。 Has anyone ever played Ts of Hanoi。

 Does anyone know what that is。Okay， so in the first exercise。

 you have to print out instructions for solving a tower of size 6。

And what I want you to print out is I want you to print out。Move a plate from stack1 to stack 3。

Move a play from stack 3 to stack 2 and on and on until the puzzle solved。

The second assignment is I want you to implement a stack library。So。

There will be a function called Cate stack。Okay， and you can create a stack。

And then you can call dot push dot pop dot peak on the stack。Okay。And then in the third exercise。

 you will use that stack library to improve your towers of Hanoi implementation。

 And then what I mean by that is。Imagine that the plates in your tower are labeled with numbers。

 Okay， so 1 to 6， the lightest one being at the。Labeled 1 and the heaviest one being labeled 6。 Okay。

 I want you to improve your implementation by printing move plate 1 from stack 2 to stack 3。

Move plate 2 from stack 1 to stack 2。Okay。So that will require your implementation of the stack library to do that。

And that's that， that's the first assignment， so this will be due in a week。

And you can just email it to me after you're done。Alright。Thank定。So you should view the lack。

Of features。As making your life easy。I've been taking notes on people asking for other features and you'll be given those as assignments。

You be careful what you ask for。All right。か。Okay。So we're going to cover interpretation and I hope。

Enough of interpretation。 And the time remains that you can do。The second exercise。

 which will be to build an interpreter for that language。What is an interpreter？Boy。

 is this slippery？This is pretty hard to get。A really good definition for that really， again， it's。

 it's one of these things which you know it when you see it。

 but trying to get a definition that sorts the。You know， the fish from the fowl is not easy。

 So a first cut is like， well， an interpreter for source language L is a mechanism for the direct execution of all programs from L。

 depending on what you mean by direct execution， of course， that punting。 So that。

Allows interpreters to be hardware as well as software， which is good because to me， Chi。

 a microprocessor is an interpreter of the instruction set of that。Microprocessors。

 so I really do want that to be included in the definition。

 so a risk five chips and the interpreter risk five instructions。But it doesn't really。

 depending on how you mean， what you mean by direct， doesn't really exclude dynamic compilation。

 And I wantna exclude dynamic compilation。From interpretation。 So a second attempt。Now。

 unfortunately， I have to exclude hardware to write this definition。

 a software interpreter for a language L is a self contained， complete programme for the execution。

Of all of programs in L。 So it doesn't generate any。Additional instructions， right。

 All the instructions are there in the original binary。And that kind of works for me as a definition。

 except， as I say。It doesn't include hard work，ca it's， it's a definition of a software interpreter。

 But I have another take on it。Which is a sort of a more operational take， which is an interpreter。

 is a mechanism for the direct execution of programme。

 which executes each element of the source program without reference to the other elements。So。

The execution of some fragment of your program is unaffected by the structure of the rest of your program。

 It does not take into account stuff near it。Stuff around it just looks at that thing。

 And that actually， I find to be a more useful definition。In some ways。

 and that's what hardware does， too。 So some consequences of that are。

Performance is typically uniform。 That's good。 Uniform performance is good。 And it's predictable。

 That's also good。 Preictable performance is good because every execution of the same node is the same and has the same performance。

 until mod or whatevers going on in the hardware underneath right。

 There's caching and branch prediction and all of that stuff。

 But you're doing basically the same thing。 And it tends to be very predictable。

 The bad part is it's slow。 It's predictable but it' predictably slow because there's no optimization scope here。

 right， when I'm executing some tiny fragment of my program， I can't look。😊。

A line before or a line ahead and say， I'm going to do the exact same thing down there。

 Maybe I should remember this result and pass it down to there because every element is executed independently of every other element。

Contrast that with compilation。So firstly， compilers don't execute anything， right。

 They just take your program and they transform it into some other form， right。

 They don't execute your program。 Theyre translate it。 it's not an execution mechanism at all。

 It's translating from some form into some other form， which is meant to be equivalent。

 hopefully faster。So the truth of it is that usually these things go together。

 It's very rare that an interpreter directly interprets your source。

 that it's reading character by character， what you're doing。You know， and aggregating those things。

 And you know， the only cases where I can think of you doing that is when you have trivial languages。

 a command language where there's no parameters， there's no control structures， right， If all。

 all you can type in your interpreter is quit and run and do。 But that， you know。

 that can be done just by executing directly， But usually for a general purpose programming language。

 you need a bit more structure and what usually happens is that you some compiler is invoked to transform。

The source into some other form that's more efficient to interpret。

 So theres some amount of compilation usually going on， even if we only call it pasing。

And that intermediate representation that you interpret then remove stuff like lexical noise。

 right where the spaces are in your program， if they don't matter comments formatting that doesn't matter。

 I mean， I have to now give caveats because this is a format sensitive language。

 which I'm not used to。 but it removes the stuff that isn't relevant to the execution because well。

 for one thing， we don't want to penalize commentary and make the programme run slower because there are comments in it。

 The first programming I did was on a basic interpreter that did that。

 The comments were held in memory and had to be skipped over by the interpreter。

 So the more comments you put in， the slower your program ran。Not a good。Place to be。

And you don't want the formatting to in increase the execution time or to have descriptive variable names cost you。

 you know， performance。 So you w to kind of normalise away all that stuff and then interpret。

So the le seas typically are condensed into some smaller representation identifiers and constants and things are abstracted。

 and then the operations are usually combined operators are combined and abstracted。

 and often some kind of reordering takes place to make the say the operators in an expression available in the order that you want to run them rather than in the order that they were written so that you don't have to figure that order out every time you interpret the expression。

 So we'll be going through some examples of this。嗯。So。

All execution ultimately bottoms out at hardware interpretation。 I。

 I can't think of a single counter example to that。 If you can think of one。Tell me。

 and unless you like writing your interpreters in machine code， I binary for the machine。

 You will need to compile something to interpret what you're typing and running it unless you have one of these。

 Anyone know what one of these is。There's a front panel for a PDP 11。When I learned。

System programming at Manchester University。 The first thing you did was you walked up to one of these things and you wrote an interpreter for Otal。

And you flipped these switches for the binary， and you clicked the button and it loaded it into a me location。

 and then it loaded the next one into the meial location。

 And you did that until you had something that could read Opal characters from a tape reader or some other input device and put them in memory。

 And then you wrote in Opal an asmbler。😊，And you bootstrapped you way up until you had a machine。

We don't have these anymore。 So it's kind of hard to， to。

 to write and install software without some software being in the loop， right。 here you could do it。

 There's no software at all being involved。 You just。All electrical， right。

 It's nothing programmable at that level。 So you're gonna have some kind level of software that's doing something roughly akin to compilation。

 Translating something into something else， even if it's just translating  opticalal into inter binary。

The thing that an interpreter gives you is an illusion。Or a reality。 actually， it's a reality。

 The reality is， you type something or you load something， and it runs right there and then。

And it's a very， very， very powerful phenomenon to directly have staff executed。 And， in fact。

 I would argue it's probably the best way to teach anybody to program is to interact with something like that。

 But the catch is， as I mentioned earlier， that it's slow interpretation is slow。

 And so what you really want in the implementation of an advanced VM is to preserve that illusion to make it feel like you're interacting with an interpreter。

 that there' this directness。😊，Of interaction with an underlying machine。

 But the performance is really good， as if you had precompiled it and optimized it。

So you get that experience of interacting at the speed of a machine。

 but you don't have these long pauses while you compile and you go get a cr of coffee and break the train of four just to get a little bit more performance。

 and this can be very challenging。 So compilers commonly， you know。

 if you're doing on flyly compilation， compilers to get performance will do reordering typically。

 and now you have to debug this reordered code as if it were not reordered。

So there are some interesting technical challenges and we'll get into some of these as the course progresses。

 So the trick here is to get this is to define or discover。

 depending on how much malleability there is in the environment if you' are defining your system you can say what's observable or what isn't。

 but usually you're given some level of observability and you have to explore what's observable and what's not and cheat behind the scenes。

 you're doing tricks and changing representations and generating code。

 but all the while trying to give the illusion that there are these instructions being executed one at a time in the order that they were written And so when someone looks。

 it looks like that， but when they're not looking of the stuff is going on that has the equivalent effect but that's much faster and it's very similar I know some of you hear a hardware involved in hardware it's very similar to some of the things that people do in microarchitecture。

 reordering instructions and memory effect。Pserving some external illusion of sequencing that the spec insists on。

And the trick there as well is， you know， as long as no one looks， you can do what you like。

As long as you get the right answer。So we're going to start with the very simplest highest level interpretation technique which is called abstract syntax tree interpretation so AST for short AST isn an abstract syntax tree and that's the tree that's typically produced by the PAser of a highlel language so the very front end of a compiler hopefully you know as a PAser。

 the PAser generates a tree， the tree is typically an AST because all that irrelevant stuff has been thrown away。

 there are no comments， irrelevant formatting is gone things have been condensed into you know atomic entities so for example as fragment of C which is a little loop might be translated into a structure like this where are these little atoms you know some kind of primitive representation of the identifiers and a tree structure that indicates how those various statements and expressions are connected and there isn't related to the original source order it's kind of it captures the more of the semantics of the program。

In a， in， in a， in a high level way and throws away the irrelevant stuff。 So， for example。

 if we had a loop here and the loop bound was， say 8， we could write 8 or we could write ocal 10。

 which is the same for 8。 and an8 would be in memory， right。

 It wouldn't care what you wrote originally， it would map to some canonical representation。

And this is a convenient form for interpretation， because we've lost all of the irrelevant stuff。

 but we have a structure that's easy to navigate and， and to， to attach actions to。

So I'm going walk you through a very simple interpreter with a few little variants for the rest of the half hour。

 and that hopefully will give you enough to get you started on the second exercise。

 which is due two weeks from today， which is the AS T interpreter for Fi if you get done with your program exercises in Fi don't hold back dive into this one because the more you do the more next week's material will resonate with your experiences So it's entirely up to you how you you've structure you time。

 but doing stuff early is in this course is going to help you a lot because you'll understand the points I'm making you know it'd be great if I could have given you an exercise to work on on the summer before the first lecture and then we'd be more in sync but doesn't work like that。

Okay， so we have a simple expression language we want to interpret。 The languagenish elements are。

Single letter variables。Lower case in this example， the variables hold an integer。

 There are integer constants， and there are expressions involving simple arithmetic and assignment。

 So we have， these are examples of the， so I can write 3 plus 4。 and it should give me a 7。

 I can write Bs 2 a plus 1。 if I'd previously assign to a should give me an answer。

 X times x plus x plus5。 You know， you get the idea There's nothing It doesn't need a formal definition。

 And here's the tree that a paer might generate for one of these simple expressions and assignments。

 and hopefully that's。Hope there's no surprise there。So an interpreter for that。Here it is。

 one slide。Now， I don't。Recommend。Writing code like this。

II have scrunched this down so it fits on one slide using every trick I could pull in C to try and make it concise without being totally cryptic。

But the idea is to try and give you just enough to hang on to to understand this。 And will， you know。

 in a font that's big enough to still be able to read in the back。 So this is a。

 this is an interpreter in Siig。 we have only one kind of declaration that that's only there notationally really。

 which is we're going manipulating these trees， and I'm going to call。

The thing in one of these nodes。An expression， an exp。 And it's implemented using a Cstruct。

 So I I've type depthstruct X。To ex only because we need a recursive definition of the type。

 So we need a self referential thing。Later on， an ap is a lot shorter thanstructax。

 So what is astruct a。It contains two things， a tag which tells us what kind of a tree node we're dealing with。

 And I've got nodes for all of the different。Kinds of operators or elements， computational element。

 So I have add means an ad operation sub is a sub operation， mole and dev。 obviously， the functions。

 constant means I have a a a literal constant v means。

 I have a variable name and an assignment is an assignment， a variable and an expression。 And then。

The second part is a union。 Everyone， Anyone not know what a C union is。

So all these variants can exist within the structure， but only one of them at a time。

 They all overlay each other in some way。 And the idea is that this distinguishes which variant we're looking at。

So if the tag is a comm。The union field is a v， which is the value of the integer。 If the tag is a v。

 the union field is a single character， which is the name of the variable。

 If the tag is an operation， one of the arithmetic operators。

 then we have two another structure as the field and sub elements of those structures are pointers to the sub expressionpressions on the like left and right of that operator。

So this is where we're using pointers and a recursive types。 So an X has as a field。

 sub a subfield of a subfield or pointer to an X。And then the assignment is simple enough we just have a variable。

 and I'm an point to an expression。Any questions at that point， because I don't want to lose anymore。

Okay， so we wrote only 26 lower casts。Variable。 So I have a simple array of 26 ins。

 And then here's my evaluation function for an expression。 How I evaluate it。

 So given a pointer to an expression， I look at the how it's tagged。😊，If it's tagged as a constant。

 I return the value of the constant。 If it's tagged as a variable。

 I look up in the array of variables。The index， which is the， the name of the variable。 Now， I've。

 I've done a little cheat here to make the interpreter faster。

 which is instead of using the name as it was typed， I've best it。

 I've subtracted off the air to best them 0 to 25 so I can directly index the array without an extra piece of arithmetic。

It's a common sort of thing that people do in interpreters。

 you try and move computation from the interpretation to the passinging because you figure your path once。

 but you might interpret a whole bunch of times。So this this has to be done at least once for every variable lookup。

 But if we do it once in the PAsza， we never have to do it again in the interpreter。

 So that seems like a pretty good tradeoff。Then for the operators。

 they all look more or less like this。 So I've only listed the ad。

 The ad evaluates the left hand side， evaluates the right side。

 adds and returns the result similarly for subtraction multiplication division。

 I haven't put them in。And then the assignment evaluates the right hand side。

And stores it in the variable referenced in the assignment statement again。

 using the same offset trick。And that's all there is to it。

It's a little bit clunky because of all these weird subfield things that you have to do in sea to。

 to build a structure。 But it's very， very concise。

 It's very easy to reason about and convince yourself that it's doing the right thing。

Very easy to read， to write or and read if it's not written quite as densely as this。Any questions。

Okay。So I'm going to go a little bit further with this and add the notion of a statement so I can sequence things together。

So let's assume we have some kind of way of sequencing statements like a semicolon that lets us write a whole bunch of things and execute them together。

 So now I'm adding a type of statements。 And the thing that distinguishes a statement from an expression in this language is that it doesn't return a result or of the result is ignored。

 So in this case， I have only one kind of statement to begin with will add more in in in later slides。

And I have simply account of how many stamins are in this sequence and。

 an array that points to each of the substments。And that's indexed by， by an integer from 0 to n-1。

And then the evaluation of a sequence statement is， well， the switch is kind of in this case is。

 is simple because there's only one kind of thing， but I put it here because there's a framework for the other things Ill add。

Once we've determined that this is a sequence， I just have a loop that iterates through that array and evaluates all of the substatements in turn。

 and because the're statements and we don't care about the result， I'm using an Eval S。

To do statements which returns void compared to the eval for expressions， which return an in。And。

 and that's all there is to that。Any。Everyone following along fine so far， good。Okay。

 so that was kind of C。U。What you'll find is， firstly， it's。

 it's sort of a weird style of programmingca， because the you have this。

 this switch dispatch thing and these weird structures and unions， which don't feel very clean。

It's a really good fit for an object oriented language to build an A S T interpreter。

And the way you do that is that each kind of node。Becomes a class in your object oriented language or a prototype of its prototype based。

 You can use inheritance for better factoring and commoning out stuff that's common to the evaluations of different things。

 And then you use method dispatch for evaluation。 And here's the same kind of thing。In Java。

 I've relied some detail here。 and， the font is already getting a little bit small， unfortunately。

 but， but it， it， it is the same thing。 Basically， I have a class。Common to all nodes of A S T nodes。

 And then an abstract subclass of that for expression。

 So X node extends the A S T node and adds on the eval method that returns an int。

And then a constant node extends expression node and defines Eval to just return the value of that it stores。

An ab node extends expression node to have two expression fields and evaluates the left and right。

 and returns them。A variable， in this case， because we have objects。

 we can store the value directly in the object that represents the variable and just share those objects amongst all the expressions that contain turn them。

 So we don't need a separate array off to the side。嗯。是丹。Has a seter and an evaluator。

 The setter is for the assignment。 The assignment node evaluatevals the right hand side。

 sets the variable based on the right hand side。 And in this case， I。

 I return the right hand side in this。 And I've just delightedlided all the constructorsca they're kind of trivial and。

They would just clutter the slide up。But that's kind of the object equivalent of this。

 And this is much， much cleaner， a little bit more of a both， but it's a much nicer structure。

 And one of the nice things about this is that you can extend it with new node types without interfering with the the code of the existing node types。

 whereas the C version。 you you're inserting things into the middle of switches。

 which always there's a little。😊，A little less comfortable。Okay。

 I haven't shown you any control flow yet。 So I'll give you one more thing。

 And then that should be it for today。 Hopefully， you can go away and。

Do some implementation and we'll go back to we'll come back to more of this。

 Like I say if you don't get to any of this by next week。

 you'll see in the next lecture more detail on this interpreter before you get to implement it。

 But if you get to at least to think about how you're gonna implement it。

 the next set of lectures will make more sense。 So control flow can be easy and it can be difficult。

 So let's really the easy case。 if the semantics of the control flow are local to the tree that you're operating in。

 And in particular， they're equivalent to a control flow structure in your implementation language。

 life is beautiful and simple。 So let's consider implementing a do while expression that we've added to our expression language。

 Well， we have a do while in C。 So life is is good and it's local control。

 So I add a tag into the statement union that says， okay。

 our do while has a do part That's a statement and an expression partners an expression。

And then I extend the interpreter route loop to implement the do while of the higher language using the do while of the implementation language。

 so just simply do e the statement until the evaluation of of the expression yields false and this is nice and easy because the faults line up and the statements line up and life is straightforward。

 you're not going to have it so easy。You， there are some Cha more challenging things。

 And you'll get to think about the next， so。The first lab assignment， as Patrick mentioned。

 is to get familiar with Fie， the second one， this is not the assignment。

 the assignment is a multi-page document but to summarize is to write an interpreter for Fie given the framework that Patrick has put in place once you've written the interpreter。

 you have to take some measurements from the performance of the interpreter which we'll discuss next week and think about some extensions and design decisions in there and we'll look at some of that stuff next week。

 and I think I'm going to leave at least this section for now。And break off。Here。嗯。

And we'll call it a day， I think。Any。Questions， comments。Concerns。嗯。

I should mention this for the assignments。Find the partner。いや感丈ですか。Covi done。むら？

To talk about the fiza stuff。都。Yeah， I mentioned it briefly。

 so all of the assignments are on a website called Piazza。好转。さで。Okay， thank you。有Okay。

I'm actually just audit in going for moment。Hey yeah slide you so then you talked about a V versus a from I understand the V had an operating system in it and the in the directly So the question is。

 does it provide the API of an operating system or does it provide the API of a piece of hardware I there a difference Yes。

 yes， I was thinking if you have an O then it makes your virtual machine because OS interact with the hardware Okay。

 let's look at a picture just to get。😊，Any one of these should do。 Okay。

 so if you look at the left hand side of this。When you write an application for a particular machine。

 the application is not only compiled for that hardware。

 but it also knows about the operating system interface。

 a system calls it can make right So if your VM emulates both of those。

 the hardware and the OS interface， then it's a process VM。 and it runs an application。

 if it emulates this layer， which is that only the hardware。

 then it's a system VM and you're expecting to run an operating system， not just an application。

 that's the distinction。 so the combination of this plus this is called the ABI。

 and this is the system interface or the hardware interface or the IA or I guess that's I guess if you have a system because the system。

Yeah it's more difficult because you have to well unless you have a system like。This one。

 see in the IBM 370s， this layer is designed to be such that you can write a thin piece of software that assign resources。

 but then presents the exact same interface to these independent Oss。

 and for a system like this where the instruction set has been designed to be virtualized in this way。

 This is a very small piece of software。 a hypervisor can be 5000 lines of code， right。

 It's not a huge opera because there's no device drivers in here。 there's no scheduling。 Yeah， yeah。

 yeah， and there're just being passed straight through to the hardware。

 The virtual machine monitor is basically， all it's doing is saying this OS gets that device this other OS gets the other device but they can't mix them up Yeah。

 partitions， the resources amongst them。 So for example， in a mainframe， it might have said。

 okay this job is doing。It's reading from a tape drive and it's printing on the printer。

 That O is gonna get the tape drive。 It's gonna get the printer。

 This one doesn't get the tape drive in the printer。

 It gets the terminals and it manages the terminals。 Yeah， yeah。

 yeah if you want to do that yeah Yeah Yeah， no that's fine， that's fine。

 If you look at something like virtual box。 When you start virtual box up or VM or on one of there's a little bar in the preferences or the settings that says which devices this O is going have access to you can say。

 okay， I have a keyboard。 Does the keyboard get past to the underlying O。

 the wholester S or does it get past to the virtual O。 You are doing the partitioning。

 you're playing the role of the virtual machine monitor in partitioning， the system up。

 And then the VM implementation take your decision and implements it and says， okay。

 that one has the。But that one't virtual， so what happened was when Java came before Java。

 most programs were written for a specific instruction set and operating system and you had to do a poet to run it on a different one So recompile it and changed。

