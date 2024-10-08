# P22：Lecture 22： Transactions (Con't), End-to-End Arguments, Distributed D - RubatoTheEmber - BV1L541117gr

 Okay， let's get started。

![](img/8aaba7373c703fc51f66e8bca6497145_1.png)

 So this is lecture 22 and we're going to talk about reliability。

 Then we're going to dive into transactions， get into the end-to-end argument and then。

 talk about distributed decision making if we have enough time。

 So remember that we have the file system buffer cache and the role of the file system buffer。

 cache is in caching disk blocks， right？ Because the time to access memory， 100 nanoseconds。

 The time to go out to disk， millions， tens of millions of nanoseconds。

 So we use memory as a cache for the disk in the form of the buffer cache。

 And so we cache all sorts of things， right？ We cache data blocks。 We cache i-nodes。

 We cache directory blocks。 And we cache important metadata structures like our free fit map。 Okay？

 Now there's some important abilities that we want to talk about today。

 The first ability is availability。 And it's the probability that a system can。

 let's get rid of this。 There we go。 Okay。 It's the probability that a system can accept and process requests。

 We typically measure this in terms of nines of probability。 So a 99。

9% probability of being available is called three nines of availability。

 So at times you'll see someone offer a service level agreement。

 And they'll say the system will be available with three nines of availability。 That means 99。

9% of the time the system will be available except and process requests。 Now。

 how do we get availability？ The key idea here is independence of faults。

 The one component failing doesn't cause the entire system to go down。

 We'll dive into this more in just a moment。 Now， durability is the ability of the system to recover data even in the presence of faults。

 and failures。 So this is really fault tolerance applied to our data。

 Now one of the things that can be confusing here is what it means is that the data is， preserved。

 It does not necessarily mean the data is accessible or available。

 So for thousands of years there have been hieroglyphics carved into the side of the pyramid。

 But it was fairly recently with the discovery of the Rosetta stone that we were actually。

 able to read what those hieroglyphic said because the Rosetta stone was basically gave。

 us a translation table。 Showed examples of text written hieroglyphics and text written。

 I think it was in Greek。 So the data was there， it was durable for thousands of years。

 but it wasn't available。 So that's why you separate the notion of durability and availability。

 Now a lot of times， you know， like a cloud provider or， you know， some service provider。

 will say we provide high availability。 So the system is up and processing your requests。

 But they don't tell you is whether it's actually processing those requests correctly。 That really。

 the question you should ask is what is the reliability of the system。

 The reliability is the ability of a system or component to performance required function。

 under stated conditions for a specified period of time。 Now that sounds super formal。

 that is because that's the formal IEEE definition。 And so this is much stronger than availability。

 Because it means that the system isn't just up and accepting and processing requests， but。

 also that it's doing so correctly。 Right。 And so there might be some bug in that service and if that's that service is accepting requests。

 and processing those requests and corrupting data and giving garbage back as results。

 Technically the system is available。 It's processing the request。

 But you wouldn't consider that system to be reliable。 So like for example。

 when we think about a space mission， like the Apollo missions to， the moon。

 they looked at not just the availability of the computers on that mission， but the。

 reliability of those computers could function for correctly for a two week period with a。

 high degree of probability of that being true。 Okay。

 so this means we have to take a really holistic view of the system。

 We have to make sure that the data survives and crashes of the system and failures of media。

 like this crashes and any other potential problems that they could there could be。

 The same kind of reliability applies to airplanes。 Right。

 We want to guarantee that the plane is not just simply available。

 The flight computers are not just simply available， but they're correctly processing the， data。

 Okay， so let's start talking about some of these LEDs。 We're going to talk about durability。

 So how do we make something like a file system more durable？ Let me make sure and pull up my chat。

 Okay。 All right。 So we do it at a number of different levels。 So one at the lowest of levels。

 the disk blocks contain read Solomon error correcting codes， or ECC。

 And these are used to deal with defects on the drive。 Now we could try and make a hard drive。

 but if the ferrous oxide coding on it， absolutely， perfect。

 And manufacturers strive to make it as perfect and as uniform as possible。 But that's difficult。

 That's expensive。 And so there's a trade off on how well I do in terms of making it perfect versus errors。

 And so the error correcting codes are a way of dealing with some of those manufacturing， effects。

 Also， as Cooby talked about last time， you know， I jostled my laptop or other device that。

 has a hard drive in it。 And those heads that are floating。

 it just microns above the surface can impact the surface， and damage the media。

 And that can lead the data。 Error correcting codes may be able to recover the data in those cases。

 So the second thing that we need to do for file systems is to make sure that writes survive。

 in the short term。 So once we get writes onto the hard drive。

 the argument is they'll survive long term。 We'll use things like ECC and other techniques to make the data durable。

 But we still have to get from the application out to the drive。

 And so either we have to think about when an application does a write， instead of treating。

 the buffer cache is right back， we treat it as right through。

 So when we return back from the application， the data is durable， persistent on the hard， drive。

 Now why might we not want to do that？ Well， at the very beginning。

 exactly what I said was the role of the buffer cache。

 It's dealing with the difference in it taking 100 nanoseconds to access main memory versus。

 10 million nanoseconds to access the disk。 So if we want to use write through， we might as well。

 you know， we've given up a lot of， the benefit of having a buffer cache。

 So the alternative is to do something like use some kind of battery backed up RAM or。

 nonvolatile RAM and store our writes there。 And so that's what a lot of servers will do。

 They'll have a special area of nonvolatile or backed up RAM， battery backed up RAM， where。

 writes get queued。 And so that way they can immediately return back if the system crashes。

 when it comes back， up， we just continue writing those blocks out to the disk。 Okay。

 so now we need to make sure that the data survives in the long term。

 And simply writing it to the disk is not really going to be enough。 Why？ Well。

 disks have a mean time between failure time of around 50，000 hours of operation。

 That's a pretty long time， but that's actually not that many years of continuous operation。

 So eventually the drives are going to fail。 And I'm sure all of you have encountered the situation where our drive failed。

 Right？ And so what can we do？ Well， we can do replication。 We have more than one copy of the data。

 That way if a drive fails and we lose a copy of the data， we have another copy that we can， go to。

 But the important thing to hear to think about again in terms of durability is independence。

 of failure。 All right， so I could put two hard drives into my computer。 But if my computer fails。

 right， then I lose both of those drives， potentially。

 There's a-- I could put it in a drive in a separate computer in my machine room。

 But if I have a fire， I could use-- lose both of those servers。

 I don't know if the building gets hit by light or hit by a tornado。

 So maybe I put them on different continents。 Right？ And so then， you know。

 it takes something like an asteroid striking the planet for me， to lose both copies。

 And at that point， I probably had bigger things that I'm worried about。 All right。 The key thing。

 and this is what a lot of the cloud providers think about， is how do I。

 ensure independence of failure？ So when you use Berkeley Mail， powered by G Suite。

 when you press Send， Google before， it unquix that Send button。

 guarantees that it's copied your message to servers in three， different data centers。

 which may not even all be in the same content or country。 Yeah。

 So that even if there's a failure of one or more of those data centers， your email message。

 will still be delivered。 It will still be a copy that they can access。 OK。

 So let's look at some different approaches。 Yes。 So the question is， what is battery background？

 It's just what it sounds like。 So it's a special memory module where there's a battery attached to it。

 So even if power is lost to the machine， like the server， the contents of that memory will。

 be preserved。 Another example would be an SSD or the flash memory that's in an SSD。

 I can turn off the power and it will still preserve the charge。

 There it's done by maintaining that charge within the actual flash memory cell。

 But before those were actually cost effective and popular， what people would do is just。

 attach a battery to some memory。 Now， cautionary tale happened here in the department。

 We used to have a big file server where all the projects stored， their research and all。

 our home directories were located and all。 And it was on a server that had a battery backed up memory region。

 Well， batteries fail after some number of years。 And after some number of years， the battery failed。

 Now these servers are really smart。 They have lots of monitoring。

 And so it detected that the battery had failed。 And it dutifully logged in the log that the battery had failed。

 No one ever read the log。 The server was on a UPS， but the UPS failed。

 getting to independence of failure。 And power went out。

 But power only went out for a few milliseconds。 It was literally just the light flicker and everything was good。

 except it wasn't。 Because in that small amount of time， the server lost power。

 that battery backed up memory， where all those important rights were being stored was lost。

 Now think about file systems。 What data do you think is going to be in that battery backed up memory in our buffer cache？

 Any ideas？ I'll go back to my picture。 It's all of the important stuff， like the free bitmap。

 like the directory blocks， the， i-nodes， the i-node table。

 all of the information that tells you where to find stuff in the file， system。

 And in a few milliseconds， that data was lost。 We had backups。

 But it turns out people added more disks to the server and had forgotten to add those。

 disks to the backup groups。 There were groups that lost all of their research and individuals who lost all of their。

 research。 It's a cautionary tale， it's actually really hard to have full independence of faults。

 Okay。 So first type of replication I want to talk about is a technology developed here at Berkeley。

 and now a $1 billion a year industry， which is RAID。

 RAID stands for redundant array in expensive disks。

 The argument was I can either try to make a disk that is super ultra reliable， but then。

 it's also going to be super ultra expensive。 I could use the best of the best titanium。

 gold plated and beryllium components and get， some insane mean time between failure out of them。

 But it's going to be priced out of everybody's price range。

 So instead what I'm going to do is I'm going to just take commodity drives with their 50，000。

 hour mean time between failure。 And I'm going to put them together in an array。

 By putting them together in an array， I'm now going to put them in these recovery groups。

 and duplicate the data。 So instead of going out and buying 110 terabyte drive。

 I'm going to go out and buy two 10， terabyte drives。

 And each disk now is fully duplicated onto its shadow。

 So we'll say the green disk is the primary and then the pink flash purple disk is our shadow。

 So this is really great for high IO environments and high availability environments because to。

 lose the data， I have to lose both of the drives。 And now we're looking at the probability of a double drive failure instead of just the。

 probability of a single drive failure at any given time。 But it's really expensive， right？

 Instead of having 10 terabytes， I now have to go out and buy two of these drives。 But they're cheap。

 And they're cheaper than making a 10 terabyte drive that would be super ultra reliable。

 So the trade off is the bandwidth that I get for rights。 Right？ Because when I do a logical right。

 I actually have to do two physical right。 I have to write to both drives。

 And so when these first came out， there were these like wires that went between the drives。

 that were like servo wires and they perfectly would synchronize the rotation of the disk。

 so that the same sectors were under the same head on the two drives。

 And so when you're doing a right， you can simultaneously do the right through the controller。

 Now modern versions of this don't do that。 And so there's a cost because they're going to be slightly out of phase with one another。

 And so there's going to be a cost， a higher cost for doing those rights。

 Reads on the other hand are optimized。 If I have a high read workload， then RAID 1 is great。

 Because I can read from either drive。 I can read from both drives in parallel。

 So I can send half my reads to one drive， half my reads to the other。

 I've effectively doubled my read capacity between the two drives。

 Now what happens when a disk fails？ I just simply unplug that disk and replace it with a new 10 terabyte disk。

 And now I copy all 10 terabytes from the disk that's still working over to the disk that's。

 brand new。 Now what happens if a failure happens in the middle of the night？

 Well now there's this vulnerability window between when that failure happens and when。

 I complete copying all of the data。 What happens if that other drive fails？

 Well then I lose all my data。 So to close that window down， I can have a hot spare。

 So now instead of going out and buying a 10 terabyte disk to store 10 terabytes of data。

 I'm going to go out and buy three 10 terabyte disks。 One is a primary， one is a shadow。

 and one is a hot spare。 So that gets really expensive to store the data。

 But it still is again less expensive than if I tried to over-engineer a drive to get a。

 very high meantime between failure。 Okay， so let's look at sort of the other spectrum of RAID。

 There's lots of different ways we can do RAID。 But one of the more common ways of doing RAID is what's called RAID 5。

 And I say RAID 5 plus because this is the technique that's used for the higher versions， of RAID。

 So the idea here， and I'm going to go through this slowly， we're going to take the data。

 and rather than saying all the data is going to go on one drive and then all the backup。

 the redundant data is going to go on the other drive， I'm going to have an array of drives。

 So here I have five disks。 And I'm going to stripe the data across those five disks。

 Now I could have more than five disks， I could have 10 disks， I could have 12 disks， any number。

 but the idea is I'm striping the data across the drives such that block zero。

 goes on the first drive， block one goes on the second drive， block two goes on the third。

 block three goes on the fourth。 And then the next block for this group is a parity block。

 And I compute the parity block by XORing the data blocks。 And then I repeat。

 So now here I have my next data， my next data， my next data， and here we should actually stripe。

 the parity。 So there are versions like RAID 5 where you just have one drive that's your parity drive。

 But the later versions you stripe the parity across。 So not one disk is like your parity disk。

 And there's a bottleneck。 So now I can read in parallel for block one， block two， block three。

 and so on。 Now when a drive fails， what happens？ Let's say， I don't know。

 we'll say that disk refails。 All right， well if disk refails。

 we can reconstruct the contents of disk three by XORing the blocks， on the other drives。

 So block D2 is just simply D0， D1， D3， and P0 XOR together。 Block D6 is just D4， D5， P1， D7。

 XOR together。 It's like I can very quickly， or I can recover all of the data that was on this particular。

 drive。 All right， now in this case， you know， typically you'll find these in like a network approach。

 appliance that sits in your server in the box。 But you could imagine that I could actually spread these disks around the globe。

 Of course there's going to be a trade-off， right？ Because speed of light is finite and so I'm going to add latency to the time it takes。

 to do reads。 But I could get more independence of failure if the data isn't stored all in one data center。

 that could be hit by a tornado or hit by lightning or an earthquake。 Okay。 So now in general。

 the raids are some form of a ratio code， right？ So assuming we have some way to tell a disk is bad and we do because we could look at the。

 error correcting codes that are used and see， do we， are we unable to recover from the errors。

 that in a block？ So we can tell when a drive has failed and that's considered an erasure。

 And so erasure codes correct for erasure。 So erasure correcting codes。

 So it turns out today our disks are really large。 All right。 So I said 10 terabyte。

 I think you can go out and buy like a 12 or 16 terabyte drive。

 It takes a really long time when you have one of these failures to read all of the other。

 drives and reconstruct that 10 terabytes of data that was on disk free。

 And so now we have to actually look at what's the probability that I'm going to suffer another。

 drive failure while I'm rebuilding disk free。 So let's say， I don't know， disk for phase。

 What happens if disk for phase while I'm doing my recovery？ Oof， that goes my 10 terabytes。

 I have no way to recover it because the XOR is only good for one drive having failed。

 And so while this was really good when drives were small and， you know， drives were hundreds。

 of gigabytes， like a terabyte or something like that， I could recover from a failure in。

 a few hours。 Now we could take many hours or over a day to recover from a failure。 During that time。

 with something like RAID 5， I'm vulnerable to another drive fail。

 Now I don't have time to dig into it， but if you look at， you know， the failure curves， for drives。

 drives tend to immediately fail or they tend to fail around their mean time， between failure。

 And if you buy drives from a manufacturer， like a distributor， you tend to， and you look。

 at the serial numbers， you'll see oftentimes they're like sequential。

 They all came from the same production batch， which means they all have the same rough。

 and if there are any issues or anything like that， the same mean time between failure。

 But turns out it's actually very likely if one drive fails that you're then going to。

 suffer a second drive failure。 So when we go out and we build a network of arrays of storage in my group。

 we actually， go to multiple distributors so that we get drives from different batches。

 We reduce this kind of sibling behavior that you see in failures。 But it's still not perfect。

 and so that's why we use things like RAID 6， which is a more。

 complex code that allows two of the drives in the strike to fail。

 So then you combine that with hot spares， and so if a failure occurs， you can immediately。

 start rebuilding the array and close that window of vulnerability to multiple drive failures。 Yeah。

 question。 Yeah， so the question is what about RAID 0？ So RAID 0 is a recipe for disaster。

 Is the polite way of saying。 So RAID 0 is just I'm going to take my two drives。

 And rather than using one as a backup for the other， I'm going to treat it as what they， call JBOD。

 just a bunch of disks， one giant of disk blocks， one giant disk。 So if either drive fails。

 I lose my data。 So RAID 0 was only used because people wanted for mistaken reasons to create larger disk。

 pools where they could have a really big file or something like that。

 But the value was really bad because if either drive fails， I'm going to lose this really。

 large file。 So nobody uses RAID 0 unless you really want to play with fire。

 RAID 1 is probably one of the most common ones。 A lot of a low end。

 two bay drive naz is that you can buy for your desktop are basically， doing RAID 1。

 You just mirror for one drive to the other。 And then if you have a number of drives like you have five drives。

 then you can do four， drives even， then you can do something more complicated。 Okay。

 so you have these more complicated erasure codes for something to be able to tolerate multiple。

 disk failures。 And you can see that in the reading。 So in general。

 erasure codes are things like lead-solving codes。 So the things that we were applying at the bit level。

 we can also apply those at the block， level and have a way of basically encoding it so that we're encoding some number of fragments。

 So we can encode our data， we can take our data， chunk it up， and then encode it into。

 a set of fragments。 And then we only need m of those chunks in order to be able to reconstruct the data。

 So we're replicating the data， but this is increasing our durability because now we have。

 to erase more chunks before we would actually lose the data。 So in the example here。

 if we split the data into m equals four chunks and generate 16， fragments。

 Then any four of those fragments can be used to reconstruct the original data。

 So that makes it incredibly durable。 But it comes at a cost of there's an overhead associated with that。

 Now we can take this even further and make it really hard to destroy all the copies or。

 a large number of the copies by taking and replicating it across a geographic region。

 So this gives us great performance for reads because I only need to read in the simple case。

 a copy if I just replicated it at the copy at the full file level。

 Or I just need a fraction of those fragments in order to be able to reconstruct the original， data。

 But it doesn't work as well for writes。 Because when I do a write。

 I need to be able to update all of the replicas。 I want to change some value in a file。

 I have to update all of those fragments across all of those replicas。

 If any of those replicas are down， then I'm faced with two choices。 One is the system stops。

 That impacts availability。 The second choice is I use some kind of relaxed consistency model。

 So for example， I can put version numbers on the fragments and then write them out。

 And then when I'm reading back， make sure that I'm reading the latest version of the， file。

 There's all sorts of protocols that I can use to try and ensure that I'm reading the。

 latest version of the file。 And then eventually if the replicas come back up。

 I can make them consistent by updating， them with the rights that they've missed。

 But it adds a lot more complexity。 But this is what a lot of the cloud providers actually use。

 Again， they take your data and they replicate it out in these fragments。

 And then they support the notion that one or more of those replicas might be unavailable。 Okay。 Now。

 to get true reliability again in this context， we have to think about all of the， components。

 We have to think about availability。 Are the replicas available and able to process results？

 We have to think about security。 If a worm or virus comes in。

 we don't want it corrupting our data by encrypting all of。

 our data and encrypting all of our fragments。 Then our data is not available， not durable。

 not accessible。 And then of course you have to think about all of the possible faults。

 So it actually turns out that a lot of effort has gone into designing cloud infrastructures。

 And it's really interesting when there's an outage， like you can go to like Google's。

 status page or you can go to Amazon or Microsoft。 A lot of times they'll have after action reports。

 after a failure。 And it's really interesting to kind of dive into those and see what went wrong。

 What was the critical thing that caused Google to go offline for three hours one day？

 And it's oftentimes innocuous things like someone made a configuration change and made， a mistake。

 It broke things and there was no way to roll it back。

 Or an authentication server that no one realized was core to the entire worldwide operation。

 went down and brought everything down。 Those are just some of the examples of things that have caused worldwide outages。

 Okay， so how do we make a file system more reliable？ So if we think about file system reliability。

 there's kind of a difference from what we， have at the block left。

 So we talked just now about how do we make our blocks durable。

 Now we want to make our file system durable and reliable。 So we want correctness as a component。

 So what happens if a disk loses power or your operating system， blue screens or crashes？ Well。

 there's some operations in progress that might actually complete。

 So if I'd send stuff to be written to the disk and the disk controller still has power。

 but the operating system crashed， well， maybe those writes still make it out to disk because。

 they're in some disk buffer on the physical drive and not just in some operating system， buffer。

 But some of those operations that are in progress might get lost。

 And I interrupt the power and writes that were occurring just don't occur instead。

 So I might have a block that I was writing on the disk that's only partially written， doesn't。

 get fully written。 And the thing is having something like RAID isn't necessarily going to protect us against。

 these failures。 Right？ There's no protection against an application or an operating system writing bad state。

 RAID will dutifully protect that state that you've written， but it's bad state， garbage。 Right？

 There also can be errors and issues with RAID controllers themselves， where maybe one of。

 the disks in the RAID group doesn't get correctly written because there's a bug。

 So the file system needs to have durability。 And kind of as a minimum， right？

 If the file system's not durable， it doesn't matter if the blocks in the disk are durable。

 because we won't know what those blocks mean。 And that's exactly what happened when we had the power failure with the storage。

 The data was all there on the disks， on terabytes worth of disks。

 But we had no idea what block belonged to what file。 And so for all intents and purposes。

 it was lost。 It was gone。 It was unrecoverable。 Okay。 So we want durability where， you know。

 maybe we have to do some recovery actions after， you， know。

 a failure occurs after an operating system crash after a power system failure。

 We might have to do like some kind of disk checking file system checking operation in。

 order to reconstruct the state of the file system。 But durability alone is not always quite enough。

 Okay。 So now if we think about it， right， we do a single logical file operation， like a right。

 We're touching many different physical disk blocks。 All right。

 we touch the i node because maybe we need to allocate it。 We touch indirect blocks。

 We touch direct blocks。 We touch the data block。 We have to touch the bitmap that tells us what blocks are in use and not in use and so。

 on。 And then we have sector level remapping that might be being done by the underlying drop。

 And if blocks contain multiple sectors， when I actually do a write， I might be writing over， here。

 writing over there， writing over there to write the same one block。 Right。

 because it's been remapped due to data defects on the drive。 So at a physical level。

 operations are completing one at a time。 I do a sector write， I do another sector write and so on。

 We want concurrent operations for performance， right？

 Concurrency always allows us to get performance out of being over being able to overlap IO computation。

 and so on。 So how can we guarantee consistency for our file system even if some crash occurs？

 Well the thing about that， we need to think about what might be affecting our reliability。

 What are sort of the threats to the reliability of our file system？

 So some of the threats that we're going to face are interrupted operation。

 So crash occurs and power failure occurs during the middle of updates to our file system。

 And that could lead the data that we've stored in some inconsistent state。

 Some of the data was written， some of the data wasn't， maybe some i-node was updated。

 but the directory wasn't， or the free block wasn't， and so on。 An example， you know。

 sort of at the logical level is I want to transfer $100 from one bank。

 account to another bank account。 The power failure occurs in the middle。

 What happens if I'd already taken out the $100？ But I hadn't deposited it in the other account。

 $100 just disappears。 The bank's books now don't reconcile for the branch。

 don't reconcile for the account， and， so on。 There's also the loss of stored data。

 So if we have a disk that fails， we saw how we can address some of that with things like。

 RAID and a ratio occurs。 So there are two approaches that we see in our file systems to try and get reliability。

 The first is to have a careful ordering and a recovery process。

 And the second is to do some kind of versioning and copy on write。 So in the first case。

 and this is what's used by the FAT file system。 It's also used by the UNIX FastFile system。

 So in the FAT file system， we have check disk and in the FAT file system， we have the file。

 system checker， FSCK。 And what happens is that each step we build the structure of the file system。

 that we're， like write a data block， then we write the i-node， then we write the free list， then。

 we write the directory entry。 And then the last step is what links it into the file system when we add it to the directory。

 And if a failure occurs， we just simply rescan looking for these incomplete actions。

 Like maybe we only wrote the data block and the i-node， but we didn't update the free。

 list or we didn't add it to the directory。 In the versioning case。

 it's used by ZFS and OpenZFS and some other file systems。

 We've versioned the files at some granular。 And so we're going to create a new structure that links back to the unchanged parts of。

 a file， like if we're just appending to a file， and then the new parts of the file。

 like that append that was the write that we just did to a file。

 And that last step is going to declare that the file is ready for use。

 Let's look at that first approach where we use a careful ordering。

 So here we think a lot about the sequence of operations， and we always execute those。

 operations in a specific order。 And we assume failures will occur and could interrupt that process。

 And then after a crash， as part of the operating system booting up， we're going to run a recovery。

 process。 And so this is why， like， you know， if you have a Mac or something like that， you'll。

 notice sometimes， like if your operating system just crashes， when it comes back up。

 it takes a long time to come back up。 What booting doesn't actually take that long？

 Booting takes seconds。 What is it doing？ It's running this recovery process where it's checking the disk to see where their operations。

 in progress that have left the file system in an inconsistent state。

 And the time that takes is going to be proportional to the fraction of the disk that you're using。

 If you're like me and you have a large hard drive in here or a large SSD in here and it's。

 very full， those operations can take a long time。 Okay。 So again。

 this is the approach taken by the FAT file system and by Berkeley FFS to protect。

 the file systems and metadata。 Now notice I said file system and metadata。 I did not say data。

 So this approach does not protect the data that's stored by application。

 And so it's up to application developers to come up with their own recovery mechanisms。

 And we'll look at those more in just a moment。 But there are things like Word and EMACs they autosave to a different file。

 And so that way if there's an interruption， you can always， you know， come back up and， it'll say。

 oh， you know， there's an autosave version。 You want to use that instead of the version that you tried to open。

 Okay。 So let's look at how it works in the Berkeley FFS file system。 So in the normal case。

 we allocate a disk block， write the data block， allocate an i-node， write the i-node block。

 and then we update the bitmap of free blocks and free i-nodes。 And then as a last step。

 we update the directory with the file named i-node number mapping。

 And then we go and we update the modified time for the directory since we just added a new。

 file to it。 Okay。 Now on recovery， what do we do？ We scan the i-node table。

 If we find any unlinked files， the files in which there's an i-node allocated， but there's。

 no directory entry， what we do is we can， I'm too choice。 We could delete it。

 but maybe that was somebody's important。 That was somebody's thesis。

 That was somebody's CS162 project。 So rather than delete that file。

 what the FFS file system and many other operating systems。

 do is they put it in a lost and found directory。 If you go and look in your Mac。

 you'll see that there's a lost and found directory。 That's where， like。

 files that are unlinked get put。 On the FFS file system， it would be files that have an extension。

 or I think like CHK or， something like files， 000。chk。

 So then you could manually go look at the contents of the file and realize， "Oh， this。

 is something really important，" and then manually link it back into the file system structure。

 Or if it was garbage or a temporary file， you could just simply delete it。

 Then we compare the free block bitmap against the i-node trees to see if， again， there。

 were blocks that were written， but they weren't actually allocated to i-nodes。

 And then we scan directories for any missing updates and then update the time and access， them。

 Again， the time to do all of this is going to be proportional to the size of the file system。

 which is proportional to the size of the disk， assuming the file system fills the disk。

 So it can be a very expensive operation if you have a very large drive。 So， yeah。 Yeah。

 so the question is， "What happens if we crash after we allocate the i-node but。

 before we write the data？"， So in that case， oh， after we write the data before， yeah， yeah。

 So if we crash after we write the data before we've gone and allocated the i-node， then。

 the data will be lost。 Because we haven't marked in the bitmap that the data is the block is in use。

 We haven't attached it to any i-node。 And so in that case， it's just simply lost。 So that's why。

 like， at the application level， you might do things like Word might make two， copies。

 So it has the autosave copy and the original copy。 And I'm doing a save。

 I'll save to a temporary file。 And then after I complete the temporary file， right。

 I'll then go and take the original， file， rename it to something。

 And then I'll note that's a file system operation， so it's atomic。

 And then I'll rename the temporary file that I just wrote to the original file。 So that way。

 if I have a crash anywhere in there， there's either the autosave file or， there's the old file。

 And so I have something I can recover to。 But sometimes you get corruption during that autosave process and now you end up with。

 you， know， you end up with nothing。 You end up with the original file。

 which if you're not saving frequently， it could be， very old。 There's a lot of questions。

 I'll start here。 Yeah， so the question is why do we update the bitmaps last？

 So we want to fully fill out the data structure before we then say we're allocating。

 If we allocated the bitmap first， then we might have a data structure that was incomplete。

 And so we'd have to throw it away anyway。 Yes， the question is what if we're allocating a file and we're writing to the same block。

 So again， we're not protecting the data blocks。 We're only trying to protect the file system integrity to make sure that the file system。

 at the end of the day contains is contains integral pointers to disk to data on the disk。

 and files on the disk。 And there's nothing incomplete or inconsistent in the file system that doesn't again protect。

 us against， you know， writes to data blocks that don't make it out of the buffer cache。

 It doesn't protect us against incomplete writes to a data block because I was in the middle。

 of writing a data block。 We'll look at other approaches that will give us those kinds of protection。

 But they come out of cost。 There's always a trade-off question。 Okay。 Any other questions？ Okay。

 So let's look at the second approach， which is a copy on write。 So if you think about it， right。

 the multi-level index structure that we have， let's just figure。

 out where all the data blocks are for a file。 We have the direct pointers。

 We have the indirect pointer blocks。 We have the doubly indirect blocks， the triply indirect block。

 And instead of overriding the existing data blocks， why don't we just simply update the。

 index structure？ So we'll reuse all of the index blocks that are unchanged。

 We'll reuse all of the data blocks that haven't changed and only update parts of the structure。

 that have changed。 That's why it's called copy and write。 So that seems kind of expensive。

 Like it seems like we're doing a lot of duplication， but we're really not。

 Because one of the things we'll do is we'll batch updates。

 Rather than trying to do every single update， we'll do this kind of copy on write， we'll。

 batch together a bunch of updates， and then make the change。 All right。

 So this is the approach that's taken in a lot of network file server appliances， the。

 Waffle file system from NetApp， ZFS and Open ZFS uses approach。

 So here's what copy on write looks like。 And in this case。

 I simplified things by using small write blocks in our tree。

 But our file is just represented as a tree of blocks。 So here's our old version pointer。

 The points to this index block， which points to another index block here and another index。

 block here。 This points to an index block here that points to one of the extends。

 Here's another extent， another extent， and so on。 And the writes。

 let's say we're appending to the file。 So we really just need to update this leading fringe of the file。

 So we can do that right。 Right？ So we'll write to it。

 And now we're going to copy that the rest of that file。 We're not going to actually copy it。

 We're just going to copy the pointers and as much of the existing data structure as， we can。

 So if you think about it， what needs to change？ Well， certainly this needs to change。

 This index block would have to point to here and point to here。

 So we're going to have to duplicate that。 And then we're going to need a new index block for this。

 And we're going to need a new version at the top。 So we're going to do that。

 And now we're just going to add pointers to point to the existing data structures。 All right？

 Now we add our write。 So the actual overhead for this is relatively small。

 Now the other nice thing that you might have noticed here is this also now allows us to。

 have both the old version and the new version in a relatively space efficient manner。

 And so a lot of these network appliances offer this as what they call a snapshot feature that。

 will save some number of these old versions。 It'll be one old version an hour for the last day。

 And after that one per day， going back a week， and then after that， maybe one per month， and， so on。

 And it can do this storage in a very efficient manner。 The relative overhead is relatively small。

 assuming I'm not just completely rewriting， the files every time。 Okay。

 so file systems that implement this include ZFS and the open source version of， it。

 which is called open ZFS， variable size blocks。 So you can have sort of different size extends。

 It's a symmetric tree。 So we know if the tree is going to be large or small and we have to make the copy。

 we store， version numbers with the pointers。 And so we can just create a new version by adding the blocks in the pointers as I showed。

 on the last slide。 And we buffer a bunch of writes together before we write it out to this。

 So again， we're trying to protect the file system integrity。

 We're not necessarily trying to protect your data integrity or your data。

 So your data is going to live potentially in buffers longer before we make it go out， to the disk。

 And then free space is a set of extends。 And that way we can just simply grab an extent when we need some large blocks of data to。

 allocate to a file。 Okay。 So I want to take a moment and talk again about our collaboration policy。

 I know this is a super busy part of the semester when everybody's working on the last project。

 and working on homeworks and exams and everything else。

 So some of the things that are good to do in this class， explaining a concept to someone。

 else in a group， doing that at a high level。 Doing algorithms or testing strategies with other groups。

 So how you might do glass box or black box testing， how you might try to design the space。

 of test cases that you're going to use。 Discussing how you do debugging or different approaches to doing debugging with another。

 group。 And then if you're going online looking for generic algorithms like what's a good hash。

 algorithm or what's a fast memory allocation algorithm， things like that。

 Where it's a generic algorithm。 So all of these are good things to do。

 Things that are not good to do are sharing code or test cases with another group。

 So that's even if it's just a fragment of the code or it's a fragment of the test case。

 Copying or reading another group's code or test cases。

 Unfortunately we've had situations where we had to have those hard conversations because。

 someone simply looked at someone else's code。 And then many hours later went and implemented their code。

 It turns out the way we each write code， the way we each design our code is kind of like。

 a fingerprint。 It's different。 It's unique。 And so just looking at how someone thought about structuring their code can be enough to。

 influence how you structure your code。 And then that triggers our cheating detection algorithms。

 And then we have those hard conversations。 Copying or reading online code or test cases from prior years。

 So disk space is cheap。 We've kept a lot of years worth of submissions。

 And we compare against all of those submissions。 The TAs are also really good at Google。

 And they find all the instances of 162 code and repos that people have made public and。

 things like that on the internet。 And again， if you look， even just looking at one of those。

 even if you don't try to copy， from it， it's going to influence the way you structure your code。

 It's going to influence the way you write your code。 And again。

 it's going to lead to one of those difficult conversations。

 So helping someone in another group debug their code is not acceptable。 And again。

 what we've seen happen before is someone's hit a wall， they can't get through， it。

 and a friend comes along， helps them debug their code and says， oh， you know， I just。

 did it this way。 And they change it。 And then we detect that because it turns out that was a unique way of solving that particular。

 issue。 So those are all things you should not do。 And again。

 we compare all of the prior year of current year， all the online solutions to。

 everybody's submission。 So what do you do if you hit the wall？ You know， it's deadline is due。

 code is due， and it's not working。 Well， that's where you reach out to your core staff。

 We're here to help you get through this class。 And we have a lot of office hours。

 We have a lot of TA support， a lot of reader support。

 And it's all designed to help you with any problems that you run into。

 So if you find yourself in a situation where you think you have to turn to Google as your， friend。

 please don't。 Instead， turn to your TA， turn to your instructor， turn to your reader for assistance。

 Also， please don't put your friends in the situation where you ask them for help， you。

 ask them for code。 We've had situations where a roommate left their computer unlocked and another student。

 looked at their computer and saw their code， saw how they did things， and they influenced。

 their design。 Now we have a really hard conversation between two friends who are now not friends。

 So with all of that in mind， again， if you run into the situation where you think you。

 need to turn to doing something like that， please come see you。 That's why we're here。

 Any questions？ Yeah。 Is it open to you？ Okay， to read which source code？ Yeah。

 it is perfectly fine to read the source code for a public operating system like BSD。

 or Linux or any other operating system。 That's not going to necessarily change or influence directly your solution in 162。

 but， you'll see an example of how an operating system implemented something。 The generic cases。

 that's perfectly fine。 But if you go and you find somebody else's 162 code repository that they left up on GitHub。

 that crosses the line unfortunately。 You're welcome。 Any other questions？ Okay。

 so let's talk about back to technical stuff， some more general types of reliability， solutions。

 All right， so we're going to use transactions to implement atomic updates。

 And the goal here is we want to make sure that multiple related updates either completely。

 happen or don't happen at all。 So it's an all or nothing。

 So if there's a crash that occurs in the middle of a transaction， at the end of the day。

 after we've completed recovery， our state is either everything is complete or nothing， happened。

 We can't end up in some kind of inconsistent weird state where $100 got taken out of bank， count。

 but didn't get deposited into the target。 Now， as I said， most modern file systems。

 their focus is on protecting the file system itself。

 and the metadata associated with the file system。 They don't try to do anything about the data that's stored in the file system。

 It was these are my examples of where they do try to protect some of the data in the， file system。

 But a lot of times， applications have to implement their own types of transactions or。

 other techniques to preserve their data。 So we also want to provide redundancy， of course。

 for media failures。 And again， we saw how we can do that with things like error correcting codes on individual。

 drive and then by replicating the storage media itself through something like RAID or by using。

 erasure codes to replicate the data blocks across a geographic area。 Okay。

 So transaction is kind of really closely related to something we've already looked at， which。

 is critical sections。 Right？ We use critical sections when we wanted to manipulate a shared data structure。

 A transaction takes this notion of doing an atomic update to a shared data structure and。

 takes it from memory to persistent storage。 Right？ If you think about it。

 like with a critical section， the idea was everybody outside the。

 critical section either sees the data before you entered the critical section or they see。

 the data after you left the critical section。 They can't see the intermediate state of the data。

 It's what a transaction is going to do for us but with stable storage。

 It's going to do it with persistent storage。 Now there are lots of ad hoc approaches， right？

 So what we saw in fast file system is we did it is really careful ordering of the updates。

 to the file system data structures such that we could either leave it the case that the。

 file never got created or never got updated or it's the case that the file got created， or update。

 But we don't end up in an inconsistent state for the file system in between。 Like I said。

 applications still do techniques using temporary files or other things to try。

 and make things atomic。 So the key concept here is transaction。

 The transaction is atomic sequence of reads and writes that takes our system from one。

 consistent state to another consistent state。 And again， just like with a critical section。

 transactions appear atomic to all other threads。 So a thread can't see what's going on with the state in between while the transaction。

 is active。 So again， transactions are extending our concept of atomic updates from memory in a critical。

 section to stable storage， persistent storage。 So the typical structure。

 first thing we do is to begin。 That gives us a transaction ID。 Then we do a bunch of updates。

 Now let's say we run into trouble。 Our program throws an exception。 That's fine。

 We abort the transaction and roll back like it never happened。

 What happens if we run into a conflict with some other transaction？

 We're trying to read and write the same files that that transaction is right is trying to。

 read and write or same data structures that transactions trying to read and write。

 So we have a conflict。 That's fine。 We abort both transactions or one and just roll back。 All right。

 So that's the idea is that when we do to begin， we're going to kind of snapshot what's going， on。

 Then you can do whatever you want with the playground。 If anything goes wrong。

 we just make it all go away。 We roll back to that snapshot。 Then finally。

 when we're done making our changes， we commit the transaction。 So let's say we have a classic。

 this is sort of the classic example of a transaction， say， from 186。

 I want to transfer money from Alice to Bond in a banking environment。

 And so I first start by decrementing the balance of Alice's account。 And this bank。

 as many databases work， has two sets of ledgers。 It has individual account ledgers and then it has ledgers for the bank branches。

 So I need to decrement $100 from the bank branch where Alice has her account。

 That's where she went and opened her account。 Then I'm going to increment Bob's bank balance。

 I'm going to increment the balance for the branch where Bob's account is stored。 And then I'm done。

 All right。 So I've got four separate operations doing reads and writes， but I want to have a peer。

 as one logical， indivisible operation。 The way I do that， it's super complicated with transaction。

 I put a beginning at the beginning and I put a commit at the end。 That's it。

 It was actually not very complicated。 And so what this does is it guarantees that even if I've got other transactions that are。

 incrementing and decrementing accounts and branch balances， this is one indivisible unit。

 Other transactions can't see the intermediate state。

 This transaction won't see the intermediate state of other transactions。 And when the commit occurs。

 the system guarantees that the results are durable。 All right。 Questions？ Yes。 Yeah。

 So the question is that we can't see the intermediate state。

 Could there be a double spending situation？ So what the system does is it guarantees that if there were a couple of different things。

 or what the system does is it guarantees that if there were attempt to both have multiple。

 threads that are simultaneously trying to decrement Alice's account， then we would either make。

 one wait or abort that transaction and the other transaction would be allowed to proceed。

 So both transactions can't actually be manipulating the data at the same time。

 So if you want to think about the ordering， even though all the transactions look like。

 they're running at the same time， there's an ordering and one transaction occurs logically。

 before another transaction occurs before another transaction occurs and so on， if they're working。

 on the same data。 If they're working on independent data， independent accounts。

 independent bank balances， then all， of those could be simultaneously running at the same time。

 And so part of what the system has to do is keep track of what's being accessed by what。

 and what's part of what transaction。 So this is really simplistic。

 It's actually a lot more complicated。 There's locks。

 There's all sorts of other things that monitor what's going on。 Okay。

 Another concept that we need is the concept of a log。

 So there's a simple action that's atomic in a log which is writing or appending a basic， item。

 And we're going to use that to seal the commitment of a whole series of actions。

 So here is a whole set of actions that we'll say is associated with a particular transaction。

 Now there may be other operations that are going on that we've written in the log that。

 are not part of this transaction。 These actions will all have that ID that was part of when we did the begin。

 When we do the begin， we get back a transaction ID。

 A transaction ID is assigned to everything that we're writing in the log。

 So when we start a transaction， we get that ID N that's going to be attached to all of， these items。

 When we're done， we're going to commit that in the log。

 We're going to write a commit record to tell us that this transaction is now complete。

 So when we look at a log， if we just see a start and we see a bunch of actions for that。

 transaction， but we don't see a commit， then it did not finish。

 So how do we turn this into transactional file systems？ Well。

 the idea is we want to get better reliability by using a log。

 So any changes we're going to make to the file system， we're going to treat as transaction。

 So previously， like in the file system， we went in and we manipulated the i-node， we。

 manipulated the bitmap， we manipulated the directory entry。

 We went and did those as we were doing the operation。

 Now we're going to put all of that in the log instead and do it through transactions。

 So a transaction， again， it's committed once it's written to the log and we see a commit， record。

 we could do one of two approaches。 We can， because the log is going to be buffer cached。

 we could force the log to disk。 So we're going to block， stop。

 wait until the log reaches disk when we do a commit。

 Or we could put the log in some sort of nonvolatile memory。 All right。

 and that way it'll survive system crashes and power outages。

 So we're doing everything in the log first。 It's right ahead logging。

 And then we're going to go and do things in the file system。

 So even though the file system gets updated at a later time， we're going to ensure that。

 eventually it's updated if it should get updated。 Now there are two different ways we can use logs and file systems。

 One is what's called a log structured file system。

 The other is what's called the journal file system。

 Everybody in this room is using journaling file systems because all of the modern file。

 systems use journaling。 The difference is in a log structured file system， we put the data。

 The data blocks also go in the log。 In a journaled file system。

 we only use the log really for recovery purposes。 So the data actually goes out to the disk just as it would in a normal file system。

 The journaling is usually， and you can think of it as kind of a add on to a file system。

 where a log structured file system is kind of a ground up reimplementation of a file system。 Okay。

 So in a journaling file system， we don't directly modify the data structures on disk。 Instead。

 we write each update as a transaction in the log。 So this is typically called a journal or it's called an intention list。

 And it's maintained on the disk。 So we allocate blocks for the log。

 We can again keep it cached in memory and either force the log to disk when we do a commit。

 or we can choose to put it into non-volatile RAM。 Now once a change is in the log。

 and it's been committed， then we can go and apply it to， the file system。

 So I'll walk through an example because it's probably a lot of words and sounds a little。

 complicated。 The idea is that there might be an instruction like modify the I know pointers in this particular。

 way。 We log that in the log and then later on we're actually going to go and modify the file system。

 Again， this is in contrast to before where we just went and modified the I。

 Now we're going to instead record， hey， go modify the I。 That's what we're going to do。

 And then we can clean up the logs。 The log doesn't grow unbound once we've actually performed those operations on the file system。

 So like I said， it's kind of a bolt-on that you can do。 So the original file。

 one of the original file systems for Linux， EXT2， was a fast file， system like file system。

 And they added journaling to it and created EXT3。 So the relatively straightforward change。 Okay。

 Other examples of journaling file systems。 This why I say everybody is using it。

 If you're using NTFS， if you're using HFS plus or APFS on Mac products， if you're using。

 Linux XFS or JFS or EXT4， all of those are journaling file systems。

 But now let's peek under the covers and see exactly how those file systems work。 All right。

 So first， let's look at an example of what happens when we don't have journal。

 So I want to create a file。 So what do I do？ First thing I do is I find some free data blocks。

 All right。 Okay。 I found some free data blocks。 Then I find a free I node entry。 Okay。

 I found a free I node entry。 And I find a directory insertion point。 And I found that。

 And now I'm actually going to go and do everything。

 So I'm going to write the map is used to say that I'm using the data block。

 I'm going to write the I node entry to point to those data blocks。

 Then I'm going to update the directory entry to point to the I node， the I number。 And I'm done。

 Okay。 So I made all of these changes on the disk in the file system。

 And I did it in this very precise order so that if I had a failure， I could try and go。

 back and kind of figure out like how do I， you know， reconstruct the disk using my FSCK， problem。

 So how does it work with journal？ It's a little different。 So we have our log。 Again。

 we're going to either store this。 We're going to store this preferably a non-volatile storage。

 So we're going to have to force it to disk and wait for the disk。

 So now we're going to find the free data blocks。 Okay。 I found a free data block。

 We're going to find the free I node entry。 Then we're going to find the free。

 to find the directory insertion point。 To find that。 All right。

 So now this is very similar to what I did before。 Now I'm going to record my intentions in the log。

 Instead of going and modifying the file system itself， I'm going to write the instructions。

 for what I want to do to the file system。 So I want to write the map and mark it as used。

 I want to write the I node entry to point to the block I just allocated。

 I want to write the directory entry to point to the I node that I just allocated。 Okay。

 And after I've done all of that， now I'm done。 I've created my file。

 So now I'm going to commit my transaction。 All right。 So there's a couple of things。

 Here we divide our log up into regions。 So done is things where the state of the disk reflects what we had in the log。

 We've done the operations that we said we wanted to do in the log。

 We have our tail of our log and then we have this region called pending。

 The pending region is all the operations we haven't done yet。 So now in this case。

 we have a bunch of pending region of pending operations that we just， created。

 So now that we finished our transaction， we're going to move our head to the very end。

 And all of this is in our pending region。 So these are instructions that say what we want to do to the file system in order to。

 create that file。 We haven't modified the file system。

 The file system still on disk reflects the old state of the file system。 So after we commit。

 eventually what we're going to do is we're going to replay that transaction。

 We're going to actually do the intentions， the intended actions that we had in the log。

 So all accesses in the meantime to the file system have to first look in the log。

 So it means if I want to look for that file that I just created， I'm going to have to scan。

 The operating system will scan through the pending operations to see was that file does。

 that file existing。 And then it'll look out onto the disk to see what's the state of the disk。

 All right。 So that file that I just created only the directory entry for it only exists here in the log。

 What's on the disk is stale。 It reflects the before time， not the current state of the file system。

 So we've added some complexity here。 Before we could just go out the disk。

 look at the disk that's hold us the state of the， world。 Now we have to look in the log。

 read through the actions in the log to determine whether。

 or not something exists or not or what the state of it is。

 Now eventually what we're going to do is we're going to copy the changes that are in the。

 log to disk。 So we'll start， so assuming we've already done everything that was pending， we'll copy。

 our changes out。 So here we'll mark the block as allocated。

 then we'll mark the i node as allocated pointing， to the data block that we just marked as allocated。

 and then we'll add the actual directory entry， pointing to the i node that we allocate。 All right。

 Now at this point， our tails that are commit and when our tail reaches our head， we can。

 now discard everything that's in the log。 We can do garbage collection。 All right。

 Now what happens if after a crash， I'm recovering， I'm reading through the log， all right， as。

 the system is booting up， and I happen to see this， and I'm scanning through the log。

 and I see a start， and I see， oh， it was allocating a block， right。

 But what I don't see is any directory entry。 What I don't see is any commit。 So in this case。

 I've got a transaction that has a start， but it has no commit。 So it was interrupted。

 and so therefore that transaction did not complete。

 And so all I'll do is just simply discard the log entries。 The disk remains unchanged。 All right。

 Now， if instead I see a commit， that means the transaction completed。

 So when I'm scanning through the log， I find a start， I find a matching commit。

 So there are two choices。 I could actually redo it right now and make it happen。

 Or I could just keep booting up the system， and eventually the log processing code will。

 just simply replay everything from the head until it gets to the last commit， and we're， done。

 And then we'll discard those changes。 But those changes will have been applied to the actual file system on disk。

 So why do we go through all this trouble？ Because it gives us updates that are atomic。

 even if we crash。 So even if the operating system crashes， even if we suffer a power outage。

 we're able to， ensure that our file system remains in a consistent， coherent， correct state。

 Updates either get fully applied or they get discarded。 So all of the operations we're doing。

 like creating files， deleting files， updating files， occur as atomic operations。

 They either complete or they never happen。 So you could say， well， is it expensive？ Yeah。 Right？

 We're writing everything twice when it comes to our metadata。 We're writing it to the log。

 and then we're going and we're actually writing it to the。

 disk and modifying the data structures in the disk。

 And that's one of the reasons why in modern file systems we only do journaling for the。

 metadata updates。 Because doing journaling for the actual data blocks。

 now our logs would just blow up in， size。 And we'd be doing a lot of copying if we had to copy the data blocks out of the log and。

 into the rest of the disk。 So it's kind of a trade-off， right？

 We're able to protect the file system structure integrity， but we're not protecting the contents。

 of files。 And so that's why， again， applications will choose to do their own thing at the application。

 level。 And again， there are lots of different approaches replicating the files and temporary files and。

 things like that that we can use。 Questions without journaling？ Yeah。 Sure。 [INAUDIBLE]， Yeah。

 So the question is， when I'm recovering here， right？ I see that I have a start。

 I see I have a commit。 So I know that this completed。 So I'm going to redo this。

 I'm going to redo allocating this， redo linking in the I node， redo linking in the directory。

 entry to the I node。 What happened if I was right at the crash occurred right after I'd already done that。

 once？ Well， I end up with two copies of the file。 So the answer is no。

 because all these operations are what we'd call item posts。 Like。

 I can repeat the operations multiple times and I'll get the same outcome。

 Because when I'm doing this， I'm not saying， find a free block。 I'm saying。

 I'm allocating this very specific free block in the bitmap。 Similarly， I'm saying。

 I'm allocating this specific entry in the I node and this is what， I'm going to write to。

 And similarly， I'm saying， I'm allocating this specific directory entry and this is what。

 I'm going to write to it。 So I can redo， I can actually redo these operations multiple times and I'll still get the same。

 physical outcome on the disk。 And that's important。 These operations all have to be item potent。

 If any of them were not， then making changes would result in having， like you said， multiple。

 files be created。 Okay， so simply finished with our journaling summary。

 Next time we'll talk about LFS and then we'll get into networking。 Okay。 Okay。 Okay。 Okay。 Okay。

 Okay。

![](img/8aaba7373c703fc51f66e8bca6497145_3.png)