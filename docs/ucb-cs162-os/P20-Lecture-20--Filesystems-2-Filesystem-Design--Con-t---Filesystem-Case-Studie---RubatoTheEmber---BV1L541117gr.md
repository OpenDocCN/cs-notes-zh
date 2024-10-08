# P20：Lecture 20： Filesystems 2 Filesystem Design (Con't), Filesystem Case Studie - RubatoTheEmber - BV1L541117gr

 Okay， everybody。

![](img/a18cf2fb36816e8a629cbe9c653b7153_1.png)

 Welcome back。 Today we're going to pick up where we left off on file systems。

 And one of the things I wanted to do is show you the new version of the slide。

 So I decided that there was a little bit too much overloading of。

 And so if you remember what we were talking about here was the notion of overhead。

 where if you had a gigabit per second link， which means the total bandwidth is divided by eight that's 125 megabytes per second。

 And a startup cost of one millisecond。 Then you get a curve that looks kind of like this in terms of the effective bandwidth。

 What's that mean？ Well， that effective bandwidth isn't 125 megabytes per second for small packets because your overhead is getting in the way。

 right。 And then as you make the packet larger， then you get less and less of the time is spent in overhead and you can get closer and closer to the total bandwidth。

 So if you notice now this size of packet here is as X invites。 And so hopefully this is easier。

 So the thing that we talked about here was the half power point。

 or the whatever half point is basically the point at which you get half of the total bandwidth。

 because your packets are large enough to overcome enough of the overhead that you get half of the total maximum bandwidth。

 So if you have a larger packet you could get closer and closer to that 125。

 So I wanted to make sure there were no more questions on this before he left。 Yeah。 Yeah。

 that's the， so there's always a maximum link and with involved in a calculation like this so this one it's 125 megabytes per second。

 So for a different bus， this is sort of like an ethernet link if there was a different bus it would be a different bandwidth would be the max and this thing would converge to something different。

 Okay。 This linear latency here is very standard model。

 And then you want to try to get as simple as possible it's basically the latency to transmit a packet of size X is that overhead plus X over the bandwidth。

 So this is the startup cost and the second part is the time the raw transmission time。

 So this is not rocket science but I wanted to make sure you saw the new and improved version with the better variables。

 All right。 Sorry about that。 Yeah， go ahead。 So be oh this is the W。 Oh。

 there's a typo there that's piece of W。 Yeah。 One more typo。 Okay。

 That's the point at which things are。 It's the exit which the transmission band with is half of the max。

 Okay。 So the other thing we did last time， which was more involved was we talked about queuing theory。

 And remember that the queuing we're dealing with in this class is purely equilibrium queuing theory。

 which means that this queue has a stationary average link。

 So basically over time the average number of things coming in meets the average number of things going out。

 Okay， that's equilibrium。 And what do we mean by that that means that if you look at this whole system。

 Things are coming in things are going out， but you look on the average they're equal。

 Now of course what that really means is that the service rate of the server is faster。

 Than the arrival rate， but their periods of time where the queue is empty and so that's how it averages out。

 Okay。 And so parameters we talked about that matter was this lambda parameter。

 which is the arrival rate。 And in the queuing theory we do in this class it's very simplistic we assume that things arrive with memoryless distribution that said exponential distribution。

 We also said that the server could have an arbitrary distribution。

 And so the service time T sub sir is the average time。

 but it could be an arbitrarily complicated distribution。

 And so that's the average service time sometimes called the first mean， right。

 And then C is this new thing we introduced which was the variant squared over the mean squared and that's unitless。

 Okay， and what's kind of cool about C was。 If you take a complicated distribution and you boil it down to C。

 that turns out to be enough to figure out what the queuing is going to be like。 Okay。

 so that's why we even introduced it。 And if you remember sequel one corresponded to memoryless。

 So then we can derive some numbers like the service rate new is really just one over T sir。

 That's the average speed at which things exit once they hit the server。

 The server utilization which is not new it's you has to be between zero and one and it's really the arrival rate over the service rate and that needs to be less than one because otherwise queue fills up。

 Without bounce right。 And then parameters we want to compute we talked about the time spent in the queue。

 And the length of the queue those were kind of two things in the length of the queue we got out a little law from last time which is lambda times T Q。

 Okay， so now before I give you and right remind you of the key results we had from last time were there any questions on these parameters。

 You should be able to take a system that's described to you and kind of figure out at least what these red things are lambda T sir and C。

 And then you can plug them into the equations to figure out the time you're spending in the queue。

 Okay， and we went through a problem last time which I'm not going to go through again。

 So the two results we had were the memoryless service distribution and that's when it's a memoryless input and a memoryless output called an mm one Q。

 And in that case the time you spend in the queue is this the service time times this scaling factor。

 And then you over one minus you， and the general version was the one in which this server has an arbitrarily interesting distribution。

 And that's just like the memoryless one except we insert this little factor in the middle here of one half one plus C。

 All right， and when C is one， one half one plus one is one。

 And so this mg one reduces down to mm one one equals one。 Okay， are there any questions on this。

 The key thing that's interesting hopefully for you guys here is that we see this。 So the latency。

 or the time or whatever you spend in the queue grows without bound as you get to the 100 power point。

 Okay， so when you get to 100% this， goes to infinity if you had an infinitely long queue。

 And that's really comes from these two factors of you over one minus you。 All right。

 and that you're going to see this general behavior pretty much in almost all of the queuing problems you're ever going to run into。

 You really like queuing。 Actually a series of books by Klein rock on queuing and I'm sure there's a good course on the Corey side that talks about queuing to。

 but this is enough for this class。 So I'm going to leave this unless there were any more questions about variables or anything。

 Good。 All right， you're now experts。 This is your primary back of the envelope way of figuring out what a queue is going to do to you。

 Okay。 Now where we left off last time we were kind of asking when is disk performance highest。

 So right now I'm talking about spinning storage disks。

 And you know the thing about spinning storage is what you got to move the head。

 You got to rotate to the right sector and then you got to read。

 So it's going to be fastest when you don't have to do any of the seeking or the rotating and you're on an actual sector and you just read a whole bunch of them。

 That's going to be the highest bandwidth off of a disk。 Okay。

 because you're not moving anything and you're not waiting。

 And so big sequential reads are going to be something we want to optimize for when we start building file systems on top of disks。

 The other thing that's kind of interesting is when you have other stuff to do so that you get a bunch of requests in and they can be sorted。

 I'm going to show you this in a second in a way that minimize seeking。

 So the thing about a seek is it takes time and you got to kind of go into the right cylinder with the disk。

 Right。 And if you have a whole bunch of requests， then it's just like an elevator。

 You can service on the way in， rather than having to go back and forth like this and so the ability to have a bunch of requests and sort them is a way to get better performance as well。

 And of course， as with everything else we've talked about in this class around resources it's always okay to be inefficient when things are mostly idle。

 So the resource is not the bottleneck and it's not in the middle of everything then being a little bit inefficient it's important。

 It's a when it's not mostly idle。 When it's mostly full。

 then people really start seeing things and this here， this curve is a mostly full curve， right。

 This is that I'm trying to get as much out of the disk as I possibly can and that's when these latencies go way up。

 Does anybody remember what was the root cause of the latency going up。 Yeah， burstiness。

 If you look at that burst slide I showed you last time， you still get the same average。

 but you burst a bunch of things and then you have a longer period and then a bunch of things。

 And if you look at how that lays out。 There are periods of time when the queue is empty and there's nothing for the disk to do。

 And there's no way to get that time back。 Because there's nothing for it to do。

 And so burstiness immediately starts expanding out what you can do and as a result。

 The burstier things are and the closer you get to 100 power point you get more and more build up of the queue and that's why what's going on。

 Okay， so you know you can think of all sorts of optimizations。 All right。

 and so let's talk about a couple of things。 So one we could do is scheduling of the disk。 Okay。

 so we're no longer talking about scheduling of this you were talking about scheduling of the disk。

 And here you could imagine that you got a bunch of requests。

 And this could be from inside the operating system outside the operating system doesn't really matter。

 And those requests are for something like you know cylinder two sector two or cylinder five sector two or cylinder seven sector two。

 And if you schedule them one at a time。 The best you can do is you move to the right cylinder you read then you go to the next one you go to the next one you're going back and forth and you're wasting a whole bunch of time。

 And then what you do。 So that's a FIFO order。 So by the way as you might have gathered we don't like FIFO in this class right we didn't like FIFO when we scheduled with it we don't like FIFO here。

 It's fair among requesters but it's a really bad way to utilize the disk。

 You're spending all your time seeking。 So here's another idea shortest seek time first。

 And what I'm showing you is suppose we have a request here that I've numbered 123 and four relative to where the disk head currently is so right now it's in the middle。

 And what I'm going to do is I'm going to work my way out I'm going to gather number one which is poses two and then three and then four。

 So the disk head is just kind of scanning in as I'm doing my operations。 And this is good。

 Now this is actually called shortest seek time first but today you actually have to take the rotation that they had and everything so it's really taking a spiral on out。

 So this is good。 Reducing reducing the seeks but it can lead to starvation。

 Can anybody figure out why it can lead to starvation。 Yeah。 That's right。

 So the problem with this is suppose that we were in the middle of the disk and a bunch of requests start showing up there well we're going to go back we're going to stay there because that's moving the head the lease。

 We're never even get to the outside。 Okay， so there's another thing called scan which is the elevator algorithm the one way elevator algorithm。

 And the idea is that we go to the extreme point and we only move in one direction and then we go back again and move in one direction。

 Okay， and so it has one long seek and then it does picks a bunch of folks up and then a long seat。

 I guess this would be like if you're going for an elevator and it stops and grabs everybody in the way up and then it goes straight down and then does it again。

 Okay， so that's going to be less starvation。 Okay。

 and both scan and SSTF are loosely called the elevator algorithm if you were not being particularly。

 Specific。 Okay， and why is the elevator algorithm it's like an elevator right you pick people up on the way。

 Okay， and this is a really good way to optimize for for seek time but it means you have to queue some things。

 So here's an example where by queuing and delaying the overall satisfaction of these requests we can get better overall system behavior because we can queue。

 We can reorder and then the system is faster overall。

 So this is another example where cues can actually be a good thing。 Okay。 All right。

 and so then see scan is the one I just mentioned that goes all the way back。 Okay， so let's。

 So now the question is if you were going to do something like these elevator algorithms。

 where would you do it。 Okay， again， this controller that's a that's a great right answer。 Yeah。

 it used to be in the old days。 The disk controllers weren't very smart and so the OS did the elevator algorithms themselves。

 Okay， and then what happened was the controllers got smarter and smarter and they started putting all that logic in there in the controller and now what happens is the OS submits a bunch of requests。

 In parallel or at the same time kind of overlapping and the controller sorts them and takes care of it。

 And so a lot of things that people run into today are things where the controller is doing an optimization and the OS has to just figure out how to stay out of the way。

 Okay， as opposed to the OS knowing everything and controllers are a great example where that matters today。

 Okay。 So， by the way， just to be clear on this so scan is the elevator algorithm that goes up and down and see scan is the one that that only goes one direction。

 Okay。 Now， so in general， how do we hide IO latency because it was clear from this that hiding the IO latency by gathering a bunch of requests is advantageous to the system。

 So now how do we hide that IO latency。 Well， now this is back to three things we started IO on last week。

 Okay， we can have a blocking interface， which is literally what you've been doing all term so blocking interface is an example where when you issue a read。

 it puts you to sleep until there's at least one bite back。 Okay。

 when you issue a right it'll put you to sleep until it can actually do the right。

 So that's blocking so that's not hiding IO latency because the IO latency is smack in the middle of everything right。

 We did talk about a non blocking interface。 So the non blocking interface is the don't wait interface。

 And what it says is you make your read or your right system call and it returns immediately。

 either with some data or an error that says no there wasn't anything for you but it returns immediately。

 Okay， and so it's good about that is I can try to do some IO if it doesn't happen。

 do something else I'll come back so that allows you to do some polling。

 Check for IO do some stuff check for IO do some stuff。 Okay。 Now。

 another option is the so called asynchronous interface。

 which is subtly different from non blocking and I'm going to take a stab at this again because people are never quite clear exactly what the difference is when they hear it the first time so asynchronous。

 interfaces are ones where you set up a descriptor that says I want to read this amount of data from this part this amount of data from this part you can actually link them together。

 And then you submit the file descriptor excuse me submit the asynchronous executions to a special system call and later you get notification that it accomplished was accomplished。

 So that has the advantage that it returns immediately after you schedule it。

 And the advantage that it goes ahead and tries to do all the IO rather than just saying hi I don't have anything for you。

 Okay。 Yes。 It's a couple of things it's actually a an API with system calls that led you describe what you want to do。

 And then you use that use that API to submit so you don't submit the asynchronous IO via like reads and writes there's a different system call。

 And it depends on the library what it is。 And， and then later you can either poll to see whether it's done。

 or you can actually get to send you a signal。 Okay。

 so those of you that are really interested in this and it's a good thing to know about you should Google a IO for asynchronous IO。

 And there's a there's several different versions of it ones that are actually deep in the kernel other ones that are at user level using bridge and they hide that all from you but they're different ways of doing。

 Okay。 So， if we have these kind of interfaces， then we can give the user program the ability to go out and do something else while I always happening and that's kind of helpful if you want to overlap some IO with computation。

 especially if you're trying to do things like elevator algorithms， et cetera。 Okay， questions。 Okay。

 good。 So now， let's do a little flashback to first couple lectures。 So you remember this stack here。

 This is the IO and storage layer stack where you have high level IO with streams and low level IO read right open and system call interface and the file system and the IO device drivers。

 So we've covered the high level stuff kind of in their early lectures。

 And then how to use F open and open and you know F read and read。

 And now we've recently in the last couple lectures been talking about the low level things the device drivers and some of the devices。

 So what's missing， of course， is this thing in the middle。 Okay。

 And the thing in the middle is kind of what makes these devices that are all sorts down at the bottom。

 Uniform enough that they're easy to use。 All of you have done things where you've plugged in。

 you know， USB drives or maybe you put a new disk driver and sst or whatever you've done all that。

 And the interesting thing is， despite the fact that these are all very different。

 you can still think about a file system on top， you can think about directories and files。

 So that's going to be our next topic to figure out where we're going。

 To push on this a little bit more。 So if you think about the users view of IO up at the top here is a variable size buffer and bite level access。

 So I can say read 12 bytes from that file and that works。 Okay。 But it's really kind of a cheat。

 Okay， because underneath the covers， namely inside the operating system for this lecture。

 The file system is really working at block level and typically blocks are 4k and size。

 So when I say read 12 bytes from that file。 It's not like I can get 12 bytes off a disk。 Okay。

 what happens is the file system figures out which block of 4k to pull off the disk。

 Put it into the RAM and then get the 12 bytes that you want。 Okay。

 and so that's the file system is doing that translation from the fact that these underlying things are fundamentally block based。

 but the use， use the Unix interfaces fundamentally bite。 All right。

 and for instance we could have hardware devices like hardware disk drive。 Okay。

 where sectors are the。 Minimum quanta and I've mentioned a couple of times that different disks today have either 512 byte or 4k byte sectors。

 Those are both more and more common 512 was the standard for years and years but。

 In that time period where you really want to impress your friends and you want to show them the seagate website and how you understand how to navigate it。

 You can show them， you know， here's the disk spec and you can see that there is 512 byte or 4k byte options for sectors。

 Now a sector again is the minimum thing that you could read and write off of the disk。

 But typically file systems work in 4 kilobyte chunks。 So if you take a 512 byte sector。

 what it really means is that the file system is going to know to take a bunch of those eight of them in a row to bring a 4k at a time and so going to and from the disk。

 It's limited by the disk at 512 bytes but typically using through the file system it's actually going to ask for 4k bytes up and down。

 Okay。 Now， the other thing we talked about was SSD。

 And SSD is of course completely different looking inside than a disk right a disk is a bunch of platters。

 They rotate。 There's a head that goes in and out in flash。

 What happens is we have a bunch of physical blocks that are made out of flash transistors and the physical chunk that you're allowed to grab is typically 4 kilobytes at a time that's actually called a page if you look in the flash literature。

 And so this interface is reading and writing 4 kilobytes but which 4 kilobytes well that's actually translated by the flash translation layer。

 So if you say I want， I want page number 36。 The SSD actually says oh the OS wants 36 it goes into this little translation table and says oh yeah that's a physical page 1 937。

 So there's actually indirection in the SSD system that does that all automatically and why is that well。

 If you remember with flash you can never overwrite anything you have to erase first right again afterwards。

 And so we need this flash translation layer so that every time we overwrite a logical block。

 What really happens is we go grab a clean erase page right into it swap it swap the old one out in the flash translation layer and now that old block becomes garbage for collection。

 Okay， questions。 Yeah。 The granularity of the accesses。 Oh addresses。

 So the granular that's a good question the granularity the addresses depends on the interface。

 And kind of the minimum quanta that you've got so the， the。

 it's going to be 512 bytes will represent one item you ask for so you'll always ask for 512 bytes on the flash side you'll always ask for 4k。

 Okay。 Good。 Any other question。 Yeah。 In an SSD。 Oh， hard disk drive。

 All of the sectors are already there if that's what you're asking。

 So what happens when you format a hard disk drive is formatting。 The， the。

 the base level formatting actually goes in and for every track on every platter。

 It goes in and it writes a little header on every sector that says this is sector 1， 2， 3。

 4 of that track。 And so that's all initialized at format time。

 And so then when you go to actually write a sector。

 What happens is you move the you move the head into the right cylinder you activate the head on the right track。

 And you rotate until the head reads that little header that says hey this is sector 43。

 And then it starts writing and that's how you write it。

 So the sectors are already always already there if you want to say when you're using it。

 Did that answer that question。 So when you， when you allocate a new file system or when you open a file。

 It's going to look at the information that's already in the file system on the hard disk drive and so before we can answer that question fully let's get some more slides here to see what a file system is。

 Okay， good question。 No， yeah。 So the file system。

 The file system knows the block size and then a little bit below is you could ask whether it's in the file system or in the device driver knows that it's always grabbing 4k at a time instead of the underlying。

 Yeah， kind of depends on it depends on how things are laid out it's different on different operating systems。

 But I mean what what you need to know is at the file system layer we're reading and writing 4k things at a time。

 And somewhere between this green block thing and the actual physical part figures out what the sector side is so it knows how many do access at once。

 Good。 Question other question。

![](img/a18cf2fb36816e8a629cbe9c653b7153_3.png)

 So， how do we build a file system file system is a layer of the operating system that transforms block interfaces of disks or other block devices。

 We looked at this we could SSDs there are many others out there into files and directories and so on。

 And it does that by inserting itself between the high level thing that thinks about bytes and the low level thing that thinks about blocks the file system。

 Gives you the view of directories and files。 Okay。

 and this is kind of a classic operating system move okay we take limited hardware interface the rate blocks。

 And we give a more convenient or useful interface。 And in this case it has naming。

 So you can find a file by name not block number。 That's great right because oh I got to remember what did I put that in。

 In in block number six or number 37 I forget right。 So it gives us a way to name our files。

 It gives us a way to organize the files and directories。

 It gives us a way to map files to individual blocks。 So a file is really a bunch of blocks。

 And then of course it also gives us the way to enforce protection。

 Access restrictions and it gives us a way for reliability。

 Which is despite the fact that there may be crashes。

 We have ways of making sure that we can recover from a crash such that your files are not lost。

 Okay， so all of those things go into the file system。 And again。

 what does it have to do here the users view。 Is really that those files are durable right when you put stuff in a file。

 You expect that you go back to it it's there。 Maybe you don't maybe you're maybe you're clever enough to never put something somewhere and expect to get it back all the time but。

 Let's suppose that that's a goal。 Okay， so the systems view。

 At the system call interface is a collection of bytes。

 And it doesn't the system doesn't care what you're doing with those bytes so you could have a bunch of bytes。

 That are a video you can have a bunch of bytes that are a database you can have a bunch of bytes that are web page。

 The OS doesn't care it's just a bunch of bytes。 All right。

 and so the systems view inside the operating system as I mentioned it's a collection of blocks。

 Where a block the logical transfer unit。 To and from the device and the block size is typically greater than or equal than to sex sector size。

 So again we're going to stick with 4k for the moment。

 And so again another view of what we just said here is here you are the user。

 You ask for the file which is invites。 It goes to the file system which ultimately goes to the desk。

 And so you know what happens if the user says give me bites to the 12。 Well the file system。

 Fetch is the block corresponding to those bites and then it grabs just those bites and gives them back to you to the user。

 And what's we know is going to have to happen is because we're talking about 4k blocks。

 If I asked for 2 to 12 that's only 13 bytes right so it's going to have loaded。

 4k into memory somewhere。 We're going to call that the buffer cache and then if I ask for bites 13 to 26。

 That read will go into the file system the file system will say oh I've already got it and give it back to you immediately because it's been cashed into the buffer cache。

 Okay so one of the advantages of the file system is that it can start invoking caching certainly did match up with the fact that we're asking about bites but also to help deal with temporal locality so that so the caching layer the file system is actually kind of an interesting component in itself。

 Okay， now what if we have to write bytes 2 through 12 well that's a little more complicated so assume for a moment that we didn't read them prior to this。

 So you can't just write 13 bytes onto a disk you have to write you know minimum say 512 bytes。

 So the first thing is the file system takes your right and it says oh goes to disk loads in 4k bytes in the memory and now your 13 bytes get put on top of the ones that were there。

 It can write it back to disk。 So you have to do read modify right in the file system in order to match up with the fact that the disk does blocks but the user does bite。

 Okay。 Now， I just completely waved my hands about an interesting question here which is。

 if it loads the 4k in and it overrides the bites。 Should it write them back to disk right away。

 Yes or no。 How many people think it should write them back to disk right away。

 Good we have one paranoid person here。 How many people think that it should wait。

 A number of two trusting people also。 So， you know the right answer is it depends。 Okay。

 If you're really worried about that particular set of bytes and this is all I've told you。

 of course you flush it back to disk because if it crashes and it wasn't flush back to disk you just lost your data。

 But on the other hand if you're likely to be writing things 13 bytes at a time。

 It's not very clever to push it out every time because you'd rent much rather that some of the but you know one。

 two， three， four， five sets of rights and then push it out。 Okay。

 and so there's a significant advantage to waiting。 Even though you give up on durability。

 And that trade off is one that you have to worry about all the time。 Okay。

 and it'll turn out in one of our next lectures， the discussion of what a log can do to help you with this will come up。

 Okay， because we'll actually log these bites so that if everything crashes we can still get them back。

 All right， so everything inside the file system is in terms of whole size blocks。

 Actual disk IO happens in blocks。 And any reading or writing of things smaller than the block size need to be trans translated and buffered somewhere inside the file system。

 So that's our bottom line here。 We good。 So far so good。 Yes。 Good question。 So wait。

 maybe I let me make sure I understand your question。 So if you're a user。

 do you have to read 4K and then write 4K or you asking about the file system。 Okay， good。

 Great question。 The question was， suppose I'm going to write 4K bytes。

 And I'm going to overwrite 4K bytes。 Do I have to load the data first， overwrite it， store it back。

 Okay。 Yes， unless you give it better information。 Okay。

 and actually most file systems will look at the fact that you're。

 you're writing 4K and that it's on a block boundary and it'll do the right thing because it knows that it doesn't make any sense to load it in over write。

 store it back。 So that's something that would happen at the file system level。 And importantly。

 you as a user。 Don't have to worry about that unless you really care about performance。

 So the only thing you worry about there is a performance thing， not a correctness thing， right。

 Because if it loaded the bytes and you over wrote them and it sort them back， that's bad。

 but it's correct。 Okay， and so you're opening up interesting cans of worms about how to get performance out of these systems。

 and there are lots of ways of pre-patching and delaying writing back and all those sort of things。

 So good question。 Okay， any other questions。 So， I thought I would say it early mid term threes coming up some day。

 So， we'll let， we'll move on。 Oh， by the way， next week。

 I think conflict form is do or something so watching Piazza。

 Project three design documents next Monday， so that's getting a little close。

 Today we're talking we're going to tell you what an I know it is， so that might be helpful。

 The other thing I wanted to say a little bit about is always make sure your T a knows what's going on if you have any group issues of any sort make sure you're keeping them a prize because they're your advocate。

 Okay， everyone of you has a TA。 Hopefully everybody in your group has the same TA just make sure they know what's going on。

 Okay， in addition to the group evaluations， which we have you do make sure your T a understands what's going on。

 Okay， I don't have any other interesting administration today。 I'm not sure these are interesting。

 but I don't have any other administration。 All right。 So， how do we manage the disk。

 So basic entities on a disk are a file is a user visible group of blocks arranged sequentially in some logical space。

 Do you think of a file is a bunch of bytes， a directory is a user visible index mapping names to files。

 So the disk is accessed as a linear array of sectors。 So how do we do that。 Well。

 we start counting on the outside， and we just kind of spiral our way in until we've got all of the sectors。

 Okay， now how do you identify a sector。 Well， in the beginning。

 in the old days as it were sector was really identified by something like cylinder surface sector ID。

 Okay， so which cylinder are you on， which surface are you on， which sector on that track。

 Are you on right。 This is not used anymore。 And the interesting thing about that is。

 Discs were growing in the 80s。 And they started growing to a point that got beyond what the MS does by us could handle。

 And the disk manufacturers couldn't wait for the bias to change。

 And so they started doing something different， which is this logical block addressing。

 And so this logical block addressing， which really makes a lot of sense。

 actually got forced by the fact that the MS does bias。 Wasn't keeping up with disc size。 Okay。

 But everything today basically defines every sector。 And so every sector has an integer address。

 The controller translates from address to physical position。

 And it really shields the OS from the structure of the disk。

 So this is a good thing and this is a bad thing， right。 It depends。

 I guess that's going to be my answer for a lot of stuff today。 Right。

 So this is a good thing because it means that the controller can take bad blocks filter them out。

 map them to somewhere else for you。 And do it under the covers at format time。

 since the OS doesn't have to worry about that。 Okay。

 The reason it's not a great thing is it also means the OS doesn't have pure information anymore about where things are。

 So if the OS tries to build a file system in a way that optimizes perfect perfectly for locality and it does it by thinking to itself well logical block addresses if they're close to each other。

 They're kind of in the same track。 Right。 That's like a heuristic。 It's not necessarily true。

 And so the LBA idea has really kind of shielded things a little bit。 From from the OS。

 And so the question here is so the LBA is maintained in the disk controller rather than the OS。 Yes。

 Now， the other thing that I'm just going to mention here which is kind of also interesting is you can take a disk。

 And you can allocate a bunch of individual partitions that have more total logical block addresses than there are physical blocks on the disk。

 And the way that works is it automatically the controller will increase blocks as they're needed for each of those partitions on the fly dynamically。

 And so as long as all of the partitions don't try to use all of their space simultaneously。

 this kind of works。 Okay。 And so this is this is used often this called thin partitioning。

 This is used in virtual machine deployments。 So， all right。

 But the thing you need to know for today is the logical block address。

 you deeply identifies every sector and it's roughly the case that logical block addresses that are close to each other are kind of close to each other on the disk。

 Okay， kind of。 Yes。 Yeah。 Yeah。 So partition is a logical grouping of sectors on a disk that kind of looks like its own disk。

 like a virtual disk。 And where this becomes very useful。

 I don't know how many of you on your laptops or whatever have two operating systems。

 How many people have windows and Linux or something right。 The way that works is windows and Linux。

 or maybe we have Apple OS is and whatever you want to go， are in separate partitions。

 Plus there's a special boot partition that comes up when you first turn the machine on and it asks you kind of which one you want to boot and then it boots the proper partition。

 But once the OS is running that partition thinks that it's got the whole disk for what it sees。

 Okay， good。 Now。 What is a file system need well it needs to track free disk blocks。

 Because it needs to know where to put newly written data needs to track which blocks contain data for which files。

 Okay。 Need to know where to read the file from。 And you need to track files in a directory。 Okay。

 To basically figure out how to resolve names。 Now there's a question on the chat here is so the file systems implemented in the OS rather than the controller。

 Yes。 So we're now talking about how the OS is going to decide to organize logical blocks to give you a file system。

 Okay。 And so where do we maintain all this information about mappings between directories and files and so on。

 Well， it's got to be on the disk。 Hopefully， right。

 because when you shut everything down and you boot it back your files are still there。 Okay。

 so any of this management stuff we're talking about needs to be stored persistently in addition to the data。

 So what are some data structures that are on disk so it's a bit different than data structures in memory。

 Because we can only kind of access a single block or a range of blocks at a time。

 You can never efficiently read or write a single word ever on these block devices you can only read and write blocks。

 Okay， and ideally you want sequential access patterns if you think about a disk drive it's spinning。

 You'd like to access on most commonly everything on a single track。

 Rather than moving back and forth all over the place okay that's clearly going to be optimal when we're on a hard disk drive。

 When you get to flash drives there's no seek。 Okay。

 but there are some more subtle things like garbage collection that can go on so if you actually write randomly all over an SSD。

 You could actually invoke the garbage collector and end up with a slower access than you expected。

 So I actually answered a question on Piazza for last lecture if you want to take a look at that。

 So durability is says that ideally the file system is in a meaningful state when you shut things down。

 Okay， that obviously isn't always the case。 So if you take you're running a Unix workstation and you yank the power out and it dies。

 That may not be good。 Okay， and why may not that be good well because there'll be a bunch of unflush dirty blocks in the block cache that haven't gone to disk。

 Alright， now a lot of modern file systems like x t three x t four have logging so that if you just randomly killed off all of memory。

 And the machine and you went to boot again it's likely that the log will be sufficient to restore the state。

 So there's a lot of work around making file systems resilient to unexpected failures like that。

 So let's talk a little bit about file system design。

 Some critical factors in file system design are well。

 if you got a hard disk you better maximize sequential access access and minimize seats。

 I even put pre exclamation points here so think of that like shouting I guess。 Okay。 Now。

 from a authorization standpoint， you open before you read and write and so that means that the file system is going to perform all of the permission checking at open time。

 Okay， that's right， you do open that's the point at which it fails and says well you don't have permission to use this thing。

 And what that means is we're going to， we're going to design our file systems around this idea。

 where we check things out first and then when you return from open you got a file descriptor。

 And now you can read and write that file descriptor。

 because you've already checked the permissions and permissions are not checked on every reading right it's only checked on open。

 Okay， and that's going to be a design piece。 The size is determined as things are used。

 I guess I thought this was worth shouting about too but so the idea is。

 if you're writing a terabyte four bytes at a time。

 First of all you better go brew some coffee right。

 But the second thing is the file system has no idea that you're scaling to a terabyte。

 And so it's going to make some choices that might not be great that it could have made better choices if it knew you wanted a terabyte size file like allocate a whole track for this file。

 Right， whereas if you're just doing a little at a time。

 depending on how the allocation works you might just grab a couple of sectors and then a couple of sectors somewhere else and so on and it might not have all the locality you could hope for。

 But that is a fundamental property of the POSIX file interface is basically that under except for hints that some some system calls will give you really the file system's not entirely clear how big the thing is going to be when you're writing。

 Okay。 All right。 And of course we want to organize things into directories。 So， I have you。

 you know I used a really old IBM machine when I was consulting more moons ago than I will say。

 And what was weird about it was you'd mount a disk into your system and there was no directories nothing it was just a flat view of all of the files that were on that。

 and I'll tell you that's a really bad way to organize things。

 So directories you guys don't know how good you got it。 Right。

 Directories directories rock right now， of course they don't really。

 because now of course how many of you forget which directory you put something in。 Okay， that's my。

 my latest problem。 So， you know， probably really search all of Google or whatever on your file system is really the way to go and there are things you can install that let you do that。

 Okay， because we've got so much data。 But anyway， that's another discussion。

 And you need to carefully allocated free blocks so that access remains efficient。

 Now what do I mean by that well， if you have a file and you keep allocating new blocks you'd like them to be all on the same track。

 So， you know， you're not going to want your allocation process to try to give you locality even with imperfect information。

 Okay， so， so here's some components of a file system so if you have a path。

 you know slash user slash home slash， and you take it to the directory structure to look that file up。

 what comes out of that file is something called an i number。

 which is really an index into the i nodes on the disk。 So。

 there's that word i node okay can't say I didn't tell you about that today。 All right。

 and an i node is a descriptor for a file and that descriptor says which blocks are in that file and in what order。

 Okay， and so this i number is really like an array index to the set of all i nodes。 Okay。

 and it's the i number that's put into a directory okay this is a very simple figure but I'm going to stop for two seconds and see if anybody has any questions。

 Yes。 Yes， all of this is on disk。 So the directories。

 So here let's make this really easy so assuming that files are an i node pointing at a bunch of blocks right。

 Then clearly the i node needs to be stored on disk so that I can later figure out which blocks are part of my file right。

 But what's a directory well a directory is just a series of files right that map name to i number。

 Okay， and so really all of this stuff is i nodes and blocks on disk。

 And I'll make that more clear as we go on。 Now， remember the abstract representation of a process this from the early parts of the class kind of in kernel space we had these file descriptors which are integers pointing at what we call the file description。

 And of course if we open food tech。 Then what it does is it actually opens the file and then from that point on we can read and write it using that file descriptor and there's no access control from that point on right that's a how we talked about it earlier。

 Really。 What happens on open is the file description actually has an i number in it。

 which is a pointer to an i node。 Okay， because that's what it means to open the file is to verify the access permissions and load the i node in the memory so that now I can find out which blocks to get to the file。

 Okay。 Now。 So components of the file system so we have file name offset。

 Go through the directory structure gives us a file file number。 Okay。

 open gives you name resolution which is translating a path name into a file number， or i node。

 i number read and write operate on the file number。 Okay。

 and ultimately that gives us storage blocks。 So they're kind of four components there what our directories look like what's our index structure。

 What are storage blocks and free space map are all pieces that we have to resolve in terms of a file system。

 So， where do we get the file number from well that's look it up in the directory structure。

 So a directory is really just a file containing a file name to file number mapping， or i number。

 And the file number could be a file or another directory so what does it mean when you say slash user slash home slash kuby slash。

 Secret file slash。 You know， data。tech。 Well， that's really you go to the root directory you look up slash us are in the root directory it gives you an i number then you look up。

 Homes in the next directory and then you look up kuby in the next directory and so on so you're doing a series of file opens。

 but you didn't have to worry about that because the file the。

 The OS is doing that for you as part of the open system call。 Okay。

 so process isn't allowed to read the raw bytes of a directory because they are formatted in a particular way。

 And so instead there are some system calls like reader， etc。

 which lets you iterate over the directory and i'm sure you probably already used that so we won't go into that in great detail but。

 Why don't we let processes read the directory directly well they wouldn't really know what they're seeing and we wouldn't want them to mess it up。

 So directories structure comes out of what I just said。

 So the abstraction here is directories are specialized files slash user slash user live four dot three and then user live board or three slash food。

 Basically is looking at a series of files。 Okay， and there's a bunch of system calls to access directories。

 So like if you open with create in a directory it'll actually make a new directory entry for you and allocate an i node for you。

 and that's what happens when you create a file。 Okay。

 And there's a bunch of libc support so here's some new system calls that you can look up if you haven't already like open dear or dear redear or redear underscore are for traversing your way through directories so you can do that traversal if you put something like this in a loop。

 Okay。 Yeah。 Yeah， so the file number and i know number those are used kind of interchangeably。 Okay。

 So the directory structure well how many disk accesses does it take to resolve slash my slash book slash count。

 Well you read in the header for root。 That's in a fixed spot on the disk you read in the first data block for root。

 Okay， because you're you're reading that file。 It's a table of file name index pairs。

 You search it linearly。 Okay， so that's because Linux is not terribly clever about the way the director directories are laid out so you have to actually search through the directory linearly。

 You eventually find my。 Okay， so now you read the file header or i node for my。

 and now you go into my and you find you look into my for book。

 And then you read the file header for book and then you look into book for count。

 That gives you the file header for count and now at that point you can start reading and writing the file called count。

 Okay， the other thing I mentioned briefly at the very beginning of the term was the current working directory。

 Really what the current working directory is is it's a per process directory。

 That's the working directory it's really an i node。

 Of the current working directory and it's a starting point for file resolution。 Okay。

 So it's almost like you're pointing at a file that's everything's resolved against but it turns out it's a directory in the case。

 Okay。 All right。 So here's another view of the in memory file structures。

 So if you do a read of a file descriptor it's going into your per process file descriptor table。

 which points at the file descriptions which have i nodes in them。

 Which then points at blocks and so when you open the i node gets pulled off the disk into memory and then it's being used to figure out which blocks to get for your file。

 Okay。 All right。 So this is easy to see。 So now let's look at what we want for our file system。

 So there's been lots of studies over the years。 Of what is data look like in a Unix style file system。

 And so the first observation that's come out of these various studies across many years is most files are small。

 So if you look here， this is a probability of mass function of number of files of a given size by year。

 And if you notice， it's all mostly peaks around small files like 2k or less。

 And there aren't very many big files so we want to be able to deal with lots of small files efficiently。

 And most bites are in large files if we look at the。

 You know the containing file size what we see is that most of the bytes peak out at this like 2 meg or more file size so the big files have most of the bytes。

 But most of the files are small。 So what does that tell us we want to be really efficient with small files but we better handle big files well。

 And what's new of course even newer is multimedia files are really popular。

 And so there's really big files tend to be streamed because they're videos or whatever okay and so we。

 you know， newer。 And so， you know， the systems like ext four for instance。

 are even more optimized toward the large end of the files because they're on server systems with lots of large file。

 Okay， so things to get out of this again other than you know we'll try to deal with lots of small files and be able to handle big files is different file systems optimize for different access patterns。

 There are many file systems out there and you know in the early days。

 When you guys were like freshmen you probably chose whatever file system was given to you。

 But now you can actually consider choosing a file system。

 You know you could reformat things in different ways depending on what you want to get out of it。

 Okay， so I just wanted to point that out so。 So， with the simplest file system out there the so called fat file system file allocation table。

 It's from 1977。 So you'd think it's not very useful anymore。 You'd think， however。

 pretty much every USP card drive or thing you put in your camera or whatever it is。 So。

 basically default to the fat file system， you know the the large versions of them that handled 32 bits or more for addresses。

 And the reason for that is it's so simple that you can actually put it into firmware on cameras and stuff。

 Okay。 Now， the question here a good question was in the chat that I missed is since the directory structures also stored on the disk how do we know the course bonding I know in order to access the structure。

 The answer to that is the root file system is going to be stored at a special place that we can always find。

 And once we go to the special place， then we can resolve everything else。 Okay。

 so here's the fat file system。 The idea is the file allocation table is really just a series of pointers。

 An array of pointers from zero to n minus one where n minus one is the number of blocks。

 And we're going to assume for a moment that we have a way to have a directory so we can translate a name to a file number。

 Disk storage here。 Okay， is just a collection of blocks old data。

 And so that data means nothing it's just a bunch of data until you put the fat part of it。

 And how does that work well for instance let's suppose that we have a file。

 And it has three blocks I'm going to put your block 01 and two of that file can be file number 31。

 Okay， you'll see where file number 31 comes from in a moment。

 But assuming that we have this laid out that way then if we want to read from file 31。

 And we want to go to the second block offset X。 Okay。

 so clearly we're inside the operating system here。

 What we need to do is find a way to find block number two of that file。 Okay。

 and what I've shown you so far there's no way to do that because I've just got these blocks are just mixed up right there just kind of hanging out there。

 So what is the file allocation table do。 Well， we have to index into the file allocation table with file number 31 so that this file we care about。

 We go to entry 31 in the fat and it has a pointer to the next block。

 which is a pointer to the next block。 So if we know that the file number is 31。

 what that tells us in the fat file system is that block number 31 is actually the first block of that file。

 So what we put in the directory which is that file 31 is mapped to the name tells us also where the very first block of the file is。

 Okay， now remember this is a very simplistic file system。 But what the fat does。

 So we could get to block 30 we can get to the first block just by knowing 31。

 But what's in the fat is this linked list of all the remaining blocks that are linked to that file。

 Okay， so we go to 31， we follow the link to 32， which is where block one is and then we follow the link to way down there wherever that is。

 And that tells us block two。 And so in order to read block two， we have to actually go to the fat。

 follow the links until we get blocked to。 And then we can read it into memory and at that point we can index。

 And read offset x。 Okay。 Now the question here， why not link the blocks with having a pointer at the end of the block and have a list of all first positions。

 I'm not entirely sure what the question means there but this is。

 I mean this is the structure they've got and we don't want to put the pointers in the blocks because these blocks are an even power of two。

 And so the fat has to be something separate to make that work well。

 So let's look a little more about this。 So the file is a collection of disk blocks the fat is linked one to one with blocks that's just implicit I don't even have to put a pointer there。

 The file numbers and index of the root of the file file offset is a block number and an offset within a block。

 And then we follow the list to get the block number that we're asking for。

 On use blocks get marked as free。 Okay， so there's a way to say that there is a entry in the fat that represents a free block。

 Okay， and that we can scan through to find a free block when we need one so for instance if we're going to go ahead and write on file 31 a new block three so we're appending。

 Then what happens is we grab one of those free blocks we link it into the fat and now our file has an extra block in it。

 Okay。 Questions。 Good。 Yeah。 That's a great question and obviously has to be stored on disk when things aren't running。

 If it fits in memory。 They will try to fit it in memory。 Okay。

 so part of opening the file system will be to try to get as much of the fat in as it can。

 but if it's a really really really big disk then it might not be able to do that。

 And you can see what's the advantage of getting it into memory。

 Be much faster to find things right because you hop through you could even build an index on top of this in memory if you wanted。

 Right。 Good。 So， here's an example of two files。 So notice how I've actually got yellow and green。

 So where's it stored on disk， how do you format a disk well you just said everything to zero which represents a free block。

 Okay， so that's how you get a brand new disc or format a disc away and notice a lot of things that format a file system。

 You think are deleting data but in fact the data is still there you've just deleted the fat。

 You've got rid of the fat。 Right。 So。 That isn't a clean that's not a secure way to delete your data。

 Okay， and in fact when you delete a file all that really happens is it goes through and it marks all the entries as free for your data still there。

 And somebody who has the right tools can go through there and potentially reconstruct your file。

 Okay。 So how do you quick format a disk you just marked the fat injuries free。

 So the thing that's great about the fat file system is it's simple you can implement it in device firmware。

 But you can see that it's got all this linearity to it right if I'm on a fine。

 The 37th block in a big file。 Yeah， hopefully I'm going to load the fat into memory but then I got to follow a bunch of links to get there。

 So this is not efficient for random access by any means。

 Now oftentimes where you see fat file systems today are on media devices like cameras and phones。

 And things where what you're doing is if you have a video you're probably not ran doing too much random access to the middle of it you're mostly going sequentially。

 So this particular file system kind of works well for sequential access。 Okay。

 But notice that it one thing it doesn't do well is if there's any errors in the fat at all。

 Then you lose everything。 And so there are all of these file recovery programs you see out there that try to look through the blocks and figure out how they're linked together。

 And they typically work a lot better than you might expect。

 But what they're doing is they're trying to reconstruct this guy based on contents here。

 You'd be surprised I see people like shaking their head you'd be surprised at what it can do。

 Which is again why you don't trust in a ratio program to a fat system you want what you really want is something that overrides it with ones and zeros and then one zero one zeros and then zero one zero one and makes it really really really impossible to recover。

 Okay， so what are directories look like。 Well if I want to do。

 Just like in general which we talked about with a fat the directories are linked name combinations of a name and a pointer to an entry in the fat file system。

 Okay。 So that's pretty easy。 And directories a file containing file name file number mappings。

 Free space is left for newly or deleted entries so if I have food。

text in that directory and I delete it what happens is this file that gets marked as free。

 And then the next time I add something to that directory it just links it in there to the free space。

 So the directories don't garbage collect much。 And unless you ask it to file attributes are actually kept in the directory so what's interesting about that is the file lives on the disk。

 And the permissions are in the directory so if you're managed to go and mess up the directory or half the directory and change its permissions now all of a sudden you can access data。

 And that's not independently protected in the fat file system either。 Okay。

 every directory is a linked list of entries， you have to do a linear search。

 How do you find the root directory so this is a should be a key question for you guys now when you're talking about file systems well in the fat file system。

 the root directory is pointed at starts at block two。

 And there is no block zero or one don't ask me why。

 But so anytime you mount a fat file system it goes it finds the root directory it pulls things into memory and now you're ready to go。

 Okay。 All right， question。 Now I'm hoping that this is pretty straightforward right does this seem like a good on ramp to file systems for everybody。

 Not too bad。 Ask your questions if you're not sure because I'm going to show you a better file system in a moment。

 Hard to call it hard to not call this better when it's used by everybody but it isn't a great file。

 Okay， go on。 All right， here we go。 So， let's finish one other little thing here so suppose you start with a file number。

 How long does it take to find a block while you got a。 Got a search through linearly right。

 What's the block layout for a file。 Well， look at this notice how the blocks in this。

 On disk are kind of spread all over the place right I've written block zero and one and then two and then three。

 And because of the way the free list。 Or the free blocks were searched。

 There is no rhymer reason about how things go into the data storage so there's no locality in the fat file system。

 And so， that's not required。 Now it turns out if you took a brand new disk and you started writing a bunch of stuff sequentially just by happenstance。

 Those new files will all kind of be nice and linear。 Okay。

 but now if you delete a file and add some new ones and delete and add some new ones very quickly you'll end up with scrambling going on。

 In the fat file system itself that tries to return it to nice sequentiality。 Now there is this。

 How many people have ever had done block compression kind of optimizers on their file systems。

 These are great when you're， you're having trouble sleeping you put this up and it shows you all the blocks moving around back and forth as it's rearranging them。

 And four hours later you kind of wonder what happened to those previous four hours well。 Alright。

 so sequential access is not great because if you're accessing something sequentially you still got to follow all these pointers and you might not have sequential access random access is also not great。

 So this file system after it's been used for a while isn't great for sequential access isn't great for random access。

 It has lots of fragmentation。 What about small files well small files if they've totally fit in a disk block that's actually pretty good because you're really only pointing to a disk block。

 But anyway， it's okay big files kind of all the same。

 So let's look at the Unix file system Berkeley fast file system。 So I know it's in Unix。

 Look like the following so file numbers and index into a set of I know to raise。 Okay。

 the index structure is an array of I know it's file number index into the array of I know it's each I know corresponds to a file and contains the metadata。

 So things like read write permissions are stored in the I know not in the directory already were very different from fast。

 the fat file system。 And because we've set it up that way we can actually have multiple names for the same file in different directories they just point at the same I know。

 So the file itself kind of hasn't has an independent independent of the way you name it。 Okay。

 and I know it maintains a multi level tree to find storage blocks or files so it's great for little and large files。

 It's an asymmetric tree with fixed size blocks。 The original I know format in Berkeley BSD 4。1。

 Was widely copied by lots of folks so Berkeley Unix。 Yeah， you know。

 this is the home of Berkeley Unix。 Came up with this original idea way back when。

 and it's very similar to the Linux ext two or three file systems which you're likely to run into today。

 So here's the I know structure。 So remember a files defined by an index into this I know to Ray or defined by an I know those are the same thing。

 And if you look at what's in this I know at the top we have a bunch of metadata like what are the permissions to read and write how big is the file。

 And then we have pointers to actual data blocks。 And so the metadata have things like user group owner access permissions。

 Things like a set UID bit or set GID bit saying whether you inherit permissions of this file when you try to execute it。

 And then there's a bunch of direct pointers and a direct pointer is literally a pointer in the I know itself pointing at a data block。

 So this is a logical block address pointing at a data block。 And we have a set of those。 Okay。

 so for instance， we might have 12 of them。 Okay， and why is it good to have a bunch of direct pointers to blocks。

 In the I know itself what does that give us。 Yeah。 Fast lookups of what。

 Gives us sequential access and what do we know about files where we mostly use the direct pointers。

 Small。 Remember what we said earlier we want to optimize for small files。

 That's how the I know structure does that has a bunch of direct pointers。

 Then okay and that's getting at the small files。 Okay。 And then how do we get at large files。 Well。

 we do what are called indirect pointers where these pointers that are down here in the I know don't point at actual data blocks。

 They point at blocks that pointed data block or blocks that pointed data blocks。

 Or blocks that pointed blocks that pointed data blocks。 You get the point， right。

 These are called indirect。 Okay， and so for instance down here you see a triple indirect pointer points to one block that has a bunch of pointers in it。

 They point to blocks that point to blocks that point to data blocks。

 And it's the inclusion of indirect double indirect and triple indirect pointers that give us the large file size aspect。

 So this I know structure is optimized for little files but it handles large files well。 Okay。

 questions。 Makes sense。 Now， so if we look at on disk index。

 we have a sample file in a multi index format。 Here's another case where there's 10 direct pointers。

 How many accesses for block number 23。 Well， what you do is to we have to go down to the indirect block because you've gone past the block direct blocks。

 You have to do look up one indirect block and then you can get your block you want。

 So if you're asked， how many disk accesses that doesn't take me to get to something you can look that up okay and that might show up。

 Who knows that might show up on an exam。 How about block number five or block number five is in this starting part so that's only one look up。

 Okay， etc。 Block 340 turns out you have to go to the double indirect blocks to do that。 Okay。

 Questions。 Yeah。 Right， so you're wondering about how many pointers are in the square the indirect blocks。

 That depends on the size of the blocks and the size of the disk actually right because you need to have enough bits there to point at every block。

 But a simple rule of thumb would be to assume that these are 32 bit things and so if you have a 4k block。

 Right， you can， you can calculate that out， figure it out right it's going to be a 2k of them。 Okay。

 Yes。 You know what so the original was 10 which is why I went to 10 here。 As disks got bigger。

 The centroid of the small files shifted up a little bit so they just added a couple pointers。

 So really， you know， I will say that the original usonic Unix I said that twice now the original Unix。

 I know structure is basically the same as BSD 4。1 in a lot of modern systems in Unix。 So。

 he xt two and three look very similar。 And just there tweaked in some of these things like how many direct pointers and stuff。

 Okay。 So， critical factors in file system designer things like high performance to maximize sequential access open before read right size determined as you write organized into directories etc。

 So， how do we get high performance。 Well， if you remember， this will be our last topic for today。

 If you remember， because of the way disk drives are laid out。

 you want to avoid as much of that seeking moving the head in and out as you can。 And then， you know。

 you'd like to get locality on the disk itself。 And so really we would like to design the file system so that it mostly had locality in it。

 And so， you can all the blocks in a file。 They're mostly on the same track。 That'd be great。 Right。

 And so there's been a lot of work。 So the fast file system and dsd 4。

2 was the same I node structure is 4。1。 So 4。1 had the same problem kind of that the fat file system did。

 which is if you got a brand new file system， and you did a bunch of reading and writing and reading and writing eventually。

 So， the blocks in a file would be scrambled all over the disk。 Okay。

 because there's nothing that was recall lessing them back together。

 So the big innovation in the fast file system was ways and heuristics to try to make sure that in general files had good locality。

 Okay， and I even put up a paper for you guys on the resources page from the original authors of the fast file system which you should be able to understand now about what did they do to get that locality out of the system。

 Okay， so that's the fast file system for Unix。 This is actually also。

 if those of you that might be interested in 262。 This is the first paper we study。

 So it has a bunch of optimizations and it's all about getting locality out of the fast file system when you know you've got a spinning disk。

 Okay， so it distributes I nodes among a bunch of different tracks so they're closer to data so the original file system put all the I nodes in one place。

 namely the outside of the disk。 All of the data was spread throughout。

 That's got two really bad problems one。 If you ever if the head ever crashes and destroys the outside of the disk you just lost everything。

 Okay， and by distributing the I nodes throughout now if you destroy part of the disk the rest of the disk is fine so that was a big deal。

 The other big deal is by putting I nodes spread throughout the disk。

 So you can have all of the files in a directory and their I nodes and the data blocks are all kind of in the same part of the disk so as long as you're in that directory you're not moving very much。

 Okay， so that was a big optimization。 There was bit map allocation in place of a free list which led it do much better jobs of figuring out where the disks were。

 or where the blocks were together。 We also had this 10% reserve disk space trick。

 which is as long as you reserve about 10% of your disk and don't tell anybody about it。

 Their allocation heuristics were much better able to give you locality in the files because it left a lot enough space that there would be long runs of empty disk blocks and therefore you could get locality。



![](img/a18cf2fb36816e8a629cbe9c653b7153_5.png)

 So it's a lot of time to talk about this this time it'll pick it up next week but。

 in fact we will we'll say that for next week as to how some of the changes of the fast file system but in conclusion。

 the file system is that piece that transforms blocks into files and， libraries。

 you know it takes the user's view of files and directories and the block reality underneath and it turns it into something useful。

 And it's all about optimizing for access and usage patterns。

 The file is defined by a header called an i node。 The first thing is this idea of following the path from the route through a series of files until you find the i node of interest。

 a file allocation， the file allocation table scheme is a very simple linked list approach and surprisingly it's everywhere still。

 And then we looked at some actual file access patterns。

 and we started about on the bsd i node structure and we'll pick that up next time。

 so I hope you all have a great weekend。 I hear it's going to be cooler tomorrow so that's good so stake bowl for the rest of the day。

 And。 Thank you。

![](img/a18cf2fb36816e8a629cbe9c653b7153_7.png)