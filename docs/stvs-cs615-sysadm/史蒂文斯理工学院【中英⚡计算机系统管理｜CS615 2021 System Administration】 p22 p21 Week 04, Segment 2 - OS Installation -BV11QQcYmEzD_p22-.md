# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p22 p21 Week 04, Segment 2 - OS Installation -BV11QQcYmEzD_p22-

Hello and welcome back to C S 615 System Administration。 This is week 4， segment 2。In our last video。

 we just spent some time discussing the different types of software。

 and we did draw a distinction between the operating system。

 the O and several other types of software。So why don't we start out thinking about how we get one of those things。

 one of these operating systems onto our disk。In this video， we do just that install an o。But。

 of course， remembering that we want to keep scalability as a core pillar in our mind。

 we don't just worry about getting an O S installed this one time on this one box。 but rather。

 how to ensure we can do this in an automated fashion across hundreds or thousands of systems。

And before we can do that， we should probably come up with a plan of what files should go where。

You remember the here menu page on our last video。 It tells us the file system layout and describes the hierarchy under which we place the various files。

In there， we had noticed a difference between， for example， the bin and user bin directorories。

 Everything under the user is not needed at system boott time。

 So it can be place into a different partition that's mounted as part of the boot process。

So note the presence of the Var directory， which contains well variable data。

But why would we care about having variable data under a separate directory or partition？

To answer that， let's look at the definitions of different types of data。Now variable data。

 as the name suggests， is data that is expected to be modified during routine operations。

So that includes log files obviously， as well as the data in the user's home directories。

 for example， as we expect them to write to their files with some frequency。

In contrast to variable data， we then also have static data data that is not expected to change during the normal course of operations。

This includes pretty much all of your operating system files， your libraries and applications。Sure。

 you may need to update those once in a while， but by and large， those do not change。

And perhaps you already see where this is going。 If you know which data changes and which data does not。

 then you can set up separate partitions and mount the file systems accordingly。

Variable data read write with asynchronous I O to improve performance and perhaps no exact or at least no S I static data。

 read only。The separation then makes it more difficult for an attacker to compromise the system。

 even if they get access， but it can also help you organize your file system across multiple hosts。

And for that， you may want to further divide your data into shareable data data that if youre on multiple hosts。

 remains the same across all of them。And non shareable data data that is necessarily unique to each individual host。

Again， you can hopefully see why this might be useful。

If you know which data sets are identical across hundreds or thousands of hosts。

 then you can think about how you can share it or deploy it or manage it in a central fashion。

 where the bits and pieces that are non shareable need to necessarily be managed on a host by host basis。

Here， let's look at some examples of these different types of data。Cate a matrix。Since variable。

 static and shareable， non shareable may overlap。So as an example of data that is static， that is。

 we don't expect it to change during the normal system runtime， as well as shareable。

 that is the same for multiple systems might be the data found under user。

 the common libraries and applications for a given operating system。As well as the data under opt。

 the popular directory or Mo point for addon software。

 not included in your OS or not managed by your package manager。

These files should not change frequently， but would be identical across your entire fleet of systems in the given operating system。

Sharable data that we do expect to change。Might be that under a separate data petition we specifically set aside for a project。

 for example， such as bar data or the home directories of your users。

As we mentioned earlier in the semester， you might use the network file system to make shareable data available to multiple systems。

 and NFS mounted home directories or perhaps the most common use case here。Now。

 in the column for non shareable data， we'd list the system specific files such as the unique boot blocks or the system configuration file under Etsy as examples of static non shareable data。

And the various runtime files created by processes on this particular host as examples of variable non shareable data。

Now， of course these distinctions are dependent on your particular setup。

 but I hope you can see that it might be useful to plan for how you are going to manage your data in this fashion and more applicable to this video segments topic。

 that it be rather useful to have decided on this layout before you begin the OS installation such that all the right partitions are created and the files installed appropriately。

That is， we get our first taste of one of the more important aspects of operating system installation。

Not so much the actual deployment of software or packages onto the disk。

 but the advanced planning of what to put where。But allright。

 so let's assume we did plan out our file system layout and partitioning scheme。

 and we now want to go ahead and install an operating system。



![](img/d27699193be8467bebcf42c1d951115c_1.png)

You may be familiar with a screen like this， a graphical installer offering you a few buttons to click to install the OS。

Now， this is certainly useful， and it takes quite a bit to get to this point。

 We must have bootied from some alternate media， loadeded the temporary or lesson into memory。

 initialized the graphics hardware and detected the correct display and all that so that we can interactively ask the user how they want to install the operating system。

But in this class we said we want to keep an eye on simplicity and scalability。

 and I think it's obvious that we can't easily install a few hundred systems for each one we have to manually click on some boxes to start the installation。

And， of course， nobody outside the individual consumer would use such a graphical installer。 Instead。

 in the industry， we use deployment engines that are oftentimes custom built that allow for the completely automated installation of an operating system based on the system profile。

But to be able to build such a system， we need to understand what the actual steps are that take place during OS installation。



![](img/d27699193be8467bebcf42c1d951115c_3.png)

So let's go ahead and perform a manual installation， but not using a graphical display。

 but instead using the actual commands that the graphical installer would invoke。So for this。

 we are booting a virtual machine of an NBSD install Cd， which drops us into a menu based installer。

This is too interactive and doesn't show us the commands。So we simply decide to drop out of the menu。

This lends us in a root shell on the Rams coes booted off the C D。

 and we can now run all the commands we need to install the operating system ourselves。So first。

 let's identify the hard disk available to install the OS on。There， W D0 with a geometry。

 as shown here by the kernel。From our previous videos。

 we know that we need to set up the partition table。

 so let's calculate the total sectors left if we start our OS partition at offset 63。

And then use F disk to set partition 0 of type Ne BSD at offset 63 of the given total size。Next。

 we copy the actual boot code into the boot sector。And mark petition 0 as active。

Then we create the BSD disc label。Since the editor environment variable is unsai。

We get dropped into Ed， the Standard Unix editor。But don't worry， that is not that bad。

 It just a line based editor。 So we have to specify the actions with line addresses。Anyway。

 here's what the disc label looks like right now， and that looks just fine。

We have a single large partition for use by the O。 and in this case， we have no need to change that。

So we simply write the label to disk。And quit。Now we're ready to create the file system on the partition。

 similar to what we've seen in a previous video， if you recall。Okay。

 so now that we have a file system created on a destination disk， we can mount it。

 We use O as things so that ride happen faster when we extract the data。Next。

 let's look at the data sets we want to extract。We see all the different tarrbts here and can choose which ones we want to install。

I'm going to leave out the X window system since we're installing a server and don't need a graphical user interface。

So we extract all of these。Into slash mount， we are disus mounted together with a generic kernel。

Next， we copy the bootstrap code into place。And install the primary boot loader for a file system with a5 second countdown。

Then we create all the device notess under a s dev， and were mostly done。

Mostly because our system is now installed， but not configured。To do that。

 let's shoot it into it so we can treat it as a regular system and don't have to remember the pass names under slash mounted etc。

See， here we are。 Everything looks fairly normal。We need to adjust a few bits in Esyrc do com。

 The F controls the system startup。On other unique systems。

 that might be equivalent to inner D or system D configuration。Here we enable DHCP。NTP。

And said a host name。Then。😊，Update et C F step to tell the system to mount the root file system。

And now we're done。So we can exit our root。And not the disk。And reboot into a newly installed OS。

When the system comes back up， we find our stage1 bootloader here。With a5 second delay。

 we had specified。Oh， I Corel bootss up。DHP does its thing。And here we are， up and running。



![](img/d27699193be8467bebcf42c1d951115c_5.png)

Okay， so why don' we go through all this work of running all these commands ourselves when there's a perfectly good installer provided by the O。

Well， as mentioned earlier， those installers don't lend themselves to automation and what's more in this class we seek to actually understand what the system does。

 how things work。And in the process， we can then extrapolate roughly just how OS installation needs to happen regardless of the particular unx flavor in question。

So let's generalize and run through the steps to install the system based on what we just observed。

Obviouslyvily， we'll start with a system being powered up。As we've already covered before。

 there's a few things that happen。 But at some point， we'll be looking for a boot loader。

 If we are installing a yours， then obviously， we don't have a boot loader yet。

So we need to boot off alternate media。 In our example。

 that in the case of your custom one time end user scenario， that would be a C D。

 But for a scalable approach in a data center， you'd probably want to have your system net boot。Now。

 this includes a bit of L complexity， such as the system need to obtain its network configuration and retrieving the Rammdesk to boot into over the network。

 but will hand waveve over this for the time being。Once your Rammbs has booted。

 you then need to identify the hard drive to install the oil onto。Partetition and lay of the disc。

Create the file system。And store the boot blocks and make the partition bootable。

And retrieved the O S itself。In some cases， this will be extracting the data from the local CD as we showed。

 or in the data center retrieving the data over the network from a local mirror via HTPS。

 for example。We then extract the data onto the disk。

Perhaps add whatever additional software we might need。

And then perform a little bit of minimal system configuration， just as we've shown。After all that。

 we're good to go and can reboot the system。Now， these steps are more or less the same for most unique systems that you would install。

 and they would only differ in the specific command you'd use to perform them。

And having understood these steps， you can then automate the whole process and build a deployment engine。

 something just about every system administrator I now has built at least twice in their career。

But perhaps you also notice that the basics of this process are really not complicated。Rather。

 the more difficult parts are happening elsewhere。That is an order for you to be able to build an automated deployment system that can install an OS unattended across many systems。

You need some sort of hardware inventory。A method to determine which rest should go on which hardware。

As well as what software to add that's not part of the Bezo S。

This may be accomplished by defining a profile or identities for your different workloads or images。

 for example。Next， you need to perform at least some initial system configuration。

And register the now installed system in your inventory。Before you restart it。

But many of these steps here require a bit of infrastructure and organization around them。

And once again， it's not always clear where the boundaries lie between how you bring up a new system and how you configure a running system。

 That is there some overlap with a larger topic of configuration management。

 as well as service orchestration。 Topics will come in more detail a bit later in the semester。

And finally， you may also have noticed that we kept talking about noiseest installation as if it was necessarily onto a physical or virtual roll server。

But it needn't be。 nowadays， it's perhaps more common and certainly more scalable to build individual containers or O S images。

 That is， your AW S machine images are examples of where an O S is installed。

 not onto a running system， but instead into what becomes a machine image that can be instantiated。

Now， there's obviously a bit of difference in creating a container for a process and instantiating a machine image。

 but perhaps you can see that the upfront work we discussed。

 deciding what data can be shared were aesthetic static， et cetera。

 and the general steps we outlined help us better understand that process as well。

So let's summarize what we observed。For starters， even though it may seem intimidating the first time you do it。

 the steps involved in installing an operating system are not very complicated。What's more。

 they're the same or similar， at least across the board。

 which is why it's useful to go through the exercise of manually installing a system。Secondly。

 we saw that planning out our file system layout can help us streamline the Earth installation process。

 improving its scalability and making it simpler。Lgically then the bulk of the work lies not in executing the same set of commands。

 but rather to identify the surrounding properties。

 factors and system aspects that need to be accounted for。All of that leaks into， as we said。

 with other areas of work and system administration， which well get to later in the semester。

 but which you may want to look at already to see how， for example。

 configuration management overlaps here。So a few exercises for you to improve your understanding and internalize what be covered so far。

Would be to repeat the process shown here for a few different operating systems。

Download the install images and install them into a VM。

Follow their provided installer and note which steps they are executing。

 Then see whether or not you can repeat the process yourself by running the commands manually。

Finally， think about how you would automate the plot of installing these different Os。

 There are some tools out there that can help you research and find out what they are and how they work。

😊，Then think about how this process differs from creating a machine image instead of installing an O S。

 How would you handle the host specific bits in such an environment。

 What infrastructure services does the cloud need to provide to make this possible。



![](img/d27699193be8467bebcf42c1d951115c_7.png)

As you can tell， you could spend a lot of time on this topic alone and rest assured that system administrators everywhere have done so。

In the process， we've all found out that there is a distinction between what makes up the operating system as provided by your vendor or open source project and what ends up on your system。

 You will have to add more software， some of it open source。

 some proprietary and some developed in house。How we try to manage all these different components will be the topic of our next video when we discuss package management。

Until then， thanks for watching， G。