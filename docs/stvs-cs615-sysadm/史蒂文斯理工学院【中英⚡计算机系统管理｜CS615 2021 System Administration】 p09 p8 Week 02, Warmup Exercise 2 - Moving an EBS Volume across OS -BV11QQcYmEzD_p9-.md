# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p09 p8 Week 02, Warmup Exercise 2 - Moving an EBS Volume across OS -BV11QQcYmEzD_p9-

Hello and welcome back to CS615 System Administration。In this video。

 we're going to quickly run through one of the recommended warmup exercises for week two。

I'll show you how to do the basic exercise and the hope that this will set you on the right track to then explore the other questions and dive a bit deeper into the topic at hand。

The exercise itself is intended to get you familiar with the concept of cloud storage and to visualize how we can use elastic block store volumes just as if they were hard drives that we plug into a physical system。

So let's see how we do this。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_1.png)

Let's start by creating two instances。In the easier example， you create two instances of the same OS。

 but later I'm going to ask you to try two different operating systems to illustrate the requirement for file system support。

Then we create a new volume and attach it to one of the instances。

We create a file system on a new disk and mount it。And write a file to the file system。

Then we can terminate the first instance。Now note that any files stored in the root file system of this instance are lost to us as they have not persisted anywhere。

 but since we're looking at our custom volume here。

 we are then still able to attach this volume to the other instance now。

And then retrieve the files from the volume via the second instance。Pretty straightforward， right。

 but this gives you an opportunity to practice the commands relating to file systems and disks。

But I bet you picked your favorite operating system for this exercise。

So why not make it a little bit harder on yourself and pick a OS that you're not as familiar with。

 you should find similarities， but some of the tools will behave differently or you may need to use different tools altogether。

And next， the more interesting question is。Can you do this with two instances that do not run the same OS？

That is， can you mount a disk with a file system created on one OS on another OS？

Let's give this a try。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_3.png)

So let's start with a NePSSD instance。And an Uundo instance。Now。To create a volume。

 I have another shell function to avoid me having to type too much。 It's called new volume。

 and it takes two optional arguments。 That is if a first argument is given。

 it should be the size of the volume in gigabytes。 If the second argument is given it would be the availability zone。

If neither are specified， we default fall to one gig volume in USS East 1A。There。

Now we attach this volume to a netPSSD instance。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_5.png)

This one up here。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_7.png)

Next， we SS H into the instance。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_9.png)

And look at the D message output for our disks。There we are X PD0 as the root disk。

 X PD1 is the newly added disc。We use the disc La tool to look at the partition table。

 which is shown here as a default with a single partition spinning the whole disk。

So let's create a new file system on this disk， we use the default UFS file system version2。



![](img/e77bd8f53e90e9a9ccee0a75e0185a08_11.png)

And mounted。Under a slash mount。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_13.png)

There we go。Next， we create a file on the file system。So we can now unm the disk again。And exit。

We then deach the volume from the instance。And unceremoniously terminate or running that PSSD instance。

Now， let's see what the instance ID was of the Ubutu instance we started。There it is。

So let's now attach the volume to this instance。And as his age to that instance。



![](img/e77bd8f53e90e9a9ccee0a75e0185a08_15.png)

美维尔。Let's use the LS block command to show the discs it uses here。And there it is。

Now we mount this disk， but since this disk contains a file system。

 that's not the standard file system or U to Linux。

 we have to specify that this is a UFS file system and we specify the version as well。

The Linux kernel？Only supports UFS in read only mode， so we specify the amount option2。

And there's the file we had previously created on an NPSSD instance。And there you have it。

 we successfully moved the volume from one EC instance of one OS to another instance of another OS and were able to access the files。

As I said， please give this a try and make sure you understand all the commands used here you。

Then repeat the exercise using different operating systems and see if you can go the other way。

 creating a file system on Sa Linux and mounting it on freeBSD， for example。

Some of the links here may be useful for you in the process。

If you run into problems or have any questions， don't hesitate to ask on the mailing list to enter our class lack。

Thanks for watching and good luck。

![](img/e77bd8f53e90e9a9ccee0a75e0185a08_17.png)