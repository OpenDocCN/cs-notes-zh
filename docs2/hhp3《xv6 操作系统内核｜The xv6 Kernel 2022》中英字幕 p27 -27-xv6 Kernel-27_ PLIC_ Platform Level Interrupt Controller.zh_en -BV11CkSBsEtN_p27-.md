# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p27 -27-xv6 Kernel-27_ PLIC_ Platform Level Interrupt Controller.zh_en -BV11CkSBsEtN_p27-

![](img/da1cf8f6bcaa577091b6c9a933918bbd_0.png)

What happens when an I O device wants to interrupt a processor core？ Well。

 if this question has been bothering you， then this is the video for you In this video。

 I will describe and explain the platform level interrupt controller or the pque。

This is a circuit that's particular to the risk five processor ecosystem。

Although other computers have similar kinds of circuits。

 so if you are interested in the subject generally， this will be a helpful video。

This video is part of a series on the X V6 operating system kernel。

 but this video is pretty much just about the pque and doesn't talk too much about the kernel itself。

 However， at the very end of this video， I will go over the code in the file， click dot C。

Let's start with a high level overview of the problem。Here we see some IO devices。

 We may have some disks， here's a keyboard， we may have some other devices like a UAt or a USB card or network card。

And we have cores down here。 And from time to time， an I device will require attention。

 and it will need to interrupt one of the cores。 So， for example， when a human types of character。

 the keyboard might send an interrupt， and it needs to be routed as some core and that core will then talk to the keyboard directly。

It will run an interrupt handler。 So the corps will be executing along。 It will get the interrupt。

 A trap will occur， and then the interrupt handler code will run。

 That code will then ask the keyboard what character was entered and。

Probably added to some buffer somewhere。 And then that interrupt handler will say I'm done with the interrupt and go back to whatever it was doing before it was interrupted。

For disks， typically they're。Busy doing a read or write operation。

 which takes a relatively long time。 And when the operation finishes。

 the disk will then send an interrupt。 And so some core will need to be interrupted and that will cause a trap in the core and that core will then talk to the disk directly。

 and perhaps wake up some waiting threads that we' waiting on the operation to complete。

And it may also start that disk on another operation and then go back to doing whatever it was doing。

 So again， when a device feeds attention， it sends an interrupt。

 The interrupt is routed to one of the cores that causes a trap。

Whatever their core is doing will be suspended， and that core will then run an interrupt handler。

 which is some code that will talk directly to the device so it will go around the p。

And so the question is， how does the p route the individual interrupts to the various cores？

We have to assume that not all core can deal with all devices。 For example。

 there might not be a direct connection between some devices and some course in a large system。

 So the first thing we have inside the click shown here in red。 is a large enable matrix。

 And this is a matrix of bits。And it shows which devices can send interrupts to which cores。 So。

 for example， this keyboard here can send an interrupt to either this core or this core。

 but not this core and so on。 This big enable matrix is generally set up during the initialization phase and won't change。

Now， the p。Is connected along with the audiou devices and the cores and the main memory to some other interconnects。

Here， I've shown the cores and main memory。 And typically， there's a bus down here。

 So if a corps wants to read or write to main memory。

 it sends a request on this bus and data is sent either to the main memory or to the core。

If the core wants to。Manipulate a particular I O device。

 It generally uses memory mapped I O registers。 So these devices are each mapped into some addresses into the physical memory address space。

 and for this core to communicate with this disk， it will either read or I should show read this way。

 or will write data to the memory map registers。Up above， I've shown the interrupt lines。

And those are essentially wires that are used to transmit the interrupt。 So when an interrupt occurs。

 the signal will go over the wire to the p， and the p will then notify one or more coar that some device is requesting attention。

The p itself is also memory map， so for example， to set it up during the initialization phase to write in that enabled matrix。

There are registers inside the p。 So one of the cores during initialization will do rights to these memory map registers in the p。

 Also， the communication to the p to indicate which interrupts are accepted and when the trap handlers complete are done using memory mapped references。

Now， some devices will be integrated on the same chip as the cores and others will be external devices。

Typically in a processor， you'll have several cores， maybe four cores on one ship。

And the p will likely be integrated on the same circuit chip as the cores。 In the old days。

 it might have been a separate chip， but then we didn't have multiple cores on a single chip either。

Some of the devices may be integrated on the same circuit chip as the cores and the plck。

 and others may be external。For example， a U art device is almost always going to be integrated on the same chip as your cores。

 but other devices like disks and obviously， a keyboard are not going to be on the same chip as the cores。

 The main memory may or may not be on the same chip。

Here's another view of the platform level interrupt controller。

 I've shown the cores over here and the devices over here。

These arrows represent wires whereby a device can transmit a signal to the p to indicate that it。

Needs attention。 In other words， when an interrupt is signaled by the device。

 signal will go over the wire。 And the first thing it encounters inside the p is something called a gateway。

And the gateway could just be thought of as a single bit。When an interrupt arrives。

 a bit in the gateways is set to remember that that interrupt has happened。

 And that's called the source interrupt pin bit。 And at some point， that bit will get cleared。

 But while the bit is set， it means there is an interrupt pending。

 And it in the p will at that point， channel it to one of the core， one or more of the cores。 Now。

 the signal coming in。Can either be level sensitive or edge triggered。

 Perhaps you all already know these terms， but I'll discuss them in a second。But first。

 I want to talk about what happens when an interrupt occurs。 Okay so when an interrupt occurs。

 the source interrupt pending bit becomes one。And at that point。

 the p will notify all of the cores that are enabled for that particular device。

So the matrix of all the enabled cores will be consulted to determine which cores are going to be notified。

 Here's the matrix。 So for example， when an interrupt comes in for the keyboard。

 these two cores will be notified， but not this one。What does that notification mean， Well。

 it means an external interrupt will be raised in that core。 Now， remember， with risk 5。

 a core can deal with three kinds of asynchronous interrupts。 One is a timer interrupt。

 One is what's called a software interrupt。 and the third is an external interrupt。

 So the pl will cause an external interrupt to become pending in that core。

If that corps has interrupts enabled， then a trap will occur immediately。

 But if interrupts are disabled， then the trap can't occur at that time。But when the trap occurs。

 the trap processing will invoke a trap handler routine。

 So the trap handler code will start executing。 And the first thing it will do， presumably。

 is to interact with the p to claim the interrupt。 and this claim operation basically is the code telling the p that hey。

 I want that particular interrupt。 I accept it， I've got it。

 I'm claiming it as far as the other course that you told about this particular interrupt they don't get it。

 and this claim operation is done by reading a memory map register in the p so the trap handler will do a load from some word in the ps address space and that p will then return a particular value for that memory load。

The p will return the ID of the interrupting device as a result of this claim operation and we'll also at that point clear the source interrupt pending bit because the interrupt is being taken care of。

 I might clear it later， but that's in the details。What if there are multiple cores that are enabled。

 Only one should get the interrupt。 Okay， so only one claim will return the I D of the interrupting device。

 The click will make sure that the others get a0 when they read this memory map register。

So when they get a zero， they'll say， oh， I didn't get it， okay。

 I can go back to doing whatever I was doing， whereas the handler code in the core that actually got the ID will then go on to communicate with a device and take care of whatever operation is required。

So at that point， the handler code will run and deal with the device and then at some future time。

 the handler code is done and it can signal interrupt completion。

 that's another operation that it does by communicating to the p。

And once that interrupt is marked as completed， then the next interrupt from that device can occur。

 So the interrupt completion operation is done by。The core writing to a member map register in the clickque。

And then once the interrupt completion is done， the p will look at the source interrupt pending bit and see whether there is another pending interrupt from that same device。

 And in fact， devices is requesting another interrupt or when that device is requesting another interrupt。

 and the gateway bit is set again。 Then the p will once again signal another interrupt。

 and the process will repeat。Now， I want to describe what level sensitive and edge triggered mean for those of you who are not electrical engineers。

I'm talking about the signal that travels along this wire from the device to the gateway。

In the case of a level sensitive signal， we see that over time， the wire is low carrying a zero。

 and then it rises at some point and has a one and then later falls。

What the p will do is check the value of that wire。 If it's high。

 it will cause an interrupt when it checks。 Okay， so whenever the handler completes its operation。

 it will check this wire。 And if it's high， it will cause an interrupt to be sent to one of the cores。

 The handler will execute and at some point will complete the operation。

 will complete the processing of that interrupt。 and at that point。

 the p will check again to see whether the。Wire is high or not。 And if it's high again or still high。

 doesn't matter what happened in the middle here。 But if it's high at that point。

 then the p will signal another interrupt。 And then the handler code will run and complete。

 And then once again， the p will check。 And in the third case， it finds out that it's low。

 So no interrupt is signaled at this time。Now， in the case of an edge triggered signal。

 we have the signal going from low to high。 and what the p is watching for is that transition when it goes from low to high and doesn't really care too much about when it goes from high back to low。

 and the rising edge is what signals the interrupt。

And there are really two options or two variations on the gateway。 In one case。

 the gateway has a single bit， and the rising edge will set that bit to one。

 and that will then cause the interrupt。 and that bit will stay set at one until the handler completes。

 And if there are additional rising edges， those will be ignored。 But at some point。

 the handler will signal it the processing is complete。 And at that point， the p will clear the bit。

 and then the next edge can set the bit and cause another interrupt。In the second option。

 the gateway contains a counter， and the idea with this counter is that each rising edge will increment the counter。

 So we're keeping count of how many interrupt signals have come in from the device。

And then each time the handler claims an interrupt， then the p will decrement the counter。

 And then once the handler indicates that the handling of the interrupt is complete。

 the p will then take a look at the counter。 And if it's still positive。

 the p will immediately signal another interrupt， otherwise it will just wait until a rising edge causes a counter to increment from 0 to 1。

Next， let's get into some of the details and complications that arise with the pque。First of all。

 devices are numbered， starting at one and going up to 1023。

The number zero is used for no device at all。Next， each core can contain more than one heart or hardware thread。

The core might be a superscalealar core， or sometimes we say， simultaneous multi threading。

And the idea is the cores running two threads simultaneously。

Another thing is the core in risk five can be executing in machine mode， supervisor mode， user mode。

 the spec for the pL also talks about hypervisor mode。

But the interrupt will be sent to a particular mode。 Okay， so it may be sent to supervisor mode。

 or it may be sent to machine mode。And we call these things target， so you know。

 each heart is a separate target and each mode is a separate target within that。

 and the specification can deal with up to 15782 different targets numbered with numbers。Now。

 the specification goes up to these numbers， 1023 and 15，7，81。

 although a particular implementation may not be able to handle quite that many devices or targets。

Okay， next each。External device that can generate and interrupt is assigned a priority。

 Some are high priority devices， and some are low priority devices。

We want to assign a high priority number， a large value to a device that we want to have serviced immediately。

And others are very low priority。 Typically， slow devices have low priority。 You know， a keyboard。

 for example， doesn't need a super high priority because people just can't type very fast。

 but a rotating disk might need a very high priority if you are going to try to start another read operation before the disk spins all the way around。

 If you don't start the operation soon enough on the same track。

 the disk may have to do a full rotation to get back to the right spot。Each core， well。

 I really should say target。 So each one of these targets is assigned a threshold。 Okay。

 and here's the key。A device will only interrupt a core if the device priority exceeds the core's threshold。

Next， let's talk about how a core controls the platform level interrupt controller。

It does it by reading and writing to memory mapped I O registers。

 so the p will occupy a number of bytes in the physical address space of the processor and a core can do loads and stores to addresses within that range of memory。

 so called memory mapped registers to send or receive data to and from the p。First of all。

 we have 123 words of 4 bytes each that are used to store the device priorities。

 these are initialized at startup and we can set the priorities of all the devices by writing or doing a store into these particular locations。

We also have the priority thresholds for each of the targets。 So we have a bunch of words。

 one for each possible target。 And then we also have that big bit matrix，1023 devices times。

15782 targets， That's a bunch of bits。 So during initialization。These。

Memory locations will be written into to basically configure we might even say program the platform level interrupt controller。

 although I don't really like to use the word program unless there's actual code being executed and the platform level interrupt controller is not executing any code by any stretch of imagination。

Then。We have the pending bits。 So this is allows a core to query to see which devices currently have a pending bit。

And then finally， we have， and this is probably the most important one。 These are the claim words。

 So for each target there is a word。And you could either load or store to this location。

And what the core will do is a load to the addresses associated with that target to claim an interrupt。

 So when an external interrupt is signaled on a particular core。

 that core will load from the word that corresponds to it。 a 4 byte value。

 and that will be the I D of the device that is requesting an interrupt or it might be0。

 if some other core got to that interrupt first。And this same word is also used to do the complete operation。

 So that's done by storing into the word。 And in that case， we store the。Id of the device。

 whose interrupt we have just completed。A core might be handling several interrupts simultaneously。

 and it can claim several and complete several independently。Okay。

 so all told these memory map locations are mapped out into a range of 64 megabytes。

 It's really quite large of the physical address space。

 There are a lot of reserved bits or unused bits and the actual mapping I'm not going to go into too much in this video。

Next， let's look at how the platform level interrupt controller is implemented in our system。

We're talking about the X36 kernel， and that will be run on Kimu， which is an emulator。

So the p is not actually implemented physically。 it's simply virtually emulated by chemo。

The number of cores in XV6 is determined by this constant in CPU， which happens to be 8。

 so we have eight cores， and cheu is only going to be able to send the interrupts to machine mode or supervisor mode。

And so with two different modes and  eight cores， we have 16 different targets。

 and they are numbered as shown here。And our implementation of X V6。

 we are not going to use machine interrupts at all。

 All the interrupts will happen in supervisor mode。Cemo implements。Two devices。

1 is the Vir Iio disc device， and the other is the U art device。

 and Kimma will give these numbers 1 and 10。So during the initialization phase。

The code will set the priority of both these devices to one。And then for each core。

 it will set the cores threshold to0。 so the threshold won't stop any particular interrupt from getting through。

And we will also enable the bit， set the enable bit for both the devices。

 So this means that any device can interrupt any core。Or more precisely， when a device。

Is ready for an interrupt when it signals and interrupt， all cores will have an interrupt signal。

The benefit of signaling loss of cores when you have an interrupt is that the first core that is free will get to it and take care of it。

 And so it will presumably get serviced more quickly。

 If other cores are busy and can't claim the interrupt， then they won't get it。

 but the one that can claim it first is the one that we want to actually get it。Okay。

 now we're ready to take a look at the code in X V6。 And as you can see， it's pretty short。

 we're looking at the code in click do C。 and we have four routines。We have two for initialization。

 and then one for the claim and one for the complete operation。

Pick an it is executed only once by core 0 during start。

 And remember what we need to do for initialization。

 we need to set the priority of both devices to one。 So that's what's going on here。

Click is the address of the clicks memory map region。

 And then we add this to get to the particular register for the priority for this device and that device。

 And we just store a one into those locations。And so that's done once by core0 and clicking it heart is executed once for each core。

 So the first thing it does is determine what core it's running on so it gets the CPU ID。

And then we need to do two operations。We need to。And set the enable bit in the enable matrix to one for both of the devices for this particular core。

 And then we need to set this core threshold to 0。 So that's what's going on。

Here in the we use this macro click S enable。To get the address for the word we need to write to update the enable matrix。

 So what we're going to do is write into the enable matrix for this particular core。

And we're going to write into it。A word。 And that word will contain two，1 bits。

1 in position 10 for the Uar and one in position one for the disk。

 And so that will set the enable bits so that these two devices are allowed to。

Interrupt this particular core。 And so we write that。

 And then we use this other macro here to determine the memory mapped I O address for the priority register。

 And at this point， we store 0 into that word to set the priority threshold for this particular core to be0。

So these two macros click S enable and click S priority are coming from memory layout do H。

 and we can see them down here。Plick is the starting address for the member map region for the p。

And here we have a number of macros that aren't actually used in the code。

 We only use the S enable S priority and S claim。 We don't use the machine mode。Macros。

 and so each one of these just gives the address for this particular course register。

 the enable register， the priority register and the claim register。By the way。

 when I was looking at the code that creates the virtual ladderer space for the kernel。

 I noticed that we only memory map four mega bytes and not 64 megabytes。

 I think that's actually an error in the code doesn't cause any harm， but I wanted to point that out。

Okay， so we have these two functions。When a。Handler for some interrupt is activated。

 The function device interrupt or dev enter will be called。

 and it will immediately invoke this p claim。 And that basically asks the p。

 which device is interrupted。 And the p will then return the number of that device。

 And so here we see that going on。Click claim for this particular core is the location of the claim register。

 And if the p。Once the p will return the device IDd， and that will be saved here。

If some other corps got to deplelect first and claimed the interrupt before this particular core。

 then this particular load from that memory map register will return 0。

In the dev enter or the device interrupt function。 if we get something that's non0。

 well we'll either get a1 to indicate it's the U art or tent to indicate it's the disk。

 and then we'll call the appropriate handler routine for that device。 But if we get a0。

 we immediately return。 So one core will handle the interrupt and other cores that get 0 will immediately return。

 go back to doing whatever they were doing。If we do service the device， that is。

 if we get something that's non zero， then the devb enter the device interrupt function will then end by calling the click complete function。

 click complete will then store into the same location， right， the same location。

 The code for the interrupt that it is complete。Okay， that's it for the p。

 I hope you found that interesting。 I will see you in the next video。



![](img/da1cf8f6bcaa577091b6c9a933918bbd_2.png)