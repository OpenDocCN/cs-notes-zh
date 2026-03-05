# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p32 P32 Write your own Operating System B02： File Allocation Table (FAT32) -BV1BDBEByEBY_p32-

Hello and welcome to the second part of the Appendix B to the tutorial and writing your own operating system。

Now， in this part， we will be looking at the file allocation table file system that。Microsoft used。😔。

嗯。Yeah， I don't think they still use that， but。I mean， today， they have N TF S and stuff， but。

You've had to still。A relevant file system， I guess。So。We'll be just using that and have created the。

The two file systems in our virtual machine as F。So。

 so today we will actually be going into directories and files on that directory， so。

So then we aren't talking about sectors anymore more than we are talking about files and directories and that's。

Also a big step， I think， because that gives us a nice abstraction from this raw data that the hard drive gives us。

Okay， so。Yeah， how does that look the。

![](img/91143d54e154175360703749a1d405ee_1.png)

The hard drive， I' write Ill draw it like this。

![](img/91143d54e154175360703749a1d405ee_3.png)

Looks kind of like this， so。Here in the first sector we have the masterbo record。

Which contains the partition table。And that partition table gives us an offset。

Where the partition begins okay？And then in the first sector of that partition。

We find a so called bias parameter block。Okay， and that contains several informations about the structure of the。

Partition， Okay， so let's say is a partition。Start here and here。So。

A F file system basically contains three sections。First， a reserved section。

 which which contains the bias parameter block。 So the bias parameter block is inside that reserve section。

Then we have the second section， which。Contains the so called file allocation table。

And then the third section is where the。Yeah， well the directory entries are the file the file entries inside the directories and the data of the files。

 So this is the data section。Okay， so let's see。So。Yeah， where to start。😔，嗯。The thing is。

When you write files， okay， say。Here's already some data and here's some data。

Because you've written something here， here， here， here， and you've deleted this。

 you've deleted this， now it looks like this。And now you want to write something else。

Then you want to be able to write the first part of it up here again and then continue here。

So something like a linked list， but。So you need to be able to jump around in the data section and that is actually organized inside the file allocation table。

Okay， so。The file allocation table just contains these references from one cluster to the next。Yeah。

 we'll go into that later。So the first thing that we really need to address is this bioos parameter block。

Which contains a lot of data。嗯。First， it contains three bytes of just executable code。Which is。Yeah。

 a jump instruction that jumps behind this bias parameter block。

Because the booting process process might decide to jump into this location。

And then if you didn't have this jump。Instruction， it would try to execute the data that is here。

 And that's not a good idea， you know。Because you don't know what's in there and it's probably not even legal instructions。

You cannot execute data， you know， this is data。I mean， the processor can execute it。

 but it shouldn't， right？Okay， so then so this is three bytes then we have。

8ight bytes for the name of the software that formatted the drive。In our case， this will be MKFS。

We fat。Because that's the tool that we've used。Then we have two bys， which tell us how many bites。

Are they per sector？Then we have。😔，8 bys。Which tell us how many sectors are there in a cluster？😔。

You know， the file system。Says okay I don't know it's probably around eight or so。

 so eight sectors are one cluster and then all four kilobytes。

 you will have such a reference okay you don't want to have such a reference。Every 512 bytes。

 if you had only one sector per cluster。So。So， a fire。Must always。Spend， at least。

Sectors per cluster times rights per sector， right okay。So then you have multiple sectors， which。

Grouped together as a cluster。And yeah so。No。So if I must always。Alloccate full clusters， okay。

So then you a file is at least four kilobys large or something。

 the size on the disk is always a multiple of4 kilobytes then if this was8 for example。

And that is one bite。Then we have two bytes that tell us how many reserve detectors are there。😔。

And that's interesting because。This year whats the point that we got from the partition table。

And now this reserved value gives us a pointer from the partition table from the。

From the start of the partition to the fat。Okay。Then we have one byte telling us how many copies of the file allocation table are there。

😔，Because if one of them breaks， you want to have a backup。

Usually you have just two copies of this table。And then you will find the two in here。

And then you get some， yes， really some garbage two pipes which tell you how many files or how many entries are in the root directory。

 this isn't used nowadays anymore so。I'll just ignore that， I'll just write the tools out。

When 2 by for the total。Count of sectors， Yeah， whatever。Then。1 by for the media type。

Which tells us is this a hard drive as it are。A floppy disk or whatever。😔，Then。Two bys telling us。

How many sectors does。This fat contain。 but this was from F 16。

So this will just be zero in our cases。So I'm going to skip this also again。

Then two bytes for sectors per track， this has to do with the geometry of the hard drive with the CHS addressing。

That was used in ancient times。 this will be zero， I guess。😔，Yeah， that's not interesting for us。

 at least。啊。Second last put track。😔，Have count。And four bytes for hidden sectors。😔，I'm not sure。

 It sounds like we should。We should add that somewhere。 but yeah， in the code that I found online。

 they didn't。 So whatever we are。We'll just assume that we don't hit that。And个。

For it's for total sector count。Okay， this is also not really relevant for us。😔。

When we only want to read the data。So the steps that we really need is。Here the size of the clusters。

😔，When this point are here to the fat。Then how many copies of the F do we have。O now呃。Yeah。

 this is the end of the。Of the bio parameter block of F 12 and F 16。Yeah， no。

 it's not the end of the bio parametermeter block， but this is a common part of the bio parametermeter blocks。

 okay。So Fed 12， F 16 and F32 just have different。嗯。Extent to this。

 but this is common in all of them。嗯。So。嗯。我了。The next things in the bio parametermeter block are。

4our bys for the table size。This is really interesting。 This tells us how many。

 how many sectors are in。Each of these tables。 so fat count multiplied with table size， gives us。

This point。Okay， so。So the offset from the partition table plus。

The reserve count plus fat count multiplied with table size， gives us the。

Offset of this data section。OkayAnd that's really interesting， that's where we want to get into。Okay。

 then we have two bytes with some flags， two bytes with some version。😔。

Then4 bytes for the root cluster， This is really interesting。Because this gives us。嗯。So root cluster。

Multiplied with sectors per cluster。Gives us the offset from here to。The root directory。

 you know C colon backlash。啊， whatever待吧。If we are talking about Windows terms。Okay。

And that's where that is really the point where you stuck your iteration when you iterate through the。

Through the file system。Okay， then you have two mobiles for。😔，Some information。😔，2 bys with。

With a pointer to some backup。Back up。Yes。じ嗯。Operating system， I don't know。 and I don't care。

Then we have 12 lights。That are just reserved and have to be zero。Then some drive number， one bite。😔。

One reserved。One called root signature。发或者 volumee ID。I think that's a Ut。

 a unique identifier for the hard drive。欢你。11 bys for the volume label。You know。

 when you format a hard drive， then you can give it。The name， and I think that's where that goes。And。

8 for fat type label。你。ok。So that's a lot and we are。Not really interested in most of them。

So from the extended data， these two other ones that we are interested in。

So these things that have marked， they give us the pointer down here， down here。

 and then into the root directory。Now， how does such a directory look like？😔。

So a directory is also a cluster。 So it's， I don't know for kilobytes or something。嗯。And。Yeah。

 they are just。诶。Yeah， every sector in that。Contains just 16。Yeah， 16 entries。So。

The point is that you get here。This to a sector Okay， and this sector。Contains 16 directory entries。

And how do these directory entries look like？

![](img/91143d54e154175360703749a1d405ee_5.png)

Why do we have。Okay， such a directory entry looks like this。It has。8 by for a name。What's her name？

Three bys for an next tension。Then。One byte for attributes。Like for example， is this file hidden。

 is it a directory or what？Then one reserved by it。😔，Then， you have。7 by。For some date and time in。

You know the creation date of the file and last access and that stuff。Then， you have。

Two bys with cluster number。So a cluster number in F 32 contains is。Four bytes long。

 and these are the high bytes of that。Then four more bytes for some time in。So。

These are the last right access。Then the low bites of the class now。And then，4 by for the size。



![](img/91143d54e154175360703749a1d405ee_7.png)

Of the fire。So we might be interested in the name and the extension。

 the attributes tell us if it's a directory or a file。And if it's hidden and stuff。And also。

 the cluster， low and high。Yeah， and I think the size is also relevant。 I think these time things。

Yeah。You can look that up yourself， I don't want to go into that。嗯。But yeah， so。u。

You go to the route directories the way I told you before。

 and then you just read that sector and you get 16 entries that look like this。And yeah。

 then you just， you can just examine the name of the entry。Which would be a file name。

Usually all a directory name if it's a directory。And then this cluster low and cluster high together are basically a pointer。

Within this。Within this data block。So。If it's， say it's a directory。Then there is a first cluster。嗯。

So this really gives you a pointer to the cluster where these directory entries for that directory start。

Okay so I hope that makes sense。😔，If you have a directory entry， that's。

Itself is for a directory and it gives you a different cluster where the directory entries of that directory are。

I think that makes sense。And if it's a file。😔，Yeah， then this。

This cluster pointer here tells you where the data of that file is。😔，Then you would just read that。

Or that cluster。And if the file is larger than the size of a cluster。

 then you would have to look into the file allocation table。So let's say。😔。

You are reading cluster number five。And you have determined okay。

 the file isn't finished at the end of this cluster。

 then you would just look into the file allocation table in line 5。And get。And there you would get。

The number of the next cluster。Okay， so that's in the file allocation table。😔，So here's the root。

Here's a fire。😔，And this is cluster number five。And then you would just。I mean， we。

 we do know the first。系ello。We do know where the F starts， and then we would just have to。To say。

Five times。4 because we are talking about four bit integers here。

So five times4 is the offset of that entry， which tells us which is the next。系咯。

Which was the next cluster for that file。And that also goes for the directories if the directory has more than 16 entries。

ふ。So that was a lot of talking。Yeah， as I've said， this stuff is really。Really ancient， and。

It's kind of common when you have such ancient things that they just have a lot of remains。From me。

Other decades。So what I'm going to do now is really no great code， but I will just。

Show you how to go through that stuff and。Read some files， find files。Yeah。分。し。Yeah。Yeah。Okay， so。

Now we need structures for these。😔，啊。For this structure there。😔，This is a lot of typing。Yeah。Yeah。

Okay， so。あふ。3 bys for the jump instruction。8 by for the name of the。Software， you know， as I said。

 M K FS we've had， will that be in our case。So the sectors per cluster。

 that's one of the really interesting things。😔，Yeah。So how many copies are there of the fat？

So reserve sectors of sub。😔，Point her down to the fat。Yeah。そ。So the number of fires。

 but as I have said， this is just going to be zero in our case in Fed 32。Yeah。Yeah不。

The out of F 16 version of the Fed sector account， which we will ignore because it will be zero。

And F 32。Atcount。Okay。That was the left one。😔，オ。Again， Ho cluster。

 that's one of the very relevant things。😔，12 reserved ones。Yeah。ふ。So。With these。

 we can now read the B parameter block。Yeah。But that's not going to help us a lot without the directory entries。

没。分。So the creation date and time。😔，So that's excess time。😔，And now the interesting one。嗯。

So let's write time and write date。😔，Okay， so these structures。Should work， I hope。

 if I haven't made。A big mistake here。😔，Yeah。Yeah。嗯。Yeah。OO O。

So very similarly to what we did in the。In the MSdo partition table， we will just instantiate。

Such a bias parametermeter block。こ。Yeah。So we read the first sector of the partition。

 which we have gotten from this partition offset。😔，Yeah。嗯。Okay。

 let's just look at that once now because this was already a lot of code。😔，一。Yeah。Okay。

And it takes a。Stoped。So that was the offset of the partition and we pass that to this read bioos parameterra block。

😔。

![](img/91143d54e154175360703749a1d405ee_9.png)

嗯。Okay， so。Okay， that doesn't really tell us much。😔。



![](img/91143d54e154175360703749a1d405ee_11.png)

Yeah， whatever so。Yes。こ。So where does the F start， It starts at。

The partition offset plus this reserve sector account pointer pointer that talked about。あ。Okay。

 so this is the start of the F。So the start of the F plus the number of sectors in one F multiplied with how many copies of the F we have。

 That's the start of the data。😔，Yeah。よし。不意。Okay， so the root cluster number multiplied with the sectors per cluster。

Is the offset from the start of the data。 but there's。The minor thing， these cluster numbers。

Have an offset of two， so we have to subtract two from that。Okay。Yeah。う。Okay。

 so we we now have space for 16 entries。😔，And we didn't have many files in that directory， right。

 so this should be enough。Okay， and we read the first sector of the route directory into that。😔，So。

Yeah， one interesting point is。If the name of an entry starts with。Yeah， it was a zero zero。When。

Then there are no more entries， okay。Okay， so then we can break this loop。

And we iterate through these entries。😔，Okay， so this is going to be a bit hackish。😔。

But since the directory name， the file name doesn't have a back slash N and print if expect such a back slash N。

 yeah， this is going to be a bit hackish。So we copy the。😔，Fiile name into this。Into this buffer here。

😔，And then we print it。Yeah， let's see what that does。Yeah。



![](img/91143d54e154175360703749a1d405ee_13.png)

![](img/91143d54e154175360703749a1d405ee_14.png)

Yeah， in the AT A driver， I will。Deactivate the printing of。

The data that we read because it kind of screws up what we are doing here。



![](img/91143d54e154175360703749a1d405ee_16.png)

Yeah。Okay， so what do we see here， AF file 1？😔，And A F file2。😔，Looks kind of strange， but。

This is this is on one of the partitions with type 83， type 83， reading a file 1 a file 2。

 These are the file names。That。That we created in the other video where I created these files on the disk。

Okay。But they are in upper case。U。Yeah， one thing about the F file system is that it originally only supports uppercase file names。

嗯。But， yeah， they。I mean， of course， Windows。With Windows 95。

 Windows learned to use files with longer file names and not all uppercase。

And this is done by a hack in these entries， I don't even actually know all the details。

 but you basically just have multiple of these entries in a row。And。Yeah。

 the first one has this dos compatible entry， you know with a Tilde one at the end。嗯。

And the following ones just have an illegal attribute value。

 So they aren't printed when when you say。When you list the directory。And。Yeah。

 then the other ones contain really these the rest of the name and the long name with Unicode characters and stuff。

 but I don't know all the details and actually if I knew them， I wouldn't even tell you them because。

呃。Yeah， there was at least a patent involved。 So Microsoft Pat。Patented this。

A system with long file names with multiple entries with illegal attribute values。嗯。

And at least there was a time when you could really get sued when you even implemented this。

II'm not sure。 I think the patent was revoked some time because it was deemed trivial or。

I don't know。 Maybe it was too relevant to。To have only one company have the control over I I don't know。

 I think it was revoked， but don't quote me on that。 So， so yeah， that's why we are getting these。

Ha these strange file names here。

![](img/91143d54e154175360703749a1d405ee_18.png)

Okay。Okay， so now we find these files。😔，Oh。N， oops。Yeah， so these。

This is this illegal value for this attribute by it。嗯。Yeah。So we will just skip these。😔，Yeah。

And how I would just。😔，Go into these files now。So if the attributes。😔，Have the fifth bit。On one。

 it's a directory。And I'm not going to print directories here。😔，Yeah。Okay。

So this is a cluster well zone。😔，Weather fire starts。Now we turn that into a sector。And again。

 we multiply with fair cluster minus-2。😔，Okay， so we can go to data start then。

The number of the fire cluster， but -2 because of this offset and multiplied it with the count of sectors per cluster that gives us the。

Seectctor number where the file starts。😔，嗯。So I read the file into at least the first sector of the file into this buffer。

😔，Tinate the buffer and then print it。 Let's see。Yeah。



![](img/91143d54e154175360703749a1d405ee_20.png)

Yeah。And there you have it。 This is file 2。Here and on the second partition。

 And it says this is partition 2 file2。 It was the。

The content that we've wrote into that file on the second partition so。This really looks good。



![](img/91143d54e154175360703749a1d405ee_22.png)

嗯。Just in the， in the kernel， I'll just。Move everything down a little。😔。



![](img/91143d54e154175360703749a1d405ee_24.png)

![](img/91143d54e154175360703749a1d405ee_25.png)

A little more。

![](img/91143d54e154175360703749a1d405ee_27.png)

So master putre hard trading part zero and mapputable。😔，Really。

So file one has content on the first partition， file  one has the content。

 this is partition 1 file 1， correct， that's what we wrote in there。

File2 has the content This is partition1， file2， correct， that's what we wrote in there。Parttition 2。

 file 1 has the content。 This is partition 2， file 1。 correctect， partition 2， file 2。



![](img/91143d54e154175360703749a1d405ee_29.png)

As the content this is partition 2 file2。So， yeah。Isn't that something， so。Yeah。

 this was a bit much code， mostly due to a lot of data that we don't really use anymore。嗯。But yeah。

 at least。 so we've gotten into the directory， into the。Into the files， at least in the first。😔。

Sector of the directory is the first sector of the file。嗯。

But you can continue reading the sectors for。Sectors per cluster。 And if。

For this many iterations and if。The file or the directory isn't finished after that。

 then you have to look into the fat and look for them。

 but you know what I'll just make another video about that so。So because。😔。

I'm too exhausted to do this now。AndSo。Yeah， I'm going to make another video about that and so yeah then tune in next time when we talk about that。

嗯。Hit subscribe so that you don't miss that video， hit like if you like this video。Yeah。

 I like the video， I think it's quite cool that we can now actually go into a directory and go into a file。

Inside that directory。I think that's really a nice and interesting part of your operating system。

 so have fun with this and see you next time， bye。