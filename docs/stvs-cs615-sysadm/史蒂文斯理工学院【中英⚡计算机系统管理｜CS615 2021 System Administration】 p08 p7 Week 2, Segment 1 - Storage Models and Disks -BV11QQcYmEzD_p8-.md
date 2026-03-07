# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p08 p7 Week 2, Segment 1 - Storage Models and Disks -BV11QQcYmEzD_p8-

Hello and welcome back to CS615 System Administration。This is week two segment one。

 and we're going to be talking about storage models and discs。As system administrators。

 we are responsible for all kinds of devices， we build systems running entirely without local storage。

 just as we maintain the massive enterprise storage arrays that enable decentralized data replication and archival。

We manage large numbers of computers with our own hard drives using a variety of technologies to maximize throughput before the data even gets onto a network。

 just as we often require and guarantee access to share data storage across the internet。

We begin with this topic because without data storage， we can't even bring up an operating system。

 we are always dealing with ways to store data， and so as a asset。

 we better have at least a rough idea what's involved here what can go wrong and how to scale data access。

Talking about scanning data storage， that's really a futile endeavor。

 no matter how much we make available， we'll soon run out of it。Think about it just a few years ago。

 having access to even just one gigabyte of data was mind boggling。Alright， for most of you。

 this probably has shifted and the notion of needing a terabyte of storage for your videos。

 photos and music doesn't seem so outlandish， but of course you may also have heard the famous quote attributed to Bill Gates that 640K ought to be enough for anybody。

Data expands to fill any void。No matter how much storage you allocate。

 your users will find a way to use it up。So we need to think about how to try to avoid a perpetual state of full disks。



![](img/59879360979ce405a8b8642a15d68ec8_1.png)

For that， we will discuss the following。Basic disk concepts， basic file system concepts。

And file systems in general， as well as the traditional UniX file system in particular。

Within each of these topics we have a few subtopics in order to understand basing disc concepts。

 we need to take a look at common storage models， which is the primary topic of this video。

Following that， we talk a bit about disk interfaces， how we connect storage devices both physically。

 as well as what protocols we use。We talk about physical aspects of disk drives as they are important to understand file system concepts later on。

And from there， we talk about partitions， which will flow logically from the discussion of the physical structure。

 as you will see。Next， within the area of file system concepts。

 we'll talk about how to combine storage devices using， for example。

 a redundant array of independent disks or rate。Logical volume management。

And how formatting devices may influence the storage capabilities。Finally。

 we'll talk about what you can do with storage media once you have it hooked up appropriately。

What types of file systems they are and exactly how the traditional UniX file system works？

That part will be covered in the next week， while we'll try to cover all the other topics in week two。

So let's get started。We distinguish different storage models by how the device in charge of keeping the bits in place interacts with the higher layers。

By where a rawblock device access is made available。

 by where a file system is created to make available the disk space as a useful unit。

 by which means on protocols， the operating system accesses the file system。Somewhat simplified。

 we identify the operating system。The storage device itself I eat that thing where the bits are actually stored。

The file system sitting on top of the storage device and interacting with the application software。

Okay， so the first， the most common， as well as most simple storage model we'll talk about here is direct attached storage or DS。

It's just what it sounds like， the storage medium， most commonly a physical hard drive。

 is directly attached to the host。

![](img/59879360979ce405a8b8642a15d68ec8_3.png)

If you look at your laptop， a workstation， an desktop， or a physical server。

 you'll likely find a physical hard drive present。Here we see one partition on the physical disc。

 the disc1 mounted under slash。As well as several other partitions mounted elsewhere in the file system。



![](img/59879360979ce405a8b8642a15d68ec8_5.png)

Now for a workstation or a typical server， the direct attached storage device might be a regular IDE hard drive as the one shown here。

On the right we then see how the different components come together as obvious as it may seem。

The storage device is part of the physical server and managed by the operating system。

The file system is created on the storage device and facilitates access to the block level storage provided by the hard drive to the application software on the file level。

Makes sense， right？Direct attached storage is a very simple architecture with a number of advantages。

Since there is no network or other additional layer in between the operating system and the hardware。

 the possibility of failure on that level is eliminated。Likewise。

 performance penalty due to network latency， for example， is impossible。At the same time。

 there are some disadvantages。Since the storage media is well directly attached。

 it implies a certain isolation from other systems on the network。

This is both an advantage as well as a drawback， on the one hand。

 each server requires certain data to be private or unique to its operating system。On the other hand。

 data on one machine cannot immediately be made available to other systems。

But we frequently want to be able to access certain data from multiple servers。

When a user logs into host A， she expects to find all her files in place just as when she logs into host B。

Record that our shared Linux systems at Stevens are behind the load balances that when ISSH the Linux lab and may be dropped into one of several physical systems。



![](img/59879360979ce405a8b8642a15d68ec8_7.png)

But I still expect to and fortunately do have all of my files available。

The way we can accomplish this is by having the data storeden a network attached storage device。

 which sits in a central location somewhere and where the Fire to access via， for example。

 as shown here， the network Fire system or NFS。Okay， so how does this work then？

We see that there's a central server， Chronos source I， in this case。

 which offers the data from my home directory。From a specific path at the local host。

 even in this case， Monsad under Home de Shama。So the file server must have the actual storage and has created a file system on that。

 which is then makes available over network。Such that clients can access it。

But these clients do need to support the network file system。

 which in turn provides a standardized abstraction of the file level access to the application software。

Now note that the file server accesses the storage device as direct attached storage。

 meaning it's as best as we can speculate anyway， physically connected to that server。

What that looks like in practice depends on the scale of the system。

But seeing of the path on Chronos society is called x rate 01。



![](img/59879360979ce405a8b8642a15d68ec8_9.png)

Might。Just be an Apple X rate storage appliance， a mass storage device virus that was offered by Apple up until 2008。

 and which offered storage of up to 10 terabytes or so。

I remember when I worked here at Stevens Beckck in 2006， we did buy an X rate and used it as our NA。

While this system is no longer in use here， the export paths were kept the same to avoid having to update all possible clients it seems。

I also have a little Sis and War story relating to this X rate here at this link for your entertainment。

😊，Anyway。Now network attached St allows multiple clients to access the same file system over the network。

 but that means it requires all clients to use specifically this file system。

The NAS file server manages enhance the creation of the file system in the storage medium and allows for shared access overcoming many limitations of direct deched storage。

At the same time， however， and especially as we scale up。

 our requirements with respect to storage size， data availability， data redundancy and performance。

 it becomes desirable to allow different clients to access large chunks of storage on the block level。

To accomplish this， we built high performance networks specifically dedicated to the management of data storage。

 storage area networks。In these dedicated networks。

 central storage media is accessed using highper interfaces and protocols such as Fichan or ISikazi。

 making the exposed devices appear local on the clients。

 appearing effectively as a blocked device using directly attached storage as's shown here on the right。

Another chunk carved out from the storage pool could then be used by a separate file server to build a new file system on and export that via NFS as illustrated here on the left。

Storage area networks are also specifically that networks。

 that is they can be configured in a true switched fabric using hardware that looks a lot like network gear。

 where it may use a variety of protocols to overlay storage communications on existing networks or build brand new separate networks。

 often using fiber optical connections。

![](img/59879360979ce405a8b8642a15d68ec8_11.png)

Now once you've internalized that the sand may be a fully switched fabric and can be used to make available both flexible block level storage as well as filele network storage。

 it comes as no surprise that you end up with yet another layer of abstraction and start to offer storage as a service in what else the cloud。



![](img/59879360979ce405a8b8642a15d68ec8_13.png)

Now here there's yet another set of distinctions that we want to make。One。

 services that provide file level storage and access as in the case of file hosting services。

 such as a Dropbox， Google Drive or Apple I Cloudud。Two。

 services that provide access on an object level， hiding file system implementation details from the client and providing for easy abstraction into an API with Amazon simpleimple storage service or S3 being the prime example。

And three， services that offer clients access on the block level。

 allowing them to create file systems and petitions as they see fit。

 such as obviously AWS Elastic Bstore or EBS。

![](img/59879360979ce405a8b8642a15d68ec8_15.png)

All of these categories have one thing in common in order to provide the ability of accessing storage units in a programmatic way。

 they offer a well defined API for access， oftentimes HETP or rest based。

On the service provider side， shown here in the bottom of this graphic。

 the storage model in use remains an opaque system to the customer。

They may use a storage area network to combine large numbers of distributed storage resources to present a large storage pool to the users as users of the system we really don't care and the storage magically appears as if are of the blue。



![](img/59879360979ce405a8b8642a15d68ec8_17.png)

We have already and will continue to see how this works by using AWS。

 but let's quickly illustrate the distinction between the object level and block level。First。

 let's take a look at S3。We create a new S3 bucket。😮。

And then recursively copy a bunch of files into it。



![](img/59879360979ce405a8b8642a15d68ec8_19.png)

And that's it， nothing else needed。It really couldn't be much simpler。Just like that。

 we backed up a directory full of files into cloud storage with the ability to inspect the contents via the command line and without having to worry about whether there is enough storage available。

How large our files are， or whether there are any limitations on how many files we can create。

Pretty neat huh？Well。Let's nu those files again。Goodbye。



![](img/59879360979ce405a8b8642a15d68ec8_21.png)

All right， next， elastic block storage。As the name suggests。

 this cloud storage method allows for access on the block level。

 meaning we get a device that looks and behaves just like a real disk。From an instance's perspective。

 this is really just a variation of directly attached storage because the virtual machine doesn't know nor care where the block device comes from。

And in fact， the regular AWS EC2 instance will utilize an EBS volume as local storage。As shown here。

What we see here is that we have a volume that is attached as a disc under De SDA1。

We can get more information via the Describe Vol command。

Which gives us the details about the volume size and some of the properties。But with EBS。

 we can always make new disks magically appear。

![](img/59879360979ce405a8b8642a15d68ec8_23.png)

Here， let's create a new four gigabyte size disk。Now， as a block level storage device。

 we can' directly write files to this。They would need to create a new file system。

 something we'll get back in a recommended exercise in just a minute。But for now。

 let this brief demoifies to illustrate what cloud storage can look like。



![](img/59879360979ce405a8b8642a15d68ec8_25.png)

All right， let's take a break here and recap what we covered。

We distinguished four primary storage models， directed test storage or D。

Network attach storage or NAS。Storage area networks or sand。And cloud storage。

We noted how these can be combined and may offer different kinds of access。

 although we primarily distinguished between block level access。

 where the device appears as if it was a directly attached physical disk。And file level access。

 where systems interact with a storage medium through a file system or API。

Each of these models has a number of implications。For starters。

 it's important to remember that even when we're dealing with magic storage appearing out of nowhere in the cloud。

 somewhere， somebody is managing a physical storage medium。Secondly。

 as we add layers of abstraction and allow for increased flexibility。

 we are changing the security model， a directly attached physical drive can only be compromised from that host or by physical access。

 but the network file server may be compromised well over the network， for example。

We also note that as we're combining the different models。

We may end up using or combining significant number of technologies and protocols。

We'll take a brief look at some of them in our next video。When we talk about inters and protocols。

Alright， this brings us to the end of this video segment before I let you go though。

 I'd like to leave you with a few recommended exercises and problems to help you deepen your understanding of what we covered today。

Try to research the details of some public cloud storage services such as AWS， Google Public Cloud。

 Microsoft， Asia， etc。Can you find out what storage solutions they might be utilizing on the back end。

 what kinds of scalability considerations do they have to make？Next。

 think about the different storage models we discussed and identify specific security problems。

Adjusted that each has specific implications， but what might those be in particular？And finally。

 heres a more specific exercise that I recommend in it。

 I'm asking you to create an EB volume attached it to an instance， create a file system， add a file。

 then move the volume to another instance to help you get more comfortable with elastic block storage and file system concepts。

Good luck。 And remember to ask questions if you are run into problems。



![](img/59879360979ce405a8b8642a15d68ec8_27.png)

Until next time， thanks for watching。