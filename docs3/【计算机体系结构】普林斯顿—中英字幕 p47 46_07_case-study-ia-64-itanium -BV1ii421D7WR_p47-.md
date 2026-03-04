# 【计算机体系结构】普林斯顿—中英字幕 p47 46_07_case-study-ia-64-itanium -BV1ii421D7WR_p47-

![](img/debc07c82f6d6e93f375b12867191932_0.png)

Okay， so I wonder just。Briefly。Give a case study here of one of the more interesting。

Modern day V I W architectures are probably the most famous and possibly also the most infamous VL I W processor out there。

 This is the Intel ittanium， also known as the Intel IA 64， or was known as an epic processor。

 explicitly parallel instruction computing architecture。And a lot of this work actually。Was done。

In collaboration between Intel and HP。😡，HTP uses these lot in their big servers。

 They're sort of big main。 Well not quite mainframes， but big， big， heavy， big iron computers and。

Intel was trying to use this to effectively kill all of the other workstation vendors。

 And this was going to be their 64 B solution to computing。So it's a modern， non classical UIW。

And this was going to be Intel's chosen IA。 There was they were they were going to deprecate X 86 and choose IA 64 as those 64 bit ISA。

 And as we now know， going a few few years forward after the creation of all this stuff。

 that didn't really happen。 Intel went and did this。

 It built a bunch of processors with this instruction set。

 You can still buy processors with with this instruction set。

 but it never got as as good of acceptance as the competitor， the competitor is。

What at the time was called AM D 64， which is a 64 B extension to what people already had。

And that's what people ended up wanting。 It' is a 64 B extension to what we already had versus you know。

 something totally different。Okay， so a couple features here。 It's object code compatible V I W。

 So it's not quite a V I W in a classical sense。 It's object code compatible， which means。

Different generations， different micro architectureits of this V I W can have the same。

In instruction code in the same binaries， in order to recompile and how they did this is effectively。

 as as I alluded to before， they had。The ability to have perilisms straddle across instruction bundles。

And they have this notion of groups， which we'll talk about in a second。

So first few implementations of this， Merced was the first Intel ittanian implementation。

 It's kind of like the 8086 for X 86。 but Merced as lots of things。

 you'll realize if you look at Intel code words and Intel code names named after a river。

 Intel likes to name their things after either rivers or places。

 I think this has something to do with you can't trademark a place name so they just sort of get around that and make sure they don't have any。

Trademark issues by choosing place names for all their code names。One of the big problems here。

 it was supposed to ship in 1997。First customer shipment， not until 2001。It's a four year miss。

And superscales another thing sort of had caught up on it at the time。

 And it was supposed to be faster and better than everything else。 And the first。

 the first one was not very good。 It had low clock rates and was not as high performance as it was supposed to be。

 And sort of the， the。X 86 side of Intel's business line actually had almost the same performance as as the first titanium。

 and then very quickly surpassed the first titanium。

 So their high end processor wasn't actually very high end。Coup， couple other things here。

 So McKinley was the second implementation shipped pretty quickly after that。

 This was much better implementation， but。You know， it's still， still hard to do。

 But we're still buildinging these things。 So in 2011， at ISSCC。

 the Intel introduced the Pulsson processor。Big， big machine here，8 cores and 32 nanometer。

 lots and lots of rael。We'll look at that。 Yeah， So， so 32 MB of shared L 3 cash。Big， big processor。

544 square mm in 32 nm。 So at the time this came out。This was the biggest processor ever built。

Most them are transistors， So over 3 billion transistors， or at least the biggest commercial thing。

 Intel might have had a research prototype。 I think that might have had more transistors than this。

 I think theyre。Multi corere processor or they call it the SCC。

 their single chip cloud computer might have had more。

 but I't actually know their transistor account， but from a commercial processor perspective。

Huge chip。But they're selling into extremely expensive sort of sockets。

 the sellingship for premium is going into big mainframes。

 That was not where this was originally detined for It was detined for both big mainframes and workstations。

 But now this is sort of the in 2012 standing here now， this is not used in lots of other places。

 except for sort of bigger， bigger hardware mainframe sort of things。

 So few interesting things here is the。Cours are multi threaded， and you can execute6 instructions。嗯。

Or you you could fetch six instructions per cycle。And you can execute up to 12 instructions per cycle。

Per core。 And then there's8 cores。 So this is a beast of a machine， very。

 very high performance computer。Okay， so let's dive into some of the details here of itanium。

Itanium has 128 bit instruction bundle。And inside of there， you can fit the three。Operations。

 and then there's some what called template bits， which sort of say it says what is in the instruction bundle。

 So it's not actually a fixed format bundle。 These instruction boundaries can move around a little bit。

 And they did that so you can sort of mix in。Something like a immediate instruction with an instruction which doesn't have immediate and get more space in in the bundle for the immediate bits。

 So you can have or branch offset or something like that。

These template bits also describe how a particular。搬到。Relates to other bundles around it。

 So sometimes these are called begin end bits or start in stop bits。 So it says。

The number of instructions， which can execute explicitly in parallel。

And the machine doesn't necessarily have to execute these in parallel。 So， for instance。

 if you say 20 instructions can execute or 20 operations can execute in parallel， but。

Your machine is only too wide， or they build a too wide implementation of ittanium or IA 64。

You just are going execute， you know， too wide for 10 cycles or something like that。

 But what's really cool here is the compiler is able。

 just like all the other VAWs to express the perism to the machine explicitly。😊。

Some interesting things about the registers。They， because this is a V I W processor。

 and because you're gonna have to do code scheduling， like what we saw in last class。They， and that。

 that increases the。General purpose register pressure， you don't have a register namer。😡。

So you can't go and use different names for things。

 And the hardware is not going to rename things for you。 So instead。

 the compiler and the software have to do the renaming。

 So they had 128 general purpose registers and128 floating point registers。

 And they also had these predicate registers。So they're not quite full predication。

 but they're pretty close to full predication。 So you can have bits that say whether later instructions are going to execute or not。

 And you have to compute that into a little register file。

 So they had a preddicate register file that you have to bypass。So that's。

 that's sort of interesting to see。 And then they had the a really interesting feature here。

 which is called。Roating register file。 And's let's talk about what a rotating register file is。

So the problem this is trying to solve is in a code sequence as we solve in last lecture。If you have。

If you have a。Very long instruction word。Scheduled piece of code。

And you want to get good performance。 You're going to have to unroll the loop。

 and then you have to software pipeline the loop。But when you do this。

 this is going to increase your register pressure or increase your register names。

 how many register names you need to use。And。As we saw。

 you're gonna have to add extra special code in the prologue and the epilogue。

 which are different than the main loop body。So how do you solve this in one fell swoloop well。

You add a subset of your register space。Which will sort of statically rename itself every。

 every loop iteration。 So slightly change the， the， the loop iteration or change the。

The naming of the registers and what this looks like。Is if you go to access， let's say register R1。

There's a register。Sort of a architectural enabled register called the Roating register base or RB here。

 which has a value that gets added to this。 and it it's modular arithmetic。

 So it rolls around at the end。 and that points to different locations in the physical register file。

Oh， this is pretty cool。 So what we're going to do is every single time we come to a new loop iteration。

😊，We are going to change the RB， and it's going to point at a different set of registers。And。

We can actually， effectively software pipeline。Just by using this one feature。

Here we have the same code sequence we had from last lecture。So is the previous code example。

And if we recall， when we unrolled all of this， what we ended up with was。A load。An ad。A store。

We'll talk about this in a second。This was kind of the， the， the。

 the key thing we were trying to execute。 And if we have to unroll this。

 we had to unroll the code and then look at the dependencies。 So let's look at the dependencies here。

Well， dependencies they're going to have is this load writes。F1。Or the floating point register。

F1 here。And。We know that。This is actually going one get red。

 Let's say the lane sea on this is one to three cycles and doesn't get red till here。Likewise。

 this ad here computes。P 10。And the ad， let's say， is a floating point ad， it has some long latency。

 and down here is when it's ready into the store。So on something like a I Tium with a rotating register file。

 we don't actually。Generate all this code。 Instead， we generate one instruction， this。

 which is gonna take care of our epilogue， our pro， our prologue， our epilogue and the main loop。

And what we're going to do is we encode the distance in register numbers。

Between these two values here。So what this means is if this writes F1。And 1，2。

3 loop iterations in the future want to read that value。 We encode that here with a register number。

 That is that number off。And then likewise， here。 So this would be F1 to F 4 because it's off by 3。

 And here， this writes F 5。And we know this wants to be read 1，2，3，4 later。

 So we encode it with a register number that's。Forwards of the future。

And now were going talk about this instruction here。

 So what this is going to do is it's going to change the routine register base number or the RB。

 And it's going to bump it by one。 So we can basically just keep branching to itself here。

And each time we do it， all the registers are going to change names。 So by the time。This is ready。

By time the load is ready here。These other values will have sort of caught up with it where the physical register that they're actually going to look at will now point to the correct location。

So we can effectively encode into one instruction here， all of this。

 including the prologue and the uploadlo， using this protein register file。Okay。

 so last slide of today。Why do I think？Itinium， I think we could pretty confidently say， failed。

I actually don't think it was a lot of the ideas。I think some of a lot of it had to do with the implementation。

 So first off。If you tie the hands of the micro architectitect。They're going to scream。So。

IA 64 added a lot of。Architectural， big a architectureecture or IA level features in order to get lot of the speculative parallelism。

 And a lot of that stuff was implemented and talked about。

 but never actually built in real processor。 So people didn't go through the effort until basically the first titanium to try to implement some of these things。

 And they didn't all mix well together。 And they added a lot of states and they added a lot of complexity to the processor。

 So we have ala full predication or almost full predication。

 rotate register files to name a few this is really complex bundling sequence。

 probably one of the hardest to decode instruction sets in the world。Very， very challenging。

 And this was a big， a big big challenge。 and its it。Tide the hands， the micro architectitect。

And the micro architect couldn't make decisions。 So a good example of this funny funny story here is that。

After the。Deck alpha。Employees， digital equipment Corporation employees left deck and were sort of assumed into a part of Intel。

 That same team that used to build out of order Al processors went on to go build sort of the next next generation of an ittanium processor。

And what they said is they went to go look at the itium processor。 and theyre like， wow。

 this is really complicated。 took much more complicated than alpha。 And then they said， oh。Well。

 we could probably do better if we just built it out of vote superscalear。

 took apart all of the instructions， took apart all the dependencies。

Poured that data into what was effectively an alpha out of our superscalear core。And then execute it。

 And what was funny is you go look at this is like all the people you sit there just bang your head because you did all of this work and added all of this architectural state。

😊，To allow the compiler to do all this， this work。 And then they would just wanted to undo it all。

 they would did this because they wanted performance。

 but then they wanted to undo all of the sort of state and all of this hard work the compiler did and just redo it all dynamically。

 because they thought like youd get better performance。 They probably could have。

It probably was a good idea， but it was kind of funny there is you built an instruction set that had one micro architecture in mind。

Basically， an in order architecture。And then all of a sudden。

 people are thinking about building out of order variants of it。

 And it sort of throws everything you had before away or all these notions sort of went away。

So its just just a funny story there that， you know。

 people tried to build out out of our versions they ultimately not did not do the end up doing that。

 That same team decided it was basically too hard， mostly due to predicate registers and sort of how to bypass predicate registers of out of order or things。

 And I think they ultimately ended up not not doing that。 or they definitely ended up not doing that。

And thats what's sort of known now as the would choose it or what Earths community nothing would choose it。

 It's known as the Tuuckwilla processor from Intel。Another other couple of problems here。

 First implementation at a very low clock rate。 So your first one out the gate just was not very good。

 This， this sort of hurt。 and it was， it's hard to build these things They're wide。

 The the speed demons versus the sort of brainiacs。 This is this question of you want to go wide。

 or you want to go long and narrow。 long and narrow was doing okay at the time。 Big code size bloat。

嗯。Fundamentally did not solve all the dynamic scheduling problems that out of our superscaler could get at。

 So， for instance。Branching or changing your instruction schedule based on。

Based on whether a load hit or missing in the cache， they couldn't do。Big compiler complexity。

 you need profiling and not everyone wanted to profile。

There was also just not that much in static level static instruction level app perism in all programs。

 So the compiler couldn't necessarily find all apparilism， or it wasn't there statically and。

If you're going for a compiler only approach， you need to be able to do that。

 And then this is what really killed it here is the people did go build these more complex out of our supercals。

 So at the time， there was this big discussion， can we build more complex out of our supercals。

 And people said， no， those are too hard。 They're too hard to build They to take。

To they cost too much。 We don't know how to solve all these problems。 So instead。

 we'll try build something simpler and push a lot of the complexity into the compiler。Well。

There was money behind this question。 So people went and did build these complex Auto ofvo supercals。

 And that's what we're basically still using today。 in our sort of desktop processors。

 We have out of our superss today。And then finally， the last big one here， AMD64 happened。

What is AM D 64， Well， it's a 64 B extension to X 86。 AM D originally did this。Intel。

 after started dragging their feet for a couple， couple years on this， finally decided， oh。

We're gonna， we're gonna use that because people wanted this。

 People wanted code compatibility with the ability to do 64 bit， sort of wider。

Both arithmetic operations and wider address addressing。

 So more amounts of memory and 64 bit is a lot of memory。 So A D originally came up with this。

 This is now known as， I believe， E T 64 or Intel 64 not to be confused with IA 64's what Intel calls now the 64 B extension X 86。

 and now Intel is building those processors too。 So everyone has sort of jumped on that。

 And that's and Intel is kind of deemphasized itanium now and the itanium instruction set。

 And instead we're basically sticking with IA 64。 and this instruction gonna IA 32 the 32 B X 86 with extensions。

 a 64 B。 And you know， that's that's taken over the work workstation market。

 And was kind of funny here is this was this processor was really designed to kill or unify all of the。

😊，Worktation vendors together。Under one processor that was going beat them all。

 And and it did its goal to some extent， because this processor was coming around。

 Either companies went out of business or they jumped on the IA 64 bandwagon and decided they were gonna to take that on。

 But what replaced it replaced all of the different little variants of processors that were in workstation。

 So Sp P risk and for H P。SG， SG I sort of mips processors。 Id already say spark。 Yeah。

 all these sort of other different things are empower powered by IBM power is still around。

 But a lot the other ones sort of died through atrition or moved on to I。

 were supposed to move on to I 64， but I 64 did not end up winning this。 Instead。

 we replaced it with 64 B X 86 processors。 So it sort of did his job。 It killed the。

Killed the workstation processors， but replaced it with not itself。

 It ends up replacing it with something else。Anyway， we're gonna， we're gonna stop here for today。

 and we'll， we'll talk more next lecture。

![](img/debc07c82f6d6e93f375b12867191932_2.png)

![](img/debc07c82f6d6e93f375b12867191932_3.png)