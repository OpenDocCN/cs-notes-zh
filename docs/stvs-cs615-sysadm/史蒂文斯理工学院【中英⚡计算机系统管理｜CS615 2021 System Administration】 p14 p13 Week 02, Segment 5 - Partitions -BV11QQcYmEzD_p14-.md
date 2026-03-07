# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p14 p13 Week 02, Segment 5 - Partitions -BV11QQcYmEzD_p14-

Hello and welcome back to C S 615 System Administration。This is week 2， segment 5。

When we talked about the physical structure of the traditional hard disk drive in our last video。

 We mentioned that understanding those aspects would help us better understand other file system concepts。

 And one of those is the topic of this video。 Partitions and partition tables。That is， this time。

 well talk about how to divide a single disc， physical or virtual。

So let's start with a little pop quiz。What's wrong with this image。

What you see here is the disk utility interface on Macs。

 which presents to you a graphical representation of the parts you might want to create on a disc。

In this example， we have a 1 GB disk that we divide into our 100m boot partition at 250 sites MV root partition called slash。

 a small partition of raw disk space left for swap and a user partition using the remaining disk space。

Thisis futility shows that these partitions as pie wedges of the whole disk。

 which is a bit irritating because that's not how partitions work。Well。

 at least not on a traditional hard disk drive。Because。



![](img/c10a41da61916ba298d48e5726328985_1.png)

Suppose it did work that way。Then we'd have our disk drive here。

 and we'd create a partition like this。But now， as we discussed in our last video。

 we know that data on the same partition is likely to be accessed sequentially。

 meaning if we wanted to read a few files from this partition。We'd end up seeking all over the disk。

 This would be quite inefficient， to say the least。

So let's rethink how partitions are actually laid out on the disc。Rather than using a pie wedge。

 we will use a number of cylinders that we group together and create a partition that looks like this。

There is all the data on this partition is now stored within this ring of cylinder groups。

Accessing this data will be much more efficient， as we now reduce the seek time and can read and write from the spinning disk without much movement。

So rather than using the pie wedges， Apple's discontinuility showed us。

 let's visualize our partitions like this。So we'd have one small boot partition。

 which is typically kept at the beginning of the disc。Remember in our last video。

 we talked about disk possibly being larger than the bio can address。For this reason。

 the historical layout places the boot partition near the beginning of the disk so that the OSs can boot up and then possibly use partitions that the bios cannot。

 but that the Os can address。Now， that is largely a historical factoid as modern biases and bootloaders can handle large disks that it explains why you still sometimes see separate boot partitions in the first still in the group of the disc。

Next， we might want to create a swap partition， which would then begin right where the boot partition ends and extends to cylinder 228 in this case。

After that， we create the root partition， as well as the user partition filling up the remaining slender groups。

Okay， so you understand why the partitions are arranged by cylinder group。

 that is actually precisely how we partition the disc by describing the layout using cylinders。

Let's see what this looks like in practice。We started in that B SD instance。

And create a new volume so that we can illustrate the creation of this layout， just like the。

 the one we just presented。We attach the volume to the instance。And then wait for it to come up。

And then log it。On that BSD and other BSD versions。

 we use the disc label utility to display the partition table。

And what it shows us here is 512 B per sector， as we'd expect，2048 sectors per track。

1 track per cylinder， and a total of 1024 cylinders。

This thing gives us the total number of sectors and has the total capacity of the drive。

 as we discussed in our last video。Now note that the disc label also tells us that both the boot block and the super block are size 0 here。

What that means， we'll cover a new video。 But let's go ahead and edit the partition table。

Here we start out with partition A。We'll start at sector 63 to match regular bootable net BST partition。

W is 63， said Tide will get into that in the next week，But okay。

 let's specify the size as 100 megabyte。This now shows us the size in sectorrus。

Which we can confirm via some trivial shell arithmetic to indeed， be 100 megaby。Good。

Let's continue with the next partition。Partition B。We'll make this partition a swap partition。

 Have it start at the end of partition A and make it 0 28 MBby in size。Next， we use partition E。And。

Wait， why do we skip partition C And D。Well， on BSD systems。

 partition D is traditionally reserved to simply describe the entire disk and partition C as the part of the disk gets reserved for this OS S。

Here， too， we'll get back to this later。 So let's continue with editing partitionee。

We'll make this partition start where our swap partition ends。And size it to 256 MBby。Now。

 we finally at the last partition partition F， which begins where partition E ends。

And extends to the end of disk。Now that we finished carving up our disc。

And writing the partition table， we need to write this disc label to the disc， and then we can quit。

We can display the partition table again using the displayable command using the cylinder head sector addressing here。

Now， we see how the partitions shown here match what we had illustrated earlier with our cylinders。

 but we also see that partition D spends the whole disk， as I had just mentioned。Okay。

 so now we could move on to create file systems on this partition。

 but that's the topic of our next videos。 So first。

 let's compare what this looks like on a different operating system。

Here we start an omniios instance。And again， another volume。Same procedure as before。

 We wait for the instance。Attach the volume。The order of these two steps really doesn't matter。

And then we SS H to it。Now， in Omniios， we use the format utility to inspect our disk。

You may remember from our earlier videos that Omnios uses ZFS pools by default for the root file system。

 So instead， let's look at the separate disk that we attached。Disc C 1 T 5 D0。

 which is shown here with its geometry of 1022 cylinders with two alternate cylinders。

64 heads and 32 sectors per track。When we select this disk， the tool informs us。

That no sals if this petition was detected。This would be the master boot record partition for the disc。

 So let's create one by calling F disc。Will accept the defaults。And display them here。

This gives us a default partition table in which we notice that similar to the Ne BSD D partition。

 there's a partition here reserved to represent the entire disk。 Partition 2， labeled back。

We also notice that this OS S has two cylinders reserved， Partitions 8 and 9。

 which it may use for alternate boot blocks。 again， more on that in the next video。

But this is not the layout we want。So， let's call partition。And change partition 0。

We call it the boot partition market as ridable and mountable。

 Let's start it cylinder 0 and give it 100 mag size。Then we edit partition1， mark at swap。

 make that partition ridable， but unmountable。And habit started cylinra 100。

And making it 256 MB in size。Next， partition 2。Now， wait， partition 2 describes the whole disk。

 as we said。 So let's edit partition 3。We make it the root partition。256 max and size。And finally。

 partitioned 4。For user。Using the remainder of the disk space。

And here's what the new partition table now looks like。

 All entries neatly reflecting what we had requested。

So let's write this label to the disk andque out。Then we can use the PRRT Vtlk tool to print the volume table of contents。

Which just displaced the same partition table。As you see。

 while somewhat different from the Ne BSD example， there's plenty of similarities。

So let's quickly also compare this how you do this on Linux， okay。Again， same procedure as before。

This time， we use a fedora instance。Wait for the instance， At the volume。And as a age to it。Oops。

 we have to use the Fiora user for this instance there。Okay。

So here we start with the Es command displaying the current partition table。

Which contains no entries。 So we only get the this geometry。

Let's use the C of disk tool to edit the partition table。This， too， let its own peculiar syntax。

But to specify the pre， we enter comma100 M B here。

Then specify the information for the second partition。Then， the third。And the fourth。

The resulting part table looks like this。 And we write the label to the disc。Now。

 since this is Linux， we have about another half dozen tools that could do the same thing in a different manner。

 So let's use the C of this tool to verify the layout， Why not。Here we go。

 Nice menu driven interface。Okay， everything looks kosher。And Els block。

 which remember from an earlier video， also shows us the correct partitioning of the disc。Okay。

 so let's reapp。Weve seen that partitions on hard disk drives are groupings of clin groups into contiguous regions and thus cannot be visualized as spages。

 even though that's a common representation in many tools。

We've seen different partition schemes and have mentioned different types of partitions。

And we saw that even though different operating systems may use different tools and have some other slight differences。

 the overall concepts remain the same。 We utilize cylinder groups。

 tracks and sectors to address the blocks and define partitions with a description of these partitions。

 The partition table being written to the disk。We did hint at the fact that the buyers or MR partitions are different from O S partitions。

 but we haven't quite looked at how they're different。 That will be covered in the future videos。

 so don't worry。One of the perhaps peculiar things we've seen is that parts may overlap。 that is O。

 however， as it depends on the purpose of the partition。If we want to describe the entire disc。

 we need a way to do so。 And logically， other partitions will be comprised within that larger partition。

Finally， we should quickly note just why we may want to partition our disk rather than just using all the disk trace we have in one giant blob。

 The reasons for this include a desire to separate system data from user data so that， for example。

 users writing to their home directory cannot fill up the system partition。

Another reason might be to separate the boot partition from the rest to allow the boot loader to boottrap a system that can address a disc that's too large for the bios。

 for example。Another reason might be that we may wish to use different types of file systems for different partitions。

 Again， we'll talk more about this in the next few videos。And finally。

 you sometimes may wish to apply different mount fls for different partitions。 For example。

 you may wish to mount the system partition as read only so that a compromise of the system cannot lead to a persistent compromise by installation of a back door。

Or you might want to mark a petition as no su idea and no exactec to further strengthen security or enable or disable asynchronous I own in the file system。

There are many other reasons and will soon enough revisit many of them as these topics continue to build on one another。

So make sure to come back to this in the previous videos。

 even as we prepare to move forward to file systems， bootloaders and how the system bootsts itself。

Until then， thanks for watching， cheer。

![](img/c10a41da61916ba298d48e5726328985_3.png)