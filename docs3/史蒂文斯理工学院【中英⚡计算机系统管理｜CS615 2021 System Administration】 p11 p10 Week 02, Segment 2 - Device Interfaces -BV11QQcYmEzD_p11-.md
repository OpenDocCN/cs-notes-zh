# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p11 p10 Week 02, Segment 2 - Device Interfaces -BV11QQcYmEzD_p11-

Hello and welcome back to CS615 System Administration。This is week two， segment2。

 and after we covered conceptual storage models in a previous video。

 we'll next be talking briefly about storage devices and interfaces。As usual。

 this is merely scratching the surface on a much larger topic。

 but I hope you get a bit of a taste of the many layers and concepts involved as we talk about storage media。

Let's begin with Guzi， one of the older standards describing how to connect devices or peripherals to computers and transferring data between them。

The small computer system interface has been around for over 30 years and exists in the confusing number of implementations and variations。

Scazi used to be the default method to connect any peripheral device using long。

 white and generally unwielly ribbon cables and different types of connectors。



![](img/c34ca040b7bbf476b0353cb052165c3e_1.png)

Here's a Sczi drive， but different devices may use different connectors and require different cables。



![](img/c34ca040b7bbf476b0353cb052165c3e_3.png)

Scazi has now largely been obsoleted by the advanced technology attachment or ATA standards。

 but still lives on in the IScaI standards specifying storage connections using the Szi command protocol over IP based networks。

 a common choice in storage area networks。Another variation we'll see in a few minutes is the more serial attached Sczi Sas or a sczi over fiberchan protocol。

The ATA standard on the other hand， is often equated with the integrated device electronics interface or IDE。

You may have seen parallel ATA using flat wire ribbon cables that make it impossible to wire multiple drives in such a server case。

 although nowadays， fortunately for segmentss in their hands， serial ATA or SaA is more common。

These are your typical hard drives， which are named Inegrated device electronicics because the drive includes the controller。

 integrating some of the complexity carried on the motherboard and separate controller and Szi。

That is， the drive includes a controller circuit， as well as a few bits of firmware to facilitate the access。

Now we're talking about a fairly low level connection here。

 but now is as good a time as any to remind you that security affects everything。

A few years ago became public that the NSA was capable of implanting malware in the firmware of hard drives。

 which included an API and the ability to read write arbitrary information into hidden sectors on the disk。

This is a really difficult threat to protect against and a good reminder of the fact that just about anything can be compromised。

Specifically， it helps us consider that words have meaning and that the name integrated to Vi electronics implies that there is not just a bit of rather helpful magic sitting there。

But don't fret， not every hard drive is necessarily compromised and you are not necessarily likely to be on the target list of the NSA。

However， for several reasons， including security， but more likely performance。

 you made a wish to move away from IDdeE drives。Perhaps towards solid state drives or SSDs。

An SSD drive puts away with having mechanical rotating magnetic plas on which to store data。

 and instead uses integrated circuits to store data persistently such as flash memory。

These drives are significantly more resistant to physical shock。

 more silent and have less latency than IDE drives。

 which is why your cell phone most likely uses SSD for storage。

While still more expensive than traditional mechanical heart drives。

 you nowadays find more SDD or flash memory and use even in the server market。

These will still use the SaA standard to connect， but may also be combined into larger storage devices which then might be connected externally or over a storage area network using。

 for example， the fiber channelnel protocol。Fibber channel is usually used in a switched fabric。

 meaning it looks and behaves a whole lot like your normal switched Ethernet network。

And utilizes optical fiber cables shown here on the top right。

 although you can also run it over a copper wires。Now if all these different technologies and not enough for you。

 you also want to consider that in just about any but the most simple environments。

 all of these are combined in some form when storage and networks are created。That is。

 you will likely find a multilayed stack of protocols building on top of the fibergen protocol。

 which might be utilized in a pure optical fiber channel network。

 an ethernet network on top of regular TCPI and so on。Similarly。

 the scy protocol may be used on top of either one of those or over something like remote direct memory access over a sient fiinnne band。

That is， we have all sorts of means to piggyback doors protocols on top of other protocols。

ATTA over Ethernet for example， allows us to reuse our existing ethernett network and turn it into a storage area network by encapsulating ATA frames into Ethernet frames。

Fiber channel over Enet is the same， but for the fiber channel protocol and thus gives you an idea。

 a trend whereby folks realize that hey， we already have a working network here。

 let's just make it carry block level instructions as well。So you really get anything over Enet。

 which makes things quite easy， but also notably implies that the storage area network you build in this way is restricted to the same layer to network segment and as it runs on that layer has no inherent security properties。

😊，So you can then try to push things up this stack by using， for example， Iikazi。

 which includes authentication and can be wrapped in IPec for example。And of course。

 we can take it up a notch and move on to a serial attached Szi， which we mentioned earlier。

 image nowadays is used in huge storage arrays， such as this one。

 offering efficient high speed storage access using the Szi commands and protocol on modern hardware。

But true to its s heritage， SAS， of course also suffers from no shortage of confusing variations and connectors。

As you can tell， the opportunities to broaden your understanding or to specialize in storage technologies and protocols are not limited in any way。

As a quick look at how technologies have advanced， note how performance throughput has increased over time and by protocol。

You see all the technologies we've mentioned so far in this scroll， increasing bit rates over time。



![](img/c34ca040b7bbf476b0353cb052165c3e_5.png)

Noting the introduction of fiber channel with around 100 megabyte per second。

And then moving forward with the various over ethernet variations。

Now going over gigabit Ethernet and eventually over 100 gigithsonnet， which is really pretty slick。

So this addresses the bit range for throughput。But just how many bytes can we store on the different media？

Well， the individual IDEri has come a long way from the roughly 5 megabyte drive costing around $1。

500 in 1980， hasn't it？I remember well when we built server with 500 MBby drives when eventually a 10 gigy drive was considered huge。

 but of course nowadays that's nothing。In fact， the price of storage for IDE drives has gone down so much that you can now buy an 18 terabyte drive for just about $600。

18terbyte and a single IDE drive， that's just amazing。



![](img/c34ca040b7bbf476b0353cb052165c3e_7.png)

So yeah， in a way， upgrading your individual disk drive is an example of scaling vertically。

 as we discussed in the previous video。😊，But even if 18 terabyte is not enough for you。

 because as we established， this usage expands to fill all available space。

 you can consider just getting a whole bunch of them and hooking them up one by one。

There'll be a disk configurationfiguration commonly referred to as a JBd， just a bunch of discs。

 which is exactly what it sounds like。You'd buy a bunch of drives。😮。

And there you go now there's a fair bit of overhead on your server because you have 15 individual disks。

 but it's certainly an approach that might represent horizontal scaling with all its implied drawbacks。



![](img/c34ca040b7bbf476b0353cb052165c3e_9.png)

Or perhaps a better approach might be to take all of these BP exhaust drives and put them into a rate controller to then combine them into a single volume。

 in effect， combining the vertical and the horizontal scaling approaches。

We'll talk a bit more about rate in our next video。

 but of course nothing requires us to use IDE drives for this approach。

 we could instead use SSDs right like this one。This is a 100 terabyte solid state drive。

100 terabyte and a tiny 3。5 inch form factor。Only problem。This will cost you a cool $40，000。Yep。

 you heard that right， $40，000 for 100 terte STD。Well， STDs are more expensive。

 but they also are a lot faster and reliable than HDs， so talk about scaling vertically here。

And now imagine scaling that horizontally as well into a storage appliance that combines SDDs or flash memory like this net up all flash arrays shown here。

Again， as you can see， there are countless ways to combine things to provide you with the right solution for your storage needs。

 with each carrying its own advantages or disadvantages。

And so there's no single simple solution to save， you should buy X or you should use Y。

What the right solution is depends on your specific requirements。

 as well as as we've just seen your budget， skys the limit。Okay。

 I think we're going to take a quick break here。Next time we're going to be talking a bit more about rate and logical volume management。

 as well as the physical aspect of a typical HDD。But before we go there。

 I'd like to leave you again with another exercise。

Let's pretend you're a S app in working at Stevens and you have to replace the current storage system we use for the home directorories on Linux La。

What solution would you propose？Now， obviously you're lacking a lot of information to make this call。

 but on the other hand， you can probably make an educated guess on the storage needs based on the observed usage。

Try to spec a solution and then see how much they will cost you。

 then consider that as an academic institution， you are likely bound by a budget with certain limitations。

Finally， consider what implications your choice might have on the rest of the computer environment。

Okay， I think this would keep you busy until the next video， see you then cheer。



![](img/c34ca040b7bbf476b0353cb052165c3e_11.png)