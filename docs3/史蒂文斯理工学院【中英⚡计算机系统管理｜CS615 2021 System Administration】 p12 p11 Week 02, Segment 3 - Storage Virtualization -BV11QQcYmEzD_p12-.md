# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p12 p11 Week 02, Segment 3 - Storage Virtualization -BV11QQcYmEzD_p12-

Hello and welcome back to CS615 System Administration， this is week 2 segment  three。

In a previous video， we talked a fair bit about different disk devices and how to connect them。

In the process， we briefly mentioned a few configurations for how to combine individual discs into larger storage pools。

 so in this video we'll pick up where we left off there and cover this concept of storage virtualization in a bit more detail。

Now， when we hear the word virtualization， we often jump to certain assumptions and think about virtual machines and perhaps cloud services such as。

 obviously AWS， that on basic level storage virtualization really boils down to simply separating individual physical storage media from a logical storage unit。

Meaning we might populate a large dis with hard drives。

And then carve that up into virtual discs as needed。

This is in a way the inverse approach from dividing a single hard drive into separate partitions。

 a concept we'll discuss in more detail in the next video。

Here we will take a quick look at two different approaches to storage virtualization。

A hardware based approach where a physical device may support and offer means to combine individual drive such as a rate appliance。

And host based solutions， whereby the operating system manages the physical storage devices and combines them using logical volume management。

Well also see two practical examples of logical volume management。

 the device mapper commonly used to modern Linux systems， and ZFS。

 a file system that includes a storage virtualization layer。



![](img/b9095de947c754daf882a809a18860f0_1.png)

But let's start with raid。As mentioned in the last video。

 what you see here is a now obsolete piece of hardware and Apple X rate appliance。

keep using this example picture because it's easy to immediately see how rate works。

 a device offering a redundant array of independent disks or a redundant array of inexpensive disks as it was originally known。

 provides housing for several individual hard drives add a management firmware to manage the drives and connects to your storage area network wire。

 for example，51。But just dashing the drives into the cases and not quite enough。

And this is where the stiffers from the Jbot approach we mentioned in our last video。

 This is not just a bunch of disks， but red allows you to combine all the disks into a single virtual disk so that you can create a large file system that spans all disks。

Another advantage offered by rate devices is to improve IO efficiency by striping rides across all drives。

 thereby minimizing， for example， seek time on the hard drives。And thirdly。

 rate provides for a certain amount of data redundancy。

 but instead of writing data across all drives， it mirrors data between subsets of the drives。

 thereby providing full tolerance。Which is important since we know that all things eventually fail and the damaged hard drive should not lead to data loss if we can avoid it。



![](img/b9095de947c754daf882a809a18860f0_3.png)

So we see that we have several ways of combining and utilizing the discs in the radar array。

 we use the following numeric levels to describe the different approaches。

Level 0 through level 6 represent the most common solutions。

 and you can see the distinction in how data is written as described here。That is。

 at times we consider IOperform on a physical block level， other times on a byte or bit level。

Don't worry， we'll go into the details of what exactly a block is in this context in our next video。

 but perhaps it might be good to briefly summarize the most popular rate levels to illustrate the benefits they provide。



![](img/b9095de947c754daf882a809a18860f0_5.png)

So the simplest way to use multiple discs。Is to put them next to each other and then issue rights not to just one drive at a time。

 but to distribute the data across both drives。That is。

 when the file system issues a right operation， the right device will chop it up on a pro block level and write the first block to disk1。

 the second block to disk2， the third block， again to disk1。

The fourth block again to this two and so on and so on。In this fashion。

 IO performance has increased as you can read or write data double as fast as you could otherwise。

However， there's one problem。If any one of these two discs fails。And from experience。

 as well as simple probability， we understand that the more discs you have。

 the more likely it is that a disc will inevitably fail。Well， if this this goes away。

 then you have lost half your data and you're unlikely to be able to reconstruct what you lost。

So rate zero provides IO performance benefits， but no fall tolerance。

If you want to ensure that you don't lose your data in the case of disk failure。

 you could use a rate1 configuration。In this case， we have the rate duplicate every block of data that your file system is asking to write to disk and it will write two copies。

One to each disc。At a time。Now， in this case， if you lose one of the discs。There's no problem。

 you still have all the data available on the other disk。

Your rate will alert you that it's now in degraded mode， you pop out the broken disk。

 replace it with a shiny new disk， and when you pop that disk in。

 your rate will automatically copy all the data from this one onto disk2 and you're back in business without any downtime。

So that's pretty neat。But of course， in this configuration。

 yourre A foregoing the benefit of Io improvements。And B。

 you effectively only get half the disk space of what you put into the system。

For any one terabyte or file system space， you want to have available。

 you need to put in two terabytes of storage。

![](img/b9095de947c754daf882a809a18860f0_7.png)

So instead of doing either a rate level 0 or level1 configuration。

 you might decide to do a rate level5， which combines IO performance with fault tolerance。

And does that by striping the rides across multiple disks。With each right， going to separate discs。

But then also writing parody bits， Now these pary bits allow you to reconstruct the data in the case of this。

Furthermore， Ra 5 distributes the parity bit across all disks so that you can at any point lose any one of the disks without losing any of the data。

Now you could write all the parodybits onto one of the drives and still retain the same fog tolerance。

But doing so known as a rate 4 configuration incurs a performance penalty。

 which rate5 overcomes wireless distribution。Now with a rate5。

 you do need to have at least three discs and you do not get a linear increase in disk space as you add disks。

 as some spaces reserve for the par information， but by and large this is a popular and efficient solution to increased performance while at the same time retaining fault tolerance。

Now of course you see where this is going right you can combine these approaches in different ways。

 so if you want to have increased fault tolerance or increased performance。

 you don't have to choose any longer That is you can combine different rate levels to get you a mirrored array of stripes。

 a striped array of mirrors， etc， etc。

![](img/b9095de947c754daf882a809a18860f0_9.png)

The firmware and the controller handles all this volume and swapping this why the system is running。

 so called hot swapping as one of those things that makes a little cissipbin hard happy as you see the blinking lights of the device as it rebuilds the array and saves your data。

Quite useful such a redundant array of independent disks and tell you。

But the concept of rate need not be implemented solely via special hardware devices。



![](img/b9095de947c754daf882a809a18860f0_11.png)

And when generally speaking， any kind of storage virtualization can be performed using software。

 meaning the currently exposes the hardware and then allows a piece of low level software to manage it。

This is often referred to as logical volume management and in general terms。

 this is broken down into the management of the physical storage units， for example。

 hard drives or storage devices connected by a fiber channel Z。

These units are divided to physical volumes， which then can be combined to form so calledled logical volumes。

These logical volumes may then spend multiple physical devices。

 providing a layer of abstraction from which the LVM， a logical volume manager。

 can then further combine or create logical volumes such that you could combine individual disks to create a larger volume in the Jbot like fashion。

Could allow for redundancy and fall tolerance by a allowing 40 disk to be replaced without downtime。

Could allow for a file system to immediately and automatically be resized to grow when a new disk is added。

To provide the same rate functionality we already discussed or to automatically perform periodic snapshots of the file system。

 thereby offering a convenient life backup mechanism。

We discuss file system snapshots in particular and backups more generally later in this semester。

For now， let's briefly demonstrate what the use of a logical volume manager and the typical Linux system might look like。



![](img/b9095de947c754daf882a809a18860f0_13.png)

For that， we log into Linux Lab。Where we observe two discs mounted。

Deef SDA1 mounted under slash boot and what appears to be a map device as the root file system。

The root file system。Thus， it does not sit on a regular discretition。

 but appears to be managed via the device map， the basis underlying the logical volume manager and Linux。

Let's look at the D message output relating to the disk。



![](img/b9095de947c754daf882a809a18860f0_15.png)

Here we see that deaf SDA appears to be a scy disc that contains several partitions。

The LS block command shows us a bit more information about this block device。

We have one 20 gig disc with the first partition mounted under boot。The second partition。

Deaf SDA2 is an extended partition， so it only contains the meta information for deaf SDA 5。

 which itself is then divided to two subpartitions， both managed by the LVM。

One part for slash and one for swap。Swaap on confirms that the swap space available in the system is made available by other device mapper device。

 D DM1。We'll look into the concepts around partitions in more detail in our next video。

 but as shown here， we can see the use of an LVM even for a very simple system with just a single disc。

Another thing I wanted to demonstrate here was the use of ZFS to manage storage resources。

ZFS is a file system originating from Suns， well oracles nowadays， So Laro's operating system。

It is a fairly different5 system from others， and that it includes all the bits for logical volume and storage pool management。

 as we will see。Let's start with a new screen session。And spin up an omniio instance。

Omniio is a version of Ilums， an open source's Uni system。It is based on open Sos。

 so the easiest way for you to run a Solars variant。This AMI image here lets us get started。

In our custom EC2 weight function， which you may recall from one of the warm up exercise videos。

 lets us know when the system is up and running。All right。So let's log in。Here we are。

Let's again look at the disk devices reported by a D message。



![](img/b9095de947c754daf882a809a18860f0_17.png)

Here the disc is called XdF。Let's try out the format utility to look at the partition table for this disc。

We find one disk。Identified using the historical s addressing schema as controller1， target0， disk0。

With individual petitions or slices in So's lingo then being referenced after this prefix。

When we select this disc either， we get a warning message。

Slide0 of this disc is part of an active Z vestpo。

![](img/b9095de947c754daf882a809a18860f0_19.png)

So we can't use the format utility here。

![](img/b9095de947c754daf882a809a18860f0_21.png)

DF confirms that our root file system appears to be located on the RPol ZfS pool。

Let's take a look at that via the Zpool tool。

![](img/b9095de947c754daf882a809a18860f0_23.png)

Here we see that indeed the apool appears to be backed by that very disc， C10 D0。

 giving us roughly 7。5 gigy of disk space。

![](img/b9095de947c754daf882a809a18860f0_25.png)

ZFS list then shows us the file systems created on this pool in a way similar to how the extended partition on the Linux system contained the root file system。

Now。Let's pretend that we're adding a new physical disk to our server here and going to create a second storage pool from those disks。

For that。We run the AWS easy to create volume command。In a separate screen session。

I created one gigabyte volume。Then we attach that volume to the instance。W。

 what was our instance ID again？Let's check what instances we have running with one of our aliases。

There， let's grab this instance ID and continue。Now。

 not repeat the same thing for a second volume so we can pretend that we just hooked up two separate hard drives to our server。



![](img/b9095de947c754daf882a809a18860f0_27.png)

![](img/b9095de947c754daf882a809a18860f0_28.png)

Okay， you're all back to our server。

![](img/b9095de947c754daf882a809a18860f0_30.png)

Looking at the D message output again， we now see that we have two more discs showing up。



![](img/b9095de947c754daf882a809a18860f0_32.png)

XDF0 remains the root file system， but now we also have XdF1 and XdF 2。

Note that when we use the AWS E2 attach volume command we specified a different device name。

 this is a bit confusing and annoying because the device name we choose may not be what the OS on the instance uses。

 but so be it。Not also that we didn't have to reboot our instance。

 we could simply plug in our new hard drive into the life system Evoa， here are our discs。

 That's pretty cool。Anyway， let's see what disk info tells us。here they are our root disk。

 ethics in size， and two new disks， C1 t5 d0 and C1 t 60。

Now let's create a new pool from these two discs。Let's call it extra。

The Zpo list shows us that our new extra pool combines this space from the two disks yielding roughly 1。

9 gigabyte。So there's always a little bit of overhead involved。

 so we didn't get the full2 gig of space， but we do see how we can combine storage into a single pool。

ZFS list shows our file system。But we haven't even created one on our extra po yet。

So let's do that real quick。The EFS create extra space there。

Now let's tell the system where to mount this new file system。And here we go。

 new disk space now available under the slash mount。

We can write data into this file system now as we would expect。Okay， so far so good。

But now let's pretend that we got our hands on yet another disk drive and want to add this to the pool。

So we create another volume。Attach that just as before。And immediately。

 disk info shows the new disk present， C1 T70。

![](img/b9095de947c754daf882a809a18860f0_34.png)

![](img/b9095de947c754daf882a809a18860f0_35.png)

Our disc mounted on a slash mount has about 1。8 gigs of space。



![](img/b9095de947c754daf882a809a18860f0_37.png)

We add the newly attached disc to our existing Zpo。And。



![](img/b9095de947c754daf882a809a18860f0_39.png)

Bam， just like that， our amounted disc is now 2。7 gigs in size。So that's really cool right。

 we didn't have to shut down the system to attach the disc and we didn't have to partition the disc or recreate the file system or anything。

Simply adding the disc to the pool underlying the file system gets us extra space。

Now that this gave you an impression of the flexibility and power of ZfS。

 and how this illustrates the concept of storage of virtualization。

 as for now using storage units in a very flexible manner to combine and create file systems。



![](img/b9095de947c754daf882a809a18860f0_41.png)

All right。Time for a break again， I want to make sure that you follow along with these examples so here's another set of exercises I recommend for you。

Create an omniioos instance and use ZFS to create different types of pools ZFS supports all the concept we talked about and you can use it to increase performance by striping data。

 increase fall tolerance by mirroring data， or a combination of these via something called rate Z。

Once you've created such a pool and mounted the file system。

 simulate a hard drive failure by detaching the EBS volume， how does the system handle this？Next。

 think about how the system behaves if we add a disk。

 adding a disk add space so growing the file system seems an easy enough thing to do。

But what if you were to remove a disk， can you shrink a file system in this manner？

Seems possible so long as the data on the P system still fits into the new pool。

 but what if that's not the case？As you can tell， there are a number of things you can play around with here。

 and I hope that you will explore the concepts from this video in this way。

If you run into problems or have questions， don't hesitate to ask for help。Okay， that's it for today。

Next time we'll talk about the physical structure of traditional hard drives as well as continueual discussion of different partitions that we already hinted at a little bit today。

Until then， thanks for watching， cheer。

![](img/b9095de947c754daf882a809a18860f0_43.png)