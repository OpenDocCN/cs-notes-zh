# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p26 -26-  L21_Memory Organization, Technology, Hierarchy & Caches (Spring 2025).zh_e -BV1iV1XBWEJW_p26-

![](img/ff856a208c9bdf150731fedfd0e928b4_0.png)

How about now can you hear me， okay，' online？Okay， that's good， thanks。对吧。すは？可能是。嗯嗯嗯。错了。中。如果。什。这个。

Thank。Thank。然子。这。嗯。さ。是。I。あ？会。回。就说啥情。あ。两个。你都。上他。每都。那你有时候个。都是原来。Yes。好。样。そ。でです。不错。我s。嗯。看到这时刻。あか。Thank。

客在。然个。对。Yes。Oh。快等等。没打。I。🎼嗯好。Okayか。Okay， let's get started。

Now we're into the last five lectures of the semester and we're going to go deeper into memory today。

 which is as you learned from the last lecture， one of the most critical components， you can hear me。

😊，Is it good to know， how about no？It's this is on， it's green， okay？Oh but no better， yeah。

 I'll use the other one。On was good。没给力。😊，if you don't have robustness sense。

 you don't have computing。Let's see。Is this better？我 good。Okay， I don't know what the problem is。

 is it online online good？是。One9 is good， sir。I don't know what station over there。

 but this is green。And I don't know， oh， is this muted Okay， how about now somehow it was muted。

 Okay， there you go。😊，So this is what we call a user error。

I should I checked the mute button over here。 Oh good， All right， okay。Okay。

 so it's not the fault of the hardware， it's fault of the user in this case and a lot of computing errors are actual user errors there have been a lot of studies。

😊，that are made and users are the ones who make the most mistakes。

 but then software bugs and also hardware bugs are also quite substantial later on user areas are a bit easier to fix。

😊，Okay， so we're going to talk about memory and my hope is。

 we'll at least cover the basics of caches today。😊。

But just a reminder you have an opportunity for another 1% extra credit by using MDdlf's seminal paper and these are some of the readings。

 so if you want to supplement what we're talking about。

 please especially do the chapter that we wrote with my PhD student about 11 years ago。

 it's really a nice introduction of for a layman actually， for memory systems。😊，Okay。

 last time we covered memory critical for our computing and we discussed many different metrics that memory design affect。

😊，We talked about some memory fundamentals， which I'm not going to talk about again。

 we were talking about memory organization and technology。😊。

And I'm going to go through some slides again to jog your memory and this was a hierarchical memory structure that we looked at。

 especially in the DM subsystem。 I'm going to talk a lot about DM subsystem today。

 and then we're going to talk about other things too。

 but if you recall you have a memory controller and then it's connected we have some buses channel to many memory modules and each memory module has memory chips and each chip internally has a bunch of arrays called banks and each bank consists of a two- dimensionmensional array of cells but then we're going to break this also down in a little bit so we're going to really understand the lower level operation of this as well and we looked at the DM subsystem organization from the top down I'll go through these slides relatively quickly because we covered them again these are the channels connected their real processor you can see four modules here or dual inline memory modules。

And each module has a front and a back in this particular case。

And these are called ranks basically it's a collection of eight chips in this case。 it could be4。

 it could be 16。 it could be 32 depending on chips and then these ranks share address and command buses and data buses as you can see so it can access only one rank at a time at a given time and part of the one of the bits in the address if you have two ranks one bit needs to determine which rank you're accessing so basically mapping the data to the appropriate rank becomes an issue and we will talk about that in a little bit so essentially physical address。

 part of the physical address is used is called chip select let's say an old terminology but it's called rank selecting this you're really selecting one of the ranks using one bit of the address。

And then you access the data， you get 64 bits from a rank， and there's a multiplexer， as you can see。

 depending on which rank you're accessing， this multiplex is also controlled by the rank select signal over here。

 and then you pick the data that you're accessing and then send it to the processor。😊。

Okay that's how we access 64 bytes we're going to see a little bit more of that also and then we broke down the rank each rank consists of eight chips and each of the chips supply eight of these bits so that you get a wide supply of data even though each chip supply a smaller piece of the data eight bits for cost reasons because if each chip was supplying a larger amount of data there would be more pins in the DM chips so the cost would be much higher this way we have lower cost chips but then we can aggregate them together so that we can actually get higher bandwidth。

 let's say higher data throughput by accessing all of the chips concurrently at the same time right that's the idea over here that's why it's called their rank it's kind of like a rank of soldiers。

 all of these chips receive the same command same address。

 same row etc except they provide different data right。So they do the same thing。

 but provide different data in this particular case。And then if you look at a chip。

 it consists of eight banks and you've seen banks before bank there was a good reason for having banks。

 which is if you didn't have a bank， if you didn't partition the data array into banks。

 then you would have a single multiple array given the same size。

 total size and single multiple array would be very long latency because of the interconnects and the road decoder etc that you need to build and the multiplexer in this case you partitioned it to eight banks and this way each bank can be lower latency and you can also exploit the parallelism or concurrency across banks by starting multiple accesses across different banks either in the same cycle or across different cycles in this particular case we're looking at DM so DM is very costs so starting accesses concurrently across all banks requires you to send the address send an address to each bank and a command to each bank which is really expensive so if you want to send an address and a command to each bank you need to actually have pins to support8。

Current address is an 8 concur。Commands to be sent to each bank that's expensive so normally DM chips are built by sending one address and one command to a particular bank at a given time。

 and then you start access to that bank and then in the next cycle。

 next clock cycle you can send the other address to another bank this way you don't need to support more address and command pins than needed for one bank。

So I'm giving you the design choices that are actually there。

 many of them are dictated by cost as you can see， but you still get some pipelining benefit because of you can access banks concurrently after you start the accesses and you seen this before we've seen this in vector processinging as early as vector processinging but now we're looking inside the chip we're going look a little bit more inside the chip before we move on to other things okay once you break down the bank it's a two dimensional array structure and essentially you see two dimensional array of cells each of these over here is a cell it's not to scale because you can see that you have 32000 rows in this particular case and2 kilobytes of columns which is 16000 if you think about it and one column can be thought of as one byte essentially so when you access the there's something called a row buffer we're going to talk a little bit more about that it's really a row of sense splifiers that's how you sense the data and data needs to come to the row buffer first when you access a row and then you access different bytes in the row so if you want to access。

One bite， for example， you bring in the entire2 kilo bytes of row。😡，Into the row buffer， send them。

 and then you multiplex using this multiplexer， which you know very well about multiplex 1 by out of that row buffer。

 That's how you get a single byte out of a bank。And you get you get different biketes different banks in different cycles as you can see and that multipleplxer helps you select which bank you're accessing Okay。

 this is where we stopped actually I kind of spent a little bit more time than expected to talk about this because we're going to build up using this。

😊，But even this an abstraction so we're going break down this row buffer into smaller let's say arrays because building this 32000 by 16000 bit cell array is possible but if you build it it's long latency because you have a large decoder you have large interconnects and that increases the latency ourrc delay and also a reliability is hard to maintain if you have very large arrays it's easier to build large arrays at low latency as well as high reliability so we're going to break it down but before we break it down。

 this is the abstraction normally what a memory controller sees so how does this thing operate so assume that we have these columns and rows when the memory control。

😊，Color needs to access a bank， I already said this lecture internally a bank consists so many cells and other structure that enable access to cells I'm going to go internally a little bit more。

 but basically when you want to access a bank you first need to bring the road that you're accessing so you need to supply two addresses your whole address and call them address。

 which is part of your physical address。😊，After you supply the row address。

 the data needs to be sensed using sense amplifiers。

 the sense amplifiers are also called a row buffer。

 we're going to see this a little bit more in detail how this is built。

 it's actually built using SGM like cells across a couple of inverters。😡。

Initially you have nothing to sense you didn't access this array now if the memory controller wants to access row0 column0。

 what it does is it send the row address0， which gets decoded using a row decoder。

 which very which is the same as the decoder that you've seen in the past。😊。

And this row decoder enables a word line of row0， all of the cells in that word line gets connected to their respective bit lines or columns。

😡，And the robot buffer， the sensor fire sends the data in those cells and then basically captures the data in the robot in the robot buffer。

 Now we've captured the data。 We're going to see this a little bit more。

 Now you have the entire2 kilote。 let's say that row is2 kilobytes as consistent with the previous picture。

 Now the memory controller sends a column address。 And let's say we want to eat column0。

 we want to read the data at column 0。 let's say that's an one byte data。 It sends a column address。

 And this column address is used to multiplex out Every single one byte inside this2 kilobyte row buffer。

 So you basically have a very wide multiplexer。 and you select the byte you want in this case。

 a0 byte in that particular robot buffer。 sounds good right。 you know how these are built。

 This is just a bigger memory。 We actually built something like this with d flip flops。

 Now we're going to talk about DM。😊，Does that sound good， its actually fascinating， I think。Okay。

 so this is how once the command comes， the multiplexer operates and the data gets multipleed out and it goes on the bus to the processor ship。

😊，Okay this sounds good Now if the memory controllert wants to access row zero column1。

 it can do an optimization because row zero is already in the row buffer so we actually already read two kilobytes of data inside this row buffer it's in the sense amifiers and the memory controllert I can record that and know that it has to actually record that and know that and now if the processor wants to access row zero column one the memory controllert say oh the rows already in the row buffer I don't need to activate it again meaning I don't need to access I don't need to supply the row address again I don't need to go through the row decoder etc ceter it's already there so I just want to this' call the row buffer hit and we're gonna to see caching soon that's actually an example of a cache which is really fitting here so we've already access that two kilobytes of data now let let's actually access the second column in that data or column one in that data so memory controllerter realized that it's a hit。

It supplies column address1， which multipleples out the next。😡。

Byte compared to the column address zero， and now the data comes out。😡，Sounds good， right。

 This access latency is clearly faster， shorter because we didn't have to access this huge array。

 We just needed to access this row buffer using a column address。

 We just need to go through the column multiplepl。😡，So this is an example of caching。

 we're going to introduce a notion of caching basically we accessed a lot of data initially concurrently and then we put it inside the row buffer which is an example of a cache which is essentially a circuit that memorizes the data or remembers the data and then if we want to access the same row again。

 the access is much faster because it's already there in the cache or row buffer okay let's take a look at another example。

 if the processor wants to access row zero column 85。😡，Then again。

 the memory controller recognizes this is a row buffer hit because row zero is already open inside the row row buffer。

 and then it supplies column matter 85， which triggers the multiple here to multiplex out。😊。

The data from the row buffer， the appropriate byte column 85 from here now if you can think of how a pro accesses data let's say let's assume you're going to an array and your data is all mapped in the row buffer entire2 kilobytes if you're accessing every single byte what you can do is you first access one byte column zero column1 column 2 column3 column4 column 5 column 6 column seven column8 until column 128 or so easily you can go through the entire elements that you're accessing and they will all be almost except for the first one they will all be row buffer hits so the access will be faster because you have the structure called row buffer that's a cache。

😊，Makes sense， right？Now the problem happens if the processor wants to access row1。

The memory controller gets this status from the processor row1 column zero memory controller checks in this bank。

 of course we're looking at a single bank here if this goes to a different bank that's a different issue in this bank row zero is open。

 but I want row one。😊，And then the memory controller says okay。

 now I have to do something first I have to close the row 0 because there's a conflict。

 I cannot open row0 and row1 at the same time。 This is only a single row that I can cache or buffer So this is a conflict。

 the memory controller first writes back the row It's called precharging It's not exactly right back but it could be right back also depending on whether you updated the data it writes back the row into the array and then so it takes time and then it supplies row address1。

Wwhich goes through the row decoder， it activates the word line belonging to row 1。

 and then the bit liness from the cells that are in row1 get connected to the sensorifiers corresponding to sensor fires concurrently the entire3 kilobytes。

 and the sensorifier sense it， make the data strong inside the row buffer and now the row buffer can be accessed because it contains the contents of row 1。

Now the American chart needs to send the column address0， which belongs to01。

 and then the column maxs multiplexes out zero column。😊。

Now you've seen this conflict took a longer time， right？Roe buffer hits was fast。

 Rob buffer conflict is slow because Rob buffer conflict says you need to write back the current rope in the row buffer and open it another row and then do another access so there are three steps to do this you need to precharge or write back the current rope。

 you need to activate the next row and you need to send the column address to get the appropriate column。

Okay， this is actually exactly how a D chip operates。

 We are looking at just single bank over here ideally。

 of course you would like to maximize the robot buffer hits so this is affected by a lot of things how you map the data into your banks。

 how you map the data into your rows， what are the access patterns that happen from the processor so if the processor is always sequentially accessing data and the data is sequentially mapped in the robot buffer that's good。

 you get a lot of row buffer hits like I explained。😊，If the access panel of the processor is random。

 you always keep accessing random accesses， random addresses。😡。

What happens is you'll get robotbo for conflicts because of the nature of randomness right you will not access if the access are truly random。

 then the probability of hitting in the row buffer is very， very， very low。

 you can actually calculate that probability with true randomness then you will actually get robotbo for conflicts and your access latency is much longer because you keep writing back the row activating the next row and doing the column axis。

This is why the memory performance matters a lot because in terms of latencies in D we're talking about 25 nanoseconds for a robot hit。

 give or take and 75 nanoseconds for a robot for conflict。😡，Let's say it's in that order。

Doesn't sound very good， right？If you think about the processor frequency today， five gigahHtz。😡。

75 nanoseconds is 75 times five cycles， it can do the calculation that's more than 350 cycles。

Protor cycles Earl， we were talking about one cycle， say one cycle here in the processor。

Remember that saving one cycle right data forwarding。

 et cetera we did all of those things when we built the pipeline now once you go into the memory hierarchy。

 if you're waiting this is why this is why a lot of the processors are waiting for data because the latets these year are much much longer。

😡，Even though we try to still optimize the latencies， they're still much longer。Okay， okay。

 I already said this this is an abstraction so we're going to go into a little bit more detail。

 so it turns out this is very hard to build。😡，Even this huge bank is hard to build， as I said。

 because the interconnects are much longer So what people do is they partition the array into smaller subways。

😡，These are called subs when you access data you actually activate one sub and then you sense the data and a local row buffer so what you do is you bring the data only 512 rows so the interconnects。

 the bit liness are actually short and this enables you to sense the data much faster and also more reliably and then you have bigger interconnects that are not exactly shown here actually they're shown kind of here but it's not actually a very accurate picture I'll show you better picture soon essentially you have bigger interconnects that drive out the data out of the chip so you bring the entire row into a smaller array sub over here smaller local row buffer and then if you want to access a column there are bigger interconnects over there。

That's just for you to think about。And this is actually a more complicated picture that's showing the role that you're accessing and think I'm not going to go through this。

 but I'm going go through some animations。 you can read this paper actually has a very nice overview of the DM subsystem from the ground up we're going to look at an example right now inside the DM chip because I want to go into a little bit more detail as to how how this thing works before we look at different technologies Does that sound good。

😊，Okay， you can study this picture on your own。 It's going to be very similar to what I'm going to describe with animations。

 So let's take a look at this again。 So this is another idea module。😊，It looks like this internally。

 and there are a lot of goals in the AM design actually， which I'm not going to talk about right now。

 but cost is one of the most important ones。😡，Latency is usually secondary to cost。

 the goal usually is capacity， how do I get high capacity？😡。

High capacity means you dedicate most of your area to the array itself。

 you don't want a lot of area in the peripheral circuitry。

 okay latency is important so we will divide things into hierarchical structures and then there's behind with parallels and power。

 energy reliable security there's a lot basically。Okay。

 let's take a look at this bit in a little bit more detail so here you can see actually eight banks。

 one bank over here and then it's basically replicated over here we're going to look at different structures inside the bank and this is cartoonish because we're going to see two different subways over here not really in a year I'm sure we have in a bank maybe 64 or 128 maybe6 subways。

😊，But I'm going to introduce the sifier because this is going to be interesting to you hopefully because this is our crosscoupled inverter if you remember earlier。

 this is what SM is， so in a DM chip you have this SM type of structure we're going to modify it a little bit to make it work with DM essentially have a crosscoupled inverter。

 this is our sifier。😊，Okay， we're going to modify it slightly。

 we're going add an enable signal when this is enabled， it's when when it's disabled。

 it's not sensing， when it's enabled， it does some operation。😡。

So basically there are two stable states of this and you can also imagine this when this is enabled you can have VDD meaning high voltage on top and low voltage over here。

 you can say this is a logical one because we're going to connect the sub over here so essentially this is a logical one and this is a logical zero top is0 and the bottom is high voltage when this enabled when this is disabled it's going to be we don't care what the value is but we want to set it to some reference value so that we can sense things I'm going to go through the sensing operation a little bit so what's the sensing operation basically there's some voltage on top we're going a little bit into the analog domain a bit but there with me there's some voltage on top and there's some voltage on the bottom VT VB top bottom when the s splifier is enabled the s sifier checks whether Vt is greater than VB because of actually the way things operate over here you don't need to go into a lot detail if VT is greater than VB。

😊，Circuit amplifies VT to high voltage and the bottom voltage to0。

So this is the basic global operation of sensing that we're going to build on and we're going to build DM with that's the basic idea this is what the sensing circuit does you need to modify a crosscod inverter a little bit to make this happen you don't need to know exactly how that works You can learn about it on your own。

But this session on the SM cell so now let's connect us to a DM cell remember DDM cell is a capacitor。

 we store charge in a capacitor and DM cell has two stable states。

 one is the empty state meaning there's no charge in the capacitor let's call this logical zero and the other is fully charged state meaning there is full charge in the capacitor。

 let's call the theological one now we're going see how we sense these students the issue with a DM cell is because we want to maximize cap。

 we want to make this capacitor as small as possible it's amazing actually how small these capacitors are in DM today。

ItIt's the inventions that are much smaller than some of the other circuitry that we have and it's very hard to make it work correctly also okay but basically these are small。

 they cannot directly drive circuits so you need to sense what's inside this capacitor to understand whether it's a zero or1。

 you cannot just connect it to a circuit and say okay if this capacitor has charge it'll gonna drive an end gate for example that's not going to work you need to have the special sense amplifier and when you read this actually reading destroy the state also because when you actually sense when you actually read the charge over there。

 you're actually taking the charge out So you need to replenish the charge whenever you read the I mean you need to put the charge back in it if you want to keep the state that you read。

Okay， so this is how we are going to sense the cell。 basically this is our capacitor。

 this is our sensor fire。 we would like to sense zero over here clearly and we would like to sense one over here。

 So this is ideally what we would like to happen so we're going to connect。😊。

The capacitor to the sensorifier using an access transistor。

 there's actually a transistor we've seen transistors before。

 this access transistor will enable us to connect the capacitor to the bit。😊。

And then the bit line is connected on this end to the top of the Sen fire and then there is the other end of the c fire so basically these are what we have seen earlier。

 this is a word line I'm showing you only one cell over here but this is the access transistor that's connected to a word line which is not exactly shown here the control over here is the word line we will see that later on and then this is a bit line so I'm showing you one cell but you can imagine a grid of cells two dimensional array of cells that we're going to build soon on top of this but let's look at this operation if you enable the access transistor the capacitor gets connected to the bit line so it actually starts sharing its charge it's called charge sharing it shares its charged with the bit line okay if forgot something very important。

You basically set the different end of end of the s fire。

 the top end to and the bottom end to a voltage level of health VDD initially they're both equal and the s fire is not enabled they're not connected to each other initially okay what happens is because we want to sense whether this is lower than BDD or higher than EDD okay so if this charge。

When you connect it to the bit line， what happens is it shares a little bit of charge to the bit line。

 and this becomes。VDD plus some delta value， let's say right or gamma or epsilon。

 whatever you want to call it right essentially now the circuits。

 there's some charges shared to the bit and this Bitcoin is not VDD anymore want to have VD anymore it's VDD want to have VDD plus something。

Now， if you enable the C fire because of the operation that I described earlier， because this site。

 the top voltage is greater than the bottom voltage， sensor fire will。😡。

Slowly and at some point fast。Amplify the top value， top voltage to VDD and the bottom voltage to0。

 This is how you send a very small charge value and then amplified to the high voltage level that you want to use in circuits。

 Okay， this is basically， this is the operation of the。 Now， you know， exactly how all memory。

 all main memory in the world operates。 This is how it operates。😊。

Okay now let's see what we can build on top of it and then once this happens actually very interesting and happens。

 once you amplify the charge over here， this becomes VDD and the sense empire is now strong this charge goes back because now the charge is huge over here and that charge goes back and fills the capacitor right that's how you replenish the capacitor that's called charge restoration。

😡，So you connect the access transistor， once you connect the access transistor the cell shares it's charged with the bit line and cempifier senses that charge。

 amplifies it and then restores the charge into the cell again so that the cell has one and the sempifier sense one and this is a stable state after that point after restoration of course these operations take time so there nanoseconds it takes nanoseconds to make this work because this is really small。

😡，If the DMM cell was much larger， it will take faster actually。

 because a lot of charge will get out and things will operate faster。

 but a DMM cell that's large is not good for capacity right today we want capacities that are huge for many many reasons machine learning being one of them but many applications if you want capacities to be huge that cell needs to be much smaller。

😡，Okay， now let's build it higher， so this is our capacitor access transistor and s fire。

This is our building blocks so we're going to build a subway。

 this is our bit line now on this part of the bit line you have these three cells。

 you can also connect something else on the other side of the bit line it operates exactly the same it's just the opposite side right。

😊，This is our bit line now a single bit line， it could be 512 cells connected to it。

 and then this is our wordline now， this is our structure。

 you just need to add the same thing and replicate it， right。😊。

Now you see a two dimensional array structure that part of our subine。Okay。

That's and then you have to have an send fire enable signal of course。

 and then you connect your road decoder， this is four by six array as you can see。

 but in real life it's 512 by 512 potentially。😊，This is an area of sensor fires in real life it could be 8 kilobits。

2 kilobytes， and then these are the cell arrays that belong to the same sub。😊。

Now you put more subways together， more row decoders， and that gives you a DM bank。

 and then you need to actually have a way of connecting what you sensed to the IOL outputs of the bank。

 meaning because you want to upload it out of the chip so you need to have additional interconnects that connect the sense empires to the bank IO。

 but these don't need to be very wide， it can be only 64 bits for example， in the bank。

 8 bytes for example， it could be even one byte。Okay。

 and then the address needs to get distributed so which row you're accessing depends on which sub address you have so this is a physical address determines which sub you're accessing which row you're accessing。

 etcter。And then there's part of the address that also gets used for column select because if you have the data inside the Cumifiers。

 then you need to select which column you're accessing， right to which H bytes。

 which byte you're accessing。😊，Okay， so basically that's it。

 I will go through this also relatively quickly， but a chip may output only 8 bits as we have seen earlier。

 but this is how the8 bits come， there is an internal bus sorry there is an internal bus it's just8 bits let's say and each bank is connected to it and each bank at some point can provide 8 bits which is a single column to this internal bus。

Okay。Now let's look at the steps again， so this is two subways， assume that you have an address。

 you first supply the row address and then you decide which subway it goes to of course because part of the address determines which sub it is assume that it's this row and you want to access this black column in this yellowish row you first need to activate the row by supplying the row address which brings the data into the sensorifiers that are local inside the subway。

😊，You wait until sifier send the data and amplify data to restore the cells， et ceter and then。

The memory controller sends a read signal。 let's say。 I'm going to read column X here。

 So the memory controller needs to send this column address， as well as the read commands。

 which brings the data into the bank IO through some interconnects that are not really shown here。

Which is what we saw earlier in the bank level picture， but we're looking a little bit deeper here。😊。

And then now the row is open， the row that's activated is open and the local lo buffer。

 if you want to access some other row， you need to set the sensoromifier to a stable state or reference voltage。

😊，Because sensorifiers， when you sense when you open the row。

 the values on the sensorifiers are essentially determined by the values that you read from the capacitors now if you want to open another row。

 you need to set those sensorifiers to a reference voltage so that they can sense another row。

 what was the reference voltage the top of the sensorifier as onehe EDD the bottom is also onehe EDD now basically there needs to be some circuit that I didn't explain to do that but this is the precharge circuitry essentially precharge circuitry goes and changes the voltages such that first writes back the data into the cells which I didn't which actually happens kind of automatically but then sets the voltages of the sifier to onehe EDD on either side so that you can start the next axis reliably。

That's the precharge operation， basically row becomes closed after that so that you can activate another role so that you can sense that row reliably。

😡，Now actually Ive demystified all the magic， basically there's no magic on how this operates。

 assuming what I said is true and what I said is true， essentially the old memory operates this way。

 all main memory operates this way today。😡，Okay， so if you're interested。

 you can if you want to do some more reading， there's a comprehensive DMM background in this paper that we wrote。

 we just need to look at section two that builds up the DM。

 but you can also study what I just said any questions now you know how DM operates。😊。

Which is good because you're going to see a lot of DM in your life。Maybe。Okay。

 now let's let's go into how data gets mapped and how we actually access a cache line we're going to look at cache lines later on。

 I've given you the let's say organizational perspective so far now let's look at the operational perspective。

So I have some physical memory space and I have some data that I want to access that's called the 64 byte cache block it could be smaller also but usually as you will see later in the lectures you operate paid using 64 bytes whenever a processor wants to access some data it wants to access 64 bytes for the reasons we're going to talk about later I assume that this is the case but the operational principles are the same if you want to access smaller data also so it turns out the 64 byte cache block gets mapped to a single rank。

😊，So a single rank in a single channel。That's called the stem zero rank zero right so this 64 byte gets mapped over here and we want to access 64 bys so how do we do that so let's take a look at that rank This rank  zero looks like this And if you remember the picture that I showed you earlier each chip there are eight chips in a rank and each chip supplies8 bits and we've seen the internals of a chip also now so there is no magic。

😡，Each chip supplies  eight bits， but we want to get 64 bytes。

 meaning if we access all chips concurrently， we'll get 64 bits。😡，So we're going to do that。

 we're going to access all chips concurrently to get the first byte。

 and then we're going to access all chips concurrently again to get the next byte。😡。

And then we're going to access all the chips concurrently again to get the next byte and then the next bitete and the nextte。

 So we're going to do 8 accesses concurrently to all of these chips to get 64 bys。

 If you wanted  one by。You access all chips concurrently onces if you wanted 64 bytes。

 you access all chips concurrently eight times if you wanted 256 bytes。

 you access all chips 16 times， right？😡，Yes， I think no， 32 times， not6。 Okay， I can still do math。

Okay， so basically for this to work， the data needs to be mapped correctly in this case， for example。

 the first byte comes from first eight bits comes from here， the second eight bits comes from here。

 the second eight bits comes from here。😊，So basically with every single axis， you get eight bytes。

 right？So this is one byte， one byte， so there are  eight bytes， so you get  eight bytes over here。

 that's 64 of it。😡，And then you move to the next。Let's say column row zero column one in each chip so initially you access row zero column zero in each chip get eight bytes。

 then you access row zero column1 to get the next eight bytes。

 then you access row zero column2 et ceter I already said this so basically if you want to access 64 bytes it takes eight cycles8 IO cycles to transfer and during the process eight columns that are read sequentially and the good news is it comes from the robot buffer right initially it may not be in the row buffer initially you get a it takes some time but after that all of these are in the row buffer and you access row buffer sequentially okay so you get row hits。

😊，Okay， so now you know actually how to access a cache block also。

 we're going to see how to design caches later， but the operational principle of accessing 1 by is the same。

 You basically just access all of the chips concurrently so that you get。😊。

Essentially eight bys and then you pick the bite you want over here， right？😡。

You can decide which bike to pick， okay， okay。Okay is I should also say that this is one way of designing DM。

 this is the common way in general purpose computing there could be other ways to design。

 but if you look at DM today HM high bandwidth with memory for example LDDR low power DM they're different kinds of DM but all of them operate pages on the same fundamental principles at the core the array is essentially the same but's matters sometimes as the interface for example。

 how do you design the interconnects so that they're high speed or they're low power etc。

 but these are below the abstraction of this course they're also architectural issues but again we cannot cover everything in this course。

😡，Okay now I'll move to memory technology， although we have been talking about memory technology。

 let's talk about Dm a bit more now you know D a lot。 I'll go through this relatively quickly。

 Ive already said everything over here it's dynamic capacitor charge states indicates stored value whether the capacitor is charged or discharge indicates storage of one or0 so you have one capacitor that's why this is very dense that's why many memories are built this way and you need an access transistor to access that capacitor so that you can connect the capacitor to the bit line and then sense it and the row enable or word line enables that access transistor and you know exactly how this operates now。

😡，Now there's another issue with Dm， which is。When you have capacitor and when you have this sort of access transistor。

 it turns out there's some path that is still active。

 so there's some leakage that happens through this capacitor， there's an RC path。

 even though you have not enabled the row， meaning enabled the access transistor。

 there's some leakage that happens。So DM itself loses charge over time you start some charge but it keeps leaking over time iss one of the reasons why it's dynamic so it needs to be refreshed so this sort of memory needs to be refresh periodically and today we're refreshing so for example in my pocket my cell phone is refreshing every single cell every 32 milliseconds or so at high temperatures could be even worse while operating this laptop is refreshing all of its memory at this point once in a while every 64 milliseconds or every 32 milliseconds memory control goes and refreshes every resell。

In the， every role， I should say because this happens at the program Grand late。

So our refresh is really reading the role and writing it back so that you restore the chart completely so that you don't get data corruption。

Okay a memory that doesn't have this problem SM Sstrm a static random access memory you've seen this before also now we have two crosscoupled inverters that store a single bit this feedback path enables the stored value to stay in the cell as long as it's powered on both of these are volatile memory technologies for these to keep the data they need to be powered on they lose once you lose the power you will lose all the data and DJM and SstrM in this case you have four transistors for storage because you know from lecture one or two that each each inverter is two transistors in CMmo technology and then you may have two transor for access and I explain the operation of this briefly last time I will not go into the details again。

 but you can see immediately that this is quite expensive you have six transistors already and there are versions of this that are eight transistors and theyre bit and bit loss so there's some differential sense。

😊，But in the end， whether you're designing SstrM or DM or some other technology， a lot of memories。

 actually almost all of them look like this， so you basically have a bank。😊，Internally。

 the bank actually can be subs， etc cetera like we have seen。

 but let's let's look at the bank abstraction right now。

 you have a two-dimensal storage array and then you have a row decoder to access the row and the red access sequence happens to be you decode the row address。

 drive the word line in this case attributee word line you drive a single word line assume that we want to access this row the blue row and we want to access the red column and then the selected bits the selected bits drive the bit lines you read the entire row you amplify the row data in different technologies have different ways of amplifying you've seen the quite a bit and then you decode the column the least significant bits that are coming from the address most significant bits are used for the row least significant bits are used for the column these significant bits enable this multiplex here to multiplex the by or bits or whatever grand layer you're accessing out from the member。

😊，And then you precharge the bit lines for the next axis。

 so DM or STM they both operate this way you've seen how DM operates exactly。

 we're not going to go into SstrM in detail SstrM is a little bit easier actually。😡。

Except when you go into extremely small technology notes。

 when you go into small technology node all the charge levels is also small so you get noise issues et cetera but we're not going to go into those issues right now。

 but still the operational principles are the same that's the beauty of memory like they all look like this in the end。

Okay so let's take a look at SstrM a little bit more this is ourM SM is used to design all of the on chipnames today。

 so if you look at the chip the processor chip over here。

 most of it is SM the reason most of it is SM is most of it is caches as we will talk about so all caches are designed using the SM technology。

😊，So this is our B cellll array in SstrM let's call it the bank again and you can see some numbers over here you use nbits of the address to decode one of the rows。

 enable the word line and essentially the access is the same right so you read the entire row and you do differential sensing so the sensing circuitry in SstrM is a bit different and then you select the column that you want and then you get the data out and if you want to access another row you precharge all the bit lines。

😊，Okay， essentially I will not go into this detail。

 but access latency is dominated by how fast you can drive the raw word line and how fast you can drive the bit line so these are interconnects if you're thinking about it right that's why increasing the size of this in terms of both x and y axis increases your latency right。

😊，Cycling time is basically how fast you can access the next roll。

It's really dominated by the interconnect latency， as well as how fast you can precharge all the bit liness。

 meaning prepare the array for the next axis。So these are all important latencies。

 but SM doesn't have the refresh problem， so because of the crosscod inverter。

 SM kind of amplified once you store some data inside the SM cell it keeps amplifying the data。😡。

It doesn't have a charged leakage problem because of the crosscod in， whereas DDM。

 it doesn't have a feedback mechanism to amplify its charge as a result it keeps losing and losing and losing charge。

 so you need to refresh it once in a while right。😡，Okay， but ramp is more expensive as you can see。

So DMM looks like this， I'm not going to go through this in detail essentially because we've already gone through this a lot。

 but essentially we've discussed it， so two differences from SM you have distractor reads whenever you access a row you destroy the data inside the capacitor so you need to amplify them。

 restore the charge and we've seen exactly how that works and your charge gets lost over time so you need to refresh it。

😊，Okay， we've already discussed all of this， so this is for your reference。

But they look essentially the same if you think about it， right it's just a technology。

 it's just a bit cell， the storage technology that's different。

 capacitor versus quacod inverter plus access circuit needs to be a little bit different also to take into account the storage medium。

😊，Okay， let's compare these two because this is actually important。

 this is why we are going to memory technology we're still we looked at memory organization now memory technology。

 we're looking at theMm and these technologies actually have different tradeoffs in the end that's why we'll build a memory hierarchy tool。

😊，So DM is in general， slower access because capacitor sensing is much slower process。😡。

You're really reading from the capacitor that's really small and you need to amplify that， as I said。

 this takes nanoseconds， many， many nanoseconds。😊，But because capacity is so small and also it requires only one access transistor。

 it's called a 1 T，1 c， one transistor， one capacitor cell， it's very high density。

 so you can actually have very high capacity in a given area。😡。

As a result of that it's also lower cost per bit and when you talk about memory you usually talk about cost per a bit so cost per bit is very low as a result all memories today big memories are D if you want storage it's going to be flash memory which I'm not going to talk about but I will mention that later on the downsides the green ones are good the red ones are bad basically it requires refresh if basically refresh is not good because it consumes power its least a performance issues and also it it has extra circuitry。

😡，Now manufacturing is also different so SGM is actually logic if you look at everything that I said over here there is no capacitor there is no extra difficult sensing circuitry et ceter so SGM manufacturing is compatible with logic process so you can actually build it directly inside a processor chip with the logic seamlessOS processor chip with the logic structures that we have seen earlier now D I'm introduced a capacitor that we have never seen let's say in earlier lectures except for yesterday except for last week that requires actually a very different fabrication technology and as a result。

😊，This cannot be put together with the CMmost logic easily， I should say。😡。

It's very inefficient to put it together， so this requires a completely different fabrication tabab。

 if you will， you need to build billions of dollars of Fab that's completely different for memory。😡。

That's why memory companies are very different from logic companies today。

 That's how the industry evolved。 Unfortunately， or fortunate。

 it's a bit unfortunate because if you marry these together。

 you can actually get a much better computing system。

 we're going talk about that okay so SstrM is exactly opposite of the ArM' faster access because there is no capacitor unfortunately it's very low density60 cell it's much smaller given a single bit requires much bigger area to store as a result it's much higher cost as a result。

 we don't build large memories with SM right there's no need for refresh that's good news for energy performance and circuitly and you can put this together with CMmos as a result you can actually all on chip memory are SstrM。

😊，Let me give you aside， these are not the only two technologies。

 this is an area that I have worked on quite a bit。

 I actually work a lot on memory in general but there are other technologies I'll give you one example over here phase change material so there is some phase change material example one example is childco glass it exists in two different states ammorphous and crystalline you can represent something like this so it looks like this basically this is a glass over here in one state this has low optical reflexivity and high electrical resistivity in the other state opposite state it has high optical reflexivity and low electrical resistivity meaning you can read this optically。

😊，Depending on the state， you can shine light on it and if the light reflects back。

 you can figure out whether you have stored a1 or0。

 now you can see that this is a very completely different technology right it also requires a completely different fabrication process。

 but this is a memory that can store data also， right。😡，And。

Or you can actually build something that detects a resistance so you can do this reading in two different ways optically or electrically。

 which is fascinating and people have actually worked a lot on figuring out how to do this reading fast electrically because optical reading is usually slow。

 unfortunately people have worked on that technology。

 if you had this CD reriable CD I mean people know about reriable CDs。😡，Okay， it still exists。

 okay I think it's it's getting an older technology， let's say if you have a irwriable C。

 it works based on these optical principles， slow。😊，But if this can be made memory main memory。

 you can use it， you can design circuitry to detect resistance。

 I'm not going to talk about that in detail， but you can read papers again。

 so we worked on actually enabling this as main memory so this could be very dense。

 this kind of technology can be extremely dense as you can see from CDs。😊，So DM， for example。

 it has some downsides as we will see in the next slides， PCM has some upsides。

 so if you can enable this technology you can have a much better main memory。😊。

And this is a paper we wrote and later Intel actually designed the 3DX point。

 unfortunately they discontinu it currently it's a bit sad because Intel has a lot of problems these days in addition to technology problems but basically it's a memory module that Intel designed let's say 10 years。

 after we evaluated and envisioned etc ce， and you can see that it's actually huge 120 gigabytes and its costs can be much lower。

 so if another technology comes in and if it can be manufactured reliably it could actually be very good for having much bigger memories。

😊，Now let me give you the differences between DM and PCM。

 so DM is actually faster access in this case， compared to PCM。

 it turns out because it has a capacitor， capacitor is faster。

 whereas PCM turns out to be slower access。😡，Because you need to have heating and cooling to change the phase of the memory。

TheEM is lower density， which is interesting because capacitor is less scalable。

 it has higher cost whereas phaseage material is much more scalable， you can make it much， much。

 much， much， much smaller than the capacitor itself the EM requires refresh phaseage memory doesn't require refresh。

😡，Yeah， I'm manufacturing。There needs to be fabS unfortunately PCM manufacturing。

 there needs to be also fabs it's not mature today and that's one of the reasons why Intel discontinued that they were not able to at least under the financial constraints they were。

 they were not able to make the fabrication process let's say extremely good Dm is Walto meaning loses data at loss of power PCM is non Walalto it doesn't lose data at loss of power。

 meaning this a storage technology but it could also be a main memory technology at the same time。😡。

DRM has no endurance problems as far as we know， but PCM has endurance problem， this is one downside。

 I will introduce it very quickly and then we'll take a break soon。

 but basically if you keep writing to a cell after some points the cell wears out in phase change memory this happens in flash memorym technology also meaning you cannot read or write from the cell anymore。

😊，This is a very technology dependent problem but flash memorym SSDs so let's say drives have the same problem but DM doesn't have that problem that's good unfortunately PCM has higher access energy than DMm so you can see that now we have tradeoffs right red Zen greens whenever you have red Zen greens it's good to think about how am I going to place this sort of technology in the memory hiarch and we're going to talk about that in the second part of lecture I'm going to pick it up from here talk a little bit about technology and then we're going to build up to memory hierarchy and caches soon。

😊，So let's take a break until the bell rings and we're going to talk about all of these。😊，嗯。Yeah。

Okay， everything is good。Okay， now we can continue。

So now you all know how DM operates in a lot of detail， SM operates in some detail。

 and now at least a high level order of PCM you can see that there are different technologies。😊。

I will also distinguish between charge versus resistant memories。

 especially on the main memory sites， very quickly again the difference between DM and face change memory is DM actually is charge-based memory flash memory is also like that SSDs are also like that but we're not going to talk about that you basically write data by capturing some charge and you read data by detecting some voltage you don't need to go through as detail whereas resistant memory is phase change memory magnetic memory for example。

 memory series which we may have heard of which we're not going to go into you essentially read data by detecting some resistance so these are two fundamentally different types of memories。

 the first one is volatile in general although it could be non-vaaltal also depending on how you do things whereas the second one is nonva。

😊，Okay let's go through the cell in detail so basically I've already given you a phase change memory。

 you basically store charge in terms of the phase of the material because resistance is determined by phase there are some other interesting technologies like spin talkque transfer MM magnetic memory you have a magnet and the polarity of the magnet determines whether you store a one or zero you have a reference magnet and you have a magnet that's free magnet and whether the magnets at the top is parallel or antiparall in terms of polarity to the reference magnet determines whether you have stored a one or zero and your resistance that really determined by the polarity and the way you read or write those memories by injecting enough current so that you change the polarity of the magnet to a different direction which is very fascinating this could also be potentially a very large scale memory but these are all relatively emerging technologies they're not there yet so you cannot buy these easily in the market except for some niche。

😊，Applications， for example， and then there's a memorys。

 You basically inject some current to change the atomic structure of some material and the resistance is determined by the distance of the atom。

 So you need to have reading circuitry to determine that resistance。

 So you can see that these are all different。Memories。

 they have all different reading mechanisms and writing mechanisms。

 but in the end their structure is the same the organization is two dimensional arrays in the end。

 it could be three dimensional in some cases， but we won't talk about three dimensional here where people are just building to three three dimensions now。

😊，Okay， so if you're interested in this， there's a lot more in some other lectures。

 which we don't really have time for， so I'm going to flash these slides。😊，Flash memory actually。

 the reason I talk about these is very important， so these emerging memory technologies you may say。

 okay， why is he talking about this？😊，These don't even maybe exist。

 I cannot even buy them in the market well there was a memory technology that you couldn't buy in the market。

 it didn't exist in the 1980s，90s， almost a lot of 2000s and that's flash memory SSDs today。😡。

So that flash memory operates based on again some chargebased principles。

 it can be made nonwalto essentially this was a very doubtful emerging technology for many。

 many decades， like 30， 40 decades almost and then people have figured out how to manufacture it nicely and also people have figured out how to use it nicely at the application level。

 for example， people have figured out how to store images on it， how to store music in it。

 how to store media in it and as a result that flash memorym technology is really what enabled a lot of the innovation at the mobile system so this thing is very usable today because it has a huge storage associated with it and that huge storage is really flash memory。

😊，If flash memory wasn't there， you would be carrying a huge cell phone with a lot of D or a magnetic disk。

😡，Wwhichch is not very good right clearly so these emerging memory technologies can enable new applications and new use cases and that's one of the actually important questions that people are asking in research。

 what can we do with them to make the systems a lot more efficient？😊，Okay， I'll leave at that。

 but if you look at a flash memory actually it's very complicated and it's very interesting。

 but if you're really interested in this stuff you can read papers。

 we're not going to go into that or take our advanced lectures。😊。



![](img/ff856a208c9bdf150731fedfd0e928b4_2.png)

Okay， there are lectures， as you can see， theres have an SSD course for the same reason also， okay。😊。



![](img/ff856a208c9bdf150731fedfd0e928b4_4.png)

So I'm going to talk maybe in the last lecture about processing in memory so one of the things that we do today is I will kind of flash this thing over here。

 one of the things that we do today is you have processor you have memory。

 what I've described so far is processor and memory are processors always asking memory for some data to come to bring to get right or it's writing data to memory。

 why not put the processor on the memory side also。😊。



![](img/ff856a208c9bdf150731fedfd0e928b4_6.png)

Based on what we discussed in the last lecture putting the press on the memory side is a very interesting proposition and this is something that's going on in research that we're trying to enable again this is like looking into the future because I'm finishing the memory technology lecture we're going to talk about memory hierarchy soon and we have a pressing and memory course also if you're really interested。

😊，Now we're going to go into memory hiarchy that was kind of a research ending to the memory technology memory organization lecture。

 now we're going to build memory hierarchies。😊，And if you look at memory today。

 it's all about hierarch in the end， most of a system today is memory， you have SRAM caches。

 another level of SRAM cache， another level of SRAM caches。

 another level of SRAM cache and then DRAM。😊，A lot of the and then a lot of storagech so most of the system is memory as we discussed in an earlier lecture so again I'll flash through these picture that I showed you earlier。

 a lot of it is memory hierarchy right just an example a memory hierarchy for example right most of it is really memory。

😡。

![](img/ff856a208c9bdf150731fedfd0e928b4_8.png)

![](img/ff856a208c9bdf150731fedfd0e928b4_9.png)

Older system， actually， as I said last time you had some caches， but they were outside。

 but with Moore's law and very large scale integration， integration technology is becoming very good。

All of these memories became part of the Proor chip。

 So the reason Proor chip is actually is dominated by Mer today is because it's kind of ate all of the other chips around it and you have now a single chip with billions of transistors actually we're getting closer to tris of transistors that depending on how big of a chip you want with a lot of it is memory you can see that this is how it's got integrated level  two cache got integrated So we're going go into the cacheching basically we're going look at how these caches operate and again。

 if you look at a system today， most of it is caches you're seeing a lot of these pictures before。

Okay， so why are we going to talk about it ideally you would like an ideal meid and you've seen this picture before。

 we want zero access time， we want infinite capacity， zero cost infinite bandwidth zero energy。

 clearly we're not going to get all of them， we're not going to get even one of them， right。😡。

Because zero is a very low number， and infinite is a very high number， right？😊，Okay。

 the problem is idea， but you would like to approximate it right whenever you want to build a system that's good。

 it's good to think about the idea so idealism is good。😡，Of course。

 you need to marry idealism as a reality and you need to understand how you can try to achieve or approximate that ideal with real right so the problem is ideal memories requirements oppose each other completely bigger is slower and you know that from today's lecture and from last times faster is more expensive。

😡，Higher bandwidth is are more expensive if you want to actually access many things concurrently。

 we've also seen that today you want to have enabled a lot of pins。😊。

So a bigger takes longer to determine the location faster。

 their multiple faster basically you can make the smaller。

 but then the peripheral circuit becomes bigger， et cetera。

 but memory technology also SM is more expensive than DEM DM is more expensive than SSD SSD is more expensive than that disk disk is more expensive than tape right this is a hierarchy actually and higher bandwidth is more expensive because if you want higher bandwidth。

 you need more banks， more ports， more channels， higher frequency or faster technology in the end。😊。

Okay so let's give some numbers， I don't expect you to read all of these but these are some numbers Crca 2023 or so these are some technologies that are in use at the time。

 but you can see that bigger is slower SM can be small there could be bigger SstrM also you go from smaller nanoseconds like sub nanoseconds and Dm about 150 nanoseds on average let's say but you know that DM is also not the same depending on what row you're accessing whether it's in the robot or not so this is actually the obtaintane which is the phase change meid them you can see that it's about 300 nanoseds it's longer than Dm with one technology and then you got SDs it becomes gigabytes and terabytes and the access latencies becomes microseconds。

It's very long so you don't want to access SSDs in general but that enable access to our storage right you still don' to have SSDs this is PC on page memory based SSs and then if you go to flash memory it's actually more microseconds and then hard disk can be on over milliseconds right。

😊，And then faster is also more expensive， this is the dollars per megabyte comparison。

 you can see that SM is multiple orders of magnitude like 50 x actually less's than 5 yeah about 50 x。

😊，No， that's 500 x right，500 x more expensive than D per megabyte。

 F change memory is cheaper than DM slightly。 Slash memory is much， much cheaper than D。

 as you can see， And hard disk is even cheaper than flash memory。 So this is good to think about。

 I mean you can also figure these out on your own。 But this is one example。

 And this scale over with time。 I'm going show you a 2011 version of this。

 which is much more expensive and not as slower， but much more expensive。😊。

So other memory technologiesn may have their place as well， right。😡，Okay， so this is a table view。

 I should have probably gone through this because this is a much better perspective as you can see。

 big is slower as you go from memory device， latencies increase significantly and faster is more expensive in terms of dollars than Shaperia。

😊，So this is the energy view I'm not going to go through this。

 but energy per access also increases as you go from smaller memories to bigger memories。

 so for example， if you want to access a hard disk it's only the order of 60 millijoules for example。

😡，Whereas if you want to access SM on chip it's pickco juice。

 this is the reason why we want we don't want to move data between different types of memories right because you go through a big interconnects and you waste a lot of energy you've seen in the last lecture how much energy is wasted on accessing memory。

 right？😡，If we had some processing on the memory side， we wouldn't be wasting a lot of energy。Okay。

 this is a 2011 version if you're interested in comparing this one to the 2023 version。😊，Okay。

 so why do we want memory hi Basically we've seen these technologies and we've seen that ideal memory requirements of post teachers are basically we want both fast and large in the end。

 The problem is we cannot achieve both with a single level or single type of memory in the end。😡。

So the idea of MM memory hierarchy is have multiple levels of memory or storage。

 that's called a storage medium， and they get progressively bigger and slower as the levels become farther and farther away from the processor。

😡，And have a mechanism to as much as possible， ensure most of the data that the processor needs is kept in the faster levels。

😡，So you want to access some data， hopefully it's in the faster level。And not in the far away level。

So you get high capacity by having many levels， let's say multiple levels。

But you can access the faster level fast and you try to ensure as much as possible that you're accessing the faster level to get the data and you don't need access to rest。

That's the idea basically so a memory system at a very high level looks like this you have。😡。

This is actually just cache is a main memory， but you can extend with the Ss， et cetera。

 You have some caches that are small and fast and you have main memory that are large and slow。

 You want to access the data from caches and then。Just like what we did with memorymy。

 there's hierarchy inside the caches， you can have。

Smaller and faster caches and then a little bit larger and slower caches and you can have a hierarchy over there and ideally you would like to access the smaller and faster cash。

 smallerest and fastest cash， right？😡，You can also build main memory with smaller components that look like that as well。

 Okay， so basically， it looks like this。 You have some fast and small components memory。😊。

And then you have large but slow components， Okay， let me go back with good locality of reference。

 memory appears as fast as。😡，This small component， but also as large as this large component。

 That's the idea we want to get the best of all world。

 we're going to talk about locality of reference。 We need to have a nice access pattern。

 as we all see。So you move what you use here and you hope that you're going to access what you use again and again and again right so Rob buffer was one example right you moved a lot of data into the robot in DM and you hope that you access the robot again and again and again and again so that you don't need to activate another rope in DM so that was an example of a fast and small cache from the DM perspective we're going to build SM caches that are faster and smaller。

😡，Okay， and then you back up the large data here， hopefully the data that's not going to be used stays here。

 but when you need it。😡，Hopefully it gets back and then you keep accessing it。

That's the locality of preference， basically the data that you access heavily gets into the fast and small components。

 small memory components， cache， and you keep accessing it frequently and hopefully you don't access this large but slow components often。

😊，Okay and then you can actually generalize the idea。

 you can have an next level and an next level and next level right as you go from large components to small components。

 you get faster per byte and as you go from small components to large components you get cheaper per byte so clear there is a benefit to speed as well as capacity because there is no one size fits all because it's a very fundamental tradeoff latency capacity trade off。

😊，Okay so if that's basically the trade off right fundamental trade off is fast memory is small and large memory becomes slow and this is the idea of the memory hierarchy is an example over here you have CPU you registers actually when we introduce registers when we talked about the vnoy model we talked about temporary storage right？

😊，That is part of the memory hierarchy as well。 It is really you move the data that you really need。

 or you allocate the data that you need and the instructions inside this register file。😡。

And these are things that you don't want to access going to memory right that's why we introduced the concept of registerries and the instructions at architecture。

 because you're operating on some temporary values that are that instructions are using and communicating with each other。

 right That's the register file。 That's managed by the compiler or the programmer separately from the rest of the memory。

😡，And then you have some cash and then you have some other caches and then you main memory and then you have hard disk。

 so clear there are trade offs in terms of latency cost。

 size and bandwidth as you go from left to right， latencies increase。😊，Costs of memory decreases。

 size of memory increases and the bandwidth of memory also decreases here your register file can be very high bandwidth because you're operating at the frequency of a CPU a pipeline。

😡，Okay， this is another example from the book chapter that I kind of recommend you to read。

 this hierarchy with three cache levels and the main memory at the bottom level。

 and you can see again the capacity and the latency traded off over here。😊，Okay。

 so hopefully thiss clear。 So why does this work， basically。

 why do people build memory hierarchies because it's based on the locality principle。😡。

It's really a very fundamental principle in terms of both。呃。Let's say how programs operate。

 as well as how humans also operate。😡，So I'm going to give you examples。

 essentially locality means at a let's say， lose level， predictor。

 one recent past is a good predictor of their near future。😊，So a temporal locality， for example。

 if you just did something， it's very likely that you will do the same thing against you if you're paying attention in lecture listening to me。

 it's very likely that you're going to pay attention。😡，If you're not paying attention。

 it's very likely that you're not going to pay attention。And this is actually true。

 I would like the sleep example if I keep sleeping long， I'm going to sleep long。

 if I keep sleeping short， I actually start sleeping shorter。

This' is actually very interesting also observation。😊。

If you're sitting here right now in the next nanosecond， you're going to sit here again。😡。

There's this temporal locality， as you can see， probably in the next 30 seconds or until the bell rings。

 et ceter。 So basically this temporal locality right based on your actions。

 you also exhibit temporal locality， I also exhibit temporal locality obviously right now。

There's another okay， another example since you are here today。

 there's a good chance you will be here again and again regularly and that's also true actually。

 people who come here regularly， come here regularly， again and again。

 people who don't come here don't come here regularly again and again right that's temporal locality for you。

Spial locality is if you did something， it's very likely that you're going to do something similar or related from a space perspective now let me give you an example every time I find some of you in this room you're probably sitting close to the same people。

😊，and or enclosed by seats and that actually holds in general also there's a spatial relationship you have your friends and you sit together right and sometimes you happen to sit together in the same seats all the time or most of the time right so there's some spatial locality also right in space you're correlated with each other also。

😊，Okay， that's one example clearly， I'll give you some more examples， but basically similar to this。

 memory has locality as well in a typical program。A typical program essentially has a lot of locality and memory references I'm going to give you examples of this typicaly programs are usually composed of loops as we discussed right T locality means the program tends to reference the same memory location many times and all within the same window of time。

😡，You have some variable that you need to add to some other variables。

 so we keep accessing that variable many times because you need to add it to many other variables。

 right？😡，Hopefully that makes sense right so that particular variable is accessed a lot right you have a piece of the graph and you're doing some analysis on the graph and you're going through this graph many。

 many times to do this analysis right？😡，So that's another example of temporal locality where you're actually operating on a collection of data elements。

 and if you keep them in your cache， you're going to access them tasks。😊。

Sppatial means a program tends to reference nearby memory locations in space， address space。

 on this case， within a window of time。😊，And again， there's a good reason for this array references。

 for example， in vector processing， if your array is allocated consecutively and if you're going through your array sequentially。

 you're basically accessing element one， element zero， element one， element two， element three。

 element4， element five element6， and if they're spatially。😊。

Let's say adjacent to each other consecutive in memory with each other they basically have a lot of spatial locality in that reference that you make in those references that you make to the array essentially arrays and vectors if you remember you often have a stride or stream of one for example。

 even a stride or stream of two is okay because spatially you're closing up whereas if you're stride was let's say 10 million then you're spatially far away but we don't want 10 million strides because that's not good for locality in general and many programs don't have huge strides if you remember the vector array processing GPU vectors。

 you basically have a lot of spatial locality if you add two vectors together for example or multipied two matrices again there's a lot of spatial locality。

😡，Another example is instruction memory references because we have sequential programs in the Wal Neman model。

 you basically go through a PC， PC plus forward next PC and the next PC and next PC you keep ining the PC right and the program counter as location in the address space。

 you're basically going through consecutive locations and in the address space。😊。

So in terms of space， you're traversing the address space right so these are two very good reasons why there's a lot of good spatial locality in programs so combined with these cache has exploit both temporal and spatial locality in the end。

😊，So the basic idea， let's talk about exploiting temporal locality first。Because it's a bit easier。

 you store recently access data and automatically managed fast memory。

 automatically meaning programmer doesn't deal with it， compiler doesn't deal with it。

 hardware manages it。😡，This is called the cache， that's a hardware cache。

 there could be actually software caches also which we're not going to talk about a lot。

 but the caching concept is actually pretty general。😡，This is the idea basically。

 if the CPU or if the processor requested at eight elements。😡，And with an instruction。

 load instruction， it puts it in a fast memory， anticipating that you're going to access it again。

 That's the anticipation， basically。Same memory location will be accessed against you。

So a basically temporal locality principle says recently access data will be accessed again in the near future and this is very strong in general if you're of course accessing if you're not reusing any data than you're not going to get the temporal locale but that's not true in general so one of the earliest papers in fashioning was written by Morris wills if you remember Morrisris will you also introduced the microcoded microarchits a long time ago multicycled microarchures and in this paper I'm going to read this because this is fun because we're going to look at core memory later on as well the user discussed of a fast core memory of say 32000 words which is very small today as a slave to a slower core memory of say one million words in such a way that in practical cases the effective access time is nearer that of the fast memory than that of the slow memory it's beautiful basically you have two types of memory is one is small fast the other is slow large and then hopefully you're going to access the fast one most often。

😊，Okay， so that was temporal locality if there are no questions。

 we're going to move to a spatial locality。😊，So spatial locality。

You basically do the same thing in space， you don't look at a single variable。

 but you look at a collection of addresses。😡，Essentially the data in that collection of addresses that are adjacent to each other store those in automatically managed fast memory。

 so if you're accessing， let's say one data you're using a load instruction。😡。

You look at the other addresses around it， and you bring all of that data into the cache。

With the anticipation that because you're accessing address X。

 you're going to access the surrounding addresses as well。😡，That makes sense so fullyate。

The processor， it access address x， but when it brings data。

 it doesn't just bring the let's say word that is operating on that address x but let's say 16 words around it and brings it into cache and the hope is that you're going to access a lot of those words also that's the idea basically。

😡，Simple to be able to do this， there are multiple ways of doing this， but one way of doing this。

 which is really the common way that's implemented in all microprocessors today is you logically divide memory into equal size blocks。

😡，It's going to call call a cache block and you fetch to cache the access block in its entire this block is can be 64 bytes remember the 64 byte in Dm that's why I showed 64 bytes it a 64 byte cash block the processor load instruction may need only one byte。

😡，Doesn't matter。 load instruction goes to memory the memory controller brings。

The block that contains the single by that you really need。

 but it also gives you 63 other bytes around it。😡，And that goes into the cache。

 and if the processor happens to access another load that references one of those 63 bytes。😡，Bgo。

Meaning you already fetched that into cash， right？It already came from memory so you don't need to access memory at that point that's the idea basically it's a beautiful idea as you can see simple idea and the anticipation is that nearby memory locations will be accessed soon when you're accessing memory location X。

😊，Okay so this is spatial locality principle and we've already discussed why this makes sense sequential instruction access。

 arraycurversals， matrix curversals， etc ceter， this is what was implemented early on in 1960s in IM this is one of the seminal papers also for example IM 36085 had 64 purebyte cache which is relatively small for today with 64 byte blocks today we have actually 64 byte blocks also which is interesting。

😊，Okay， I like this bookshelf analogy for caching also。

 so you may have books in your hand that you're using when you're studying that's。😊。

You're going to reuse that book again， right， This's a temporal locality。

 And then you may have some books in the desk， Usually books that may be needed soon can be in your desk。

Some of them are in the bookshelf， you don't need them as much。😊，Some of them are at boxes at home。

 you really don't need them much and some of them are boxes in storage and those are less needed。

 so basically recently used books tend to stay on desk。

Maybe your computer architect your books if you're reading them or books for the classes you're currently taking right until the desk gets full of course。

 right well your hand you can keep on a couple of books probably one book is a good start。😊。

Bookle parallelism is also good， but your hand is kind of like the register file you're operating on this book at this point right and then your desk is like the caches okay you got this book。

 you switched to another class and then you read those books and then because your desk has limited capacity and you don't want to fill it with books only because you may want to have some drinks also right as a result you basically move some of the books to the bookshelf right？

😊，So this is the temporal locality principle right。

 and the size is going to matter also in this case。

 because at some point this cache is going to get full and we're going to ask the question how what are we going to replace from this thing？

Okay， the spatial locality principle is interesting also， for example。

 you can organize your books such that there's some logical principle in the organization。

 all books related to computer architecture may be spatially in the same location in your bookshelf right so whenever you go to your bookshelf。

😊，Computer architecture it here， and sequentially you can figure out which book you want。😡。

That's the spatial locality， that's how you can improve spatial locality things that you're going to access close by。

 you put them together， this is called data mapping， you're mapping your data to close by locations。

 whereas if you map your data randomly， computeruter Act book one goes to this side of the bookshelf。

 computeruter Act book two goes to this side of the bookshelf。

 computeruter Act book three goes to that size of the bookshelf good luck accessing that data easily right。

😡，This is latetency you have to go through there， there， there。

 assuming you're going to access those things。 let's say around the same time。

 right So basically if you organized and categorize your books well in the shelf。

 you can actually exploit spatial locality much better。😊，Okay， hopefully this's interesting。

 you can make a lot of other analogies， but we don't have time to make a lot of other analogies。

Any questions， otherwise I'm going to go into a little bit more detail。

 We're going to build this cache soon。 So let's talk about caching in the pipeline design。呃。Okay。

 I don't see any hints， so it turns out the cash needs to be tightly integrated into the pipeline。😡。

So ideally， for example， remember， when we design pipelining we said there's instruction memory。

 there's data memory， and we assume one cycle axis。That was the assumption。

Now we're going to make the assumption a little bit more realistic。😡，Basically。

 if you want to supply that。😊，There needs to be a cache that gives you data in one cycle。Fine。

 you can build it。 No problem。The problem is going to be small， right？

So if you have a high frequency pipeline， you cannot make the cache large。

 but you ideally want to large cache in a pipeline design。😡。

It just doesn't work if you want to access the cash with one cycle， only in one cycle。😡。

You need to make that cash small。😡，This is another reason why we have a hiarch basically。

 instead of having just one level one cache， we have a level two cache。😡。

Level  one cache can be one cycle to satisfy the needs of the pipeline。

But level 2 cache can be longer access latency， except the person needs to stall to access the level 2 cache。

 or you need to do out of order the execution to tolerate the latencies that happen in the level 2 cache。

Okay， so the T takeaway is level one cache is really part of the processor if you think about it。

 meaning the processor， it's really dictated， the design choices that you make in the processor dictate how large。

😊，And what structure how large the level one cache can be and what structure it can have so ideally one cycle。

 but we're going to see caches that are three cycles， et cetera。😡，Okay。

 there's another note which is manual who manages the cache， programmer or hardware。😡，呃。In general。

 when we talk about cash， it's a hardware cache today， it's kind of the assumption in general。

 but that's how I kind of defined it also automatically manage it based on the hardware software can also manage it。

 but manual means programmer manage data moment across double of the cache Iarch this is still like exists this in GPUs I'm going to show you very quickly。

 but usually it's too painful for programmers especially on substantial programs。😊。

Because now the programming gets exposed to this hierarchy and they have to decide， oh。

 where do I put the data in this hierarch？😡，And it used to be that way。

 especially in the embedded processor， but GPUs， but GPUs also started introducing caches。

 a lot of ML accelerators， machine learning accerators also still do scratchpad type of memories。

 it' is also called the scratchtpad memory manual management of the caches scratchtpad memory because it's visible to the programmer now。

😡，So it has its own address space that needs to be dealt with automatic means hardware manage the data moment across levels transparently to the programmer programmer doesn't need to do anything。

😡，Of course， this is the huge advantage that programme is life is easier， which is important。😊。

As we have discussed in the past， right？And the average programmer doesn need to know about tas。😡。

So for example， you don't need to know how big the cache is and how it works to write a correct program。

But the issue is a little bit different if you want a fast program。If you want a really fast program。

 you still need to know what your cash hierarchy looks like because you may design your program such that locality is terrible right。

 if you're not careful if you don't know the sizes of the caches for example and how they work。

 you may design a program with terrible locality in general。😡。

So if you want to optimize your program， this is still very important and given that a lot of the programs today are bound by memory accessed latency。

😡，It's really important to optimize your programs。 We're going to see an example of this next lecture。

 But just to give you an example， GP though both ways。 A lot of modern。General purpose process， CPUs。

 they have caches that are not visible to the programmers。😡，呃。Whereas GPUs。

 they started with scratchpas， meaning programmer managers the caches。 But over time， they said。

 okay， this is too difficult as they became more and more general purpose。They said basically okay。

 programmer can also use these desk caches， meaning programmer doesn't want to deal with the management or hardware management。

 so they have kind of both ways right as you can see over here。

 this in this particular MVDM peer GPU， 192 kilobytes per streaming multiproor can be used as a1 cache and or scratch pad or some sort of combination base。

😡，And this is increasing the size of this is increasing。 And again。

 you can see another example from Hopper here。Okay。So if you look at ML xccelerators。

 we've seen examples before here there are no caches currently。😊。

If you look at the tile that we examine in the past as a S processor if you remember it has a S floating multiply and accumulate units and basically in each tile you have a 42 kilobytes scratchpa cache totally totaling 18 kilobytes in the full chip in this particular example so basically here the programmer does everything or the compiler so this is why this is a bit more difficult to program。

😊，Okay， and then this is increasing over time。Let me just give you an example of the old things before we go into caches because in the old times there was caches also the memory technology was a bit different so you can see this is a technology that you don't want to carry in your pocket。

😊，This is the main memory technology in the 1950s， 1960s。 There's a lot of magnetic things。

 then it became this is drum memory because of its operational principles。

 And then it became core memory。 And if you look over here， even the structure very similar， right？

 Yes， there is magnets， there the magnets need to move and depending on depending on the orientation of the magnets。

 you store one or0。 but you still have the word line and midline two dimensional array structure。😊。

It's just not the electronic in this particular case。And I like reading this over here very quickly。

 so using smaller cores than wires， the memory density of the core slowly increased and by the late 1960s。

 the density of about 32 kilobits per cubic foot， about 0。9 kilos per liter was typical。

 however reaching this density required extremely careful manufacturer which is still a problem actually。

 which was almost always carried out by hand in spite of repeated major efforts to automate the process。

 a lot of things that happen by hand to make the DM work also today。

 the cost declined over this period from about 1 per bit to about 1 cent per bit。😊。

That's extremely expensive by today's standards。 if you remember the numbers。

We're talking about main memory， DM is like 0。03 per kilobits。

 maybe even lower today actually the introduction of the first semiconductor memory chips in the late 1960s which initially created static random access memory SstrM we have seen began toerode the market for core memory。

 this thing over here。😊，And the first successful dynamic random access memory DM。

 the Intel 1103 followed in 1970， it's available in quantity at 1 cent per bit。😊。

Marked the beginning of the end for core memory so that's how D actually replaced these huge things because it was easier to manufacture and also it was cheaper as you can see and today it's much cheaper and this is all of that improvements in the memory technology the cost for a bit enabled where we are today basically I don't think AI for example would be possible without those improvements there's of course a lot of other things that went into AI but hardware both GPs and memory are a big part in fact memory still a huge part of it。

😊，Okay so automatic management， let's talk about this automatic management。

 I've already mentioned this what Wil said over here。

 but let's see it a little bit more by this slave memory， which is called cache memory today。

 I mean one which can automatically accumulates itself to itself which automatically accumulates to itself words that come from a slower main memory and keeps them available for subsequent use without it being necessary for the penalty of main memory access to being cur again so you've seen this before there are actually earlier cache papers that I'm not going to talk about but caching is done much earlier and this is an example that we may return to we're going look at how the cache is organized but this is a paper from 1960 and you can see there is a tax store and there's a data store I'll introduce this concept a little bit more later and we're going actually build the cache but data store is where the data is stored you bring the data from main memory you stored in the data store T store is an index into the cache that tells you which memory address that data belongs so you need both of these。

😊，You need the tag， which is part of the address。😡。

Which basically identifies the address that this data belongs to and need the data。

So you can also think of tag as a metadata that specifies where the data comes from from main memory。

 right？😡，Okay。So this is the modern memory hiarchy again， I've shown you a lot of examples of this。

 I'm not going to go through this in detail， but I will mention that later in the last lecture probably。

😡。

![](img/ff856a208c9bdf150731fedfd0e928b4_11.png)