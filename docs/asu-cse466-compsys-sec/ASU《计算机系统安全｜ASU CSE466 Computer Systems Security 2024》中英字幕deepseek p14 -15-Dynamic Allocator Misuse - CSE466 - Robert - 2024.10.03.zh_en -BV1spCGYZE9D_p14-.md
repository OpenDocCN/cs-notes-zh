# ASU《计算机系统安全｜ASU CSE466 Computer Systems Security 2024》中英字幕deepseek p14 -15-Dynamic Allocator Misuse - CSE466 - Robert - 2024.10.03.zh_en -BV1spCGYZE9D_p14-

I started。I think OBS is actually behaving。Its mind blowing。All right， so today is October 3rd， 2024。

 we're here at ASU in CSU 466， we are just kind of halfway through starting on slash and starting on。

I didn't change the title again， so it's still wrong I just copied the previous one Dane says dynamic heat exploitation。

 but it would be dynamic allocator misuse or heat misuse or I'll leave itate heat exploitation one like all of these are all in know word salad。

All goes to the same place。Memes。啊。I didn't get a whole lot， we never get a whole lot on Thursday。

 it's why Thursday is a good day to show up because we actually talk about things lo。

If you just decided to like randomly Google Heap exploitation on Linux or CT TF Heap on Google。

 I loosely refer to this on Tuesday or alluded to it。 There's a whole lot of stuff behind the T cash。

 Nothing in this module requires it。 Most of the tricks that are。Slides on Twitch， not updating。

I was so confident in OBS for a moment。OBS。II was such a believer。Then it was all。All来。All right。

 so you missed a lot， thank you for mentioning the slides for Buter。

But all of these like more complicated heat mechanisms that interact with various bins and deeper parts of the heat。

 they are known by like some kind of shorthand a lot of them are referred to as house of something so it's like house of lo or house of spirit。

 house of bo and these are。Ways to refer to specific techniques of heat exploitation。

 you don't need any of those for this module so if you are going down which is like interesting and fun to learn about。

 but if you are going down that road thinking that you're going to use it for this module。

 it definitely is not the intended path it wouldn't surprise me if theres some unintended there I't gotten out of my way to stop people from using these things。

 but it's not what you're supposed to do。😡，Twt seems to like it when I say things for them。

 that's pretty awesome。 I know other characterss don't。

If this is your like general take on this course， hey， I go through， get past the checkpoint。

 hit something hard and stop， that's awesome， go for it， that's why the checkpoint's there。

 you know there is something hard that。Right there was some cruises through easy point。

 you got stuck then we go hero and then in general I've noticed that there's just the giant flood of CSE meme if you missed it。

 I gave Sam one of the Ts here liking mean power so。

Go play post beams that make him happy in case I'm missing them。So， soon T。

 so one of the things I've said for several weeks now is that there's going to be like this great amazing extra credit live thing。

It isn't all just me saying useless things on camera here for you。嗯。

Meant it totally as in once you can demo some more and I know。

I'm not sure what you're going for there， Twitch chat。Sa it again， but extra credit stuff。

 at this point there is a PR that's on our public Gitthub that is the implementation of that。

 I'm waiting for other people to like tear it apart and tell me that they hate my code。

If I don't get any like major request for refactor， I'll probably merge it into B evening。

At which point， congratulations， extra credit will be live on the Dojo for hopefully everyone。

But part of me like debugging that is I play with， you I dev on prod as everyone should。

 and so you probably saw me like thanking myself for liking my own memes that weren't memes and that that was just me verifying behavior works from the live Discord and communicates where it should。

そ we said。Next week， next week， meme。Lack of homework will be getting to me to try and leak the stat I still don't know what you're going on about Twitch。

 I'm glad you're up at2 I am working on this with that that is all I have this is why Thursday is awesome。

 all right。Tuesday is we can get up with 30 minutes of slides were ampling or Tuesdays， Thursdays。

 boom， four slides we're done so we're going to get to some demos what are you guys stuck on I haven't looked at where your progress is these are some things I think are useful to talk about。

But is anyone stuck on something in particular？And I guess more importantly。

 have you watched Jann's videos because that was a problem on Tuesday。

 So I like had to reiterate stuff that was kind of already there just to make sure that it wasn' applicable。

 So does anyone have anything specific you want me to try and touch or hit on。

 I have like the super generic， amazing binary that probably has bugs I don't know about that I'm going to use as a prop probably for the rest of this module。

Nobody has anything， I'm just going to get right to it。



![](img/152a346ded6a33fd1b7d095ec8b59a2e_1.png)

哎。So I will start up。Some random challenge here， what are we dynamic？Allocator misuse。



![](img/152a346ded6a33fd1b7d095ec8b59a2e_3.png)

Connect to the old Dojo。One quick moment， I do see a Twitch chat trying someone says there stuff on seven seems the secret key needs to be 10 bytes。

 but puts only outputs eight。So I am still despite what I did on Tuesday I'm not going to like try and solve literal challenges that are there for you what I would say there is puts does not have a restriction of eight bytes when does puts stop printing things to the screen anyone know nullbte because it it prints a string so somehow you are getting a nullbyte after eight which does make sense。

Asking Discord， other people want to help great， okay， somebody says question。

Leaking stack and main address when the heat isn't contiguous。

 so the heat itself is a contiguous region of memory let's start there。All right。

 so I made this amazing binary。It's probably that's large enough。

 it's very similar to what how these challenges where most challenges follow this type of a format where you're presented some type of menu。

 maybe they disguise it as an address book or a phone book。

Something where you can perform these operations， right， you can perform a Maa free， or read。

 write puts， and then I have a couple other options here。

Now the statement on Twitch here was that the heap is not contiguous。The heap itself is contiguous。

 so if I grip。8 out out here and I attach GDPB， so pseudoGDBA 156 I'm now on that binary if we type VM map。

 everything on the heap is located in this region of memory that is called the heap right they may not be right next to each other。

 but they are in fact contiguous。m now， if your issue is that your trunks are not right next to each other。

 well， that has to do with the order of operations that you are performing。So for instance。

 if I were to mallic something。I will put it in slot zero， let's mall something of size。

64 well mallic something again， we'll put it in slot  one of size 64。

 and then we mallic a third thing。Of size 64， that's great now in the order that I free these matters。

If I care about where they are located。Okay， wait， so the statement is they're correcting me。

 they do understand the heap is contiguous。The heap isn't contiguous with the stack wind or main so that is true if we look here。

 the heap itself doesn't is not contiguous with our binary。

 it isn't contiguous with our elephant memory。And the heatap is certainly not contiguous with the stack。

And so you getting a leak of the heap。Only informs you about where things are on the heap， right。

 where the heap is。 if I want to， and I don't believe this is necessary。

 but well we can do it anyway since you're asking if I wanted to know。

Is it possible for me to leak something on the heat that tells me the stack？If you have Jeff。

 I'm sure Poybug has a similar command。嗯。Is that the right command？好普了。Okay， it is the right command。

 I just wasn't in the natural T problem， so Jeff provides a command called scan。

Scan is super helpful what you're looking what you're doing here is you are looking for pointers to a region in a region so when I say scan heat stack it says I'm searching addresses in heap that point to the stack there's nothing in my binary's heap that point to the stack now what if I did the reverse。

😡，The answer is there are pointers。On the stack that point to the heap。

 this doesn't solve your problem。 Twitch chat。 And this makes sense。

 how the behavior of my binary is I'm calling malik。

 I'm storing that pointer in some local variable more than likely， maybe it's a global。

 but in this case， it's。Probably on the stack。 I'd have to look at the source to see where I put it。

 But all of these addresses on the stack hold a pointer to the heap。

 So it is showing me is here's a stack address。 Here is the value that is at that memory。

This is extremely useful if you are trying to the terminology typically used。

 there's pivoting around memory because you have those contiguous blocks of memory。

 And so if the only thing I can leak is heat stuff， well can I。Let's scan the heap for。

Something that points to a dot out now why did I say a dot out why didn't I say elf so scan is actually not that fancy of the like complicated of a tool What it's doing here is it's preing the names over here on the right hand side and so when I say a dot out it's anything over here that has the string a dot out。

that's what it's searching for， you can pass literal address ranges。To scan as well。

 And there are cases where you may want to do that。 I don't believe that's needed in this module。

 So the。We were able on my example binary， if I can leak stuff on the heap。

 I couldn't get a stack leak in its current state， Maybe I can perform more operations and that would change。

But what I can get in the current state is I can scan the heap for。Anything。

That is in this range right that's contiguous with the binary itself and we see right now on the heat and I haven't done anything like particularly crazy right I just malled a couple things there are addresses on the heat that hold coins into my elf。

I don't know the specifics of your challenge here， Twitch。

 but does that help you as far as what you're thinking about there？Give it a moment。everyone。

Does this make sense to everyone here or what scan's doing？所以。All right， I got nothing from Twitch。

 or it's like the world's longest delay。Sweet。So I mallked three things here in 01 and  two。

 they're all size 64， if I care about the proximity of the next to each other。

 the order that I three and Malic matters。That the heap is actually deterministic。

People don't realize that at first glance。Now the heat may be based somewhere arbitrarily due to ASLR。

 but the distance between the first 64 byte allocation and the second 64 byte allocation is known。

 and so if you have any series of actions series of Mals and trees，😡。

You can deterministically say the 50th Malik is going to be so far away from the 130th Malik。

 assuming you know all of the operations。It's just a matter of getting to that state that you are trying to analyze and then examining in GDP or using something like Ltrace。

hOn the point of GDP， I've malled three things and I don't really care that they've been malled。

One of the things that I showed was heat chunks and it gives us this。

 pretty output of where these trunks are located in memory。And that's great。

 but what if I want to have a different perspective。

 I want to make sense of what this looks like Well， we can use tools that we already know so。

I can say examine。How many do I want eight？8ight for 64， let's do 10。

 let's do let's do 14 examine 14 giant hes and this pointer that I got right here。

 D1 AC0 was my first allocation。All right， it's not particularly interesting right because we haven't put it in there。

 we just ask for memory。Let's read into index zero， let's read eight bytes， let's put some A's， 1。

 two，3，4， five， six。Can I count one， two， three， four， five， six， seven， eight？I'm going to hit C D。

 one thing to be aware of in this case it was 8 and8 so it wouldn't have mattered if I， for instance。

 put 20 and then when I'm interacting with the challenge， I use send line or if I'm on the terminal。

 I hit enter what's going to happen。It's going to put that hex OA。

 it's going to put that new line character that may or may not impact。What happens？

In my play binary here， I have puts， so I could puts。Index zero。我嘅诶诶诶。Why。

 because there's a terminating Noll byte to go back to what Twitch said。

 What happens if I instead write from index 0 and I write， I don't know，100 bytes。Okay。

 so I didn't have a new line， so we just， here's my A's。There's this queue here。

 And then this is the help text。 It didn't give me a new line。 makes sense。

 There's no new line there when we did， right。So far， not super interesting。

Whatever happens if I read an index one， let's read in again， eight bytes， let's put BB， B， B， B， B。

 B， B， B， B。Okay， and then let's do that same thing where we write out from index zero and let's do 100 bytes。

 so they don't have any idea what we think we might see any guesses。And why。Nothing cool， so we see。

 we get that queue again。And then we see the bees。What happened。What did I do？Why do I see the bees？

I put the bees in index。The heat allocation on next one。Yes。😊，Tictures don no like。

So if the statement for which was， is it because there's no no light between them？

That's a good theory， right， and if I was using puts。We see that there is。Theエスた。

Puts stops at a noll light。But when I use right。this may seem backwards。

 right is literally displaying it to the output because it's performing the right cisco read is reading into memory。

So it's writing to the allocation when I call read。Deal with it。But if I call right。On index zero。

 it ask for a size because right doesn't care about this being a string。

 right doesn't care about what the values of these bytes are， Wright just says。

 giveive me a number and I'm going to just throw those bytes to the screen to stand out。

And so when I say， write， 100。I'm writing 100 bytes starting at my first allocation。

My first allocation was at 1C0， which is this place right here。And in my he chunks output。

 we see 6161，6161， what is that？😡，诶。And then there's nullbittes， there just happen to be nullbytes。

 it's not like I said it to be nullbittes。And then what is after？That trunk in memory。

 So this is my index 0。 this is my index 1。 and engines 1 B0。 It's right after it。

 right It's 64 plus 16。 What is that 70，80。 it's 80 bytes ahead。 And so when I say right 100 bytes。

 I'm starting from this location or this location。 We see all of these A'。

 It actually is writing out all these no bytes， but the noll bytes don't display my terminal So it's kind of a noaw。

And then we keep writing bytes into until we are writing bytes from the second application。

 despite me printing out from the first memory address， does that make sense？Yes， okay。

 so this is like the read equivalent of a buffer overflow， right。

 it's an overread and we can use an overread to read information from other chunks right it is a particular interesting right now because the values that are on these trunks and that are being used are user values right these chunks have been allocated。

What's way more fun is if we do the same thing。But we do it on free chunks， so let's free index one。

And then let's write from index zero。So we're freeing the one that's ahead。

 we're going to write from the one that's earlier， we're doing that exact same thing。

 and I'm going to write out 100 bytes。But now you get something a little bit different。

We still get A， we still got this Q， but now I've got squiggly C。Where did that come from。

 what is it？Why did squiggley see up here there？I put b b， b， b， b。In fact， my bees are gone。

Wherehy are my bees guy？All I did was I malic to put my bees there， I freed that bad boy。

And just to show that this isn't like a trick， I should be able to， for instance， write from index1。

 write my eight bytes， this should be my eight Bs。What来。How are these trunks used when they're free？

This is what Y's whole video and why we draw pretty pictures。

So the trunks are reused when they're freed。To be to store metadata。So right now I have two trunks。

Technly of three， but there's only two that matter here。We have B， which has been freed， we have A。

Which is right here a currently has。A bunch of A's in it。B has been freed。

 What happens when I free a Trump？これでこて。There's two things ahead， well， there's a next pointer。

What's the value of the next pointer if I freed this？it's the only allocation。What's it？No， right。

 we looked at this in GDP。When we had heat bins。And what we see is here is my bee trunk that I free。

 it's chilling on the Tc， it's the only thing in that Tc bin， so it next point it has to be no。

So what happened when I freed it is my bees， finally had eight。Well。

 that memory location is now being used for the next。So he gotten olded out。What other metadata？

I short on a chunk。This is the critical piece， right so there's this next pointer and B is where the beginning of the allocation is。

And then this is just kind of a whatever， this isn't used。In。That this part isn't used in。

Tcast for assemblyly linked lists。Maybe that shows up。

It doesn't say whatever all right I wrote whatever after next， well what is before the next pointer？

ではい？Previous size and size。All right， what's the order of those things？ユエさ。Okay。

 so we're saying previous size。And then size。Okay。That makes some sense。

 that's how this knows that this is how many bites。We can examine that。In G， I could examine。

 for instance， for giant Hex at that address and we'll go minus 10。What do I say？I see。But， this is。

My backwards here， where's my pointer， B B10？B 10， so that's my next pointer。That would be my。

I feel like it's previous size， isn't it？So let' let's free another one。

 let's take a look here it makes sense that this is a five because these are all chunks that are allocated against 60。

 64， which is hex 40 and 10， the Trump size is 50。 The question is is this size or pre size？

You're saying size， so my pre size is。J， why is it currently zero？There was nothing。Well。

 there's something in Tcash。There's this trunk。Okay， let's free index zero。

That's the thing that was before it in memory。嗯看。And then we will heat bins。I do， in fact。

 have two or three trunks。This is my first one， so if I examine four giant hacks。At this location。

-10。That's my first one。And then my second one was the same thing， except it's D1。B10。So。

We really just have this one guy。For these quick， singly linked lists。

Its why does this 51 and not 50？Okay， so the。Least significant， I want to say four bits。

 but we can envision it as the whole nibble。Is used for flags， which is what was said here in class。

That's how when we say heap。Oh we have it right there He bins we see previous in use is emmaped non main Areta right these are。

Things that can be flagged for a particular chart。Fortunately， if we're dealing with the Tc。

Everything is going to look like this。Everything will be markeded。Um。

 and not everything will be marked previous in years。

 but the previous assuming the previous came from the TC。ItThe previous will be in use。

 The Tc is a caching layer and as a part of the implementation of that caching layer， this。

Everything that's in the TCash is a lie and it is marked as in use。So the reason that。

Both of these or this guy， B10， has previous in use is because the trunk before it。In memory。

 like in physical proximity to each other is this one which is in the Tc。

 so if things are in the TC they are considered in use。😡。

Which is counterintuitive because they are actually being used by the probe。

So we have this metadata that we can corrupt。Or that we could at least leak so if I wanted a heap leak。

Can I do my right trick？Where did I had。Where was my garbage。Where I had the squiggle。

 I'd like sququiiggle C。 You guys remember that。 Where's sququiiggle C， Squiiggle C here。

 What do you think that is being leaked out。So I started writing。From。

Or from this location right here。And then this was a。I was started from waiting here。

And then we read through this。What does my squiggle see？Let's just do it again。Its Malik back。

Index zero。I have to let G set this guy free。We mallic that back， so now I have it。

We will read in to index 0， A8 bytes， we'll give it a。Hey， give to bunch of as。Okay。

 and then I will write out from index zero and we'll do 100 bytes again。Okay， so I get these A's。

 which makes sense， I put them there， I get this Q， we still't figure out what this Q is。

 we get squiggle C， Q， squiggle C， what are these？Well， this was the address I'm writing from。

So let's examine like 20 giant hecks from that location， this is what I'm pretty。

These are the bites we got a suggestion here。他是。Data there so be the Q Q I actually don't know Q off hand。

 but that's okay， it's a good theory， So the statement was hey is Q x 51。

And it turns out if we consult the ASI table here， Q is right here， it is hex 51。

 so the cu that was being displayed to us from our overread。Was the metadata？Right here。

So what do you think the Squiiggle C is？The rest of these are no bikes， we said no bites。

 at least when rightright puts it to the terminal here is basically a noob， right？

So we're seeing the printable characters of this address。

So I could use this to leak out a heap address。哎。What else could I do with that？This is。

What are you asking？Or what are you saying？あ八。This part of。Okay， so the statement。

 this is conflating terms， I'm going to try and deconflate them。

 the statement from the class here for Twitch was the memory that I'm looking at that isn't in the Tc that's in the heat。

😡，Everything that is in the tea cash is in the heap。The Tc itself。If we do。

I think I can do heat bins tea cash to not print out the other garbage I can。So the Tc。

 the TC is just a singly linked list， right， it's not like memory moves from heat to the Tc。😡。

The memory address is always in the heap。When we talk about the TC， this is like a bookkeeping thing。

RightThis is the。Logic of the implementation of how the program like the code that supports and gives us malikin free does the bookkeeping on what is mallik or free。

 but everything that we look at。In memory is going to be in the region of memory that is the heap。

So if we grab this right here， we Vm map it， we see that is in the heat。

 right this is in the heatap if I were to grab this address。That is the first pointer。Or the first。

 let me get this word right， first chunk that is listed in this TCash bin。

 and we were to VM map that address。It is also in the heap right the TA bin is a bookkeeping tracking of what things in the heap are free and what things。

In the heatap are in use。So when things are free， we just make a note of it here in the TC。

 but the memory address will always be in this he region。Unless you're doing like。

Really crazy things。So somebody had the observation here that if I start writing from this memory address。

 we get this cu and then the sququiiggle C is the printable parts of this memory address。😡。

Are these other bytes of the memory address being output？诶什么车子啊诶。Now I don't get to see them。

 but what would I want to do if I wanted to capture that？

You've done you've probably done this already， right。

 we printed out some bitetes in memory corruption and redta in， what did we use？

We just get all pun tools。So let's start writing our do dot Pi。User bin N， Python 3。From Poone。

 importm star。P is process， my thing is8 out out。Okay。

 now one of the things that is a common gacha is do I send or do I send line people still are not like quite sure。

Which they should use and why？Does anyone have a clear way of explaining why I should use one or the other？

Or is it just try it and see if it breaks？that's all it does right it's not like send line is a mystery as far as what it does。

 the question is which one should I use to talk to this program why？It takes one。

We have to enter a new life for that input to be。Processed by。Okay。

 the statement for Twitch is I should use。Sline and then the explanation was honestly kind of drain all right。

 like you were just assuming behaviors of the program， right？It does depend。 Twitch has it right。

 it's a bit of an empty statement， but it's correct saying that if it's just asking for bytes。

 don't use sunlightline And if it is they didn't put this。

 that's all they put us if it's only asking for bytes， don't use sendline， but how do I know。

How do I know how this program is doing it， You made this assumption because I was typing it that way。

 right， Well we could GD be it。 I assume you could GD be it。

 I assume you could open it up an item and hit tab。

One other tool that I listed on the slides was something called Ltrace。U。

 so everyone here has used S tracece at this point， right， right。

 L trace is S trace is like half brother。I am。Etrace trace's libraries are dynamic library calls。

 it must be dynamic， it must be dynamically linked， if you use Ltrace on a statically linked binary。

 you'll get nothing。The way Ltrace works is it hooks when that call goes into the library。

 so it's like hooking on the PLT GLT stop there。So if I run L tracece。I want Malic stuff on。Heap。

 a out out。I honestly think I don't know why I get all this other stuff。 I'm probably misusing the。

The filter。But this is how I use Ltrace， someone else could read the main page and tell me what I'm doing wrong。

 but what we see here is it's now not printing cis calls with it printing out library calls。

Is it either I want？Okay， I like this so far。Okay， this is the that was nice and then is that going to give me free as well or do I get a filter for free？

I got a filter for free。So。Probably let's guess this， what I care about Mal and freeze。

not for what I was just talking about。At this point， I'm just curious index。Okay。Index 1， free。

 selection free， index 1。Okay， yeah， so you can pay multiple Es to do the filter。

What I'm interested in as far as whether or not I should use sendline or not。

Is is this thing calling read or scan F？Right， so if it's calling Reed the just raw Reed cis call。

 Reed just wants bites at which point send is probably what I want。

If the implementation of the program is using scan F， does anyone have any idea how scanf works？😡。

How could we find out how scanF works？You just did it。Yes。

 we can read the old man page so we can man scan F。And if the dojo is firing up correctly。

 it will describe it to us。 So scananf takes a format string。

 which is a string of some escape characters that define the type that scanf is going to convert this string to。

 So I for instance， say scanf percent D， it's going to read input until it parses a number。

 a decimal number。Now， how does it know when that number ends right I it after I type the first one。

 how does it know if there's another one kind or another digit。

 another digit because number can be arbitrarily large and scanf has to deal with this Sc F will parse the type specified until a new line or white space character is encountered。

😡，If。The challenge is taking an input via scanNf。You want to more than likely use sand line。

 you could also use sand in then just put spaces in between it so despite the like obvious way of working with this thing。

Being。I need to type Malik one and then 20， I can fire it off altogether and it just works。

RightBecause what's happening here is when I type in， where's my input mallet space1space 20。

 that fires on down standard in into this challenge the challenge is going to say index and calls scan F scan F is going to or actually it call scan F parses the mallet reaches the white space。

 it's done It says index， it then parses a digit encounters white space， it's done。

 It says give me the size， which is this part right here。😡，It parses the 20。

 it encounters my new line， that's white space， it's done。If I were using send。

 this is why you should use one or the other and why if you're using the wrong one and you're blowing up why it's happening。

Different parts， like if I were to call read on this。Do you think read？

Do you think this thing is going to call？Scanana。No， it's called Reed。 It's going to read。

 It's going to call literal reads。 So this thing does not need a new line。It just wants raw bites。

Is that the later ones that use read the first 20 were just scan F your knowledge So this isn't meant to be like a trick。

 It's not something we purposely did like haha， there's scan F here like scan F is a regular everyday thing that programs do and deal with so is read。

😡，Now， if you Strace and something is doing scanf， what will Stra show you？The answer is read， why？

That's the Cis Yes， scan F is a library function that calls the Cis read in its implementation。

This is why you can't use S trace to find out if it's using scanf or read。

 because everything will just show up as read。All right， cool。

 so we got to see a little bit of L tracece there， we got to talk about new lines。

There was some good stuff， right？What do we got？Twitch。

Very annoying how some challenges you scanf and some use read。

 Yeah we did it to just be mean No like that that is a regular thing that you should like be able to deal with from every challenge。

 every module going forward， like the expectation is and it should be your first step more than likely open the binary in IDda or binja or whatever you want and see what this thing does don't assume behavior。

The expectation is that you have some kind of。Reverse engineering skills at this point。

 so my goal here is to try and leak that address that we we saw what we here in memory。We said， hey。

 if I mallic two things and then I free it and then I overread。

 we should be able to get that memory in our script， so let's do that。

What were the order of operations that I did？Okay， I'm Mal。00。64。

Another P sun would do the same thing， cool， I got that。I got two of these what are I doing now？

Should be the second对的。And there's one。So this one should be in one instead of zero。

 That was a good catch on me。 what's my next action， I'm Malek， Malick。I'm free， right。

 why do I need to free it？To get it into the TC， now getting it into the TC， what does that do。

 it gives me the next pointer， right？😡，What's the next pointer going to be right now just looking at this？

's going to be null so how do I want to fix it because I want to actually leak out something。

 leaking out null would be pretty boring for a demo， let's leak out something of value。

 How do I get something of value。😡，In the next pointer， what do I got to do？第一单元。I free it again。

 we can free it again， this is going to be a great learning moment。ok你你啲水你。Oh， oh， don't free again。

 free zero， okay， I freeze zero， now what do you want me to do？And why did I freeze zero？是的是。在这个。

Over points to the overlap is a problem we'll talk about next week that one gets fancy All right so the next Okay so if we understand how the TCash works is a singlely linked list everything as we free it gets pushed onto the head of this list so without using GDP and without printing this out we should have a working mental model of what's happening。

I'm going to grab two trunks， assuming the tea cash for this bin size is empty。

 these should be fresh off the heap。So these are going to be right next to each other in memory because the heap is deterministic。

Your June sea heap is deterministic， not all heavs are。And then when I free one。

 that's going to put it on the head， the first entry on that Tcash list， when I free zero。

 what happens？This becomes the head， the previous one becomes the next All right。

 so the statement was zero becomes the the first guy the head points to and then zero gets a next pointer that points to one。

Okay， so now what do I want to do to get that next pointer？Relayase。Do want me to read， okay， okay。

 so you want me to write？And， I do still want to send line。

 we're going to write and we're going to write from where， where to where。感觉得。

You want me to write from zero？I can do that， in fact， this should be super boring， but we can do it。

9 for three。So。We don't need the 64 there， that's a good call。So we were thinking about things right？

Now， this will work。Because we are assuming we're making an assumption here about this。

 the behavior of this binary， what are we assuming？This will work we can do it。P received。

 does this thing say anything when we write？Let's get G to off of that。嗯。Yes， okay。

 we'll receive until。Let's receive all。With a timeout， oh I don't want to receive what do I want。

 receive repeat。I think。Time I and give it like a second。I wish she's clean， that's even way better。

P clean will send right， and then I'm going to receive until。What do we add slot zero？

We'll P receive line because we're getting up to this end of line right here。And then。

Let's P receive until。Right。That makes sense。And then I'm going to throw on。

 I'm not entirely sure what's going to happen here。 We're going to import I Python。

A little embed eye Python。These parties。U， so were we're not doing what I was saying over there。

 we're actually doing something else and hopefully we'll see why。Well run our dot pie， I got this。

 what's my leak？Okay， so I only。I needed to print eight buttontes， here's my address。

This goes back to the what am I assuming， why does this work？

You actually didn't do the same thing I did， let's think about it。

 so we have to think about not only the order that we're freeing things。

But where are these pointers in memory。Contiguous to each other。 What we did here is we have two。

 two chunks。 We have an early chunk。 right， This is the first one。 He's earlier in memory。

 This is the first thing。 It's allocated。 We have the later one。We then freed。The later one。

 we then freed the early one。So。When we write from zero， where is the next pointer。

 the next pointer is literally right there， we're using a use after free here。 we aren't overriding。

 we're assuming that the binary doesn't know the pointer。😡，Do you see what we did？

There's some thinking， I got a head and nod there， it was like this is this is important to know because like I can add one line here and this whole thing will break。

Because I added this like really cool things， I thought about that you I end up doing this toggle mule。

 you know what， that does that makes this binary null after free。

 which is a sane and reasonable thing to do。So this binary does have to use after free vulnerability and that's what we use to leak out。

This memory address， and we could， I assume people could say， give me leak。What do I want， six bytes？

And then we'll adjust it。2，8。Where。No bites。And then we use 64。Does that what did I miss spam。

 and then we hex it。Okay， that's why Heapbleak。We were able to do that， we got a heapble。

 we did something。Somebody says very annoying， oh yeah。That is a you problem， not not a U problem。

Later once use these， don't remember， but I think I struggled a lot with heat stuff at first because I didn't understand how scananf worked and she assumed to work like Re Yeah。

 well one of the things that will repeatedly bite you in this type of content is assuming things。

Right， there's documentation go read it So we we got this this next pointer， right。

 but we assume that we had。A use after free， Wi it does。If I。Before this。Do P send lime？Toggle。

 knoll。But all that does is make the binarynll it out after it freeze。leakak。That doesn't work now。

Because now that's been rolleded out， can I still get that next point？Yeah。

 we can do what I originally said。So how do we do that？

Right I want to overread okay so let's think about what this setup looks like and we have to think about not only the order of operations。

 but where are these pointers in memory now I could draw it out but it's going to take time and I think we're cruising okay so far so what do I need to do。

😡，To create that setup。I need。A valid allocation。 that is early。Yeah。

 because that's the thing that I'm going to overread on because I can't use a freed one because it's going to allll it up。

So I need a valid allocation that's early。 So we know this first thing is early。

 let's keep this guy around。So I'm not going to free that。What else do I got to do？

My goal is to get a next pointer in this index 1。😡，Jorop。How do I get a next pointer in index1？不完美。

I overwrite。1。After I've already freed it， I write something into one。It's been northed。

So if if I like， for instance， we can。Do this real quick piece end line， we're saying right into one。

 it will say 64 bytes of size。And then in theory， I'm sending a times 64， right？

They didn't didn blow up Oh， what do I need to do？For sending my TV。The sending bys。Ah。

 that does make sense。Am I doing that， iss not what I expected to see happen。Um free one， read  one。

 64， because that should be reading。What are I remove？What do you want me to do？Right， then read。

Okay， you want me to do this？I'm going to write whatever is at that pointer。And then read it out。

I'm really what like。The literal cis call， read and write。Yeah writing。 So I will stop that it。Now。

 read will call read， right， we'll call right。A 64 if that right。You want read？てこれて。Read16 word。

 And then the next slide be said。Like this。いだ。After we said 64 S。Yes。Okay。

 I'm doing something wrong here。Let me thank pre one read。164， I'm doing something wrong with my IO。

LetSee， does that get there？Okay， that works。 That free。 slot  one is null。

 So you're saying I want to just do it by hand here。 I'm going to call the read。In the one。Buffing。

 and then it wants a size， which will give it。64 recalling， read。You give it a bunch of A's。

That should freak Segful。But it isn't。 So we'll just carry on and we'll find out what's wrong。

 Then you want to， oh， I read into0。 No， I read in this slot one。 So then you want to write。From。

Right。I'm screwing up okay， either， which is funny because I thought I tested this stuff。Okay。

 but I got nothing。So I guess that's good， I just don't know where it's reading into because that should se fault because it should be reading into a null pointer。

I could Judy be it， but that's not the exercise。I don't want to turn this into another。

Start pivoting extravagannda。So reading and writing here should se fault is what should have happened。

 There's some bug in my code。 All right， so that's why it's not doing it because assuming that we are。

😡，Toggling null。Then after this free。The pointer that is in slot one will be null。

 so then when we read into slot one， we'll be reading into a null pointer and that should sayful and so that doesn't get me what I want。

😡，哎。What what I need to get is a next pointer into。

That what we said that you get an next pointer into something by。哎呀。

Pushing it onto the Tc when there is something next。When I'm freeing。In its slot one here。

 is there something that？So what is the next pointer going to be？It's going to be an null。

 so I need to get I need to put put something onto the free something into the teac so that it can。

 there is something to be a next pointer， so I actually need to mallic a third trunk。

So let's mall something into slot two here。Can I free it right here？Why。Right， if I freed。

Slot2 right here。 and then mallik did。 I'd be mallicking and freeing it， putting it in the tea cash。

 And then this mallik is just gonna pull that same chunk back。

 So I have to do my malls together because I want these to be distinct chunks。

 What order do I need to free these things。And why why the statement was free two， then free one。

Free to put the slot2 in the Tcash everyone pushes it forward。 and the next。The one would be。

So the statement was free two， then free one。And the reason for that is when we free two， that puts。

It at the head of the bin。 So then when I free one， there's something already there。

 So when we push one onto the head of the teaclf， the address of。Allplicationation2。

Will be the next pointer that is written to one。Okay， so now I can do my overre。

What am I overreading from？Right， the statement wasn't reading from zero。

 so I need to P send line this actually not read。 it's right because。Reasons。

We're going to go with again， our 100 bytes。And then we have our P interactive。

 except we already had this P plane。P leak equals P。Receive until right。And then。

I'll importm by Python。And have the eye Python。All right， let's see if that behaves as when expected。

Okay， a whole lot of warnings， but you know， warnings are just a suggestion。And when we get our leak。

What we see here。Okay， so I leaked。I didn't do my IO well。嗯。Like the I is good。

 like the address is hiding， it's hiding over here somewhere。

But it's you can't see that very well right， So I didn't do my like receive until slot zero new line。

 I just did P dot clean so we'll receive until。嗯。Spott zero。

And then will P received line that should eat that garbage。And then we receive until。What did I miss？

That doesn't matter。That all gets eaten right here。Now typing receive line correctly， absolutely。

Okay， so now I don't have that early noise。And here is。My。Address。My next plan。

If we were to take that。And we could do the math， right and say， okay。

 this from that point of it should be。What would it be at 64？64 bytes plus something。

 So if we were to take。Lak， what do I want， 64 onward？Is that right。

 and then I have to do another eight？See if I can do this math right， that is my previous size。

 right， that's my cube。This right here should be a heap pointer。If we say pointer equals this thing。

Is that eight bites， probably not？Let's take the pointer that's L it to eight with nullbittes。

And then use 6 for it gives me a number， we hack it okay。I have this。

 Now my claim is this is a heatap leak。Let's see if I am correct。Yes AuxX Gr8。

 out let's find this process， I actually don't know which one of these it is， that is nobueno。

I don't need this thing anymore。Right， this was my。Toy example。Okay， we see 2039。

 so we'll pseudo GBA 2039。Not Gb， GDP。And this was my address。And we see that it is， in fact。

 a valid heat point。挂水。😡，You universe at the last。You don't understand the last instruction。

In the the code。来十要は。嗯。Okay， how is right 000 leaking the address was the question we can get there。

 I have to scroll up a bit in。I'm not going to get that。Okay， we can get there。

 sorry if I do heap bins。I have two free chunks right that matches what we did。Over here。

 I freed two and I had freed one， so this address right here is going to be one and this address right here is the thing that was in slot2 that we mount through Yeah because remember we pushed to the head so the latest thing on the singular linked list is the first thing that was freed。

2。Now， the other thing I can look at is heat bins。Or not he bins， heap chunks。And。

I'm going to have to do a little bit of hand waving here。Oh no， I can get us there。So if I do P and。

Read。What do I want read into zero， that was my guy that's sticking around。Let's read eight bytes。

And then let's give it one， two， three， four， five， six， seven，Let GDP do its thing。He chunks。Do I。

See my A in。Keep chunks。Oh， I do not。That should。MP。ゼロさ。Yeah， there's some As， but that's not。

So like right here， what do we see this this is an interesting like anecdote we see my string read08 A A right We are not the only ones that use the heat。

Who， what program process function likely dealt with this data？So probably not the cis call。

 so when you do a cis call， you'd go into the kernel。

 the kernel has its own heap that's separate from what we do。

 we are not going to cover kernel heat in this class。It's super cool and interesting。

 But I know it's not the kernel， but it iss the right idea。

 This is likely a chunk that was used by scan F。 So it was used by Lib C in userland when scan F。

 I said， it scanf has to like take in this data and parse it move it around。

 Scf doesn't know how many bytes it has to read to get in right so it can't be a constant value that's on the stack。

 This right here is just some chunk that scan F used on the heat。In its implementation。

 it's actually unrelated to us。😡，So I can't。And we're going to have to do。

To get us answer your question。Nothing。Nothing else from Twitch that's good is I need to print。

This stuff。And we will。Decode this as。Latin1。Because I was just swallowing that before the earlier output of。

Of the challenge。Okay。So now。Why did that not print， I did， in fact， say parent。

Print P receive until oh， that's going to get。Quicker than me。Okay， hopefully， yes。

 we get slot zero's address， this is literally what I wanted。

 I just wanted this so we can confirm that this is this trunk。All right， then we had leak。

And our claim was these magic bites here。I don't know how many I got。Beautiful， so we can use 64。

Matter。And then hacks it， cool， that that's my leak。And then if we reattach GDP， PSAUX， grip Eta out。

 pseudo GB A2478。Okay， so now I have this。Slot zero address。

 we are writing out from this valid allocation。So two STD out and so if I examine and we'll do like 40 giant hacks。

 I don't know that if this is enough from here。This is an allocation。

 This address is the beginning of an allocation that is supposed to be。

What was I asking for 64 bytes in size so that's going to be eight。

 it's going to be here this is the end。呃。The valid allocation that is supposed to be in use by the program on the heat。

 but I'm going to keep ahead。I will try to see thank correct。So next is the next chunk that。

But we can see 51 an address。Because it isnt the peak catch。If it was not in a key cash。

 you would not see those 51 end。This is the beginning of the allocation。That is currently in use。

Okay， so so so when we are given a pointer by the heat and this is where're watching Yn's video。

Super， super important， having little drawings of like what is going on here， super， super important。

We in user Li get the pointer this spot right here。 But I keep saying I allocated 64 bys。

 It's what I asked for。 But I keep saying the chunk is hex 50， which is 16 by bigger。😡，Why？Metadata。

 So even when I am。Holding onto and using an allocation。

 the heap still has to have metadata and it hides it behind。The pointer that it gives us。

So when we say malik 64 bytes， it gives us this point that's what I threw into slot zero the Heaps implementation says。

 yeah， you asked for 64， you're allowed to write up to 64 bytes。

 you can put whatever you want right here as long as we say you own it。😡，And the he says。

 we're just not going to tell you， but we're going to have a little scratch space behind that pointer that we use again for bookkeeping。

So what I am doing when I am writing out 100 plus is I'm starting from this valid allocation address。

 I actually can't read backward。Right in this program。

 I have to read fours and so I read and I read my 64 nullles that basically do nothing。

 and then I read my Xx 51， which is pointed out was that Q。

 and then I read a whole bunch more null lightstes。And then I get this right here。

That is because I hit the D catch。Yes， the。This。Did we free this in the wrong order？We did。Rea。

That's what my math was。So this is actually his next plan。And this right here is。Somebody say it？第是。

写嘅。还先为。key。やで。Without。Yeah， it's so the statement was the key right so we weren't actually leaving the next point and we were leaving the key。

And the reason that we did that is because we freed things in the wrong order。

Where I thought we walked through it， we still got it wrong right this is why it's important to keep track of what order is what being free。

 right what's the order the allocations was the order that you're freeing them。

Because it turns out we free this one。Then we free this one so this is the first thing that was freed with the no next pointer。

 this is the second thing that we freed with a next pointer that points to this guy。

And so we end up getting an next， but it's not where we thought it was。You got to fix this。

 I am at time， or do you understand what we have to do？And。I'm sorry。

 so I could the one statement was I could just read more。And I could。The other thing that I could do。

's two people so I free them in the right order， I malled them in the wrong order。

 good good catch like one of them had be had had to be wrong there。And that's why it's super。

 super helpful to script this stuff。So now let's do that same thing real quick here。

 PSAuxX grip A do out pseudo GDB A 27，25， and then let's examine， I don't know。

 40 giant hes at starting at slot zero， the same thing that we were like roughly looking at now this looks same right we're starting our leap from here。

There's my 64， right？1632 is I 64， this is。The 16 bytes that the heEAP has hiding behind the second allocation for metadata。

That's why we add the Xx51 there。This is our next pointer。

 The next pointer is located at the address that is。Maalked and freed。

So there's metadata behind the pointer that you get for MalC。

 and then the next pointer is literally at the allocation address。And that this is the G。

In late challenges， this will not be a heAP address。

 the key becomes a random string of bites that has no meaning。

Just FYI but for early understanding and learning about the he。

 it's ways easier here if we deal with it this way so this is the next orderer that we wanted to leap and this next pointer is to this address and so I could know for instance。

 the address of my current allocation by doing this overreading I leak this address and then I know hex 1100 or hex a0 behind this week should be me。

I don't know if I map that right， but there is a constant from this week。

 which is this allocation that would get me to there。And哦对。必须。次アケシ。O。Because they have been。

the state bank this will be the last things I am over time， if we freed slot zero。

 then the pointer that is sitting on the stack， I don't think this has， yeah it doesn't。😡。

I all compile it with symbols next time there is an array。Oh， actually。

 I think it's the BSS now that I'm thinking about how I wrote this。So I just have this global。

Charge our pointer I don't really care that's on the BSS right so there's this a array in the BSS that is these pointers and so when I say we no longer free what's happening here in the in the code。

😡，Is we call free and then we just literally sent that。

Poiner that's in the array to be null right and the statement was does that mean that this wouldn't work if we know that out answers yes。

 because when I try and write from that pointer， it's going to write from null and it should se fault as an no pointer de reference。

All right， well with that amount of time。We'll try again next week remember。

 I think there's holiday Friday。I don't know。' It's coming up and it's creeping。

 it's gonna mess this up。 So we'll see what we can do。 Good， Good luck， everybody。

 Thank you for tuning in。😊。