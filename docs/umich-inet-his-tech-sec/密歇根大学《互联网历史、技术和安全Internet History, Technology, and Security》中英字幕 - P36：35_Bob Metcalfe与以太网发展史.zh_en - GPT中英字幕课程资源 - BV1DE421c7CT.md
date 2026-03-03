# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P36：35_Bob Metcalfe与以太网发展史.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

🎼你是。🎼Yeah。🎼こ。🎼，🎼こ包。I was extraordinarily lucky。And happened to be at the Xerox Research。

 Xerox Palo Alto Research Center。When a problem evolved that had never before occurred。

 the problem had never occurred， and that was the problem of having a building full of personal computers。

And I was a networking guy， so they turned to me and said。

Networked these puppies and we had just finished。Starting the internet was then called the ARPpanet。

Which was packet switching。And it was pretty clear we wanted this network to connect to the it wasn't yet called internet thing。

 so it would be packet switch， we're pretty sure。At the same time we were building arguably。

 I don't want to get into that argument， the first laser printer， which in our case， the first one。

Whose name wasE， that's a whole other story。It was a page per second， 500 dots per inch。

 and if you do the math， that's about 20 megabits per second。

So the existing methods of interconnection had a lot of problems。One is they were all home run。

 so all these wires， one from every desk would all come to this one place in the building and put a big rat's nest。

 and called it a rats nest， by the way。Two is they generally ran at 300 bits per second。

 or if you really rev them up to go to 144 kilobits per second。

And that wasn't even close to 20 megabits per second。

 and we wanted to be able to keep the printer busy by sending documents from all these。PCs。

 which hadn't been built yet。Well it hadn't been built even at park at that point。

 so we were building the printer and we were building the PCs all at the same time。So i am。

Start work on this and there was a pre an effort before mine called Signnet at Park。

 and it was being done by Charles Smey， my friend。And but he wasn't a networking guy。

 so they sent me in to pick up Signnet from Charles and he was going to go off and do something else。

 and by the way the other thing he did is he wrote a text editor， a word processor called Bravo。

Which then became。Microsoft Office Charles。Is a billionaire， and he's been to the space station。

Twice， the international speed。So maybe I shouldn't have kicked him off Signnet。

 maybe I should have done Bravo， I don't know， anyway， so I immediately decided that Signnet。

 by the way， Signnet stands for Simonemoni's infinitefinly Glorious network。Was， in fact。

 infinitely glorious and much had too many moving parts to be a land。By the way， the word land。

Wasn't invented until 1990 and this is still 1973， so the word land was way in the future so that's netachism anyway。

 the signnet had too many moving parts for。A land。And it was in the course of investigating how to organize this land that I ran into quite by accident by a packet radio network at the University of Hawaii。

 it was called the Aloha Ne。And what was beautiful about the Oloha network is it solved a distributed problem。

That is how would we share a radio channel back to the mainframe in Hawaii at the university？

If we were just a bunch of terminals scattered among the Hawaiian islands。

And they couldn't really easily talk to each other。To get coordinated。

 how would they coordinate their sharing of this inbound radio channel？

And Norra Abramson there at the University of Hawaii devised this very simple randomized retransmission procedure。

A person would type， by the way， what they would type was a card image。

 was 80 columns wide back from the days of card batch processing。

So you would type in your card image and hit sendend。And then， your terminal would。

Send it in toward the mainframe and then would wait a short time to see if there was an acknowledgement returned on the outbound channel。

And if there was， everything was hunky Dory， but if there wasn't。

 that probably meant the two terminals had decided to send at the same time。

So then as many terminals as participated in that collision of transmissions would then randomize and then retransmit at a random time in the future。

 thereby if they overlapped here， they very likely would not overlap again in the future because they would choose different random numbers to count down。

So that's randomized retransmission， multiple access。

 So I since I was trying to avoid this big rats nest of wires and only wanted to have one wire。

 just one wire， not 16 or 32 or whatever the。Alternatives were just one。

I wanted a distributed solution to how to share this cable and the Aloha network produced that using randomized retransmissions。

So then I。Actually， you know。There's sort of two stories here。 One is a hardware story。

 about hardware。 There's a hardware story， and there's a software story。 and the hardware stories。

Not that interesting， but it's there。So one of the first things I did was to buy a kilometer of cable or maybe been a mile。

 I don't know if I'd gone metric yet， but so a spool of。

Collaxax cable about this big with the two ends。Sticking up。

 so I got a pulse generator and I hooked it up to one end and hooked it around back into the ocilloscope and started launching square waves down the cable and watching what came out。

 I thought that would be good preparation for building a network。

And what came out the other side wasn't a square wife。Sort of lazy rise times and lazy fall times。

But if you put a digital gate， you could recover the square wave that as you just said。

Use the digital threshold and so out of this gate came a squareway so you could recover at the end of a mile of cable。

 this square wave， so I kind of knew。I kind of had some confidence then that various stations connected to this cable could inject their square waves。

And the other guys could recover them。So that hardware。Wasn't that hard。

It was a straightforward so the first hardware was kind of relatively straightforward。

 very straightforward and the square wave， by the way， was called Manchester。

 what we'd do is we'd take the bit， we'd make a packet of bits and then we'd send them one at a time。

Down this cable， and we would encode them， and the encoding was also simple。

 It was Manchester coding， meaning for each bit， the first half of the bit would be。

The complement of the bit and the second half of the bit would be the bit。

 so you would have a transition in the middle of each bit cell。

 which is a very simple modulation scheme。So as you're sending the packet。

 the cable's wiggling and you can recover the signal at the other end and clock those bits into a shift register and then clock the shift register into the memory and collect a packet that way。

And that all took just some soldering to make that all happen。Well， I don't want to。

It got a little bit complicated when you wanted to put 255 of them on a mile of cable。

 you had to be a little bit careful about the impedance of the taps because the square wave coming by a tap might generate reflections that would then interfere。

But the beauty of Manchester encoding was that while you were sending a packet。

 there were constant transitions， so if you listened。

You could tell whether a packet was going by and you didn't have to listen for long。

 You only had to listen for about a bit time and then you which。

Which turned out to be 34 nanoseconds。So you could wait that long and tell whether there was a packet going by。

So one of the first differences between the ethernet and the Aloha net。

 there are a lot of differences， but one of the first ones was。嗯。Carrier sense in the Yoloha network。

 you couldn't tell if somebody else was transmitting at the same time as you。

 but on the ethernet you could and the advantage of that was you might as well if you're sending and somebody else is sending at the same time。

 you might as well give up because you've destroyed each other's packets so punt then that recovers that bandwidth it would otherwise be lost to just。

Continuing to transmit a damage packet。And the。The other thing was this Manchester code meant that the cable was on half the time and off half the time。

 that is the driver， sort of an open， what we used to call an open collector driver would either yank the cable up to three or four or fivevols。

 I even forget the voltage now， but it was under five， I'm sure that I had a rule。

 I never won above fivevols。You would yank the cable up。

 and then during the other half the bit when you weren't yanking， you let go。So for example。

 in each bit cell， you got to look。To see if anyone else was transmitting when you had stopped and if there was somebody else then you had a collision so that was a second feature so it was really a digital signal it was really a digital signal。

 it wasn' a modulated signal in any way well it was best you could send a digital signal over co on off with the Manchester encoding so the Manchester encoding is akin to a modulation scheme but it's the simplest one you can think it' very base。

Yeah it is very base band， but it's a sort of modulation scheme that a computer scientist would come up with as opposed to one of those fancy radio people and by the way I took a lot of gas from all those radio people why did you use such a simple scheme。

 you was you would have wasted all that band， you wasted all that band with that capable that cable was capable of carrying hundreds of megabits per second and you only carried 2。

94 what a waste of the cable。Well。There was plenty of cable to waste。

 so we've talked about carrier sense inclusion detection。

And the scheme would be that each packet would carry two addresses。

 the address of the destination and the address of the source。And each of these would be eight bits。

 and so on the back plane of the little personal computers with wire app。

 you would wire app in a code between0 and 255 and that would be the serial number of the machine。

 and then you would read that off the back plane and put it in the packet。

So each packet had two addresses， this is different from the Alllo one incidentally which had one address because the channel was only going。

There were two channels。So two addresses and we added。

Acyclic redundancy checkum on the end of the packet。

 which we implemented in hardware so that you in addition。

So you could tell if the packet had been damaged， so if there was a collision and the terminal。

 the contending stations backed off， there would be a hunk of garbage on the cable zipping around。

 but when it was received to check some wooden' add up and youd just throw that chunk of garbage away the day that I was launching pulses down this spool of cable。

I was doing some soldering。And I was doing some。Knife work to get the insulation off the copper。

And across the room was a young grad student who was doing something else。

 and he noticed me not being good at this。And it turns out he was very good at it because he had worked in a television studio and he had worked in cable television。

 so he knew all about skinny wires and coaxes， so he came over to help me and that was his name was David Boggs。

And then we started working together。And embedded Ethernet together。So he was and he was he was。

Slightly more hardware and I was slightly more software， but there was then a third guy。

who was even more hardware than David， who was the Picoferret guy。

 the guy who would put those last few passive components on the end。

 just be sure that connection to the cooxial cable。呃。

Would be clean for transmissions would every time you tapped into it。

 you didn't put a big lump of impedance on the tapping seems like a counterintuitive thing。To me。

 I mean think that I mean everyone would think that a star is the right thing。

 but you were going to tap into the just Well one of the problems we decided to solve was the ratsness problem we did not want a ratsness and every time we installed a new PC we didn't have to home run a cable back to the rats nest。

So we wanted to put one cable down the middle of the corridor。

 and then every time you want to put a PC， you just run up and tap into it。

And we didn't want the network to go down while you were tapping into it because we wanted 24 by7 access to the network。

 so there had to be a way to tap into the network without bringing it down。

So that led to a device we found in the cable TV industry， it was called a geald tap。

 and it was basically a vampire tap you'd drill a little hole in the outer。Casing of the coax。

 and then you would screw in this tap that would puncture the insulation and go right to the copper and tap in。

 and you notice in that operation you're not breaking the copper。

So the network continues sending you tap in and you're now part of the network so that came from the cable industry it did Oh so a guy named David Ladell who had done cable TV installations when he was in grad school in Toledo。

Suggeted that we used the jaral tap since it was already being made in volume and worked just fine as far as he was concerned。

And it allowed us to solve the rats nestest， what we perceived to be an important problem。

 the ratsn problem。The Alova network ran in the kilobit per second range like 4800。

I don't remember the numbers， but kilobits per second， Ethernet then started at 2。

94 megabit and in those days， by the way， T1 was 1。544 megabits per second。 so in 1973。

Even it was already twice as fast as T1。Of course， T1s still around。Odly。But then we went from 2。94。

 we briefly went to 20 megabits per second inside of Xerox。

And then when we bumped into deck and Intel for the standardization process in 802， we decided on 10。

 we came down from 20 to 10 so the chips would work。And then we went from 10 and later。

 I helped found a company called Grand Junction Networks that introduced the 100 meg Ethernet。

 and I remember being at my coffee table。In Palo Alto， I think it was。I forget the year， now。

 maybe it was in Woodside。But we were trying to think of how we would make a faster etherm。

And there's some math that shows that as you go faster。

 the efficiency depends on the diameter of the network， and as you go faster and faster。

 the efficiency goes down。The diameter the network in bits。

And we were trying to go up a factor of 10， and then I don't know who it was。One of us observed that。

 wait a minute， we've been assuming that ethernet is a kilometer in diameter。

But we're all going to hubs now so that。We only need 100 meters， not 1000 meters。

 and that was the factor of 10 right there so by changing the collision interval。

You maintain the same efficiencies， theoretical efficiencies by just。

Assuming you're going 100 meters instead of a kilo。

 so that got us to 100 megabits per second and now gigabit。10 gigabit。

 which I guess is the mainstream now， and then 100 gigabit is now from beginning to run 100 gigabits per second。

You can't be a computer scientist and build that kind of digital now。

 you have to actually be a hardware engineer to run it 100。I think at that point。

 you're pretty much a radio person。But then after 100 gigabits comesterabbit。

 so I've already begun giving talks on terab。