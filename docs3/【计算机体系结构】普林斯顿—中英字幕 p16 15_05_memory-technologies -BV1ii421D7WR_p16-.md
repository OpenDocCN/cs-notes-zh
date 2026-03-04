# 【计算机体系结构】普林斯顿—中英字幕 p16 15_05_memory-technologies -BV1ii421D7WR_p16-

![](img/6893decb90fb4f51d0955450cc641ba5_0.png)

Let's start off our。Third topic so far in our review of computer architecture。

 So this is still review at this point。 As I said at the beginning of of this class。

 If you know everything up to this point in the class。

 that's a requisite or prerequisite for this course。

 We're just trying to blow through everything you should know in order to start the much more detailed content later in the this course。

 where we talk about real processors you're gonna be building。 So things like out of order， multiis。

 Multi corere or microprocessors versus simple little processor you should have built in previous classes。

So this is E Lee 4，75 at Princeton University。 We're talking about computer architecture。 And today。

 we are going to be reviewing。Cashs。And this is the last topic cache review。

 as I said before we move on to new material and the new material we're moving on to very soon is superss or processors which can execute multiple instructions per cycle。

So let's take a look at the。Agenda for。The cash review lecture。

We're going to start off by talking about memory technology and motivate the different。

Or start off talk about memory technology， and。Use that as a motivation for caches。

 So we're gonna look at different types of technology， D Ram versus S Ram。

 what the transistor technologies are behind them versus or why we have these different memory technologies。

 Why dot we just have one， Why are there different ways to store information。Why。

 why do we just use register files for everything or simple flip flops for everything。

Then we're gonna motivate cache design or why we have cache is。 So let's define what a cache is。

 A cache is a little piece of memory that you stick next to something which does not have all the information that you're trying to store。

 Instead， it has a subset that information。 And hopefully。

 it has a useful subset of that information。😊，We're then going to talk about classification of these different caches。

 So we'll put names and labels on sort of。Different cache architecture。

 So we're gonna talk about associivity of caches。 We're going talk about size of caches。

 We're going talk about。Whether the cache has multiple things that could fit in one set or not。

 and we'll talk a bunch more about that。 and then we'll have a very。

 very brief introduction to cash performance or some of the things we should know about why caches give you good performance right now later in this course。

 we're gonna actually have two more lectures about advanced caches， advanced caches。

 we're going to talk about more sophisticated topics with how do you build and implement actual caches for very high performance processors。

So let's start talking about memory technology。Okay。

 so let's look at a memory or something that can store multiple values and give us back some data。

So here we have a very naive。Flip flop based register file。

 You'd probably never actually build this in a modern microprocessor。But let's。

 let's look at that sort of conceptual idea here of what a memory really is。

Here we have four entries that are flip flops。 Maybe it's multi bit wide。 So it's maybe。

 I don't know。 Let's say these each of these registers are 32 B wide。

 and each of these buses here is 32 B wide。And we're gonna sort of select based on a readdress。

 some value。 So we can choose， you know， this is 2 Bs here。 You can choose out of one of four places。

We have right data that comes in， and we just sort of broadcast that to all of the registers。

And we write， depending on the right address here and the clock。 And， you know， if。

 if the decoder tells us to light this up and the clock clocks the actual element。

 it'll load in the value。You may even have a write enable on something like this where that would also feed。

 let's say， into the and gates here。 So it'll say， if a rights's not occurring。

 don't actually load anything into these registers。 Okay， so that's really， really naive。

Let's look at something a little more complex and how these things sort of start to actually actually look。

 Okay， so that we're gonna to transition from talking about this naive register file and see what people actually build。

And the first thing you should realize is。If you go to build something that's an naive register file。

 you have lots and lots of bits as you add more and more bits here here， we only have four。

 But if we go to 1000 B。Register file， this multiplexer grow really big。

 And if you stack these all up1000 long， your aspect ratio， your X versus y or the size。

 when you go to lay it down on a piece of silicon is， is very long and very narrow。

 So you'll end up let's say with 1000 Bs，1 B tall。And that does not lay out very well。

 And it's not necessarily good for speed。Or from an area perspective。So why is it not good for speed？

 Well， it's not good for speed because wire wires have costs and take time to propagate。

 So you have to propagate from 1000 bits away or 100 bits cells away all the way over to the multiplexer。

Your cycle time is not going to be very fast versus if you were to somehow make it more square or more rectangular。

 the distances actually are minimized。So this is how we end up with。A raise。Or memory arrays。

 And we're to look at a memory array for register file First， Let's look at a register file。Aray。

And how you could possibly actually go build this， because it's a little bit different。

 We're not gonna use fully complementary logic here for everything。 Instead。

 we're gonna to start to transition to something where we will have more of analog circuits connecting our bits to respective buses。

And we're also going to change how we do the decode。诶。

We're not gonna to have a full multiplexer here or a full decoder here。

 We're going to split that into different portions。 So here we have an example array。 It's a square。

 And we， each of these little boxes is a single storage element。Bit cell。And。

The address comes in here。And that goes up into a row decoder。Which will turn on one of these。

Wiires at a time， and these are called word lines。😡。

And we'll have both read word lines and write word lines。And this is still just for a register file。

But we're actually going to split out some of the bits here。Of our address and send it over to here。

 which is the column decoder。And that's going to choose。 This is。

 this column decoder is just a multiplexer。Very similar to this multiplexer。

But it's going to only have a subset of the bits。 instead of having all of the bits that are together here going through this。

 this multier and having n bit address coming into it instead has a subset of that。

 So in this diagram here， we have a4。诶。Bit wide read out or write。 And we're going to have 1，2，3，4，5。

6，7，8 bits in。Bits across here。 So we're gonna need a 2 to1 column decode。

 So this is a 1 bit decode here。 But as， this is just a toy example。

 you go to build sort of thousand B arrays or megayte arrays or gigabyte arrays or gigabit arrays。

 we're going to have lots of bits coming here and lots of bits there。

 But the the idea wanted to get across is you split off。

A portion of the address to the word line creation and a portion of the address to your column decode here。

And in this register file， I wanted to just sort of walk through。What this diagram over here。

 the circuit little diagram is。Here， we have。Two cross coupled inverters。And as you'll see。

 where we don't have full complementary logic connecting these to things。 But this is。

 this is a stable storage itself。 If you give us power， it'll store data。If we wanted to a read。

We need to connect the output of this to read bit lines。

 and these read bit lines of these vertical wires running here。And we're gonna use。

 we're gonna do this with effectively a passcade here。 When we energize the read word line。

 it connects the output of。This gate。Or output of it's going to be this inverter here to the read bit line。

And if we want to do a right。We're going to turn on not the read word line， our our WL here。

 but we're trying the write word line， WWL。 And what that's going to do is it's going to connect both the Q and Q bar。

To the right bit line。And now we get into sort of some analog magic here。

 But in order to have this work， what we're gonna do is we're gonna put。

 we're gonna energize or or ground the right bit line so that that it's stronger。😊。

Then what's going on of these two or stronger than what either these inverters can drive。

 So we overpower the inverter， and we can flip it。 let's say， from a 0 to 1 or a1 to a 0。

So this is not traditional sort of complementary logic。

 but this is how we typically build register files， small little arrays that are close， let's say。

 into a processor。Now， let's move to something a little bit larger。 Were gonna look at。Memory race。

So these are things like S Rams。 So we go from register files。

 something that we'd hold our general purpose registers for our processor in。

And we're gonna move out a little bit and talk about small arrays， something like caches。

 maybe a kilobyte of data。And these are typically built out of S Rams。Same structure。

We're gonna change the cell a little bit here。 The main difference is the cell。 we're gonna have。

Two sets of bit lines。We're going to have。Bit and bit par。

And then we're going to have two passscades here， and these are crosscod inverters in the middle。

And by doing this， we also have this， this word line running the other direction。

 which connects this crossco inverter to the bit lines。By having these S Ram arrays。Typically。

 what happens is because the。Because you have bit and bit bar。

 you can have these be even weaker than normal。And when you go to build something like an S Ram down here。

 in addition to the column decode， you're also gonna to have what are called senseamps。

 These are basically operational amplifiers where you hook the bit and the bit bar to them。

 and it can sense a very small difference between bit and bit bar。And by doing this。

 you can effectively have a very low difference between bit and bit bar。

And be able to sense it at the at the other side。And one of the differentiations I wanted to make between a register file。

And this S Ram here is that the moisture files。Many times are' designed to be sort of multiported。

But in this diagram here。These bit lines get reused。 They are both read and write bit lines。

 So we've effectively built a single ported S Ram。 Having said that。

 people do build multiported S Rams and single ported register files， but。Conventionally， you。

 you build a register file when you need speed and you need lots of ports and you build an S Ram when you want to be。

More dense in your storage。 Okay， so now let's move。To。

A piece of technology that is in all of your computers。

 or register files and S Rams are all in your computers。

 But this is something that you can actually like see becauseuse usually the S Rams and the register files are all integrated onto your centralized microprosor。

 You don't actually get to go see it。But here we have。A stick of DRAM。So let's see what this is。

 This is PC 100 D Ram。 And this is old stuff。 This is 1 28 MBby of Ram。Nowadays， your computer has。

 at least this laptop here is 4 GB of of D Ram。And different people， different amounts。 But Dr Ram。

I want to contrast with SR， you still go and build an array out of it。But。

The actual storage looks very different。The bit cell storage。

 instead of being some form of cross coupled inverters。Instead。You're going to have one transistor。

Which hooks a capacitor into your bit line。Now， you may ask yourself， how do you build a capacitor。

Capacitor， typically， you need， you know。Two plates or two pieces of metal with some dielectric in the middle。

We can store charge。What's inside of that Ram？Looks very odd。 It is a capacitor。

But it's a very oddly shaped capacitor。Typically， what will happens is you build these very。

 very deep trenches。very。Long and skinny trenches because you want they skinny because you want to put them very close together。

 because if you want gigabytes and gigabytes of Ram， the smaller you make it。

 the more you can shove on a single piece of silicon。

But you have these really long and narrow trenches here， and you have。

Two plates of metal and then a dielectric in the middle。So in this case here， we have。

 I think there's two metal sort of plates here。 and then there's some dielectrics sort of shoved in between there。

 but you can't really see it on this picture。And then all the actual logic。Is up here。

 So in this diagram here， this is the transistor。And doped and doped。 And here's the。

 the depletion region。 And here' is our word line。 But basically， that's。

 that's this transistor here。 So we're gonna be connecting the。Capacitor。

 which has a very funny aspect ratio， very tall to this bit line。 And， and to give you some idea。

 this is a slice through this the silicon wafer。This is not a planned view or top view。 top view。

 you would just see the Well it looks like a transistor and then some poly plug here running vertically。

 it would look really small。 But this is a slice。 And the reason we do this is because we want to see that the actual capacitor is very long。

 very deep。Into this。And what they wanted to point out is this is typically really hard to go build on your standard sea mos process。

 So this is hard to go build on something a logic process。 You have to go build this。

 let's say in a special D Ram only manufacturing process。 So you want to。

It's sometimes hard to mix that。 There are some technologies which allow you to mix them。

 But when you do that， people haven't really designed ways to make them as small。

 The D Ram cells as small。Okay， so， what are the advantages of DM。

 Why are we even talking about DRAM。Well， it's a lot easier in DM to have large amounts of storage。

 You can have big amounts of storage in the same area， because instead of having， I don't know。

 in S Ram。6 or 8 transistors for each cell。 Instead， we now have one transistor in one capacitor。

 So it's actually less。Now， how does this circuit work？Well， logically。

 what we're going to do is we're going to store。Data or store charge in the capacitor。

 So we're gonna connect the capacitor to the bit line。

 We're gonna either put a one or a0 on the bit line。 and then we're gonna disconnect it。

 and it'll hopefully store the charge。 And at some point in the future， we're gonna connect it。

 and we're gonna discharge it into the capacitor into the bit line and read out the value。

And we still need something at the bottom here， which is very sensitive to be able to read out this bit。

And the reason is because the capacitance that you can store in one of these little capacitors is a very small amount。

 So there's not a whole lot charge in in the circuit。Okay， so what is the cell， What's。

 what's the problems with this。Well， first， one of the major problems of this is you're gonna end up having。

This capacitor discharged and charged。And capacitors， as you may recall。

 don't always store their charge that well。 They might slowly lose that charge over time。

 And what this turns out to be is you're actually gonna have to refresh the D。

 So you might have heard of D refresh。 But typically， you know。

 in a modern modern day computer your your Dr will only hold the data for maybe a few seconds。

 It used to be that it only held it for a few milliseconds。 Most Rams actually decent now。

 And you've probably seen some attacks that people have built around this。

 like there's some encryption attacks where people will effectively turn off a computer and then pull the Ram out and stick in a different computer and the Dr will still hold the charge。

 still hold the information even if you remove the electricity or remove the power from it。

 because this is a bunch of little capacitors that will store that charge。

 that's a funny little case where this Drra ends up being a negative， but we're really doing this。

To have more space to store data， because each of these bit cells is a lot smaller。Okay。

 so I like this diagram this is。One of the more key diagrams in today's lecture here is showing the relative sizes of SRAM。

Versus D Ram in different types of S Ram versus D Ram。 So let's start off here with。

An S RamM cell built out of logic。On a logic process or logic CMmoss technology。

So that's this one here。This looks to be。6 transistors， So sort of optimized SM monoologic process。

And。It's pretty big。Let's contrast that， though。With this one over here， we have Dr Ram。

On a memory specific process。And it's tiny。So， it's not only。1 transistor versus 6 transistors。

 It's actually more than six times smaller because they can optimize it because they can go into the Z dimension here。

 go into and out of the of the board because that's。

 that's that that trench capacitor goes down into the substrate。And some other interesting things on。

 on this diagram here， we have。A D on an AsI process or DRAM on a traditional ASI process。

Which is here。呃。Here we have 6 transistor cell with local interconnect。 It's a little bit smaller。

 So what that means by local interconnect is you can use the polylay of your process or the polysilion layer to do interconnection。

 So you don't have to use wires for everything。 So it gets a little bit denser。

 the layout gets a little bit denser。 And I really like this bottom one here。 Yep。

 the bottom one labeled a is not。Its not four different things。 Instead， what that is。

 is this is a fully compliment logic cell。A storage cell built out of gates。

 So there's some number of gates put together here。

 So this is what thiss trying to get across here is that the addition of。Custom logic cells。

This one or this one storage cells in your library is really important。Because otherwise， you're。

Ram's going to be a lot， lot larger， or you won't be able to fit as much。Memory on your machine。

 Okay， so to wrap this memory technology section up， I want to talk about some of the trade offs。

 And computer architecture is all about the trade offs。And why would we use。

One type of technology versus another type of technology。 So what are our trade offs here？Well。

 we can go from。Fast， close， small things。 So things like latches and registers。

 at least sort of put them together into bigger。 we we put together into bigger things like something like a register file and then S Ram and have different technologies even。

 And as we sort of fit to bigger and bigger memories。We got a lot more capacity。

 but it takes longer to access them， kind of by definition。And typically， we have less bandwidth。

But if we have small things， we have low capacity。Low latency and very high bandwidth。

So it's sort of a trade off of capacity versus the other positive aspects。

And depending on where you put it in your memory system。

 you might want to trade these off differently。

![](img/6893decb90fb4f51d0955450cc641ba5_2.png)

![](img/6893decb90fb4f51d0955450cc641ba5_3.png)