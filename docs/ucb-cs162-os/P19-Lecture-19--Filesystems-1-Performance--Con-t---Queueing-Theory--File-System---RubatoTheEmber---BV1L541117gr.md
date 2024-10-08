# P19：Lecture 19： Filesystems 1 Performance (Con't), Queueing Theory, File System - RubatoTheEmber - BV1L541117gr

 Okay， everybody。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_1.png)

 Welcome back。 Again， so we were talking last time about disks and SSDs。 And among other things。

 this is an example of a disk that multiple platters two sides。

 You think of it as a cylinder is it the set of all tracks， which are concentric circles。

 moving all the way down through the stack。 And the reason we think of a cylinder as a thing is the heads move all together to a given。

 cylinder and then you rotate to actually read the sectors。 Okay。

 And the reason the heads are all tied together and you have to go together is because heads。

 are really expensive， complicated technology and it's a commodity device and so you can't。

 afford to have independent heads。 So we said there was a model of performance here， seek time。

 which is the time to move， the head to the right cylinder rotational latency。

 which is the time to get the right， sector underneath and then transfer time。

 which is the time to transfer the blocks off。 And so a total model for disk latency is that it has that seek time plus rotation time plus。

 transfer time， but it also has some other elements like queuing delay， which we'll talk。

 about today and hardware controller time， which you can imagine that's just the time for the。

 controller to tell the disk what to do。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_3.png)

 Okay。 So we're and we also talked about kind of typical numbers。 So for instance。

 if you look at a seagate 18 terabyte disk that's over one terabit per， square inch。

 four to six milliseconds seek time and then the various rotational latencies。

 you're going to see on a commodity product are somewhere between 3，600 RPM to 7，200 RPM。

 but servers can go up to 15 or even 20，000 RPM。 Okay。

 So were there any questions about disks before I move on？ So if you think about it。

 the model there of moving the disk head into the right track。

 and then rotating and then finding the data means that there's a significant advantage。

 using locality to our advantage when we're starting to build file systems。

 And so we're going to talk about that a little bit today and definitely next time。



![](img/e7e8fedabeca3779235890b7a1e5c0fd_5.png)

 Okay。 We also talked about SSDs that are made out of flash memory。

 And I wanted to put this slide up， which I didn't last time to give you another idea。

 of how flash works。 So this is silicon， dope silicon。

 you probably all seen that in one of your 16 level classes。 Normally。

 there's a single gate on top and a control line and you get a transistor。

 When there's a high voltage， the current flows and when there isn't， it doesn't。

 What you get with flash is you actually put two gates on there with insulator in between， them。

 And so that floating gate you see right here， oops， wait a minute， that you see right。

 Don't do them。 The transistor in the middle is insulated from both sides。

 So you can either store a bunch of electrons on it or not。 And if you store electrons。

 it changes the properties of the transistor enough that you， can detect it。 Okay。 All right。

 And the reason things wear out with flash is because basically those electrons get stuck。

 every now and then embedded in the insulation。 And so eventually when you get enough of those in there。

 then it just doesn't work properly， anymore。 Okay。 And so the summary of SSD。

 which is kind of where we were at last time， was really that。

 the pros are really low latency and high throughput。 There's no moving parts。

 which is a big advantage for reliability。 And you can read things essentially at memory speed。

 The cons used to be that the storage of these devices was much smaller than hard drives and。

 much more expensive， except that none of that's true anymore。

 And I should remember I showed you that you could easily get a 15 terabyte SSD no problem。

 Now the it's a little more expensive， but it's not a problem from getting to space。

 Some other interesting problems that show up and we're not going to have a lot of time。

 in this class to discuss the file systems for flash that are unique from disk。

 But there is this weird notion that you have to erase a whole group of blocks at a time。

 And so there's a lot more management that has to be done down in the controller of the。

 SSD to make that work well。 Okay。 And also the SSD has to realize that things wear out。

 So but things are changing rapidly。 And as an amusing thing， last time。

 remember I showed you that 100 terabyte disk that was， a， you can put into a regular computer。

 Now of course it was $40，000。 Really worth more than several computers， but you know。

 you do this in the cloud perhaps。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_7.png)

 Okay。 The last thing I wanted to mention is if you have any interest in persistent memory， it's。

 always kind of fun to see what's coming up。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_9.png)

 Right。 So for instance， when flash originally showed up， it had several different ways of using， it。

 some of which were just like a memory card。 Others of which went into the SSD and had controllers and everything。



![](img/e7e8fedabeca3779235890b7a1e5c0fd_11.png)

 Similarly， there's a bunch of persistent memory technologies。

 This is one of my favorite ones that doesn't quite exist yet， which is made out of nanotube， memory。

 which and has a cross hash pattern and it's three dimensional for storing bits。

 And the difference between a one and a zero is kind of whether all of the nanotubes are。

 aligned or not。 And you can detect that difference with a resistance。

 And the cool thing about nanotube memory is it doesn't wear out。 Okay。

 And it's also potentially as fast as DRAM。 So and SSD is not that fast。 So someday。

 there's a whole slew of possible technologies out there。

 And it may be the fact that when we teach this class in five years or whatever， it'll。

 be all about the fact that the memory is persistent。 There is no disk。

 And the problem is when you reboot， it's got everything it had before。

 So rebooting no longer is a good way to get rid of bugs。 Right。 So that's on the horizon。

 That's not that far off。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_13.png)

 Okay。 All right。 So let's change gears now。 Let's talk about ways of measuring performance before we get into the file systems themselves。

 Okay。 And so you can measure things like times and rates。 You can measure latency。

 which is the time to complete a task。 That's easy。 Like if I wanted to get a block off the disk。

 how long would it take？ And that's measured in second units， right？ Seconds， milliseconds。

 microseconds， hours， years。 The other thing， which is possibly similar is response time。

 which is the time to initiate， an operation and get its response back。

 which can be different from latency if you're thinking， about things like overhead and so on。

 And then on a different fashion， is things like throughput and bandwidth， so how many。

 accesses could I do per unit time or how much， how many bytes per second can I get？

 And then there's the overhead， which is the time to actually start an operation。

 So typically you go to send the controller a request。 There's some fixed amount of time。

 probably in microseconds or milliseconds that needs， to lapse before the disk even gets the request。

 And that's going to be pure overhead。 Okay。 So most IO operations are roughly linear like this。

 This is a very simple model that often works， which is the latency as a function of the。

 number of bits。 Remember little B is bits。 Is the overhead plus the bits divided by the transfer capacity。

 which is sort of how， many bits per second you can get。 Okay。 Very simple model。

 which we're going to show you something about in a moment。

 This is ultimately what people care about， but what does it really mean？ Okay。 By the way。

 the question here is why is this P bytes that's a type of order。

 So what does it actually mean here to have performance？ Does it mean faster？

 Does it mean lower latency？ Does it mean higher throughput？ So whenever somebody says。

 does this have higher performance？ Your question ought to be， what do you mean？

 That ought to be your first question if somebody says it performs more。 Okay。

 Because you got to even know what you're measuring。 All right。 Now， here's an example here。

 So suppose we have a link that's a gigabit per second。

 That's a pretty standard ethernet link these days in low end places。

 And that actually means that our， we can get 125 megabytes per second。 Okay。 Out of that link。

 I just took one gigabit and divided by eight。 All right。 And the startup cost， let's say。

 is a millisecond just for the sake of argument。 And so we can build something that looks like this。

 which is the length in bits on the bottom， that we want to transfer in a packet。

 and then we can have latency in blue and bandwidth， in red。

 So I'm putting two different scales on the same graph。 I hope you don't mind that too much。

 But what can we learn here？ Well， latency here has that startup cost plus the number of bits divided by this maximum。

 rate。 Okay。 And you're going to have to normalize so that if you're using with bits， you deal with。

 bits or bytes， you deal with bytes。 But this S plus B over B is the thing that looks like a straight line。

 right？ Because it's linear in B。 So that's our blue。 And notice that it to transfer no bits。

 there's still a millisecond。 That's why the intercept here is at a millisecond or a thousand microseconds。

 which by the way， since my last Tuesday lecture， you guys are all that all these units figured out now。

 right？ Yeah。 So we're dealing with powers of 10 or powers of two here。 Powers of 10， right？

 Because we're dealing with bandwidth。 Okay。 So the effective bandwidth for transmitting so many bits is B over S plus B over B。

 So that's the total number of bits I transfer divided by the latency。

 And that gives me bits per second。 Okay。 And that's this red curve。

 So notice that even though in the best case， I can get 125 megabytes per second， it takes。

 a very large packet to overcome that overhead and get that full bandwidth。 Okay。 Questions。

 Does that make sense？ All right。 So now we can talk about this key dotted line。

 which is the half power point。 And that's or the half point。

 And that's typically why it's not advancing。 There it is。 This is the number。

 the value of B for which I have half of my bandwidth。 Okay。 And so usually the half power point。

 that's what this dotted line is， is an interesting。

 one because it means you're kind of not overwhelmed by the startup overhead。

 It's kind of you're kind of getting along to getting real raw overhead。 So a link， by the way。

 the question is what was a link in here？ We're talking about a network。

 So a link is a an ethernet cable or something that's transmitting。 Okay。 So for this example。

 the half power bandwidth occurs when B is 125 kilobytes。 Okay。 So B， by the way。

 in answer to that previous question is actually a variable。 And we're looking at the units here。

 This is kilobytes in this case。 So where does that come from？

 We find out the point at which the value of B， which gives us the half full bandwidth。

 half of the bandwidth， and that's 125 kilobytes。 Now what's interesting about this for me is if we make the overhead much larger like for。

 a disk， what's suppose it's 10 milliseconds， then the same kind of idea， the half power。

 bandwidth now is for a packet that's 1。25 megabytes in size。

 Before our half power point here was 125 kilobytes。

 That says that until you when you transmit a packet that's 125 kilobytes in size， you're。

 going to get at least half of your bandwidth in use。

 Here that 10 millisecond startup cost says that if we don't get 1。2 megabytes as a packet， size。

 we don't get half of our full bandwidth。 Okay。 So when the overhead gets high。

 you've got to figure out ways of getting rid of the overhead。

 Either by making things arbitrarily large， which isn't always practical， or by， for instance。

 in the case of disk， you make sure you don't seek very much and that will reduce the overhead。 Okay。

 Questions？ Yeah。 So， I'm sorry I said this incorrectly earlier。 The lowercase b is the amount。

 is a variable， it's the amount you're transmitting。 And I'm showing it in bits down here。 Okay。

 And this is the capital B because this is a constant。 This is， this is bytes capital B。

 So here again， this little b is a constant。 So what I really ought to do with these slides is I ought to get rid of the small b that's。

 in the equation in bullet x。 Maybe that makes things less confusing。 Okay。 I'll do that。 All right。

 All right。 Now， so what determines the peak bandwidth？ So remember the peak bandwidth is this。

 this point that you would finally reach with an， arbitrarily large packet。

 You'd hit the peak bandwidth and that's the guaranteed not to exceed bandwidth。 Okay。

 So a one gigabit network link， the guaranteed not to exceed bandwidth is a gigabit， right？

 But what determines that？ Well， in the case of ethernet， it's the protocol。

 If it's a gigabit ethernet， you're not going to get better than a gigabit out of it。

 But there's lots of things in systems that set that high point。 So in case of buses， you know。

 you can look at this like PCIX is a very old bus。 That's a， you know， a gigabyte per second。

 let's say， thunderbolt is another one that， a lot of you have on Intel machines。

 which gets you 40 gigabits per second。 So varies widely。

 So when you're sort of trying to figure out， am I going to get my full bandwidth， you have。

 to start by figuring out what is the thing that's the bottleneck bandwidth here。

 And so the device transfer bandwidth is another thing that could be setting a bottleneck。

 So for instance， the rotational speed of the disk， if the disk is spins twice as fast， you're。

 going to get twice the transfer rate off of that disk because the bits are going under。

 the head twice as fast。 Okay。 And that's why high performance systems have 15，000 or 20。

000 RPM disks in them。 Okay。 Whatever is the bottleneck in the path tends to be the peak bandwidth。

 Yes。 No， if we increase the disk speed， you mean how fast it's spinning？ That's going to。

 it's going to do a couple of things。 Okay。 It's going to not only decrease the overhead of rotating to find your sector。

 So that's going to go down。 That's overhead。 But the other thing is when you're reading off the disk。

 the bits come off twice as fast。 Okay。 So it's， so the case of spinning the disk faster is actually speeding up a couple of things。

 Now that latency for moving the head in and out， that's a challenge to make faster because。

 that's a physical thing。 I mean， the nice thing about spinning is you spin it up to a certain speed and it stays。

 there essentially。 Okay。 In terms of moving the head around。

 it depends on how fast you can actually accurately move， the head。 And that's。

 that's a harder one to improve。 It's been improving over time。

 It used to be that the access latency was like 15 milliseconds or 20 milliseconds and。

 now we're getting down to four and six。 So it's been improving， but it's not improving rapidly。

 Okay。 So that's kind of pure overhead。 Any other questions？ Yeah。

 So the half power bandwidth is what packet size， in this case it's， but packet size do。

 I send such that I get half of the bandwidth out of my system。 Okay。

 And the problem is that when I go to send a packet or take something off the disk， there's。

 the raw overhead and then I get to get my full bandwidth out of it。

 And so that because of the overhead， you can't just， what you need to do is figure out what。

 is the largest packet that I need so that I get half of my bandwidth out of it。

 That's the half power point。 Okay。 Okay。 All right。 Any other questions？ Now。

 so the question here again， what does it mean exactly to get half the bandwidth？

 It means that this red curve， which you say， here's a packet size， how much bandwidth am， I getting？

 What is the packet size here where the bandwidth I get is half of the maximum？

 That's the half power here。 Okay。 Clear？ And it's really， I mean， this previous slide showed here。

 it's really the effective bandwidth， is having to take into account that overhead。

 So if there was zero overhead and S was one or zero， I mean the effective bandwidth would。

 be exactly a gigabit and there wouldn't be an issue of half power point， but we have， overhead here。

 That's why we have to take that into account。 Okay。 Now， so hire the bandwidth the better。 Yes。

 but you can't always get higher bandwidth， but you'll try to get what you can。

 So let's look at a couple other things in terms of modeling。

 So let's suppose we have some operation a server is going to do and it takes L latency and it。

 always takes exactly L latency。 And we would get something that looks like this， okay。

 where we do the first thing， then， we do the second thing， then we do the third thing。

 They're all equal length in time。 And if that is true， which it's never going to happen by the way。

 but if it were true and， say L was 10 milliseconds， then B which is the big B here script。

 which is the number， of operations we can get per second is 100 because one over 10 milliseconds is 100 ops。

 per second。 Okay。 And that's just the inverse of the link。 Now if the length was two years。

 I don't know what this represents， maybe this represents， growing an orchid or something。

 I don't know。 Then the number of orchids you get would be a half of an orchid per year。 Okay。

 One over L。 So this is like the simplest scenario you could possibly have and it never happens this。

 well。 Okay。 But let's just， this is sort of 61C material。 I'm reminding you of this。

 So for instance， and this applies to processors， disk drives， whatever。 Here's a pipeline。

 Suppose you've got your item that takes L but you can divide it into three separate。

 pieces that can be done independent of each other。 Remember that from 61C everybody， right？

 So we could have blue， gray and green be the different pipeline operations to get that， full L。

 right？ So we first do a blue thing， then a gray thing， then a gray thing and we're done。

 And so this would look like this。 Here's the first thing。

 Notice the individual item still took a whole L to do but it was done by doing the first， third。

 the second third， the third third。 And that means if we pipeline it like this。

 that means while we're doing the blue thing， for the next operation。

 we can be doing the green one for the current one or the gray one。

 for the current one and the green one for the previous one。 So we're pipelining。

 That's look familiar to everybody。 So now we can just talk about the rates。 So for instance。

 if L is 10 milliseconds total and there were say four pipeline stages。

 that means that instead of 100 ops per second， we can actually get 400 of them coming through。

 because we've got the pipeline going。 Okay。 And really you could also say that each one of these little things is a quarter of what。

 L is so basically we get four of them for L unit time。 All right。 Okay。 Now。

 so there's lots of systems pipelines。 So the reason we talk about performance a bit with you guys is so that you can start。

 thinking if I've got a system， what are my bottlenecks for bandwidth？ What's the limiting factor？

 What are the overheads， et cetera？ So you can imagine here， for instance。

 you've got a user program that makes a system called。

 it to access the file and then it's got to go through the file system software and then。

 maybe that's got to go through the upper half of the driver and the lower half of the。

 driver and ultimately get to disk。 And so we can look at pipelines where we have kind of one process is making a system call。

 Well， another one's working on the file system。 Well。

 another one's in the upper part of the device driver and another one's in the lower。

 part of the device driver。 So these pipelines kind of show up everywhere。

 not just in processor pipelines like in 61c。 All right。

 So anything with queues behaves roughly pipeline-like。 All right。

 And those queues are going to be a problem for us。

 We're going to have to talk about what's the actual queuing behavior。 Okay。 Now。

 the other thing that you can do， you also heard about this in 61c， is I could have a。

 bunch of L things and if I put a multi-core at them， I could have a bunch of L things。

 happening in parallel。 All right。 And now I can split them up as well。

 So if I have four cores and each thing takes 10 milliseconds， I can also get 400 ops coming。

 out for once， but that's because they're now being done in parallel。 Okay。

 You see the difference of pipelining， I split it into pieces and I've got a pipeline going。

 Parallelism， each of them is kept the same and they all go through multiple of them at， once。

 Those are just different ways of structuring systems。 And of course in 61c。

 you saw this as multi-core。 Okay。 So lots of parallelism again。

 where now we can have a bunch of user processes， all submitting。

 syscalls at once and maybe there's a lot of parallelism in the file system and the drivers。

 and there's multiple disks。 So we could have multiple things happening at once going through the system。

 Okay。 So， could anybody tell me that if we wanted to exploit parallelism like this， what we're。

 likely to run into？ Can anybody come up with what are the biggest issues that might show up here？

 Synchronization problem。 Great。 Yes。 Okay。 Because if there's one file system and lots of people are accessing it。

 you could imagine， you don't know anything about file systems quite yet。

 but you could imagine that they're， all using shared data structures and if we don't have good synchronization。

 it gets， all screwed up。 So parallelism， just like when we talked about thread level parallelism earlier in the term。

 in the IO system， we're going to have to make sure our parallelism doesn't get in the way。

 of correctness。 Okay。 This is like this class， you never lose the stuff we teach you early on。

 you just have， to apply it to different topics。 Okay。 So。

 let's go back to sort of a model of IO for a moment。

 And here's a thread from a user and it is going to make generically some sort of IO， request。

 I'm going to forget about file systems and stuff for a moment， say it's accessing the， disk。

 So what happens is that request gets put into a queue。 Okay。

 It could be a queue in front of the controller。 It could be a queue in the operating system or in the device driver。

 And then there's a controller that pulls things off the queue and sends them off to the IO， device。

 Okay。 And so the response time is going to typically be a queue time plus an IO device service time。

 And so this is important。 That green thing is in the main path to getting your satisfied response。

 right？ Because your request has to work all the way through the queue and then through the controller。

 and get back。 So you could imagine that if the queue was completely full that this controller could。

 be spitting things out really rapidly， but when you put your request in there， it still。

 got to drain the queue down so you're in the front and then get to be processed。 Okay。

 So a large queue translates into long latency。 Okay。 This is the McDonald's analogy， right？

 You really want that McFlurry or whatever it is you're going after。 You go into the McDonald's。

 there's a huge line and you got to wait through the line before。

 you can even get to the counter to get served。 Okay。 And so that queue， believe it or not。

 has a lot more importance to latency than is usually， recommended。

 So when we're looking at the performance of an IO system， you know， we have our metrics。

 like response time and throughput。 We can start talking about effective bandwidth here where we have the number of operations。

 we're trying to do。 There might be some overhead and then there's something which is the time per operation。

 That looks exactly like that simple model I gave you earlier， right？ Because it's pretty universal。

 it shows up all over the place。 What's going to be different about this is we're going to start having to address things。

 that look like this。 Okay。 This is kind of got a linearity to it or it's a slight concavity downward。

 This is something else entirely。 Okay。 And notice how I've labeled it at the bottom， 0% to 100%。

 What this represents is the full utilization of the device。

 So 100% utilization means the devices go on all the time。 It's completely busy。 0% means it's idle。

 We have an overhead， but notice this behavior where as you get closer and closer to 100% of。

 the capacity， the latency goes greater and greater。

 And there will be many things you encounter in your career at Berkeley that all have that。

 response behavior。 Okay。 And you need today， we're going to talk about where some of that comes from。

 but also you， need to be aware that this is a general engineering pattern。

 And there's a couple of things to think about here。

 If you design a bridge and you compute its maximum capacity for handling weight， call， that 100%。

 Do you want to run the bridge at 100% capacity？ No， right。 That sounds very non clever。 Okay。

 And so 100% anything once you've identified your 100% points becomes very important。

 But the other thing that happens with cues is typically because of simple random behavior。

 which we'll talk about in a moment， once you get closer and closer to that 100%， the latency。

 goes higher and higher toward infinity。 Okay。 Now any real system， of course， can't go to infinity。

 but it's going to get arbitrarily， large。 Can anybody guess what was happening in the point where we're kind of growing without。

 bound？ The crew is growing。 Great。 That's exactly right。

 And the cue is growing in a way that's much larger growth for a little tiny bit of change。

 in utilization。 Okay。 And that's generic。 So contributing factors to latency。

 if we think about the user thread， submits a request， and then they get a response back。 Software。

 which is loosely modeled by a cue， the hardware controller， the I/O device service， time。

 It's not easy to get in the way， but cueing behavior is very important。

 And I don't know if any other classes that you've taken have focused on cues。

 We're not going to do a lot of it， but I want to give you some simple ideas about cues just。

 so we can have some back of the envelope kind of ways of talking about performance。 Okay。 Now。

 let's start with something very simple。 So here's a simple deterministic world。

 which unfortunately the world is not deterministic。

 but it's always nice to pretend it is for a few slides。 So what do I mean here？

 So I have a cue in front of a server。 And that server， by the way。

 could be a controller plus a disk。 It could be McDonald's， whatever。

 And so if we imagine that items are arriving exactly every T sub A seconds， exactly， then。

 we know that the server only takes T sub S seconds to serve。 And notice that T sub S is what？

 It's shorter than T sub A。 Significantly shorter。 Okay。 So what's going to happen here？ Well。

 we're going to， the arrival will show up。 It'll get put on the cue。

 but basically get taken off immediately because the cue is empty。 And then we'll serve T sub S。

 And after we're done， the cue is now empty and the whole server sets idle。 Okay。

 So from the standpoint of how busy that server is， it's clearly not 100%。 In fact。

 it's less than half kind of the way I've got this diagram here， right？

 So that server is really idle。 Okay。 And in this particular useful situation。

 we're assuming determinism， so all requests are at， regular intervals。

 There's a fixed time to process。 There's plenty of time in between。

 We can start talking about a service rate， which is how fast is the server serving things。

 It's one over T sub S。 So it takes T sub S time one over it is a service rate。 Okay。

 Just like one over L was our service rate in a couple of previous slides。

 And the arrival rate is how fast are things arriving that's one over T sub A。

 What can you tell me about Lambda versus Mu？ What was that？ Yeah。 Yeah。

 so Lambda one over T sub A is smaller than one over T sub S。 So this seems like a good situation。

 Okay。 And typically when we're talking about utilization， it's Lambda over Mu。

 And the fact that Lambda is less than Mu means we're not at that 100% point and we're okay。

 All is good。 Okay。 Because the rate at which things are coming in is less than the rate at which they can go。

 out。 Now， average rate is a complete world。 So this ideal world we're in， if we go from zero to one。

 that's the 100% point at one， and we offer this low TS over TA。

 what's great is we can serve this immediately。 And so the queue never builds up。

 At most it has an item on there that gets taken off immediately。 So this is great。 Never happens。

 This is great。 However， if you notice this scenario where we try to offer more than 100% load。

 what's， going to happen？ Well， we're going to start saturating。

 And so the device is going to be spitting things out as fast as it can， but where items。

 are coming faster than the device can make it。 And so the queue is going to grow。 Okay。

 So when we're in the mode where TS over TA is greater than one， what happens is we grow。

 Our queue keeps getting longer and longer。 Okay。 So you could maybe say this is。

 you're at that McDonald's， but there's a bunch of tour。

 buses that keeps showing up and dumping people at the door， and they're all going for that。

 McFlurry。 Okay。 Now， at the end of the day when the buses stop going， the queue will drain。

 And we get back to being able to get our ice cream quickly。 Okay。 Now。

 what's the queue wait time look like what's growing unbounded at a rate determined by TS， over TA？

 Let's look at reality。 So reality， nothing's deterministic。 Okay。 I hate to break this to you。

 If you don't know that already， maybe this is a sad day for you， but nothing in the world。

 is deterministic。 Okay。 Even at the quantum level。 So what happens？

 So let's look at a situation where we're going to have the same average rate of arrivals。 Okay。

 So the average rate of arrivals are still going to be one over TA， but we're going to。

 have bunches of them。 So there'll be a bunch of people and then the killed and then a bunch of other people。

 Okay。 That's bursty。 All right。 And this is much better comparison with the bus because the bus shows off。

 but people get， off and the bus leads and other bus shows up。 A bunch of people get off。

 So look what happens here。 So the first item arrives and it's immediately pulled off the queue and it starts serving。

 Okay。 So that so far looks exactly like the previous slide we had。

 Then another one shows up at the next bursty time slot and that's white and now white is。

 going to be sitting in the queue until the blue one is serviced。 Okay。 So this。

 this white rectangle here is unhappy because they're not， they're going to take。

 longer to get their ice cream than they would have expected if there's nobody in line。

 And then orange comes along and orange。 Notice how they're each coming at these little ticks here。

 So orange shows up。 It's in the queue， whites in the queue， in front of it。

 And then gray comes along。 Okay。 And now we're at the end of a burst。

 but notice we've got three items in the queue。 So the queue is no longer empty。

 It's got things in it。 And as soon as blue finishes。

 the great thing is that now white can get in the server and。

 now orange is in the front and gray is next， right？ You guys see what's happening here。

 And then we go down one more and then eventually the powder blue one gets serviced and we're。

 good to go。 And the queue even has a period of time where it's empty。 Okay。

 But we could set this up so that the rate in which they arrive over on average is exactly。

 the same as the deterministic case。 But notice the difference here。

 The difference is that there are some folks in here that are really unhappy。

 Like look at this powder blue guy。 He arrived just a little bit after the dark blue one did。

 But look at all the time they're stuck waiting in the queue。 Okay。

 So queues in a bursty scenario start filling up。 Questions。 Office hours simplify。 Yes。 Very good。

 Today， today I'm presenting a model of office hours。 Yeah， I apologize about that。

 Are there any questions other than how close this is to the office hour situation？

 So the moment we start getting burstiness or non-determinism， then we start having problems。

 And the question is really， how do we model burstiness？

 And there's a mathematical framework that works pretty well。

 Where if you start with the exponential distribution like this， which says the time of the next。

 arrival f of x is lambda e to the minus lambda x。 Okay。 Where the average amount。

 the average arrival rate is one over lambda。 And so lambda is a rate。 This is called memoryless。

 Okay。 And the curve looks like this， where I'm plotting the time between now and the next arrival。

 Okay。 On the x axis。 And this is a probability distribution function because it tells me kind of what's the probability。

 that I'll get somebody that has a， a， a， a， a interval of two。 Okay。

 Does anybody know what the deal with memoryless arrivals are？ Yes。 Perfect。

 So the conditional probability， if I already know I've waited two seconds， what's the probability。

 of the time to keep waiting？ It turns out that if you do conditional probability for those of you that remember that and you。

 rescale the graph， it looks exactly the same。 So this model is a great model for burst buses in Berkeley。

 right？ You're sitting， waiting at the bus stop， and it doesn't matter how long you've waited。

 The distribution of how long you're going to wait is the same when you rescale it。 Okay。

 It's memoryless。 That's what this means。 Okay。 Now。

 the good thing about a memoryless distribution is that it's easy to plug into things and use。

 as a model。 The question you might ask is， is it realistic？ Well。

 it turns out that a lot of physical processes when you combine a bunch of them。

 together tend to have what looks like a memoryless arrival rate that comes out。

 So oftentimes what will happen is if you don't really know what the actual distribution is。

 oftentimes people will say， let's assume it's memoryless， let's compute the， let's compute。

 the rate。 Okay。 Lambda。 And that will be， we'll use a memoryless distribution and we'll plug that into our formulas。

 Now， there's lots of arguments that you can run into and in 70 and 170， they'll talk about。

 this a lot。 You know， is that a fair characterization？ Not always。

 But it is one that people use a lot。 Okay。 So what am I saying？

 I'm saying that if you don't know anything better， you assume that they're all independent。

 of each other and have a memoryless distribution and there's only lambdas， the one parameter。

 you have to find。 Okay。 So what does this mean for this？ So if we had a burst。

 a memoryless bursty behavior， what this really is， is there's some。

 arrivals that are very close to each other and then there's some long tail arrivals。

 So if you look here， there's a lot of short ones and there's some occasional long ones。

 So we could talk about a queue with a memoryless arrival。 Okay。 And there's an average arrival time。

 just like we talked about earlier， which is one over， Lambda。 So lots of short， a few long。 Okay。

 So I will tell you that a lot of folks who are not trying to get a hyper accurate model。

 will think about things in terms of memorylessness。 So we're going to use this moving forward。 Okay。

 So let's quickly remind you of some general random distributions。

 So you all know about if the server spends time t with customers， we could look at the。

 distribution of service times。 So what you think about this is you get to the counter at McDonald's and this is the。

 distribution of how long it takes to get your McFlurry。 Okay。

 And there's an average in the middle and some distribution。 Okay。

 So the mean is the what you get when you sum up the probability or sum up the area under， the curve。

 Okay。 The variance is what you get when you sum up probability times the t minus the mean。 Okay。 So。

 and you're familiar with the square root of variance， which is the standard deviation。

 So this is the way you think about midterms one and two， right？ Where the mean is like 52。

 unfortunately， and the standard deviation was， I don't know， 12 or something， right？

 So the squared coefficient of variance is something you probably haven't seen too often。

 And that is the variance， which is sigma squared divided by the mean squared。

 And what's great about C is C has no units。 So we can come up with some equations for queuing that are unitless。

 And if we know what C is， we can plug them in there and have a good， have a good approximation。

 of what's going on。 So for instance， important values of C here are if C is zero。

 we're back to determinism。 Why is that？ Well， if C is zero。

 the only way that's going to happen is sigma squared is zero， which means。

 there's no standard deviation， which everything takes exactly the same amount of time。

 Or deterministic。 Another one is that this good old memory list thing。

 remember this is how you talk about， buses in Berkeley， C is one。 So typically， when C is one。

 it's often because it's a memory list situation。 And then finally， disk response times。

 there's been a lot of people that have measured how， disks perform。

 and they have a C that's a little bigger than one。 So it's not memory list， and really 1。

5 means that the majority of the seeks are less than， the average。

 Can anybody come up with a reason why the majority of the seeks might be less than average latency？

 Remember， seek is moving that it's an expensive move in the head in and out。 Yeah。 Say that again。

 Okay。 Because a lot of things are on the same。 Yeah。 So the file is good。

 The file systems that try to exploit locality， try to make sure that you don't move the head。

 very much。 So if you do a really good job with your file system。

 then you're going to have more locality， and most of your seeks are going to be less than the average。

 And that's why oftentimes people will talk about C equal 1。5。 Okay。 Now， of course。

 that only works if you build a good file system。 If you don't build a good file system。

 you're not going to get that。 Okay。 Question。 Right。 This is all stuff you know， right？

 So now let's talk a little bit about queuing。 Okay。 So queuing theory is a whole topic。

 Anybody here taking any classes on queuing theory or had queuing theory talked about？ No。 All right。

 We're the first。 I feel privileged。 So queuing theory is a very complicated topic that all sorts of。

 you can take a whole class， on it， but I'm going to give you a very simple model here that works well for some of the。

 things we talk about in this class。 And that model is that we have a queue in front of say a controller and a disk。

 And we're going to look at the whole queuing system， which is what I've got in cyan here。

 is having some arrivals that come in and some departures that go out。

 And if you remember from high school chemistry， remember detailed balance was talked about。

 at one point in chemistry， which is you get to a point where the rate of a reaction happening。

 and the rate of the reaction， unhappening are meeting each other。 And that's the final stage。

 So in queuing theory， you have arrivals are at the same rate as departures on average。

 And in that case， you get a steady state。 All right。

 So the queuing theory we talk about in this class in this lecture is steady state queuing， theory。

 This is not something that deals with transient startup behavior。

 That's a whole much more complicated topic。 Okay。 So when we talk about coming up with a queuing model for something。

 we're talking about steady， state behavior。 All right。 By the way。

 there's a series of books by somebody named Kleinrock。 Great books on queuing theory。

 So if you feel like you want to learn a lot more about it， go for it。 Okay。 But for today。

 we're steady state。 Okay。 And arrivals are characterized by some probability distribution。

 We showed you one earlier that's possible memory list， right？ That's an option。 Okay。

 And departures are characterized by some probabilistic distribution。

 And the trick is what is the latency from the point that your request arrives to when。

 you get your answer and also how long is the queue on average？

 Those are two questions we care about。 Time and queue size。 Okay。

 And so I want to introduce you to Little's Law。 Okay。 This is just a little law。 It's a good one。

 Okay。 Little was his last name。 But the idea is if you have a situation with arrivals coming into some system and departures。

 and the arrivals are coming in at some rate， lambda and in general， there are L items， in the queue。

 then what can you say about this？ Well， in any stable system， as we just said。

 the arrival rate is equal to the departure， rate and the average number of jobs in the system， N。

 I'm sorry， I said earlier that L， was number of jobs。 L is the latency that you wait。

 What you can see here is that the number of jobs N is equal to lambda times L， period。

 So if you know what lambda is and you know the average latency it takes to get through， the system。

 then you know how many jobs are stacking up there。

 And what's interesting about this is this doesn't matter whether you have memoryless。

 arrivals or anything you like。 It works under all circumstances。 Okay。

 so regardless of the structure， bursts variation， instantaneous variations， whatever。

 it all washes out in the average。 Okay， so if you know what lambda is。

 you know what the time to do a request is that you can。

 figure out how many jobs are sitting in the queue。 So this is going to be interesting here。

 So the question， by the way， from the previous， why does memoryless imply C equal one？

 You just have to plug it in。 Okay， because sigma squared over M squared for memoryless is one。 Okay。

 so here's a simple example。 Look， if the latency for us to get through the system is L equal five and there's an item。

 arriving every one second， then it's pretty easy to see that there are five jobs at a。

 time in the system。 Anybody want to disagree with that？ Seems pretty simple， right？

 If they're arriving one a second， it takes you five to get in， then there's on average， five jobs。

 Here's how you think about that。 You go to McDonald's。

 you're getting a lot of free advertising for me today。 I don't even like McDonald's， but anyway。

 you go， you come to the door and you look in， the McDonald's and there's a bunch of people in line in front of you。

 Okay？ And you walk to the counter and by the time you get to the counter， if you turn around。

 and look behind you， there's the same number of people in line。 Okay？

 That's what it means to be steady state。 All right？

 And so that's why this equation works because if you look at the rate that people are coming， in。

 all right， and you look how long you took and you turn around and you look， you know。

 that in that time that you were going through the line， people were coming in at that rate。

 You take the time you were there times the rate that gives you how many people are in， line。 Okay？

 Very simple。 Now， that's little's law。 And here's a very quick sketch。 You ready？ One， two， three。

 put your put your proof sketch hat on。 If you look at a bunch of items。

 each of which takes L time and they're varying all over。

 the place and there's T time that we're looking at the system。

 So we're going to average over capital T。 How do we know what the average number of jobs are in the system？

 Okay？ It's very easy。 We say， well， here is the number of jobs at this one slice of time。

 How do I know that？ There's one， two， three， four of them。

 And what I want is what's the average number of jobs in the system？

 So can anybody think how I do this？ Yeah， very good。 Area。 We compute the area。

 So what we're going to do is make each one of these stripes equal to size one。

 And if we compute the area and divide by the time， we're going to figure out the average。

 number of folks in here。 Okay？ Exactly。 So here we go。

 We're going to say the system area S at any given time is L i times one， okay， which。

 is that height。 Okay？ So L i is the length。 The height is one that gives us the area at that point。

 And so we'll just add up all the areas throughout here。 That's the sum of all areas。

 And then that turns out is just L of one， L two， L three， L four， which are the latencies。

 And so now we take the total area， we divide by T and that gives us the average number。

 of people in the queue。 Good。 And so if you look here。

 the average number of people in the queue is S over T。 We can compute that out。

 That's the sum of all L's over T。 Or if we take the total number of jobs。

 we're going after divided by T。 That's the average number of jobs times the L's divided by N total。

 That's the average latency。 And that gives us the number。

 the average number of people in the queue is equal to， lambda average times length average。 Okay？

 Little's law。 Something to remember， it might actually show up on midterm three。 I suspect it might。

 But it's universal and think of it as this is the McDonald's law。 You look in the door。

 you have a rate of people coming in， you look when you get to the counter， you look back。

 That tells you how many people are in line。 Okay， any questions？ All right。

 So now when you apply it to a queue， what do you got？

 If you know the average time waiting in the queue and you know the average arrival rate。

 you just melt climb together and that gives you the average length of the queue。 So basically。

 this is going to be universally useful for going from the time you've been。

 in the queue to the average length of the queue。 Okay？ All right。 So here we go。

 We'll do all of this and we'll take a brief break。 So here's a。

 here's your little bit of queuing theory that we expect you'll know something， about。 Because one。

 systems in equilibrium， no limit to the queue。 Two。

 the time between successive arrivals is random and memoryless。 So we're going to have a。

 a rival rate， which is memoryless。 Okay？ So the arrival rate is lambda， the service rate。

 which is how long it takes the server， to go can be an arbitrarily complex thing。

 So we're not going to make that memoryless。 And you can think why that might be， right？

 If it's a DRAM， you go to the DRAM， it probably takes a pretty deterministic amount of time。

 to do a read from it。 Okay？ So deterministic service times for servers are not out of the question。

 but the arrival， rates， things are typically coming up in bursts。 Okay？ So here's the parameters。

 So lambda， the service rate T， CER， and C， which is the squared coefficient， those are。

 things that are kind of like independent variables。 And if you know them。

 you can derive a bunch of other things like mu， which is the service， rate is one over T， CER。 Okay？

 That's just the average number of things the server can do per unit time。

 The utilization of the server is just lambda over mu， like we said before， which also comes。

 out to lambda times T， CER。 What do we know？ We know that the utilization's got to be between zero or one or we're in trouble。

 If we're greater than one， we know the queue is going to grow without bound。

 So any stable system always has u less than one。 And so here are our results。

 Now in times past a number of years ago， I used to derive these for you。

 At least the first one is very easy to derive。 I won't subject you to that。 But if you notice here。

 the time in the queue， T， Q， is equal to the service time， the average， service time。

 times u over one minus u。 Okay？ Now the general service time where we have a generalized service here。

 not just memory， lists， looks exactly the same except that there's this one half。

 one plus C factor here。 So notice by the way， if C equals one。

 one plus one is two divided by two is one。 This middle thing factors out if we have C equal one。

 Okay？ So the memory list service distribution is just the special case of the general one。

 And the way we talk about this is an mm1 queue。 It's memory list input memory list output one queue。

 The bottom one is a memory list input general output。 So it could be any distribution one server。

 Okay？ And so if you look， the question is， why does the response delay grow unboundedly even though。

 utilization is less than one？ Well if you notice the closer and closer you get to one with you。

 what happens， we blow， up here。 See that？ So the closer you get to one。

 the more we're getting kind of on this part of the curve。 Now why is that？

 Anybody want a hazard of guess？ Yeah。 So first of all， right。

 we're assuming the queue is of infinite size because otherwise， this math doesn't work out， right？

 Okay， yep。 Why does it go up like this？ Let me show you。

 So in fact actually I'll show you in a second。 Let's take a brief break。 We'll come back。

 I'll show you why it goes up。 All right。 Stand up， shake it out。

 This is a rough lecture because there's a lot of mathematics in it。

 So the question that was on the table was， what's causing this behavior？

 Now you can derive these equations given some reasonable assumptions and you happen to get。

 this u over 1 minus u factor。 So you could say if I were being particularly annoying that。

 well it's just in the math， right？ The math causes it to go like that， end of story。 Okay。

 but that's somehow a little unsatisfying， right？ I mean， I would find a little unsatisfying。

 So let's see if we can do something else。 Okay， so let's see if I can get this to advance again。



![](img/e7e8fedabeca3779235890b7a1e5c0fd_15.png)

 Hello。 Where is this locked up？ Okay， so if we build this where the maximum utilization is at one point here and here is。

 the number， this is the rate at which things are being served on the y-axis， then what we。

 can see is as we raise our request rate， this green curve kind of represents maybe what。

 we get out of the server。 Okay， and there might be a little bit of overhead。

 That would prevent things from going forward。 So that， you know。

 so we know for instance that in this point we can't do anything actually。

 greater than mu max because we're utilization is greater than one that's bad。

 If we look at this queuing that we just came up with， why does the latency blow up？

 Because the queue blows up on every birth。 So the fact that we have a memoryless input says there's randomness on the input that's。

 going to cause burstiness which is going to cause the queue to build up。 Okay。

 and so if you look at it， we really have something latency wise that looks like。

 this and latency is really what matters to us because it's how long do I have to wait。

 from when I submit a request to get the response back。

 And we know that this curve that we're talking about here has proportionality of utilization。

 over one minus utilization and so it's going to blow up as we get closer and closer to this， point。

 Okay， so the half power point here says that we may want to try to find a point in which。

 about half of the systems use so the utilization is about 50% because that'll be a nice medium。

 between keeping things busy and not getting this latency effect。 Okay。

 so that notion we talked about half power point is useful from earlier。

 But let's look at why do we get an unbounded response time。 So here we go。

 Remember that if we have determinism in the arrival， then we can actually lay things out， like this。

 Oops。 And we can use up 100% of our service time because we do the first service and then the。

 second service and the third service and things arrive exactly at the right rate to be used。

 by the disk or whatever。 So there's never any slop here， it's perfect。 Something arrives。

 we process it。 The next thing arrives， we process it。 We effectively keep the queue empty。 Okay。

 now what did I say about generalized processes where a bunch of stuff is arriving？

 It's probably not deterministic。 So let's look at what happens if we add some burstiness here。 Okay。

 so now we have a stochastic or bursty arrival process and now what happens is things。

 arrive in a burst， here they are， did it look， and then they get processed in order by the。

 service and then there might be a gap and then they arrive in a burst and we get some。

 processing and so on。 But notice if we go for the same arrival rate on average we did earlier。

 then if we have， a bunch of bursts， it does mean that we have these blank spots。 Okay。

 in order to make sure the average catches up， but it turns out what happens here is。

 this wasted time never gets reclaimable with bursts。 Okay。

 you burst things grow up and as you're trying to empty things out， there's never。

 a long enough period of time for things to fully empty and that's kind of why we get。

 this curve going up。 So the moment we start adding burstiness。

 it's like we have a bunch of them arrive and， they start getting processed and then there might be a few long ones and then a bunch。

 of them arrive and the net effect is that things just add up。 Okay。

 And that's kind of an intuition of what's happening here。 Okay， so let's give you a little example。

 So let's suppose that the user has a request of 10， 8 kilobyte disk I/Os per second。

 So 10 per second is the request rate。 Suppose that requests and service are exponentially distributed。

 So that means first and foremost that C is one and we use a simpler equation and now。

 assume that the average service time is 20 milliseconds。 Okay。 Now。

 what if we want to ask some questions like what's how utilized is the disk？

 But what we're going to do is we're going to compute the utilization which it turns。

 out is lambda times the service time。 And once we've got that。

 then we can start asking questions like what's the average time， spent in the queue。

 what's the average length of the queue。 And this last one which I think you should look at carefully is interesting is what's。

 the average response time overall for the disk request。

 And what that means is it's the time you spend in the queue plus the time it takes to get。

 your service done， right？ So it's two pieces。 So T system is the queue time plus the service time。

 And so now you can imagine a computation like this showing up somewhere that you might run。

 into in a few weeks。 But for instance， you might say what's lambda lambda is 10 per second。

 Why is that it's 10 I/O per second？ Okay。 What's the service time？

 This is the average time to service a customer 20 milliseconds。 Okay。

 Because it says it's 20 milliseconds。 And that's including a bunch of things like the controller plus C plus rotation plus transfer。

 And you could imagine that the way you got this service time was you did a computation。

 based on other things。 But fortunately for this slide I gave it to you 20 milliseconds， right？

 And 20 milliseconds is how many seconds？ 0。02。 You guys are all very good at that translation now because of that magic slide from last week。

 And so now we could say what's the utilization of the server？ Well， it's lambda times T server。

 which is 10 per second times 0。02 seconds， which is， 0。2。

 So notice that the 1 over seconds and the seconds cancel。 This is very helpful。

 You learned this in high school chemistry as well that you always cancel the units。

 If your units don't cancel， you got a problem。 Okay。 And notice that our utilization is 0。2。

 Is that bigger than 1？ Good。 People are paying attention。 I'm glad。 So no， 0。2 is not bigger than 1。

 So now what's the time in the queue？ Well we use this version of the equation T server times u over 1 minus u because。

 well， that's the memory， the MM1， Q memoryless in memoryless out one server。 Okay。

 And so we just plug it in。 Service time is 20 times 0。2 over 1 minus 0。2。

 That's the queuing equation gives us 20 times 0。25， which says 5 milliseconds。

 What is that 5 milliseconds at 5 milliseconds at the time you spend in the queue？

 Now notice because of the parameters we've got here， that's only a fraction of the total。

 disk service time。 That's good。 It means we're not building our queue up。 Okay。

 If we had different numbers here， such that this utilization got like 0。8 or 0。9， this。

 would be considerably longer time spent in the queue。 Okay。

 And that's the point at which it builds up and you got problems。 But let's finish this example。

 So now if I'm a user and I put a request into this queue， how long till I get my answer？ Well。

 first of all， how long is the queue？ The queue is lambda times TQ。 There's little's law gives us 0。

05 items in the queue on average。 So the queue is really not a function here， right？

 But if we look at the system time total， it's TQ plus T， sir， and it says that when I take。

 queuing into account， rather than it taking 20 milliseconds， it actually takes 25 milliseconds。

 So there's a little extra time in the queue。 All right。

 Now this is an exercise to you guys if you were to try adjusting this so that lambda。

 was faster and so that this 0。2 was closer to 1， you would see this number could go arbitrarily。

 large。 In fact， it could be easy to come up with 100 milliseconds or 200 milliseconds purely because。

 of the queuing time having nothing to do with the fact that the disk always takes 20 milliseconds。

 Okay。 And so the reason I go， I subject you guys to learning a little bit about queuing theory。

 is I want you to realize that the queue can become easily the most significant contributor。

 to latency easily if you're running too close to that 100% utilization point。

 So whenever you're doing a back of the envelope calculation， you might try to figure out what。

 is what is the utilization of one mean in terms of whatever operations per second， how。

 close am I to one？ Okay。 And I would say the best advice you can get out of this class as being engineers in general。

 is you never run anything at 100%。 If you're running anything at 100%， something's going to break。

 Right。 It's much better to run at that half power point or maybe a little bit larger than that。

 but never get close to 100%。 Either in the weight capacity of a bridge， that's a bad idea。

 or the number of requests。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_17.png)

 per unit time you're trying to get out of a system。 Okay。 Now。

 there's a bunch of resources we have on the resources page you can take a look at。

 that have some things from the Hennissian Patterson book and so on。

 And you should definitely assume that back of the envelope queuing theory like we've been。

 talking here is fair game for mid-term three。 Okay。

 But now that we know what the queue could do to us， we can start asking questions about。

 how do we optimize IO performance。 Well， response time is really queue plus other stuff。

 And so how do we improve performance？ Well， we could make everything faster。 Okay。

 I have a little smiley face there， but that's not a bad solution if we let you do that right。

 on the mid-term。 Maybe we don't let you do that。 But always consider if something's a bottleneck。

 what did we talk about scheduling？ Scheduling only matters if there's not enough of something。

 right？ Queuing theory gets in the way when there's not enough of something。

 So always consider maybe making things faster。 The other is maybe more parallel。 Okay。

 If I have a bunch of disks and they're spread out， then maybe I could send requests to all。

 of the disks and now everything is faster by parallelism。 Okay。

 And we're going to actually toward the end of the term， we will be talking about distributed。

 systems and parallelism that you can get out of things that are spread through many servers。

 in the network。 That could be a way of improving queuing time by spreading things out for many queues。

 Okay。 Now， we could optimize the bottleneck to increase the service rate。 Okay。

 So there's maybe we'd get a faster controller or slightly faster device here。

 We could accept the queue and do something else。 We compute a few more digits of pi while we're waiting for a response。

 So there are other things we can do。 But queues are useful。 Okay。

 If the one response to this could be， well， this is a problem that's removed the queue。

 Who needs a queue？ Okay。 But remember， the reason the queue was there in the first place was to absorb bursts because。

 bursts are the real world。 And if you have a queue that can absorb some bursts。

 then the things that are generating， the requests don't have to wait around just to put their thing on the queue。

 So that's why we have a queue。 So queues are very important to smoothing the overall behavior of the system as a whole。

 So you can't really get rid of queues， but you need to know they're there。 All right。 Now。

 and then for finite queues， obviously， you need to do some pushback on people putting。

 stuff on the queue。 So that's admission control。 So when is the disk performance the highest？ Okay。

 Thinking back for a moment。 When there are big sequential reads or there's so much work to do that they can be piggybacked。

 so you can reorder queues。 It's okay to be inefficient if things are mostly idle。

 So if you don't have so many things that your queues are filling up， maybe you're less， efficient。

 It's only when your queues are filling up that it's very important to be extremely efficient。

 at that disk。 Okay。 So bursts are a threat and an opportunity。

 They're a threat because they cause the queue to grow。

 They're an opportunity because they'll let you guarantee there's always something there。

 to you to satisfy and therefore you can keep the system busy。 That could actually be a good thing。

 right？ Because when you're in this， I should say that before we lose this whole thought process。

 When I'm in this point here， where I'm close to 100% utilization and the average latency。

 is really high， what's happening with the disk？ If you just look at it from the standpoint of this queue。

 it looks bad。 But what's happening with the disk？ It's working， right？

 The disk is efficiently doing stuff all the time。 That could actually be a good thing， right？

 If you put in an expensive resource， you want to keep it busy。

 So you've got to be able to go back and forth between the latency of any one request grows。

 without bound。 But the thing was when the queue is full， we know the expensive resource is busy。

 So keep that in mind。 Okay。 So this is why we talk these through with you。

 And so other opportunities， which we'll talk a little bit about toward the end of the term。

 and in the next couple of lectures too， is we could use user level device drivers to make。

 things faster。 We could reduce the impact of I/O delays by doing other useful work。

 These are all about making overhead smaller， doing something else when you have to wait， for things。

 These are all， you know these things because we've been talking about them all term。

 One process goes， or one thread goes to sleep， but another one works。

 And now today you learned about reducing the overhead as well。 Okay。

 So I'm going to pick up with disk scheduling next time。 But let's in conclusion。

 I'll let you guys go， disk performance is really queuing time。

 plus controller and then plus seek plus rotational plus transfer time， those five elements。

 And remember the rotational latency， the time to get to the or sector once you've gotten。

 to the right track is on average half a rotation on average， right？

 And then the transfer time is a disk spec， excuse me。

 We talked about complex interactions with the queue and so for hard disk drives， you've。

 got queuing time plus controller plus seek plus rotation plus transfer。

 SSDs are simpler because you just the controller time plus the transfer time。

 We talked about systems being designed to optimize performance and reliability and bursts。

 and high utilization give you lots of queuing delays。 So we introduced the queuing latency equation。

 And the thing to keep in mind is we gave you two equations， but they're really the same， equation。

 If you look at what we've got here， if you set C to one， this thing collapses down to。

 the MM1 queue。 If you set C to something non one， then this is the MG1 queue。 Okay。

 And so with that， I'm going to say have a great rest of your Tuesday and we'll see you， on Thursday。

 All right。 [ Silence ]。

![](img/e7e8fedabeca3779235890b7a1e5c0fd_19.png)