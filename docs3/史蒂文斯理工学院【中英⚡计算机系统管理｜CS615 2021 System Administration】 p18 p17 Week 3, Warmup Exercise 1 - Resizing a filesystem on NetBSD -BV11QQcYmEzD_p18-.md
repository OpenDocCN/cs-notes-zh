# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p18 p17 Week 3, Warmup Exercise 1 - Resizing a filesystem on NetBSD -BV11QQcYmEzD_p18-

Hello and welcome back to CS S 615 System Administration。In week2。

 we already did a few practical exercises relating to file systems。

 so let's continue to try to put into action what we talk about in class。In this video。

 we'll resize an existing file system nondestructively using thatPSSD again as our reference platform。

Don't worry， we'll show how to do the same thing using the in a separate video， but as usual。

 I want you to become comfortable with different types of operating systems。



![](img/7c81c3dfdaaabaee73ea399233b66a67_1.png)

We've already seen how to increase the amount of available disk space by adding discs to a Z F S storage pool。

 And we discussed storage virtualization。 But can we do the same thing on a system that doesn't use Z F S。

When we did our exercise to run out of disk space and i notess。

 we noted that certain aspects of a file system， such as the total number of i notess are fixed at file system creation time。

Within a week three videos， we saw how the traditional UniX fire system manages its resources。

Knowing all that， would it be possible to grow a file system provided we have space available on the disk。

How about the other way around， can we shrink a file system to allow us to reppartition the larger。

 most the unused drive。

![](img/7c81c3dfdaaabaee73ea399233b66a67_3.png)

So here's what well do to give this a try。We'll spin up a net B SD instance。

 create a new volume and attach it to the instance。

 Then we'll partition that disk such that we have 2，512 MBby partitions。

We created fire system on them。And mount them and create a5 or2 on the file system so that we can verify that the operations we are performing are non destructive。

Then we'll take the first partition and grow it back to1 GB and verify that we can still access the file on it。

After that， we shrink the part down to 256 megaby and see what the outcome is。So I'm good。



![](img/7c81c3dfdaaabaee73ea399233b66a67_5.png)

Let's go。Okay， let's create a new volume。And start a noon at B SD instance。

We can then immediately attach the volume to the instance without having to wait for the instance to be up and running。

Remember， we are making use of the various AWS aliases we had to find earlier。

 so make sure to source that fight in our shell。Once the instance has booted up。

 we can assess age to it。And take a look at the resize F F S manual page。



![](img/7c81c3dfdaaabaee73ea399233b66a67_7.png)

Resizing a file system requires you to consider the disk space you have。

 as well as how your partition table aligns with your desired sizes。

So let's take a look at our discs。

![](img/7c81c3dfdaaabaee73ea399233b66a67_9.png)

DFH shows us the default disks and file systems。With the root here being shown to reside on the L D4 disc。

So we can look for the second disc we attach to the instance via D message。There we go。

 It's called L D5。

![](img/7c81c3dfdaaabaee73ea399233b66a67_11.png)

Running this label will tell us what the current part table looks like。

Let's interactively edit it to create the two5 from the 12 megabyte partitions we were looking for。



![](img/7c81c3dfdaaabaee73ea399233b66a67_13.png)

In interactive mode， we get a simple menu where we can display the current partition table。

 which shows us a single 1 GB partition。

![](img/7c81c3dfdaaabaee73ea399233b66a67_15.png)

Let's redefine partition A。

![](img/7c81c3dfdaaabaee73ea399233b66a67_17.png)

We accept the default file system type， start at the beginning of the disk。

 then specify the desired size。

![](img/7c81c3dfdaaabaee73ea399233b66a67_19.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_20.png)

Next， we create the second partition， partition B。We want that partition to also use a standard Unix file system and to begin right after partition A and extend to the end of the disk。



![](img/7c81c3dfdaaabaee73ea399233b66a67_22.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_23.png)

All right。

![](img/7c81c3dfdaaabaee73ea399233b66a67_25.png)

We can write the label to the disc。It now looks like this。



![](img/7c81c3dfdaaabaee73ea399233b66a67_27.png)

Next， we create a new file system on each partition using the new F S command。



![](img/7c81c3dfdaaabaee73ea399233b66a67_29.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_30.png)

Pition 8。

![](img/7c81c3dfdaaabaee73ea399233b66a67_32.png)

Yeah。And partition B。

![](img/7c81c3dfdaaabaee73ea399233b66a67_34.png)

And mount both partitions， partition L D 5 A under slash mount and partition L D5。

 B under slash mount 2。

![](img/7c81c3dfdaaabaee73ea399233b66a67_36.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_37.png)

Here's the amount of disk space available on our disks。



![](img/7c81c3dfdaaabaee73ea399233b66a67_39.png)

Just as we expected。Let's also create a file on the first partition。



![](img/7c81c3dfdaaabaee73ea399233b66a67_41.png)

没有一个。Now we want to resize the partition。For that， we first have to unm the file system in question。



![](img/7c81c3dfdaaabaee73ea399233b66a67_43.png)

Since we want to grow the file system， we first have to tell the system how much disk space there is available。

 So we need to first edit the partition table again and delete partition L D5 B。



![](img/7c81c3dfdaaabaee73ea399233b66a67_45.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_46.png)

And adjust partition A to spend the entire disk。

![](img/7c81c3dfdaaabaee73ea399233b66a67_48.png)

There。Now we can run resize FFS。And specify the raw disk device， D R LD5 a。

 which will expand the fighter system。

![](img/7c81c3dfdaaabaee73ea399233b66a67_50.png)

Let's mount it。

![](img/7c81c3dfdaaabaee73ea399233b66a67_52.png)

We can verify the size。

![](img/7c81c3dfdaaabaee73ea399233b66a67_54.png)

Which looks about right。And the file we had created remains in place。

Showing that the operation did not destroy and recreate the file system。



![](img/7c81c3dfdaaabaee73ea399233b66a67_56.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_57.png)

But about our second partition， L D5 B。

![](img/7c81c3dfdaaabaee73ea399233b66a67_59.png)

Nope， that won't work。That partition doesn't exist any more。 We only have one partition。

 at this point。Okay， so far so good。 we've seen that we can grow a file system provided we have the space。

Now， let's try to shrink the 1 GB file system。For that， we again， have to unmount it。This time。

 let's create a 256 MBgaby partition。How much is that in sectors。



![](img/7c81c3dfdaaabaee73ea399233b66a67_61.png)

5 to 4，2，8，8。Now note that when we want to shrink the fire system， we will run resize FFS first。

 specifying the new size。

![](img/7c81c3dfdaaabaee73ea399233b66a67_63.png)

After that， we adjust the disk label to match。There， partition A is now 5 to 4，288 sectors in size。

And we create a second partition， spanning the rest of the disk。



![](img/7c81c3dfdaaabaee73ea399233b66a67_65.png)

Now， we can mount our first partition again and see that we have successfully shrunk it。



![](img/7c81c3dfdaaabaee73ea399233b66a67_67.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_68.png)

And our fire。Remained in place， hooray。Trying to mount the second part now。



![](img/7c81c3dfdaaabaee73ea399233b66a67_70.png)

Will fail again。 But this time， this is simply because that partition doesn't have a fire system on it。



![](img/7c81c3dfdaaabaee73ea399233b66a67_72.png)

So we first have to create one。There we go。

![](img/7c81c3dfdaaabaee73ea399233b66a67_74.png)

And there we have our two partitions adjusted in size， as we had planned。



![](img/7c81c3dfdaaabaee73ea399233b66a67_76.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_77.png)

Okay， that wasn't so difficult after all。 And I was it。Let's recap。

 We've seen that in order to grow a file system， we first have to adjust the partition table so that there is space for the file system to grow enter。

After that， we can resize FFS and let it figure out the size to grow to from the information in the disc label。

Growing a file system will necessarily destroy any data that was previously on the part of the disk that we're growing into。

 So just be mindful of that。Now， if we want to shrink a file system， we have to reverse the order。

 We first use resize FFS to adjust the size。And then added the disc labor to have the partition table match。

With a freed up space， we can then create another partition if we like。

 But if we want to use that partition， we， of course， do have to create a new file system on it。

Meanwhile， the data on our original file system remains untouched。Well， that's it for this time。

Next time we do the same task on Linux。 make sure to tune in and subscribe to this channel。

Until then， thanks for watching。

![](img/7c81c3dfdaaabaee73ea399233b66a67_79.png)