# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p14 Lecture 13_ Flash Memory and Solid-State Drives (Spring 2025).zh_en -BV1Xc19BnET7_p14-

嗯。

![](img/8bfbb4e3708c5d2dcc3dd769d48d6f6a_1.png)

ま。嗯。C你。Yes。Yeah。はいましたしどうぞ。全。不去。な。はい。研究。this is here advice。I sure better and it。あ。这个。嗯。12。啊你拿啲你个。

Is it that？Yeah。你仲要。有我随接。Okay。是。是。嗯。Okay。今天。是。Yeah。H。喺。はよそで。上次嘢诶。不是。Okay。有什么示。🎼。Okay。

 let's get us started good afternoon everyone， welcome to lecture 1s of fundamentals of computer architecture。

Today we're going to discuss about flash memory and solid the state drives， which is another really。

 really interesting exciting topic in computer architecture。

I had actually a kind of difficult time to understand， to decide what to cover。I had like around。

 I don't know， 700 slides。But definitely， I'm not going to cover the whole。

So let's see until which part we're going to get， but we're going to learn a lot about SSD architecture。

 modern SSD architecture， as well as flash memory， how flash memory works。

And I'm going to also show you some of our past analysis on flash memory characterization。

 like flash memory reliability and security。Okay， but before we start talking about flash memory。

 I would like to。Just as a aside， I want to talk about emerging memory technologies a bit。

 why is that because flash memory actually was a kind of doubtful emerging memory technologies at least for two decades so people were not so optimistic about flash memory and there were a lot of people that they were working on flash memory to make it possible and because of all the effort that people made now we can see the adoption of flash memory in our computer system today and we cannot really imagine today's application without having flash memory like the fact that we have smartphone in our pocket。

Is one of the very good examples that's why flash memory actually made that impact。

So we discussed a lot last week about memory robustness and we basically talked about the myth of charge memory and flash memory is also also considered and categorized as charge memory because it also you're going to see that it has a floating gate chart。

Which in the end， you're going to store some charge in the floatingoting gate。But essentially。

 the problem of charged memory is that reliable sensing becomes difficult as charger storage unit size reduces。

And essentially we can have two different solutions。

 one is that we can come up with new memory architectures to overcome memory shortcomings with using for example。

 memory centric system design， novel memory architectures， interfaces function。

 also better waste management。As we already discussed some of these techniques actually through this course。

 there are a lot of key issues to tackle， for example， how to enable reliability at low cost。

 how to reduce energy， reduce latency and so on and so forth。

And we have also worked a lot on this topic， here are some examples。

 some the papers that we have published， but on the other hand， there is also another solution。

That basically we can use emerging memory technologies。

 so there are other memory emerging resist memory technologies that they seem more scalable than D and they are also novel。

So one good example of that is actually face change memory。

That essentially data is stored by changing the phase of material and data read by detecting the materials resistance i'm not going into detail of that unfortunately for the interest of time。

 but essentially。in ITRS 2009， they expected to escape to9 nanometer and it's also we have prototype of this memory at 20 nanometer in IBM in 2008 and essentially is expected to be denser than Dran because it can store multiple beats per cell that's also the criteria that flash memory has that you can store multiple beats per cell。

 but be the different essentially technique。However。

 emerging technologies have many shortcomings and that's why actually we and also many other people。

 they have worked a lot on this topic to make them possible。This is one， for example。

 industrial solution for 3DX point as an emerging memory technologies。

 which is 3DX point is actually very similar also to PCM。

So these kind of des you can actually you could buy it， I'm not sure if they are still available。

 but in the past you could buy it and put them on your machine as a normal the but the fact that these des are novel electronic so you can use them for persistent memory for example。

Professor Motlu and with his also coators， they work on this topic a lot， this is one of the very。

 very first papers that published in 2009 architecting face change memory as a scalable D alternative essentially。

 so basically people wanted to see where we can put or place this kind of emerging memory technologies in this grand scheme of teams。

And this is also another writing for that work， which you can also check if you're interested。

 but essentially there are。Different kind of memories that people came of。

 this is also not complete comprehensively there are many。

 many also other emerging memory technologies but PCM is essentially you inject current to change material phase and then resistance determined by the phase of that material SCTMogram is another memory that you inject current to change magnet polarity and resistance determined by the polar of that magnet and also other memory like memory store orM re that you inject current to change atomic structure and then resistance determined by atomomic distance。

If you want to learn more， I would suggest that you check this very recent lecture that we had in computer architecture last semester that we basically take went into more detail of such architectures。

But now I like to basically get to modern storage solid estate systems， solidity drive。

 which essentially they use flash memory as one of the main basically memory units。And as I said。

 flash memory was actually one of the emerging memory technologies in 1990s， 1980s。

 but starting from 2000 or so， they actually started to to use make flash memory more available and make it more possible such that we can use them for a computer architecture。

So in this modern solidity drive in safari we are actually working a lot on this topic。

 we have basically this is one of the very exciting work that we had in fast 2018 that we develop a simulator for such a for modern solidity drive now actually we are working on extending this simulator so we are also kind of recruiting you know exciting excited people to work on it and make it more useful for today's systems。

😊，But essentially we have worked a lot on improving a storage system as well as also using a storage to do computation。

 for example， we show that using aS you can implement some field training technique。

 you can do essentially bulk B operations， also you can basically do metagenomics applications。

And recently， Mayan also published stpher match that he accelerated homomorphic encryption in using flash processing。

So essentially this topic is actually very， very active in our group so if you're interested in this lecture you can actually just approach us similar to other topics that we have discussed during this semester。

😊，But I'm to start with the overview of an SSD organization that a modern SSD is a complicated system that consists of multiple core。

 hardware controllers， D and nonf memory packages， so essentially your SSD is quite complicated system here you can see the nonflash packages four of them they are also for on the other side of these board。

And then you have this Samsung basic， which is your storage controller and also some G that you have here is LPDR data。

So inside the SSD controller we we're gonna to see more essentially you have several cores。

 you have some hardware flash controllers and these flash controllers are doing essentially a lot of controlling logic that we need to do in order to communicate to flash memory and as you're gonna to actually see a lot compared to memory controllers for D that we actually argued a lot during this course that we need to make them more intelligent and unfortunately current memory controllers are not that intelligent and they are not doing much basically except they are doing that require a signaling to know to connect to the D but flash memory controllers they are quite intelligent so they are doing they are doing actually many。

 many stuff and you're gonna to see today how we can make that flash memory which is quite error pro possible and you can just reliably access your disk or your SSC and get your data so you're going to see how much they are doing in order。

to make it possible， which I think is going to be is a very good example that how much we can get。

 how much performance we， how much reliability and performance we can get if we make our controllers more intelligent。

 as we did also for flash memory。Okay。So。Essentially in our storage controller we have host interface layer and another important layer flash translation layer which we call it FDA and also there are flash controllers so I will start going over these components at a very high level now using some example here we also have DM and in this D essentially we have the queue for host request right buffer logical to physical mapping this is something quite key that we're going to see later and also metadata that we essentially the controller and the scheduler use these metadata in order to make more intelligent decision。

So let's go over these components very quickly by considering that we want to handle the right operation。

 so your system sends a right request to the SSD。So the communication with the host operating system actually happens through the certain interface can be SaA or for example NVME in the past we had this SaA which I think you know like you're connecting your artist right with SSD also in the beginning the interface was actually mostly SaA but then people realize that SaA does not provide enough bandwidthits you know that SSD can provide much much more bandwidthit so then they develop this NVME basically Portugal that you can access your SSD with higher throughput but now we have still SaA and NVE when we are using SSD。

So and also a host oil request which coming from the operating system or can be actually also coming exactly through the process。

 so with NVM actually we don't have time to go into detail of that。

 but one of the important thing about NVM is that each process or each application has a certain cue in the SSD which without OS integration actually that process can access the SSD and write to and read from that queue so this is one of the important how why we are improving the throughput by removing the OS integration in between。

So a host audio your request includes several attributes， for example request direction。

 whether or not it read or right offset， which is a start sector address。

 this sector term is actually coming from hard disk drive。

 but it still we are using it for SST as well for compatibility reason。And also the size of request。

 which is the number of sectors that we are reading。And as well as basically。

 and also this liquid is usually typically aligned by 4 kilobyte。

 and that's the page size that we usually have in our oil system。😊，So。So after that。

 after passing the SI which is host interfaceface data right。

 UC needs to get to the FTL and for FTL basically we first have this data cache management and you can essentially buffer the data that you want to write into this right buffer。

😊，So that gives you basically is essential to reduce the right latency you're gonna to see that rights are actually very。

 very slow in N flashlash memory so we have this right buffer such that we write to that buffer and then quickly send acknowledgement to the host such that the host can continue and there are some ways which I'm going to say very soon that in order to make sure that that right is not going be because when you write to the SSD you're considering that SSD is normal memory right so you cannot write to the D and say that okay I'm good right so essentially modern SSDs they have some capacitors and that those capacitors provide enough charge when we have these power cuts those capacitors provide enough charge for d staaging process there might be some dirty let's say data in that data buffer and when you have this power cut essentially those capacitors provide charge for that SSD essentially to write back the dirty data。

In that Dran to the flash memory， the power cut electricity power。No， no， no。

 your data is saved in the D。But they are not saving their flash memory。So from the sorry exactly。

 so flash memory is no volatile， but Dram is volatile。

 so they make that Dm actually kind of non vision by adding some capacitors。喂，他。

So the thing is that that's actually safe， but the problem is that you cannot make that Iran large much。

 you know， because if you don't want to do that， you need to add a lot of capacitors。

So D is actually in a bullet no， those capacitors provide charge to do the staging to the flash。

So you need some electricity power to write back from Don to flash exactly。So yeah。

 essentially that's very important to reduce right latency and also it enables flexible I scheduling。

It's because basically right latency and read latency are so hetero re by adding these right buffer you can have more different kind of latency and more balanced latency and then you can have more flexible I scheduling。

 unfortunately we don't have time to go into scheduling techniques for SSD。😊。

And helpful for improving lifetime， essentially you're going to see that flash memory we have these program array cycles whenever you program to flash memory you are causing some you are causing wear。

 you know you're aging your flash memory essentially and each flash memory cannot tolerate more than certain number of program array cycles。

😊，So as much as you can write to this right buffer and filter your rights without going to the flash memory。

 that's a good thing， right？😊，However， that needs actually some locality so you write to write buffer and you are hoping that the next right which going to be to the same physical location which is like not physical to the same logical address essentially which is the update so you have a you write to the address and you send another update to that address。

 so if that's the case okay this diagram can capture your new right or new update which is very good you don't need to write to the flash memory but that's very unlikely because usually on that level you don't have that much of locality。

😊，Because your locality hopefully has been captured。😊，Through the caches and also through the Dm。

 so when you get to the SSD to the storage， locality is not that much。So as I said。

 the size is limited to tens of megabytes because it needs to ensure data integrity even under sudden powerof and most data capacity used for logical to physical mapping。

 which you're going to see next。So this is a core functionality for out of place right you're going to see that in SSD in flash memory we don't do in place rights so whenever you want to update a page you basically write it somewhere else so that's why we call it out of place right then you actually need a table to say which logical address is mapped to which physical location and basically this is logical to physical mapping that we have。

And this needs to maintain this L2P mapping and thats tell you that the logical page address。

 LPA map to which physical page address， which we call LPPA。

And mapping gra is usually4 kilobyte so essentially you need to store four bytes for each 4 kilobyte of page and that brings us to this 0。

1% of SSD capacity so usually people realize that this D mostly is actually the size is around 0。

1% of SSD capacity so if your SSD capacity is oneyte you have kind of1 gigabyte of D essentially。

And most of it is actually used only for a basically logical to physical mapping store。

So there are a lot of things that we need to do in order to make sure that this flash memory works like garbage collection veryleing refresh and so on and so forth and all this actually they need this metadata some sort of metadata for example these number of program and array cycles so how many like how many program array cycles we have for each block in the flash memory so these stuff needs to be stored in this Dm and then the process the control process in the storage controller can use this information in order to make decision so garbage collection which is going to see actually today is to reclaimse three pages and also because when you write out of place。

At some point you are running out of the number of three pages right so then there should be a process which we call it garbage collection that try to reclaimse free pages by erasing some of the old and invalid pages。

So we're going to learn about garbage collection later。

 I don't want to go into a lot of detail now and where leveling is another very important function that essentially we want to make sure that our blocks in flash memories also pages they are going to be aged in the balance way for example。

 if you're flash memory can tolerate 10 to the each flash set can tolerate 10 to the。

Tend to the power four， for example， number of program rates。

 so one way is to just write to one cell， you know， and just that cell is going to have out soon。

Even though there are many or many other flash pages and blogs that they are useful。

 so that's not a very intelligent solution because at some point you cannot use。

Your stories because they are you know scattered on basically faulty pages and blocks in the flash memory so there is a technique which we call it very leveling that try to make sure that we don't have hot blocks and code blocks so hopefully we are going to write and do program array evenly across all the blocks so that's the job we're very leveling。

And data refresh， which is even though flash memory are considered to be novel at type。

 but you're going see later that we actually need to do refresh at least once a week， for example。

 or once a month， you know， if you for example store some data in your flash your coolest like flash memory and you don't touch it for let's say five years and after your graduation you just connect that flash memory I mean good luck you know getting your data you might not actually get your data。

😊，嗯。At least。You able might be able to recover if you add some techniques， some ECC stuff。

 but that's not easy。Okay， so after going through FTL， then we need to go into the flash controller。

 remember that we were writing， so we were writing a data to the flash memory。

So flash controller actually does signaling which is very important thing for N flashlash packages。

 so you need to do some signaling which is to such that you can communicate with this N flashlash package and with that you need to have this kind of analog essentially support to send some pulses importantly for N flash packages such that they can work but in addition to that flash controller for example does ECC and randomization so randomization or randomizer is basically does a scrambling data to write。

😊，So people realize after some characterization that there are some data patterns that they can exacerbate the。

Errors， the number of errors or also the probability of errors that we are getting from flash memory so those are worst case patterns so people try to use some key and using that key they you scramble data just to make sure that we are we don't hopefully we don't have those you know worst case scenarios so that's the process of randomize it so you basically your data that you want to write you randomize it with the key and then you write to the flash memory and when you're reading you need to use that key to deranomize essentially and get the actual data to the to the to the host。

And also we need to do this error correcting code ECC in order to detect and correct errors。

 for example， we can store 72 bits for one kilobyte of ECC essentially。For 1 kilobys of data。

 you store 72 bits for your ECC。Okay， and then after that， you can issue right operation。

 which you call it flash flash comments， you send the right command to the nu flashlash package。

 and then you write your data。So when you want to read it。

 when you send a read request after passing through HI。

Essentially your first SSC checks that if it can service your read request through the right buffer because it can be also considered a cache right so basically first check the right buffer if so the system returns the corresponding request immediately with the data。

But。But another important thing is that a host read liquid can be involved with several pages。

 so you might need want to read many several pages like 10 pages。

And then you might be able to service two of your pages through the right buffer but the rest might not be there so for the rest you need to access the flash memory physically。

 so that's why actually the system this FTL actually waits or HIL actually waits until you have all the reads all the pages that you wanted to read and then send the respond to the host system。

😊，So that's a very important thing because you might be able to service the first two reads。

 the first two pages very， very quickly。Through this right buffer。

But other pages you need to wait for them anyway， so that's not going to also that that helps you to understand how we can do some scheduling technique because。

If if I have to wait， you know， if I have to wait， for example， anyway。

 so then maybe storing those kind of pages， those pages in the right buffer is not needed that much。

 you know， that's not going to be helpful for you。Okay， anyway。So。

After if we don't find our data through this data cache management。

 we need to check this logical physical mapping because the host has the logical address but we don't know that SSD stores the data there remember that we have this out of place right so there is no map basically you need to check the table to see where exactly your data or page is the stored so you check that and then you get the physical location so once you know that which N flashlash package in which for example block and which page store your data you basically access you send the read command to that Nant flashlash package and then you get your data so once you get flash controller basically performs ECC decoding。

And then de randomomize the raw data and then send it to the the host the thing is that especially when your SSD age。

😊，ACC decod usually fail。And then you're going need to rewr reading of the page by doing some adjustment。

So and that might be one of the very one of the important reason that once your SSD is ad and you're using。

 for example your system for a long time， your disk access is going to be slower。

 so in the beginning you're going to have very good performance probably out of your SSD but after five years。

 six years，10 years your SSD going to be quite as slow because every lead you need to re a lot in order to make sure that your ECCC can handle the number of errors essentially。

But you're going to see what I mean exactly by adjusting a reference voltage。Okay。

 so what is flash cell， flash cell basically is the transistor。😊，嗯。

That you know that each transistor we have this gate source range and then when your gate source voltage is higher than a voltage which call it threshold。

 then the transistor will act as a switch。Not ideally， but as a kind of switch。

 so it's going to be fun。😊，And when your gate source voltage is less than threshold voltage。

 your transistor is kind of open switch。So but flesh cell。

 the difference is that we have floating gate。And for 2D flash technology， for 3D。

 they call it charge strap is actually different， but overall they are the same at the high level。

So here we are showing the2D floating gate so the floating gate important characteristic is that it can hold electrons in a nonvolat manner。

 so when you want to program a fly cell you basically apply a high programming voltage to the gate so now for example 20 volt and this 20 volt essentially absorb some electrons from the substrate and then trap them in the floating gate。

So these electrons are tallering through from the substrate through this gate and then here because of this floating gate。

 because of a structure， they are kind of trapped here。So now you have these electrons here。

 essentially your gate has a negative charge。😊，So when you want to turn on your transistor。

 you need to apply a higher gate source voltage。So because of these electrons that they are trapped here。

 the threshold voltage of your transistor is going to be higher。

So that's a key difference here that makes it basically flash memory to work so if you don't program。

In the nominal bay so this is your threshold voltage when you program your flash memory by adding this applying this high voltage you're going to have a higher threshold voltage so now you can apply a reference voltage as a gate source if this reference voltage basically turned on your transistor then you're going to realize that okay I haven't programmed my flex cell。

So you can encode it as a array， usually people encode it as one， for example。

And if this reference voltage does not turn on my transistor， then I already programmed it。

So that's a reference voltage and then you can encode this state as zero and that's a way that you can work with your flash memory。

Any question？Okay。So the thing is that when you program and then when you want to basically write so when you program you have zero for example。

 and then you want to write one， there is no way to write one。

 you need to erase it and that's the process of erasing that you apply the negative programming voltage like minus 20 volt in order to basically tunnel back these electrons to the substrate and then get to the the nominalal thresholdial voltage that you have but the problem is that this process is not ideal。

So whenever you program and you also erase， you might basically leave basically you don't get。

You don't push back all the electrons that you had here。

 you might actually send more electrons or leave some of them here。

So and that makes some errors and after doing a lot of these program race cycles。

 you essentially accumulate your errors and that's why flash memory cannot tolerate。

After some certain number of program resets。Makes sense。Okay， great。

So one of the cool thing about flash cell characteristics is that we can actually have multileted so a flaget can store multiple bits。

 why is that because so you can consider okay I have only two levels when I program I program one the end when I erase I basically erase fully and then you can you know encode it as zero and one but you can actually also encode it as two bit multileve cell so when you are programming you have some middleless step as well。

😊，So you can actually in your the distribution of threshold voltage you can be more accurate and say that okay if I complete array。

 I will encode it to 11 if I program a bit I'm going to encode it a0 one if I program a bit more I will program it encode it a00 and so on so so that's for example2 bit multileve set。

Today， actually we have flash memory that they are QLC。😊。

that they are restoring four bits at each cell and that comes at the price of reliability and also performance。

 but when you care a lot about capacity， that's the way you go essentially。

So retention loss is also another important characteristic of lifestyle cell so S leaks electrons over time。

 so that's what I said even though flash memories are considered as nonvolat memory。

 but after some time they're basically S leaks electrons over time。So this is for example。

 the initial step state of your cell after one year you're going to get to you know this kind of charge is it still okay you don't have error but maybe after another year you might get to this and then now you have retention error hopefully your ECCC should be able to fix that。

But when you have a lot of retention errors， your A capability cannot fix everything for you。

And also I said that we have limited lifetime as cell wears out after a number of PE cycling。

And that essentially P cycling affect your retention loss so after one year。

 if you have only 1 kP cycles， you still have okay you know charge。

 but after one year if you have like a sale with 10 kP cycles。

You essentially might have retention even after one age。

So these are very important characteristics of flash memory that you should consider question。Yeah。

Yes， are there actually flash memories that inform about this？

Like now I have too many pe cycles or something like this that I need to replace it no。

 I don't think that's visible to to the。To the user， yes， yeah。It's actually at the FT。

 people are working on open channel SSD。That you can implement FTL at a host actually， and with that。

 yes， you should be able to to be aware of everything internally。

But from the researchers that I'm going to show actually later。

 we actually beat the infrastructure similar to Dam Bennder， for example， you know。

 and we were studying a lot of these flash memory characteristics using FPGA infrastructure。But yeah。

 you need such kind of infrastructure to know about what's happening internally。And in general。

 flash memory vendors， they are not open， you know， to share。As usual， I guess。Okay。

 so another string is。So each of these is a N set。We have another terminology which we call it NandA string。

 which you can see is very similar to the Nand gate。

 you know that you carry several Nand cells together， so multiple like for example。

 128 flexs are serially connected and so that's a NaandA string for us。And whenever you want to read。

 for example， right， you might have a target set。😊，And other cell they are not your target。

 so the way that they handle it they will apply a high voltage which is vPAS and that vPA is actually high enough to make sure that this transistor or this flesh cell is going to be on。

Whether or not you have programme it or you're not。

 essentially you want to make sure that only this cell target cell would basically specify if I'm going to be connected to the ground or not。

So this should be the main you know， the cell that you're going to decide on it。

 other cells should be all act as a switch， which you have the connection to the to the ground。

If this cell is on， then。you have your full connection and you will encode it as as one if this cell doesn't。

 so everything is on， but this one is going to be open switch。

So your connection to the ground is not basically happening， and then you can encode it as zero。

 for example。I'm feeling that people didn't get it。Yeah， I get it。 I just don't see what the benefit。

O。I guess we're going to see some。So。So when you want to read， essentially。

 so you prechar this speedland。So that's the process for ready。

 you precharge speed line I'm going to show actually later also。

 but you but very quickly you precharge speed line to a。To high voltage。

And then you have a sense in p circuittry that you're going to see that if this chart is discharging or not。

 essentially。So depending on this fly cell if it is on when you apply a reference voltage is' going to be might be on might be off right depending on that you might see that my current is discharging or not right so you want you want only this fly cell your reference basically your target cell decide if your current flows or not right so that's why other cell。

They all should act as a resist。So how is it possible to people applyPA， which is high voltage。

 high enough to make sure that this going to be on， whether or not we have programming or not？Okay。

Another important termin is pages and B， so a large number of cells operate concurrently。

So this is very similar also to our 2D array that we have also in data。

 essentially this row we call it， we have a boardline。And word lines。

Several holes under here 128 board lines。That they work in parallel through all these bit liness。

 we call it a block， essentially。So this is my block。

And there might be other Naandez string that they are also shaving the same bit time。

 but those are other blockss， essentially。And yeah， and that's my page。

 so when you talk about Nflash page， you are essentially talking about your wordline。

 if if you have a SC non flashlash memory which you store one beer cell。

 then your page you store one page per wordline。But when you have MLC， for example。

 that you are sorting two beats per cell， then your word line， you are sting， for example， two pages。

 right？Okay， so program ands， they are unidirectal。

 you already discussed voltage like when you program a cell you need to increase the threshold voltage and when you're erasing you need to decrease the cell。

Basically a voltage threshold。And the programming page cannot change zero cells to one so that's why we need to do erasing。

 so we do arrays before right property in flash memory。And people do erase at the block level。

 like the programming and read is actually happening at the page level。

 but when want to erase actually people do erasing the whole block like the whole block they erase it and why is that because arrayse is actually quite slow so they want to have high throughput at least high bandwidth so they do arrayse at the Gr of block。

😊，Which means that。That makes in place right on a page very inefficient。So just to give you a clue。

Assume that you want to do in place update。So in this block。

 there is a page that I want to update it right， so I cannot update I need to erase everything。

But there are some valid there are some other pages here that they are you know they are valid and I don't I shouldn't raise them right so one one thing you need to do is you need to copy paste。

Everything。That is stored here to a buffer to a D so you need to read everything， you know。

 keep everything temporary in a buffer and then you you can erase this whole block。

Update that page that we want to update it in that temporary buffer and then store everything back again super inefficient so that's why people just make this for basically they do out of place right whenever I want to update they make this invalid so that okay this copy that I had for this logical address is invalid it's not valid anymore and they just write that logical address somewhere various。

And then you need to update the logical to physical address mapping we're going to see。

 but that's out of place right and the reason that we are doing out of place right update exactly valid exactly。

😊，Yes， if now one is faulty because of too many rights and does the whole page or even the whole block suffer from this it depends on your F I mean some yeah and actually we don't know because that part is not fully you know。

 disclosed but essentially it's very hard if you have some faulty pages。

And you want to still use that page， you want to use that block。

 is it still possible and I know that they are doing it but。In which graity they can keep doing that。

 I don't know， essentially。So the reason of having its own could you repeat please so yes yeah this is yeah exactly so actually as a good interesting alternative we have also Nor flash this is N flash。

 but we also Nor flash， which essentially the string is a bit different you have more connectivity。

And that provides you better performance， less latency。

 but then your density and also the cost is higher。

 so that's why mostly I mean today's SSD is because they want to you know have good capacity for good density they are using non flashlash memory。

 but when you care a lot about the performance you might use no flash memory as well。Okay。

So this is block and then several blocks basically a large number of blocks that they share bits they we call it the plane so this is each of these is an another string and they are actually connected to the same bit line right so the whole thing we call it the plane。

😊，And so there people add two transistors actually to each Naand swing in order to make control that which Naand swing should be able to connect to the bit line essentially。

 so this if for example， this Naand swing needs to be connected to the bit line。

 we're going to turn on SSL and GSL transistors。And other than think these two transitionistors should be off essentially。

 to make sure that we don't have the base interference across so the beginning yes， exactly。

And then another level of hierarchy we have die， which is a die contains multiple planes two to four。

 for example， this is an example die from a 21 nanometer to the net and you can see we have four planes。

And interestingly is that these planes actually， they are shad grow and column decoders。

Which means you can actually do some parallel operation across planes。

As long as the offset is the same so if you want to。

 for example do the same operation like the read operation and the offset in the planes are actually exactly the same then you can do it in parallel so that's a multiplaye operation that we have actually there is a command for non flash memory that you can do multiplay operations but you need to do a lot to make sure that you can benefit from multiplaye operations because because normally it's not easy because of this fact that you need to have the same boat word9 offset parallel。

😊，So you yeah， usually you cannot read four blockss at the same time as actually you don't read B。

 you read T pages parallel。でてまそう。Yes， exactly if they are in the different planes and they are also at the same opposite yeah。

But actually there is also another comment that we have proposed in our recent paper。

 actually not very recent， micro 2022， I mean， if that's recent flash cosmos that we develop multi wordline sensing。

And with that you can actually activate， you can sense multi pages intrab and also multi pagesage intrablock。

 and with that you can do computation。For example， if you activate two pages in one block。

You are doing an operation of these two pages。But then we don't have time to discuss today about it。

Okay， so。And running late anyway this is threshold voltage distribution that essentially you have a reference voltage that we discuss and then the nominal threshold voltage that we consider naively that there is only one place but actually there is a distribution and when you program also you have a distribution and why you have this kind of distribution because we have variations across the sets so there are some says that they are more easily programmed or erased。

😊，And so that's why you have different nominal and also program threshold voltage it's not fixed because of the process value。

So。🎼And this is another example that for example， we have we have when you want to store three bits in each Nlife cell。

 you need to have， for example， eight states and you have MSB。

 CSB and LSB and essentially you can encode these states into you know different encoding and this encoding scheme actually can be different whether to what you prefer。

And what you care more。So there is limited width of basically threshold voltage window here。😊。

Compared to ST as if I show you again， so here you have actually much you wider region。

 but when you go to TLC， these windows are actually much narrow。😊。

And that basically makes in order to guarantee that we have sufficient margin between adjacent threshold states is actually very actually challenging and that's why when you go to from SSC to MNC and from MC to TSC and QSC。

Your read circuittry is going to be more complicated and also you're going to have also more errors because it's very difficult to distinguish across these regions。

And also when you write， and after some plan you have ter voltage changes over time。

 which is retention error which I discussed， for example， one way。

 one reason is actually retention error and why retention actually these are shifting to the left。

 they can be also shifted to the right as well， we're going to see how later if we have time。

 but actually normally retention error is actually shifted to the left。But it's not only shifting。

 they are also widening， so essentially you can see that the shape of these actually curves is also different and at some point they have these overlaps and these overlaps cause errors essentially for you。

😊，So it's like on the sense amplifier on how many bits you can store a。

On send spl mostly under read circuit3， yeah， yeah， sense amplified as far as I can say。

 does not care much。There is a circuit read controller that needs to retry the read process with different reference voltage which actually we're going to see very soon。

Let me get to it。So let's see how， let me finish this part and then we can take a break。

 hopefully short break this。😊，So basic programming， we want to program a page。

 we are considering SC here just to give you the idea。😊。

I want to program this page so we need to apply V program and other sales。

 as we discussed we apply V passs and these two should be on right to connect this Nada string to the B line。

So there is another important， interesting feature in N flashlash circuitry that you can actually control B and you can inhibit cells to nott be program。

So for example， assume that you want to write this pattern 01010 so you know that when it's already erased I'm st one right so I don't need to program for example this fly cell essentially so there is a way to do that by inhibiting these cells if you apply VCC to the bit line you are essentially inhibiting that cell so this cell is not going to be programmed at all because by controlling the which voltage voltage you are connecting to the you're driving to the bit line essentially。

In order to fully understand， you need to know the detail of the circuitry， but this is important。

 this is just to give you an idea that you are able to control every single cell in the flash memory。

So。When your page is already erased， this is the distribution， right， everything' is erased。😊。

So if you apply the program。You want to get to this right so there are some inhabited cells that they really stay in program in their raised basically state and other cells they need to be programmed in their program cells。

Right？But unfortunately， when you apply B program， you get to this kind of。Care。

So if you apply your program advanced once。There are some cells that they are easy to program。

 so they quickly get to this you know high  traditional voltage。

 but there are also some cells that they are hard to program。

 so you need tonovate more and apply more voltage essentially。So in order to fix this problem。

 people came up with this idea of incremental step Pauls programming ISPP。

That essentially the instead of applying V program advance。

 they have incrementally increasing the V program so they have a V program zero and they apply and then after that there are some cells that they are already programmed so after one program zero they check。

So， these。For example。Yeah， so after a program， we verify and we realize， okay。

 this cell is already programmed enough。😊，And then for the next cycle they inhibit this cell by adding VCC to the bit line。

 so this cell does not need programming anymore， and then we will repeat with another program voltage program V program one。

 and then after some time we get to this our beautiful curve that we wanted。😊。

Just after the storage is aged no， no， actually from the very， very beginning。You need to do that？No。

 no， no， no， on that， its not destructive reader。Destructive in the the meaning of Dran that when you're reading yeah。

 no， it's not that， but when you read you might have some read disturbance similar to Dran and also write disturbance you might have。

So this。One is higher than yes， yes， exactly。Wouldn't it be whether to just apply this higher voltage everything。

So that that might， first of all， you need to， if you apply that high voltage at once。

 you should also also wait enough。And then the problem is that those cells that they are easy to program。

 they may actually program a lot。You know， that's the issue then yeah exactly when your SlC maybe you don't care。

 but if you want to really， you know， accurately manage this window with for example， TLC and QSC。

 you really need to be so accurate entire that means entire exactly exactly。😊，Okay， interesting。

So when you want to read， you essentially you need to apply reference voltage as we discuss。

So in SSC is actually easy， you apply reference voltage year。And you need to charge all bit lines。

 basically they're going to be VCC and then basically you're going to monitor if the current flow or not here。

 for example， the current doesor flow， so you know that when I apply a reference voltage。

 this cell acts as an open switch meaning that already I already programme it so you will encode it as zero。

This one basically my current flows so i've been encoded as one and that's how it is there is a circuitry here that understand that the flow you know the current flows are not which I'm kind of ignoring at this moment and I have it in my back office the side if you're interested you can check。

😊，But yeah， but at the high level， this is how it works。But when you want to read in a TLC。😊，In MLC。

 for example， then actually here and I'm showing， I mean。

 MLC people mistakenly usually think that it' actually storyoring two weekss。

 but MLC is saying that multiple or multile set。😊，So TLC is also MC， essentially in the end。

 but TLC here I'm showing we have eight window。😊，So assume that I want to read the basically the CSP。

 which is the center beat。So we apply so we have seven different reference voltages essentially to distinguish across each of these windows essentially right so you have many like seven reference voltage。

So when you want to read a CSB based on your encoding。

 you need to see what are the reference voltage that are important to you。

So those reference voltage that you are observing some toggling。

Those are the reference voltage that you need to be careful about like here， for example。

 one goes to zero， so this reference Vf1 is important for me。Also here，0 to1。

 Re3 is also important and Re5 is also important。When I want to read CSB， for example。Okay。

So the way that you do， you apply first we reference5。And then， you read。

Like you as if you have your reading from SC right when you apply this basically everything before。😊。

Every voltage threshold below V F 5， you're going to encode it as1 right and everything above that you're going to encode it as zero。

😊，So you apply V f 5 and this is basically what you're going to read1，10。

01 you are you're seeing that。Almost is correct， but this one is not correct。Because for this0，0。

0 actually is here。 so I had to you know have a。😊，For example。

 I had to have we actually I had to use VF1 in order to understand that this is programmed。Correct。😊。

So essentially you need to repeat the read procedure by applying other reference voltages that they are important for you。

 so here we also need to apply V F3 and then we read so we have 11001。

And then we apply also Vef1 and V rate。Okay， and then you need to have a technique to logic such that you combine whatever you have read。

Such that you get to the actual data that you have to So this encoding actually very exciting because by by extorting what you have read。

 you're going to get to the。Value that you need。Just an example， but no， not normally actually。

 actually normally you read one of them because you want to read， for example page。

So we are restoring three pages for example in a wordline right so you want to read the center page for example the usually is' not on the same Yeah I mean that can be also that can be also the case but usually people don't do that people store multiple pages different pages in a TLC for example。

Okay， so this some takeaway， essentially we need this ex logic。

And bit encoding actually affects the read latency， so here is a very cool example with this TLC。

 I'm showing two different encoding for example。So the above en codingd is actually what we had before。

But the below is different， right， is it different and code？

So now you can actually have fun bit comparing like the number of reference voltage that I need。

 for example， to read LSB so in the above this basically encoding when I want to read LSB。

I need to apply only reference Bf0 and Vf4 because these are the only you know the two reference voltage that I'm observing togg between。

But for the for this one， when you want to read LSP。

 you need to apply for reference voltage clearly reading LSP for the if you use this kind of encoding is actually slower。

😊，喂。But there is a trade of year when you want to read MSB， for example。😊。

Here you need to apply two reference voltage。But for this one。

 you need to apply only one reference voltage。Right。

 so that shows you essentially that by changing the encoding you can have different latencies and trade off and actually there is actually kind of active research going on that for example。

 this one we observed that reading MSP is much faster compared to reading LSB with LSB I had to apply four reference voltages。

 meaning four read process， but for MSP Im only apply one read process。And people try， for example。

 say that， okay， the MSP page can be used as a cache。😊，For LSP pages， for example。

Right because MSP pages are faster or that doesn't need to also be cache for example you want to store some pages that they are more latency critical so you are restoring them in MSP pages those pages that they are less critical you are restoring them in LSP pages that's for example one of the trade off that you can make but you can also have one bit more trade okay let's take a break。

Let's have a five minute break if possible， and then we will continue afterward， thank you。😊，嗯。这。我。今。

Do。そゃち。不是。说。不是个。それでそ八百。け。Yes这也对。やた。I think you very。ャ。我是这段消息。that's所。🎼，おらし。Yeah。嗯所以钟嗯有接。

have questionHe mentioned that some cells did very fast than others wasnt used what is a day to send a higher higher education so that they get the correct？

EnDuring the right process， you mean？嗯。Since。So some because you mentioned that some of them were hard to was advisory。

 I can't remember yeah。Yeah， exactly。 So there are there are some。

 So when you apply a programming you voltage， Sound says quickly get the together and。Yeah， exactly。

 Okay， and you just check every time exactly exactly so you write with the programming voltage page and then you immediately read what you have written。

And if then you inhibit some cells and then you could basically keep you could just add some like metadata to the D about the entire salary array。

 figuring out which one of those is slower to right。Yeah， yeah。

 that could that could that could work if if those cells are the number of them are manageable。

 you know， so you don't know， I metadata that yeah exactly So the problem is that even。

So there might be some pages， there might some pages that only a few of cells are problematic。

 but other pages that there might have a many pages， many cells that they are problematic。

So in the end the。If I want to summarize like the fact that we have flash memories working today is a magic like I mean it's not magic it's because of all the research and effort that people have made but but these you're going to see actually later today。

Flash memory is you can actually。You know， and you can consider it as a noisy channel。Like you right。

In a in a noisy channel and when you read you are really noisy essentially and then you need to do a lot to make sure that noise you can work with that noisy channel Yes now hot pages are pages that you might write to them a lot for some reason your leveling might not be effective enough and you might do a lot of writing in some blockss So when you in the end when you count the number of program arrays for every blog there might be some blogs that you have use them you call them as hot blogs and those blogs are they're gonna vary out quickly essentially there are some cold blockss that they are not they are still they have time so you gonna swap them and it's easy with flash memory architecture swapping because can you have these logical to physical mapping right so you have the possibility in the end for example don't have that easily So when you are reapping some it's not。

Rapping is not easy is not the easy thing to do in Dra， for example。

 it because you got more precious just you can just take some random no no。

 but even even if you realize that okay， there are some roles or in Dam but they are faulty。

 for example。And you don't want to use them， so you need to reap to somewhere else。

 essentially to another rule。So I think you can you can do that from some of the analysis that we had。

 but it's not。So the circuitry is not there much so you're not that flexible when you're doing a remapping。

 you need to be more careful in the end。Okay。Okay， let's continue。So there are actually a lot。

 a lot of things that I didn't cover in the first part， for example， there are。

A lot of advanced commands in NFlash memory to improve performance that you can check them in my back of a slice and I'm going to also you know put some links to other lectures that you can check if you're interested。

 but I want to also quickly just give you the basic of address mapping and garbage collection。

So we discussed about this flash translation layer that it provides back compatibility with traditional HDDs actually that's one of the important feature or let's say task of FDL or SSD firmware to provide that back compatibility for you and that happens by hiding a lot of characteristics of nonflash memory so there are many things which they are specific to flash memory and your system does not need to deal with all of them so the FTL is actually doing that to make a very nice interface for you but in addition to that FTL also does a lot of for making sure that flash memory works well。

😊，So some of the important responsibilities， for example。

 address translation and garbage collection that we're going to see we leveling that we already discussed a bit and data refresh and audio scheduling hopefully we're going to see I mean this one for sure and data refresh also in my future slides。

 but I will let you check very leveling an audio scheduling later through my backup slides。😊。

So this is let's start in an example。😊，A very simple SSC architecture we consider we have one plane。

 single plane and we have five blocks and in each block we have four pages。

And this is the way of the whole system， the way that the fo system or audio block actually looks at your SSD is actually kind of continuous area。

So your logical address space， for example is 16 basically pages。

 so this is a storage view at the operating system level， a flat block device。

And each of them is logical block address。And that's something that people gets a bit confused because。

This block is actually considered on page here， so the terminology of page block is different at the OS。

With yeah exactly compared to the SSD so we have physical block address。

 so this is the address for physical block address and also physical page address。😊，At the SSD level。

Okay， so and you can see that we have kind of overproing here that physical capacity is greater than logical capacity and that's something that always happened in SSD so when you buy for example SSD with one TBbyte that SSD actually internally has much more than onetbyte。

😊，To make sure that we can do these out of place update as much as possible。

 at some point you cannot and you need to do garbage collection that we're going to see。Okay。

 so we receive a request from the host from the logical block address zero。😊，And the size is one。

 one sector， and the direction is right with the data。So essentially your plane is completely empty。

 your SS rate is a to this block0 page zero， essentially。

So we are assuming here that logical block size equals to physical page size。

 so basically4 kilobyte and physical， but usually the thing is that normally in our SSDs。

 physical page size is actually6nct kilobyte。😊，But that's something that I kind of ignore now and you can check my backup slash for fingering mapping if you're interested。

 but this is for simplicity， we consider that these two are the same size essentially。

Okay later on we receive another right request， starts from logical block address4。

 the size is 12 and the direction right and this is all the data。

So you might think that SSD actually starts to write from you know because this four and here is four so nicely I can write right and then even this is also 15。

 this is also 15 so all good but the thing is that SSD writes like this。

So starts from continuing from block zero and why is that actually from the reliability reason once you have a block open to write which we call it open block。

 you want to write to that block as much as possible as as fast as possible because keeping a block open actually cause reliability issues for the。

Data that have been installed storeded already so that's why block zero now is open so I will continue writing BCD here and when block zero is full then I go to the next block and open block one and then write to it also。

😊，So that's a baby right。This is talking about this active block problem that I already talked about so now you can see that later on when I receive a read operation for logical block address for basically we don't know from where I should read because physical page address now is different it' not for so that's why we need to have this address mapping logical page address to physical page address。

😊，That tells us that basically logical block are four maps to physical page address one。😊。

And by getting this information， you can access your flash memory and get your data。Okay。Sounds good。

So later on you receive another write， which is actually kind of considered update because you are writing another value to the logical block address that you have written in the past。

 so now you have update。😊，The problem what we are doing here is that we just we do out of la update。

 so the open block now is block three， so we just write a prime there。

And then we need to make this one invalid so that one is not and also we update this location that this is the you know the new location for this logical page address。

 so we receive another update we update invalid update invalid update and at some point we are running out of free pages okay。

So now we get to this garbage collection to reclaimse three pages by erasing invalid pages。

 so now you can see that we have， for example， a lot of invalid pages， right？😊。

So we can' try to erase them to reclaim three pages。So a race unit is blocked。

 so if a victim blocked the block that we want to erase has valid pages。😊，Like these。So here。

 for example， if block three is your victim block， three of them are invalid。

 but you still have a valid page， right？So essentially you need to copy basic all the valid pages need to be copied to other free pages。

And that comes with the performance overhead because you need to read all these valid pages and there might be a lot。

And then you need to write them somewhere else and that cause lifes on overhead as well。

So usually one of there are a lot of policy for doing a garbage collection。

 one of simple one is greedy that you essentially erase the block with the largest number of invalid pages so you want to make sure that we have less number of valid pages because the problem is coping valid pages so then we need to maintain number of invalid or valid pages for each block how we are doing that we add a status table to our F and for each block address physical block address we are keeping the status so here for example block zero we know that the first one is invalid and the rest is valid。

😊，And for example， for block four， we have valid and three free。😊，And for block3。

 we have valid entry in。So now I want to invoke garbage collection。

 basically I will select the victim block the one that has the highest number of invalid pages。

 so this one I will select。I need to essentially write basically read the valid page。

Which is read the address 12。And then program it。And somewhere else。To make this fun invalid。

And then I need to also update。This is status table and also update the mapping。

 so we also need to know that this physical page address 12。

Initially it was mapped to logical page address 15。And now I need to change this to 170。So normally。

 you cannot do that because this table actually only stores these three from logical page address to physical page address。

 you cannot get the logical page address associated with two physical page address。😊。

How we do it essentially we in a in each page we have some area which we call it out of band out of band area that we store that this page belongs to each logical page address。

 so we are using some auto of band area in each flash page。

To basically sort the logical page address for that。

 and we are using that in order to understand that this is logical page address 50。

So you update and then now block tree is all essentially invalid so you can raise it。

And now physical block address3 is all free， so you updated status。

And you can use this block three for future rights。But just to make to basically to。

Just to let you know this raise operation， you are doing it， you don't do it immediately。

Because once you erase a block， you make blocky active， you make block ready to be written。

 and you want to do it when you really need to do it。😊。

So usually we invoke garbage collection actually a bit ahead of time I don't wait until I don't have any free pages or I have only a few pages and then I start doing garbage collection so SSD starts doing this garbage collection for example when SSD is not that much active you know invoke it to reclaim some free pages so there are some blocks that they all have invalid pages and I can raise them but I don't do it immediately I will wait until I have to do it you know for example。

CPU orchestra and sort ofNo， the things have when you' yeah， so when you well no。

 we don't have that much that kind of information， but when you write you usually write to the dealer right during I write。

You have that information， yeah。Okay so garbage collection actually cause a lot of performance issue and because of this for example。

 copy， a block， for example， can contain 576 pages， if you。

 for example assume that only 5% of pages in that victim block are valid。

 basically you need to copy 5% of this number of pages somewhere。😊。

So you need to read and program and the number of pages that you need to copy is around 28。

And garbage collection latency is going to be at least 28 times reading and programming and also erasing essentially and this is actually a lot like 27 millisecond which is orders a magnitude larger latency than reading program so that's why actually garbage collection is so expensive and if FTL for example perform garbage collection in atomic manner。

 it delays user requests for a significantly long time so previously in the it was the case when you were providing your SS the performance was good。

But at some point， garbage collection starts and you were seeing actually significant drop in your performance。

😊，Because of garbage collection。So there are some mitigation techniques that people came of like T is a command that people basically proposed it at the software layer at the OS that we can inform FTL of deletion or delocation of a logical block。

So at your system， when you delete a file。😊，Normally you don't inform SSD or hard disk that oh I delete this way you're gonna just delete from the page mapping that you have at the OS right but with trim command people tell you that okay when you when you docate or when you delete something you can inform SSD that page or these pages are not valid anymore so then SSD does not need to basically copy them you know through the garbage collection so with trim command you can inform FDA that we skip copy of obsolete or invalid data essentially。

Go to。Yeah， exactly。 yeah， but that command was not there。 So after so because when when SST。

You know， it started to to be used more and more people have been using the audio system or audio block that has been。

You know， propose for Hardy stfe， but people started to look into okay how much I can improve it。

 like to make it more specific to SSD and that twin command was one of the thing that is already added to Linuxn。

 for example。😊，N can you can do。You can also do garbage collection at background。

 so the challenge is that how to accurately predict SS the ideal time people who have work on it。

 there are heuristic techniques there are also machine learning techniques that to understand that when SDC is ideal to a schedule garbage collection request。

 you can also do progressive GC that you divide garbage collection process into subtestt。

 for example if you want to copy 28 pages。😊，You copy one page and then you service one user request and then do it multiple times so you don't for example do okay i'm copying 28 pages i'm not going to do anything else and when i'm done i'm going service some other resources request basically you're going to do it progressive essentially you know。

And that is very effective at decreasing the tail latency of your request。Christian。Yes。

 where is the mapping table and how is is actually stored。So mapping tables is stored the data。

And that internal them of the of the SSD week。So actually， yeah。

So the actual mapping table is stored in the flash memory。😊，But when you want to use your SSD。

 that mapping tables should be loaded to your to that internal D that you have inside SSD。

Enterprise SSs， that D is large enough to house the whole mapping table because you want to be fast。

But low cost SSDs as the mapping table is not large enough sorry the D is not large enough so you cannot house the whole mapping table so people came up with caching technique like DFTL is one of the cool technique for in S+ 2009 if I'm not mistaken that they try to cash mapping table essentially。

 so you can also think of prefetching caching and like all these things have been you can also revisit there as well。

Okay。Very good question。So I cover most of it， I didn't cover a scheduling and flash memory parallellles for that you can check previous lectures in the past and also my backup slides。

But I want to also go into error characterization。In flash memory mitigation and recovery。

This lecture this part is three hours by itself。😊，But clearly we are not going to do that。

 but at least I will give you some idea about it。Christian。Are you excited。

This is a cool thing topic at least right？Okay， so。This survey， error characterization。

 mitigation and recovery in flash memory based solid state drives is actually summarized many of these techniques or this characterization that Professor Mu's group have and also other papers that they have done to understand basically flash memory reliability and basically characterization and also provide some mitigation and recovery techniques。

😊，So。I don'Unfortunately， I don't need to go into background or know all this stuff。Lotin gate。

 how will you write？Okay， good。This is a side that I already talk about it， N and nor。

 you can see that in Nor flash actually we have much more connection to the bit line and is actually faster。

 but the problem is it's density which is lower compared to the Nan flash memory。😊，Okay。Yeah。

 this is also the problem of retention loss that we already discussed and we're going to have errors after some time。

This is this paper actually talks about how we store multiple pages in MC N flash memory。

 so if we want to understand how they map different pages to MC architecture。

 you can check this paper actually。嗯。Okay。So many of the work that I'm going to discuss。

 they are considering Plan N flash memory， which is3。

So I want to give you just a very quick story that essentially in 2D flash memory。

 so the vendors they wanted to you know improve the capacity。

 so they made the flash cell smaller and smaller and you can guess it so when you make it smaller and smaller like D also you know you have much more reliability issues。

So and actually they reached the point that they were kind of strugglingug， you know， how they can。

 you know， provide better capacity why they don't， you know。

 but but not at the price of even worse reliability， essentially。

So then 3D nonflash memory technology actually comes to play and that gives some freedom to the or let's say breathing room to the vendors and they could provide some capacity through the you the 3D architecture and they were using larger sets so by using larger sets they could provide better reliability and they provide the capacity。

Vert， I mean， through the 3D architecture。So at that time。

 this 3D and flash memory was not well studied， let's say 201617 or so。

 but now there are also some works that they also discuss about 3D and flash memory reliability and so on so forth。

 but the thing is that。Back then，t people haven't observed much of a reliability issue when they use  tradingD and flash memory because cells were larger。

But again you can guess it as we you know， as we wanted to have more density then they have to even for treating nonfleshman。

 they also had to make it smaller and smaller and now we have even different and it can be actually severe in some cases。

 issues that we have。😊，So this is structure of Tri and fresh memory memory。

 I'm not going to into detail of it because the part that I'm going to talk about it today is not actually related to 3D flash memory。

 but you can check the backup slice if youre interest。😊，Okay， so。

We discussed about limits of charge memory and essentially the problem is that MC and flash memory liability endurance is a key challenge for satisfying future story system requirements。

And our goals at the time was to build reliable error models for NFlash memory by experimental characterization and develop efficient techniques to improve reliability and endurance。

😊，So by having kind so flash memory have ECC and ECC can correct some of the errors。

 but ECC are usually good for things that you don't know like there are some errors that you don't know the source of them right so once you have an error and you can understand why such errors are happening you should be able also to design some techniques some architectural techniques to mitigate those errors essentially。

😊，And then that reduce the how much you rely on ACC essentially。

 so you could get the same reliability actually by using much smaller ACC or using the same CCCC。

 but then you get much longer time， you know， the higher endurance and lifetime for your flash memory。

 so that's why actually why these kind of works are quite important。😊。

So this lecture is going to be actually flash summary many of our recent results in the past 10 years and these are some papers that I'm going to。

 I mean not all of them， but yeah。😊，Okay， so this kind of evolution of N flashlash memory from 1998 to 2010 and so that essentially you can see that flash memory is widening。

 its range of applications and portable consumer devices。

 laptop pieces and enterprise servers essentially。So the problem we have with flash is reliability endurance。

 this is the endurance。Result for at the time that for SLC you can you have kind of around the 100。

000 endurance， the number of program very cycles for MSC is lower and for TSC is much lower so the P cycles provided is few thousand specifically for TLC。

However， the PE cycle required based on this standard is actually 10 times per day for five years。

 which means that you need somehow more than 50 k PE cycles。

 so there is quite a big mismatch between what you have and what you need。So。

The question is that how we can hopefully bridge the gap by using more intelligent technique to provide reliability。

So in theance of flash memory decreasing with the scaling and multileve cells。

 which you can also guess it， like when you use MLLC。

 you have much less reliable and also when you scaling it your cells are smaller。

 this is also very similar to data the issues that we have。

And then in order to have reasonable fee cycle， you need to add stronger ECCC。

 so you need to increase the complexity， the error correction capability in order to basically tolerate and provide some reasonable endurance。

Okay， this is what I talk about it， that Nan is kind of noisy channel that you write it and read noisy。

😊，So from this noisey you have this memory signal processing and with that memory signal processing hopefully you can get some lower raw bit error rate and then you can have a much better error correction code or let's say let's cost the error correction code such that you get to the uncorrectable bit error so this is the standard which we call it uncorrectable bit error rate。

It should be less than 10 to the power minus 15。So the goal for ACC is that we need to get to this rate。

So when your uncorrectablebitta rate is higher than that。

 that means that this is not a medium that you can use it as a storage， for example。

 so that's the standard essentially。Okay， so our goal is to build reliable error models for N flash memory and design efficient reliability mechanic based on the model。

😊，Okay， I can kind of skip these things， so these are different papers that we have published for to understand and characterization and also where we apply technique to when we want a race block when we want when we are programming page neighbor page program set to sell interference and retention error。

I think I already discussed about this。Okay， so this survey is actually full of information and I would recommend everyone that if you're interested in understanding all this stuff。

 check this one it's very very actually informative survey。

But let me show some of the results so this is the infrastructure that we had at the time。

 you can see the Vertex 5 FG and we had this Nant controller there were some Nant company that they were helping us to build this technology。

And basically to have this kind of N controller because having Nant controller is also a big challenge。

And that's why they help us。So there are four types of error that can cause。

 so one is caused by common flash operation， which is read errors， errors errors and program errors。

And another one is caused by flesh cell losing charge over time， which we call it retention errors。

Okay。Essentially in all the pipeline of Nflash memory you can have errors so when you era block you have era errors when you have program you have program errors。

😊，When you also have retention errors， you might have read errors。You have retention errors。

 basically， you have error everywhere。And that's why actually flash memories are quite error from。

Okay， so let me show some results。So here in this plot you can see that essentially raw bit error rate increases exponentially with PE cycles so when you have higher P cycles。

 raw beat error rate is much higher， I should also say that this raw bit error rate before ECC so hopefully your ECC should be able to reduce basically make this beat error rate in less than 10 of the problem minus- 15。

So when I say that real bit errorerate。Bas essentially the error rate that you observe before applying ECC essentially。

Okay and retention errors are dominant， so more than 99% for one year retention time and retention errors increase with retention time requirement。

 essentially。So essentially electron loss from the floating gate causes retention errors as you can imagine。

 but the interesting thing is that。Says that they they have they are storing more charge。

 actually they are more。They have more different shares。So in this plot。

 we actually show different patterns like how much error we got， for example， Im going。

From00 state to 01， for example。This one so you can see that this one is a big chunk and from 01 to 10 is also another big chunk。

 but other pla also have we have observed some of them。

 but they were not that probable as you can imagine。Okay。

 so you can check this paper for others and seeing all these you know error patterns in MSC and flash memory。

 but now I want to see how we can do some management based on this understanding。

So solution to retention errors is we can refresh periodically， as we also do in DA。

Hopefully we don't need to do it as frequently as we do in data。But see。

 if you want to avoid retention errors， you can refresh。So you can change the period。

 the period to which you are refreshing based on the PE cycle where when your cell or block is still young。

 you don't have that many PE cycle you can actually do refresh less frequently。

 but when your device is quite aged like for example， you have 10，000 P cycle。

 then you might want to do refresh more frequently just to make sure that your device is working correctly。

And you can actually use a combination of in place and remapping base refresh。

 So when you want to do refresh， you can just。Write to somewhere else。

 so before losing your data you read and you write to some other pages。

Similar to similarly to out of place update right just write the numbers so that's a refresh。

 but you can also do in place。Refresh， which is interesting and I'm going to show you， but that。😊。

Is mostly possible actually in SlC devices in MLC， it's very hard to do in place update without losing reliability because of adjacent roles or pages。

So。We had some key observation here， retention errors are the dominant source of errors in flash memory。

And limit that limits flash time as they increase over time okay retention errors can be corrected by refreshing each flash page periodically and the key idea is periodically read each flash page correct its errors using ECC so hopefully you don't need that as much strong ECC because you don't wait until you have a lot of errors and then you really need strong ECC to correct things so you write and after some time you read and hopefully by that time that you're reading the number of errors is not that much so you can fix them with a weaker ECC。

😊，And then you either rem it to a new physical page or reprogram it in place。So。And basically。

 you should be careful to do it before the page accumulates more errors than ECC correctable capability。

😊，Okay。So there are two key question， how to refresh。

 which I already discussed you can do remap or reprogram or you can do hybrid。

And also when to refresh， you can have fixed period or you can be adaptive the， for example。

 to the retention to the number of P cycles， for example。

So in this paper we realize that based essentially hybrid and adapt the period is going to actually lead to a better solution。

 so how we do in place reprogramming of life cells。After some time。

 basically retention errors are caused by cell voltage shifting to the left。

 so you're going to have this kind of you know distribution。

So you can actually do ISPP to move sales voltage to the right， essentially， so you do that ISPP bit。

And you need to be careful but essentially you do ISPP and then you read and then you check ECC and hopefully you should be able to fix errors and then you already after some time you can see that okay。

 I already fix a problem I refresh in place。So the problem I'm saying that this one is actually less effective or。

At least it's not easy to do it。Because many you do in place update。

So when youre so later on you're going to see program interference essentially。

 so when you' are programming you' are actually adding doing some interference to neighboring pages。

 so when you're doing in place updates actually you are adding some accumulate some errors to the neighboring pages that you have in that flash memory。

That block。So when you have SLC， this might not be a big problem because you have room you know。

 to error， but when you are using TLC for example， or TlC。

 in place update is not easily actually doable。😊，Any question。Yeah， as I said。

 the content actually increases the occurrence of program errors。

 which you might not be able to tolerate it if you have TLC or QC， not flash memory。😊，So with this。

 we observe that， for example。Having a remapping based， having hybrid FCR and adaptive FcrR。

 which is the best technique we can actually provide。A much higher lifetime。Yeah。

 so you improve lifetime base compared to the basin。Okay， and and the energy overhead。

 so using adaptive rate refresh。😊，Still is less than 1。

88% energy increase until daily refresh is triggered so as long as you are refreshing。

Less than know once per day。Your energy overhead is less than 1。8%。

But at some point your block is so aged and you need to do it you know more frequently like every day or even every hour。

 you know， and with that then your energy overhead is going to be much high Yes。

 so with re basically refresh isn't that like a devil because its it indeed。

There is a paper that talks about it， but I actually have it in these slides。

 but I'm not going to get reached to that point， but that's a very good point， yes。😊，Okay。

Check this paper again， it's a very interesting paper to read。Okay， how much time we have？Okay。

 I kind of see it also。Any question？Okay。So。Now let's look into threshold voltage and program interference analysis。

So there are some key questions that here we want to ask like how does threshold voltage distribution of different program state change over flash lifetime and can we model it accurately and predict the VTS change so if you can model。

You have a model that tells you that okay， which so my ter voltage is going to be to is going to be what amount you know after some time after the number of P cycles。

 so then you can use that model in order to get to the optimal reference voltage that you need to access your flash memory。

Okay， so。We work a lot on this and then use some of these。

 you can see the distribution across different number of PE cycles。And then let me see。Yeah。

 so essentially we came up with a model and that model can modeled with 95 person accuracy as a Gaussian distribution withitive additive and white noise later on also we improved that model by adding a students T model which I have a slide but I'm not sure if I'm going to get to that。

I think I can get to this actually here so this is。So there are some cases that you have problem。

Like。So these are the actual you know the distribution that you have。

 so your GaussA model is going to tell you this you know dots。

Care but there are some parts you know that for example is happening here so you should be able to somehow basically predict and with that we actually use a students a students T based model in order know to model the whole plot the whole distribution。

And actually， studentss T based model provides the results similar to Lapl model。

 but it's actually much faster。So it's easier to do it at the run time， essentially。Yeah。

Be normal love plus。You are getting the same average， more or less。

The average of basically the error that you are getting。

And essentially you can get to use this students T to get have a good trade off between Gsian and normal levelss。

Okay。So now you can use actually this kind of model in order to design technique for better reliability。

 so when a cell is being programmed voltage level of neighboring cell changes and that's we call it as a program interference error and that can cause the distribution of traditional voltage to go to the right here normally I talk about retention errors but this can actually increase。

So this is just a reminder how we do programming。Here is my victim。Seell and all over it。

 we have some rightss。Even in the same boardline and also other neighboring board lines。And。

All these they're going to have some deelta voltage changes and everything can affect the terial voltage of the victim cell。

Actually， people realize that。The cells at the bottom actually the lower， they don't affect much。

 so it's mostly actually the top and also neighboring。And yeah。

 and they so this is the traditional model for victims cell threshold voltage change。

So the problem with this model is that this is not accurate enough and also there are some values that you cannot easily calculate like coupling capacitors is not easy easily calcable。

😊，So our goal was to develop a new， more accurate and easier to implement model for program interference。

 and the idea is to empirically characterize and model the effect of neighbor cell threshold changes to the VTH of the victim。

😊，So this is the model that we wanted to learn and essentially these are the thing that you can calculate so these are different like the change of the voltage in the neighboring cells and also some parameters that you can also train them using your analysis or characterization。

😊，Okay， so here is our analysis that our victims still。

We observed that immediately above cell interfer is dominant。

 so this cell is going to be the most important one to affect the threshold voltage of the victim' cell。

And then immediately diagonal neighbor is the second dominant。

But also far neighbor cell interference exists also so these all far neighbor also they affect the the victim cell threshold voltage so as a result of all of these interference we observed that for example。

 the threshold voltage of this cell has been changed by for example，2% for example。Okay。

So we actually designed this model and then the accuracy of this model is。Quite reasonable。

 as you can see from this plot。Okay。Let me see。Any question？啊。

Let me also quickly also go into key idea of the second one and then I think we are done。

I was not planning to actually。Over others， so I think I got to the point that I want。

So now so what can we do with the model， the goal is to mitigate the effect of program interference caused by voltage shift。

So after some shift essentially when you have some overlap。

 there is an optimal reference voltage when you apply that， hopefully you have less number of errors。

 so the idea is that we should have less number of errors such that ECC should hopefully is able to correct errors。

So when we have that kind of state actually having the reference voltage is okay is easy。

 but the problem is that we might have this kind of variation that our reference voltage is actually here and you can see that we have different overlap so now actually I need to actually adjust the reference voltage。

😊，And so the reference voltage is that is here is actually going to be better， the optimal one。So。

So the goal is to layer like understand that where I'm standing and then adjust the traditional voltage。

 the reference voltage study， the reference voltage such that you can get to the optimal。

A number of errors essentially。So you need to predict this threshold voltage shift， essentially。Okay。

🎼So we have this threshold shift learning， which is done every 1 KP cycles。

 you program sample with known data pattern and tests。

And then a program a their neighbor cells and test victim threshold voltage after interference and you characterize the mean shift in threshold voltage which is we call it program interference noise and then once you have it then you design optimum reference voltage prediction so we default reference voltage plus predicted mean VTS shift by model so the model tells you that okay how much you need to add to your reference voltage in order to create。

And with that， you can actually improve performance。

 This is the plot that I wanted to actually talk about and then we are done so essentially you can see that。

Having the same ECC support using 32K bit BC code。You can actually increase the lifetime by 30%。

Right， so you have。Higher lifetime。But you can also look into this plot in other ways and say that having the same。

Like by having if I want to have the same number of the lifetime。

 I can actually have less powerful ECC， like PC code can be simpler。So it's actually the both sides。

 so you can have with this similar capability of ECC， you can have a longer lifetime。

 or you can you should be able to also reduce the complexity of ECC while you have more intelligent technique to handle。

And with that， I think I will stop。But yeah， there are a lot in the back slides and also a lot of links so if you're interested you can check we can also discuss later if you're interested。

 so thank you so much and see you next week for the last lecture I guess。



![](img/8bfbb4e3708c5d2dcc3dd769d48d6f6a_3.png)

Yes。