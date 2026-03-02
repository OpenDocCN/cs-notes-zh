# 斯坦福大学《并行计算｜Stanford CS149 I Parallel Computing 2023》中英字幕（gpt-4 - P19：Lecture 19 - Accessing Memory + Course Wrap Up.zh_en - GPT中英字幕课程资源 - BV1Y5V5zjEsX

![](img/7d651cf9f64706596146a9b68febffb4_0.png)

Okay， so so here's what I was was thinking about doing today。's the last day of the quarter for us。

 We should make a little bit casual。 There's one piece of content that we haven't gotten to that we do in some previous years。

 And I always think it's kind of interesting for you all to know。

 given that you're always talking about， oh my God， we're out a memory bandwidth。

 I just wanted to talk a little bit about how memory works。 So we'll talk a little bit about that。

 I'll do a really quick wrap up and things like that。 And then。

 and then we'll maybe open it into just a little bit of an AM M A。 We can talk， we can leave early。

 we can talk a little bit about now that you've taken C S 1，49。

 What might be some things that might be useful at Stanford to go do next。 So that's that's the goal。

 Okay， so let's get into accessing memory， which which has actually been a pretty abstract concept so far。

 And of course， given its importance So in your head you're probably thinking about okay。

 there's a processor。😊。

![](img/7d651cf9f64706596146a9b68febffb4_2.png)

And then there's memory， which some of you might be think of as D Ram。

 And I'll explain what that means in a second。 And then to make memory faster。 And by faster， I mean。

 reduce memory access time and increased memory bandwidth。

 we have this cache sitting in a modern computer。 So if you think about this box here as the CPU or the core。

 know， you've got a processor core in there。 Like， you know， for example。

 the Intel chips that you ran on have four cores and myth they had forgetting now what they had on AWs。

 I think we gave you 8 core machines with 16 virtual， two hyperthreads per core。

 And then there's some caches。 And on this diagram， I'm only drawing one of them。

 I'm drawing what's called the last level cache。 So if you have like an L 1， L2 and L3。😊。

Your L 3 is your last level cache。 Or if you just have an L1， Well your L 1 is the last level cache。

 We often like to think about the last level cache， because that's the。

 that's the point in which memory requests that don't hit the cache now have to go out to memory。And。

 and then there's a box on any modern processor that's called the memory controller。

 And the memory controller is responsible for when the the last level cache takes a cache miss。

 the processor has to go get the data from memory。 And the memory controller is responsible for for making that request out to memory and then grabbing the results when they come back and making sure the data gets into the appropriate cache and things like that。

 So that's what we're talking about。 So， so what we're gonna to go is we're going to talk about the implementation of memory now。

😊，As memory as DNA。So if you， if you， you know， got upset about the final and bashed your laptop over your knee and you opened it up and looked inside。

 you would actually see some some D Ram chips in there。 And one way you could think about a single。

 single D Ram chip is as an array， like a big array of， of memory cell。

 So every box on this diagram is you can think about as holding a a bit。😊，And this is a memory cell。

 so we're actually working in the analog world at this point。

 and how do you think a bit is represented by an amount of charge stored in each of these cells？

It's kind of like the inverse of a photo cell in your digital camera。

 right Like you have an array of pixels and light hits the photosensitive material and generates a voltage and you have a capacitor to hold that voltage。

 It says this is how many photons hit the thing。 Here's the opposite。

 We're trying to store information。 So if we want to store a one， we encode that as some voltage。

 and we want to store 0。 We encode it as a different voltage。😊，Okay。

 so you have all of these different bits and they're organized on a D Ram chip， actually。

 in this 2D manner。Now， down here at the bottom of the chip， there's two important， you know。

 structural pieces。 First of all， you have your wires。

 your data pins that actually connect this chip to the rest of the computer。

 So there's 8 data pins here， which means this D Ram chip at any one clock can only send 8 Bs of information。

And there was a one or a0 on each of these wires。H。And in order to access the D Ram chip。

 the DM chip doesn't actually send data from the the DM array onto the wires。

 It actually has a buffer here， which is like a digital buffer that stores the the values。

 the bits in one row。Of the D Ram chip。 So this is called the row buffers。 This stores one row。

 And so when you access data from a D Ram chip， you're actually only accessing data for a byte sized chunk of information stored in this row buffer。

 And I'll tell you， okay， So so let's say that we have we take a cache miss。

 And the cache like the actual load instruction is I need to access the address X at this point where we're talking about like the physical address X in memory。

😊，So the memory controller gets this command or this request from the processor says， hey， give me X。

 And really what that is is give me the cache line that contains X。 So when I say X。

 just think about x being like the start of a cache line。And。

Every byte that the processor might access is gonna be a contiguous part of some row in this D Ram array。

 So let's say we want to access the byte that I'm highlighting here in red。😊，Okay， so。The goal。

to do is we need to read the values out of those memory cells and then communicate those values back to the processor here over these bit liness。

And so there's a number of steps to be able to do this， basically to convert this voltage。

 this charge stored on these capacitors into digital ones and zeros。

So the first step in D terminology is actually called called precharge。

Which is kind of like getting ready to read a particular row。And in other words。

 what you could think about it is is there's these bit lines。

 There's these these wires that go all the way through the chip。

That are supposed to read off the voltage in those cells and communicate that voltage。

All in one from one row into the row buffer。 So if this was software。

 I would say we need to make a copy of the data in one of these rows。

 put it in the row buffer so we can access the row buffer。

 But making that copy is actually communicating electrical voltage down these wires。

 So we have to set these wires to sort of a known amount。😊，And that's like sort of this precharge。

 And that takes some time。 And so on this slide of saying， it takes about 10 nanoseconds。

 So in memory we we we think， usually in terms of nanoseconds， because。

 know we might be at a different clock rate in Dr Ram than the processor。 So if we said clocks。

 it's a little confusing on what what clock we're talking about。 So， you know。

 on the order about 10 nanoseconds， This is like， okay。

 these wires are now kind of normalized to some known voltage。

 And if we drain the capacitor the capacitance of some row onto these wires。

 you knowre their voltage is gonna go up or down。😊。

So then we basically lock into the row that we want。

And we row activate and row activate is basically reading the charge from this row and bringing it down into that row buffer at the bottom of the chip。

😊，So that's the copy of information。And actually， it's interesting since this is analog。

 that copy actually destroys the value in that row。

 So the only place where that row of information sits is actually down here at this point。

So I had 10 nanoseconds to kind of get the communication lines ready and another 10 nanoseds to sort of read off the voltage in that row。

 And now that information is sitting down here in the row buffer。

And then given whatever particular bitete that I want， then I can select that information。

It's called column selection because like the byte that you want is selecting certain columns in that row and transferring that bit。

 those bits onto the memory bus。 And now they're moving back to the memory controller on the chip。

 and the chip is going to put them in the right cache。And so on and so on。 So this process of。

 of reading a by actually is like， get ready， activate the appropriate row。😊。

Then select the right column and then move the contents from those eight columns on to the wires。

Jason B great question。 So what would happen if the next bite that you wanted to read was the next bite over in that row？

the reader。You can't be able to read it from the row。 And， and not only you can't。

 you don't really want to because you have the whole row sitting right down there in the row buffer。

 And so you just move over。 So if your first access was like needed a column access。

 a row activation， and then a column selection， your second access is actually faster because all you need to do is read off more。

😊，Read off the next byte in the row。 The data that's already in the row buffer。Okay。

 so this is kind of interesting， right， like DRA， so we've talked about accessing memory has variable access times。

 depending on whether or not you hit the cache。😊，If you miss the cache。

 DRAM has variable access times depending on the access pattern that you actually choose。

DRA may not be prepared or ready to deal with your request。

 It might need 20 extra nanoseconds to sort of get prepared。

 and that can be a big deal there a few questions Yeah you could almost think about this as like we're basically digital at this point。

And， and we're just sending those information that out。 And what has to happen is periodic。 like。

 like， if before we read the next row， let's say another。

 let's say we want to read like this bite here。The first thing the DM has to do is actually write this data back to that role。

So we don't lose that information。So if we switch to a different row， there's actually an extra step。

 It's right back。 then you know， like ready the data pins， then activate the new row。

So it can actually be quite slow if you're moving around memory。Is there any reason why？

The number of data。ずし。S。Well， yes。 and， and that's because you would love to have more pens。

 but this is expensive。That that' would be like saying like， you know。

 why doesn't Highway1 have 1000 lanes because we would benefit from 1000 lanes at rush hour So we'll get back to that comment though in a second And and the other thing that you're saying well why not more pins or something like that。

 You know，s this is actually the basic unit of D Ram。 And so if you want a wider memory bus。

 you will use more of these。 So Dras got to be cheap because it's kind of a commodity。

 And so the industry is standard on a basic Dra chip with like pin with8。

 And so if you want more of these， we're gonna start stacking them。

 And we'll get to that in a second。 So okay， so you know if everything。

 know if you take away anything from that sequence， it's like Drra latency is not fixed。

 know all all addresses are not the same。 It depends on your access pattern。

 how much you might get out of that。 And that's a pretty big difference， Like just think about it。

 I can either grab a bite every cycle or I might have and it takes about 10 nanoseconds。😊。

to push that over the bus or I could have like a whole 40 nanocond。

 30 nanosecond process to get the next bite and all of a sudden I've just cut my DRA bandwidth by a factor of three or four。

はず。What extent can we control other please to operate existing significantly？So。

 so what I'm talking about here is I saying when I when the computer。The processor requests address。

 data and address X。It is the memory controller's implementation。

 It's that responsibility to map that to a place in that 2D array。You and software。

I have very few mechanisms to address that。And there's some reasons why。

 which might be more apparent later。 So the thing that you're noticing is that let's say I have to make four memory access these to these locations that I've。

 I've highlighted in in。In different colors， like， let's say you're like walking through a linked list or something like that。

 Or you don't know where that data is going be at。 where Malick put the data in the address space。

 You know， some of these。 So I have just my， my operations are precharged， ready the bit lines。

Row access Stro。 So RA S is select your row。And the column access。

 select your row and bring the data to the row buffer and the column access sbe。

 the cas is the read the appropriate columns out of the row buffer。

 Okay and and so I'm highlighting the ca in red， because that's when the data moves over the memory bus。

 the memory pins。 And if the memory pins are like like the most precious resource in the system。

 Your goal should be to make everything， you know， you want to be able to use those pins at all times。

😊，If you're not making 100% utilization of them， you are wasting your scarcet resource in the system。

So what are some things that we could do， given that this particular， you know。

 what's the utilization of the memory bus in this example， You know， there's 1，2，3，4，5，6，7，8，9，10。

 you know， about 41s。Only four out of those10 boxes are。

So what are some standard tricks from this class in making better use at of something。

So we could pipeline it。 Now， how do we do that。Okay。You're on the right track。

 there's a couple of different things you could say。We increase bump sites。

And what do you mean by you actually mean increase the minimum request size？Or something来。

Two row buffers。 Okay， so so basically you're kind of saying I want some multi threadreading kind of ideas。

 Yeah， yeah， and you were kind of getting closer Yeah， it's totally on the right。 First of all。

 I want to just go the easiest one first is you allow the， the the chip to support bulk transfers。😊。

Like， you have actually like ability of like the command of the chip is not give me a by。

 but the command of the chip is give me like 64 contiguous bys。

 So the first thing in any computer system is you do bulk stuff。 If you want to amortize overhead。

 right， So that's， that's one way to do it。 And that's one way to do it。

 If your access pattern affords big contiguous data。 By the way。

 there's a reason why if you run right through your memory system， you get the best performance。

 And it's not just you're using the whole cache line。😊。

It's actually that the memory controller can communicate with the DM system in the most efficient way possible if it knows the access pattern is。

 is all contiguous。 That's also the reason why there are cache lines。 You know， Ca lines are 64 B。

Which helps suggest， you know， like big bulk contiguous granularity transfers are more efficient。

Right， like a memory bus is 64 B on modern Intel stuff。 A modern cache line is 64 B，8 times larger。

 which means there's a lot of bulk bulk transfer there。Now。

 what you all are hitting at are really good ideas。 And that's exactly what's going to happen。

 So basically， what's going on here is this is your classic problem of I have an operation with some latency。

😊，I need to hide that latency。And in this class， if you， you want kind of arbitrary latency hiding。

 you multi threadread。 And if you want kind of more structured latency hiding， you pipeline。

Right you put more operations in flight。 and we're definitely going to pipeline this thing。

 So here's what we're gonna do is every D Ram chip has like one of these rays and it has a row buffer。

😊，And the way they do their pipeline is they're going to take all of this。

 and they're going to replicate it。So here's what's going to happen is we're going to share the data pins。

Remember， like multi threading was like sharing the processor and having different outstanding requests Here。

 the outstanding requests are into the array。 We're gonna share the data pens。

 but we're gonna build build more row buffers and more。Sorry， sorry。

 we're going to share the row buffer and the data pins， and we're going to build more Dize。Okay。

 so we're gonna have what in DM terminology are different banks。

So what's going on here is while we are waiting for data pin sorry。

 for a rows to activate on one bank， we're gonna make a request and start reading the data from other banks and sending data over the bus from other banks。

 So notice here that if your addresses are interleaved over the banks。

 I can start the the processing for bank 0。Or removing the data for bank 0 when I'm initiating the。

 the row access on bank 1。 This is your classic。A pipelining example， like you said。

So every D Ram chip， if you like， go buy a D Ram chip， it's gonna have some number of data pins。

 which is basically gonna be 8。 It's gonna have a row buffer to store a row from any of these D Ram arrays。

 And therell be multiple D Ram arrays， which are called banks。That's packaged up。

And then if you want a 64 B bus， this is an 8 bit bus。Then you start stacking them wide。 So this is。

 you know， like when you go to or you go on Amazon or new egg， you buy yourself a D Ram dim。

So the dim is in IMM is the inline memory module。 There' is just8 of these D Ram chips。S林 there。

So this is now a 64 bit memory bus， 1，2，3，4，5，6，7，8。So your Intel processor。

 your standard processor connected to a 64 B memory bus。 The memory controller is sending a command。

And that command is not， I want address X， but that command is I want the the byte at Bank B， row R。

 column， whatever。And all 8 D Ram chips get that same command。 They all return their data in Bank B。

 row R， column 0。 And that all together is 8 B of data。

So it's the memory controller's responsibility to say， oh， if I'm supposed to get a 64 by cash line。

At this address， where in this 3D address space of bank rows and columns is that data。

And you issue the request。People looking confused， yeah。

We're not replicating there's no data replicated， there's just simply in this case， three banks。😊。

Here's the pre。So if I'm accessing Bank0， here's the pre on zero。

 here's the grabing the row into the row buffer。And then there's the read the data out of the row bufferer for an access to bank 0。

 While we are reading the data out of the row buffer on Bank 0， we're precharging Bank 1。Yeah。

So the vertical data lines are replicated， the replicated lines， there are n different DRAM arrays。

And they all hold different data。有。How smart is it？

To like like if we go a contiguous rain we to try to scatter these across。

Well let's let's think about it a little bit。 So let's think about reading one cash line。

From this thing。Right so one cache line is 64 bys or 512 bits。Okay， so imagine that I do the。

 the most simple thing。Which is I put because like the width of these D arrays is like 2000 bytes。

So maybe I put the whole cache line in contiguous。A contiguous row of1 D Ram chip。

How long does it take me to read an entire cache line， So my first8。

 my first bite comes from this D Ram chip。My second bite comes from that Der Ram chip。

 My third bite comes from that Der Ram chip and so on and so on。

 So even though I had a 64 B memory bus， I'm only using 8 B。😊。

So what does it suggest the answer needs to be？I have to， yeah， I mean。

 like like one thing is I should interleave the address space over my D Ram chips so that notice now when I say read Bank B row R column 0。

 the same address or not the same address， the same like location and all of the chips。

 I get what happens to be 8 consecutive bytes in the physical address space。Now， of course。

 if I wanted 64 by for the cache line， I would need to do this eight times in time。Yeah。

Ts ago when you have the way。Is that you have multiple banks， but then it's one grown。

 one set of data planss。Yeah， when you go one slide forward。

 like it looks here like when you do each of these little modules。

 that it's in on one back and like each of those。Oh， what I want you to think of， sorry， yeah。

 this diagram here， every one of these boxes is a DRAM chip。

And every DM chip inside of it has multiple banks， which I did not illustrate here on the slide anymore。

 Sorry about that。 Yeah， I probably should have done that。

 But you could just think about it A D RamM chip as a module which accept as input。

 a request which says， give me the byte at the inbank B row R starting at columns column 0。Right。

And so now， now keep in mind that if I do this， let's， let's do this。 let's go here。 Okay。

 so let's say I stride my bys across the D Ram chips。

 Does it make sense that we're gonna get 8 consecutive bys here。Right， okay， so。

 but we have a whole cache line， right， We need the next 8 B。

 So I would probably put the next by inter leave it amongst the D Ram chips。

 but put it in a different bank on those D Ram chips because I w to initiate that row access to the next bite immediately in the next cycle。

 So Yeah， I should change that diagram to show that there's a couple of of banks under each of these。

 Yeah， does the memory。😊，When I makes some questions just let the hear our module know to start reing the next bank。

No， it'll look like thisll。There will be a come。 Well， the， the D array。 Okay， so the， in every。

 think about it this way， in every clock。The memory controller is sending。This command。

So let's say it starts getting started in that command immediately， just for simplicity。

 And the next clock， it'll start precharging bank， B plus1。Or something like that。

 right Because the N command will say， I want the data at Bank B plus1， right。

 So the memory controller is gonna give the memory system requests in a manner that。

 based on its knowledge of how memory works， it can satisfy those requests as quickly。Yeah， yeah。

 yeah。 It's pipe in the request straight in。 And， and if it's a whole cache line。

 let's say it's 64 B。 that request actually could be burst mode transfer。 I want 8 B。Located。

 starting at B， R and column 0， right， because what I would probably do is I'd put the next bank。

 if those are the bys I'm reading there。 Well， the next by I read from every D Ram chip will actually be in the same。

 Oh， sorry， I'm in the wrong place in in the same row。 So in this case。

 I would not start a new bank transfer。 I would just say， look。

 I I need 8 consecutive bys from the same row of all D Ram chips times to 8 D Ram chips。

 That's gonna get me to my 64。Exactly。Do the requests from the。also go across the Sun。know。

 there's usually like a command bus。 Also， yeah， yeah，'re usually a 64 bit data bus。

 And then there's a command bus。 I haven't ever implemented one of these myself。

 I'm not sure if there's any clever temporal multiplexing of the pins。

 but I'm pretty sure that there would not be because in modern DDR。

 you're you're actually doing transfers twice on the rising edge and in the closing edge of the clock。

 So unless you're really creative， I don't see how you could squeeze any more information down。

But yeah， okay， so this is like your basic memory unit。

And then sometimes you'll hear things like dual channel memory system or something like that。

 And so like you could think about this as one channel between the memory controller and a。

 and a memory module， again。😊，And notice that one channel has one command per clock or something like that。

 And the same command is given to everybody。A dual channel memory system is just to take this。

And make another one。Right， so here's an example of， of oh， sorry。 No， I got ahead myself。

 So one more thing before we talk about dual channel is， remember， we have the processor down here。😊。

And the processor is just generating cash misses and cash misses turn into， I need this cache line。

 And those are requests for the memory controller。 And the memory controller takes all these requests for cash lines and translates those into memory channel request。

 which is like， I need this bank， this byte， this row。Right。

So the memory controller is mapping physical， Line addresses to spots in a D array。Now。

 the memory controller is getting just kind of random cache misses。 You know， what it， you know。

 whatever the algorithm does and what any modern memory controller does。😊。

I it just starts and queuing those and buffers them up and then reorders all of those cash misses such that if it can find。

 you know， like like request that it needs to make to the same bank or sorry to the same row。

 it will reorder the requests in order to maximize this sort of hit rate。

 So it's gonna basically reorder all the processors memory requests in order to try and and get the highest bank pipelining and the highest row buffer locality。

 because remember， the processor's memory request might be coming from all the different applications on the system。

 So you might have an application that's reading linear through memory。😊。

There could be another application that's linearly reading through memory running on a different core。

 and think about how those two memory request streams are going to interact。All of a sudden。

 you thought you laid out your data perfectly， but now it's like core zeros over here。

 core ones over here。 now you're going thrash that memory D Ram chip。😊。

So how many requests are we going to wait for？This is an implementation detail right。

 so you have on one hand。Buffering will increase latency。On the other hand。

 buffering and reordering could increase bandwidth。So if your're bandwidth bound。

 you want to buffer aggressively and maximize bandwidth。If your application is latency sensitive。

 like some real time thing。You might not be so happy with a heavily buffering memory controller。

 And Nvidia memory controller is probably the most complicated part of the chip and could be buffering tens of thousands of memory requests。

 actually。Because everything is bandwidth bound on the GPU。 So it's just like。

 I'm gonna wait and see if there's any more request for this open row for the next like 10 nanoconds。

 And if anything else comes in， I'm gonna let them go to the front of the queue because they're gonna be really cheap。

the latency versus bandwidth bond。Does the memory controller dynamically determine that or if you build one memory controller。

 it will begin kind that is your discretion as the implementer of the memory control this thing so what's happened is that all the sophistication of an out of order。

 complex superscalealar processor？We kind of stopped getting more sophisticated there。

 We even went built cheaper or simpler processors for a while there。 Like， you know。

 a modern GPU probably doesn't do nearly as much smart stuff in the in the core than even still a modern CPUU does。

What's happened And so we start building all of these cores？

With all of this core share memory system。 And so all of that scheduling logic that we used to have to schedule instructions has turned into papers and algorithms and other stuff to figure out how do I take a look at my cash miststream as it's coming in and guess whether this is latency bound or not latency bound and how do I come up the good scheduling policy。

 So in the late， you know， like in the in the from like 2012 to 2000 and like 15 or 16。

 computer architecture was all over this。😊，Right，Or like in the 90s or early 2000s。

 they were all over how to build a branch predictor for an instruction stream。

 So they took the complexity out of the processor and basically shoved it in the memory controller。

 which is getting requests from like 16 cores or like like like 32 hyperths and is trying to figure out how to reorder all of these requests from different processes to maximize pen utilization of the DM bus。

 or energy。 The other thing is like you're actually trying to maximize energy too。

 So or minimize energy。 Okay， so the last piece of this is take what we just did And if we want more bandwidth。

 we're gonna start replicating。 So if you hear dual channel DDR 4 memory system。

 That's just that 60 that 64 bit bus connected to a dim。😊。

There's just two of those connected to two dims。 And now when you have two channels。

 you could actually say， you know， maybe this channel is actually sending different commands to this dim than that other。

 other dim。 But everything connected in a channel is， is， is the same command。

 So here's an example of something， you know， like something you might see on， on。

 on a website like DDR。 So DDR 4， that's a memory technology。

 The number after it's actually just the clock rate of the memory bus。😊。

And so all of these things are 64 bit memory buses these days。And the 2400 is a kind of know。

 bigger number sound better in computing。 It's really a 1。2 GHz memory bus。

 So it's sending data or like the cycle is， is 1。2 gigHz。 And it turns out that the。

 the first D is the DDR is actually is double data rate of memory technology。

 and actually sends two transactions per clock on the rising edge and and the following edge of the clock。

 So if you multiply 1。2 by 2， you get 2400 memory transactions per second over a 64 B bus。

 So if you say 64 B times 2 times 1。2， you actually get 19。2 GB per second。😊，Right。

 and if it's dual channel， you just multiply everything by two and you go look up at the。

 the specs of the memory system。 It'll say something like， oh。

 the memory system can do 38 GB per second of bandwidth。 And that's where that number comes from。😊。

So this is like a very standard thing in like a， you know， modest PC or something like that。

And then it says like， you know， like at the time， when I looked this up。

 it was about a 13 nanoseconds cast。So。That's how long it takes to get data in that's already in the row buffer or out of the DM chips over the outlet of the bus。

Yeah。それに。Chrisine that the only is like covered the caps overly dear。that just because。いぱま。Yeah。

 you kind of think about that because if you've got a nice friendly memory access pattern。

 it's how quickly can you get that data out？Y。嗯。Okay。And that that's not trivial， right。

 becauseuse if you think about a modern processor running at 3 GHz。At one gigahertz， that's what。

 that's a nanosecond， right？I do that right。And then so if you're running at 3 gigHz。

 it's 0 you know，0。3 nanoseconds。 And so you're taking。30 x that just to get the column out of the。

 the road。 it's on trivialvi。 Now， of course， you should also。

 your memory access time is gonna be all the cycles needed to get from the processor to miss miss a couple of caches。

And get off chips。 So there's a lot more latency in there than just accessing the DM itself。

 But that's just how it adds up。对啊我就唱好的。好认。Oh， so one thing I did not talk about here is any kind of fault tolerance me like if a bit flips or something like that。

 typicallyy what happens is you have these air correcting codes。

 And so if you buy slightly more expensive memory or server memory， largely。

 instead of a dim with eight。Chip center， therell be a9 chip。And the9 chip is， is the redundancy。

So basically， you can check to see if。If， if you have， depending on how many extra how you do things。

 like， you can actually check to see if you at least detect if there's an error。

So you just actually burn a little bit more capacity for。呃，否认。Okay， so， you know。

 I think the takeaway would be。 that's a little bit on how DM works。

 And the big conclusion is there's a significant amount of complexity in the memory controller scheduler。

😊，To take requests from the processor and reorder them such that those requests hit the D Ram in a very。

 very friendly order。 You can think about it like， you know， you did like with your flash attention。

 right， Like， you're reordering the computation。 So it hits the cache。

This is about reordering the cash misses。 so they hit the D Ram in a nice way。 And obviously。

 this is being done by hardware and not by the programmer。Okay， that's the all I want to say on that。

 just kind of kind of cool。 And just so you， if you ever get asked in an interview。huh。

How would you schedule a DRA request stream？It's pretty cool right。😊，Now， the problem， of course。

 is that we are bandwidth bound all the time。And so one way to， you know。

 like so you can think about it is like Dr Ram sits over here。You know， on the board。

 and then there's those pins and those pins go over the entire board to the processor over here。Now。

 the problem is like the only reason why we have eight pins is that those are really expensive。

To your， to your question earlier。 So there's a lot of interest in bringing that processor a lot closer to the memory so that the distance information travels is less。

 which makes it economical to build a lot more pens。😊。

And the number one way you're seeing this like two day in high performance things is via these a combination of chip stackacking and colocating the memory on the same die Silicon die as the processor。

 So here's a diagram of kind of how like if you went and got like a server class GPU today。

 that you might hear about this HM high bandwidth memory or HBC， hybrid memory cube。 I think HM。

 I think is basically won the won the competition。 So you get a lot of HM these days。

 So here's how it works。 Here's my GPU or CPUU over here。😊，And typically。

 that GP or CPU is plugged into。A board， you know， a motherboard。 And， and then there are traces。

 you know， almost copper traces over that motherboard to a D Ram chip that I plug into the motherboard。

These days， if you want this high bandwidth memory， this is your CPU or GPU。

And it's right on a silicon chip。It's on a silicon chip and on that same silicon chip。

Is a memory module right into it。So now the connections between these two are actually wires on a piece of silicon。

 They're not board traces。And then the DM chip is actually stacked。😊，Which means that these。

 these D Ram chips are on top of each other physically。So， and the， the key technology was this。

 this thing called the T S V through Sil via。 So you can think about the wires that used to be like 8 wires at the edge of the chip。

Are now wires that leave the chip throughout the DM array。

 So you kind of get area amount of space and not one edge of the chip amount of space。

 So you can run a lot more wires right off the bottom of the chip。

 like from everywhere in that array。And those wires have to run through the D Ram chips below it。

So there's these vertical wires that then go right on the， you know。

 right into a piece of silicon right over to the GPS P。 So if you bought one of these things。

 this is all in the same package。What I mean by that is like it'll look like one chip。

So that's allowed people to put a lot more wires out of the memory system to the CPU。

 And I'm talking about not 64 bits anymore， but 1000024 bits。And so if you go buy a modern Intel。

 high end， like supercomp Intel thing or an AM D or Nvidia GPU， This is now the chip。 This is the。

 you know， the processor。 This is what's called the silicon interposer。

 which is a piece of silicon and that processors on the silicon。

 And then there's 4 different stacked D Rams next to it， all of which are 1024 B into the chips。

 This is a 4000 B memory bus。😊，This is， this is fast。 You know。

 this is now delivering 720 GB per second。Of bandwidth end of the chip。

 And that was back in 2016 now or significantly higher。 I think we're closer to like 2 TBabys。Right。

 but this is a fixed amount of memory。 So this is 16 GB of memory only back in 2016。

 Now now we're higher。 And if you want large amounts of memory。

 then you have a traditional memory bus that goes out to DDR 5 or DDR 4。

 And you might have hundreds of gig or  TBab of that。 So this is a form of D Ram。

 That is not the cache。😊，There might be like an 80 MB L 3 cache here。 If you miss the 80 MBte L 3。

 you have access to， in this case，16 gig of about a terab per second of stack D Ram。

 And if you don't fit in the stack D Ram， then you got to put your data out in conventional memory。

 And now you're back to 300 to 400 MB per second or gig per second。😊。

So the memory hierarchies are getting really， really deep。

 and flash attention thing you guys implemented was initially designed to fit the intermediate matrix matrix。

😊，In the 16 gigaby of HBM。Instead of going out to DM on these chips。Yeah。

 it's lower also it's also higher bandwidth lower ratess now in a GPU。

 we don't care as much about that latency because we can hide it with multith。Or pipe planning。

But yes， lower latency， higher bandwidth， lower energy。Okay， so， you know， like， I， I， I， if you。

 you know， last day of class， if you walk away with anything， it's really that in a lot of times。

 parallel parallelization is pretty easy。It's really trying to figure out how to get data to your dam。

 dam processors。 That's hard。 It's scheduling。 that's hard。

And so you've been doing it yourself in this class， you know， flash attention。

 your coupa programming assignment was very much about locality。

 And then the hardware folks are designing better memory systems for you。

And the general design principles are like， look， either data needs to be located next to the processor。

 or the processor has to be but closer to the data。

 And one thing that we haven't talked about very much in this class is if you're bandwidth bound。

 it almost always pays off to data compress。Cause if you're bandwidth bound。

 your CPU is idle or your GPU is idle。 So actually have' it burned more instructions to move less data。

So like GPUs， for example， for texture data and other stuff， actually， when you take a cache miss。

 it compresses the data before putting it out in memory。 So it actually moves less data。

 And then when you want the data back， it actually moves the compressed data onto the chip and then decompresses it into the full cache line。

 It's a very common thing to do in graphics。😊，All right。

 so that was a little bit on memory these days。Anybody worked on any of this stuff actually。

 like an NV internship or Apple internship or anything like that？No。It's Apple， if I couldn't say so。

Okay， I think we're basically done。 We're basically done。 So let me let me。

 let me wrap up some some technical stuff here is a few takeaways for the foreseeable future。 I mean。

 if you look at Apple Sil these days or what's in your iPhone or Android phone。

 It is a heterogeneous multi core processor with multiple CPU cores， multiple GP cores， neural core。

 core specific for processing the data in your sleep schedule and stuff like that。

 the only way things are gonna get more efficient going forward until there is some massive breakthrough in technology。

 know on the level of like being more optical or being more quantum or something like that。

 But for the foreseeable future， it's gonna be through。😊。

It's already happened through parallelization。 It's gonna be through specialization of certain sorts。

And so there's huge interest in making these specialized processors easier to program。嗯。

The other thing that I， I really hope people walk away from here is most software。

Is shockingly inefficient compared to what modern computers can actually do。Like。

 we saw in assignment 1 that a well written C program is 40 times slower on our laptops than extremely well written。

Program that uses the vector units and uses the Sdi and specialized processing is another 10 to 100 x on that。

 So just when you're， when you're working in， in labs and doing future work， If someone says， okay。

 we're about to scale up to a big cluster。😊，Sometimes that's the right idea because it can be hard to optimize your program。

 But sometimes it's like， gosh， we could either work really hard to scale up to a big cluster or wait overnight or something like that。

 Or we can put a little bit of effort in and run 1 thousand times faster。

 Sometimes that can be absolutely gamechan for， for folks。

 or it might allow something that you nobody thought was possible on mobile to become possible in mobile。

The fun thing about this class， at least， is that almost all computing applications these days。😊。

Are actually the types of applications that fit into the mold of what we talk about in this class。

 You we don't have to go to big scale scientific computing to be applicable。

 You take an interview at Apple to work on mobile team right now。

 efficient software and power efficiency is what they care about。 You know， you go to Waymo。

 That's what they're gonna care about。 And so there's just a lot of places that that one could go from this class even more so with all these large AI based language models that are extremely efficiency bound right now。

😊，We've talked about a few themes， like we've talked about。You know， identifying perism。

 which I say often is kind of the easiest thing for everybody to do。

 which much harder is scheduling that parallelism once you know the dependencies。

And we've talked about that in the small and the large。

 and then we've also talked a lot about how to make our lives easier by relying on higher level abstractions。

 which in future courses， if you're programming in Tensorflow or pytorch or programming in SQL or something like that。

 you can think about oh my gosh， like think about all the parallelzization and efficiency that's going on under the hood that you don't have to think about because someone's put in place a useful abstraction。

嗯。And we've talked a little bit about how hardware works so that at the very least。

 if somebody comes up to you and says this computations taking three hours and you can kind of call a little bullshit on them。

 you're like， you know， if I think about it， this thing should only take 5 seconds。

 You must be doing something really， really wrong without your scheduling it。

 You'd be surprised how much that that happens。Okay， let's see。 So it's just some practical things。

 Next steps。 we do teach other courses。 So Konley has his hardware programming class next quarter。

 I believe So if you're interested in using spatial。 And I think they teach in spatial。

 if I remember correctly。 that could be interesting。 there's as some of you know， there's 229 s。

 the new course that's simultaneous with this one which maybe we should think about putting those on different quarters in the future because it feels like you should take 149。

 and then you'll get a ton out of 229 but there's that's a great course。

 I've been tracking that new course。 that's really cool in the sprint， you know。

 I teach graphics next quarter。 So if you're interested in graphics by all means join us。

 But if you're not interested in graphics， I teach this hybrid graphics basically if you take 1。

49 and you take vision and graphics。 and you put them together。

348 k in the spring is that it's a small course， we typically keep it around 30 people。 we read。😊。

Papers on how to build systems， systems like video processing at Google or haide or these days like how to serve chat。

 you know， how to serve chat GT in the data center or something like that。 So we read like very。

 very recent papers that we discuss them。 And then it's a projectbased course。

 So the idea is how to think about building these， these visual computing systems where the goal is to produce or understand pixels。

嗯。Yeah， I mean and then of course there's like a lot of the standard fare， like EE280s。

 a great course if you want to get into more hardware operating systems here， I mean。

 there's so many courses in the department that start touching on parallelism in different ways。Okay。

 so， so then there's， then there's the idea， of research， right， And， you know， after taking 1。

49 with the assignments that we give you， which are not the， the easiest。

Like many of you through this course have really built up some some real started to build up some real programming chops like you know you know the fundamentals。

 And so you now kind of stand if you're interested。

 maybe kind fitting in a little bit in one of the research labs in a systems group。

 like King I or any of the other systems faculty。 And I do encourage people to think about that。

 not because I'm really advocating for research。 So there's folks that work with us all the time。

' like I do not want to be an academic or a researcher。

 but they want to treat an independent study just like a class。

 they'll take three units or four units and their role is to jump in on an existing research project and often perform more of a software engineering or support role saying hey。

 we were thinking about paralyzing this。 but like we don't have anybody to do it。

 Would you want to like see if you can make this 100 times faster。

 And if so we can put you on a paper and you can be part of writing a paper or something like that。

 I think one of the coolest things about being at Stanford is。😊，Like compared to other places。

 like you can probably take a pretty good parallel programming class at many universities across the world。

 you know， it really is the peer group at Stanford that's so interesting。

 right like working with your partner or working with other people in the class or the CAs。

 that's what's really interesting around here。 And so if you can believe that your master's students or undergrads that you're working with now。

 you're like， wow， suppose are really cool folks are like working with them。 You know。

 our PhD students are not too shabby either。😊，And so， you know， like。

 it can really open your mind up Im like， loa， that person's only2，3 years older than me。

 And they are awesome。 Maybe I should be， you know， like， I can get to that level， too。 So， you know。

 it can be kind of fun if you， if you find the right fit。😊。

So let me just tell you about one project in my lab just to be more concrete about things。So as。

 as many of you have probably experienced， you know。

 I I people are very interested in training AI agents。

 whether they are robotics or just software agents these days to do things in the real world。

 And I come from， you know， I'm interested in graphics。 And so for me， I'm like， oh。

 you guys are doing all this stuff in these simulators。😊，Well， there's not。

 what is a game engine as a simulator？And so a lot of this work。 here's some example， know。

 you might have heard of like the open AI dota playing bots along you know， kind of old news now。

 Here's another example where like there was this two on2 game of hide and seek where two of the agents had to hide and the other two agents had to to find them。

 there's a lot of stuff and robotics and stuff。 Well the problem is that in general。

 people were basically taking unity are unreal。And running a simulation in them。 And if you。

 if you don't know anything about this modern AI stuff， it's that， well。

There's kinda two things you can do is you can have an LLM tell you what to do， which sometimes。

 sometimes works。 And then the other thing that sometimes works is you could just have large amounts of trial and error。

You know， robot try and do this task。 oops， you fell in your face。 You know， like， okay。

 take that as an error and make a small correction and try again。

 And because of all this trial and error， people are using pretty massive resources to。

 to learn these skills。😊，Like clusters of GPUs， billions of time stepss of trial。

 And it was like computing all these， these time steps in like these 3D environments was taking all this time。

 And as a result， they were， they were just loading up on big clusters。

And so one of my students kind of saw all this and said。Well， the。

 the reason why they're doing that is they're running like。

10000 copies of unity all on a different server， playing the same game。 you know。

 like one server per And he's like， or you like run like 30 copies of unity on the same box。

 And that's like， you know， they start thrashing and and like。

 this is a bad way to do this If your goal is to like play out 10000 games。 So。

 so you started going like， okay， what if we just design like a mini game engine from scratch。

 And the goal of the game engine was not to render pictures for， for humans。

 What was to carry out 10000 independent copies of a game。😊。

But do so kind of in a lock step so we can get all the good coherence and all the good properties of perism。

So， you know， here's an example of a game that was created in his system。

 So you can just kind of see some of the requirements。 This is that hide and seek thing。

 We should have cut there's two teams。 like there's these two guys， I think or。

 I think there's these two guys and those two guys you see them。

 they've learned to like win the game by like pulling' like's like a small child like pull something in front of your face。

 And technically， by the rules of the game， they can't be seen And so they win So I'll play that again so they have to learn how to like hide other people like like in this case。

 like they have to learn to go see someone else。 I think that's what the guy walk into the right is But some interesting things happen。

 some originally done by open AI and we just replicated it。😊。

So there's a lot of pretty gnarly computations， like you've got to do physics。

Sim the physical world by the rules of this game or even just to give people a sense of the environment。

 you actually have to do a bunch of ray tracing。Becauseuse you have to say， who can see who。

And then there are just rules like gameplay logic。 Like when I get close to this block and like press the button。

 it should attach to me because I picked it up or something like that。 So there's arbitrary logic。

 So you want to be able to write your game logic like， okay， like like here's an event handler。

 here's some basic script to say， when I'm close to this thing And I pick it up。 know。

''s who owns it property turns into me and stuff like that。

 So you write your game in your normal way。 But we have ways of basically like。

 think about like ISPC in a find it or co find across everything。

 And we actually run the simulation like this。😊，So you don't think parallel， but we parallelze it。

And now we line up tens of thousands of games at once。

 And just by this kind of basic CS S 149 kind of thinking， we can go quite fast。

So this is on the order of speedups over off the shelf。

 open source things on the order of two to three orders of magnitude。

 So stuff that used to take like 64 GPU clusters for a week can now be done in a single GPU in an hour or two or someone training this overcooked AI thing which is a common reinforcement thing used to be about four hours for a training run turned into three seconds because like these are pretty simple game。

 So that's like an example and it's pretty easy on a project like this to be like， oh yeah。

 we'd love to have someone add a feature to the game engine and so we had an undergraduate who a good undergraduate has taken 348 class like a freshman or something like that。

 he's the one that actually just built a brand new rendering system that amortizes over 10000 different scenes and builds the rendering system。

 So now we can render these thing。 So if we don't render pixels。

 we can run this thing at like 2 million frames per second。 But now we're。😊。

Actually rendering pixels in case you wanted to train an agent that actually took images to actions。

 I can do that on 200000 frames per second。 So for small images and stuff like that。

 So that's a pretty big difference。 You know，200000 frames per second。 Okay。

 let's drop it to 100000 because you got to run like a deep network or something too。

 So about half and half simulation。 So it's like 100000 frames per second。 in 10 seconds。

 you have a million examples of experience。😊，Right， like so you're into a billion example， know。

 you're getting close to a billion examples in a weekend。 So maybe that'll allow some stuff。 So。

 so there's， you know， ways to like， okay， like， it'd be really great to be able to write the scripts and python and have the python compiled to coa PT T X stuff。

 So that you can write your scripts in Python instead of couta right now。

 There's a whole bunch of like little projects that would be extremely technical that people could help out with。

 Like so that's an example of the project where if folks are really good implementers。

 It's really easy to get you involved。 Other projects are are harder to get involved。😊，You know。

 we have one master students that took 149 last year。

 and he just wanted to start implementing Minecraft in this thing。

 So he's implementing his own Mincraft that runs at like 600000。So。

 so the hypothesis here is just like， you know， like now that you are kind of midway or three quarters of the way through Stanford career。

 it's probably a good time to start thinking about what the heck you actually want to do when you get out of here。

😊，And and this is the point at which， you know， sometimes like starting to do some of your own projects or some less directed stuff can be a heck of a lot more useful to you if you're disappointed about it。

 then just taking the next course and figuring out what know some professor comes up with like five assignments。

 You're like， okay， I don't want to think about what to do。 I'm just gonna do what they're told。

 So so that's that's just something I like to tell people roughly around this time in their careers。

 like what's the conventional path at Stanford， and wants to be honest。

 it's a conventional path at like every other top university。

 which is you guys all got really good Ap scores， if I took more A classes and other people。

 and there's this notion that like if you get A's in a whole bunch of Cs classes。

 you're sort of doing a good job like so you get that 40 G。 you can go the job there。

 you can hang out and attend some free food， some people give you some callbacks。

 and you're gonna get a good job。 You're definitely get that first round interview。

 You're gonna get a good job。😊，You know， wherever the good jobs are these days。 I don't。

 I don't know where the， the hot place is these days。 But， you know， like it used to be like。

 if you could get your Facebook or meta or at the time Facebook， if you get your Facebook。

 Google and like Dbox offers in your senior year， play them against each other。 and then you're not。

😊，Just go there for two years or something like that。 Nowadays， I actually。

 I'm not sure if it's so obvious where the， the so called default odd job offer is coming from。

 And I'm actually curious。😊，Is there like a singular set of like three or four companies that everybody's trying to pursue。

 I don't get the sense that that's true anymore， actually， yeah。Very。Yeah。

 I don't think it works anymore， actually， yeah， but it used to be that case。But， you know。

 the thing that does work a lot better。 and and I'm using my name on this slide。

 I'm not saying come work with me or anything like that。 But like， you know。

 every year there'ss a few folks that come up and say， hey， you know， this course I took with you。

 whether it be one of these things， was pretty cool。 iss there anything else I can do？😊，Right，And。

 and sometimes I say， hey， like， yeah， I remember like your assignment 3。

 like you did to like every extra credit in the book。 Like， yeah， sure。

 like you seem like you know what you're doing。 And， and then I'm like， oh， well。

 we definitely are looking for someone to like hack some hardcore coa code right now or。

 or be able to like implement a new application and benchmark the hell out of it because we want to compare that benchmark to something that we're doing in the lab。

 That's like basically how people start to get involved。

 Like you just kind of are useful in some way and。😊，Sometimes not all the time。

 I would say about 50% of the time。 maybe， maybe 30% of the time。

 It really is the right student to get involved with my PhD students。

 and they basically just start acting like a PhD student for independent study credit or something like that。

 And we get to know them。 and， and they have a really good time。

 and they start doing something a hell a lot harder than anything I could reasonably ask you to do in a class。

 if I asked everybody in the class to do some of the things that my PhD students do。

 it would be a tough class。😊，And， and typically， what happens is， you know。

 there's a whole bunch of letters of recommendation and all this foy。

 But typically what happens is that student gets around of the senior year。 And at some point， like。

 I don't know， I'm bored。 I'm like， hey， by the way， like。

 what are you doing like next year or something like that。 And they're like， I don't know。

 I've got these offers from， from these companies。 But I'm not so excited about them。 And， or。

 or they're like， I'm just really want to get into this part of the industry。 And， and sometimes。😊。

Sometimes I know people。Right， and， and what I mean by that is as not， I'm calling in favors。

 It's like one of the more interesting aspects of the job is to get students that are great。😊。

Where do they want to be？So it's a good thing for me to go， oh， like the student is like in my class。

 and they've been like in the lab for like the last six months。 So I know them pretty well。😊。

That's when I go call my friend and like， oh， they want to go into the game industry。 And like。

 I don't know， like Robblox is offering them this like entry level driver position or something like that。

 That's a total waste。 That's when I go call the like， you know， lead engineer Roblox。 I'm like。

 there's like a superstar here at Stanford that wants to work for you。 Like。

 can you get them a good job。 and so that， that's the stuff that opens up doors。

 It's not like you got to know people to。😊，Cause they like， if you know someone， you' get a good job。

 it's more like， you know， Stanford professors are pretty well connected with other people in the industry that are doing interesting stuff because they used to be our students or。

 we're hanging out with them and stuff like that。 And everybody in the world loves to pass on really strong people to other people and make stuff happen。

😊，And so that， that's a really great part of my job。 I love that a lot more than like， you know。

 dealing with people that have to take a remote exam next week。 you know。

 that's like the least last thing I want to do。 And。

 and that's where you find the pretty interesting stuff。 right， Like I， I'll give you。

 I'll give you an example is there was a student。😊，Quite a while ago now。

 like five years from now came up to me in my equivalent of C S 3，48 K。 It was like。

 I'm really interested in PhD programs in graphics and actually， the time of like photography。

 like Google photography stuff。😊，And and and this student was good。 But I was like。

 that you don't have a chance of getting into like you， you're gonna w to go to a good PhD program。

 And I was like， let's just be honest you're not。 you haven't done the research。

 You don't have the background to get into to good the type of places that you want to get。

 I was like， I know you're good enough。 but you just don't have like there's no way it can be justified in the emissions process。

 And so I was like， well what do you want to do like I want to do like really awesome like fancy Google camera app kind of stuff。

 And I said， oh， okay， so here's what we're gonna do is we're gonna take。

 So Google would just publish the paper on how their HDR and portrait mode stuff works， And I said。

 okay， in my class because there's an openend class project。 Here's I want you to do。

 I want you to read the paper。😊，And I want you to try and implement the paper。

 That's your class project。And if you can get this thing implemented and get it to work。

 that's like the perfect opening for me to go tell the person who I know that runs that groove that you're looking to like get in with his PhD students and do some work。

 right， because this is a person that was like second half of senior year。

 There was no opportunity for them to do research or build a resume anymore。😊，And， and。

 and the folks like saw that class project and they were like， yeah， A， if， if， if you know。

 if he's taking like Calin's classes and Calin says this persons good and this person has put their actions on like reading our work and implementing their own version。

 we think this person's terrible， even though most people we hire PhD students。😊。

And so they struck a deal。 They said， look， we'll have you work with all of our PhD hires as long as you promise you you know if we're gonna put the time into you。

 you need to stay for two years or something like that， right， And so he said， okay， fine。

 like there's no better way for me to prepare to grad school than go work with the top people in the field in Google at the time。

 And that's how it worked out。 He worked with them by the second year。

 they'd given this person some opportunity to write a paper too。

 And then he had the strongest resume in the planet and got into Berkeley two years later。

 was already halfway done， got out of Berkeley， I think in like four years。

 And I think now he's at anthropic or something like that or and stuff。

 So that's just an example of like if you get to know your faculty a little bit better。😊。

We want to help。So that's。That's just some， some advice。 You know， again， not for me。

 maybe for anybody here at Stanford， you might like other classes better， but usually you're。

 you're here because the people around here are pretty good， so。You， use that resource。

So just a few practical things about that。 here's what happens almost all the time。

So I get students all the time say， I'm really interested in parallel systems。

 I there anything I can do in your lab。Which I first， I was like， great。 That's awesome。 And then I。

 I， I start wonder， you know， I my next question to myself in my head is。😊。

Can I find a good fit for the student？And a lot of the students come up to me and say this before taking 149 or any of these classes。

 And for those students， I kind of have to say， look。

 like we have to assume you have some base knowledge。 We can't teach you the assignments in 1。

49 in an independent study， you might as well just take the course。

 So typically what the faculty look like is like， is the student really interested or they just kind of think that they're interested。

 And if they're really interested， they would have taken your course。

 and they would have done a really good job on at least something in the course to show that they're really interested in it Like if somebody comes up to me and says I have a B in 149。

 I'm like， well， if you were really interested， like I gave you like some of the coolest stuff that I can think of。

 like why didn't that get you excited。 And sometimes they're like， well， I have this other thing。

 But if you look carefully my last two projects are awesome。 I'm like， oh yeah， that's true。

 Like let's go forward。 So so there's a little bit of that So there is a filter of there are plenty of opportunities in class to show that you're super interested。

 especially in classes of projects。😊，So I kind of ask my question know questions like this。

 Have they taken the courses that are relevant to doing anything in that area。

 Are there examples of them just going beyond expectations， Like this person's actually interested。

 Have they been talking to me in office hours， Have they worked on anything of sort in relating classes or do they have like an industry internship in a video like。

 oh， you've been like the co a team and a video like you totally know what you're talking about or something like that。

😊，Okay， so there's also a few pitfalls after I say all this stuff。 So first of all。

 I often get a lot of emails right during finals week。And like everybody else。

 like our heads are kind of going all over the place during finals week。

 And sometimes like after we get all the grades done。

 that's like right when I'm about to head off to family。😊。

And I just don't get around to responding until I get back。And at that point。

 that email is like 1000 emails down in my inbox， right， So if I don't respond。

 just please keep emailing again and email again loudly。Like like you would， there。

 there become it sounds very upy， but there is a point for your Stanford faculty where it is no longer possible to actually answer the emails that we get with a personal level。

 And so if we don't respond， it's not because we're not interested in you。

 It's just slipped through the cracks and just be persistent。

So email again in all caps in a friendly way with a smiley face to make it right or plant your sit outside my door and say。

 hey， at some point today you're gonna be free。 I'm just gonna stand outside and wait till you're free。

 The other thing is that we want you to have a good experience。

 And sometimes it's hard to find a good fit。 You know。

 there are projects where we're just getting started， we don't really know what we're doing。

 And so it's hard to give somebody something to do like three days later。

 we were like oh just kidding。 we thought that was a good idea now we're go in this direction。

 So sometimes I'm just gonna say like， look， you're awesome。

 But like I just don't know how to fit you into anything right now。 And so that will happen as well。

 So don don't take that personally from any faculty So I think that you know the big point here is now that we get later in the junior senior masters programs。

 your job is to try and start making some decisions about where do you really want to get yourself make some bets。

 And。😊，Sometimes those bets are best done outside the classroom。

 Sometimes they're not done outside the classroom。 And so I just want to make sure that people aren't。

Overfitting， too。Some stuff that you might hear， which is like， look， like。

 you have to have this internship。 You have to have this many A's or something like that in order to get those good jobs。

That's how you get like the hard to get normal jobs。I think， actually。 but there。

 there are definitely grades that you can figuratively get from working with folks through a recommendation or through。

 you know， just some professor going， hey， have you ever thought about this company because like they be。

 you might be really interested in going there。 there's ways to do things that are maybe a little bit better than A's and A plus。

 So I'll leave it at that。 We have five minutes， I guess I can hang on a little bit。

 have a good break。 send me a postcard or something if you go in somewhere interested。

 I'll put it on my bulletin board。 Alright， let's get out of。😊。



![](img/7d651cf9f64706596146a9b68febffb4_4.png)