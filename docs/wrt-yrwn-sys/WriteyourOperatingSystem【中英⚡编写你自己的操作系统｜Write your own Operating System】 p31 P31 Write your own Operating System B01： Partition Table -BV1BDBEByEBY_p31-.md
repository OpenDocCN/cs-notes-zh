# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p31 P31 Write your own Operating System B01： Partition Table -BV1BDBEByEBY_p31-

Hello and welcome to the first part of Appendix B。OfOf。Tial on writing your own operating system。Now。

 in this tutorial， we will talk about。A partition table。

Because yeah you have access to the hard drive， but you can just read it in a very raw way。

 you can only get raw data。And in practice， you will want to put a file system between your。

Between what you are doing and。The hard drive。So that you don't have to deal with questions like。

Which sector has this data， Which sector has this data， so。

Yeah and before we can write a file system， we first have to look at the partition tables。嗯。Yeah。

 because you can have just multiple partitions on a hard drive and。

That is important for the file system， so we need to do this first。Yeah。

 and we will be using the MS dose partition table system because this is。

As far as I know this is really the standard nowadays。

 even on Linux systems because yeah it's a way Windows does it and if you used anything else in that you wouldn't be compatible to Windows。

And yeah， then you could not do a boot with windows and I don't think it would be a good idea to use a different partition table system。

Yeah， but the MSS partition tables are really simple。

I don't think we will need a lot of time for this。So。I mean。

 you are already able to read raw sectors from the hard drive， right？And。Yeah。

 the master Bo record is just the sector number zero， okay？So。When we wrote that。

It's a system to read and write， then we。Wrote HTTP， colon s s and so on into this。

 but this isn't a valid masterbo record。So。A master boot record looks like this。It has 440。Ws for。

That a put。A boot loader， what I call a pre boot loader。Some people call it the bootstrap。And。Yeah。

 when you boot， this is just sector0 is just red from the hard drive and。Then。

The bias just jumps into that。 So there needs to be some。Righthite coat。And down。But yeah。

 440 bytes is really not enough， so that is you why this code would then proceed reading the partition table and selecting the good partition and loading the real good loader from there。

Okay， so after these 440 bytes， you have four more bytes。Which us。It's called a signature。

 We are not going to use that， really。Then， we have。2 bytes， which are unused。嗯。

Then we have four partition table entries。And each of them is 16 bytes long。And then in the end。

 we have two metric partss。Which way around was it？😔，Was it 55 AA or AA55 doesn't matter。嗯你。It's 5，5。

88。こ。Okay， this is how the master boot track looks。

And yeah the so we are not really interested in this。 We will just leave this the way it is。

These we will leave the way they are， we will leave this the way it is we will just check that this is correct。

And these are really the things that we are interested in。And how do they look？Well。First。

 you have one byte which tells you whether the device is put or not。And yeah， of course。

 you can have multiple installations of Linux， you can dual boot with windows and whatnot。嗯。

But only one of the devices is allowed to be bootable， and that is the designated boot drive。And。

Yeah。The bootloader in there is then supposed to have its own ways of deal of finding out。

What's with the other parts and other drives so。So we will only have one if any。嗯。

Partition with this set to0 x80。お。お。0 x 18 means it's putable and 0 x00 means it's not putable。Okay。

 then you have three more bytes。Which is a。The cylinder head and sector of the start of the partition。

 but as I've told you， yeah this isn't really what is used anymore today so。

F disk sets these values correctly， but we are not going to use them。

So this is a CHS address of the start of the partition。Then， we have one by。So these are three。

 theres is one byte with an ID。嗯。I think this ID tells you which。

Operating system has been used to format the hard drive。 So I think we will be seeing。0 x。83。

 I think。😔，Which stands for Linux。Then， we'll have。3 more bys， which。嗯。

Are the CHS address of the end。Offi of partition。And then after that。

 we have the data that we are really interested in。To 32 bit integers。Which give us the ABA address。

Offf the start。Ops of partition and the ABA address。Not in the AB address or length。Of the partition。

O。So yeah， that's not too complicated， I think。然。Yeah， let's just program this。

 I think this will be quite easy， but I will go into。



![](img/23ba9a987d424bfd3c37dac6d93f4b57_1.png)

I will go into one thing。So I have downloaded。😔，A life disk of tiny core Linux。And before we proceed。

 I just want to。Wait， I just want to prepare a hard drive。😔，That we've created in Vitrobox。

So I'm going to the drives here。😔，And select tiny car as Bo medium。And by the way， we should really。

Stop writing to the hard drive， because this would break the。Partetition。T it again。Okay。

 in tiny calm。First， I will start FD。😔，So， I will create。😔，APition table。Then I create a partition。

Primary partition， we will not go into extended partitions， by the way。

 so I'm just going to create two primary partitions。Number one。

 which is going to be the first entry there。Starting at a first。Use was the sector。

And I'll have it go to sector number 130。😔，And then I will make another partition， primary number2。😔。

131 is the first。😔，And 261 is ales。😔，7点钟。Okay。Now， I've read the。Yeah， no I have。

Written this partition table to the disc。嗯。And yeah， while we are at it， I will also create two。

File systems。But tiny call。😔，Doesn't have。It doesn't have the。The appropriate programs to to create。

Fat。File systems， so。😔，So I'm going to install the package does FS tools。Okay。

Now I'm going to make two。😔，嗯。Entries。So now we have a file system。We've had。

Dash F 32 because we want to use F 32。On the first partition。And the second partition。O。

So now I'm going to mount these partitions。😔，And just create two files。😔，Okay， so。

Now I'm going to reboot。So what we have now is we have a hard drive。

 which contains a valid partition table and。G up。There are。Two fat file systems now。

 which both have two files in them。Which we will be looking at in the next part of the appendix B。So。

Yeah。Yeah。Okay。Yeah。嗯，是的。个。嗯。Yeah， so as I've said。😔。

The partition table entry is the one on the down is the lower one of these diagrams。

So what do we have in there？So we have subputable flag。😔，By。The head。

 sector and cylinder of the start of the partition。

The start sector only is  six bits and a cylinder is 10 bits， so I'm going to do it this way。Okay。

Then the partition ID。And down here is an interesting part。So electric block address of the start。

And the links。O。And then we'll have a structure for a master boot record。😔，Right。

So 440 bys for the boot loader then。😔，32 B signature。Which we are going to ignore。😔，Two unused bys。

Then for partition table entries。And the metric number in the end。Okay。

So this is already all we have to do in the。In the head of fire。Yeah。你一下。K以。No。没可爱。😔，Yeah you。Okay。

看了。Yeah。Yeah。对。Although， actually。Yeah， yeah， I will do it。そう。So as a primary slave， this one is。😔。

The bus where our heart tro is。😔，O。So。あのよ。So this is supposed to show us the partitions。😔。

That we've just created。So in here。😔，I will instantiate this masterbo record structure here。

And then read from the hard drive into that。Sector number0。嗯。To the masterboard record。Okay。

 so this should load the master boot record。😔，嗯ん。So， this should print。😔，The file system entries。

And then I am afraid I just overgrte the。😔。

![](img/23ba9a987d424bfd3c37dac6d93f4b57_3.png)

Paltition table。😔，Because I didn't compare before running that。Okay。



![](img/23ba9a987d424bfd3c37dac6d93f4b57_5.png)

![](img/23ba9a987d424bfd3c37dac6d93f4b57_6.png)

Okay， so here we have the master double record。😔，嗯。



![](img/23ba9a987d424bfd3c37dac6d93f4b57_8.png)

![](img/23ba9a987d424bfd3c37dac6d93f4b57_9.png)

So I found the mistake was actually easier than I thought。

I hadn't set this attribute packed here in the partition table entry and must have a record。

 And yeah， if you don't do that， then the compiler might just decide to。

To move these objects around a bit in the Ram and then increasing the。

Size of the partition table entries and masterboard record。

And this attribute pact actually tells the compiler not to do that。So yeah， because of that。

 the size of masterboard record was just wrong。呃。Probably was just。Too large。 And then。



![](img/23ba9a987d424bfd3c37dac6d93f4b57_11.png)

I guess I didn't read anything。Yeah， whatever。So if we compile this now。あ。You can now see here。

 what do we have？😔，This is not bootable。 The first partition， it starts at。At cycle head sector 0，1。

0，1，0，0。It's。Yeah， as I've said。I D 83 for Linux。When。嗯。

Cylinder had and sector of the end of the file， the end of the。Partition。 And then here，1，2，3。

4 bys for the。For the sector number of the start of the partition。And you might be wondering。

 why is this3 F here。

![](img/23ba9a987d424bfd3c37dac6d93f4b57_13.png)

Yeah， this is just there are just a few sectors reserved in front。And。

I actually don't exactly know why， but。

![](img/23ba9a987d424bfd3c37dac6d93f4b57_15.png)

That's the way it is， so。63 sectors in front of the first partition are just free。Yeah， and。

This is a length of the partition， and here's the next partition。It's。So， this is the。Boot flag。

 It's not bootable。Cylinder head and sector of the。Start off the second partition 83 again for Linux。

人。1，2，3， but it's for the end of the。Partition， and then。1，2，3，4 bys4。

The start of the partition in ABA addresses and links。Of the partition also in A V A addresses。

 And here in the end。So two entries are just all zeros。 So invalid entries。

AndBecause we only have two partitions。Created。 And then here in the end， we have this 5，5 A A。



![](img/23ba9a987d424bfd3c37dac6d93f4b57_17.png)

The the metric number， okay。So。So now we have the masterboard Record。😔，So。Now we can look at that。

Yeah。Yes。Okay， and。Yeah， in the end。Yeah。I will iterate through these。😔，Partetition tables。Yeah。Yeah。

Yeah。Yeah。

![](img/23ba9a987d424bfd3c37dac6d93f4b57_19.png)

So what do we have now。Yeah， okay。First partition is myput type 83。😔。

Partrtition 1 is not go to type 83。那就是。Yeah， three。Type  zero。

 I think type  zero should mean should probably say。That there is no partition。And yeah。

 the really interesting。

![](img/23ba9a987d424bfd3c37dac6d93f4b57_21.png)

系啊。Part here， now is。In this partition table entries this start A BA。 This is going to be the offset。

Which we have to add。嗯。On the。Inside the file system。

 you know the fat file system will always add this value to the offsets that it's reading and yeah so。

Yeah， this is all I wanted to show you in this video， so now you can read the masterbo Record。

 you get the partition table out and the important part is you get this offset which you really。

 really need for reading from the partitions。嗯。And that is what we are going to do next time。

And then we will take this value， and。And then iterate through the file system that we've created with tiny Quaux now。

Okay， so yeah， that's all for today。As I've set to tune in next time。

When we examine this fat file system。Don't forget to subscribe so that you don't miss that next video。

 hit like if you liked this video。Yeah， actually， I didn't like it that much because its it was quite primitive what we did。

 and I think next time will be much more interesting when we really start。

Seeing directories and files and file contents and stuff。So， yeah。Whatever， if you liked it。

 you can hit like， but。I understand， if you don't。So see you next time， right？



![](img/23ba9a987d424bfd3c37dac6d93f4b57_23.png)