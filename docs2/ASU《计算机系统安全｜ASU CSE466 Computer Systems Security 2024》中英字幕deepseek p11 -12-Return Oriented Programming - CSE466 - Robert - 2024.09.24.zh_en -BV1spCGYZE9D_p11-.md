# ASU《计算机系统安全｜ASU CSE466 Computer Systems Security 2024》中英字幕deepseek p11 -12-Return Oriented Programming - CSE466 - Robert - 2024.09.24.zh_en -BV1spCGYZE9D_p11-

いや。

![](img/b704f178700fb5c05ee8bdda43680e67_1.png)

weIt is happened at。All right。So today is the 24th of September 2024。

Halfway through rock here in CSE 466， I think it's we're about halfway there。Memes， once again。

 I did not select the memes so we can blame SJ zoo for whatever we have here。

We starting rock challenges， unfinished memory yeah yeah I could see that so I mentioned at the beginning of RA that this should be an easier module because it is kind of a natural continuation of memory corruption if you can correct memory particularly when we're overr the save return address that is what RA is we're just corrupting further than the initial save return address so if you didn't make it very far memory corruption you're probably having a hard time right now content will continue to build upon itself。

Land binary。系。Besides can't see slide on screen， you are correct。

I am failing to utilize the new technology。Mash this button。There you go， my bad。

So it's pretty unusual for user binaryers to have a ciys call in them， however。

 some of the earlier challenges do have that so you can practice performing raw and not necessarily worry about some of the more complicated things。

😡，would have we got ahead me on Rob 7。0 looking at gadgets before asking a question。

After asking the question， okay， so I'm going to assume。Oh okay， all right， I get it。

 this is all the same thing they thought they had pop R side。

 it was really pop Rsi with poppar 15 and so there's going to be you know an additional side effect that you need to account for when you're building your blockchain chain。

I'm tired of R。And then you use 30 plus gadgets， it's too damn bad， I don't think。Okay。

 at least the first half， the first half of the challenge is there's not a huge restriction on how many gadgets you can use。

 so you're welcome to kind of use as many gadgets as you need。

 I believe nine1 somewhere around there， we start restricting how many gadgets you can use at least initially。

 and that's one of the problems you have to solve。I you had any stack。

Rockcha after level nine things do get a little bit messy as far as what your rockcha needs to do because initially these challenges will only let you use a couple gadgets you may need to perform a stack pivot and then in that stack pivot performs some other action that then results in like a stage two for instance。

 rockcha， which can work very similar to like a stage one stage two shell code except instead of writing literal instructions you're writing addresses and writing a rockcha and so that it becomes a a lot more shaky ground。

 this also could be referencing some of the later challenges used PIE and ASLR。

 and so now your rockcha relies on a series of things like going well， for instance。

 parsing output from the challenge and then incorporating that into your rockcha。Feeling。

 feelings of power。Okay， if you wrote a good script。

 apparently somebody sold six through eight with the same thing， have have at it。

There are no complaints there。How it feels when return to see blockchain works on multiple consecutive levels so depending upon like how you decided to tackle things right because remember these are open open ended challenges right the binary just is how you decide to approach it and how your neighborhood decide to approach it could be completely different depending upon the approach that you chose to use earlier。

 it may plug along and solve several right you just avoided the subproblem that was in other challenges。

Sp the last hour researching creative solutions， you came up in brute forest in 30 seconds I'm going to imagine that's a loose reference to the challenge descriptions or Lte where they say hey。

 be creative or you know carefully craft to payload if it is something where ASLR PIE randomizations at play。

 sometimes the correct answer is to do some type of brute force Now there's obviously like a limit to you know what is reasonable to brute force。

I would say for this module。😡，I want to say there is a pretty large brute force。

 I don't know which challenge it is， that I'm saying this from memory。Where。

The intended is a brute force that is two to the 12 as far as the odds of success。

 so if you're thinking， hey， maybe I'm looking at something and it's a brute force。

 but it's more than one nibble， you might not be wrong。Okay， but two to the 12 is reasonably large。

 so this isn't something that's just going to fall out in two to three minutes。

 you would need to craft your payload correctly and just know that it is correct。Otherwise。

 you're writing this useless brute force that's never going to work。

So this is where that like conceptual understanding being able to put GDP on something。

 I this person clearly wasn't doing the challenge I'm thinking of because 30 seconds is way too fast for what I'm thinking of。

Uh， but if you， you want to verify as much as you can before you just let the the infinite loop run because the infinite loop。

 if your logic is wrong， the infinite loop will never succeed。You plan plan solve rock 7。

0 for a ticket at the address to Libps C to find DL I don't think any of the lectures talked about。

De open so I can get。For system use system。The call， okay， whatever， yeah， okay。

 we realize we don't have to do any of this， yeah。So if you start randomly Googling stuff and just like doing random things on the internet。

It may work， it may not work， you can definitely go in very strange directions that aren't where you necessarily need to within the pre recordedcorded lecture content。

 everything that like conceptually you need to understand should be there。😡。

I don't believe at any point we talked about DL open。On a somewhat related note。

 I saw and heard that there were people that were leaking calling Put's puts to get a puts address and then they were punching that into some website to identify your Lib C version。

 is anyone doing that here？Okay， you're following blind instructions and not actually thinking that's bad on you when I get to the demo I'll explain why that is a silly thing I understand that it was like the first hit when you Googled like rectalippsC or some something like that that this guy didn't assume that you had the version of LipsC completely unnecessary step so try not to debate yourself。

Okay， general ATC syntax bad， mean， I'll take it。Just a general reminder for logistics。

 I am doing office hours Friday from the students that have showed up， they seem to find it useful。

Ask someone who has showed up if it is actually useful。

I would encourage people to attend if you're stuck。GDB。

 I know some people were still complaining on the discord things are wrong with GDP。

 if you remove the magic from two days ago， everything should be working as far as I'm aware。

 and I have not gotten around to when falling roper so I left this on here so I can sha myself。

Demo plans， do you have anything specific？Yes。I mean， I didn't understand stack favoriteing and。Okay。

 so for Twitch， the comment was， I'm stuck on stack pivoting， I don't understand level nine。😡。

Same thing， yeah， so so I talked with the boss a little bit before I started the stream and people were like oh stack pivoting。

 stack pivoting and that was like I didn't prepare anything on stack pivoting。

 but we'll see what we can do there。Um， the things that I'm going to do u this do people actually understand the difference between the PLT and GT？

Or did we just like read something online and it's like， I use PLT on GT？

Do you want to know what it actually is？Do you need at the end of the day flag is flag okay so so like if if you got the flag。

 you get the credit okay， so that's more of on you right do you want to have the the knowledge or are you just like screw it I'm good。

AndIf you're good， we can pass that in theory that'll be in some other recorded video anyway。

 so I'm fine with that I I do want to show put puts which at this point you've done and it kind of touches on GT。

 PLT。And then based upon what we get from Put's puts。

 there seems to be quite a bit of confusion about base address。

 how do I reason about what's going on inside of a library。

 particularly when it comes to things like a partial overwrite， and so I can use this toy binary。

 hopefully I am gra end to end to show that。And I'm going to use the P toolsols drop functionality in。

This demo opposed to hard coding numbers like I did in the prior one。

 I do think it's good to do the first method in general， I do not like Pe toolsol Rob。

 but at this point some people are using it and so I might as well show it。😡。



![](img/b704f178700fb5c05ee8bdda43680e67_3.png)

And then we'll try and thrust stack it in there。Since that seems to be the popular demand。UPuts。

 puts is boring， yeah， that's， that's fine， you know， I'm not here for your entertainment。

 I'm here for your education。So hacker at Dojo。 Poc College。

The problem with stack pivoting is it's not that interesting to like do and show。

 I think I would say。Let me go into that wrap examples。2。

So we started or I ended the stream on Thursday。With this as my example and people thought this is kind of lame because I was just printing something off。

 right， puts， puts the next logical step。Would be to do something like this。So for those that。

Can't see in example two from last week， we were printing out the address of puts。

 I showed that you could use a Pochos elf object。And using the address of puts。

 we could find other things in lippsy。The difference here with example three is the thing that is being leaked out is no longer in Lib C。

 what I'm printing out is Ma。And I'm also including some tree gadgets here， I'm not hiding that。

It just makes it easier for demo purposes。So can I get？All the way to Li see from here。Yes， no。

Nobody does。We just got them calling puts， puts boring and nobody's like， hey。

 we can put puts on this。All right。If you want to get to stack pivoting。

 you' got to fire me through what I'm already going to ramble about， otherwise we won't have time。

Okay， so I'm going to make this thing， I think what did I call this？Elfle。All right。

 so we have our Llf leak binary here。Do I have a do dot pie， I do not。

I'mNot going to trap myself with i Python this time。Right， some boilerp。

It is important that you set the context。Or the architecture？

Since I'm going to be using the P toolsols wrap module。And then we start off with some boilerplate。

What did I do Am is not good。What am I thinking though？AMD， AMD 64。Okay， and so we have。

Something like this， split it off， so I'm not cutting myself off。It's about there。

And then we will make this executable， I read my do dot pi， and then if I could type。All right。

 it spits out here's mainine is located that and then ready to receive input the binary then reads in there's buffer overflow。

 it's the same offset as before because that isn't really what we're trying to do today。

So one thing that I want to do that I showed on Thursday to see if anyone remembers is capture this output。

 how do I get that output？Tll me what to type， what are we getting， where are we going？

P receive until。Located at， I'm going to give it a space。G在。Can disrupt the space or within。right。

 so receive line will rave up to and including a new line， strip will remove that new line。

So now I have in theory， this right here ending at D。What do I want to do with that value？All right。

 convert it to an inmp specify that this is。Baase 16， and this is going to be the address of mainine。

 so now I have this。Okay。So。One of the things that you can do。Is use the Pone tools elf object。

 There's a few ways that you could do this。 there's all caps Elf。

 And then if that is one way that I could set this。

 the other way is since I already have already any process of this， we can say E equals P dot L。

 it's gonna to give me that same object because it knows the binary that I'm working with。

What is the problem with my P dot Elf at the moment？

So I like peanut health is useful because I can do things like。Print E symbols。Maine。

We can even make this a fancy string， main is at。Get real fancy with her。

And then we will say main his。Really at。The hacks of whatever the challenge told me。

 I'm going to trust that the challenge is correct here。And if I were to do this。

What we see is my Elffins main is that。X 11 AD， however。

 the challenge informed me that it's at some other very， very long address。

 how do I inform my EF object here in P tools to think about this correctly something what do we have？

ですょ。Okay， we want to set the base address so we need to inform the E object。

Because the elf object has no idea what the runtime base address of my elephant is。

 because this elf I'm compiling with PIe。So that means at runtime。

 the address of where N is will be different every time。

 if I run this five times I get five different answers。

What the elf object is telling me by default is where this is statically。

 what is the static offset from the beginning of the elf， which is not useful to me at runtime。

And we can fix that by setting the address。To be the main address， minus。啊，没那个。What do you want？Okay。

I'm going to do this。And everyone follows what what's going on here，' taking my leap。

 remember the leaf is where main is in the elf at runtime。

And what I'm saying here is the beginning of the elf in memory is wherever main is minus the distance。

Into the elf where is。Does this make sense， should I draw it？All right， silence。We're just absorbing。

 that's a weird address， you know， you're you're just trying to flolog me there， twitch， all right。

 at least make them good hits。So now if I run this again。And。ADDR。Now what we see here is。

My elf says Maine is at and this is where Maine really is right and so now my programmatic representation here。

 my elf object over in my exploitation script，Has more information so we can accurately represent。

What memory looks like at runtime？So far so good。Stack pivoting。

question why not use both hard numbers plus ro， yeah， come on man don't tro， all right。

 you're better than that。Okay。So what I want to find， my goal is I want to find Gib C， right？

This is where doing puts， puts is useful。So we want to call puts on puts。In theory。

 most of you did this already， how are you doing it？To experience。Gode。Print the GT address of puts。

With。The PLT address outputs。Okay， so I have these two things。I don't know how to use them yet。

My payload。We're just going the trust in the interest of time。

 this is the padding because I'm reusing the same basic template here。And this is where okay。

 I need to build up my payload now I could P64 this and P64 that and play that game。Instead。

 I'm going to use Pe Tool's wrap object。And we can do that by saying R equals rock of E this is a ro object。

 a equal tools ro object that now has the context of the Elf the order of operations here matters if you set the rock to be on the elf before you set the address the rock is going to have all sorts of bad data right so we want to make sure that we set the base address of the elf object before we create the rock on the Elf。

嗯，O。And what I can do here。Is I can build up。My。rockcha， so instead of doing this math by hand。😡。

I can say rock dot， wrong， e dot。I want GT。Hout。And then I also want。I want to get one of those。

Gdgets that I had hiding in here so I could rock gadget binary a out out and I'm look interested in。

And RDI is what I'm after and we see I have this gadget and it's located right here。

 but this isn't going to help me。Why is this address not going to help？😡。

Because a Pe right what it's telling me here is giving me a static address So this is useless。

 Now I could go over here and do the math and say， okay my。😡。

Pop RDI gadget is the base address of the Llf plus OX11c right I could do something like this。

 but my this is a little bit tedious and I'm going to have to do this for every gadget that I find using Rob gadget。

Instead， what I can do。Its say R raw。RDI。Oh no， I'm sorry， not R raw， RDI R raw。R。rdiI。呃。

R do RdiI is calling R on the rock object， which is going to search the elf for a gadget that sets RDI in this case I threw it in there it's a contrived pop RDI。

And P Tool is going to do all the math instead of me setting the base address and adding this。

So if this is。Pop RDI。What's the next thing that I want my goal is to call。Puts on puts。

The calling of puts is the PLT。The address it puts is the GOPOT。

So which one do I want to pop into RDI， the J2？So I can R raw EGT puts。

 which is actually what I already had。And then we'll R raw。The PLT of puts。

My payload down here becomes our chain， what that's going to do is take these gadgets and then turn this into a bite string of those gadgets。

Now I can't demo this in a script as easily。But if I were to say E equals。Elf。

OfData out R equals Ro of E。R raw R RDI。And let's do that I don't know， three times。

One of the nice things about using this raw object of Pe tools is it has this dump。

 I think it's dump， I think it's dump， not dumps， dump function。

And what that does is it gives me this nice printout of what does my rock chain look like。

So if I'm trying to build this up in an interactive session and you can call print R Dnk in a script。

 but it makes sense to use it interactively because then you can see what you're building up as you're building it now obviously the addresses here are complete boloney because I didn't base this off of anything running。

 but you can get an idea of how that works。There are other cool functionalities that you may or may not have found。

 for instance， you can call a。Function， or as long as there is a symbol here。

By calling our call and then the symbol。So this is now a rock gadget that's going to go to the beginning of May。

 not saying that you need to do that， I know some people are trying it， yeah have addict。

But you could definitely see how this could be useful if instead of building my rock gadget off of the elf that was the binary。

 I was doing that with， for instance， Lib C， then I could R call C modD open whatever you can provide arguments。

You just put them。In an array。And so now that's going to call Maine with that's a lie that will not call Maine。

And。うんうんうんうん。嗯。And so now。One line I said I'm going to call Ma then I said I want to call Ma some arguments bone tools is figuring out how to set up these arguments for me and so it's building that rock chain for you rock gat also has a like super。

In theory， great tool where it will try and automatically build a rock for you in my personal experience。

 these type of automated high level things explode quite a bit。

 so they're great when they work but expect them to break。All right。So。I have put puts。

 let's run my script that was a fine little detour。Somebody says read the docs always。

Do I get anything here ready to receive input？哎呦嗯。I'm not sending my payload， that is a problem。

Pace and payload。Okay。All right， we got a Seg fault。What I'm hoping here。嗯，MaybeMmer啊。

I'll throw a Gb at this。Would did you say forcing？stripip will eat the new line that's not what's causing me to Seg fall。

 I know that isn't the issue。He。It's not what I was expecting to。So let's debug this bad boy。

Like I could take fault and I could be doing what I want， but what I was expecting。

Because I in theory here I'm calling， I'm setting RDI and then I'm calling puts on puts that should print some bytes to the screen and so what I was expecting to see was itt didn't have to be a pretty address but some garbage appearing。

😡，After this。I ran it a couple times， maybe the first one。

 there was a null bite or a new line or something， but there should have been some garbage bites that displayed to my screen so I'm doing something。

Wrong here。So let's see what it is。把 you申明个。The second。So there's only one payload here。If we see。

 I'm constructing the payloads， I'm using rock to build the ro chain。

 my payload is this which I just kind of assumed was correct， I actually don't know that it is。

 and then I'm app the rock chain。so so either my padding is off or my rock gadgets are bat and so it's all right。

 well let's figure out which one it is some people would be like， hey， let's run Sstrace on this。

Which， I mean， you can， but when Strace doesn't show you that I'm calling puts。

That doesn't give me a direct fix just know that something isn't working actually that's when Joe puts it chill right。

 but same idea。to actually reason about what's wrong with my payload， the the answer is good old GDP。

So we disassembled the challenge and this is apparently something people were having a little bit of trouble with is how do I step through this in GDP The point that I'm overatingrating where execution flow goes from the normal challenge behavior to my rock gadget is going to be out of RE in this case me calls challenge challenge REs that is where I'm interested in things going on we run this okay。

 I step I get my pop RDI， I get my pop RE。Okay， we're at the put at。PLT。

And then what I'm interested in is what is RDI， let's examine the address at RDI， okay。

 that is the puts at Gt。Oh， man。That is just unfortunate， that is bad luck。

That is horrifically packed。ThisThis is why you practice your demos。啊。

So does anyone want to tell me why I'm not seeing it？I didn't plan this， that this is just funny。

I'm sorry。No， that the statement for Twitch is because this has got at PLT if I were to use my script and print out。

And where am I doing it if I were to print out E got puts， it would be this address。

And I know it's this address because as I stepped through， I did it pretty quickly。

 but as I stepped through the gadgets， this RDI is what was popped in。And if I were to look at。嗯。

Let's do like four instructions at what's there this is in fact the address where there is a pointer to puts inside of Lipsy so I got the correct location I'm calling puts puts。

What does Puts do？He writes a string it writes a string， right， it writes a string to stand it out。

What is a sea straight？This is first principles like I didn't plan this but I immediately know what happened yes。

 the very first byte because remember strings， when we look at addresses。

 the strings are printed this way， so and I swear I didn't plan this。

 I'm not sure how going to fix it。this address is my pointer that we're trying to put and it is just an old light。

 and so it's immediately saying we're going to print nothing。😡，That is unfortunate。Okay。

 so lets let's think about how we can fix this real quick， let's grab example 3。c。

That is because the address of puts is there。嗯。Okay， I'm not even going to leg。

messs around with the binary。Let's start this， Does anyone have any ideas？Oh yeah。

 so I don't need to specifically put puts right， I just need to put something that points to lip see。

I don't care what it is just give me something in Liy where I know what it is and so the comment from the class was puts。

Print F， is that right， Okay， puts readed I I don't know right that this art isn't resolved right now。

 let's continue。Let's take another look at the got， yeah。

 and so these are all green so and I just use G2B to see what they resolve to。

Bots has that nobte but either one of print F and Re do not have a nobte in them， so let's fix that。

What do I need to change here？Change the gut。De F， all right， I'm a believer。

I'm just going to continue all the way through because what I care about， okay。

 so now we're getting what I was initially expecting， I'm getting some garbage bikes out。

This is not a pretty text representation of that address。

These are the raw bites that represent the numeric。Now， I can still parse this。How do I parse this？

How do I get this？I could receive all。I'm going to quickly take a look。

 it says ready to receive input， is there a new line there？I don't know。

I'm going to cheat and look at。The source。In the interest of time。

 but you could imagine that you're looking at this reversing， so since it is puts。

 there is going to be a new line there， puts a pens a new line。

 so I'm going to do something very similar to how I got the address of main question。The question is。

 if does rerunning the address change the re randomdomizes so I won't get a null bite it。

 is that possible？You're correct in the sense that the addresses are re randomized。

 you're incorrect that that particular nullbyte would be re randomized Let's see if I can show you why。

So the way that things are randomized， ASLR， PIe， what are we randomizing？Okay。

 so that's the answer is I'm random Lib C， so this is an address in this case it is Lib C that I care about。

But is every nibble of the address randomized？Now， what is actually rank right。

 what is the implementation of ASOR only the base address and the base address is a multiple of a page。

 a page is 400 or。49 4096 bytes， which is Hex 1000。

And that's why when we look at these base addresses here。

 they all end in 000 for the least significant nibbles。So。If that's where everything starts。

 then the offset from the base will be consistent and so the least significant three nibbles。

Of anything。Will be consistent， you can't say that about the。

 but what I can say about this puts is the three least significant nibbles on this challenge right for this Lib C will always be 50 zero。

the highest higher nibble here the。I'm going to call it first five that could change because what randomizes is the page and the page starts at the fourth middle。

Everything from the fourth nibble onward is the page and then the last three nibbles are the offset into the page。

 and so those last three nibbles will always be consistent。😡。

The randomization impacts the other nibbles involved there in the middle of the address。

Good question。So we got around this by printing just something else in Lipsy because I don't actually need put to puts。

Somebody said print puts plus one， right， I could have done that， I could have taken no。

 I couldn't have done that。That wouldn't have worked because you're providing a pointer。Into。

Into the gott table and so you'd be incrementing the pointer into the gott table and what you would get from that is a bite that doesn't matter followed by a null bite so so your better option is to print something else that you know is in Liy All right so I need to capture this thing。

I'm going to P receive until same strategy I had before here， except now I'm looking for， I believe。

 input exclamation point。and then I'll throw in the new line so that I have that so now I know I've read everything that is there。

Now here I just need to eat however many bites。This is。I got one， two， three。Four， five。

 six bites here。Some of these， none of these are three digit hex values。All right。

 I know that was something people got tied up， the way to read this is escape X。

 the next two digits are the encoding， this nine is a literal character nine。

 which is the bitete hex 39。Not that you need to be able to read this from and print out。

 but that is。Worth being aware of。There should be， what did I say six？One， two， three， four， five。

 yes， six bys。I'm sorry。啊。Yeah， there this。But what about this box offing？

So when I'm looking at this and this because I'm familiar with how Python represents byte strings。

 the first byte is Hex 1 a， the second byte is the character9， which is the Bked Hex 39。

The third byte has the value X8 B。The fourth bite。Let I do that right one。Oh， the。The back tip， okay。

1，2，3。Four， five， it's still six， I just， I knew it was six， I just counted wrong on paper， Yeah。

 so it's backt。1 a， the character nine，8， B。He he， the character swggly。All right。

 so it's going to be six bytes。Does this end in a new line。

 the question was why can't I just receive line again？Now you're actually right。

 it does because we're calling puts puts a pens a new line to whatever you're pointing to。

 so I could do that in other contexts， you don't have that guarantee right in my opinion it's better to receive the raw six bys。

诶。Because you'll get these scenarios， imagine this challenge printed off more garbage。

 right afterwards。2。And there wasn't a new line， right。

 you could have this and then it says hellello world right after。If I receive line。

 I'm going to get this garbage in this specific scenario you could receive line。

So I have these six bytes， how do I turn this into a number， something I can work with？Pack unpack。

 okay， so here I want to unpack。And I have six bitetes， so that's not good。

I'll just it with null bitetes。I think that that's what I'm after and this is going to be what did we say Lib C print half？

谁有对。Minine let's， let's print it off to make sure that we are correct because it's a good practice。

For an F is at。Liib say print F。We are still running this with G， which is nice。Let's break at。

I can't can I break good puts， I' make break puts， I think that'll get me where I want。

Let's go one more。Backact trace， we were definitely there。We get Maine， I'm going to go one more。

 that's a shame。All right， so instead I'm going to have to step through this thing。

 we'll disassemble challenge， we'll break it challenge plus 83。Remember， we could script this。

If we wanted。There's my puts puts。Okay， now I am inside of puts， which we f。Out of puts。Go。Dang it。

 am I getting it， what is it？Complaining。L just P64 P receive。hidingiding air messages here。

Unpack requires a buffer of eight bites，Gosh stayingang it。My Python's exploding， not high。Gdb。Okay。

So now I see up here， this is what my phone tools， parsing of those bytes was。

 my mistake in case you didn't catch it， I hit L just2 and then the null byte。

 L just you set the length that you want， I want this thing to be padded two a length of eight with null bytes。

That gives me this six throws on the two nubytes that way it can be parsed by the unpack or U 64 and this is a good practice here is to have GDP verify that what you're parsing and thinking about is correct So this is where I think puts is inside GDP I could print print print print F and what we see here is the address print is at this is the same address Now this I came to not from anything in GDP right I came to this number purely from my leak and my exploit you want to make sure these two things are separate but I can use GDP to verify that what I'm doing and what I'm thinking about here in memory is correct。

All right， so now that I have this。Liip C leak， how do I use it？But something I may want to do。

Something you guys really wanted to so I knew want a C more of the flag， right。

 but let's let's think about the problem that I'm facing here。What happens after I send my payload。

 what does the challenge dude？It exits。So by the time I get my leak。By the time I get Lib C。

It's just going to exit。Am I screwed？那。After the are after the fix。After the fix， what's the fix。

 you just know that there is one， you think I'm a clever guy？What do we got？

Go back to the position where I could do a second read when you say go to the position I could do a second read。

 be more specific， what are you suggesting？Make the wrong such as。the challenge so that就。Okay。

 so so more general， instead of drilling down and saying exactly where you wanted。

 you step back and generalize， I'm okay with that， it was still feel correct so somehow I want to be able to get a second payload into this。

And so I want to call Re。Can I do that and where do I do that？After the option。After the rock chain。

What goes after the blockchain， so the statement was somehow call read here， which I think I can do。

I am just whoop。I don't need four of them。And did I mess that up， I did。추추추추。

I only need one of these， so I can call read。All right。Let's break onread， let's see if we get there。

 this first one should be the challenge doing it， the second one is if we take a look at the back trace。

My claim is this is the rock adget doing it。I actually can't prove it to you here。

Then that's my claim， where am I reading into？Does this help me？So the first argument of Reid is。

RDI RDI is is not looking like a file scriptor The second argument of read is the buffer I'm reading into。

 which is RSI， This is somewhere。It's somewhere in the heap， we haven't talked about that。

 I wasn't planned。But okay？So I need to fix these。We know I have a we can just。Okay。

 so there was a statement that I could call Maine。You can do that right you can you can treat functions just like how we're calling puts a gadget right it's just a really big gadget that calls this whole function there's nothing stopping us from going back and calling Maine again right and starting execution one of the things I would be wary of doing that I'm not saying that it won't work in this context is。

If you start like calling yourself and going into things。

 you're going to start messing up things on the stack and things will not be what the program intended。

 this is particularly true if you start doing pivoting stuff right or you clobber RBP for existence for example。

Because remember a local variable could be referenced by RSP。

 but it could also be referenced by RBP and so if the challenge is doing that in Maine or in challenge or somewhere in its regular execution。

 if you are messing up things in memory， you'll have pretty good odds of a Seg fault so something a Se fault or a SG bus right you messed up something on the stack or you're accessing memory in a way that was unintended。

😡，You can do that， so I'm not saying that you can't。

 but it isn't where I would try and drive people to we have the gadgets right now。To set RDI。

All right， then I hit our raw zero right， that's going to set RDI to zero。

 The other thing that I'm interested in here is RsI。 if you recall from the source， there is a magic。

RSI gadget in this binary， but you can see how you could use something else。

And when do I want to set RSI to？That is something I did not think of。

 so where do I want to write to in memory here？I want to write to something on the stack， right？Okay。

But I can't know where the stack is right now because the only things that I have are main and。

Print F。Can I get a stack leak？Maybe。嗯。What do I get here， move RV， RVP。

 picture pop already I brought， I can get it into RVP what I'm looking for。嗯ん。あちょちょちょち。At RSP8。

I'm looking forward as a way to get。RSP into RDI here because I need a stack leak。To get that leak。

Because then I could put。Whatever's on the stack。Yeah， let's see，s what's going to be useful。嗯，吃吃。

Lack of RSI gadget， I gave myself an RSI gadget。Someone's just go to start。All right， whatever。

 so I wanted to just try and call read again， but maybe maybe you guys are right here the answer is to。

Go back to。Main or start。See what happens。Print F， I got this read， so I can't do this read。I want E。

Smbs。Man。See what happens。That would be awesome。Does this？Get me back to Maine。

There's my first maine。It gets me to the second man， I continue， I'm out the read， All right。

 I'll buy it。 Okay， that what was the way to go here。啊。Okay， so I've got my second read。

 what I'm interested in now is what does this payload have to look like to do？My next problem。

So what I'm interested in。RSI and then。Finny， I don't care。嗯。Okay， now we got there。嗯。Info frame。谁。

Take my bites， Oh， though the bites go up here now。Okay可。Info frame。

And then what was my RSI from earlier？ちゅちゅ。Maybe dollar sign one， print dollar sign one。

 we subtract the two。Hopefully it's still no it is a different number's a good thing we we masked it's 272 for whatever reason instead of 264 until I could then repeat this getting that payload。

And rock Lib C。Do people want me to wrap lips here or do people want me to throw together something with the stack pivot？

That个人。Okay， that looks pretty universal this would have been this would have been cool all right guys we would have Elf Lib C。

 we would have driven through there all right， this was a two stage option， this was a sweet demo。嗯。

All right， so let's make this some type of contrived stack pivot for。For you all。That's not too hard。

 What we'll do here is we will make。This buffer only be 24 bytes。

 and I will set a global variable up here， which we will call global Buff。And it will be a big boy。

256 bytes。This challenge is going to。Print or puts。Give me global。It will then。

Read from standard in into that global buff。256 bytes。It then does the exact same thing except now。

I'm only going to read in。48。32 some small number。It's 32 reasonable I don't know。

 48 should be should be enough to overflow this buffer getting into the same pat dress。

 but I don't get a bunch of gadgets right so so we see that I'm under some kind of constraint here。

Now what I'm giving myself in this challenge that I don't believe you have in。

The or at least like as obvious as you do in this is I'm giving myself this like scratch area。

 this global buff right that I can write things into。And let's。In the interest of time。

Bak out global B。All right， that seems like a reasonable。Reasonable scenario。We hate it， we like it。

 I don't know， there faces。Let's build this thing， what did I just write， example three。

So we can make， I think I called this thing Lleak。IfI did that right， give me global。

 ready to receive inputs。Okay， we have to adjust this thing a little bit。

My payload should now be 24 plus8 should be what 32。啊。It's a guess， right。

 the compiler could have chose something else。Then I need to change what I'm doing here。Okay。

So instead。I need to somehow do a pivot。And I'll do is we will P receive until。Global。

 that's what this thing says， right， yes。Receive until global new line。I will send our chain。

 so I'm writing my rock chain to this global variable。

And what I want to do is somehow pivot up to this global variable what is AStAC pivot in the simplest of terms？

Okay， popping RSP， the all we are doing， all we have to do for it to be a s pivot is set RP to point somewhere that isn't where it is right now。

Why do I care about that？😡，Because if I pop RSP in RET， what does RET do？哎。Pops Ri。

 does RET care where RP points？The answer is no， what we are doing here。

 this is where we find out if technology works。OhAnd then you don't get to see it。

This is where all of it goes。Goes awry。あチ？

![](img/b704f178700fb5c05ee8bdda43680e67_5.png)

嗯。Fll screen sure， does that make it oh that something really bad。



![](img/b704f178700fb5c05ee8bdda43680e67_7.png)

Okay， so that wasn't what I wanted。That isn't what I wanted either。This is all。All going downhill。

Okay， well， we're about drawing later then in theory， I was going to draw a pretty picture。

What's on there？You see what I want you to see， oh， this twitch delay sucks。Okay。

 we're going to go with that。We have some region of memory where the BSS is。

 this is where my global buff is， which has my ro gadgets。I then have somewhere else。

A region that is the stack， and there are gadgets here， gadgets here。

 and RSP is pointing to one of these。When we want a stack pivot， as somebody said。

 the ideal thing would be。Pop RSP， and then this becomes the address。

Will you C syntax the address of global Buff and what that should do is if I have a pop RSP。

 then the RSP becomes the global buff， which points up there。

 which is where the rest of my gadgets are。Yeah。All right， so realistically， do you get pop RP？

There's heads， making the noise， left and right。Let say and no， what do we have instead of pop RSP？

We have leave， what is leave？So almost every function。Ends with。Leave R。

This is the function epilogue。What do these things do？I here， move RSP， RBP。Pop RVP， pop RAP。

 so leaving RE are both instructions that are like performance optimizations because they happen all the time at the end of every function。

But if we were to think about the actual actions that occur， it's these three things。

 we're going to set RSP to be whatever RBP was that's eliminating the current stack frame。

 we're then going to pop RVP， so we're popping that saved RVP and then we pop R that's where we are popping in that saved return address。

So if we don't get P RSP， we can find a leave rep。But what is one thing to be aware of if I'm going to use leave rat？

I need a set RBP。I'm not saying I have to set it to be something valid， but I have to set it。

 and so I have to know that in my payload。So if I I'm going to route gadget here。Sure。Leave rat。

There is a way to use P tools。To get a leave rent， in fact。

 they have the whole fancy pivot function that I don't understand either。啊。

I'm going to use E address plus whatever I got there。Because I'm a savage。Okay。So I have my padding。

 I have my lead rat， what do I want to include after that？As we said over here。

Over here that it is move RSP RBP， do I care about that step， not really。

 I need to set something to be RVP and I need something to be rip。So payload plus equals。

I don't know， where you want beef？Beef is good。P64 at beef， this is what's going to be in RBP。P 64。

 this is where I need my。A new。Oh no， wait， wait， wait。嗯。Move RBP， RSP， hop RBP。

I'm thinking about this wrong。What do I care about the RBP？我是那个。

Yeah I need to set RBP because what I care about here is not the pop right what I care about is this right here。

 this is what gives me control of RSP， so I need to set RBP first as you pointed out。嗯。

So that means I don't want RBP to be beef， I want RBP。To be see if this exists。U。

Is this going to work？Is it going to keep that symbol for me。 What did I call that thing global？

I don't know if this exists or not， we'll find out together。Global buff， global buff。

 that's going to set RVP。Then we have a gadget again。Where we pop rip。Okay， that's my leave ratt。

 that's what's going to be popped into RVP， then we're going to pop rip。

 which I'm going to give it another leave rat。Does that make sense？我是最开的感庭。

If I find a gadget to just pop RVP， I don't know if this guy is going to have one。Okay， I do。

That makes life way easier。So let's。Do。Payload plus equals my base address plus this。

 which is a pop RVP， then we do。The address of my global buff， and then I call Leave rat。By that。

Hopefully it works， we'll find out。I don't know if the symbol is going to be right or not。

I don't know if that resolves。Do I care about this？Not really receive until input。

I don't care about this。Yeah， let's just run it and see what blows up。Five minutes。

 I think we can get there。Challenge plus 147 will continue。I'm not sending enough stuff。

 what am I sending？Global peace end our chain。Oh。So what happened here is I didn't there's two reads。

 but these are PN PN and so there's our kind of rapid firing here one way I could deal with this is P dot clean the other way that I could deal with this is。

I actually actually， you know， I was just blocked there。

 so I want to wait until it says it's ready for input before sending the the extra input。Break。

 we fire， do I get there？They do not。Why。I'm still blocked on read， okay。Let's run this thing。

 give me global， does this make sense？P receive until global， yes。

 that makes sense P receive until input。That makes sense。嗯。Anyone see yet？🤢，Fire off there。

 That's fine。Pace and art chain。啊。This's just like a goofy IO thing that I'm hung up upon right now。

I'm not sure what it is。い个場。I'm sorry。我是。The rest of violence。せす。Uh。

 that shouldn't be an issue because this。Should flush it if we look at the back trace， I'm inside Re。

 we can go to the first frame。Give me context and then we could disassemble where we're at。

I am still at the first read， so。That's true。Its my clean， my clean doesn't get me there。Okay。

So I'm still hung on the first read。 I'll do what you are suggesting to just get this out of the way that shouldn't be necessary。

 though。 L just 256。 We'll pat it with。No bites。嗯。Doesn't that get me？Okay。That's my first read。4月。

I'm not sure what I'm hung， go， you' dang it。You want。Log level Dbug。I don't like that。

嗯How would say。It's not a new line thing because we're using read。You want log level？这点回是。See。嗯。

you continue。Give me global。Where is my？And。Our train received tall global sand。Hello。A train。

Receive until global， I get this and then I don't send that。

It's this like an encoding thing because I didn't make it a bite string that would be super dumb。

You家啲公。After they called me right。啊，说で。那谁？And we're there。 I'm receiving until I get the。

Bite strain global， which is what we see right here。That should be good。 This should send this。

I'm not sure why it is not Sunday。よし。Because it is， in fact， receiving that。嗯。advice。So。

The problem is in the IO side， I believe。And the reason I say that。

This is because we don't see the send。In this debug output。So we aren't getting there。

And so we're hanging right here。I just don't know why。Technically， I don't have to block on that。All。

 we received it。I've sent my nonsense here。I've sent 256 bytes。

This is creating Global B 256 we're sending where we're sending enough bites。

I don't know why I'm Io blockeded。That's a shame I'm over time。

But the stack pivot is setting RVP calling leave， you're taking advantage of。This part right here。

 we are setting RP then when you。啊。Pop Ri， you're executing the other rock chain that you've loaded in memory。

Does that kind of make sense？And now now like now you're just all over the place there， twitchitch。

 I will debug this later， I'll try and throw a stack pivot like code sample on the Discord。

That you can play around with， is that fair？Cool， with that， I ran out of time， that's my bad。

 hopefully there was something useful there。

![](img/b704f178700fb5c05ee8bdda43680e67_9.png)

Okay。I have audio， I can see chat， everything has just like exploded。All right。

 we're going to try this again， fortunately， sorry about that。

 I just need to completely reinstall OBS。So。I was deciphering why things were broken。

Bit of background noise on the mic， I'd believe that。嗯。it's not echoing， it's just。

Picking up ambient noise。Here， so that's that's the best I can get you， hopefully it's not too bad。

Okay， so I was starting to figure out what was wrong with my code and the answer was the challenge wasn't printing out located at。

 but I had this located at in my P toolol script。And。So we brought this back。

 so now this prints out main。What a mess。嗯。Okay。And I was setting。诶。

Was trying to do a stack pivot from here。Get rid of this。

So we can see all of the code of what was going on。

My challenge binary says main is located at Give me Global， we give it something。

 it says ready to receive input except。receive is misspelled， whatever， we give it another payload。

The challenge binary。Thiss not particularly interesting， right， we're going to。Put half that main。

 we're going to read into the global bufferuff this since it is a global buffer。

 should be in the BSO section。It's going to print off the global buffer， so I should just grab。嗯。

Global buff from there。If we're being a real。Since we have that， I get main。I had been already。Oh。

 this binary。This said poor， poor binary。Make。Fly。We get Maine， we get the global。我这。Yes。

Start with something that we can reason about。man and global。I just remove it。

This didn't actually right。We move it out， yes。Make。

Com week we have a normal binary giving global global buff for you receive input， but okay。

 so now that matches the the behavior of the binary matches the source curve over here on the right。

 So we're going to read once into global buff we're going to read a second time。

Into onto a local variable。There is a slight buffer overflow here。

 but it's not enough to really do a full wrap。And then we have some free gadgets down here to make life easy。

All right。Payload， then our exploit。Let's just go through it。Right here。

 make sure that the left hand side matches the right hand side。

 so we're going to start the process we're going to receive until located at with a space。

 I'm going to grab this hex value， which is going to be this right here。

Once I have the address of Maine， we can set the base address of this elf that makes sense。

Then I'm going to use the elf in a Ro payload。These things exist， this will be keep you written。

Into this first read。 So we are setting up our rock payload。

 We're going to wait until we receive global here。Then we're going to send that rock chain and so this rock chain should get written up in the BSS。

All right， so here is。My。DSS payload。It then will print off global Buff， so I am not using that。

But that's fine。It then says ready to receive input。I don't care about。喂。

I'm going to receive until input exclamation point。 and then I send my payload。

 So this is a little bit backwards because we're sending our second stage before our first now。

 where what we did in class it。Or where the demo that we started off with in class made sense。

 we sent payload one， then we called read to take in payload two。

 but here it's the inverse we're sending payload two and then trying to get payload one to redirect。

2 payload to。All right， so now let's run this thing。And。

We will a point that we're interested in is where we can take control so we disassesemble challenge we'll bring at。

Challenge， plus。147。If you can type。We continue onwards all right， so this should be pop RVP。

 which is what we see right here because this is my stage one。See if we can make that bigger。Right。

 we pop RVP， we print RVP， and why do I get one here， that's what's confusing。

I don't have an answer for that。 Thank you， Thank you， Siri。So some for some reason， that is。

Resolving to。1。We're popping one。Which is not good。And then， we。End up over here in。No man's land。

Okay， well， these addresses could be wrong because I have rebuilt my binary。 So let's run。

Rrop gadget again。That would。 That would make sense。We'll rot gadget， binary， a out out。

We can grab them for RVP。Again。TypeWe have a pop RVP， so that gadget was good。

What about the leave rat？Let's make sure。Leave 11 EB， so I in theory you have a leave rat。At。

That location as well。So what I don't understand。Is why I'm getting a one there。What。

Get rid of this debug stuff that wasn't helpful。Throw it in the interactive session。Okay， GB here on。

What is E symbols global boss。That is real。And if I P6 for it。I get something。And if I。Exnet。

IAlso get something saying， so the question is why？

Does E symbols global buff at this point when I send payload。Have a one in it。G RVP。慢慢的。For3。

But we can see that right now I have both。The debuer down here at the bottom paused on the program。

 and then I have this interactive Python session to try and sanity check what is。Going on here。

And so what？Interested in。W inside。I'm inside of Re because I haven't。

I'm still in the interactive session。I'm here， so I haven't sent。This payload yet。

So then what I really want to know is ahead of time， if we quit out of all of this。

 I want to get to the first read and see where read is actually putting stuff。So if we break on read。

We can continue and I'm interested in here is RsI。 This is the location that should be global Buff。

Because if I were to disassemble。Challenge here。 I am at。B1 a7。ち。B 1， a 7。

 So I at this first call to read and it is going to read into global buff。

 So that makes sense if we f from。There。This should be my global buff。And if we were to examine。

Because now we've completed the read because I finish from that read call。

 I should be able to examine the address。At this location。え。That。Is the first rock gadget。

 which if I were examine into instructions at my first rock gadget， there's my pop RDI rep。

So that makes sense。 That is this first payload right here getting sent in。 That's my pop RDI。

 And then if I were to。Examine what do I got let's say six， six addresses here。

 this is my pop RDI gadget just in the BSS， this right here is my print F in the gott。

 which makes sense that aligns with what I have right here。My next gadget is puts at PLT。

That aligns with what I'm doing here， and then I am calling。That's why everything is funky。

 I'm calling Maine again and I don't need， well no。

 that Ma doesn't hurt anything for our purposes for the pivot。

But my stage two is then going to call Ma again because。Apparently that's what we're doing。All right。

 so now I want to we info break。still have a great point at Reed， so lits。

Continue and so now I'm in the read， which I'll want to Finnny and what I'm interested in。Here。よし。

That。And that are they the same thing？The answer is yes。Okay。So then let's finish from the read。

So my elf is correct。Now here my exploit is just kind of blocked on this interactive session。And。

 you didn't miss all the fun。 I'm still broken， I'm still broken。

 and I haven't figured out why but we're going to reason our way through this。

So I am currently blocked right here。The challenge is blocked on read。

 So I can in my interactive session， say P send payload。All right， that went in。

Now I should be able to examine。呃。Let's do like 40 giant hes at RSI。Here's my A's that makes sense。

Then this should be my first gadget。We examine the address。Right， there。If that know。

 if that's my gadget， then I want to examine like three instructions there， there's my pop RBP RE。

So that is there。And then I get a one。Oh， I think I know why we're cursed。This is 8， 16 32。

 40 48 bytes I actually need to read in more bytes onto the stack。So even though I'm sending 40， 48。

56，64， I'm sending 64 bytes here in。嗯。My exploit script if we were to。

Want a cursed demo if we were to look at what was going on in here， it's really only reading 48。

 And so this read wasn't large enough for the payload that I needed。Okay。Actually， no。

 let's not do that。 Let's get rid of。Our interactive session。We have to be an optimist here。

We'll disassemble challenge。We'll break at challenge plus 147。

 which is where our stage one should hit。 Okay， we're going to pop RVP。 we print RVP。

 Now RVP is global buff。Yeah， exactly， that's exactly what I get for trying to like hot change this code to make it all work。

But now RVP is the global buff。 So we rent， then we leave and at the moment of。Leave， if we were to。

Print。RSP， it is now global Buff plus8。And that's kind of weird， right， why is it global Buff plus8。

 well if you， I don't have the scratch pad anymore。But the leave instruction does a couple things。

 it does move RSP RVP and then it does P RVP and so we were taking advantage of this first action right we were setting RVP and then letting move RSP RVP set RSP to be somewhere where I'm interested in。

What I didn't account for is to pop RBP。And so instead of jumping where I wanted to。

 which was global Buff， I at Global Buff plus eight。So that kind of sucks。Can we fix that。

 well we can fix that a couple different ways。I could。Up here when I'm reading into。The BSS here。

 I could add some dummy bites。I could add eight A's here and that is what would get。Ive popped。

The other thing I could do is I could set。This。I get offset。The address that I am using by8。

As we said， we are at it plus eight。Which means I need。To go minus。え？

see if that gets us where we want。All right。Pop RVP。Rat， we。And now what we see is。

RSP is global buff。And so RSP no longer points to the stack。RSP used to be。Down in this region。

But by doing。Here's my gadget here， a pop RVP leave rat。I have set RSP。To now be。

That buffer that is in the BSS。And if I were to continue to step through my gadgets here。

This pop RDI。It's going to match。My stage two that I had sent earlier。

 which is going to be this right here， so we pop RDI。We rat。And then if we look at RDI。

 let's print it as an address。I don't know what I'm doing over here。 I'm putting Lib C from here。

 That's what I'm doing。I'm pushing print F， I'm just doing that in my stage too now。

That I pivoted to。So then we step again on inside puts if we f。From puts。三0。Something bad happens。

ちちちち。嗯。Alright， I believe。I know what this is。I believe this is a stack alignment thing。

So there are some things inside of Lipsy that require。啊。The stack to be aligned by 15 bytes。

 and I believe we hit one of those traps right now。So if I'm right， we can。Our problem is right here。

I still don't have fluimacy right here， RSP is not 16 bytes aligned。So the。

Kind of work around for that is we can shift the stack by8 by inserting a gadget that is just wreck。

So if I rock gadget。On my binary and we just grip for everything's going to be read。

 but this is what I really need 101 a is my offset。We can R raw。去去。

I know you can search for a gadget， but I don't。Noow the syntax offhand。

 so I'm going to say E address plus or x 101 a。That should get me。Here's my break。Step into this。

My leave rat。Pop RDI， rat。We read one more time。 I'm just out of curiosity。

 So the prior to the RE RP did end in an 8。 So it was not 16 by aligned。

 But when I read a second time。Now when I get into puts。RSP ends in a zero， so it is 16 by aligned。

If this doesn't if this finny doesn't explode。Then it was a stack alignment issue。

Twitch says that a rock a that is just rent is equivalent to anob and that that is correct。

And we do see。That we didn't explode where we were， we're now exploding somewhere else。

So it likely was a stack alignment issue。But now we are exploding。On Push R 12。Okay。

 so somehow in that mess。We set RP all right， we set RP itself to be。What's it got。

And this is an example of where。嗯。Cotuttering stuff leads to like very strange behavior。

So the original problem was that my stack wasn't aligned by 16 bytes。

 my current problem is somehow RSP is getting messed up。Let's say。They can find her there。

It's my leave， there's my rat。My pot rat。What is RSP now， RP is global buff plus。24。

And then what is RVP， RVP is zero。 So when I step into。Puts at P L T。My RP。Is。Somewhat reasonable。

 right， Like it is a region of memory。That is read， right。And so it conceivably。Could。

It could be functional as a stack。But somewhere in this thing。

It's going to change RSP and that is going to just ruin our day。So this is where we exploded before。

 which we can step over。And so the question is my RSP is still same here。

We're still happy in the BSS。If I keep on marching。Where。Where are when。Does RSP get masked out。嗯。

There。Back in my source code。This was just a rat。To make。16 by stack along。

This is no longer a problem。I should be able。To make it through pot。Let's see。

 let's disassesemble parts。嗯。How many rats are there， I it just one rat？That would be amazing。

There's one rat， that's it puts plus 243。I don't think we get here。We don't。 We are in。So insider。

Put。RSP is reasonable。I went to frame two。Srame。Three， I am inputs。Okay， inside puts。

This is reasonable。The problem is that we are。But what's my？Putush takes one argument， which is RDI。

 if we examine the string of RDI。How we said already。2P。就你你你。2048。2088 right， so then we go into put。

 did I not set RDI correctly？When I called put。How R RD I to be Egot print F。And we call put。

I don't understand where。Backactre， frame 3， context。Dasseemble。

So we are failing whatever this check is， which is leading into a big oldle mass。

And so what I think is happening。Is。By pivoting up into the BSS here and then using that。

So I was twitched as they're confused。So I set the context to be puts right I'm in my broken state right now。

My actual saying fault is down here in IO do right。New do， oh't know， it's in frame zero。

This is my actual Segfa。My Se fault is occurring on P R12。Now this is several calls in from puts。

I'm not saying that I'm going to be able to fix this。

 but I want to at least understand what's going on and why it's happening。嗯。

So I'm blowing up on a push instruction， which is a strange instruction in like a normal context to Seg fall law。

But if I were look at this pushr 12。What is？Push needs to do two things。

It needs to decrement RSP and then place the value there。 What is RSP。RSP is this thing here。

And look what happened。To the memory region， so when with the reason that this is I can fix this。

 we can fix this， this is an insane problem， right and it shouldn't come up in the challenges。

 but that's part of the find of like poking at this and reasoning about what's going on。So。As。

We called puts after our pivot。When we pivoted。We made up RP， right， We just said RP is going to be。

Whatever my。Global Buff is that's chilling up in the BSS。

But when you use a stack and you start pushing values。RSP goes down。And so what happened here。

 if we look， RSP is 69a2000。And we are at the earliest part of this readrite section of memory。

 and so what is at？69 a。What would there be 69， a1 F，F8？

That's going to be this region of Emory right here， which is not rightriable。

 and so we are we grew our stack because the stack grows in the negative direction。

 we grew our stack backwards from where we were here into a region of Emory that we can't write to。

Now we didn't know that when we made this like put gadget， right。

 but that's what happened and so what we need to do。In order to make this all happy。

Which now this is just like a fun exercise to see if we can do it。

Is I don't want to pivot to global Buff minus8， I want to go later into this global variable。And so。

 I really want。Up here。In my stage 2 that I'm doing earlier， I want to send some， some padding bites。

 Does't really matter what they are。 I'm going to send a times 64。 I don't know that this is enough。

 It's completely arbitrary。 What I'm what I'm choosing here。And then my place I'm going to pivot to。

For simplicity's sake， we're going to say it's going to be where we were except I want to go 64 bytes ahead and what this will do is it moves the like starting location of our pivoted stack pointer that's hanging out into the BSS。

It should give us eight more values that could be pushed on。That was a cool。

 cool problem to kind of run into。So now let's break at our challenge。All right。 here's my stage one。

 We pop R VP， we rent， we leave。 So now we've done our pivot。 This is my RE for stack alignment。

 I think。呃， we。Oh no， no， no， that was just a normal rep， we pop our DI。

 this is my RE for stack alignment。Because I was about to go into puts。And we see that RP is。

Ending in an8。 And so this extra rep that's just kind of randomly there gets us 16 by the line。

Now do I finish through puts， I would think so。No， I'm still saying faulting。

Am I and I'm said faulting on a call。My。RSP is now this。So there's。

A whole lot going on that we did the same thing， right， we still haven't moved far enough ahead。

As it turns out when you start calling you these non trivial gadgets， like we our gadget of。

In our case， we're calling。Putush your PLT。This puts at P L T is like a big gatdget。 We're like， oh。

 but it just calls puts， right， true， that just calls puts。

 But as we can see here from this increasingly deeper call stack。

 Puts is actually doing quite a bit of stuff。 It's pushing a bunch of stuff to the stack that assumes the stack is something saying。

😊，And every time that you call， you're pushing a。Safe rip。Plus， probably a saved RVP。

So' let's see if this is solvable in the extreme。256 bys is how much that。Ged is。

 so 64 wasn't enough。Let's pad this thing by what what do we want。

 give me a multiple of eight that's like 200。So 128 would be in the middle。But clearly。

 our problem is not clearly， our problem is to start growing。 so going in the negative direction。

 So I want to bias。呃。Deep， I want to go deep into this bad boy。What it is heckx of 200。

 I should know this。Okay， 200 T is reasonable。It was important there that I picked something that was a multiple of eight。

Now， that may have messed up my stack alignment because I don't know。If 200s and multiple of 16。

 I don't think it is， so willll probably。Let's just fire this off and see if we blow up due to stack alignment。

All right， we didn't blow up due to stack alignment。But。I don't think。

Let's get rid of this recursive call。Because I don't trust that。Right there， okay， we break at。

Come out and break。Break。Challenge。Disassemble。Challenge， break at challenge plus 147。Get there。

Alright， let's step through this whole thing。 There's my stage one。 There's my pop RBP。 There's my R。

 There's my leave。 There's my R。 I'm now in my， I've now done the pivot， and that's because RP。

Is now pointing to something in。The elf。Probably in the BSS， so now we step through our stage two。

 we pop ourDI。We have a bonus rat。We are going to trigger puts at。PLT， I want a Finnny from puts。

Cannot break at 0。Whi去。It's probably because。There's no gadget there。 There's nothing。

We don't know where we're finishing too。All right。Right， right。Raned， we are inside puts， we finish。

I said fault。But。Did I put something？I think I did， that's my back race on this。I'm Anne， no man。嗯。

ちちゅ。ままだ。嗯。When I jump there， that's assume that there's a call。H。Might be。

You're trying to do math twitch， don't don't do math on me。All right， I believe in the power of GDP。

Let regret pop pop rat。Or inside cuts。You know， let's just step through puts。Just for the meme。

See if I get trapped and puts again。ItPs us happy， I just want to get to the rat。

I'm assuming that we're getting there。Okay。Okay， we are getting where I was expecting。Okay。

 so the rock chain is successfully calling puts。We aren't seeing。Anything being printed there。

 which is its own。Kind of WTF。It was in theory that should be what print F is is print F like。Oh。

 I'm consuming it。Here is that。Okay， I'm already consuming it， yes。All right。

 so my stage two is that's why I'm not seeing it in here。

 my this is where reading my own exploit would be useful。嗯。Right here， I'm。

cending the first payload right， which causes the second payload。

 the second payload is is putsing on print F， and then I'm receiving the six bytes of print F down here。

 which I then unpack into LipsC print F， and I print the address。

 which is what we see right here from the exploit， which does match what is actually occurring in the binary。

So I did it， I did it and I didn't know I did it。But that was。Um。

 can I explain why there's two pop RDI in a row， yeah， that's pretty easy。

 I put two pop RDIs in a row。Like I just put that there so there was something there。

I probably didn't need to， but it's something where're looking at。GDB。

This is clearly not a normal thing， right， this is my gadget。小で。

that's why you like build a custom custom demo， you know， custom example binaries where you're like。

 okay， this is a nice example of one thing Yeah， just something nice for me to spot yeah。Um。

 that way， when I got to the end of Put year， I know I'm going to my gadgets。But the。

A happyy little accidents， right I don't know。How useful it was for。The pivot bought。Just。ちち。

 what am I breaking at challenge？This civil challenge break at。Challenge plus 147。

 so the actual pivot occurs in my payload one。Which is what I have。Going down right here and this is。

Three gadgets， I have some paddings that I get to saved our IP。My pivot。

Is it doesn't have to be these， but this works for this challenge pop RVP。

And then I have the address of eight minus or eight bytes behind where I'm trying to go。

Followed by a leave gadget。And if we step through that， initially， we see that RSP。

Is in a same place the stack pointer points to somewhere that's on the stack。

We step to these gadgets， we pop RVP and so right now RVP now holds the。

placelace that I'm trying to pivot to。Leave is the mission critical gadget here。 Fortunately。

 leave Re is pretty much in every user land binary。 so leave rent is something that you can。

Absolutely fine to recap leave。Does these two things in this order Lee will move RSP RBP。

 This is the thing that I care about because we set RSP and I want to take advantage of this part of what Lee does。

 however， I still have to deal with the pop RBP， the fact that that other part occurs。

 and the way that we deal with that other part。Is。By。

Making sure the value that we are setting RBP2 here is8 behind what I'm actually interested in because it's going to pop off the first thing。

That。Is loaded into。RSP。Which means when I step through this， so we hit the leave。Now we look at RSP。

 all of a sudden RSP is this global buffer for me and I ended up having to set it to global buffer plus 200 that was solving its own problem。

But it was at least an interesting problem and so now we see RSP points to a readwrite re of memory inside of the elf that is really all a stack pivot is just getting RP to point somewhere that you are interested in。

where you hopefully have other gadgets， right getting RSP to point somewhere where there are gadgets that either you control or you are extremely interested in running the problem with doing a stack pivot。

As we kind of saw as I was stumbling my way through this since this wasn't。

Instead of specifically to be a stack pivot， the problem is maybe your pivot doesn't align， right。

 And this， this isn't something。This can happen even if you're doing a normal ro。

If you're calling in Lib C， there are Lib C functions that can require the stack to be aligned by 16 bytes。

 you can solve that by inserting just a RE as a gadget， it's equivalent to anob。

 and that will offset the stack by eight bytes。But if you're pivoting specifically。

 you can get into these weird scenarios where since RSP is already pointing to your RSP is now pointing to a regen of memory that was not intended to be。

😡，Use as the stack you as the stat grows and shrinks because it's just going to keep functioning like the stack pointer is going to keep functioning like a stack pointer when somebody pushes it's going to decrement when when something pops。

 it's going to increment。You can get into weird edge cases， which we happen to run into。

While going through this。So it wasn't the cleanest thing， but hopefully at least in the recap。嗯。We。

 we got there in a or we ran through it in a clean manner。

 Does anyone have any questions about the stack pivot because since that was。

What everyone was looking at， Twitch says that they did learn something interesting about stack pivoting today。

Yeah， you know， and a lot of this that that's why I kind of stress first principles like in general is。

If you understand what a stack pivot is， which is just setting RP。

Then you can reason about why something exploded。Versus if you're like， hey。

 there's this magic pivot function。Or it crashed and I don't understand why。I was able to。

 if I didn't have the ability to use GDP。To like fix this。Or to look at it。

 it would be very hard for me to reason about。Well， what the heck is going on here， right？

Like I would just assume that like the binary is broken， there's something horrific going on。

 but if we think from first principles， okay， well， I'm getting a Seg fault， I'm in GDP。

The construction that I'm setfolding on is a push。 How is that possible， Well。

 the only thing we know what push does push。Derements RSP and then tries to write to it。

 so then we want to look up here， we see RSP is whatever this is。And then we VM map RSP。

 and we see that we've reached the edge of this readriable page of memory。

And so from first principles， we were able to reason why are things exploding？

Um that's why I really stress。Trying to think about things at their like lowest level or their most basic implementation。

 because without that I wouldn't have been able to carry on from this I just be like oh。

 this binary is cursed， I have no idea what's going on inside of new do right。

So another happy accident。

![](img/b704f178700fb5c05ee8bdda43680e67_11.png)

I appreciate everyone hanging out， I got no questions from Twitch。

 I'm going to just take at least the second half of this evening stream。

 smack it on at the end of the YouTube video， it will not necessarily be in a direct continuance。But。

That's what's going to happen。With that， I'll see you guys on Thursday。So good luck then。

Goodbye and good luck。