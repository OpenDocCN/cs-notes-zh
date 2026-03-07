# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p13 p12 Week 02, Segment 4 - Physical Disk Structure -BV11QQcYmEzD_p13-

Hello and welcome back to CS615 System Administration。

This is week do a segment four and in this video we'll take a quick look at what a hard disk drive actually looks like。

Besides giving us an appreciation for the impressive engineering involved。

 and tying something abstract such as data storage to mechanical devices。

 this is also useful for us to better understand partitions as well as fire systems more generally。

So let's get started。As we mentioned earlier， the simplest storage model and the most common storage unit is a simple hard disk drive or HDD in a direct attached storage or DS model。

And even though solid state drives offer many advantages and are increasingly popular these days。

 a traditional IDE drive as the one shown here is what we use for our illustration purposes。

 since many of the considerations that interest us I in fact derive from the physical properties of exactly such drives。

But so let's open up one of these and all right chances are you actually ruined the hard drive because honestly they're just impossible to open up。

 often requiring some sort of security screw， which really just means you have to make an extra trip to the hardware store but that's okay so that means like going to the hardware store and then you come back and try again on another drive and。

There， that's much better。So this is what a boring old HDD IDE drive looks like on the inside。

We have a magnetic platter on a spin rule zipping around with a speed of over 7。

000 rotations per minute with high performance drives reaching 50，000 RPpMs。

And often you have more than just one of these， meaning there are probably multiple players。

Onces and zeros are stored in the ps as charges in the magnetic polarization of individual sections on the ptter detected and changed by the read right head。

Which sits at the end of the actuator arm， which allows it to move raly across the disc。

The disc is then divided into individual tracks， marking a specific distance from the center。

Now each disc can usually hold data on both sides and if you have multiple disks。

 then congruent tracks across multiple plas form a cylinder with multiple concentric cylinders forming a cylinder group。

Each track is then further subdivided into individual sectors。

 the smallest addressable unit of the hard disk。These sectors generally are able to store 5 12 bytes and form the standard disk block。

That is this 512 byte block size is an actual hardware restriction。

 and even though nowadays they exist hard drives with a physical block size off， for example。

 4096 bytes， a lot of computer hardware and software still assumes 512 byte blocks。

 which means that those drives oftentimes have to emulate a much smaller block size than they have。

We'll see the 512 by physical block size appear again in future videos。

 and we talk in more detail about file systems， but for now make note that due to physical limitations it's impossible for the hard drive to read more efficiently than 512 bytes at a time。

Here's another view of a hard drive where you can better see the multiple players which then logically require multiple readr heads and electrode arms。

Since each platter can be read or written on both sides， the readW heads actually look like this。

Here you can clearly see the dual read right head。You should also note that the actuader arm is the same for all read right heads。

 meaning they always move as one。We'll use that property later when we talk about petitions in our next video。

Now， one thing you may have observed when looking at the different sectors is that necessarily the sectors on the outer tracks must be physically larger than the sectors on the inner tracks。

But if each block is defined to contain 512 bytes， then a really wasting space here。Similarly。

 if the disc spins with a constant angular velocity。

 then the blocks on the outer tracks are moving faster than those on the inner blocks。

So folks decided to take advantage of these properties and came up with Zone bit recording。

 whereby the disk is structured such that more sectors are placed on the outer zones。



![](img/798af93e150f5190e062741cfc047ced_1.png)

With constant a velocity， we then increase our data transfer speed on the our sectors as we're able to reach more sectors faster than on inner tracks。

And overall， increased storage capacity as we now have more sectors and dozen more 512 bind physical blocks。

As you can tell within system administration， there's no rabbit hole too shallow for you to not tumble in and discover that there's an endless list of additional things you can follow。

And as so often， these things lead to interesting physical properties of the real world around us。

 even though we're talking about bits and bys once and zeroes。



![](img/798af93e150f5190e062741cfc047ced_3.png)

And some of these physical things affect our performance， even setting Z recording aside。

 a physical hard drive is limited in its performance by a few factors。For start。

 although most negligible compared to the others。There is the transfer obit rate with which the data is read from the disk。

 a direct function of how many consecutive blocks of data you want to read or write。

More directly though， we understand it will be limited by seek time that is the time it takes the actctuator arm to move the read right head to a specific track of the disc。

As you visualize this movement， take note that in general， if we want to read one block of data。

 we are quite likely to also want to read the next block of data that is related to just the next by in a specific file。

In order to minimize angular movement seek time， we want to store data on contiguous blocks within the same cylinder。

Next， in order to get the data under your read righthead。

 you might have to spin the disc since you might just have passed the block you wanted to accessus。

So your next performance limiting factor is rotational latency。

 which on average is one half of the rotational period。Finally。

 there's a little bit of overhead once you've read the data from the disk and have to get into the US and a bit of overhead for the integrated electronics as they initiate the various physical movements。

 etc。But all right。Theres still one more critical aspect that limits the usefulness of our hard drive。

And that's capacity。So let's think about what capacity means。

 the capacity of a hard drive really is just how many individual blocks we can store on the disk。

Which， as we've seen with Z recording can be gamed a bit。

 but ultimately we need a way to address each individual block， right？

So let's consider this disk here。With its various tracks。And divide it。Into sectors。

I know I know these illustrations here are pretty geny。

 but at least you don't have to deal with me trying to draw things on a whiteboard You get the idea here I hope we have a fixed number of blocks that we need to be able to address。

So how do we do this？One way of doing this was the socal cylinder heads sectors addressing scheme。

 whereby you be limited logically as we understand from our visualization here by the number of cylinders or tracks。

 how many heads you have， and how many sectors track you can create。Now。

 the early ATA specification defined。That you could have 64K cylinders。

16 heads with each platter being used on both sides， so it be eight ps max per drive。

And 255 sectors per track。So you do the math， calculate that you can have 512 bytes per sector and up with roughly 137 gigabyte of maximum storage for an ATA hard drive。

Not too bad。But of course， the problem was that the bios had a different limit because reasons。

That is， early biases could address 1024 cylinders， 256 heads。And 63 sectors per track。

 which again at 5 12 bys per sector， gave you a maximum disk size of approximately 8。5 gigabys。

So that's pretty bad， but guess what if you look at these two ways of limiting disk size。

 you actually have to use the lowest common denominator and thus have only 1024 cylinders from the bios limit。

16 heads from the ATA definition and 63 sectors per track for the bio limit again。Which gives you。😔。

Only 528 megabytes is the maximum size that this could possibly address。Now back in the day。

 the 528 mix seemed certainly like more than enough space anybody could possibly use。

 but soon enough people wanted to have larger discs。So with time。

 the different limitations were raised by using different data types to store each of the CHS factors。

 but the whole approach was eventually replaced by using logical block addressing instead。

 whereby the blocks would be addressed well， logically or sequentially by an index。

Cool beans you say now we don't have any limitations any longer， right， well， not so fast。

 you still have to store the total number of blocks somewhere。So in ATA1。

 the data type to represent this total number was 28 bits。

 meaning it could only address two to the 28th blocks or roughly 137 gigabys of data。

This was changed in 2003。With the ATA6 standard， which now uses 48 B LBA。

 which yield a somewhat more comfortable 144 petabytes。So far。

 we haven't managed to build a hard drive with that capacity。

But disk capacity is not just a concern for the disk drive itself。

 We also require the components involved in the boot process to be able to handle the disc。

 To this end， the master boot record partition table needs to be able to address the disc blocks。

But that uses a 32 bit data type， so it can only address two to the 32 blocks or roughly 2。

1 terabytes。Fortunately， other approaches exist。Using the GUI partition table。

 you get a 64 bit data type which gives you a nice 9。4 zabyte limit。



![](img/798af93e150f5190e062741cfc047ced_5.png)

Allright， let's take a break here， we' were picking up from here in our next video。

 when we talk about partitions， which we already just hinted at a little bit。

 when we talked about cylinder groups or the MR and GBT。

Understanding the physical aspects of the hard drive thus help us better understand those concepts as well。

 which is why we covered this topic here in this fashion。Our key takeaways then are。

There's a physical block size， most commonly 512 bytes， which is dictated by the drive。

We'll see how that impacts P system performance and some other considerations in future video segments。

We saw that some of the limitations on this capacity were imposed by the physical factors。

 such as when using the cylinder head sectorctors addressing schema。

But even when we move to logical block addressing， we're still limited this time， however。

 by the choice of data type。This serves us as a useful reminder that no matter what we do。

 we never have infinite resources， we will see similar problems throughout the semester in the discussion of other storage types of talking about network protocols。

 etc。We also noted that other physical factors influence the performance of the hard drive；

 these will no longer apply when we move to solid state drives。

 but remain an important factor in deciding which storage solutions to purchase for your needs。

Finally， and as we will see in our next video， the arrangement of the physical attributes of the spinning magnetic platter on the spindle hard drive influences how we partition our discs。

Even if the storage space now may actually be virtual。

 as in the case of NBS volume or abstracted across multiple physical drives。

 as in the case of sayade， we still pretend that there's a physical drive for such a rotating platter underneath。

But more on that in our next video， until then， thanks for watching， cheerers。



![](img/798af93e150f5190e062741cfc047ced_7.png)