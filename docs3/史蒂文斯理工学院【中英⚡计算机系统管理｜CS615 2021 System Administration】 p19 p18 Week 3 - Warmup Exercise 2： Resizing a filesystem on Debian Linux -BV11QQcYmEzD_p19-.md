# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p19 p18 Week 3 - Warmup Exercise 2： Resizing a filesystem on Debian Linux -BV11QQcYmEzD_p19-

Hello and welcome back to CS615 System Administration。In our last video。

 we showed how to resize a file system on NePSSD using the Resize FFS tool。Today。

 let's just quickly do the same task on Linux so we can see how different processes nevertheless remain fundamentally the same across operating systems provided the tools have support for it。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_1.png)

So just take last time， here's what we'll do in this video。We'll spin up an easy two instance。

 this time， a deian Linux system。Create a new volume and attach it to the instance。

Create 2512 meby partitions so that we have a starting point from which to grow our file system。

Create a file system on them。 mount them add a file to show that our file system changes are nondestructive。

Next， we'll take the first partition and grow it back to1 GBab and verify that we can still access the file on it。

After that， we shrink that partition down to 256 MBby and see what the outcome is。

We've already done this once， so this will be easy。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_3.png)

O。Here we go。We make use of our normal AWS aliases and start a debutian instance。Create a new volume。

And attach it to that instance。Once our instance is up and running。We SS H to it。

 logging in as the admin user。And we're ready to start messing around with our added disc。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_5.png)

Let's see。 Where is it。Here it is。 N V， M1， N1。We'll use F disk to part the disc。Creating a new。

 primary partition。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_7.png)

Of 512 megaby size。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_9.png)

Then we create the second partition。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_11.png)

Spending the rest of the disk。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_13.png)

We print the partition table。And ride it to the disk。

Here's what the resolving petition table looks like。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_15.png)

Ells Bluck agrees。Good。Let's create a file system on each partition。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_17.png)

Easy enough。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_19.png)

Next， we mount at least the first partition。There it is。And create a file on it。As promised。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_21.png)

With that， we are ready to now try to resize the partition we have。

In order to resize the file system， we first have to unloadund it， of course。Next。

 we'll have to adjust the partition size before we can attempt to grow the file system。

You remember that this is exactly the same as what we did on NePSSD to grow the file system。

 we first adjust the disk label。So here we have to delete the existing partitions。

And create a single partition， spanning the whole disk。

Note that F this tells us here that there already is an EXT2 file system on this disk and that we are running the risk of overriding the existing file system。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_23.png)

We'll write the new partition table to the disc and then run the F check program on the single partition。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_25.png)

That detects that the fire system on the disc doesn't match the description of the partition by noting the incorrect superb。

The backup superb doesn't have the correct ion information， but we'll let F check fix that for us。

After that， we can run Resize 2Fs to grow the file system to the full size of the partition。

There we go。Now， let's check if that all worked out。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_27.png)

Map the F shows us that the file system is now approximately1 gigin size and the file we had created on the disk earlier still there。

Cool。Now， let's shrink our fire system。Again， any manipulation of the fire system will require us to unmount the FS first。

We then try to use Resize2 FS to shrink the file system down to 256 megabys。

But the tool tells us that we first have the run F check to ensure that our file system is clean。

So let's do that。Okay， no problems found， let's try again。Yea。

 Re size 2 of S succeeds and shrinks our file system。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_29.png)

But what is that， El's B still thinks the fire system in one is one gigin size。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_31.png)

All right。 That's because Els B looks at the partition table。

 and that still describes our one gig partition。 Let's fix that。First， delete the partition。

 then create a new partition，256 mag size this time。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_33.png)

Re nuke the existing fire system signature and create a second partition Sp the rest of the disk。

 There we go。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_35.png)

And now， El's block agrees with what we had in mind。Me run F check again。

And then mount the no smaller partition。

![](img/6e1e1052ab0b6c945f559886f6d9fb00_37.png)

Which。Looks to be the right size。And still contains our file。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_39.png)

Way。Okay， so just like last time， to grow a file system。

 use F disk to adjust the petition sizes first。Then use E2 F check and resize 2 Fs to grow the file system to the end of the partition。

But note that， of course， that will destroy any data you might have had on any file system on that second partition。

To shrink the file system， use E2 F check and resize2 Fs first。

And then use F disk to update the partition table to match。

If you want to use the now available disk space， you can do so。

 but you have to create a new file on it to use it。See， that was easy。

 especially after having already done this once on Ne BSD。

 and we find that things really aren't all that different across the different versions of Unix。

All right， now make sure to run these examples yourself。

 or maybe go and give it a try in a different way altogether。



![](img/6e1e1052ab0b6c945f559886f6d9fb00_41.png)

Thanks for watching， Ti。