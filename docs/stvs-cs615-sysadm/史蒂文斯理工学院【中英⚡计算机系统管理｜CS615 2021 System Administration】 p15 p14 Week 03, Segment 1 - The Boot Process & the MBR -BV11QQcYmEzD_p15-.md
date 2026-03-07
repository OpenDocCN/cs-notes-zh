# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p15 p14 Week 03, Segment 1 - The Boot Process & the MBR -BV11QQcYmEzD_p15-

Hello and welcome back to CS615 System Administration。This is week 3 segment 1。

 and we're picking up where we left off in the last video when we talked about partitions。

In that video， we had discussed the operating system specific partitions for which we use tools like disk label and NePSSD。

 format and Omniio and Fs Linux。We also hinted at the difference between these partitions and so called bios partitions used by the master boot record or MR。

 which gets us to today's topic， the boot process on a higher level。

 as well as a fairly detailed look at the MR。So when we boot up a system。

 we likely see messages like these on the console。Here's a display of an netPSSD boot loader。

 As you can see， it is a bioOS boot loader， and it offers you an interactive menu to select different ways of booting。

If we let it time out without a selection， and it will simply begin the normal boot process in boot that B SD kernel。

 which generates these screen messages shown here， displaying the hardware as it initializes it。

At some point， then， it has control of to the in process， which we can see when the wood process。

 which is colors。In it， then continues the wood strapping process， mounting the fire system。

 bringing up networking and launching whatever demons the system is configured to start before leaving us with a login prompt。



![](img/bd28a4a5b60ba6b23bb4de4aa152e231_1.png)

So we can break down this process that we just saw into these individual steps。

Whening power on the physical server， what is the first thing that happens， Well。

 you may hear a series of beeps， which may indicate to you that there was a hardware failure of some sort。

 or you may not， if you're lucky。That is， before anything else。

 the system performs a power on self test， where checks for basic sanity of the world that theres some memory。

 A CPU， what storage devices may be present and which one a system is configured to boot from。

Once that's complete， the system will look for the so called first stage boot loader。Traditionally。

 that would mean looking for a specific signature and executable code in the first sector of the disk is supposed to boot off the boot sector。

You've probably heard the term MR or masterbure in this context。

 which is exactly what we're talking about here。This first stage boot loader may then hand of control to a second stage loader。

This might be needed because， as we will see in a minute。

 the first stage boot loader is necessarily very limited in size so that if you want to perform something more complex than a simple boot。

 you may find some special code somewhere else to jump to before you can even find and load the kernel in question。

Now， after the second stage boot loader， eventually you'll load your kernel。 Now。

 in the case of a virtual machine such as an AWs， there will be a special kernel。 for example。

 if you're using Zen for virtualization， you'd be booting the Dom0 hypervisor kernel。

All of these steps here are happening on the physical host， which is a worthwhile distinction。

 since after that colonel has booted。It would then start the respective guest domain。

 which goes for the same process。And loads its kernel， which then， as we saw in our opening sequence。

 initializes the hardware it finds。 Vir hardware， in this case。

So these last three steps here are thus happening within the virtual host in kernel space。

Before the kernel， hands off control to init or system D or whatever is used to start the various services。

If the system you're bringing up happens to be a web server。

 that application would then run bind the right network port and finally serve content。

These last few steps are still executing within the virtual host。

 but now are running in unprivileged mode or user space。So this is the simplified。

 complete boot process from power on to serving traffic。But today day。

 we only care about the first few steps when we look at how we even get to the kernelel。



![](img/bd28a4a5b60ba6b23bb4de4aa152e231_3.png)

So when you power on a physical server， this is what you might see First。

 This is an example of an American megaren by， the basic input output system。

 showing a successful power on self test。Normally， this would now simply jump into the boot sector of the configured boot disk。

 but it may also let you configure certain aspects。 That is。

 even though this piece of software is necessarily simple and still allows for some flexibility。



![](img/bd28a4a5b60ba6b23bb4de4aa152e231_5.png)

Since the bioos often sits on a read only memory chip on the motherboard and thus isn't quite so well soft。

 we don't call it software。It's harder to change， but it's not quite hardware。

 So we call it firmware instead。So this queen shows an example of a bio configuration menu。

 allowing us to select the boot order of devices， for example。

But the bio dates back to the CPM operating system from the 70s and was originally proprietary to IBM PCs。

 then reverse engineered by others， but not standardized and often specialized for a specific motherboard or other hardware。

The bio also had a few technical limitations， which we saw in our previous video。

 and we talked about the problem certain buyers had in addressing large discs。



![](img/bd28a4a5b60ba6b23bb4de4aa152e231_7.png)

So we now have the unified extensible firmware interface。

 which provides a modern and standardized way of interfacing between the operating system and the underlying firmware。

But as so often， it's important and useful to understand the history and how things were done in the olden days。

 which it turns out is still very frequently how things are done to day。

 such as for backwards compatibility reasons。Which is why we are now going to look not at U EF I。

 but instead as a traditional master boot record。Which the traditional buys expects to find in the first sector。

 the is and the first5 and the 12 bites of the Bud diskk。That's right。

 The masterwood record is only 512 B in size。Within these 512 by。

 we have to fit a fair bit of information， as well as the code needed to boot the system。

 So let's see what this looks like。At the end of the first sector， we expect to find the magic bits。

0， x 5，5 and 0 x A A。 The presence of these two buys indicates to the bias that this is a valid boot sector。

😊，The 64 bites right before hold the partition table。Now。

 this partition table is different from the partition table we discussed in our last video。

 This is the bio partition table， which describes which of as partitions the bios can see。

A bio partition table entry， then is 16 by in size。 so we can have exactly four of these partitions。

That is， a disc with an MR can have at most for biopartitions。

But we know that our operating system may want to carve up the disk into more than just four partitions if it needs to。

 and that alone illustrates the need for distinction between the bios and the O S partitions。That is。

 the buyer's part really only defines which parts the disk are located for a given operating system。

 What the operating system then does with that slice of the disks entirely up to it。

Remember that in our previous video， we showed that the BSD system used the D partition in their O disc label to reference the entire physical disk and the C partition to reference the part of the disk dedicated to this O。

This sea partition is effectively what we're defining here。

 and the oils can then create additional partitions therein。Anyway。

 so with two bytes for the magic number and 64 bytes for the partition table were left with 446 bys。

That is， everything needed to bootstrap the system needs to fit into these 446 bys here。

Which is why we are often talking about this being the stage 1 bootloader。

Is just enough code to bring up the system to a point where it can perhaps reach other sectors on the first track to then find more complex code to transfer control to。

That coat is then known as the stage 2 boot loader。

Gnu Grub is an example of a boot load earth that may contain multiple stages。But back to partitions。

 So we have a partition table consisting of 64 measly bites。

 leaving us with an even pinier 16 bys to describe the disc。How do we organize these 16 bytes。

The first bite tells us whether this partition is active or not。

Then we get three bys to address the first sector of the disc using the cylinder head sector addressing schema we discussed in the previous video。

These three bytes are defined like so。The first bite， and thenice the hit。At 8 B。

 that means we can address at most 256 heads， which was a limitation we had previously mentioned。Now。

 the second bite is a bit less straightforward， rather than giving us a whole bite for the sector。

 We only get 6 Bs with the first two bits of this bite being reserved for the highs of the cylinder address。

So the largest sector number we can address is thus 64。And then in the third bite。

 we get 8 B for the cylinder address。 plus the 2 bit stashed and by two above。

 We get 10 B for the cylinder， meaning a max of 1024。After this。

 we get one by to identify the partition type for the operating system in question， Ne BSD or Linux。

 for example。Then we get another three bites for the C H S address of the last sector。

Which we also chop up just like before。But now， as recorded with the limitations we have here。

 we couldn't address discs above a certain by tod in that pretty small limit。

So we had changed our addressing schema to use logical block addressing。

So here we get4 bys for the LBA of the first sector。And 4 Bs for the last sector。

So now we have two ways of the dressing sectors。 How do we get from one to the other。

We can start with the L B A of the address。And then determine the C。

 H and S values from that using this formula。And then use those values here。Okay。

 so now that we know what these 16 bys look like， we should be able to create a boot sector with a valid partition table entry for any disk simply by writing the required bys to the correct offsets。

 right。Let's give it a try。We start out again， as usual。

 with a new Ne BSD instance and then create a new volume to play around with。

Let's make it three get concise， this time。We wait for the instance to come up。And attach the volume。

 using another shell function to save ourselves some typing。Okay。Let's log in， on an instance。

And inspect the disks by a D message。There's our root disk and our newly attached disk， X， P D1。

Let's look at the bias' partition table of the root disk， via the F disc command。

We see the logical geometry of the drive， as well as the bios geometrytry。

The partition table shows the first part to be of tight Ne B SD and active and starts at Se 2048 and with a show clinnder head sector addresses。

So F disc shows us all this information。But what does it actually look like。

Let's use the D D command to retrieve the first 512 bys of the disk and display them as hes。

By other hex dumpump utility。Here一个。So all these bys there。Are the actual boot code。

With the first part being defined。And these 16 bites over here。And all the way at the end here。

We see the MR signature， Phi，5 AA。So let's take a look at the first partition alone。

We know it's 16 B in size。At offset 4，4，6。So， here it is。

And so these 16 bytes describe the first partition entry shown by F disk like this。Okay， so far。

 so good。Now， what does our second disk look like？F disc shows that there are no petitions defined。

No active partition。If we look at the bites on the drive。Then， no surprise。They're all zeroes。Okay。

 so how do we turn this。Into this。Let's start at the beginning。Well。The end， I suppose。

Note how E thissk tells us that the partition table here is invalid because there is no magic number at the end of the sector。

Let's fix that。We use printf to write the hex bits 5，5 A A to offset 5，10 of def X， B D1。Okay。

 so now we note that F diskk no longer complains about the partition table being invalid。

 but it still says that there is no active partition。So let's create a net BSD partition here。

For that， we need to get a partition type identifier for netPSD。Which is。169。What is 169 in hex。

 Let's use the B C tool for that。Okay， a9 is the heggx value we want。Let's write that to offset 4，50。

And then let's mark this partition as active。By writing0 x 80 to offset 4，4，6。Okay。

Let's see what F diskk says now。There。Partition0 is now a net BSD partition and is marked active。

But we're still missing the size and definition of this partition。As we see here。

 the cylinder head sector definitions are 0。So， let's define those。The beginning of this partition。

Is sector 2048， because the entire first track is often reserved for additional bootstrap code。

 as we mentioned。So we can use our formula to calculate the CHS address from the LBA address with our LB address in this case being 2048。

So 2048 divided by 160065 is obviously 0， which will be our cylinder value。

We then have a remainder of 2048。So let's divide that by the number of sectors per track。

Which gets us 32。32 decimal。Is 20 hes。So our head of value is 20 hes。Finally。The sector value。

Is the remainder plus 1。So we can now write these three bytes。Heads。Sector and cylinders。To offset 4。

4，7 for the starting sector。Let's check。There we go， starting sector at cylinder 0， Head 32。

 sector 33。So now we need the last sector。We know we have a total of this many sectors。

 but the first sector contains the M MR here。 So let's subtract that。

And divided by the number of sectors per cylinder to give us the cylinder addresss number in decimal。

391， in this case。The remainder。Here's 1，0，0，4，0。Which we now。

Divide by the number of sectors per track per the bio，63。Giving us decimal 159。

So our headers buy it in hes。Is then。9， F。Now， the value for our sectors is 24 decimal。But， remember。

We now need to puzzle together the bits for the cylinder and sector。

So we need to convert this to binary。Which gives us 1，1，0，0，0 for the header bits。

For the cylinder now， we need 391 in binary。Which looks like this。

So now we can combine the binary bits back to hex。For this。

 we now grab the first two high order bits of the cylinder number。0 and one， in this case。

Followed by the six Bs representing the sector。Giving us。58 hexadeciimmal。

And the last8pis of the cylinder number。Converted to hex。Is 87。So now we have our C， H S bytes，9， F。

5，8 and 8，7。Let's write those to offset 4，5，1。OK。What does F diskk tell us。Looks good so far。

We have a starting C HS address， and an ending C HS。But our MR also requires the LBA addresses。

 So let's go ahead and add those。We know the LBA of the starting address is 2048。Which is 800 in hes。

But the LBA field needs4 bys， and it uses little Indian by ordering。So， we turn0，800。In2。0，8，0，0。

And ride those bys。To offset 454。The last sector， then， is the total number of sectors。Minus 2048。

Inhas。And converted to least significant bit first。And written to offset 458。And now。

 F diskk shows us a proper part with the right size and the right addresses。But， of course。

 theres an easier way to do this。Let's wipe out the MR by overriding it with zeros。There。All zeros。

Then we can use F disk to specify that we want to activate partition 0 with a specification of 1169 for netPSSD beginning at sector 2048。

And。Off the given size。Which then。Looks just like we had manually written to the disk。

This shows that there really is no magic to any of the tools we use to manipulate our discs。

 It's all just a question of knowing which bits to ride to which place。That。

 and that is rather useful to be able to use D D， Hext and PC to manipulate and write individual bits and bys。

All right， let's recap。 Remember， we started out discussing the typical boot sequence。

We said that it all starts with some basic firmware， which may be the bio or U EFI， etc ce。

Which may perform a post check。And initialize the hardware it sees before it transfers execution to the first stage boot loader。

 such as the M R， which then may continue the bootstping process by hand control to the second stage boot loader。

 which then loads the kernel， which then ultimately hence control off to a user and process。

 like in it。Now， one thing to note here is that in virtualized hardware， some of these steps repeat。

 some may be skipped， and some may be simulated， as our virtual host initializes virtual hardware as it bootss up。

But ultimately， we arrive at a running system。And we are looking at the wood presses here and having understood the MB item detail。

Let's consider some additional exercises for you。AWS instances allow you to get the output sent to the virtual Cer console。

Different operating systems display different levels of detail。 And， of course。

 the boot process is different for each O S。So a good exercise for you would be to compare the output of different operating systems。

Spin up a few instances。 say an net B SD， free BSD， Uuntu Fiora or Omniioos instance。

 and compare the output of the console。 in particular。

 pay attention to the file system or disk specific messages。

 Make sure you understand what the output means。I've put sample output into individual files at this URL。

 but I still also recommend that you run the AWS commands to get more familiar with that part。Next。

I want you to think about the security of the process。As we've seen。

 there are several layers to this process and different pieces of software。

 The firmware from the rom on the motherboard， the bits written to the boot sector that we nominate don't think about。

How can we remain assured that nobody has temperered with a software or firmware。

The concept of trusted computing comes into play here。 look up the terms remote attation。

 for example， or secure boot in this context。Finally。

 you may have noticed that we still haven't gotten to the point where we're actually using the file system or what that might actually look like。

 Let's fix that in our next video， shall we。All right， that's it for today。

 See you next time and thanks for watching G。

![](img/bd28a4a5b60ba6b23bb4de4aa152e231_9.png)