# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P66：Chapter 5 13.Memory Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/cb725cea137e434e77d9985e3747b532_0.png)

Memories are another important part of our digital systems。So we store a memory using memory arrays。

And these efficiently store large amounts of data， and here's a picture of a memory array here on the right。

And we have an input or address that we want and bid address， and we。

Either read or write data into that array。 So these arrows。

 we can either write that data or we can read the data out from that array。

And so this M bit data value is read or written at each unique end bit address。

 So with2 bit address would have。Four or two to the two unique addresses with a 10 bit address would have two to the 10 or 1024 unique addresses。

There are three common types of memory， DRAM， which is dynamic random access memory， SRAM。

 static random access memory， and RAOM， or real only memory we'll talk about each of those。

So here's an example memory it's really small， but the principles extend to larger sizes。

 so memory arrays are two dimensional two dimensional arrays of bit cells。And so here's the。

Kind of highest level view of our memory array。 We have a two bit address in this case and three bit data。

And so with two address bits。We have two to the two possible unique addresses。Or 4， right address 0。

0，0，1，1，0，1，1。 And so we can store3 bits of data at each address。 So， for example， at address 0，0。

 we have the bits 0，1，1 stored there。At the address 11 or address 3。

 we have the value 010 stored there。And so each of these bit cells。

We'll dive into what those are this abstract view of them right now。

 that bit cell stores a single bit。And again， we have N address bits and M data bits。

And we can also refer to this as2 to the N rows。And M columns。 And so this。

 this number of rows is the depth。Or the number of words that we can hold in our in our memory array。

 and the width is that the size of the word。 So in this case， we have3 bit。This width is three bits。

 so our word size is3 bits。And so this array is a two to the n by M bit， array， a memory array。

 So we have two to the n2 to the two by three bit or4 by three。Bit memory array。 In other words。

 we can store a total of。So we have a four by3 bit memory array， we can store four words。

 our word size is three， and so we can store a total of 12 bits of data。So for example， in this two。

 the two by three bit memory rate， if we look at address 10， for example， we have。The word 1，0。

0 stored there。We have the word size is three bits and the number of words or the depth is four in this case because we have two address bits。

Here's another memory array， we have 10 address bits。

 so we have two to the 10 or 1024 words stored in this array and the word size is 32 bits。

 so we have two to the 10。Bits and 32。Bits per。Per entry， right， our word sizes is 32。

 So each of those rows contains 32 Bs， the width of our array。Its 32。

And we can store a total of two the 10。buuy 32 beds。Where。2 the 10 by2， the5。Its equals 2。The 15。

Bits of data。Or 32 kilobits of data。So let's dive into what's inside of a B cell。

 So each bit cell can store a single bit and each bit cell has a word line。

Which is essentially an enable。Wine。So that when this bit cell is enabled。

It allows what's stored in that of1 or a0 out onto the bit line。

And so we're going to focus on reading， writing is similar。

 except what's on the bit line gets then stored into that bit cell。And so let's say， for example。

 we have， on these cases on the left， we have the word line equal to1 so that means those bit cells are enabled if what's stored in that bit is a zero。

Then when because of our word line being1， that zero can go out onto the bit line and makes the bit line zero。

Similarly， if what's stored in there is a one， well， as long as the word line is one。

That one goes out onto the bit line。And the bit line becomes one。In contrast， if our wordline is0。

 that bit cell is not enabled。 and so it's basically。No connection。When this word line is zero。

 it says， oh， no， not enabled， can't go out onto the bit line。That bit line is then high impedance。

So now let's look at the entire memory array， we have word lines， which again are like an enable。

And a single row in the memory array can be read or written at any given time。

And this wordline corresponds to a unique address。So if we look at how we build this。

 we have a decoder here。On the left。And our address comes into a decoder。

And whatever address of this， right with two bits we have。One hot output on our decoder。

 So if the address is， for example，0，0。This word line， word line0 is high。And allows。

The bits not row to go onto the bit line。And the bit lines are connected to the data output。

If on the other hand， the address is， for example， 10， while now word line two。It's going to be high。

 but only remember， decoders have a one hot output。 Only wordline 2 is high。 The rest are 0， right。

 So we get a one here on word line2， the rest are。0。And so only the bit cells in that row。

Were enabled to drive。The bit line。And so we can read that data then out on our data output。

So in this case， when the address is 10。We read out the values 100 on our data lines。

So let's talk about what's contained in those bit cells and that is determined by what kind of memory we're using。

 so there are two types of overall memory， random access memory or RAM and RAM or read only memory and the names RAM and RA are actually historical most important part is that RAM is volatile。

And roM is non volatile。 so volatile means for a for a random access memory Ram。

 when I turn off the power to that circuit， that memory is lost。

 So volatile means if the power is lost， so is what was stored there。Non volatile。

Or ras means that when I turn the power off， that memory is still stored there。 So， for example。

 my smartphone， I took a bunch of pictures on there， and I。It runs out of power， it turns off。

My pictures are not all gone because what is stored on is ro instead of RAM。ok。So again。

 RA is volatile， means it loses its data when the power is off。But it's read and written quickly。

 so this is an advantage of using Ram over RA。And our our computer memory is Ram。 So DRA。

 when you talk about how much memory your computer has， that's DRA。

Historically it was called random access memory because any data word was accessed as easily as any other。

 so this is in contrast to like a tape recorder where it's not random access。

 it you know if you're close to that part in the tape， then it's going to be fast。

 but if it's two hours later on the tape that one's going to be harder to access。

RM or random assessment， any data address was as easy to access or as quick to access as any other。

Read only memory or Iran is again the defining feature is it is non volatile。

 sos its power when it retains its data when the power is off。Rom is read quickly。

 but writing is sometimes impossible or like on your phone or your thumb drive， it's just slow。

So flash memory cameras， thumb drives， and digital cameras all use roMs so that when the power is lost。

 you take your thumb drive out of your computer， the data doesn't go away。Historically。

 it was called read only memory because they used to be written in the factory and this was done by burning fuses and they could only be written once and not written again。

 so they were called read only memory。But again， that's clearly not true anymore， right。

 or the flash drive that I use I can。Both both read down write that。

 So Ram now refers to the key feature of being non volatile。

 retains its data when the power is turned off。

![](img/cb725cea137e434e77d9985e3747b532_2.png)