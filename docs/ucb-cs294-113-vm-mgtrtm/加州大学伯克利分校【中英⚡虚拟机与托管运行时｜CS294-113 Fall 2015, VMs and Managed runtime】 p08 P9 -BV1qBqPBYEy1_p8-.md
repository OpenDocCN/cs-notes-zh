# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p08 P9 -BV1qBqPBYEy1_p8-

And our third guest speaker， Cliff Cl， Young Cliff， since he joined son in 9。7even。

Okay somebody might be too young for this reference but how many of you。

The TV show will better get the movie match。Anyone remember the premise of the movie？

So at the beginning of the movie， some high ranking general in a field station in Korea get sick and the local doctors can't cure him。

And so they send for this crack surgical team who are flown in from， I think。

 Japan to to fix some problem。 And then they get track to that well。When I first met Cliff。

 he and his two other crack compiler guys had just been flown in from rice。

 Yeah because we needed a fast compiler and it wasn't clear that there was anyone who could do that so these guys came in and they spent two years I think。

Building what was an amazing compiler at the time， it still is an amazing compiler。

 I think that has longevity in its performance。That's definitely one of the sharpest guys I've ever met。

And he's written lots of good stuff， he knows an immense amount of stuff。

They'll give some of his distilled experience today and you've hopefully read some of his papers and have good questions for him so without further their a thanks。

So these are some facts about me real quick most。I this one when I went into a hotspot。

 it was widely considered that you couldn't Jit code。

 it were Jit wasn't around then making code at one time was just like it's going to be too slow and too low performances was never worked especially doing a heavyweight compr is when I headed straightforward and was roundly told by senior people all around the industry can't be done and of course being Miami just took that as say oh yeah。

I get told lots of times you can't do that， usually on some I'm already doing。

 but then its just I just split it off and chargeds head and all worked that great。

And so I just to gave you an idea， if you kick off a double virtual machine。

 there's probably sort of a thousand compiles happen by time you do anything interesting and if you runs three length of time there's between 10。

000 and 100，000 compiles。It's an average developer。Launches a JV 100 times a day。

 then that's100 times， 10，000， about a million compiles a day。

 there's a million programmers in Java and that's way conservative and there's a lot of trillion locationss of my compiler daily just in the developer community。

嗯。I've done all kinds of stuff， not just building VM， so that's been a long time to that。

 but I was doing compilers when I was 15 distributed computation in my 20s， early 20s。

 custom hardware， little late to GCs， non whiteing algorithms， lots of patent as。

Okay so I've been working hotspot for one time， this is a talk about virtual machines in general。

 but it's obviously targeteded from my experience in Hotspot。

 but I had a lot of things to say here that I think apply to virtual machines everywhere in particular I've been in good contact with some of the JavaScriptscript people all and less good contact with people at go and dark who I'm watching make mistakes that I've。

Made and have tried to tell them and they're making anyhow。

 and then they fail okay So there's lots of fun stuff in here。

 during the 20 years when I're working on hotspot， I watched it become robots。 and when say robots。

 I mean it is reasonable and common for a Vm to launch3000 and 10000 runable threads not just actual runable threads and the Vm will not choke on anything。

 will run but run them well， run efficiently so that's the difference between like I can run one thread versus I can run 100 threads I can launch threads getting 100 threads actually run efficiently and don't know choke on internal walks is a big thing to do。

 hotspot can do it on the 100000 level。 I ported it to half those machines。

 I watched pick up a bunch of compilers， I was very personally responsible for that one which is one sort people thought about J code。

 I had an offhand in all kinds of Gcs because I was always involved in how the GC interact with J codes。

 a key trick。GC work at all in these systems is that boundary between GC and code and much of our fun stuff came in along the way。

So the nature of this talk is that' too much stuff to say I'm doing this for a long time and know I'm fast I'm curious。

 I code hugely and along the way I fall on every possible pophole on the planet and take myself and move on and so I can try to explain some of them and I'll make my best separate but there's just too much stuff so you know maybe the topics I'm talking about today if you're head for sort the ultimate and speed or the ultimate footprint or power or whatever you get all kinds of engineering complexity and costs but often these things also interlocked badly in ways are not obvious and a decision that you made you realize you made it will totally prevent you from going to the next level of power limitations to perform to whatever you're going to do so you know I'll say what I can and there's lots more behind whatever I say I'm happy to stop for questions in particular I talk fast I talk curious if you want to find something I'll ask and I'll stop and answer it and if they're confused so as an next person and that's all good it's all fine to ask me I'll take questions。

I'm going to start in with some choices people get to make。

 so VMs are generally considered these big complicated Vs。Or maybe not。

 maybe they're really small things like Slock and OBM。

 a bunch of little tiny VMs that do the job of virtual machine in both a simple and sort of feature。

Miaturized way。嗯。But what you features you find how complexants get depend on the features that you're headed for here。

 and so I'm with the big desktop server route， which is a very different set of choices from what I call cell phone guys。

 people who are doing systems for which the code is known ahead of time what it's going to be。

 it may not be all in in in your virtual language， you're going to have things around the radio and phone。

 things DSB chips or parse analog signals， you're going to have bitlet routines for your graphic screens and stuff like that。

 that's probably not in your virtual language， but have to interact with them。

And whether or not you do sort of arbitrary cohere。

 it drives an entire set of decisions on how the VM is implemented。まこえてくれない。

So there's lots of other choices here， are you multi core， are you single car。

 are you multi threaded are you single threaded， it goes on I， here we go。

Porable or not are you going to port to X86 is's the obvious choice you're to report to arm chips。

 they're pretty common too how about DSP you do doing deep use right Okay。

 what about are you going to call native code versus your genetic code use the same calling convention for them both on X86 there are probably four or five commonly used calling conventions。

You probably only want to pick one and if you're talking to code that's a different one。

 you know you're going to get screw， you have to fix that it， you have Indianmunous problems。

 you're x86 you're small， if your arm， you're big or maybe was a bit flip， you're going to do GPU。

 you're probably a big Indian so you have to choose pretty quick what inmunist you're going be because it's going to change how you talk about all kinds of things。

Are your threads， ring threads so they you user mode threads， OS threads， which way your Ssco。

 they go you know this way， right which way you're drawing。

 Are you interested in small footprint or server route these inreparible scale now are you going to have an interpreter or a jet or no interpreter at all You're gonna be multithread or single threaded There are interesting problems in the world for which people truly intend to write single threaded code doing all kinds of control language stuff for small machines for which they wouldn't be them under the hood to make it easier to write the code your car probably has 2 to 30 CPUs in it。

 Probably many of them have a fourth interpreter buried in the bottom to get them up and running that fourth interpreter is a mini virtual machine that lets it easier to just initialize hardware screw with it before they launch onto whatever the main piece of bearing。

Are you multi car or you multiCU， you have another new set of problems to look at。

So let's focus some of the interpreter choices， somebody who was going to launch it doing hotspot interpreter right away who's faced with。

 do I do it in C or assembly， a simple pure C interpreter is easier right， easy started with。

 you'll spend all your time in dispatch so you go to the GCC label bar。

 you get about 2X faster than a standard puracy interpreter， but you go to assembly。

 you get about 2X faster again。Since there's a lot of runance code in the world。

 there's lot of startup code， it's actually worth it at some point to burn some cycles on an interpreter and have it perform reasonably well。

I've seen a couple different ways to work on that dispatch overhead that's typically you know half the time an an interpreter's dispatch there's lots of fun games you play there you burn a long time trying to get your interpreter go faster however an interpreter for Java means to have a stack or layout which sucks for Jes because they like to do classic function call layouts where you have fixed stack frames and the difference between a variable stack frame and a fixed stack frame for the interpreter versus a JI code has to be bridged by implementation here。

So maybe you give up on an interpreter you can have none and then you would to do something to run so the August when use a stage zero templatele style jet。

 rebyte code stop and code out rebyte code stop machine code rebte code slot machine code。

 it's very quick it's very easy to generate it's sucky code but it's faster than the interpreter except that the costs are diming it the first place beats just true run one code maybe you want to have stage one call it a light optimizations。

 constant folding dead code elimination， maybe some loop invariant posting and a layer scan allocator。

 and then C2， the one that I did for a sudden has like all the those and muscles possible in including a graph car allocator。

 every kind of loop optimization on the planet。This is a much heavier weight operation。

 but it gives you performance that's actually on par with C code and that's easy to verify。

 you can write code that's faster either language than the other one。

 but if you write straightforward looking sea light code and Jo don't get straight。参加了。Oh。

You care who you target， if you're Oracle and you're targeting spark then you're going to make a spark im or both people do actually sex by arm。

Are you mixing， are you ahead an interpreter， as I mentioned。

 it is faster for run lots of code and start？To have an interpreter over stage show a jet。

 but they didn't have to go back and forth， you have to deal with calling conventions across the boundary being interpret it in Jted code。

And this final look， I'll talk about some more in a minute。

 this has to do with ultimate peak performance。And Java you methods are not final unless you ask for it。

 so by default or not they can be overloaded， typically they are not in lineing is the performance optimization we have。

 I'll talk more about that later as well， but if you inline method and later it gets overloaded。

 you have to unwind and go back and try again and the ability to unwind and go back is crucial to allow you to inline those nonfinal methods sort of ultimately and get that performance out。

 but that impacts your jet very directly and how it attracts what it where inline where those bits went。

So。Stagehow versus the you and you know interpreter model。

 This is this model where you just spit out code for every Btecode you run across and then executed immediately you see a bytecode。

 you've not did it before you did it， you run it you follow the end of that little sniop that you wrote you run the next bytecode and you jet you go if you go backwards you go back to code already and you run code you've already run that the good mode the problem of course is that it's still slower than interpret you run on color and there's a lot of remote code that start out there's like a million bytecodes where you hit the main Java good news for stage with no funny stack layouts。

 it's fixed size stack frames for everybody inter call nicely with higher level optimization。

You do get lots of bulky code that started up big footprint。

 but you can throw away and regenerate it pretty cheaply。

 it's as fast to spit this code out in your L1 cache and cache makes it into your L1 IC as it is to like suck it off the main memorymory。

 you't even bother when you get tickle out to main memoryory you just want to throw it away and actually write all of your cachees。

Okay， switch threads here， Ds。Get started， use something simple， as you said。

 what was that Mark Suite or compacting？Ase space semi space collector。 Yeah。

 something really simple， So the world， pick all your objects up， move them， shovel， do MacN。

 when you go faster， suppose you got a 32 core server， you get 32 cores producing garbage。

 you get one core collecting it Okay you're can spend all your time collecting you got to go fast to keep up with the guys producing garbage fast so you need to parallel collector or it is fast and low pause time。

Are you interested in web services where you have past times under your order of seconds or somebody gets pissed and says。

 oh my God， the website's down， I'm I'm going to eBay from Amazon。

Or maybe it's low pause time because I'm doing credit card transactions that I have about 100 milliseconds between when the network transaction comes over from。

 you know you're sending line to Starbucks， I talk to a bank。

 putting know the DB lookups and the overhead send the back around you about 100 milliseconds to make that call about whether I'm going to reject your credit card or not。

So that means I want a low pause collector that maybe low pause is higher frequency trading。

 I've talked like 20 different high frequency trading houses， low pause for them means fiveseconds。

 they'd rather be nano as like can get it。I mean late right， mat， Yeah， what late。

What is the max latency between doing this to doing that。

 can I group all my GCs to a different point time it。

 until they talk to people who have arranged it that they only do young gen collections until the end of the day and then they don't do a full see to turn the box off and we turn back on。

How about the exact collector versus a conservative one exact collectors let you move objects that internalize you compact objects detriment your heat lets you do bump pointer allocation easily and efficiently that combination of compaction and bump point allocation is worth about 5% to 10% performance over a conservative collector。

Which doesn't take to move objects。 And that's because all your live objects which keeps shifting over time as what they are gets smeared out through your heat。

 as a 9% drop off rate。 G C works because there's a。Those generational assumption works。

 most objects are young， going to live long， they use a lot。

 get scattered throughout the heap with debt stuff in between them， you compact。

 they live nicely in your caches because they're living nicely in your caches。

 you get better cash behavior out of them， you're runfa。

So it's a well seen in academic nature people major this is a real effort there。嗯。

Going parallel is hard you get under all the parallel madness and rate low length。Both frequency。

 race and issue bug and concurrent and both parallel and concurrent is really really hard。

 and that's a problem that's sort of uping the Zul's got it right as assume GC got it right and no one else has got it as right as a Zul does by like a fair amount and it's a problem that people have thrown。

Oh。Probably thousands of mans at， I mean， how many mans has Oracal and Sun thrown at like CMS and G1？

We teams of 10 people， 20 people for a decade。And then I've been done the same thing and other people have done as well。

 so it's a hard problem。Only more GC choices， but the two places that you're going to pick up staff routes。

Stopping where and safe points are these sort of two competing things。

 I can argue well for them both， but I like safe points better。

What it really means is that in my multifed program this guy's running some hot bs loop copying something from here there。

 Sasby on what hell he's doing， this guy wants an allocation that heaps full he's out has the GC cycle he's blocked until GC happens this guy's middle running counter you got to stop him because you're going to move the array that he's working on in your moving collector and tell him his pointer his mode he where does he stop。

 how do he stop him you go to the OS and say stop that guy they always stops that thread okay his pieces to some random place。

I when to move them， we went to go fill his registers with new places right where the objects all basics all moved to。

 so you have to go find all those registers that hold pointers。And how you do that， well。

 one way is to have a map at each firm counterpoint， but those very， very bulky。

And actually changes kind of modestly by instruction by instruction。

 so people often will have tried at least doing things where they have hoot maps periodically and you interpret instructions between hoot maps as a sort of always compress the data down and so you start at some point nearby and you walk forward counting instructions modifying you go to get the one of the graph and say。

 what this is what my corners look like。You know the games。

Picture oops in the registers and stack areas maybe even odds the evens hold oops and the odds do not and then I don't care I just said even but odds I little more that way and I can find on my pointers I've seen jobsscript guys say I want to be conservative on stack and exactly on the heat and an the observation there is exactly the heat sort of easy to follow because those roots are fixed and unchanging and of relatively easy to track and the stack roots are hard to track because they' changing very very fast according to how leg codes running。

But in a 64 bit pointer land， there's not so many ints that will falsely be confused with a pointer。

 so even though it's conservative， it's not to be very conservative the down of course you still can't move things that are pointed out by staros and exactly those are the guys that are hot that you want to compact and you want to move。

Safe points are places in the Co agreement arranged to have group app。

You want the guy has stopped there。And we do that， for instance。

 is to pull so some Jitty code you wrote that said load a bit test it if it's not zero。

 I need to stop now and you stopping at a safe point Zul did't hard work because we thought the cost might be high it turns out next6 it's essentially free。

 you can be preempted at not a safe point， same as the stop anywhere OS might just preemped because it does and then if you want to get to a safe point afterwards you might have to roll forward somehow。

So imagine you've 10000 runables， the O is running 32 and 32 core and the other 9000999 whatever they're all asleep somewhere。

 they've all been swapped out， they're all at some random odd address and code now you want to do GC cycle while the bulk of them are not at a safe point and so the bulk of them all have to be woken up by the O run forward a little way。

 stop at a safe point go have to sleep again as you roll for 32 at a time when you're 1000 to go so that will take you a very long GC pause whereasas if you could do something cooperative of the OS you get stop at safe points ahead of time and make life lot easier。

So speaking of local threads， to the multi fing costs。So if you're landing in the realm of one car。

 you don't need walking。As soon as you go to multiple f to some sort of lighting mechanism。

L you get preempted while you're holding on a somewhere manipulating some critical resource。嗯。

So you have to find all the places where you need locks。

 that's actually a hard problem its a program that's bigger and more complicated the number of places and times you need locking sort of scales up and becomes very difficult to find because you get low frequency bottle。

啊。You do need the stack point in the program counter to find your stack routes。

Which you would normally ask an L for， I stopped that threat because I went to a TC cycle。

 give me his program count。Well， it turns out， common problem with OS is。Its that with low frequency。

 most O that would considerably be robust will lie hand to a garbage program counter garbage stack on your back。

That led to any number of long term， difficult to find bugs and in of VMs that I worked on and the reasons were all kinds of races deep in the Ls between hardware races where the hardwares cache and registers in hardware only these spaces that it didn't tell you what it looked like and they vary from chip to chip to games like this where you overflowed and you're trying to throw a stack overflow exception and should the TLB miss and the overflow handler which went to a page fall and God was wearing the LS somebody returned the wall on one of these and the pointer didn't get moved for your stack overflow such object and then crash and burn later。

About multiple CPUs， it not just multiple threads on one corner， multiple CPUUs。

 so now you need actual comic operations not just like。

To implement a lock here you actually have to have a true CAS operation。

 CAS instruction piece hardware， you have to deal with coherency and memory fences。

 you have to deal with some sort of low frequency dataator spikes where multiple threads。

 multiple cores are talking through memory in ways that you're not expecting。

You have to deal with scalable locks so before you need locks and you're14。

 but it just meant you switch thread to a different one when you have lots of cores trying to beat on lock。

 they need to compete well， meaning you can't spend all your time waking up and going back to sleep you got 10000 guys and you wake them all up and one guy grabs a lock and 999000 go you have to go back to sleep and you spend 100 wake them up sleep wake them up sleep you got to do something about scalable here and you got do scalable locks and digit code as well。

 So it's not just that you're implementing locks in an that a language implementation。

 you guys writing your VMs in C orQ+ plus whatever you have toit scalable locks So' that's a real hard trick。

 including games like spinning and retriries for lightweight weight contented locks and under super high contention you must have fair locks all modern large Java app servers web servers。

 whatever。Expect fair loss， they're not demand by the spec。

But if you don't implement fair locks when their thread can exceed some out some big load hits it some poor thread will be totally stard by the OS and I can show this on every OS on the planet。

 that starved thread when you acquire lock will never run until his timeouts happen。

 then the VM will start throwing the board and transactions left and right and it will just go down in the flames know as an app server kind of thing these guys all rely on hotspot doing fair locks under a super high contention。

Other games， I throw that makeupup。Los in you， print it out or lost N code didn his network hack arrive。

 waits after once to process the network hack。DC about your progress， why you taking a stack。

You can't actually touch a stack in particular on like Spark。

 you can't have a spark register right to prefetched stack elements that you're busy trying to write with the garbage funder。

You need to take for a GC lock where run。But this is a little bit of a lower level nitpicy funding game。

 The original implementation of 64 math and hotspot was it's a pair of into of the carry。

 you load to the low two， you added them， you pull the carry out。

 you throw it in a three free input adder to get your 64 added。 turns out that the big user of。

64 of math is a big injury package， which is called by crypto every time Sw as a web service with an encrypted transaction。

Big integer actually uses longs like their a pair of eventss。They shift the left。

 they shift the right， they mask the high， they mask the low。

 they want this bit of that half and they're trying to do merging to carry the computation around So it turned out the optimize is really well so there it is all those fasts and shifts at the job level turn into the simple register selection of the x 86 level I grabbed this four bytes for memory and not the whole eight bytes and then shift that it grabbed the correct set but our code by far on the x 86 our E32 machine and it took a long time made the 64 bit instructions to actually look and work as well as the 2 instructions it needed like dual issue on the 64 bit offs as well because of the masking and the shifting was extra opt had to half。

That you didn't need when you had it broken in half so there was a transition Huspot went through when it used to be this version of math and then it went to 64 but math that didn't understand how to do the ad out with character anymore and actually the code got works for a while it took a while to get back to the same performance。

O。What was my wild want through things that weren't obviously choices when I started out that hindsight were like。

 oh， shit。We made a choice here and now we're kind of stuck。

I wanted to take a deep dive into N calls， which sound like a thing that ought be really easy to do and in practice could not be really really hard to do and has some hard lessons in there。

O。So I'm going to show this for Spar because that's the timeframe I wrote the slide。

 but the same game happens on X86。And really the idea here is that I want to call some native routine。

 like I want to blitz some stupid piece of pile of bits onto my screen and they got pretty you know blogging me now click button aware the hell it is。

If I have a fixed application set like I own both sides of the equation。

 I own the Java code I'm running and the JBil and I own the native code I'm calling。

 then this problem goes away， I can do the right things very。

 very trivially and do the obviously Im make a call and it works because I know what the native code are to do I don't know what the native code' is going to do then my life it's a lot harder。

So I'm going to show this example here， I'm going to start by saying rest will push on Spar and the next thing takess you to add the BT big frame。

Oh，in going hours， having the wrong register， going move it， no big deal， take your native call。

Your return result， hopefully is the right restaurant next 86 it wouldn't be that one in upon BPP return。

Pretty， pretty standard stuff。Well， actually no， so if you're on you know well strong type language。

 you probably know where your float values are or your float registers。

And your answer in the registers and area the2s should cross except C compilers for the longest time dears for printf purposes and all the floats have to passed in the ant registers so in the beginning when you made your calling convention choice。

 did you choose the native X86 volume dimension， if you did you get the skip a step if you did not。

You see it this step and instead， every time Java called Java with floats。

 you shuffle the as and hit registers， and when you got into that routine。

 you shuffle them back to the flow registers to do something floaty with them。

So this's in the wrong place， so now you have to decide where you're going to pay the costs。

 Java calls Java or Java calls hate， what's more common， well Java calls Java is more common？

So put the float and flood registers。Therefore， they the call they' in one place can move。

In this case， because it's a 32 machine and I'm floating a double precision。

 I have to move it through memory and two different registers because it was 64 on one side and 32 on the other。

 we'd go away if you're a 64 bit x86 or not these days。

But you want some to a fast argument shuffle in general。

 the trick is a parallel copy from this pile of registers to that pile of registers were registers include stack slots because youve had more of things being passed and thin registers or something just spill on the stack and the guy you're calling in wants things built into different places on this stack so you have to do some sort of horrible shuffle shuffle which is really just bunch a loads in stores register moves you' got to generate them。

稍的发问。Okay， next thing， handle can't pass Robert respect pointers to NA code because the native or NA code won't tell you where those points are。

来干嘛。I was wondering you said earlier that there are a ton of different arguments。いや。

The world would not con trying to stop。Created one more。

 why did you choose to or why did Java choose to adapt to all of these？

Rather than half the world adapt it。No， well， Castavo wasn't important when it started out。

C code was everywhere， Javava was nowhere， right so I had to choose to have the sea calling convention of which there was a 32 bit one and the 64 bit one wasn't around yet。

Which there were several fadeubbit ones， but there was one that was more common that Intel was pushing。

And then what I do with floats， when I'm strongly type is a language， I know for a while。

 down the wall where my floats are。Whereas Sico did not。

You know as an example that they have the Java a memory model on day one so they eventually learned and they decided to Yeah and in fact。

 the first cut of the memory model was entirely flawed。

 broken in a lot of ways and I ended up implementing I did the reference im of the second cut and I went back and forth with the guys designing it as to what couldn could not be done in a compiler and what it meant to do the memory model So totally there was no memory model in the beginning So Cco doesn't have a memory model So right away you get this 20 game I called C code what did you do well the answer is you don't know because the C compiler didn't know because there was no spec。

RightSo you had to do on a case by case basis， this compiler invented this code in this way。

 therefore I could guess know what to help， but there's no way to upfront a already define for a particular C code。

 how it going behave in a multifed environment， you can only say for this compiler。

 this web of this compiler even this is the code in a minute， I now know what it does。

 there's a long time for X860 with a memory model。Right for a long time they delivered chips and not motherboards。

 but the memory model was all about how chips communicated through the motherboard which they weren't making。

 so they refused to put out a memory model and you had different memory model behaviors where you had to compact dual core versus Dell or Al or who else so there a couple of people doing dual core machines back then they vary we got kind of fun buds from those games that were up to the motherboard and until a few your hands something。

喂啊。Everyone read this slide five times over。I need to pass in a handle。

Because the the C code sorry the C compiler won't track my corners to this day they don't LVM with the common other C compiler out there is not got corner tracking built into it in this way。

 so if you build native code and you're passing moves in he does something with that pointer you't know what if you want to move it later because your GC says I need to move it now then you can't find it in the Jit code in the C compiler code and fix it there right？

So you don't let him have it like getting him a handle instead stack。

 give him important to a appointment。这都个混的 point。M is the handle for no。

 otherwise you put the actual loop and the stack， flag this with metadata there's a pointer here。

 you can the address to it。And you unwind when you return the pointer by asking dismal if not。

 you have to be handling one。Might be locking， if you're walking native， hear's some locking code。

 load the header word。This is a thin lock， so you set a bit， you attempt to ca it down。

 if you succeed， you win， if you lose， you going to some slow path that's out of line when you're adult。

 you have to unlock again， there's a slow path in case you need to wake up some guy you have to to notify that you let the lock go。

Alway us continue did it every time I'm writing a call to a native method of which they'll be thousands and thousands of。

系。Okay， I have to allow stack crawl and it's on entry to the native code。

 which might block I how long it's going to be like this is not a problem if I know what the hell code is doing。

I'm doing some bitbl to the screen， we'll be back in the millisecond。

I don't need to allow for a GC during that millisecond Okay I'm calling to the code I don't know what the hell die。

 Maybe it's on for the next millennia it's waiting for the disc to come back I don't know so I have to allow a GC while I'm waiting right so how do I do that All I have to slap down as I mentioned I don't have that OS and the program counter reliably from the O。

So I'm going to slap down the program counter and the stack pointer beforehand。

 I put them in some low front local storage area here。

 do it this way the X86 the answer is a little bit different。

 pick front local storage in a couple opt and  X86 a different way。

 but X hockey seems down and here I'm relying on this is sparked hardware memory model X86 is a similarly conservative model here。

This store instruction is the unlock for the GC block， which is like an inverted block。

 When all threads have let it go， GC is allowed to claim it。 If they have claimed the GC lock。

 then they own the heat and they can mutate it。 No。

 and no running thread is allowed to peek at his own stack because GC is about to edit his brains or brain surgery on himself right So this instruction。

We'll turn GC on at that clock cycle。This is the funny thing about race conditions and code here。

This instruction has to be coherent in memory for the GC thread to find it at the time that this instruction happens。

 these two stores cannot be out of order。On my big fat wide House 3200 weight machine。

 or else I have a low frequency buy where GC will grab this， see the stacks available， walk it。

 grab this， get the wrong value， crawl the wrong stack place fashionly。就。Already。

 I'm deep into memory models。While I'm just trying to say， I want to make a native call。

 there is a very delicate memory model dance going on here with a racing GC3。Having done that。

 I have to unlock and way out， which does the same thing。啊。In reverse。

 Go grab this is the instructions are different on next 86 because the CAS takes separate ops。

 but basically I slapped down to zero saying I went to CA down to zero saying hey。

 you can't GC anymore I'm replace my program kind of with a zero if I succeed。

 I own the GC lock on my own stack I can get mutate my own stack I didn't read my own stack until I acquire I cannot read my stack in for instance。

 hardware ge ahead registers which you know like register window machines will like pregra the next set they can't you're not allowed to because the GC still like probing the updated bits into the stack。

So it's essentially it's a lock required。A couple other oddsionss for Doly Land。

 I need that J&I in environment for the standard J& I handler recordpper。

As a service for native code， we allow handles beyond some local stack。

 thats cheap to allocate and throw away bunches of handles and we reset the handle before and after making a native call so that they have calls allowed to make more handles。

 these hand handles who wants to make more and then at the end of the native call you can wipe them out quickly。

So this is what it looks like。There' are some， oh， I' made a stack ring， I looked at my data&M。

 I'm handalizing however many groupsops I got passed in， I had to do an hard shuffle。

 get my floats in the right place， I have to enable my staff to get called， do my GC block。

 myF call sort of like a you know。The least little thing。

 and then have to unlike my GC where I come out and allow。

Well I'm raising against GC see if I can mut take own stack。

 deamleize and clean it up and get out so I went from you know three or four box cycles and a couple instructions to on fifth odd not counting。

 you know there's more if you have more arguments， more if you have to do locking。Kind of games here。

In a lot of five cycles。And that's the difference here is that this is required because I don't know what the hell I'm calling。

It could block， it could come back right away， it could do bad things to pointers。

 it could try to hang on to a pointer that I want to move later and I can't let them do that or I'll just get a low frequency crashes something。

There there's lots of defensive things happening here。Because I don't know what all。冇人。All right。

 we'll switch here。 So here's a here's a collection of things that we did going in。

 we didn't know what the hell we were doing， you just make a guess， best guess of time， Oh this way。

 you， you take off the go， you have to make something happen and then turn turned out to work well。

So safe points worked out really well， turns out that it was a great great notion for letting Fred do a lot of self service tasks。

 I'll talk more about that in a minute。It was a great spot to do deopimization。

 that's that unwind from over aggressiveive optimization， usually over aggressive inlining。

Inlining being the performance optimization you wanted to inline furiously as much as possible and then occasionally made the mistake head back out backing out exactly required a lot of state contract tracked by the jet tracking that state would generate necessarily code to be able to unwind your state back to the Do works machine architect at state turned out having the safe points around。

 let for good optimization of that unwind state typicallyyp you had to hold onto to a few variables of otherwise be bad。

Typically the retro allator would spill them off to the stack and mark them and then that was it that was your cost to maintain a safe point at the safety point there'd be a map saying。

 oh， you wanted the job go virtual machine Local1，2，3，4，5 with here， here。

 here or here spilled the stack somewhere the J code didn't actually want them didn't care for them he just spill them out to hang onto them so left for good optimization。

 good performance and the ability to stop in any point and line。Self serviceice tasks。

 things like find your stack root well it's all hot in your own L1 right your threads doing to himself so he's running through his coat screwing off the stack。

 test a bit， oh safe point， crawl my own stack， collect all the routes。

 maybe flip them all with is G Facebook slap them down somewhere and buffer for a G to to find it and going all over with in a microsecond。

And that's， you know DC pause time on that thread was a microsecond maybe to crawl a couple hundred day of stack and final stack。

Polling turned out to be really cheap， it's a load compared branch the load's hoting out wound。

 the branch is entirely predictable because you never ever stop but they't give it a safe point。

 it's extremely rare so it was really cheap because this pullinging cooperative preemption was I think we did to the zole and that was to handle a case of 100。

000 threads then O would just call into a thread and say hey your time slice is about up I'm going stop you at the end of 10 milliseconds stop yourself soon and that thread would see the safe point that stop into a yield。

And that was how I got all my 100，000 runables to all be stopped at a safe point already。

 and that meant the GC in the background would be crawling all the stacks and mutating them while they were blocked by the OS without ever waking that thread up or looking at it at all。

 would never care GC take his lock， crawl Sta mut it and release his lock that thread would never even know。

Okay， another thing I did， Heway compiler， this is the one that everyone told me， you can't do this。

啊。But it was really necessary for peak performance。

 I routinely got into this argument with managers at Sun where they would say oh my God。

 they're just too slow， they're just too slow， we're spending all our time changing and out writing color and whatever as well。

 not going to jle faster by turning off some optimizations or I did more peak performance and all the benchmarks by putting in more optimizations and they were like。

 oh oh but it's too slow， it's too slow but peak performance。

Every time so I move for peak performance。Compilr got slower and slower and slower。

 turned out it didn't really matter it's still an extremely fast compiler for what it does if you time compared to a standard classic LLV and DCC thing are like 100 faster。

 it's hugely fast for what does in terms of code optimizations。

And it didn't matter more and more CPU started showing out。

 what the hell you do with them well most of the time they're idle， they're blocked something。

 no one lost enough reds， what are the hell。The justs running in the background。

So why not burn some cycles to go make better power？

I went with something I had worked out in grad school。

 a graph based intermediate representation sort of very nontraditional， but it's also very fast。

 very lightweight was what made the compiler so much faster it's very easy to extend it's very easy to teach people once they got their head wrapped around it it's our graph。

Rewrite rule to do an optimization instead of a sort of a classic bit vector or data flow problem。

 it a very different mindset， but once you wrap your head around， it's very easy to work。Manipulate。

Graphcal and restaurant care a key item。Does that let me be robust in the face of over inlining So let me step you through the fail mode here。

 the problem people have had with re haters in the past。

 especially leading your scanline was that once you began spilling one gets spilled deserve another So if you inline and your method got larger your effective method that you're getting a larger inlines more and get bigger more and more stuff gets lie or longer and longer your spans。

 then you went out of register check is spilled when you've been spilling well if one gets spilled deserves another you sp a lot these seems to have a knee in their performance curve more inlinning but you ran faster you ran faster because you got rid of the call overhead head you got to optimize across the call boundaries until you begin over allocateocating over over inlining and you spilled and spilled and spilled then the performance spell band。

So to stay away from that knee in the curve， they would swallow back the inlining some amount。

 so they were not at the peak performance because it's too fragile peak performance， right？

The fix is to make the allocator not fragile and over inlining so the cost of a not in line method。

 you saved your call save registers you make the call you saved your call。

 save registers and you did the thing and you unwound those so you saved a bunch of registers on entry and split in the background on exit you a bunch of folks but they were split across the call boundary to and the call prolo epi pattern so that was the hidden cost of not inlining for register spells the trick to simply make allocator do no worse than that。

He's got that many instructions he can spill and he's not doing anything worse Once you get that right。

 then you crank up in line you crank it up a lot and it doesn't matter in terms of spilling。

 but performance would sort of asymptically increase to be hit a point where morning line really wasn't going to help you where high cash spelling or it wasn't just。

Wasn't anymore more to go get out of it。But not inlining was the failure。

 you and you must ask the allocator to deal with that。

What is it about when your skin allocate that makes it do worse them？

I don't know it has a clear like like it doesn't do as well。

 it doesn't have as much global knowledge as a graph codinging allocateocator for when it allocates but there are two pieces to this problem one is how do you do an initial coloring assuming you have enough registers to color them if it was possible at all and then when you fail and always in line you must fail and typically you have things locked into the rolling registers for color reasons anyhow So there's a lot of spill code happen no matter what Now how do you turn that into not so much spill code that's where I hadn't figured out why the linear scan guys never seem to do so well I did some myself and I watched some the people do it and then I flipped a graph coloring allocateocators while I was in grad school like I did my first graph coloring earlier on a grad school and kind of never look back like it was clearly better sort of theoretically when you would be able to color and the linear scan guys could not and then adult with spilling after that sort of how to make it friendly with graph coloring。

The same techniques I did for spelling for linear scan。

 I talked to and talked to linear scan guys and they had other approaches linear scan Als are much more approachable in the sense the curve learning curve get started is lower。

 but I think it does peak out a lower point because you don't have that global view you get out of a graph going out。

But here's funny， here's funny， this was like graphcaling knowledge for people who like care of what England soon does。

First X 86， right， we had eight registers， well， stack corners one get seven allocable registers。

 so I have a seven registered chief dealer。So if I went and did a graph ring allocator and I looked at the average live range at the first allocation after all the inlining。

 the number of neighbors in your interferences in your interference graph was well past color 15 to 30。

 the average was like way high， so you do a round of spelling at one amount of spelling。

 it would drop to an average of eight out of seven possible。And then if you're lucky。

 of course that which is color right there。 so the game there is that you always。

You always end up asymptically approaching maximal coerability with a graphic card allator because your spirit does something。

 but he doesn't if you don't just，Blaantly overspell， you under why a little bit。

 you didn't hit knowing ahead of time you're colorable but you might be when you try it。

 but instead you're always a little bit， not quite colorable theoretically。

 but in fact this turns out you got totally pretty quick and then you always had a much better allocation of that。

Whereas a graph the linger stand guys would make a pass， know they had to change stuff。

 changed a bunch of shit， but then they didn't have any evidence that they were going to get better quickly。

 so in the next pass they started spilling again that they couldn't fit it all on the round two。

 they had to fill their hands and do something really aggressive about skull until so they would just build like all kinds of things。

And that would get them be done， allocate otherwise they'd be oh another couple things didn't make it this go around。

 I'll have to spill some more things and try again， you know。

 fourth time through they're like losing big time to me doing my two slow passes versus there four fast passes its like you know。

They were losing ground on hand with us， so it was never as good and couldn I didn't fight hard enough on a linear stand guy to know why his numbers was good and an experience was just never as yet。

Okay， other fun games， portable stack information code。In the beginning， we started on X 86。

 we flipped a spark， which had these fixed register windows。

 so it was up the butt and stacks went the one way。

 and each one went their way where we had all this little code and we had to mangle around with。

And so came up with this brilliant notion， I kind of need a base and a next notion and an end of the notion。

 which is a frame it arrayerator， it's just plastic iterator， but it was written in you know T code。

Creating templates， whatever and intended to crawl stack frames of a low level thread of stack frames turned out that work for a wide range of CPUs and Ls work pretty well with registered windows actually ittanium as as spark all have sort of fundamentally different register windowing models。

 And this seem to cover them all very well。 So it was a really great notion to extract out all these weird sort of machine specific bits of what does your stack look like and get into the notion of here's upper abstraction layers I trying to do something intelligent stack in the lower layers just manipulating where you are and what the all sits for went this way or with that way。

 finding what it meant to take a map and which one whatever those all cover over the hoods。

There was another notion I put on here Ive mentioned before is that frame it adapts this idea of how you can mix Jittting and interpreter code as well as realizingizing call arguments。

 interpreters having their variable stack layouts and adapter as a way to change the stack with a little piece of machine code that would just shuffle as around from what the interpreter expected to the call site expected for the Jitted code using the standard good。

呃呃空说。Both of those things get into like games with manipulating your stack。

 which you have to get really， really comfortable with playing these kinds of things。

Code cache we're still all happily living in four gigs of didn code or less we're not close to that boundary。

 which means you only need a 32 bit code counter， which means you can use a cheap local call instruction right I say six and on spark and on risk and arms and everyone else So you really badly would on your code to fit in 32 bits and you crunch it all together and put it at a four gig boundary and say this is my code cache and nothing else lands outside this aligned four gig block and then all my call instructions are all like these third。

It's like big savings actually like it really is。Fast and slow pass stuff， blah， blah。

 blah and button flights， so as you saw in my native code call out， I had a lock， slow fast path。

I have a allocation fast slow path bailout I have an instance of runtime cashche fast slow bailout I have about 20 or 30 fast slow bailouts you're taking the slow path a lot。

 you lose slow path is slow right you don't want to take it that's the whole point you did this because the comm fast but there's an uncommon case that has to work correctly。

 but it's when you slow you take it， well then how you debug this code which is body design you frequently executed it you have complicated the tricky code it's by design infrequently executed。

 how do you Qate， how do you debug it Well you forced it happen a lot。

turn on one of these ss and whatever slow path thing this g here now happens all the time runs really slow So you tell QA hey go during a flight line it's going be 10 times slower it's going take overnight。

 I don't care， come back with whatever bugs come out of crashes it burn and usually it catches lots of bug lots of bugs usually in a very deterministic way but turns as a low frequency it rarely happens crash happens like every time on an overnight run and then from there you can get the binary research way down into what the hells going on。

That's the why。要不行。Denlocks， pigs， pigs， big businesses are not a big bit。

Fhin locks is basically the job notion of every object can be blocked。

But if you want to lock an object or some state you have to carry with that object that's dead weight otherwise And since you keep us full of objects if you're full of dead weight。

 then your cache is are full of dead weight and everything's running slower and bigger or whatever so you want to keep them as small as possible So the thing we figured out was that you could get into just a single word in the object cutter in fact a fraction of that word and you're going to have to do a cas on the object header to say I took this lock and if you win it know you're all happening if you lose it there's some slow path you're going to go deal with hey。

 I feel I' do a lock and are going go to sleep on the lock was a lot cheaper now back in the day every caves was a misseddema memory on X 86 so know。

The lots to lunch 12 300 clock cycles and a four I machine。

 100000 instructions didn't happen with30 cas these days it's only an L2 hit it's like 10 or 20 clock cycles and the unlocks guaranteed in L2 so it's much cheaper but already at 20 clocks you can do better there's a lot of lotss that are essentially never ever changed ownership。

So you want to think a lot， especially the own lock。

 No atomic lock other than the original take it once you take it， you just fail to unlock it。

 you leave it blocked next time you go to acquire it。

 you already own it and all you have to do is say， hey。

 do I own it all I do no atomic operation Atomic operations including the memory the X86 memory model memory fence that forces the hardware to install to loads and stores set across that barrier in correct way。

 not taking that fence like your own faster Furthermoremore。

 if do not take that fence in the gen code taking the lock in the beginning knowing that you hold it all the way through and all the in line synchronized methods how the locks and in locks all the way through。

 throw those out including all their implied memory ver。

 you own that lock for that whole time whether you should have held it or not。

Do it to how you want the jet， nice， ti performance savings， of course。

 paying the that to get back if you' were wrong and somebody else actually won it。

So you have to do something there's another good operation for safepointing individual threads is when one thread says。

 I want this lot and this other thread says， well， I'm kind of holding onto to spite of late。

 I can't let it go because I actually don't know if I should hold it or not to hit some safe point and inspect my state discover if I really own it or I'm just like any of it。

And so there was some engineering had to make that work。To memory model。

 another thing that didn't start out there， so we mentioned， it came along later。

 but it worked out really well to practice major piece of programming， I don't know。

 it's a mindset of learning， whatever that had to happen in that era more than 10 years ago that hadn't happened up till then that something made it possible for people to write multithread code by the millions prior to then all those multi corere things that were all handcrafted by guys doing HC and all vary from hardware to hardware to hardware until every one of your multithreaded programs that ran on the。

 whatever failed on the Fujitsu supercomp， whatever because the multithreading core talk to talk thing was all wrong between the two。

オ。You used to find what you mean by a memory model。 I just don't know that works。 Okay。

 so new model is simply the rules by which two threads talk through memory。

So the obvious example is this guy wants to fill an object and publish it so he stores to fill the object。

 then takes a pointer and he stores it some global place to publish it This red wants to find that object if it's available and if it's not he probably makes his own but he does something so he reaches for that pointer and he finds it。

Then he reaches through the pointer to the place that other guy filled in the past and asks what is in the contents of that object？

So if these stores are out of order。This guy will affect the object。

Through marry the other side and get garbage。Right so this store and these loads so there's a store to store and a load to load so all these memory model implies there are two threads it's never interesting to talk about one thread or people will say。

 oh， I've got this and what but no， you to talking about threads。Okay， store， store， load。

 load and did one of these cross， right？the memory model is telling you what the rules are for when that cross is allowed or not allowed to happen。

The big one is you want loads to bypass。Stores like get this waype。

The thing that is hard that is expensive to do。Is have a load。Stall。

 Is say it's a load of bypassing store is the big one like store stores。

 two stores are easy to direct in order two loads are harder， but can be done。嗯。But。

Load store orderings， X86 will let you go out of order on in the hardware in a big way。

And so in particular， if I store down to take a lock and then I load。

 I have to have a fence or my load happened earlier than my store was visible around the cluster。

 so the store hit on my core and then its feet of light sort of propagates out as people make coherency rules。

 my load happened hit my own cash because I was left so it happened wide way okay but I didn't actually on the lock kept from that guy's point of view because the store still propagating so that guy did a load to his own the store hadn't shut up yet the lock still open he does something and I got the load the wrong。

So there's a game you have to do there way to fix because you have to emit fence instructions to prevent bypass in certain sort of places。

Including in the Jted code， the JIt has to understand how the memory model works to know when gets becomes start fe。

は。Yeah， harding some brains out。Okay， things that were hard to do but worth doing maybe it portable。

 It turns out that it just gave a better discipline to the code it separated that implementation from ID below the line。

 I'm talking about how stacks are lay out where they go left or right or right to left whether they're big in a little and then how to register window up to screw it or not if I first them to flash or not power goes how our program counters store on the stack for return addresses sometimes they're in different places or not and above the line I've walked through frames and on this frame of when I final out stackers but when a new table stackies I don't know where they land in the stack whether they have a map which somehow correlates to the actual bits and memory the abstract player doesn't want to know how it works he just says oh my goal is to walk the stack funders my goal is to discover open slack or not because I want to release it for somebody else's purposes or whatever it's been。

Mial comps here。Li little bit of non-obviousness， hotspot lived for a long time with an interpreter and either the client of a server compiler。

 but it turns out that the middle tier compiler or however it's done usually make it the fast version of the linear can allocator or whatever hell if you put profile encounters in there it can profile about 10 times faster than the interpreter can so the code will run much faster than the interpreter code。

But it can profile at much higher speeds than interpreter can and he can do it more precisely because he's done some lost amount of inlining and then get inline specific counters。

 so when that heavyweight compiler kicks in he gets a much higher quality profile to go drive his own compilation decisions so it turns out it really is interesting to have middle tier and in particular you should not violate their profile and the interpreter other than the basic counts to say get to the next level up。

 but the next level lecture profile everything on the planet and hand those profiles off to the mixed tier that follows。

DO， this is this thing I was talking about before with inlining finals。

And yet to be careful you're with jargon are hotspot。

 use VOP for a particular word that the academic literature in a different way that word or their meanss are subtly different。

 but if you're looking at hotspot and how it does it and 99% of the VMs on planet that are running hotspot。

 you have to pay attention what this actually means from hotspot's point of view。

So the real impact here is there's no runtime cost in line nonfining okay and people who aren't playing this game。

 payy there's no hoisting cost at runtime and what the hell does that mean。

 what means there's a line in the sand and the code where the inlining was conceptually to have happened。

 the call went away and instructions got in line and then they went down and sed throughout and got merged with other code。

In the hotspot， that point went away entirely is not there at all。

 that inline code completely scattered in all directions in particular if you go up but you can't do in the other model。

 you can go up and merge with other things like youre ining an accessor function that maybe gets overloaded later。

 but the accessor function just below the load might get wasted out of the register might get common in sub expression with that same load done elsewhere。

 it definitely pays off。Of course， if you do overwride the code。

 you have to flip it to an interpretive frame and that's not rocket science。

 but it is kind of hard to get it right， it's full of nit trickyt picky details to do the deal in that way and also the other effect out of the light of these skies is that they had a point in the hand where they went down at the D time they patch here to say。

 oops， you can't use this code because the overload changed。

But then they forever paid some sort of cost at that point there after saying something happened here and do something different in hotspot you had to recompile but there was no long term cost to avoidment method it went away after the next round of getting。

And I can go into like fine details with people like IBM and I went around this back and forth a dozen times。

嗯。Soft part thank code。Hard， but you're going to do a lot of it， so get it right。Code patching。

 inline caches and not en code， okay， so what is an inline cache suite4 people on that1。

 but inline cache makes a virtual call as cheap as a static call。So you look at hotspot。

You look at all the virtual calls you know in C+ plus you say virtual you get a virtual call and Jo like you don't say virtual you get a virtual call unless you say final well no one says final calls So they're all virtual Okay well in practice。

 none of them are actually overloaded and you prove it and so you get a sad call from the G point of view and you in line them like you would just like what that is okay but if you can't prove it。

It turns out that most call sites that you can't prove aren't going to go to multiple targetsets in practice do not。

They only go to one target so you want to have one entry cache an in cache is a one entry cache saying what is the class of the object to have in my hand if it's this class。

 then I'm going to go to the Jit code for the one method that he would have is his implementation for that class so the inline cache is a one entry key value pair the key is the class and the value is the call and the implementation is compare the class ID to what expected to be if it is call make a static called target so that's a load compare branch never taken the load miss is often in your L1 cache because you learn your object pair you don't even re reason。

The compare is predictable， the branch is predictable because you never failed I' like gosh。

 so you make a static call so next 86 I'll have to issue to load， do resolve when it does。

 predict the branch， pick the call， all done like two cost cycles。

So an inland cache makes what would be a painfulfalls， a low， low。

 low jump register kind of operation， turning into something that's a couple of clock cycles long。

 same cost， almost the same cost as a non virtualr call。The staticically。

 the set of call sites that you didn't inline， you can generally， you putting in cash in。

 roughly 95% of them， the in cash will forever only go to one target for the entire Life time program。

The other 5% will flip going megamorphic right away。

 and they are actually going to some bushy set of possible choices and they' have to do a low load load drug pressure。

So you can go do all kinds of anetta and building instruction trace of what right it's very it's a high it's a really good problem just a really good solution to the problem of endless virtual calls so when you get it wrong you have to patch it or actually beginning get start with the patch being empty and it misses because you've got no classroom what the class is going to show up there you have to patch it from empty to a holding class and you have patch the call to the correct target and you have to do it in face a racing dollar threads who remote or running through here and multiple guys trying to patch。

It has to be legit for any run double for to see any partial patch in particular on X86 the ICash ec rules were completely loose go。

 so any partial patch in whatever order never might like be for fences of any kind he can see on the other side of the line like completely independentlyly。

 so every possible partial patch has to be a legitimate X86 instruction that does something sensible。

And that's a tricky barrier， so get that right， get to think through what these caches look like and then you want to get yourself some support so you don't have to think about it anymore and you say。

 oh， stick it in line cash here and how it work right you。

You obviously saw often ask shoot down for everybody， but X86 has these variable size things。

 you want to update something in memory that the processors， so another is corresponding we can do。

 you have to do an atomic update on other past shearing effects。

Atomic updates cannot span a cache line， so you have to know that the patchualable portion of the instruction isn't crossing the cache line boundary。

 so for instance a call instructions is one byte but the offsets is4 byte offset I want to patch it。

 I can patch in between these two， but I can't patch in between these two because it spans a cache line will'll get a partial patch and some racing Java thread will see half of the patch and half of the other address and the crash burn。

So actually then cache is like load， compareance a constant is the right class branch， no。

 it was good and call， and I can patch here， I need to patch here to here and I can slide this thing around as long as I don't have a cache boundary crossing the patchable pieces。

 so I insert some knocks， make it slide around。AndBut getting that right is the pain of the buttont and you want to get it right Watson like pickle it down somewhere。

To do that we use a high level as simpler because there's lots of hand ass similar going on and it gets lots of onetime support and want a lot of the variant of integration。

 like I mentioned before I want to take this in cache and shut around withnops until it doesn't span on a cashline boundary that's very X86 specific。

 the risk world does it a different way fine。Normal asmbs don't get that kind of support。

 Furthermore， when I found that in cache I'm going to put it down wherever it landed。

 I want to record here's a program counter address and the code because that points to some Jted code that I can't let go away I can't recycle that memory because some processor is going grab that instruction go there at some future date so I need to track that I need to track that place so this metadata so I'm recording metadata with my assembly I have a hoop I have a class I I have a class pointer saying this is a class I expect here Well borrowber supposed can move that class yes update that pointer so I have to have a hoop pointer here somehow so there's metadata to refer these things。

So you recall all kinds of cool memory of stuff with all your invaris that you're proving and you want to write like assembly because you're actually intending to write assembly machine noted。

 so you write something that looks like assembly that was actually valid C code Do card or whatever when you run it just emits the code into a buffer proves all the invariance supports all your you know flex metadata shuts off the side like I wrote a list code to a buffer。

 it's X 86 so that I have to do a relocation， I'm going to pick it up a remove somewhere when I done。

At the act of picking up moving it， all fixed addresses have to be updated。

 all relative pointers to things outside that scope have to be updated。

 all that's handled by the similar format。There's a lot of fun games in Matt of high that make it easy to write assembly in support of the beginning。

Hospot's been running with a double word header， even on 64 Vm when the things we did thes we pounded it down to one word。

 which is this large interesting memory savings， it's every object got one word shorter。

 how many objects you have what's a lot， the real question is how many objects fit your caches well now about 10% more。

And on next 86， performance is all how fast kind of run from one cashist to the next。

 if I get 10% more stuff crammed in my dash or run 10% faster it's pretty。

So I can't use a 64 bit class corner because obviously that eats a whole word。

 so I need some dense class ID， we pick like 19 bits of class IDs and we have table mapping classes to class IDs and there's a bunch of hacks and you somewhere to deal with that need a thread ID I'll talk more about those in minute that's through the locking need a hash code actually even a 64 bit land of you know 200 biabyte job heaps。

 you actually went all 32 bits of hash code， it's a significant savings but I have a few billion objects that I don't have to make collision into my has table。

The thread ID what I did it this little here was I took all my stacks and I line and want to make boundaries。

And then if I'm want a stack pointer I just mask off lower bits so to get the thread local storage area I take my stack pointer and I grew to a jump registerher and I mask with a that's a short mask theyre only little knock off however bits and then I got。

P the storage point， and instead if I moved it and shifted it， I don't throw。

use spread IDs for objects for locking， I use a lot of cord VM code starts by hitting the thread point and then do something。

 so that happens all time on the fast path。So this has to be fast for your fast path or your fast path being fast。

Because they're aligned I could do TLD games for page protection。

 we do that for underflow and overflow protection， stack overflows and Java have to be done synchronously at exact boundaries。

 so you march along and you're recursively actually16 your stack endlessly。

 you fall over some 4K boundary that flips a bit， I say oh now one4 to a safe point you have to guarantee during the time you piece a stack and the next safe point you don't touch more than 4K more or you'll double stack fall and blow out so that was a job make that out an ID。

But then you unprotect that page and have a no one behind it to catch him when you buzzs。

 and you get to run on a little bit at a safe point and then start throwing respect stack a over full exceptions you't。

So getting S overflow overflow drove a lot of interesting， difficult runtime behavior here。

 getting that。Correct and in cheat， you know if it check your back point on entry every method。

 which I have some people do， this one has no cost I entry that。

 but instead there's a lot of runtime costs around wage protection board。

Safe point pooling single Freds， this is a key performance hack for having the deal work well with a huge count of fs。

 we get to a front level storage just like DLS Air by taking stack pointer and masking over bit。

 a little of bites and then reaching out。Gra a corner。Word for memory， if it's zero， I'm done。

 so it's an L1 caching load in our predictable branch， it's like  one。 seven one。

Ifs a bit set and when I do something， usually I do a lot of self-service tasks here some of them。

 I'll crawl my own stack for finding GC roots and reporting them or do a GC Facebook。

 I'm just going to put some bit in knowledge fingers。

IMight be told to install an exception to one thread can come of a thread here is a thread about death for you。

And you have to take it at a known Java execution point， so that's a point and then begin throwing。

M be a biased lock group reloc where somebody asked you， hey， dude。

 you actually got this lock you just like specificallyly holding on today it and then that threat has decide。

 know if he's at a point that you might doing what not。Debuggs you knowJ。

 you get a break point in running code stops what did it do Well what it really did is it took that running thread and it deoped it on the spot he set a safe point bit it ran safe point it deoped from that safe point to an interpreter now let me interpreter your interpreter as a hook saying oh I'm talking to JBDI Im to let you debu。

So you totally get optimized false speed to code and also bugability。

 a thing that people talk about in the 80s and '90s and hotpot does it， this is help。

Clean up your caches， your online caches have a class point and it's harder going to call。

 airline caches can go stale because maybe the thing you're calling。

Have to get validated because you load a new piece of code and you had this assumption about no overloading of some nonfinal method that got wrong that code's crap shouldn't be executeded anymore here's an end cache point to it somebody passes in cache they don't there we gotta fix that so you go tell an in cache no don't do that anymore。

Or maybe you've got a class you're going to unload and the only thing holding onto it is inline cache you got to go into that in cache and clean the class pointer out and say no no no no no。

 no one's making any these anymore， there's easy DC wants to do anything have to go find in cache is you can't do it while you're running or you'll crawl over that in cash orre running threats you stops at safe points of late。

Quite pre hour dimension。Thats do with OS trying to stop 100，000 threads bought。O。

Things I won't do again， things I did and hindsight like sucked。Okay， I did this thing in CQ+。啊。Wow。

 it was a painful thing Do would do it， you know nearly everything I did in cheap++。

 I could do a job now。In particular， in C+ Sp land， a lot of the C+ plus objects are floating around。

 double levels as objects in your objectP。And then this pointer was actually a garbage cycle pointer。

 so you have some pile of CL plus code， you're talking about the member variables left on right。

 you make some function call， you know as wide as it dies while it runs off and you call something calls the variables and what down here in stack that is where you block for whatever and GC cycle happened or you' this pointer here just moved then you're in your CL plus code or this pointer is now somewhere else。

Next when you take a virtual call， you go through to this pointer which is scalele。

 you grab the wrong thing， you grab the next register out。

 you jump to it and you're running some random copy code。

 God knows right your you run another10 instructions and you die and what's the hell happened unwind for that find that button Oh my God what a opinion on that Also there was like a dozen hotpot actually had about10 on point roll their own versions of GC mallc stack hos region arenas is a lot of names of these things but they all have the same effect of I'm going to allocate something out of this fixed buffer and I'm going to reset the buffer and go again it's a version of DC at UCGC。

C2， that's the headway compiler was using Bur style pattern matching。

 you know that was useful when you had back。Never meeting on risks。

 that was the point of risks and then never meeting on the 9'86， if you look at the 9'86 now。

 the architecture state is actually very regular， whereas the encodings like suck。

 they're like horrible for encoing， that's the as symbol calling the dealing。

The actual architecture instruction set is pre down right there。

 so you don't need this fancy instruction pattern matching and adds this extra level of interaction toit engineering。

 I would never do that。Just emit the obvious instructions in the obvious way。

 because there's only one obvious choice I didn't do。Patch and roll Ford safe points。

 the original hotpot did this， another nightmare， it started out looking good。

 you decided you're going to stop somebody by stopping them and polling because we were worried about polling costs back in the day。

The stop threats no at a safe point Once you got his address like the OS didn't lie you in the first place。

 you then had to move him forward Well the thing we tried to do was like patch all the safe points of the breakpoint instructions and then tell was like let's kind run again and hit a safe point for it exit the method hopefully you really missing spot jet okay we hit safe point after a while a break point was good somebody else was running couldn't handle the break points so they were like fetching break points were in the middle of airline caches because you're about to make a function call you to stop that So the guy trying to catch in caches would discover break point where he thought there was an in cache and he did all confused so then two piece of code patch what was not so there take code but around to patch one not totally non for little caches screen but multiple OS to spin resume cycles to get the guy to roll forward to save point ever do again do goinging。

Generic Col state registers so it's sounded a great idea and for people who have lots of registers and no register windows it is a performance thing like Powerography CR have a lot of registers and no registered windows and they want to use generic Colate registers so they want to have bunch the things that would went across the call site but the call doesn't know what's them he just says I want these registers I'll spill them in a little them later he builds them on stack somewhere it let them later now deep in the call stack somewhere you take a GC cycle you call your stack this friend hey。

 give me hear os he says well here's my oops but I got these registers from the color that I don't know what they were I say here but don't。

So look one more， and I got this pile registers， I had a math and what the color。

 from the stack to do。that guy what it。 So Lisa， well， you know。

 this was my but those I got from the guy love me， I don't know there either。

These stack calls a new and mess， so like don't bother， X86 doesn't need them。

 it's not an end of the world if you get the right location good to live without them。

It does help some， but's not a huge amount。Resh your windows， on the other hand。

 both the fixed and the variable size all seemed we fine once we got that stack frame next frame iterator thing figured out having rest your windows was no。

They're the only tricks were around knowing when you had flushed them and wanted to reload like the hardware was constantly trying to reload them。

 so you had to have one final flush of them before you unlock for GC or whatever。

But that was all done on a sta rate level。So I I remember I was talking with Peter Kesler。

 and he told me。Maly thread， when that came out， became the final。It was difficult to get right。

 we eventually got right on Spark and then I did to audittanium and then did it into azo and so at that time I had kind of wired in how to make it work right。

It was a pain in the butt because multithreading that there was a GC thread running separately from the guy running and he was talk about。

 you had to have some final register flushes in the right places when you need to hand off after running the thread waking up from he went to sleep the he just randomly woke up just as the cycles about to end so that GC wants to probe that last newop update and then released this guy and this guy's already running and so he's already got his harder prefeer going and the hardware prefech was already fetched out stale bit。

Then he GC said， okay， I slap down and release the lock， this guy cass wins the lock nearly goes。

 hardware has already prefetched the wrong things and then he grabs the wrong things about it so you had to get it right he get a flush in there at the right point。

That was because of。Mth Friday， GC background GC。啊But， we got look out。提置したとは。

I didn't understand there was a problem there。In the beginning。

 it wasn't obvious that this could happen。Heinndd say， oh was blazing odd in foresight now。

 no one's talking。嗯。Aapptter frame' frame adapters。But the hell I mean， a frame。

 an adapter frame that left a frame on the stack。And that meant that。

Going into some data call to some native call， I pushed a frame and I scribbled with registers and I did handles。

And when I unwound， I had an opportunity hear a frame stack had an opportunity to unwind and particularly to move things from one return register to another。

 that sort of a useful thing out。The downside for adapter frames we were calling Java。

 Java Java was that it had a spare frame on a stack and screw of all kind of stack files in particular there was some pathological cases where you' did with an infinite number of them unwindning。

 I went from this mode to the interpreted mode， I went from the interpret back to the Jted mode it went from J to interpret it and get an infinite number of。

嗯。For any adopters， what I mean is they adapt from frame to frame， but they don't make it。

As a frame adopter is。还是这。And that meant I shuffle as， but I don't actually put a frame to that。

So I don't want to crawl the stack， there is not a spot where I say this is a frame that is not a jober frame。

 that's not a native frame， it's an adapter frame。So that one works。

 but this one does not I we tried it a bunch of different times we needed it for intercalling between native code I'm sorry it interpretted code and J code and eventually I got this slide to the z and I didn't have to do this anymore and I got rid of when I was all happy。

Things I want to do again， constant loops in the code looks really great on X86 is a 30 gig bit immediate when you're in a 32 bitit because you can load have in one instruction and hey I need to constantly' a string point I'm going to load hello world Im going to load the string for low world great and then of course when you went to other machines you didn't have 32bit immediates because they didn't have a very long instructions had 32 instructions you can't jam 32 bit immediate in 32bit instructions because that's all bits so they had multiple instructions to split the damn thing around and that meant when you wanted to move it you had to go patch it they go patch it in all these places you had to patch it comicically for running foot get half of one patch you can have of another and that we have to stop your threads and that required to stop the world pause and which you see you otherwise didn't need one。

So， yeah。Better answer， just put them in a table and you just load them from a table and instead the load instruction has you know the table index in it。

 load table base， constant table base plus offset， I'm easy to schedule around the giit it's a one cycle load that's going hit。

and being known of as now theOops are just like laid out the table， just like a big array。

 concurrent EC just modifies them as it does any big array memory。

 fewer instructions on all other VMs except X86， and then of course no tracking in the code of where theOop is because it's in some table。

Lo of object headers and stack， this is hotspots， original thin locks。

 they picked the object header out of the object and they would jam and stack as a way to count incursion with unary counting。

 that's snow。One， two， three four，5 counting a 54321， un wound the stack。Sound kinds of nice。

 but turns out that stack your object header was not in your object， its almost stack similar。

And that meant everyone else who went to go grab your object header。

 I had to have a screw around where they say， am I looking at an object header or am I looking at some four reference pointers some stock where the thing actually is？

And maybe that other guy in the middle has his stack impact because he's deoping and all his jted frames are being thrown away。

 turned into torb frames， and so his stack is getting shuffled so where is it in his stack。

 well it's getting moved？I有。Whatever， so me the answerist was pain on that we doing all kinds of things and so go it。

Ling the bits in your head are that you can count you know zero12 mini that's all you need once you get past like three bits you're done for and the lock is deeply incursive and you go slow path。

 but people don't nestly take the same lock a super high count of times。

So you could have a short counter in there and after nesting a few times you're done。

 it didn't overflow it did went slow out eating characters didn't have anything back。O。So so。

That was an hour and a half。I have another talk that's just as long。

 follows me after this one is why you can't throw away code。Or what it takes to throw away recovery？

Instead I'll just top this one off and we'll go to Q&A for while so really you know the high little picture here is you're going run any kind of code including native code。

 run it well， went it fast quite defensively， meaning the native code can block or do horrible things to GC and look extremes of fing to do high good volume GC concurrent LVC have lots and lots of code that you're going to deal with you get all these you know general purpose tradeoffs that are cheap and easy if you own the whole stack and are actually really hard when you're trying to do general purpose。

A bunch of open questions I have for the big JVMs， I can argue strongly both ways of graph codinging versus Li scan。

 as I mentioned it's kind of slippery slope where your scan easy to start with。

 so graph codinging has ultimate performance。I'll claim that this one's answered and I like what we did with the one word。

 VM， there's some serious engineering hacks to squeeze it down to one word， but they're worth it。

I'm also claim that Hospot lived forever every day with an interpreter and a heavyweight jet or an interpreter and a lightweightweight jet。

 and they should have gone to a stage one medium lightweight jet with profiling one long time ago。

 and I don't know how stage zero jet versus an interpreter that one's kind of open。

I guess I can argue fairly convincing in both ways。

OS threads versus green threads or roll your own whatever regional threads again I can kind of argue both ways。

 ultimately hotspot started out with green threads and went to OS threads that seem to have worked out okay。

 but Java threads are known to be fairly heavyweight and they're like the Dudly forejo framework is all about making can threadlight objects extremely lightweight by sidestepping threads because Java threads are too expensive。

哎，好。High throughput versus both O GC， those are both interesting and it's hard to get both and it was all about both but they completely changed how GC works。

 everyone else seems to pick one or the other and they get most of the other side but not peak on every shot。

So you kind of have to there's some interesting trade out here a lot of engineering。

I'll claim done for the moment。And and back up to， you know。Yeah whatever。是不是？Ex question。

That was red。Yourite a bunch of papers。interesting stuff。好吧。Yeah。

 what is the quickest path to a working parallel？Pllel concurrent。

 so the answer is there's no quick path。But there's a quicker and slower path。

There's a lot of papers out on the azoole， which you see。

 and they open source bits of it in the past。I piered doing that one myself。

 but I'm very familiar with it。嗯。And I know that it can be made to work relatively straightforwardly。

H in hand with that GC is what you're doing with CO generation and how it interacts excuse with GC。

 and that's another set of decisions that I went through here that have to be thought through and dealt with you talking out from scratch then。

It's not for the faint part of here。So in particular， there's a lot of OS。Level games。

 user remote TLV handle gets installed and you're screwing with the TLV directly。

 you have to rob bits out of pointers so you're mirroring the TLV to hide them。

And then there's all the， you know， there's no point to it about this unless you're already fairly highly performing。

Elsewhere。The parallel concurrent collector is important when you're running lots of threads and they're running fast。

 so they're producing garbage fast。You're writing。Or you're putting together a financial system。

And you're seeing one thread or sort of very fixed breaks doing some straight up when something a grow shut down。

 you're probably not producing garbage at a high volume and you probably don't need it a low。

Concurrent collector， no important concurrent collector is flow problems。

RightBut when you start to say， yes， I routinely have 100 threads and routinely producing gigabytes a second。

And I want to keep my pauses down。I guess I'm saying is an academic exercise。

 I would do it as an exercise but dont。Have your research， your P。It not worth it。谁呀。

You've described a whole bunch of decisions that have。Sort of interactions sometimes。One so。

When one starts designing system obviously there are some rules。

 some things are good at something they bad， but is there sort of a sort of an order in which to think about making some of these decisions？

You know， start with GC or。So， no， up what your head， why so is your design， is your decision？

I'm getting out of grad school or nine so that's one set of decisions right there。

 so if the answer is I'm doing this for academic research， totally different price points。

If the answer is you're working for Oracle and you're going to say I'm going to outdo hots buy。

 I'm going to start over cleanslate it and outdo hot to spy。

 you have a different set of choices youre going to make。You're over at Nokia， you're Ericson。

 you want to a better VM for your phone， you get a different set of choices made。

 so go from that level， then come down from there and say where am I going to go from there you'll decide。

 do I have a gender I？If I'm having a jet， and I'm going to have multiple tiers or not。

 am I having an interpreter or not， you should have you must have either an interpreter a jet。

 but you can skip the interpreter if you play the game right decide right now that one because that drives a lot of things that fall up。

Then you know start with the basic I'm going to have a GC or not， if you are going to have a GC。

 it's conservative or exact。And if it's going to be exact， decide concurrent or not。

As opposed to parallel note， there are things in DC that are more straightforward to parallellyzed and less straightforward。

And you know， the other piece is am I going for low pause or high throughput and both is tough。

 tougher than one or the other， but if you're just looking at my cell phone and I want low paws。

 I don't care for high throughput， I got one or two core producing garbage， I can collect one。

I don't need to have a parallel collector。And maybe you want to。

Then with that GC go re barrierrier base， which is an resulted versus white ver。

That completely changes the set of algorithms that are possible。

And make that choice upfront because that's going to drive it as result did it with a re barrierrier。

 which I believe made it much easier to get a low pause thing。

The white bear ones have slightly higher performance。

 and are'm very straightforward to implement a parallel through of collector。

 which is a blocking stop the world but very quick to collect and then go again， but very quick。

 maybe not creating short cell phone conversation。You side where your， as' say， cyber your price。

And that's sort of you know big ticket items I mean you've already said I'm in a virtual machine。

 I'm going to run something that's not machine instructions。

 so am I know I've got a bikecode somehow be nice if you could dictate the bikecodes。

 the white codes， stack oriented because that was a pain in the butt to work around led to a lot of decisions on the interpreter that was painful if you could to define your own bikecodes go to register style bycode。

Then you can make fixed frames that the interpreter can live with and the JI code can also live with。

Instead of this variable frame hack， which led to all kinds of grief with frame adapters。Then again。

 be native code。You're going to live with a calling convention on the nativeative code， if you do。

 you can skip a lot of the frame doctor。That's a lower performance point in general。

 but not always you know some of the DSP guys， D you guys don't have to worry about Vars so they blow it off and they say。

 hey， you know， floats and float registers it's all good， right？So those are kind of。

 I think that's a lesser choice， I think primary upfront。You know。

What's your business reason for doing this， get out of grad school。Go make another。

 go make JavaScript killerller 2。0。Go back。Whatever darner go for my internal core engineering that might go viral and it might not like set myself up to go fast if I want to。

 but start with the low it versions of。And then working to report。Yeah， so the。

There's a lot of stuff in here that's weird interactions with architecture， memory models。

 weird interactions with VOS。How much do you think the OS design choices impacted the VM？

Tice instance。And in ways that were just like the pain in the ass， but at the end of the day。

 it's just as fast and things that like fundamentally change the way you do it。

I might be faster if I had a really trivial Os that just gave me all the cores and。

you talking about OS or you talking about X86 processor choice， O。Okay， so。O has come with， well。

 hardware these days comes with virtual memory protection。It doesn't have to。And DSPs and Ts don't。

So。Ask that question， if you have that， then getting that support out of the OS enabled a bunch of fun games。

Aity to do TLV management， read write block pages， and in case of GC。

 force the TLB to mirror physical memory so that I can hide a bit in a pointer。啊。

Those are things I wanted， things that I wanted to get that didn't get reliable stack point or program counter downS is doing the context switch damn it？

Good right and the answer was mostly， but one time in 100。

000 it would blow and we get a call from the President Deutsche Bank screaming at us said they were not going to move their sun contract for $10 million annually until we root cause what went wrong with this damn thing okay。

呃，哦呃。Getting tons is one of the things I have a little talk I talk about crap had one out of P that I don't have。

嗯。AMi second time accuracy， there are most large Java。That thread， I'm sorry。Web server kind of guys。

 application servers。Have a hidden dependency that。

Sysem do currenthe millities is clock cycle monotonically increasing。So what the hell mean by that。

 meaning on this thread， if I get the current time millase and I store it down in memory。

 that thread will see it be exactly equal to his or greater。They will not be offered even one clock。

But the time from my get it to where this guy can get it passing through memory is probably majored in four or five clocks if it's L1 L2 hits into all handshakes go right。

So those two clock numbers for current time milllies have to be cycleacate on these two cores。

 how are that's done？So in the beginning， that was originally done by Linux going down to some NNTP kernel call guidelines is very expensive。

 then along comes specABB， which as a benchmarkeded current time mill of million times a second。

Holy so that had to get faster so people immediately sort of grabing for solutions how to get that faster and the answer then followed after some quick hacks were done that it broke everybody who was more complicated than inspecting be benchmark because of they didn't expect time to go backwards on them and the breakers were always a weird bad some horrible transactional thing they were trying to accomplish like failed and aborted and died in was our way would help so to get that cycle accurate and to get it right。

There's something totally true to do in OS and's extremely hard to do user land the OS needs have a page which is read only it can write to and no else can but nobody else can read it and just once a millisecond of bumps account Everyone just goes this fixed address and memory。

 loads it damn value out that's your current time you're done so the cost to compute it from a userlan is load。

And it's clockac across the board because the hardware would just make it accurate as it just gets bumped。

 so it's just like there's a trivial fix nail issue。

The thing that people did is they went for the X86。Re TSE counter registerister。

 which in beginning was not clock cycle after between two different cores and so you would load up this way and do it with that way and they'd get off by a bunch and we tried that for a milliseconds。

 but it was all over the map， so it didn't spec that now oftime would use that and it will be screwed up the next76 guy where it was monotonically the same except when hardware heat throttling kicked in and they would slow us score down because it was either looking idle or it was too hot but they wouldn't slow them all down and then they get off from each other again which just as bad as before。

And then it was not clock cycle lacr on a multicore box。

 it's multi socket box because these two guys put' in handshake and keep it in sink as they went。

 assuming we did do it as well and pay a big price for that。

 but it was totally worth it because if you could rely on that damn thing being clock cycleacr across the box。

 they do it so much easier。嗯。Like that out of the OS as I mentioned， I did my stacks。

 I aligned them on to make boundaries so that I could use a fat TLB to cover it or I could use 4KtLBs to protect ends for overflow and underflow protection and an overflow I would have to free up a page and let you run on a little while to hit a safe point without falling off the next page and a low memory was always readable because that was my thread level storage and I had a lot of things were fiddling with thread level storage in regular bases turns out we have a very high speed high quality profilers doing random stack sampling that we jammed those stack sample bits in the low 8K so we move the base stack pointer up little ways for that and that's a ring buffer that just like jammed stack cornerer or stack traces down at high volume and the trick with that one is all profilers that don't do a random stack sample resolve safe pointbased profilers all y exactly renew most。

They all lie in that any time you have a no account。The account profile takes a take one。

But the jet tries very hard to throw out all safe points how to hot small roots because that overhead slows that loop down。

So hot， tight loos don't have safe ones。Ster four， they get no profiling tag。

So you go look at your kit and you run some stupid hot loop。

 you'll get no ticks where you want them the most where you expect to see the most like it just lie and this is a wellknown problem across all you go find academic papers pointed by you have to have real stack sampling then you have to call your stack widelyly which eventually got straight out of the z and sun still had issues and then you had to record those stack traces somewhere that our profiling thread I would scrape that buffer hall off to side hang onto it and then a profile or tool could go cool mountain。

嗯。I'mly with TLP is around stacks。What else am I getting out of OS that I cared for that matter？Oh。

 fair， last did you use Z。On the original little harbor box， it was all from scratch。

 we got some core Linux designers in a couple of them were actually really。

Did you care what you wanted about Oh yeah， yeah。唔有可能有咗啊。

AndThen we went push some of that back into the red hat distro and some of that we figured out how to do without。

 or we just paid the price。嗯。Like the safe point game was done in hardware on his Z side for free and we just paid the price on X6。

 but it's all fattened wildly out of order and cash flow L1 Ca hit is essentially free because you're blocked waiting on some other missed domain memory somewhere down the line you running cash missed the cash。

出来我说。那。嗯。I go pull that talk out， I can do that here。

And we go what other things are you doing even OS land here， even OS stuff？F。

 I'm just thinking about like model mismat。The model the OS thinks about because the OS is abstracting the hardware。

 giving you some view of the hardware， is that is there a fundamental mismatch between that and what you want to do or because all these are sort of like little things that could conceivably be embedded in any sort of OS right none of these are except that exposing that。

The memory virtual memory stuff， most of them are not really fundamental to an OS。Itsile like little。

No so I want to run， I mean I've lived with this classic OSss for 20 years， right。

 so we all kind of worked out how it fits in that model。You。

 what would you do differently that you might think would be turntable and something useful？

Out of the OS， so the abstraction I don't need can't use。

Hardware bits because it's Java and that's the mantra as you're going to run everywhere。あ个去哪。

Possible to go there if you did say I'll let you scribble with the hardware bits but in a way that's safe for writing program so I still want virtual memory I always level protection that whatever stupid thing I do。

 I don't bring the box down。If you're willing to give them on that。

 then there's some different games you want to play， you actually went peak and poke operators。

 some people would write device drivers and do。啊。If you're not going to give them a that。

 but you had some abstraction for handing out。You know， low level things。

 I don't know what you would do that probably fit into what's in。know what you can do now in a VM。

 I'm looking for interesting things， so bigger ticket items， threats。At fairwise。

It' still on threads， still on OS level protection。

Oh threat priorities that's a good one that's on my list so you can pull it on Linux has no threat priorities unless you're root and no sane IT guy will let you sell anything as rude。

So there're under no threat priorities so you can't tell the jet to run at a higher priority than the nonje threads so if the benchmark launches  a00 threads on your eightway box and they all do something stupid really fast in the interpreter and they all flip the counter at once and they say go jet there's 1001 threads won the jet the rest of them all running the interpreter waiting for the jetit to complete it never gets a fly cycle。

So he never actually getss code， so he run an interpreter the entire time。So， you know。

 you want right priorities within a JBM to do support routine so concurrent Gc only works if you actually have。

You know CPU cycles spare for the GC to run same as the jet so those guys VM support routine went around the higher priority than Javava thread and then the Javava threads went't actually on prairies within themselves and they don't have any mechanism for that other than whacking the whole Vm up or down with nice you know if they whack it with nice they lose to the other VM or mice wheels running on the same box or the Hadoop whatever the hell right。

They can't get it。Sideway， so that was a Linux fail and you don't have the threat priority。转话这边了。

现在这点。So so with like so managing and Z and like custom hardware where they added their own instructions so how does that like how does that compare to like something where like you have an Intel chip that's like highly optimized and like have lots of research and time put into it versus like a custom ship right exactly so that's the azole thing and I was at at that company for a long time it was really fun and I did it but it was sort of doom。

啊。When the chip first came out， it had 24 cores when the next 86 had two。

 and they were four times slower and you had 24 of them。

 so the end result was like hugely faster than the next86。

 we could stack them in a box up to 16 sockets。So we would have a box that was 100 hum faster than where you get out of next to be6。

 but each thread was four times as slow。Turns out that that programming model is hard to do。

 even with Java doing all the good things he did with threateninging and。Concurrent library。

 this and that， but it was hard for people to write。Parallel at that level scale。

 unless it was very regular supercomputer style parallel， your regular a at that scale is different。

So， you know， it was too narrow a model where it really shine。嗯。

The thing that it did well was it around GC and jtting in the background of all those cores and it really。

 at that time the GC performance was unheard of， we would have hundreds of gigabytes of heat with tens of gigs of second allocation and take no pause longer than a few milliseconds。

嗯。And that was just completely well beyond when you can get out of N 66 and so we sold people who needed that kind of GC performance and there are a couple of market spaces where。

Retail Ha and web fixed services， coals and prizees。Walmart。

 anyone who's got new targets got to have web face。

 they're selling Black Friday hits and they're load spikes to the roof。

And the zooboxers just have enough extra threads， it's all done the thread pool stuff。

 that would all just scale up endlessly and not pause。

And other solutions would typically go black on them during their peak load time， crash on the load。

 whatever， and they would lose some huge amount of money so we talked to with people about their amount of sales and some of these companies were selling like half their annual sales came on Black Friday weekend。

So that they would， you know their $500 million your company $250 million comes out in one weekend。

 so if their server went down that weekend they were just like。啊And and。We sold them。

 but there're not that many of those guys。So it' was just too narrow。嗯。We got it faster。

 but not as fast as X86 got faster。And then everyone fought multiple cores and we were sort of forerunners and took a lot of arrows in the back。

That the next guys have next6 to step over bodies it。And went on and said， oh。

 that's how you do that， okay。That bombs hard， we won't do that one and oh。

 you can solve this one this way and they learn and we took the boat。啊。Yeah， like I said， it was fun。

 I'm glad I did it。W again。呃 right。Theどさかて。Yeah， I like to has anybody done that is I don't think it could be。

No， you went't cashable， cash was always on the way。

Because when the hardware takes the right from the OS。The OS updates it by writing it。

 the heart will just invalidate the caches and reload assuming。YeahYeah， yeah。

 in the way the hardware normally does， like everyone will see this version or they'll see the next plus one version has。

We asked for it and I don't think we got it， the Linux get time of day clock got better。

 it's currently similar， they have a series of words that you have to read twice to see that they don't update atically。

 you read them once， then you read them a second time if it didn't change。

 then you got an atomic snapshot then you compute current time notice map。

With some ads and somemobilizing divides， it's not too bad， so it's 20。

 40 clock cycles instead of one。那这个。I mean， I think that's what happened to that where it didn't matter enough。

To bother a Linux kernel team Mike screw with it。But they went to that version。

 they didn't have it when we started， they went to that version little somewhere longer。

 but they were trying to hit。Linux normal， whatever OSC time or whatever the damp thing is there's some structure that you get。

 and that structure was exactly the one C programs expect。

 so the go loaded call was all in line by the C compilers do load these for， compare again。

 they're good I'm done。Right。嗯。A lot of different types being in your slides。It's only time there is。

Do you foresee a future where？A pure message grade model。No， it's all the street I right here。

Because you can't do everything you can， and in particular you can't go implement your actors and actors。

 just go selfho yourself， right？嗯。I have a very different coding style I use when I'm looking for high performance style。

And I go to state machine coding。I didn't talk about that here at all。

 but it is clearly the you know ball walls fastest way to go if you can handle the sort of complexity and don' many tools to help。

 so kind of stocks I always cant manage it。But so I'm not playing it's for everyone。

 but it's how I implement all kinds of fun games under of the hood of VMs。啊没有 do a lot of that。

We've got to click like non blocklocking hash mapap。

 that hash map is linearly scalable to roughly the0 cores the beta Zboxs had with any ratio of reads and write。

Which is completely not true of all whole other hash map， it's a concurrent hash map。

 but it's completely linearly scalable for a000 cores and I'd build more if I had more and I will retain linear variability。

That's a state machineing program。I have the current survival act is doing cluster computing。

 we have a Java memory model that cash coherent across a cluster of machines using massive passenger machines says。

 are you guys that number。啊。But we're as fast as anyone out there with a distributed key value store。

And also were exact consistency。Which we're doing with distinguish model of the hood。

So I basically had a long talk with Kevin O' Mil。Who's a hardware cache designer did az's caches on their allway machine did signs and related caches for their score 23。

 and don't want to understand about hardware cache models。

S machine cash flow hands a hardware style protocol。

As a consequence of a distribute key value your store。As fast as the fastest I out there。

 but the exact consistency as well。We're not selling it， it's all the resources for you go get。

that state chamber so it's a different coding style what I'm doing for what I've built with those tools is Ive built a map use framework which programmers write stuff in an obviously parallel way for data sets that are massive。

嗯。and have an obvious data of parallelism built into them。

 and they just need a map reduced paradigm that's sort of faster than the standard review points。

 so the theoretically cleaned， nice and very pretty， pure Javava。

 you can write almost anything you want in Javava and I'll make it parallel distributed。

 but it's because it's a map reduced paradigm。That's sort of an easy way to get big。Rightか。

I'm using make that run， I'm using Doby's Fo， which is another variant of a parallel programming model and has a little more complexity to it。

And having said that， I'll go to the next path and say we're using the countercomp version of F joining。

 which is essentially a accumulationnu plastic solid， no JS。啊。

And I would love to have more support for that in language because I think that is a way that will let you build allher your multis cohersency things on top of other stuff。

 code to it directly and be sort of a reasonable paradigm for talking about something when you can't do essentially bulking as parallel the map uses bulking。

It's do the thing on everybody and you're done， do next them on everybody。啊。

If you want more complexity than that。There's actors as an obvious choice and Forbe join with continuation passing style is another different paradigm that's higher performance。

Actor and I don't claim it's better or worseit。上。Of course。I guys correct。

of questions I'll be here for a while。So I mean， it sounded like with your 100 core system or you were talking a lot about how like the OS would come in and lighten our some threads。

 so why didn't you explore like one thread？And then just do like a。Green thread to like。

Instead of we wereing hotpot， which didn't do green threads anymore。So we use thosesps。

But the OS was always to play with so it was a very lightweight credit model in the actual OS。

 it wasn't Linux right， but I mean like you were depending on the OS to interrupt your threads。

 you could have had like dreamed like what cooperative must。Or you have to be perfect in yourgenic。

 so it's especially in the next 86， you have fewer quartersers， you have lots of run balls。

 you have to be fair， what do you do to make somebody else run when this guy's not getting it up？

How do you get them to give it up well， if you don't do cooperative self suspension。

 you have to preempt them and that requires an OS。has to be somebody who actually has the rights to tell another friend stop now。

 you can't let alone， get off that call， that's for somebody else。So that's an OS。

 but we mostly define when OSS does that in virtual manner。啊。

The cooperative thing was as statistically cool cancer， but not a perfect answer。

So statistically good meant nearly always on my 100，000 run of rolls。

 all of them were stopped at a safe point so I could crawl our stacks and screw with them with Gs。

 almost always， but not 100。To be perfect， I would have to have the time between when a polling point was passed and when the time quantum ran out and the OS had to say you're being a bad boy I'm going to kick you had to not be long。

 or else you wouldn't get off the car in timely fashion and somebody who died。

So that one would require the jet to perfectly put where safe points went。Instead。

 the G went for the minimal number of safe points that covered all paths。

And that meant there was a time from when one state went the next that was not being tracked by the jet and could get fairly large。

I said there are no safe points in hot loops。啊。But when that happened， he would unroll in the jam。

 but you would still get many thousands of instructions then between the enrolled inner hot loop before he'd exit that。

 take a safe point check and go right back in。And so was that too long， I don't know？

If it was too long， if you had to restarting the La runo safefe point or to do a TC。

 but statistically， it didn't have another lot。嗯。You routinely ran into native code that was going to run for a long time。

 we go to B routineine， it's going make 2 line， it's going to be here for minutes。

Okay you want that core back to be fair， you must preemp it， there's no cooperation there。

 I went grab to some Forchan library I compile with a Forhand my library。

 but it is not got no safe points in it right so I just have to have preemption out of the illness。

Thank you again。O you stick。Or if you want to check head often。Until I find。就是。All right。こは。

45 minutes to get back on sort of the normal pace of things。

 it's like you've got the whole course compress into 90 minutes Okay。

 so today I'm going to start on optimization stuff。

And it's going to run for a good few hours so we'll only get a start on it today there'll be more going next week and a lot of this should fill out much of the terminology that Cliff used in this talk so if there are things there that you found。

Mysifying hopefully they'll be less mystifying by it ownone。Okay。

 so I'm going to start by talking about dispatch optimizations。

 mainly because the early history of VMs was intimately tied with dynamic object oriented languages。

And the dominant。Performance feature there， the thing the biggest impediment to performance is dispatch。

And so there was a lot of effort。Paage to making them fast。

 which it turns out laid the ground for work that followed later。

 which is probably even more significant。The merely dispatch optimization。

 but if you've got an objector language， you're doing dynamic dispatch。

So the first thing you have to do is make that stuff fast or ideally remove it entirely before you can move onto the next thing。

 so we'll start there。Inline caches you've already read about and heard about。

 I'm just going to give you a recap。啊哦。Just to make sure that that's all clear because that will lay the groundwork for the generalization of inline caches and then the use of those generalized structures to gather profile information。

 which is how we get to adaptive optimization， which will be next week。Okay， so the ideas。

20 odd30 odd years old and。You knowIt works on this observation that we use the last implication of a method called as the predictor for the next and in the original Dodge Sch technique you embed that prediction in the code by calling the thing that we called last time so I've got the movie version of inline caches here donate animation which hopefully will make everything very。

Very we'll run this twice， one in a slightly simplified form， and then I'll show you。whistle。Okay。

 so we start off with the coal site for the imvocation that we're trying to optimize。

 so that's you know PF and Java or P。In small talk itself， I assume now a compiler is put。

The target of the call in a register and it's in this case has put the name of the thing we're calling in another register so the F is the name or symbol or string or reference to those and in the initial case when the compiler generates code it just binds the site to a generalize lookup routine so the first time through we call lookup routine this is our program caches of the red thing that's going to move through our code。

Hop over to look up and then what do we do when we get there first thing we do is we find the thing that we're actually going to call。

 and that's obviously based on the semantics of the language and。Algorithms， so that's a call off。

And that will result in an end method pointer to the thing that we're going to call if necessary generating the code for that method if it hasn't been generated before。

Along the way so we now have our end method is the thing we want to call and the next step in the lookup is that we patch the call site to link to the entry point of this method so that arrow that used to call lookup now points to the entry point of the end method and we've had to change the address in the call sequence to point to that and now having done the patch we can jump to the end methods and now we jump in a little bit after the beginning to something called the verified entry point which bypasses the check that's part of theline cache so you'll see basically I'm writing kind of mockassesemble of there two labels。

Entry point and verified entry point， usually there's a fixed offset between those two so it's easy。

So we end up now row。Now， next time we run through， we hit the call site we're up here。

We call down and we go into the regular entry point and the regular entry point is going to check whether the class of the receiver that we've been given in the register is the same as the class of this code。

 which in this case is P。And if it isn't， then we go back to running the lookup。

 otherwise we carry on running the rest of the end so let's assume that this time misses and we go back to lookup。

Lookup's going to use the name。嗯。And the receiver type to generate a new method。发 the new message。

It's going to patch。Un relabeled coal and then jump to the very fine entry point。Basically。

 the movie runs over and over again with as many arrows and targets as there are different core targets。

Now as I said was a slight glossing over there in the way I structured it was that I was passing the name of the thing we were calling in one of the registers well that's only needed by lookup once you're actually running you don't meet the name anymore and so there's a common trick that's applied here which is to reuse the register which we use to pass the name the first time to pass the class or some of key that we're going to use for lookup the next time around and an easy way to do that is just reserve a slot at the call site a data slot which contains the lookup key and just load that on the way into the call so let's have a look at the。

嗯。The way it looks now so in this case we have。Call site。

 after the call to look up there's a data slot which the return sequence for the end method will have to hop over because there's not an instruction and there's just a data word。

And when we start that data slot points to the name of the thing we're trying to call。

 so the calling sequence loads that thing into a register and then calls lookup。

 lookup now has the name of thing in R and it has the receiver register by some convention containing the thing that we're invoking the methadone。

 it's now going to use that name。And。Data path to do the lookup of the code generation as before。

It's going to patch in this case the call and it's going to patch the call to point to the end method which is this part。

 but it's also going to write the data word into the X slot。

 which points now to the class of the type that this method came from so next time around if it matches the exact same class then we're done we have a hit and if it doesn't we have a miss so does the patch jumps to the verified entry point and off we go next time through。

 if we call we get to the entry point， we did the test of the class which is usually a single load off the receiver register if that doesn't match P then we call into a little prolo into the lookup routine which is going to。

Find the name of the method that we're trying to look up and put that in the register so that now the lookup routine could be reused as it was before。

So that's just a little prologue that we。That adds a little bit of code。the beginning。

 so we go here now， we finding the name of the caller is pretty straightforward because we just came from a method who knows its own name that's somewhere in the data structure and then we put that in our。

We find the end method generated。Necessary。GoAnd do the patch。The receiver。Tight or receive a class。

Always good。Hopefully straightforward。Okay， so the effectiveness was a question。

I always thought to talk about that。This scheme works well if and only if we're not bo between lots of methods all the time right and it's just an observation of most people's programming style that doesn't happen often most calls are monomorphic。

Meaning that they call the same thing every time or they're occasionally polymo effect that they call a different thing。

 but the change isn't very often。However， you do find， you know。

 that's not the case always and we'll look at the solution to that。In the next technique。

 now the polymorphism when it oscillates between two or more sides。

 obviously the thing that matters is how often the oscillation takes place。

 not how often the calls are， so if you have something that ping pongs between two targets and alternates。

 that's going to be formed very， very differently from the program which you call the first guy for half the programming than the second。

The other half is you've only got one change if you want cash there whereas it's the other one you've got a change for every call。

It used to be the accepted wisdom that this structure was faster。

Then a VT lookup and I think Cliff just said that I'm not sure that's true anymore。

You'd have to really， I haven't seen any studies done on contemporary hardware to see what the branch predictors like。

 if you have a good branch target buffer here， there's no reason it couldn't just predict where that call is going。

嗯。In a V table and do just as well and sort of half the loads。fiure it out afterwards and sync out。

 but for the longest time this was faster than doing the VTable lookup so you could actually get dynamic languages doing calls faster than they were doing。

Vual causes。嗯。And as you just saw， code patching， especially in the concurrent environment。

 is tricky。I'm not going to go down that particular rat hole here if we have time to load something。

We'll discuss it or you could you know watch the video of collecting it slowing down。

And what he said about that because that that's basically the gist of it is， you know。

 there's all of this detail like you have to get right。

And the hardwarewood generally is not making it。So the generalization of this technique is the polymorphic inline cache。

 and that's to deal with the cases where you've got genuine polymorphism in。

On the call side and the inline cash is performing very badly because you pin oning between two different end methods。

 which is really slow。And that happens in real programs so if you imagine inner a loop of a drawing program and it's drawing stuff on the screen。

 you know you have circles and squares and text and arcs and stuff well each of those is going to be a different method and they're coming sort of random order on the screen you you can't tell the user please draw the circles first and then draw your arc second and you'll find it' faster that doesn't really work so so the original inception of this technique was to deal with that performance problem but you'll see next week that it actually gives us a solution to a completely different problem。

As well as we go along so the idea here is that we're going to do the single in line cash thing to begin with。

Here's the picture before the first call where we have the bound to the looker routine。

 you know we call the looker routine that reds us。To the end method that's found first time around。

 but then when't we miss the second time around？Instead we generate a little piece of code。

 a dynamically generated stone which is going to do two type tests。

 it's going to test against the first thing we saw and if it was that then it's going to branch to that end method and then it's going to test against the second thing we saw and if it's that it's going to branch to that method and if it's neither of those two then we go to the mis case and do the full lookup again and if we go down the mis case and do the full lookup again we generate another one of these things and extend it usually can't extend them in place because of the way memory is fragmented and stuff so usually you make a new one and you patch the call。

The point to the new one and this kind of just goes on so you I got bored growing arrow so this one I drew box didn't all the arrow I think。

But you can see how this kind of generalizes so that sort of deals with get to the obvious question which is。

 well how far do you go with this do you just keep making this bigger and bigger and bigger and bigger well now you don't really want to do that。

You've got some choices here， you've got once you reach some kind of predehoine size。

 you want to switch to a different strategy in the literature that prehoin sizes is known as megamorphism。

 you know you've got many， many different core targets and they're actually actively being used。

You can do a couple of things one is you could just buy into a more generalized routine that has a non site specific behavior。

 so a global method cache， we saw that you know， four or five weeks ago， a simple hash table。

Based on the receiver types and the selectors。There's all sorts of other tweaks too as the thing grows。

 you know linear test might not be the optimal sequence。

 you can reorder the tests as you generate the new stuff to put the most frequent pace of the beginning。

 if you have frequency information we'll see how you get that next week and you can even sort of go to a logarithmic search structure by doing a branch injury if you really want to and that gives you a bit more scale。

In the technique before you have to fall back。小啊。To a V table。 And just to remind you。

 here was the picture from a few weeks ago of the V table structure。

 and the idea here is that we have。For each class。A fixed offset from the class pointer there's a list of entry points and so the sequence for a call here is given this pointer in your hand you get with associated class and you do an index based on some coloring table that was computer compile time and then you call off。

To the targeting method， this works well in a statically type language。

 we can't do it in a dynamically type language because you don't know the set of things that might be called。

啊。So。So this is a good fallback。For a statically typed system。 and as Cliff said， even in hotspot。

 which is statically tight， only does this after they。

The inline caches have failed to be effective and it uses the inline caches and the polymorphic inline caches to gather the type information and the profile information it needs for the optimizing compilation。

 we'll see how that works next week。Okay， so that's。One technique。For optimizing calls。

 another completely different one is to deal with。The problem of primitive types in the dynamic language so you've got this problem that。

 you know you see an A plus B and the A plus B might be an integer ad。

 but you don't know because you've got no type of information whether it's going to be shrink of catnation or integer ad or somewhat a completely different thing。

 but integer ads are a cheap and so you want to make that case quick when it is an integer ad if you possibly can。

And so the solution is to speculate in the compilation。

 you kind of assume that the overhead for doing the ad case is very low。

 you guess that it's going to be that one and you test that guess and if it isn't then you do the more general ones so you've made the more general case a little bit slower。

 but only a couple of instructions slower and you've made the ads a lot quicker by not doing the full。

A full lookup even though。Inline cash is kind of punitive to do addition by our coal women rights。

So here's an example， I sos as simple equals be。When generating code that kind of looks like this。

 this is sort of pseudo， C and theemer blended together more sea light。

So we're going to test whether our two operas are tagged integers and if we are。

 we just do the addition right there and then and this is older in line in the code and message by the J compiler。

Otherwise， then we do the full general。Dispatch， which might be an inline cache。

 which then has its own fallbacks as you've seen through polymorphic inline caching or global method to look at。

And。You know this was the technique that was done in the Deuts Schiffman system in a small ca。

 there's a bycode that says， I am sending a plus。Okay。

 you don't know that that's going to be an integer plus or the compiler it was it said。

 I think it's probably going to be an integer plus， I'm going to emit this code in line。

To do these tests and the full lookup otherwise。And that's how it's going to work and even though when you browse in the small talk system。

 you could find the source code for the plus operation。

 which meant you give you the illusion that you could change it。

 changing it had no effect because it didn't change what the compiler generateds it。

Compile always generates a this process。So it was kind of beged into the jet that plus was at least on integer is always going to be integer addition we'll see next week how that。

Was generalized in so that course could be anything。

And it would do the right thing when you change that。

But that that's a sort of shortcut that was a reasonable thing to do， you know， in general。

 programmers don't feel。That upset if they call it change what plus does， know some might。

Tough one is you get a faster system and it's relatively tract to build it。

That's a sort of an instance of a more general pattern which we'll see over and over。

 which is fast path slow path design we've seen I've used these terms a lot already。

But just kind of to put them in a picture， you know what we're really doing is we're looking for some feature of our implementation which has a skewed distribution。

 it's not 5050 or if those five choices that arere not all 20% probability something seems to be more likely than the alternatives and what we're going to do is look at the common case and try and make it fast than you know if necessary at the price of making the uncommon case is slower or there's a balance to be added。

So this picture sort depicts that。You know， we're going to make the fast path in line and generate code for it and the slow path be will generate code will probably be a layer line call and that we'll see as a。

Generalizes into a number of tricks。Later on。So the next technique is one that I might have mentioned but we haven't looked at in any detail and that's called customization。

So the idea here is， if you look at a standard compiler， a single a fourran compiler。

 especially something from 20 years ago， it sees a piece of service code。

 it generates a piece of machine code that is its best attempt generating the code for that particular source。

 but there's no reason air priora why you can't generate multiple different instances of the machine code tailored to the prop of the cold site。

 if you really want to， it's just no idea ever did that before。

But once you get into an object oriented language， then it turns out that that's a really good idea。

 it actually gives you a lot of opportunities for optimization that were closed before because of the nature of the language so all we have to do is decide when to do that and and what we're going to customize on to make it work really well and there's a paper from 89 by Dave Vunggar and his student at the time Craig Chas that showed how to do that in the context of self。

 but it's a fairly general approach that works for pretty much every object oriented language so the idea is that within a method in an object oriented language。

 a large fraction of the implications are going to be on self or this they're going to be recursive on that type at least。

But if you look at the way inheritance works on those languages。

 you don't know that type ahead of time， you know the class that the method is embedded in。

 but it could be executing them the context of a descended type， a subclass or something。So。

What we're going to do in this approach is we're going to generate the code for one specific point in the hierarchy and say only applies to that point。

 so if I have a class of a particular flavor， then I'm going to make a method that works only on that and that doesn't work on its subclasses in the past before this paper everybody just reuse the same code in all subclasses because that seemed like the right thing to do but you'll see we gain some。

Optimization， so here's an example suppose do we have an abstract。

Class of 2D points with two concrete subclasses for the polar and Cartesian representation。

 I'm going to use kind of self like notation here。Just because it's concise。

So I have a Cartesian point with a parent's Lo P， a point to the point， which is at the bottom。

 and the Cartesian point has an X and a Y and an R method， which does the。

Pythagan thing to figure out。The hypopotamus。And then the polar point just has a。

R and theta representation but inherits from the same abstract class and in the abstract class。

 in point I've just got one thing which is tell me the length of the hypoten they are。

So what can we get from this well when we first invoke that print thing on a polar point。

 then we know the thing is a polar point and we can generate code in the context of that polar point that assumes。

 for example， that the R is right there and we know the field officer in the object we don't need to go through all of the method dispatches and when we generate the code for the Cartesian point and we know the method that that would have called and just bind into it directly so。

We can generate different methods for the different cases and all we've got to do is make sure we install them in the lookup system such that we never get。

We never get confused， we always call the right method for the right thing and that includes。

 if we extend the class hierarchy later， we don't necessarily can't necessarily reuse the generation codes so for example。

 if you make a descendant，Of the。You know of the polar point when you change art to not be a stored thing。

 but a computed thing， then you can't call the thing that's looking at the stored attribute anymore。

So pictorially， here's the sort of the self like picture of the objects and their methods。

The class of the top。Which has its print R method and the two descendants when we call print R on the。

Cartesian think that instead of doing a lookup to find a R， Well we know R is right there。

 we can determine that and we can just。We could just call it directly or even potentially in line if we really wanted to。

 we'll get to that。In the next part， when we call print R on the polar point that we know R is right there and we know it's a desert slot so we can slow that。

Do a full dispat。 So we've got。We've got a number of advantages here。

 the red things are meant to be kind of end methods they don't really get installed in the objects they're really in the meta system that manages the code cache behind。

So it's more complex than it appears here， but still manageable。

And they're not replacing source methods right their own methods， they're not visible to be。And then。

 when we。We call a from this guy， and again， you can install a copy of that。

In the MacBook class for the Aut teamian appointment knows directly where the slots are。

If be looked at alive but the dispatches are no taxeses。

So you can actually drive this a lot further and we'll see in the after we've got to endlining that you can get a lot of mileage around this。

So the pros of this approach， the pro is that you can eliminate an awful lot of dispats and kind of apply this repeatedly。

And that improves performance， but at the cost of generating more code。

 and the danger is that if you have a large hierarchy with something inherited but not redefined that's used in a large fraction of that hierarchy。

 you can end up with generating an awful lot of costs at the same。

ystem and in fact South was the early version was terrible for this in that graphic environment。

 for example， there's a hierarchy of graphical objects which I think has 100 different types in it。

And so you'd end up after you've been running the environment for a while。

The abstract methods that came from the top of that hierarchy， you know。

 there'd be 100 copies of the machine code and they're all exactly the sand。

Is it we're just applying that？The co generation blinding。anything to say， well， you。

 this actually would be the same piece of code as I thought last time， so why not？

Just share the machine code。Regenerating。It has to be used with a little bit of caution。

So in terms of these inline caches。Roughly what percentage of the L1 cash or maybe LT cash would you dedicate toward coaching？

T the format in terms。嗯。You mean all of the generated code， no， let's say I'm running my interpreter。

I'm generating code。I need to allocate some amount of space in order to。For account。

How large should that cash be？Oh， you mean how much average bid should be made for the generated code well that really depends on your memory footprint and what kind of applications you think。

You know， some systems just say， well， that's a user problem。Pass me to flag。

 tell me how much you want to dedicate which kind is a call pattern because generally speaking users have no idea。

But， you know，10 percent Im a bad number to the。Depends if you're on a very small system。

 it might be half a memory。でされた。Agelizing a really small， relative。But as the system gets bigger。

 usually the data have size。Grow much faster。So by the time he got to two of us。おさ。

The thing that's easy about this is， if you have。Size。这次检常完。It gets full because at that point。

 the system either dies or it has to do some。Fluushing your code or compaction。

 and at that point you can record that fact and say。Maybe next time we want to make it。

I thought there might be some like andable thing that's already been。I can't think of them。

被化 thinking嘅。Okay。So another technique in optimizationim。The pulls from that slow path fast。

Is to identify。That some directions of a branch might be extraordinarily infrequent。

So infrequent that you can do something hideously painful when you go down that path。

You're not going to do it very often if at all， and so an example of this is an exception handler and you might make the assumption that exceptions are exceptional and therefore you're going to penalize the cost of the exception handling to improve the cost of everything。

And so there are a variety of strategies， one is you can just sort of pessimize。

Damn that path relative to the other path， you preferentially allocate registers down the line variables of the other path or make the control flow drop through on the fast path but go out to the line for the slow path。

 that kind of thing。But there's a more drastic technique which is you know just donning compile that code if you think it's never going to run。

 just don't generate the code at all， and instead put in a stub though that's going to call the compiler and say。

 oh， you know， we run， we actually can only it's time to generate code or transition to the interpreter or something down that path。

And if you do that， then。One of the things you find in a system like Small talk of is that they're actually incredibly frequently is uncommon paths in generating code and so having a sequence of instructions and a call and all of that stuff takes a lot of space。

 there's a cheaper way of doing that which is most instruction sets have a single trap instruction。

 and some opportunity to write a user level trap handler that will catch that and often it's like a one word。

One by or two by instruction just pp that in there and then the trap handle I kind of has to figure out what happened to I came in here where did I come from。

 I have a return PC I have to look back at that to figure out which method I was in I to figure out what I was doing at the time that was live。

 restore all of that stuff there's a lot of complexity down that path。

To making that work in a lot of time， but if it's genuinely uncommon。

 then it's probably a way and so the idea is we take our slow path。Fast path diagram only me just。

 you know， chop off。Thatside， right， we're not even going to fall through， we're want to call out。

Into some other world which is going to handle a situation from there and it's not going to fall down to through the merge point and execute the code afterwards and that's really important because now the code after the merge point doesn't have to deal with anything other than。

The conditions that were true there in this path。So you know。

 if you came in here because he thought something was an in， well， name you know。

There's no question there isn't a motive。In one case。

 it was it wasn't one It wasn't maybe know and you consume that。

Throughout the rest of the network and that's also a very powerful optimization technique in combination with the others。

 So here's an example。In a risk type architecture where you're doing an addition on a pair of oops and you want to test。

 you're assuming that both oops are going to be an ink。So in this case。

 I'm assuming two really significant bits of zero， I'm going to do the test and a branch and test and a branch。

And if those kind act that I'm going to。Give the addition， otherwise， I bettert。

And it's up a runtime system at that point to figure out what I should have been doing and do that and you have to you know the compiler when it emits this is going to happen。

Either a ni code or have a convention in which you could figure out where you were and what you were doing at that moment because they're going to be lots of these traps and it could be any one of them that's going get the trap。

So to transition， there's going to be some kind of trampoline and the trap handler is going to have to say okay I'm common trap I came from this place。

 I have to retrieve， you know figure out which method I was in I have to figure out what's line and where it was I have to probably generate a stack frame that looks like an interpret a frame the populate all of those things if you if your J code it's already dealing with a separate stack then a lot of that is already done for you because you're not necessarily executing in a very different environment but if you're having doing register allocation then the values are in registers perhaps and not。

In state locations， and you're going to have to figure that out。

From the bread crumbs that the compiler left behind。啊。

You're also going to have to change the compilers of the continuation of this method。

 if that's the way you're going to run it or generate the whole method with an entry point at this point so you can translate it into it。

 transition into it， or you're running the interpret that's a choice。资标。Okay。

 and the last thing we'll look at today is splitttting。So the idea here is we have branches。

 pair of branches that are both still reasonably likely。

 so we can't eliminate one of them we want to do， but we want to be able to generate code from both of them。

But。They divide the world into cases which are so different that there's no point in having a common piece of code after the merge point。

 we might as well duplicate the code after the merge point and customize it based on the assumption from the test。

So。Looking at the picture， have we have this thing again。

 in this case I've got sort of a below representing the following code and what we're going to do is we're going to duplicate that code。

And customize it based on what we know now from the test。

 So the test says in more variable xs of type T in this case piece of code I consume Xs of type T and just compile with that assumption。

 and in this one I know it's not a type T。A converse case and what you find is if you do this and you apply repeatedly at places where you would do。

 for example， primitive handling， then you can break out the part of the part of the me。

That represents the integer。Interpretation entirely from the part that represents the non integer interpretation and maybe even just uncommon code that helps。

So this is the kind of thing that a compiler will be doing on its IR it making passes over its IR looking for cases like this and then doing the cloning of the subgraphs and the manipulation of them。

 there's a nice example which I'll run through but I don't have time really today to go through it。嗯。

Next week we look at。Kind of an example where we blend all of these within lining and see how far we can。

Calulation using these techniques and then we' look at。

Blending inline caches and picks with counts so that we get。

Profile information and look at T of compilation， that's where we have a second or third level of compilation doing more optimization。

Any questions？So all these automation that you just described？

What are the factors that a compiler takes into account in order to decide whether or not it should do these I so there's two ways doing this when the original customization paper was written and the technique were described initially。

The compiler applied heuristics it said I'm going to guess that it's going to do it this way and I'm going to make this assumption and do a transformation and it would make these repeated assumptions and transformations and if it got it right。

 you won't big time。If you got it wrong。It was hopeless。

 you got was a long compile pause with a piece of code that actually didn't do the right thing when you ran。

You just have to immediately throw it away and generate it again。

What we'll see next week is a framework for putting the decisions in place by gathering。

Tpe and frequency profiles using Canas both in methods and also on inline caches and when you run the code with that in place。

 then you get very accurate profile information and not just frequency information that says I've been here many times but it can take a call site and split it into all of the different type cases that over occurred with basically a histogram of the types and now you have really good information on which to base your inline decisions of your other optimization decisions。

 assuming this is a question you always say that assuming the past is a predictor of the future。

That's always the assumption。I ask for。That's not true。He lives his big time。不大是这样子，我会 look at大。Okay。

这。出す。さされ。written。So last night， you have three weeks to do this one。はね。这个犯罪。

Difficulty is not proportional to。ありが。い。まだな。对。嗯。I did it exhaust。 but I do tell you what。What I use。

听我吗。我把这单。O谢。Ex a screenさ。ね。あじ。You should team up with this guy。No， I already had some more。そ時。也是发还是。

前ま。In't that anything assessed because I probably research。For in chair。いね。Yeah。等日系。美しいだりす。Well。

 but for me， has is。's very。Because it's satisfy I see happening。知道是。然后三个的个调查。😀へ。😊，Never。る。没事。不要开心楚点。

Now now we have like now。为啥？And before。Because once you do this you can find someone else。Yeah。

 we have all these checks。I don't like this micro it's very weeks。It was all that。

AndIt a human drain and be implement。あてます。Yeah that's the future。Although it。Okay。

 so there's two there's two questions first question one are we just simply being a buffer and especially something journalists if we are one of suggestinging value status？

So the answer to that right， but basically if you do this。and there are more places， you have that。

Yeah， next through。No。はいはい。