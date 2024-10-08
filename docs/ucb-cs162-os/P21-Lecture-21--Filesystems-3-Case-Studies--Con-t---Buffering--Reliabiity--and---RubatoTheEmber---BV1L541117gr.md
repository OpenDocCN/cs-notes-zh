# P21：Lecture 21： Filesystems 3 Case Studies (Con't), Buffering, Reliabiity, and - RubatoTheEmber - BV1L541117gr

 Welcome back everybody to CS162。 We're going to continue where we left off talking about file systems。

 If you remember last time， we talked about the main components of a file system。

 Was some sort of way of looking up names。 That's the directory structure yielding some sort of index into an i node。

 That represents the actual file and the i node typically points at data blocks。

 So this is a pretty generic way to look at file systems。 And why do we have things like this？ Well。

 for one thing， the storage media is divided up into a series of data blocks， either 512。

 or 4K and 512 bytes are 4K in size。 And so we clearly need some way of pointing at which blocks belong and which order。

 And so that's what the i node is good about。 And the directory structure gives us the convenience of name lookup。

 Were there any questions on this very high level thing？

 Because this is what you're thinking about right now for project three。

 So we talked about the ancient file system that came from MS。DOS called FAT。 And it's very simple。

 which is why it surrounds still。 And what it is， is it's a series of blocks and then a large array called the file access。

 table。 And that array basically has an entry one to one with every disk block。

 And the only thing it does is it links blocks together in some order to represent a file。 OK。

 so in this particular degenerate version of a file system， there's not even an i node， here。

 This is really simple。 OK， and the way we address a file is basically we say， oh。

 the file number is 31。 Which represents the first block。

 And then we link them together to get the rest of them。 OK。

 and the only thing you need to bootstrap this is you need to know kind of where is。

 the root directory。 Well， it turns out with the FAT file system。

 the root directory is usually at block number， two and then everything goes from there。 All right。

 questions。 OK， we're good on this。 Now of course， the reason this is not great。

 there's many problems with it， right？ So among other things。

 you're always doing this linear search through the file system， to find things。 And as a result。

 it's inefficient in both serial and random access。 So this is just kind of not great in all fronts。

 but it's simplicity， let's you put it in firmware。 So then we said， OK， what else could we do？

 And we gave you this original file system from 4。1 BSD， Berkeley standard distribution。

 which looked like this。 And this is kind of like the first I note ever where there were direct blocks。

 pointers， indirect block pointers， et cetera。 And really， what does this mean？ Well。

 this means that we have a structure that is the file。 You can almost say the I note is the file。

 It's got the metadata in it， which is all of the access permissions。 Who's the owner？

 When was it last written or read？ And then these pointers help point at the blocks that are actually in the file and in。

 a particular order。 OK， so for instance， in the original BSD。

 we had 10 of these direct block pointers， which， could point to up to 10 blocks。

 And then a single indirect block pointer would point at a block， which would point at data， blocks。

 and then double would point at a block， the point at a block， et cetera。 And as a result。

 this structure optimized both for short files and for long ones， because。

 it could do short files quickly and long ones it could represent。 Now， I did have a question。

 I think after lecture last week， which was， well， what do you do if you have a short file？

 Do you have to fill all these in？ No， you can make no pointers here。 OK。

 so the shortest kind of I-node you could make that has any data at all and it would。

 have one pointer to a block as the first pointer and the rest of them are null。 OK。

 And so the pros of this is it's more or less simple。 It's not as simple as the fat file system。

 but it is pretty simple and it gives you a， way to represent small blocks and large-- small files and large files。

 The con is that there's no rhyme or reason as to where these blocks come from。

 So there's nothing in this data structure that says this is going to be an efficient。

 use of the disk。 Everybody with my on that？ The only thing that says is I can represent files on the disk。

 It doesn't say that I'll necessarily make them efficient。 And that's the important part about this。

 This layout is a correctness thing。 It tells me which blocks are belonging to the file and in which order。

 Since it says nothing about performance， it could perform well。 Why？ Well。

 if I could somehow make sure that I pick all the blocks in order on a track， then this。

 could be very efficient。 On the other hand， if I randomly pick these blocks。

 the file would still work， but it， would be really inefficient。

 So this data structure says nothing about efficiency。 It's about correctness。

 Now we have to be figuring out how to make this efficient。

 And I'll tell you what happened amusingly enough is in the original BSD file system， 4。1。

 you'd make a brand new file system。 You'd reformat the disk。 And everything would be。

 I'm going to say blazingly fast for the day。 And then as you used it and you deleted and added and deleted and added files。

 it'd get， progressively slower and slower because the way the free list worked， which it linked。

 free blocks， the other and stuff。 Eventually， you would get kind of the worst ordering of blocks。

 You'd start out with the best ordering and you'd get to the worst。 Okay？ Everybody with me on that？

 So now， next thing that came along was 4。2 BSD with the fast file system。

 So there is a question here in the chat saying， so there's a limit on how many total files。

 on the disk。 Yes， the limit on the total number of files on the disk depends on how many i-nodes you。

 have。 So if you only allocate some number of i-nodes， that's the maximum number of files you can。

 have。 Okay？ And the other thing is every file is at minimum the size of an i-node plus one block。

 And there's no smaller file。 So even a one byte block has that problem。

 And usually the i-nodes are like 128 bytes。 And so you're talking about 128 bytes plus one block is kind of the minimum file size。

 for even a one byte file。 Okay。 All right。 So 4。2 BSD came around about 1984。

 And same i-nodes structure， because remember what I said was the i-nodes structure isn't。

 the problem。 The problem was allocating the blocks。 And so it was the same header。

 triply indirect blocks， et cetera。 They changed the block size a little bit。 They went from 1。

024 or 1k to 4k。 And that made things a little faster。 Why did it make things a little faster？

 Why would changing the block size make this file system a little faster？ Yeah。 Okay。

 But why does that help with the number of blocks per file going down？ Why is that faster？

 Is that again？ Okay。 And how does it average down the overhead？ That's good。 [inaudible]， Good。

 So it's reducing overhead。 So another thing that you were going around。

 but if we always allocate a block as a series， of consecutive sectors on a track。

 then a 1k block has two 512 byte sectors。 A 4k block has eight of them all on the same track。

 So we get locality out of the disk just by going from a 1k to a 4k block size。 So yes。

 that's reducing overhead， but it's also doing it in a way that's very advantageous。

 on a spinning disk。 So but then they did a bunch of other things。 Now I put up this paper。

 I don't know if any of you looked at this after last time on our resources page， but。

 this is a paper that was written by McEw's Nick Joy， Leffler and Fabry on the original。

 fast file system。 And you can look at it too。 Papers back in the day in 1984 look a little different than research papers do today。

 but， this is actually the first paper we study in 262 even。

 But what they did was they optimized the file system in lots of ways。 Okay， so among other things。

 they distributed the i-nodes throughout the disk。 Okay， so why is that good？ Well。

 it means that now， you know， when they were originally all on the outer part of the， disk。

 no matter where the file was， you always had to seek all the way out to come back and。

 get the i-node。 And so if you're doing an LS in a directory， you'd seek out， you'd get the data。

 you'd seek， out， you'd get the data。 There's a lot of head movement just because of where the i-nodes were。

 So they distributed them throughout and they got really good reliability out of it as well。

 because if you ever had a head crash that destroyed part of the surface and it happened。

 to be on the outside cylinder， then you basically have destroyed all the i-nodes and therefore。

 effectively destroyed the file system because you have no idea what's inside there。 Okay。

 so then the other thing they did was rather than a linked list， free list， they。

 actually started using bitmaps where one bit per block， very long bitmaps would basically。

 let them allocate but know what kind of locality was involved。 So if you have a long bitmap。

 you could go for a big train of unallocated sectors and。

 you could get a lot of locality just by finding a bunch of unallocated sectors in a bitmap。

 And they also attempted to allocate files continuously。

 They had a 10% reserve disk space which I'll say more about in a second and then they also。

 had something called skip sector positioning which I'll also say something about。

 So let's look about the i-node placement for a moment。

 So early Unix and the fat file system on Windows， all of the metadata， that's the directories。

 and i-nodes and all that stuff， were stored in one place on the outside。 Okay。

 Those i-nodes were fixed size when you formatted the disk and basically one problem with the。

 i-nodes being all in one place is a head crash destroys all the data I said that and then。

 the i-nodes are not close to the data。 Okay， and a secondary problem is when you create a file in Unix。

 you don't really know， how big it is and so you don't know how much contiguous space to allocate。

 Okay， and the way we get fast out of this file system is if we have a disk with 100， sectors。

 we would like all 100 sectors to be on a small number of tracks all next to。

 each other because that would give us the fastest performance。 Okay。

 And so really what they did was they spread the i-nodes out and then they came up with。

 an allocation mechanism for making sure that there was locality on average out of the allocation。

 of blocks。 And so really what they did was they divided things the cylinders into a bunch of cylinder。

 groups or block groups and you can see this these are like you know donuts along the way。

 And for each block group they put a set of i-nodes for that block group。 Okay。

 And so often because of this you could have the i-node for a file stored in the same cylinder。

 group both as the i-node for the directory parent directory it's in and in the same block。

 group is all the data for the disks。 Now if we're accessing something within a given directory all of a sudden everything's。

 within one block group and it's much faster there's not a lot of seeking going on。 Okay。

 And the so we've divided up into a bunch of block groups which are a set of closed tracks。

 And remember when we talked about how disk accesses had a C of 1。5 where the common seek。

 was below average。 Well the block groups give you that because it means that you seek much less than average。

 where average would be from every track to every other track you compute the seek time。

 and you average them。 That's the average seek time here by staying within a block group we'd only move a little。

 bit。 And as a result we get much faster access。 So basically what we've done is we've kind of put a bunch of locales on the disk and we've。

 put stuff in them to avoid huge seeks。 And the directory and its files are typically in a common block group。

 Now let me tell you one other thing here so remember when we looked at data a couple of。

 lectures ago we saw that most files are small but most bytes are in large files。

 Remember that there was two slides I showed you。 So the fact that most files are small works great with this scheme but take those really。

 large files。 If I have one large file in a block group and I try to put it all in that block group。

 what happens is I'm going to fill the whole block group up with a large file and none。

 of the small files will fit。 So what they did was they also had heuristics that you would start by allocating in the same。

 block group as your I node was in but then after you got past a certain number like 64。

 kilobytes or whatever then you would go to a run in a different block group and run for， a while。

 Okay and so what it did was it made sure that you only the seek was only every so often。

 where every so often was a large number of blocks and it reserved room so that small files。

 could still fit in there and be close to their I node。

 So the fast file system is all about a bunch of heuristics to make sure that when you。

 allocate things they're fast。 Okay so once you've got that kind of scheme then the rest of it's pretty easy to think。

 about so we have bit maps for every block group we do a first free allocation of new blocks。

 so we try to grab successive blocks that are close to each other and it avoids fragmentation。

 and then there's when big files come into play there's a way of going to multiple block groups。

 to handle the big files。 Okay the important part about this which is initially a little counterintuitive but。

 I hope you guys can see where this comes from is we want to make sure that we have basically。

 10% or more of the storage free。 If we do that then we know that it's easy probabilistically to find runs of empty blocks。

 on tracks and do a good job with performance。 It's just a probabilistic argument and so the way this shows up in a lot of modern。

 file systems is that 10% is taken right off the top of the total size of the disk and。

 you're not even told that that exists and instead it's sort of hidden under the covers。

 and it's there for performance。 And usually as an if you're a system user the root user then you can go in and change。

 that but I recommend you don't unless you're really desperate for space。

 Okay so the summary is the i-node layout for small directories you can fit all the data。

 headers etc in the same cylinder with no seeks file header is much smaller than the whole。

 block so multiple headers fetched from the disk at once so we can grab a bunch of headers。

 and therefore a bunch of i-nodes from the same directory。

 And the reliability is that even if the head crash destroys part of the disk the rest of。

 the disk is great still。 And so that's kind of think of this as minimizing the damage when there's a head crash。

 By the way I should tell you what head crash means。

 This is not like a heavy metal enjoyment sort of thing with a wall that's too close。

 That would also be a head crash。 What we're talking about here is that when you've got spinning storage you've got a disk。

 that's spinning what's actually those little heads there's a little bit of pressure that。

 causes them to be floating on a micron level bit of air above the disk。

 So those heads are not actually touching the disk they're floating because the disk is。

 flying fast enough and it's causing them to kind of fly above the disk。

 And what a head crash is is when that's going on if you jar the disk the head actually hits。

 down and digs a trench。 When you do that all the little ones and zeros come off the side and you see them kind of。

 drip it out of the side of your computer and you know that you're not recovering them。

 at that point。 So that's a head crash and there's a lot of stuff that's been done over the years to make。

 sure that disks don't head crash。 Among other things when the machine is off the heads park on a part of the disk that doesn't。

 have any data on it。 But there's also you know like it'll periodically if it's idle it'll pull it back to a safe spot。

 and so on。 But so head crash is a real thing。 Now let's just look at the first fit block allocation。

 So if you imagine that we have a bit back there where gray here is a block in use， white is。

 not in use then you can quickly look at this and figure out which blocks are allocatable。

 And so if we write a two block file we can grab two of them that are close to each other。

 or if we want to write a large file we can make sure that we mostly get a bunch of blocks。

 that are close to each other。 Okay so this is absolutely not rocket science but this says that if you have a bit map allocation。

 scheme you can easily find runs of free blocks just by looking at the bit map okay and that's。

 kind of what the fast file system did。 Questions？ Yeah。 Yes。 So that's a great question。

 So last lecture I think or maybe the previous one I basically said look modern controllers。

 remap faulty sectors automatically for you under the covers so therefore a scheme like。

 this wouldn't work as well because it does not perfectly correlate with locality。

 So yes that's a problem。 The controller does its best that it can to make sure that it's mostly reflecting locality。

 Okay so it's not perfect anymore but it's still pretty good。 Okay but that's a very good point。

 And that's a good example of you know back in the 4。2 BSD days the way you address the。

 sector cylinder surface sector number okay or cylinder track sector number。

 And so you knew exactly the correspondence between your bit vector and the location。

 Once we went to logical block addresses that it's a little fuzzier but it mostly works， still。

 So I think the important part here is mostly works gives you a big gain in locality and。

 performance anyway。 Okay good question though。 Any other questions？

 So it's interesting you guys should go look at that paper that I've got up on the resources， page。

 What's interesting about it is some very simple heuristics gave them a huge increase in performance。

 because it just made sure that files were mostly local。

 Had a lot of locality to them made a huge difference。

 Here's another thing they did which is kind of interesting。

 So a problem about missing blocks due to rotational delay。 So here's the idea here。

 You read a block off the disk and then you put it in the device driver and by the time。

 you figure out what the next block to read is the disk is rotated too far so the thing。

 you wanted is past you and you got to wait for it to go all the way around one more rotation。

 before you can get the block。 And that's a huge problem because it means even if you've got really good locality where。

 all the sectors are next to each other it means that you still have to rotate once for。

 every sector you read which is bad right。 And so what they did in the 4。

2 BSD is they actually use something called skip sector where。

 for instance if you look at the fuchsia here what happened is those pink blocks represent。

 the blocks of a file and rather than being next to each other they were spread out just。

 enough to make sure that if you had the latency of pulling the thing off doing something with。

 it asking for the next one it will not have rotated past but will in fact have rotated。

 right under what you want。 Okay so this was one of their other optimizations。

 Now as you imagine this can be a problem to get perfect。

 And fortunately in today's discs basically we have a better solution which is there's。

 enough DRAM inside the controller that you have what's called track buffers and so when。

 you go to read a track you just read the whole thing into DRAM on the controller and now the。

 OS can ask for things at whatever speed it wants because it's already been pulled off， the disc。

 Okay so this is a great example of an obsolete problem that was fixed because we have enough。

 memory。 And so modern discs and controllers do a whole bunch of these kind of things。

 So there's track buffers most I would say all of the disc controllers do the elevator。

 algorithms inside the controller now they do some filtering of bad blocks for you so。

 there's a lot of stuff the controller does that the OS no longer has to。 Okay questions。

 Alright so pros the difference between 4。1 and 4。2 was night and day for performance on。

 the drives you have very efficient storage for both small and large files locality for。

 small and large files locality for metadata and you didn't have to defragment the disc to。

 get good performance。 Okay so that was kind of cool and that's all about that 10 percent you have to leave。

 a 10 percent along。 So cons are for instance that this particular scheme is very inefficient for tiny files。

 So a one byte file requires both an i-node and a data block。 Okay so you're stuck。

 It's inefficient when the file is mostly contiguous on disk so in other words if you。

 could have a bunch of blocks that were already together a better way to describe that would。

 be the track or sector or logical block address of the first and then how many blocks it。

 is that's a whole description of that whole run of block。

 Okay and so in this i-node structure you're basically forced to name every block even。

 though they're all together already。 Okay and you need to reserve 10 to 20 percent of free space but I will say this is a great。

 trade-off this is hiding some space to prevent fragmentation that's a far as I'm concerned。

 that's a good trade-off。 Okay so you too can play with this kind of thing all you have to do is have Linux and。

 use ext probably not two anymore you'll probably use three and it looks exactly like the original。

 4。2 bsd with some small things so it has the same kind of locality idea with block groups。

 every group has two bitmaps one for i-nodes and one for blocks within a group and you。

 can set the block size at format time 1k 2k 4k 8k so when you create a new file system you。

 say what block size you want and that's a clear trade-off between locality with larger。

 block sizes and wasted space if you have a lot of small files right but you can choose。

 that and if you were making this file system to do a lot of media you'd probably choose。

 a larger block size and in reality you'd probably choose ext 4 instead of 3 but that's a discussion。

 for another day。 So the actual i-nodes structure is remarkably similar to 4。

2 bsd there's like 12 direct， pointers instead of 10 but it's otherwise pretty close and the difference between ext。

 2 and 3 is that you take an ext 2 file system which looks like the fast file system and you。

 add journaling on top to give you reliability and you get a ext 3。

 We may or may not get all the way to journaling today but we'll try。 Okay。 Questions。

 Okay and I'm kind of showing here you know you've got i-node 2 is maybe the root file。

 system it points the block 258 which is the root directory you look down you find d1 has， i-node 5。

03。3 for that directory here you look that up here it is the i-node that points。

 you at the contents of d1 and so on you can actually trace your way through if you wanted。

 to to see how the files are laid out on the disk。 Now let's remember the directory abstraction okay this is sort of the thing you use every。

 day /usr/usr/lib 4。3 and then you know an actual file inside that really what a directory。

 structure is it's the series of files that are serving as directories which map names。

 to i-nodes or names to i-numbers okay and so you know directories are just specialized。

 files they have lists of file name file number pairs there's system calls to access directories。

 directly which are different from the ones that you're used to for accessing files like。

 make deer removed deer link unlink etc there's a lot of libc support for open deer re-dear。

 and so on those are the libc functions you can do to traverse the directory yourself。

 I wanted to talk about what a hard link is so these this structure I'm showing you here。

 is representing hard links so for instance if in the /usr/directory i have a pointer to。

 directory user lib 4。3 what that means is that the /usr/text points at an i-number for。

 this file which is the directory that's a hard link it's a link between the name and。

 the i-number okay and if I delete this directory then the entry in the this directory goes away。

 and that i-nodes is freed up and put back on the bitmap for free okay so when do you delete。

 file contents when there's no pointers at it so for instance this file user lib 4。3/foo。

 could have another hard link user user lib foo and then I would show two pointers at the。

 same file okay so why do I point that out well first of all the files are self-contained。

 things they have the metadata the permissions you know all the blocks that's an i-node。

 how I name it doesn't matter I can have many names for one i-node this is sounding very。

 Shakespearean right and i-node by any other name it's still an i-node so if you look there。

 are many paths through the namespace they all point at the same i-node the i-node has。

 its own permission structure you know that file tells who's allowed to access it etc。

 And the trick is if I go and delete it from those two directories that are pointing at。

 it the file itself doesn't actually go away until I delete the last hard link to it okay。

 and in fact you should try this not on a file you care about but if you have a file in a。

 file system and you write a program that opens that file and then say goes into an infinite。

 loop and you delete the file that file doesn't actually go away because the i-node is being。

 referenced by the internal structures of your process okay and so then it's only when that。

 process goes away then the file goes away okay so this is all reference counted now you。

 probably heard of the notion of soft link what's a soft link well soft link is a little different。

 than a hard link it's a directory entry that has a path at the name of the file so here。

 we had a path and the i-number of the file whereas a sim link is a path and a name of。

 a file so if you look here here's a normal directory entry which is a hard link file name。

 points at file number a symbolic link says file name points at a destination file name。

 and those file names can be in completely different file systems okay and so these are。

 more like they're supported by open in some of the structures you use every day and for。

 a lot of things it's similar but it's really just sort of a symbolic link is a name to。

 name pointer okay and the problem with a name to name pointer is this is not even guaranteed。

 to work so if this name was on some file system that you threw out later then you can get。

 a bad reference trying to look up a sim link how many people have ever run into a system。

 like that so typically when you download a big piece of software and you unpack it and。

 then you go to compile it what often happens is the compile build directory has a series。

 of sim links to the actual ccode and then you build in that directory and then potentially。

 remove all the sim links so that's all happening by the make and so the files that are being。

 compiled are actually in a different directory for protection reasons and so that's a common。

 structure okay any questions yeah ah the permission while they're the same the permissions of the。

 i-node and the permissions of the file are the same so the i-node contains the permissions。

 so if you look at the very top of the i-node that's the metadata and that metadata says。

 kind of what the you know owner group world permissions are of that file and that gets。

 taken and that's honored by the file system when you go to open something I think the best。

 rule of thumb with i-node is an i-node is the file the file is the i-node okay that's。

 you know if you think of it that way you'll probably be in good shape so the file says。

 who can modify it who owns it who can read it etc which is very different from the fat。

 file system okay where some sense the the permissions are to the extent that there are。

 any permissions in the fat file system are all in the directory which is a little bit different。

 it's not actually associated with the file because there is no i-node in the fat files。

 good questions okay so let's briefly do directory traversal in a slightly different way so what。

 happens when we open /home /cs-162/stuff。txt so here you first have to find the i-node for。

 the root directory so let's say it i-node number two is the root directory here's i-node。

 number two and i blow it up i look inside it's got a bunch of pointers to blocks and the。

 block that holds the root directory the first block might be say block 49 358 in this example。

 and so what I do then is my pull this i-node into a cache down here alright i look up that。

 i-node okay i block 4958 i look inside i see home that points me at a different i-node。

 which i look up that i look up there cs-162 that says that that's in block 732 okay i look。

 at 732 that says that the file itself is in 909 okay i look down at this point i read i-node。

 909 and that starts giving the block to the file so what have i done here i've kind of。

 shown you these are all the i-node involved in that look up this is the contents of the。

 i-node this is like cache that we have in the system we'll talk about this buffer cache。

 a little bit later in the lecture but if you notice i cache not only do i cache the blocks。

 that i happen to load like the i-node but i also cache parts of the name look up which。

 says well when i'm looking at slash home it's uh it's i-node 8086 and i actually store。

 that somewhere in a cache so if i go and try to look up the same file again slash home slash。

 cs-162 slash stuff。txt i can get that entirely out of the name cache without ever going back。

 to the disk okay and so um i like to say at various times i guess i haven't said it that much。

 this term but operating systems are all about caches pretty much everything in an operating。

 systems of cache okay like we talked about virtual memory it's a cache right we're talking here。

 about disk block look up there's a cache we talked about named reversal it's a cache okay so there's。

 lots of caches inside of the files that they're inside of the operating system this is a good。

 example of one okay and then when we've gone all the way to our stuff。txt the important thing to。

 note is that i-node 909 9909 in this example gets put into the file description of the file you open。

 so if you open slash home slash cs-162 slash stuff。txt and you get back a file descriptor。

 that file descriptor points to a file description in the kernel that file description。

 knows about 909 9909 so that means when you start reading and writing the file there's no name。

 look up because you have the i-node of the file itself cached for you as the file description。

 okay all right questions， all right and and by the way by the time you get that file description and have the file。

 descriptor returned we've already checked the metadata of the i-node for all of these guys and。

 made sure that you actually have permission to use it and that's why subsequent reads and writes。

 to that file don't do any checking for permissions excuse me at that point okay all right now。

 so there's uh let's see let me make sure i didn't miss anything how big is bitmap to map the entire。

 disk well it's basically within each group block group there has to be uh big enough for the file。

 for all of the blocks in that block group so you can imagine one bit per block that's part of。

 formatting the file system okay so let me say one thing here which uh i will emphasize。

 briefly if i look inside of any directory here it's a mapping between names and i numbers if i。

 had a directory with a gazillion files in it okay the problem with that kind of a directory。

 structure is that you have to linearly search through the whole directory structure from beginning。

 to end to find the file in the directory you want okay so how many people have ever seen i don't know。

 uh camera software likes to do this they like to put you know all 5，000 pictures from your vacation。

 are in one directory right and you look and you try to look at it and it's just this huge。

 blah set of a bunch of numbers it turns out that that's like the most inefficient way to store。

 files in a directory because in order to find a particular file on open it's got to actually。

 linearly search through every uh every item in the directory till it finds the one you want。

 um so and especially on Unix so Unix is a very um poorly optimized for large directories if you。

 get um there are however some variants of Unix like free bsd and so on that have this thing called。

 directory hash or deer hash that you can optionally use which is actually a b-tree okay and a b-tree。

 is obviously a much more efficient way of storing a huge number of files and so um keep that in mind。

 if you're ever wondering why your software that you're using might go to a large number of。

 directories with a small number of files each it's probably the optimizer on this problem and if。

 you're ever interested in a system where you want a lot of files per directory you might make sure。

 check out whether your system can do something more efficient than linear on the directories okay。

 so let's do another case study here so ntfs is the file system you get in windows。

 new technology file system from the 2000s or 1990 something eight maybe so it's the default and。

 modern windows systems and it's designed in a completely different way than the bsd file system。

 so first of all when you name out the blocks in a large file you don't have to name every block you。

 can use extents which is you name a beginning position on disk and a number of sectors and that's。

 an extent okay and instead of a file access table or an i-note array the master file table is the。

 game here and it's like a database with a maximum one kilobyte size for each table entry and pretty。

 much everything in ntfs is a sequence of attribute value pairs okay which means um which sounds a。

 little confusing but think about it like if i have file name colon a bunch of data that's like a file。

 okay so attribute value pairs are kind of the name of the game and i'll show you some pictures。

 but at each entry in the master file table contains metadata and the files data directly for small files。

 or a list of extents for larger files or pointers to other mft entries for really really large files。

 and i want to point you at this very first one for a second here which is notice that if you。

 have a really small file unlike the bsd file system you can have one mft entry that's all of the。

 metadata and the data itself in that one little structure okay so rather than like an i-note。

 plus a block we can actually have an m single mft structure and so it's more efficient at small。

 files and so this master file table is like a database with very flexible one kilobyte entries。

 it's variable sized attribute records for the data and it uh and you can extend it with a。

 variable depth tree i'll show you an example here so here's uh what extents are so if you notice over。

 on the on the right i have what look like a whole run of blocks and what that represents is a starting。

 point and a link on some tracks somewhere and that's an extent okay and so if i want to have a really。

 large file i can have a bunch of extents that make that file up and so this is much more efficient。

 from a metadata standpoint i have just a couple of extents for a lot of blocks okay now can anybody。

 tell me off the bat what they think might be the what's your immediate thought on the heart what's。

 hard here yes fragmentation great good use of uh good use of last uh midterms terminology yes。

 fragmentation exactly so what we've bought here is efficiency of use at the expense of having to deal。

 with fragmentation okay and so that's where there there has to be some continuous uh improvement and。

 repositioning of things to try to avoid getting too much um fragmentation the other thing is this。

 has journaling for reliability by default which is good so that means if you crash in the middle of。

 something you're less likely to lose data okay so here's an example of a small file um you have all。

 the metadata which is create time modified time access time odor owner i owner ids etc you have the。

 name of the file um and then the attribute list can be just the data is one attribute so all of that。

 in one structure okay here is a medium size file where we have the same record but now the data isn't。

 in the the mft it actually points to a series of extents so now you can see that immediately we。

 potentially get much larger files here right we can handle huge files by just putting extents in。

 there okay so this works well for multimedia okay here is a really big file or one that's really。

 fragmented where the root mft points at a bunch of other mfts those are off the attribute list and。

 then all of the data points at a bunch of uh extents so you can basically generalize this to。

 make a huge file okay automatically and unfortunately if you have fragmentation going on you may need to。

 do this for even a medium size file because all the extents have to be small because you got。

 fragmentation so there's a lot of uh reason to want to re uh defragment the disk on a regular basis。

 okay and here's a huge really fragmented etc you get the point。

 so directories and ntfs are implemented as dtrees by default so if you're working on windows you。

 don't have that linear search problem so a lot of windows boxes uh basically go ahead with large。

 directories um and uh you know basically you can come up with the rest of the properties here。

 for these three um questions so hopefully what i've shown you by a couple of these examples is。

 that uh there are many ways to go from the blocks in the disk to a a file in a file system okay。

 the file system is basically the the naming structures plus the way in which files are defined as made。

 up of blocks there's lots of ways to do that i just showed you the fast file system slash。

 ext three and four that's a common one um the ntfs version here is common on windows boxes。

 and there are a bunch of other file systems out there i'll mention a couple of them later but。

 i i wanted to give you enough variety to kind of see that there are many options here。

 right and they're all about making sure that you can map two blocks off of a disk。

 good now those of you that are busy working on project number two。

 number three i mean so uh sorry mental apps any questions based on what i just showed you here， yes。

 yeah so linux let's see have multiple file systems at once。

 okay so that's a great question the question was suppose i uh i have many different file systems。

 and linux and i open a file system and there's no i note in it what do i do。

 okay so we're not going to talk about this today but maybe in a week there's something called。

 the virtual file system layer dfs what the virtual file system layer does is it provides something that。

 looks like i-nodes to the upper layers of the operating system even when the file system doesn't。

 have them and so i don't want to go into this in too much depth because i don't want to confuse。

 you yet but in the case of mounting a fat file system into Unix or linux what happens is that vfs。

 layer has a way of faking the presence of i-nodes so that from above it looks like there are i-nodes。

 in there even though there aren't in the underlying system and there's a layer of adapter code there。

 that makes it look right okay so at least in the case of linux and Unix variants uh you can have。

 many different types of file systems all with different properties to them and where this comes。

 up is when we start talking about the nt or nfs which is the network file system there's an example。

 where any i-nodes or anything are up on the net somewhere the vfs layer lets you fake it as if。

 they're local and so when you're doing open close read write operations from above that virtual。

 file system layer will turn those into operations out on the network for you so i guess the right。

 answer to your question is abstraction is how this is fixed and in the case of turning a fat file。

 system into looking like it's got i-nodes there's a good example of uh maybe twisting yourself into。

 a pretzel for whatever but i don't know if that's a good reason or not but it does allow you to have。

 many different file systems mounted in linux so good other questions。

 all right so this is a good uh breaking point let's just take a brief break everybody can stand and。

 stretch and we'll uh talk about something slightly different。



![](img/859b68e7047273cc680143916f10266a_1.png)

![](img/859b68e7047273cc680143916f10266a_2.png)

 okay let's pick up so there was an amusing question in chat about uh new technology file system where。

 does new technology come from well it was new at the time this is uh this is the danger of putting。

 the word new and anything uh someday it won't be um so let's talk a little bit about memory mapping of。

 files and um let me just get this waking up here hello here so uh so uh。

 so traditional i-o that you're all used to involves open read write close system calls right and the。

 thing about those system calls is there's a lot of copies involved because the data comes off the。

 disc it's copied into the buffer cache and then it's copied into your user buffer on the way to your。

 application and so um you know that that can be a waste uh but the question might be what if we。

 can map a file directly into an empty region of our address space and then just use loads and stores。

 and wouldn't that be nicer it's almost an implicit paging in when we read it and a write-in eventually。

 page out when we write it and so uh this is actually not novel if you think about it from what we've。

 been telling you about in the class because when we talked about exec what happened was the uh the。

 binary you were going to run got mapped into a chunk of memory and then as it started running it。

 would page fall and pull in the binary and keep running so you've already seen this idea but i'm。

 going to explicitly make this part of the thing the way to think about files for a moment so if you。

 remember back to virtual memory right we had this slide where you had an instruction that was using a。

 virtual address it uses the mmu it looks up in the page table that generates the the physical frame。

 and an offset and that particular one works fine but then there might be another one where you go。

 to the page table and the entry is marked as uh not present or invalid you get a page fault。

 then what well of course all that happens there is you get an exception it goes to a page fault。

 handler in the kernel the kernel loads the page off of disk it maps into the page table to point at。

 it and then it puts the process back on the scheduler or the thread back on the scheduler we retry the。

 instruction and it works whoo okay so that's demand paging that's last midterm right so now。

 here we have the same idea because this uh page table and mmu is still going to be around but。

 we're now going to memory map a file to a region virtual address space so here。

 we're going to go ahead and use the mmap system call and it's going to put some entries in the page。

 table which are not filled yet but they're essentially going to point at the file。

 okay and that means that there's a region of virtual address space right here that if you do。

 reads and writes in there you end up reading or writing the file so for instance let's say we。

 uh have an instruction that's a load it tries to go in here we get a page fault because nothing's。

 been loaded to the file the only thing we've done is map we go through the page fault handler。

 it loads something off the file that we access puts it in physical address space and then we're。

 going to map this correctly so that's that dotted blue line and now when we retry the instruction。

 it just works and we read the contents of the file so notice that we're using that virtual memory。

 mechanism that's already there to allow us to access our file just with regular loads and stores。

 or array accesses or whatever okay and similarly when we go to write in this region it's going to。

 update that part of the physical address space and assuming that we close or flush it'll get pushed。

 back out to the file and so now with mmap we can basically access things without open close read。

 write well we actually have to do an open first and then a mem map but then we can just do we don't。

 have to use the read and write system faults we just do loads and stores okay questions yeah。

 so it gets flushed on close and a few other things that's part of this you can also explicitly flush。

 regions okay that's part of the interface so here's the memory map system call you guys can run。

 man on it and look it up but notice it's got several arguments i know this is a little bit。

 hard to read but one of the arguments is a part of your virtual address space where you want it。

 to map your file okay and so i can actually say well here's a spot that doesn't have anything in it。

 please put my file here now if you don't want it if you want to be lazy you could just put a zero。

 there and the operating system will find a spot for you okay and then there's a bunch of arguments。

 the one i really want to point out here is this one which is the file descriptor of the file。

 and an offset in the file that says kind of what file and how far in it should be mapped in the。

 memory space okay so uh so the question here is since files could be very large won't multiple of。

 them drain all the available virtual addresses well they would if you map too many large files however。

 if you're using a 64-bit processor then you're not going to map so many files that you use up the。

 address space so clearly on a 64-bit processor this is a non-issue on a 32-bit processor you got to。

 just be careful okay hopefully that answered that question so it's used for both manipulating files。

 and sharing between processes so if you look here is an example i'm going to walk you through。

 this code very quickly but basically we have to include a sys/memman。h but here's a variable。

 something that's global set to 162 and we have a couple other variables on the stack and then here。

 we're printing you know addresses just so we can see where things are in memory you know where is the。

 global data where's the stack etc but here's the key thing now we're going to open the file read。

 write okay there's the file if it fails we have an error in exit otherwise here we do a memory map。

 notice the first argument zero which is saying well pick something for us i don't really care what。

 address it's at and then over here is the file descriptor and offset zero and then we check our。

 error returns and then finally we're going to say basically we're going to put that's put string。

 m file so notice what's funny here see this m file that is the address that's returned from。

 mem map so one way to look at that is there is a string at that address that has the whole。

 contents of the file so if i do a puts a put s of mem file it's going to just print the whole file。

 on the screen okay so take a second to see how weird that is right that's not the way you normally。

 think of accessing a file i mapped it in memory and now that memory address which is notice it's。

 a char star so that came back from mem map i can say put string and ask it and it'll put the whole。

 thing out and furthermore a little weirder is i say string copy into m file plus 20。

 let's write over it so what that does is that's actually writing over part of the file and as。

 soon as i do a close and exit it gets flushed out okay and notice how easy it was i just wrote over。

 a part of the file now if you look here for instance is an example where the file test。

 had this in it this is line one this is line two this is line three this is line four。

 and when i run m map test this thing it first tells us those addresses and then it tells me。

 what address the memory map was at see this address here it's different from where the data and the。

 heap and the stack is it's a chunk of free space notice how it's just above the data segment a little。

 bit and then we ran it it exit but notice that i didn't do another put s at the end here i just。

 let it string copy over it and then return so if i now cat that file test notice it no longer says。

 this is line one this is line two this is line three this is line four it says this is line one this。

 let's write over it line three this is line four okay so that string copy copied over the file。

 okay questions， now what's interesting about mam map is i can do this i can take a file and i can have two processes。

 mam map that file and now they can share so this is a way of setting up a shared segment between。

 two processes where all of the data they're reading and writing is in memory but it's backed by a file。

 okay now another thing you could do is you can do what's called anonymous mapping where you don't。

 even have to have the file and that's a way of basically getting shared memory that has no file。

 backing that you can share between processes okay so i don't want to go into into depths and all。

 of the different options you got here but this is kind of the idea of how you would map memory so。

 that you could share reads and writes between processes okay all right question。

 now notice by the way something interesting here the file is a bunch of blocks on disk but we've。

 mapped the file into memory so that means the way the blocks come into memory depends on the file。

 system which is actually between the disk and the memory and so when we page fault and pull stuff。

 into memory we're actually invoking the file system underneath so so all of the i-nodes and so on get。

 used to figure out sort of what order the blocks of the file get put on into memory transparently by。

 the way you don't have to worry about that because the idea of a file system is you don't worry about。

 it right the idea of a file system is the files are on the disk and you don't care how they're structured。

 okay so now let's we've been kind of hinting at the buffer cache so the kernel has the copy。

 disk blocks to main memory to access their contents i had this question a couple times on piazza and。

 i think in class here at one point or after class why can't you just read a byte off the disk well。

 the disk doesn't work that way right you got to seek rotate grab a whole sector minimum and then you。

 can't even get one byte out of that sector you got to load it into memory and then you can look at it。

 okay so basically when the kernel is accessing a disk it's either pulling whole sectors in or pushing。

 out whole sectors and so where does it go where does that data go well there's a cache called the。

 buffer cache which is a set of physical d-ram that's set up inside the kernel to help cache things。

 okay and it could be data blocks or i-nodes or directory contents okay that's the buffer cache。

 or it could even cache names when we do name reference references where you trace through a。

 bunch of directories that can also go in the buffer cache so the key idea of any cache is。

 exploiting locality by caching disk data in memory okay so let me pause on this too。

 why are we caching in d-ram this is different from the processors hardware cache that's fast。

 inside let's go this way for you guys the processors hardware cache that's fast inside the processor。

 for accessing d-ram that's a hardware cache i'm talking about d-ram's a cache on this really slow。

 disk okay which is what what's the speed of a disk read relative to instructions。

 at least a million right a million instructions maybe off by a few orders of magnitude one rare。

 another but it's a good number to remember maybe i'll make sure it's on the last exam we'll see。

 whether you guys remember that but the point is the d-ram is a hundred nanoseconds the disk is。

 milliseconds that's a big difference right so there's a really good reason to cache into to memory。

 and so the buffer cache is really memory used to cache kernel resources including disk blocks。

 and name translations and it can have dirty blocks so a dirty block as you remember from when we。

 talk about virtual memory is a block of a file that's been updated but hasn't been pushed out to disk yet。

 okay and so here's one way to look at this the file system buffer cache。

 here's our block groups over here there's some memory and the memory just has blocks of a。

 bunch of different types in it and so for instance let's suppose that we uh we could have data blocks。

 or gray i-nodes or green directory data blocks or yellow maybe the bitmap is is red all of these。

 things get allocated in the buffer cache and so for instance uh we our process control block might。

 have a file description that points it's a my node which is in memory okay and now if we want to open。

 a new file we first have to reach out and find the directory block and the directory we're interested in。

 that gets put into the buffer cache and then it's accessed okay and in that side of that is some name。

 to i number mapping so there's going to be some block that has our data we potentially pull that in。

 okay and what you can see if you look really closely is there's little flags on each of the。

 entries in the buffer cache saying whether it's currently being reserved for an access that's。

 ongoing and so on so there's some synchronization there but the basic idea is that we pull things off。

 of the disk into the buffer cache and uh you know like we're going to read for the time node we have。

 to find what to read and so on and pull it in if we're writing we'll write things which might actually。

 you can't you can't see it too well but down here it says dirty so certain blocks here are marked as。

 dirty and those are ones that the file system is going to need to push out uh to disk okay。

 and when do we evict well we could say that every time we write something in a file we push it out。

 immediately to disk except that that's not always desirable can anybody tell me why yes。

 yeah you do multiple writes to the same block maybe it's a temporary file here's a good one。

 maybe it's a temporary file that's part of a compile it gets created written and thrown out。

 right away before you ever push anything out to disk well there's an efficient use of the uh。

 delaying right okay so because of this structure you can end up in a situation where temporary。

 files don't even have to go to disk even though there's a place they could go so um this is the。

 basic structure and now we can start saying well when do we know we have to push dirty data out well。

 it's a trade-off between trying to get locality of writes and durability way there's data that I。

 wrote that I really don't want to lose it's got to get pushed to disk okay and so we can start。

 having some of this discussion so for instance the buffer cache is entirely implemented in software。

 unlike memory caches and the tlb which is partially in hardware blocks go through transitional states。

 as we said between free and in use and dirty okay being read from disk written to disk etc。

 blocks are used for a lot of purposes from the buffer cache so you can have i-nodes in there data。

 for directories and files the free map and the os maintains pointers in there so i've kind of。

 given you this idea that it's this flat thing of blocks it is it's a chunk of memory that the。

 disk that the os uses to cache all sorts of stuff and um on termination like process exit or open or。

 read or write then things will get flushed out into the buffer cache often um what do you do when。

 the buffer cache fills up well that's a replacement question remember in virtual memory we had the。

 whole discussion about do we do a clock algorithm or you know pick one pick your favorite replacement。

 algorithm same idea here okay um so what's the replacement policy well what's nice about the。

 buffer cache is since we're doing things at the granularity of disk reads and writes we can actually。

 link all the blocks together and afford to do l l r u unlike in the virtual memory system where。

 we're talking about loads and stores here we're talking about disk reads and writes and so we。

 can do l r u so most file system caching is done l r u with the one big disadvantage you should。

 try this sometime if you do something like this at the that the root find dot dash exact crap。

 foo at the root file system that's gonna go through every file in the whole disk looking for something。

 and what do you know well that's gonna load all of those files push them into the buffer cache and。

 then throw them out okay so that's a very non local thing to do and so this is a good example of。

 bashing a buffer cache and um there are ways around that some file systems let you say this is ever。

 never gonna be reused okay so what are some other replacement policies so some examples are you。

 could say i'm only going to use this once don't put in the buffer cache etc okay now how big is the。

 cache how much memory does the o。s。 allocate to it so when we talked about virtual memory we said。

 virtual memory is a cache on the disk where the disk is storing the contents of memory now i'm saying。

 the buffer cache is a cache on the disk where the disk is storing files so those are two slightly。

 different uses of DRAM okay for caching and so how do you pick do i have more or less virtual memory。

 of physical memory for virtual memory versus buffer cache and it turned out um you know if。

 there's too much memory of the file system cache then your virtual memory will always be a page faulting。

 and if there's too little memory for the file system cache then applications may run slowly。

 because the files don't work well and uh the real solution is to have a dynamic adjustment。

 which sounds obvious these days but it turns out in the old days in the original unices you。

 actually had to pick how much memory was in buffer cache versus virtual memory and you compiled the。

 kernel that way and it booted that way okay today it's adjusted dynamically based on usage which is。

 kind of nice okay so since we have a cache a buffer cache now we can start talking about。

 prefetching so one of the things that happens with the file system in buffer caching is when you read。

 one block it'll read a couple more that's called prefetching and that's built in to the file systems。

 and the reason that's useful is we're exploiting the fact that most common file access is sequential。

 and we have a cache to put stuff in so you read a block might as well pull the next couple in。

 because it'll be really fast by pulling them off disk and you just put them in the buffer cache。

 and when you go to read stuff it first always checks the buffer cache before it goes to the to。

 the disk so if you have sequential access this read ahead prefetching is doing a really great job。

 okay can anybody tell me uh what are we fixing here what type of cache miss are we fixing when we do。

 prefetching yes yeah these are compulsory misses that we're saving yep very good um the other thing is。

 if you have a bunch of uh accesses being prefetched from different processes plus a bunch of things。

 being written now potentially you have elevator algorithms that can choose which things to pull off。

 of disk and to push on to disk to keep for locality okay so the idea of having slightly more accesses。

 going on that are immediately being requested actually is good from an elevator algorithm standpoint。

 so how much do you prefetch well too much prefetching basically does what's called poisoning or。

 dirtying the cache and so you can get delays in other requests because you're busy prefetching。

 and somebody needs to use the disk for something else so there's problems there if you do too little。

 then you got a lot of seats because you have to keep going back and so how much do they do well。

 a lot of systems grab the next one or two blocks that's a pretty good heuristic that works pretty。

 well another thing is this delayed write idea which i kind of implied just a few moments ago。

 these are all of the buffer cache blocks that you've written data into but haven't pushed out to。

 disk those are called delayed writes okay and you know write system call copies data from the user。

 into the buffer cache and quickly returns to user space so when you write a file and it returns that。

 does not mean that that file is durable it does not mean it's on disk it means it's in the buffer cache。

 okay so it turns out that there is uh there are system calls like sync that you can call that push。

 things out if you really care okay but the default is that when you write uh do a write system call it。

 actually goes into the buffer into the buffer cache not immediately to the disk and so read is also。

 fulfilled by the cache so because i can read and write and it goes into the buffer cache but not the。

 disk the buffer cache makes sure that i always see a good coherent view so one process wrote some。

 stuff and the other one reads it it'll immediately see the data even though it's not on disk。

 everybody with me and that's because the buffer cache is there and we just make sure we always。

 go through it what's going to get really interesting is when we start talking about network distributed。

 file systems that level of coherency is a much bigger deal okay it's harder to get。

 you got two processes on different nodes and they're accessing a network file system。

 then you're not guaranteed that you're going to see each other's rights okay and that's going to be。

 something we have to deal with but fortunately if we have one node we're good and so when does the。

 data from a write system call finally reach disk well when the buffer cache is full obviously。

 that's one reason to push things out but the other thing which you probably imagine is important is。

 we periodically flush the dirty things to disk okay and it turns out that original。

 unix had about a 30 second flush period so it's possible if you were to crash the machine that you。

 would lose the previous 30 seconds worth of rights okay so i just want to pause there for a second。

 think about that that says if you're running something you're writing data on it and you might lose the。

 previous 30 seconds when it crashes now the way you fix that is if you really care you do flush。

 operations okay and sync operations but this is clearly a whole and it's the trade-off between。

 performance and durability where we've gone for more performance less durability and what we're。

 going to do probably not today but what we'll do next time is we'll look at how can we still get。

 this performance advantage while having the durability and what we're going to do is we're。

 going to bring logging in okay and logging is going to give us a way to keep our rights on some part。

 of the disk that we can write really efficiently while still having the high performance buffer。

 cache in here and okay and that will be how we'll fix this so the the advantage of this delayed write。

 is return to user quickly without writing the disk the scheduler can potentially order a bunch of。

 requests by the elevator algorithm because you you let a bunch of them be there and you just send them。

 out you can delay block allocation so it might be possible to allocate a bunch of blocks at a time。

 let me pause with that for a second you remember how I said you do an open of a brand new file and。

 then you write a few bytes and you write a few more and you write a few more if you have delayed。

 rights you can make sure that the blocks go into the buffer cache before they're actually allocated on。

 disk thereby letting the file system figure out how large your file actually is so it can allocate。

 a nice contiguous stream so the buffer cache gives you enough delaying that you can do a better。

 allocation job okay and some files never actually make it all the way to the disk so this is those。

 uh temporary files from compiling okay so buffer caching versus demand path uh paging so the replacement。

 policy for demand paging you can't do lru so we used an approximation uh not recently used or the。

 clock algorithm for the buffer cache lru is okay the eviction policy is demand paging in uh the case。

 of uh or it's a it's a it's a vick not recently used when memory is close to full excuse me in the。

 buffer cache you write back dirty blocks even if they're used recently um dealing with persistence。

 state the buffer cache you write back dirty blocks periodically to minimize data loss and that's that。

 periodic 30 second flush and it's a close not foolproof because you can still crash and lose your blocks。

 okay and uh what if the dirty block was for a directory well that really screws you up because。

 if you have a dirty block for a directory that points at a file and it doesn't get pushed out now your。

 metadata is inconsistent okay so you can lose a pointer to the files i node uh in the file systems。

 now inconsistent so that's a little non-smile that's a frony face okay so the takeaway is that file。

 systems are going to need good recovery mechanisms which is kind of our next topic so let me let me。

 pause there and give you uh so in conclusion we've been talking about what a file system is it's。

 transforming the blocks of a disk into files and directories it's optimizing for size access and。

 usage patterns you're maximizing sequential access allowing efficient random access and it projects。

 the os protection and security regime regime into dino's so whatever your system does for security。

 it's in the i-node piece okay files are defined by an i-node header naming translates from user。

 visible names to actual system resources and we talked about how directories are just files used。

 for that lookup and then 4。2 bsd had this multi-level index scheme plus heuristics for locality。

 the file layout is driven by free space management and so i told you a lot about bsd fast file system。

 to optimize for sequential access we talked about how you can mmap files and so that's a deep。

 integration between virtual memory and the file system and then we talked a lot about the buffer。

 cache which is memory used to cache resources including disk blocks and name translations and。

 we talked about lots of distinct updates to blocks and so next time we're going to cover。

 how we can recover if we have a bunch of state that's not written to disk but we crash okay that's。

 going to be the next topic so i'm going to say goodbye to everybody so hope you have a great。

 rest of your day and i'm not sure i'll be here on Thursday Anthony might be but we'll definitely。

 pick this up when we get the next lecture。

![](img/859b68e7047273cc680143916f10266a_4.png)

 [ Silence ]。