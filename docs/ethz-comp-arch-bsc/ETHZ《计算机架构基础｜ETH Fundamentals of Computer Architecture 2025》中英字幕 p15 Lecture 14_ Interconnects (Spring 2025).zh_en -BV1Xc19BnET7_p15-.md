# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p15 Lecture 14_ Interconnects (Spring 2025).zh_en -BV1Xc19BnET7_p15-

39 yes， exactly。

![](img/55f4bae1d21abdc895bd40a5ca129290_1.png)

I I like uploaded yesterday and。But they didn't send an acknowledgement again。😊，I hope you did。Yes。

Okay。どして。他。嗯是。はい、これは。我。大丈夫です。It the one name。It。你。efficient it takes for everyone relation have to six to the new space。

そ。嗯。Yeah。Yes what。怎个说话这未来看。Okay， the next sentence。7。うんで一つい。ちょっちっ。less诶 interest our诶。

Is everything good onlineOkay， thisOkay， cool？😊，' slow a cup one minute。剩下你。

All it's just part that I could use screen。看到上。即系我单嘅时候去会。的。等。不是。这个核心。Oh，没し。Okay， that's correct。Yes。

🎼，🎼Yeah。🎼Yes。A few seconds late。Okay， let's get started。This is our last lecture， I think。

There are fewer people I see， although some of the regulars are here， which is good。

I think tomorrow' is a holiday， right？Is that why you have fewer people？Maybe one reason。

 some people are not convinced in the back。Okay， well， we have one more regular coming that's good。

Okay。So we're going to cover interconnects today， there are a lot of things we didn't cover but。Oh哦。

The Zoom is playing tricks as usual。Okay， so basically all good things come to an end。😊。

But usually an end is the start of a new beginning。

That's good that's a good way of thinking about things in general。

 so this is our last lecture in FoOA。😊，As I mentioned before。

 if you would like more such material computer architecture， we have a lot of other resources。😊。

Not many other courses because we cannot teach more than。

Even teaching FoOCA and digital design and computer architecture at the same time strain myself quite a bit。

 let's say I love teaching， but there's a limit to doing what your level also at some point。

 especially if it's as intensive as teaching， let's say but basically I would suggest taking computer architecture。

 this is the advanced course at the master's andD level or the seminar in computer architecture which some of you are taking。

 or doing research in computer architecture。😊，And importantly。

 please fill out the course evaluations， you probably have received a link。

 how many people have already filled it out。😊，Okay some people did that's good please fill it out please tell us the constructive feedback usually good students forget about these things they don't fill it out I would like a more balanced feedback where we get feedback from good students and also people who maybe be struggling in the class it's good to get this white spectrum。

😊，If we get feedback from only four students when we have 50 students in a class that doesn't mean much right if you think about it yeah so please fill it out your constructive feedback much better。

 tell us what you liked。😊，What we should continue doing and what can be improved in the course。

 this is the first time we're teaching this course， this is the first time we're teaching。

A third year course in ET， so it's good to I think。

 understand what you liked and what should be done better perhaps。Does that sound good okay。

 so we look forward to your feedback if you haven't filled it out if you're not here or if you're online。

😊，Please fill it out。Okay， so building on this if you would like to do research this I already said so I'm going to go through this really really fast。

 if you are interested in learning more go to the systolic arrays lecture lecture 9A I were discussed if you're interested in research please contact us basically and there's slides that I copied there's a lot of material we have on research and we've covered some of them。

And we have one more PhD graduate since then。Between lecture9 and lecture 14。Okay。

 and if you're online， you can apply also。Okay now let's jump into interconnection networks。

 which is the last topic， there could be a lot of last topics because there's no Darth of topics let's say in computer architecture to discuss。

 but I chose interconnection networks， I could have easily chosen multiproors cache coherence etc。

 but I think interconnection networks is important because that's a topic we did not cover that much。

 we covered memory， we covered computation。😊，And we covered how to bridge the gap between memory and computation。

But we did not cover communication as much and today we'll cover one lecture on communication although this' is a topic that's clearly much broader than one lecture and we're not going to be able to do justice to it within two hours normally if you take computer architecture。

 the advanced one we cover this for two lectures and two lectures of three hours each so even that's not enough I should say for this topic because it's such an important topic in the end there are some recommended readings ignore the required but these are some some of the works that we have done in the area I'll touch upon them very little we won't have time if you take the advanced course we will touch upon them but some of the other ones also that are also seminal in my opinion and we'll touch upon some of them as well。

😊，Okay， so if you're interested in a longer lecture。

 there's a longer lecture for this and there's another longer lecture for this and there may be other longer lectures in the future。

Does that sound good？Okay so let's start with the basics so why do we need interconnects essentially we want to connect components and communicate between them and this is very fundamental any you can have multiple components processor and memory。

 you have to connect them right communicate between them processor and storage memory and storage。😊。

Essentially， yeah you can see all of some examples over here， caches and caches。

 you want to connect I devices to the processor， all of these require some sort of interconnect。

 some sort of wiring and some sort of way of putting something onto the wire。😊。

Put in very layman's terms that's basically it right Yeah wires and you put stuff in wire so that you can communicate stuff over the wires It may not be wired in many systems today it's wired。

 but it could be also wireless potentially it could be。

It could be also optical etc we're not going to talk about those we're going to talk especially about electrical wiring electrical networks okay so this is one example over here you have a server or some node and then many nodes over here and they're connected through this cloud which an interconnection networks and there may be many switches over here potentially right many routers。

😊，Okay， so this is a picture from one of my favorite papers from Cosmic cubebe from 1985。

 if you're interested， this is a message passing supercomputer that was designed。

At the time at Caltech and they actually looked at a topology called hypercbe as we will see。

 but essentially you could if you look at this picture you have some processors and you want to connect them to storage models and there could be a switching network over here some sort of interconnect we're going to look at the topology of it soon that's one way of connecting things another way of connecting things is basically you have the processor and then storage node is over here so this is a node together with the processor and the storage and then you connect different nodes that contain processor and storage so this is two way of designing systems actually so these are different multi-proster systems if you're interested you can read the paper but in the end you need some sort of interconnection network。

😊，And this paper argues for some message passing multiproors。

 which is similar to what we have seen in Teser Act。

 a while ago if you remember the processing in memory lecture。Okay， so why is this important。

 essentially if you want to have multiple things connected to each other。😊。

How you connect them together affects the scalability of the system。

 right how large of a system can you build？😡，How much bandwidth can you support between the communication of the components what is the cost of the system right we're going to look at the cost of connecting things soon it clearly affects performance and energy efficiency also。

I think I have said this it also affects how easily you can add more processors to the system some networks may not allow that easily as we will see and how fast can processors caches and memory communicate how long are the latencies to memory because interconnect actually goes to memory in fact I'll derail a little bit but it's important therailing。

😊，Sometimes I get feedback from students that you derail a lot in lectures。

 but I think this is important because this is how a lecture lecture convey some of the things that they have learned over the course of the career right in HPCA 2002 which is a major conference in our community。

 there was this really interesting panel， the panel's topic was is it the memory or is it the Interconnect which was ak。

😊，First thing to notice over here is computations up there。

People don't talk about computation right thiss 2002 and I agree with that which one is the bottleneck right is it the memory is it interconnect and this is a very common debate basically memory is a bottleneck as we have seen but interconnect is part of it right as we have seen in the memory lectures memory also consists of a lot of interconnects right internally word lines bit liness those are interconnects and those take time and then you need to communicate from the DM chip to the processor there is interconnect associated with it so basically in my answer to this is theyre really intertwined in the end the bottleneck is really both memory and interconnect and memory enables storage but also enables communication of the data that's stored。

😊，Okay， so that's where that's where we get back into the performance and efficiency how fast can these things communicate how long are the latent how much energy is spent on communication we've seen a lot of examples in the memory lecture where we discuss most of the energy spent on data moment right well data needs to move somewhere it's not just the access of the data but it's also communication of the data。

😊，It also affects reliability and security and all metrics we really care about can you guarantee messages are delivered or you're actually protocol communication protocol actually works correctly if you have a cache coherence protocol you want to keep the things coherent。

 does your network help guarantee the delivery of the messages correct this is important actually I will not talk a whole lot about this。

 but there is a line of work a lot of theory as well as practical empirical proofs to guarantee delivery especially in the presence of faults in networks。

😊，Okay this is there are many parameters and goals network I will not go through all of these if you're interested there are actually courses as well as books this another example that I've shown you over here so you can see examples like message latency message size etc you can look at this and this is a recommended book that I would recommend if you're interested it's all about interconnection networks it's a bit dated now because it doesn't include the latest advances for example in on chip networks for example this was written in 2004 but still。

😊，It has a lot of good information， it has a lot of basics。Okay。

 let me give you a different example than what we're going to talk about if you've taken DDCA which most of you haven't。

 we talk about timing and verification in one of the lectures in DDCA usually lecture five or six。

 and we talk about one of the things that affects timing is how fast when your clock arrives to the sequential circuit。

😡，And this actually happens through a network， there's a clock distribution network that is there to mostly make sure that clock signal arrives uniformly。

 but the problem that is trying to solve is clock signal usually arrives nonunily late to different parts of a chip causing potential timing issues。

 this is actually a copy and paste from one slide from the DDCA and the solution people have figured out is to design to interconnect to equalize the arrival time of the clock signal to all parts of each chip。

😊，This is called clock queue the first one if you are familiar with it。

 how many people are familiar with clockq okay you haven't taken that's okay you don't need to know but basically there's a specialized interconnect that exists in all chips that communicates the clock signal to different parts of a chip because clock signals generated part in some place on the chip and then it needs to travel and if the clock arrives late to some place then basically you're not synchronizing whereabouts clearly right the goal of the clock the whole purpose of the clock is to enable synchronous execution across the entire circuitly if you don't have that if there's sw then you will not you may you may get timing issues。

😊，Okay， so this is one example， this an H type of clock distribution network。

 the clock is coming in from here and that gets distributed so that hopefully you have almost equal clockq everywhere。

😊，Not easy， so people have actually people do research in this area too。

 I think Ive already said all of this over here， but the downside of clock's queue is it increases the sequencing overhead right because you need to wait for the clock to actually arrive and that actually increases your cycle time for example。

😊，So if you have a nice network that your cycle time could be better also reliably。

 this is an example from Alpha 21 to 64， which is a chip that we discussed when we talked about Autoor execution was one of the first Autoward execution commercially successful Autoward execution chips after Pentium Pro。

 but basically this is a paper written by Alpha folks that shows that in the two dimensional chip。

 what is the skew of the clock。😊，What is the latency sw in picoconds。

 So you can see that clocks their eyes to different places at different times。

 and you can see that there's an H。😊，Tre type of a distribution network over here for the clock。

So fund rate by looking at this picture， you can guess what the network may look like also。

 all right， there's some site channel that is provided by the picture。Okay。

 so if you're interested in this there's more on dim and verification。

 which we're not going to talk about， but you can see that's even something as fundamental as distributing the clock we employ networks today and the latency of the network matters。

 topology of the network matters so if you go back to over here this paper covers different types of topologies which I'm not going to get into clearly to solve the problem of clocks queue。

😊，Okay。Now let's start with topology basically， so we're going to cover a lot on topology to begin with。

😡，呃。But basically， there are three things that are important for a network，Okay， where is it going。

 okay？Okay， so basically we're going to talk about topology routing and flow control these three things actually define an interconnection network flow control also includes buffering let's see how much we can cover topology is basically how the network looks like right how is it laid out etc。

😊，So okay， what are the properties of a topology， essentially topology determines how fast you can communicate how long the communication distance between any given node if you're communicating between node A and node B。

😡，How they're connected， the connectivity between those nodes determines， for example。

 how many links that you need to go through to go from one location to another location these are some terminology I eliminate a level of terminology from this lecture normally I actually give a lot of terminology I try to minimize the jargon but there's still some terminology that we want theres a diameter topology is defined by a diameter this is maximum routing distance within the network how far away from each other the most distant components are average distance average number of hops across all valid routes this is usually based on some pattern communication pattern and there's also something that you may see I'm going to downplay a little bit but this is a bisection bandwidth essentially people used to use this to describe network performance especially topology performance you basically cut the topology in health and some the bandwidth of the links that are cut if you do that and this is often that's a bisection basically you have a bisection of the network you cut it into two。

And then the links that you severe， they have some bandwidth to the crossing links。

 and essentially that's the bisection map。😊，This gives some idea of the throughput that you can sustain in the network。

 but I'll take this with a grain of salt because in the end you're executing some application in the network and that application performances what matters。

Okay， anyway， without going into a whole lot of term knowledge let's talk about what these topologies look like。

 there are many， many topologies people have invented and people are still inventing topologies actually。

😡，Bus is the simplest， we're going to see that， and then we're going to see the most expensive one。

 which's is point to point connections， and then we're going to see things in the middle。

that try to approximate things and we're going to see some of the tradeoffs in terms of especially the cost of the network。

 latency of the network in terms of hops or potentially in terms of nanoseconds。

 these are two different things not necessarily the same and then contention in the network contention characteristics。

 but there are many other metrics as well right topology affects your energy topology affects your throughput topology affects your overall system performs and not just topology itself so topologists how the wires are configured right in the network。

😡，Then you actually also have routing， how do you route the messages in the network？😡。

Tology affect that。And then there's also how do you do the buffering and flow control。

 when do you decide what to send to the next node， for example。😡。

That also affects your performance so topology is only part of the equation you really need to know these three things to get a good idea of the network so it becomes complex basically it's not an easy equation in the end that's why bisection bandwidth is essentially useless in my opinion it's just one way of thinking about it okay let's start with the simplest topology basically this's a bus we have eight nodes over here eight nodes are connected to a single physical wire let's say or physical set of wires right。

😡，And clearly， if you want to communicate between node zero to node one， you send a message。

 you need to take over the bus or arbitrate the bus so that you can actually send something on the bus。

Makes sense right if you want to send a message from zero to seven again you arbitrate so that you get the bus。

 let's say there needs to be an arbiter and zero sends the message to seven and then someone else can use the bus basically when two nodes are communicating only those two nodes can use the bus right because a shared medium across everyone all nodes are connected to a single link essentially this is another example over here。

 you have the processor and the cache and then the memory banks on the other side or memory channels and there's a bus over here。

Okay， so the advantage of this is it's very simple as you can see right， you look at it， it's nice。

 it's cost effective for a small number of nodes。😊，It's easy to implement coherence for example。

 we didn't talk a whole lot about coherence， but for example。

 if one cache says one processor says I'm writing to this cash block。

 you can easily broadcast that information on this shared medium and say I'm writing to this cash block does anyone else have that cache block and all of the other caches can snoop the bus basically look at the bus and say oh。

 I have this cache block so let me emate my copy this is one way of implementing coherence。

 this is called snoopy cache coherence and it's very easy to implement if all the processors that you are keeping coherence have a single shared medium like this。

😡，That's the advantage。If they don't share a medium like this， it' is very hard to implement。

 it becomes harder to implement this Snoopy cache coherence as。Okay， if you're interested in cash Co。

 you should take the computer architecture course， we cover different cash Co methods。Okay。

 so the downside of this is it's not scaleal level based if you want to increase the number of nodes to beyond 16。

 let's say even 16 maybe actually a bit。😡，Pushing it depending on the frequency you want to achieve on the bus。

 what happens is you get a lot of electrical loading on the bus and also the arbitration complexity increases。

😊，And as a result， you have reduced frequency on the bus， you cannot sustain a very high frequency。

 but assume that for example， you have1000 nodes hanging off a single bus。

 it's very difficult to do at very high frequencies。😊。

Also there's another problem which is contention because there's a single bus assuming it's not pipeline in some way。

 pipelineing comp but also a comp coherence as well。

 assuming you have a single bus that everyone is hanging off on and everyone is seeing only two of the nodes can communicate with each other at a given point in time right you have a thousand processor。

 they may all want to communicate with each other in some way， but only two are communicate。

 meaning you get very fast saturation。😊，0 and1 may not communicate with each other while four and  five are communicate。

 for example， because they're sharing the same media。😊，So that's the downside of the bus essentially。

 as a result， this is very limited to a small number of nodes。😡，Hopefully this makes sense right。

Okay， this is how a lot of like small scale multiproors are built。

 but this is not scalable as there is all people I looked at many other things。

On the other extreme end， we have point to point connections where every node is connected to every other node。

So from node zero， the same number of nodes I showed you earlier， all of the other seven nodes。

 you have a single link， so this is nice because there is no contention as you can see and I'm going to complete the picture over here。

😊，Every node is connected every other node， that looks nice， right with direct links。😊。

Now the upside is this is lowest contention while node zero is communicating with node4。

 node4 can also be communicating with node two and node3 can be communicating with node7 basically there's a lot of parallelism and concurrency clearly potentially this could be lowest latency because there is no need for let's say。

😊，Arbitration across all of the node， although there is some need for potential arbitration within a node because now we have seven ports going out right or in seven ports coming in。

 this is ideal if it causes no issue right in a sense it eliminates contention eliminates latency issues。

But cost is a bit expensive as you can see it， that's one of the things that's expensive。

 You have order of N connections or ports per node。And also order of n square links。

This is part of the issue， there are other issues with this。

 it's not very scalable because of this reason right essentially if you want scale the 2000 nodes。😊。

First of all， it's going to be very costly second you ran into another problem。

 how do I lay this out？😊，On a chip， right？If you have limited metal layers， let's say。

Thousand0 metal layers is not going to be easy to get these days at least any time soon even with 3D stacking technology that's hard to get basically so in the end this turns out to be not scalable again unless you have a very small number of nodes。

😊，But if you have a small number of nodes， bus is not that bad either。

 so think about that trade off basically。Okay。So crossbar is somewhere in between。

 how many people have seen cross barss before？😊，Not yet okay so you're learning that's good yeah okay so this is somewhere in between that's the beauty of this lecture so you have not taken a network lecture also like higher low networks computer networks maybe okay we're going to see some computer networks concept also but computer networks usually doesn't go into topology as well depending on the course style so this is an interesting course interesting lecture so if you look at here I'm showing you eight nodes over here let's call them processors and eight other nodes over here let's call them banks like cash banks or me banks。

😊，Here we're connecting every node to every other with a shared link for each destination right so node7 is connected to every other node。

 but for each destination destination zero like Bank zero， you have a shared link。😊。

So if node 7 wants to communicate with Bank 7， it can do that while node1 is communicating with Bank0。

 for example， there's a lot of concurrency still， except when the destination is conflicting。

 for example， if node 7 wants to communicate with Bank zero and node zero also wants to communicate with Bank0。

 then they need to be arbitrated with each other so their need for arbitration in that particular case。

When there is a， let's say， common destination。So it enables essentially completely concurrent transfers to non conflictfing destinations。

 so this could also be cost effective for a small number of node it's clearly easier to do and also it's regular as you can see right。

😊，There are multiple ways of building is I don't want to go into a lot of implementation because if we do that then we'll not cover a lot of interesting high level concepts that are important so this is low latency and high throughput i'm going to show you a couple of implementation soon though now the downside is also expensive it's not as expensive as。

😊，The point to point， it's also not scalable because it has this O square cost。

 although it's still a little bit cheaper than and also it's easier to lay out clearly right the layout from the soul it's a little bit cheaper than the point point and it's difficult to arbitrate as and increases over here so as a column with increases it difficult to arbitrate because you're really arbitrating like this is 1000 let's say if this is 1000 processors and this is I don't know100 banks you're arbitrating between 1000 processors again not so scalable。

😡，Okay but this is at the small scale that's actually used in real systems。

 especially core tocache networks and IDBM and a lot of other procedures actually I'll give you a couple of examples。

 so this is one crossbar design where you have some arbitration mechanism there needs to be some arbiter that decides whether which one is connected to which column essentially we don't show that arbiter over here but there needs to be some arbiter。

😊，This is an example from Sun's Usp T2's core to Ca crosspy they have a nice picture over here as you can see。

 so they have eight cores over here and they have eight banks and they have an uncashable unit also and they need to basically arbitrate between so you can see that if you go to bank zero there there is a buffer of two over here theres I think they have yeah too deep to two deep buffer for each requester to hold data transfer request each requester can have two things that are buffer and then there's an arbitration mechanism that decides which one gets the column let's say that link to bank zero。

And there is one of these for every bank。And then there's another backwards。Which is。

Kind of we didn't discuss that， but there if you want to communicate between between here and there。

 you need to have the backwards mechanism also right， which makes sense。Okay。So these are real。

 but there is also actually a pipeline to decide who gets which link。

 there's a four stage pipeline you send a request and then there's some arbitration and then there's a selection and there's a transmission so you can see that this gets complicated actually it takes time to do this。

😊，Even with a crossbar， crossbar is actually not that bad。Okay， and if you look at San Niagara。

 this is old stuff， but well， not Niagara Utrapar T2， which is actually somewhat like Niagara。

 essentially this is the core to core core to cache costpar。😊，So it occupies area two。

 as you can see， right that's a big area on a chip。😊。

And this is in the kind of the old times where they。

They had a lot of processing capability in the course and caches were smaller。Okay。

So there is also a choice that someone needs to make this is actually a choice in general。

 I just want to prime you because we're gonna to talk about buffering and flow control I'm kind of mixing right now how to implement a topology with a buffering and flow control choice but one of the choices that you make in your design is in addition to the topology how do you route how do you actually enable cross- controll do you have buffer flow control do you have buffer or do you not have buffer how does the data flow in the network for example so one way is basically not having buffers that was not true for Sun Niagara they have buffers as you can see right here you can no buffers and you can basically check with an arbitration mechanism if somebody is using the link so there needs to be a sensing mechanism or arbitration mechanism that detects if somebody is using the link。

Or you could have buffers like San Niagara in this case。😊，呃。

You need to determine whether your buffer is full or not full before you send something into your buffer and also there still needs to be an arbitration mechanism out of the buffers right so there needs to be some way of arbitrating and there's an arbit okay we're going to get back to this choice buffering versus not buffering it's going to be actually very interesting。

😡，呃。But think about that for now so if you have offering usually arbitration and scheduling is simpler and you can have efficient support for variable size packets packet is essentially the what you're communicating between source and destination and their sizes may vary right in a processor for example in a cash network a request packet is small it could be one byte potentially or maybe actually if you need the address it's actually eight bytes or so potentially right。

😊，But a data packet that you're receiving from a cash bank is much larger， 64 bytes。😊。

But sometimes you may actually request if it's an uncasable access you may request only8pis right it's good to think about that basically you need actually support for variable size packets and if you have buffer it makes it easier because you can actually cut things into pieces called Fs in network terminology I don't want to add a lot of terminology because there's a lot of jargon in this area but it's called Fits flow control units that's why it's called a fl essentially you can actually buffer fls as opposed to the entire packets okay。

😊，The downside of buffering is， of course， it requires buffers。

 and that's always the downside of buffer。😊，And this is a lot of buffers， if you get rid of buffers。

 you actually simplify things as we will see， hopefully when we get time。😊，Okay， any questions？

All these are interesting， a lot of design choices as you can see。

 okay so people have thought about okay cross bars are actually not bad in terms of contention because you only have contention when you actually have a conflicting destination。

 right？😊，え。Then people have asked， can we get lower cost than a crossbar。

 yet still have low contention compared to the bus？😡。

And people have developed up this idea of multis stageage networks is a very old idea。😡。

And it looks kind of like this essentially these are networks， indirect networks。

 I'm introducing another terminology here indirect means。😊。

D networks means every switch in the network is also a node。😡。

Noe there something that communicates you communicate between nodes inject means there are some switches the network that are not nodes。

 their goal is to just route the packets。😡，They are not actually communicating agents。😡。

Hopefully that makes sense it there's some interactiondirect basically these are the nodes over here and then they send the packets to a network and the whole purpose of this network is just to switch。

😡，The messages such that they get to some other notes okay that's why it's called indirect so there are multiple layers of switches between the notes now the advantage of having something like this。

😊，Is。Your cost and latency become interesting， they reduce rates。😡，In this case， for example。

 we have eight nodes over here， eight nodes over here。😡。

Your cost is not n square anymore and you can see that they are two by two routers。

 two by two switches and they're connected this way。

 different networks that are connected in different ways that have their names which I'm not going to go into it is called an omega network because of the wiring how the wiring is done if you're interested and you can learn more there's butterfly Vens bang and a lot of other networks here the cost is really M loggan。

😊，you can think about it because we're using two by two networks and we have you using eight things over here。

 you need three layers over here， that's the log n part， and then you have n over here。😡。

That's the end look at。And latency is a really log n because you have， again， log base 2 to the8。

 essentially in this case， it's essentially log n， hopefully makes sense because you need log n layers of switches。

😊，Okay， hopefully this is interesting， but again the whole purpose is to reduce the cost over a cross bar you can see that there's much less cost than a cross bar but now the routing is a little bit more difficult and you can get more contention let me give you an example of contention。

😊，In this case， let's say processor seven is trying to communicate something to Bank7。

This is the only way you can route it， right？So you can see there's a restriction over here。And。

At the same time， let's say processor one is trying to communicate with Bank6。

They can see that they conflict， right？So even though the destinations are not the same。😡。

They conflict with each other， and this is the disadvantage over a cross bar， as you can see。

 but the cost is lower， it's not n square anymore， it's N Lo N。😡，Okay。Okay。

 so hopefully that's clear。Okay， so let me introduce some other concepts while we're multistage networks。

 so if you look at multistage networks， these things are cross barss， right？😊。

What you have in each switch is a two by two crossbar， a  two by two crossbar is easy to implement。😡。

8 by eight is much harder to implement that's why we have two by two over here four by four is also harder than two by two as you can see so two by two is actually very nice except if you do two by two then you have more latency your log log base is smaller as you can see。

😊，So essentially a multistage network restricts concurrent transfer and receive payers compared to crossbar。

 we said that already， but it's built baseds on crossBs as you can see。😊。

It's good to think about that。And it's less costly than across barss we've discussed。😊。

So here let me introduce another concept， we're going to get back to this also。

 which is circuit switching and packet switching， you probably if you've taken a computer networks course probably you've seen this because computer networks tend to deal with these high level design choices in general。

So what is circuit switch， so if you have these cross barss。😡，And if you want to， for example。

 communicate between source zero and destination7。What you can do is you can first send some control packets to set up a path。

Were're going to ignore how it's done。 There needs to be some switching to enable that。

 but once the path is set up。This closebar， this link is connected to here。😡。

It's set that way and then this zero transfers to here and this link over here and this crossbar is connected to here and this transfer is that way and this link over here is this this input port is connected to the output port using this link over here so you basically set a path that kind of essentially flows。

😊，The data this way， you set up the maxes and you don't change anything。

Once you set up the maxes or configure the switches in other words， it can transmit the data。😊。

Without buffering， so you basically start streaming the data through this network。😡。

Because you already set up everything and there's no need to buffer anything if you think about it。

 so this is essentially circuit switching， there's no buffer since switching is static once path is set up。

😡，Of course， you need some switching to dynamically set up paths。

 so it's important to think about that right now， so there are some costs associated with it。Okay。

 so that's circuit switching， another way of doing things is packet switching， basically。

 so you don't set up this path。😡，You。Basically decide every time you send something。

 you decide where it should go， this is called packet switching。

 you basically send a piece of a packet， let's say or packet and you decide at this router。

 who goes where。😡，So for a given packet， there is some arbitration that happens。

Every cycle and that packet is routed over here so there's some overhead over here there's some buffing and then in the next cycle that packet arbitrates for this router and that goes over here and the next cycle that goes over here there may be some contention course so every router decides by itself without setting up a path right that's the idea of packet switching。

😊，This requires of course understanding the availability of next router is there enough buffering over here assuming you do buffering in her al etc so these two are actually design choices that are higher level than routing decisions and clearly this different from topology let's discuss this design choice element so in circuit switching you set up a full path between source and destination before transmission and you essentially isolate that path so that no one can use it。

😊，You establish the ro and the send the data as packet switching performs rotting per packet in each router without setting off a path。

😊，So okay， in circuit switching， the key is no one else can use those links that are set up while the circuit is set。

 it's essentially a circuit if you think about it， that's set。😡，Okay， whereas in packet switching。

 you route each packet into individually， possibly via different paths。😡，So for example。

 over here if you。I guess in this case you don't have a whole lot of paths。

 in this particular example， you don't have a whole lot of paths。

 but in some other network like meshes， we will see you may have a lot of path diversity。😊。

So path diversity is， can you take multiple different paths to get to the same destination from the same source？

In this case， you don't have a whole lot of choice。Okay。If a link is free。

 any packet can use it basically， there is no circuit that set up a priori or earlier。

So the big advantage of circuits switching is you get faster arbitration because once you set up the circuit。

 you don't need to dynamically switch the packet anyway， you don't you make the decision only once。😡。

To set up the path and you don't change that decision at all， the circuit is set up。

 you always drop that way。😡，So it's inflexible after that there's no need for buffer because the circuit is set up。

 you can just flow things down as long as you know the latencies。😊。

downownside is setting up and bringing down the path takes time because once you actually are done transmitting data。

 you need to。Bring down the circuits because someone else may use it。

 so that requires a little bit more overhead。😡，Con controll overhead and a big downside another big downside is paths cannot be used by multiple flows concurrent so if you're actually set up the path between okay。

 let me go back over here。If you set up the path between zero and seven over here。😡，诶。

This seven cannot communicate with seven at all until you tear down this path because there's a conflict as we have seen earlier in the picture。

 right？Okay。Okay， packet switching it has advanced than disadvantages also。

 but this is potentially slower because every cycle you need to make a decision in every year out right you don't set up circuits earlier。

 you need to handle contention and this requires potentially buffering as we will see or it could require something else。

😊，But the big advantage is there is no setup or bring down time， that's one big advantage。

 so it doesn't have this a priori setup overhead。😡，And it's more flexible。

 it doesn't underutilize link， so this if the path cannot be used by multiple source concurrently。

 it's not flexible clearly， you need to tear down that path so that someone else can use that。😡，Here。

 at least under utilization of the network， here you don't unreutualize links。😡。

Okay hopefully this makes sense we can think about it more so I introduce this because it' is a little bit different there actually a lot there's actually a lot that goes on in a network we're talking about topology I kind of introduce buffer but I also introduce switching here circuit and packet switching are the choices really independent of topology it's really a higher level protocol on how a message gets sent to his destination so it's another design decision that you need to make for sure but it's something else than topology clearly。

😊，And right some topologies are more amiable to circuit versus packet switching。

 so especially in topologies where you have path diversity。

 circuit switching might be a good idea because you reserve one path for example。

 to communicate let's let's say you're communicating one terabyte of data from node zero to node7。

 destination7。😡，Sorcuit switching is a good thing to do over there because you don't one terabyte of data is broken down into 64 byte packets。

 it'll take a lot of time and energy if you actually individually routed all of those 64 byte packets。

😡，But if you set up a circuit that you basically pump the packets 64 bytes at a time。

D that circuit and you don't need to make any decision or any packet other than the first one that you sent to actually set up the circuit and then you to tear down the connection so if you have streaming data actually it's a very good idea to do circuit switching。

But if you have， let's say， if you're communicating only one packet at a time。

 eight bytes or 64 bytes that then setting up the circuit may not be a good idea。

But also some topologies like where you have path diversity。

 where you can go from one node to another node in multiple different ways。

 circuit switching may be okay because you can take another path if you actually cannot use this path that's actually now currently used by a circuit。

Okay。I will introduce one work Tylerra， this is actually a prototype chip that was built by Tylerra。

 how many people know what Tylerra？It's an old company right now I'm not sure if they exist this is one of the oldest multire companies when multicore was coming out a lot of people were designing different kind of cores and Tylerra was actually had the approach of designing the smallest core possible the core should be as small as possible and parallellyzze your application as much as possible of course it didn't work out for many works because it's very difficult to paralyze your application with very Vimpy cores this is a wimpiest core that you can think of almost but they had a beautiful network to connect those cores and actually they had five different networks to connect those cores and in general what we have in our systems is multiple networks so topology was two dimensional mesh which we're going to see essentially it you can see that this is a mesh network nodes are connected to their immediate neighbors directly so the links are very short。

😊，But that's the basic that's the connected to you you're connected to only your immediate neighbors and if you are lucky。

 you're connected to four neighbors， if you're unlucky， you're connected to two or three neighbors。

 as you can see the edge。😊，Edge nodes are connected to two neighbors over here because they're at the edge and that's the mesh and that's one of the downsides of mesh that we're going to solve with tous later on but basically four of these are packet switch let's talk about the circuit switch first because circuit switch essentially has a it's for streaming data similar to what I discussed if you're streaming data from one core to another core one core to memory controller one memory controller to another ch if you're doing for example direct memory access transfer。

This is very good for that essentially but there are also four packets which networks we're going to see some of these concepts over here but cash request packets have a network for themselves for example response packets have a network for themselves they specialize the network for different types of packets why because cash request packets are essentially control packets right whereas response packets are data packets that are much larger so they actually have different designs IO packets device IO goes through some other network core to core messaging goes through some other network so that these things don't necessarily interfere with each other。

😊，So they made the course wimpy but they made the interconnects much， let's say。

 stronger than the course。😡，Okay， if you're interested actually， they have papers on this topic。

 you can take a look at it。Okay any questions otherwise I'll keep covering some of the multitage networks I will not talk a whole lot of people have developed multi this is actually one of the earliest multistage networks from 1970s it's a beautiful paper from gen Patel genetic Patel is with this student he invented the mei cash coance protocol also since we don't cover cachequeance you can read this paper from 1984 if you're interested it 1984 but this is one network that he designed again it's very similar and the goal is was to replace costly cost bars pro memory in the 1970s people are very concerned about how to connect processors to memory today we actually have the same problem on chip for example or also off chip but on chip for example how do you connect processorors to different cash banks we have the same problem on chip as well as on chip today at the time it was more off chip and the links were actually extremely expensive at the time。

😊，even more so than today and the goal was to replace costly crossbars as the processor memory intricate and this was one of the first proposals as a multistage network over here so a multistage networks are different in terms of how they do the let's say what is the basic building block what kind of a crossbar they have or what kind of a router they have does does each state have different routers of the same routers in this case different routers so a design also becomes different in that case so they are interesting tradeoff。

😊，This is the mega network where all stages are actually the same。😊，呃。

Single path from source of destination， it was used in NYU Ultra computeruter。

 which are a lot of interesting characteristics。Including the Oomega network。

 but one of the characteristics of this network was it could actually do operations on data。😊。

So if you think about， we talked about pressing in memory， this is pressing in the network。

An idea that was implemented in Ultracomputer in the 1980s and they were able to do simple operations and their goal was to reduce the synchronization overhead because they were building huge multiprocesors。

 they were designing essentially parallel programs and one of the issues in parallel programs is how do you distribute tasks how do you synchronize across many processor and synchronization operations are usually happen on a single memory location and you update that memory location in some way。

😊，And they had this idea of combining operations， they combined essentially multiple operations in a shared memory location。

😊，So for example， they could set test and， they could implement test and by doing this in the router itself。

 or they could implement fetch and ad or fetch and or， which is one way of implementing test and。

In their out。Okay， so essentially fetch an ad， what does it do， you fetch a memory location M。

 it goes to the router and you can replace M with m plus I， for example。

 and this gets communicated from the processor to the network and the network does this and the network this way can increment supply different numbers to different processors that are doing different fetch and ads as opposed to every processor fetching。

😊，The data， updating it and writing it back to them。😡，Here。

 all of those operations are concurrently done in the network。😡，Which is interesting again。

 how do you do that， you can read the paper， but essentially this sort of operations are common when parallel processor for example。

 modify shared variable you're for example， distributing tasks across 1000 processors。

 each task gets a chunk of the array the first processor that happens to get M incremented by I。

 let's say because now you get the index0 to I and the next processor gets m plus I and incrementsed M plus2 I。

😊，Makes sense because you're distributing let's say an array equally across processors that's one way of doing that right if you're not doing it equally that then you in it by not by a different eye in this case clearly and that's like dynamic task let's say assignment to different processor but this sort of operations in the network essentially reduces synchronization latency significantly if you're interested again you can read the paper。

😊，Let me cover a couple more of these and then we can take a break。We're running a bit late。

 I get kind of excited about topology， maybe。😊，Okay， so butterfly again。

 there are a lot of these networks and you can see that。😊。

The the switching is a little bit different over here these are all indirect again these are used in real processors also they have different characteristics and in this case for example because of the way things are wired you get three saturation and they actually use randomization of routes because you could actually do multiple different ways of routing but again I will not go into this in detail。

😊，诶。Let me re some of these toppologies I didn't talk about blocking so don't worry about that so we're going to talk about mesh soon mesh is an example of a direct network in this at least this particular mesh not all meshes need to be direct but in this particular case every node has a router associated with it whereas here you can see that crossbar is indirect because there are routers over here that are not associated with a note。

😡，Here also， we have routes that are not associated with a dont， so not every node。

 not every switch is a node as。Okay， so if you look at the cost， we're going to get to mesh soon。

Cros power was O square， we reduce that cost with multistageial logarithmic to on n log N。

 mesh is going to be O。And our links are going to be， let's say nice。

 I mean links here are also nice， but our links are going to be much nicer over here， short links。

Latency on the other end， will be unfortunate with mesh if you think about the latency of a crossbar。

 it's really01， right？😊，You're really going through one link。

Maybe a long link let's order in the order of let's say。

 wego notations01 here or log n because you're going log n links here you're going to go all square root of it。

😊，Okay， maybe this is a good time to stop because we're going to cover some other topologies。

 but let's take a。Break， let's say until。15，13。And then we'll be back and let's see how much we can cover interconects。

No， is there a problem with this？No， I think initially it didn't work， but no it works。嗯。

We gone together yeah， okay， anyway， just。😊，啊冇。我实膏才不到。Did you start？Just check。Okay。

 like is it they can hear me now， okay， hopefully they couldn't hear me earlier。No。

 they couldn't okay， good。When you enter。And the rest remotely。😀呵。嗯。被关。Yeah。China。Okay。

 you can hear me all all good。Okay。Okay， let's get started， so we're still covering apologies。

 I'm going to speed up a little bit because there's a lot to cover over here。😊。

So topologies are interesting because part of it is creativity because there's a lot of topologies you can come up with as humans actually start topology for example we're not going talk about there are a lot of different types of topologies but I'm going to start with another simple one not as simple as the bus but it's a little bit more scalable than the bus which is a ring。

😊，Now this becomes a little bit more interesting we're going to go back to the opposite end again。

 right simple topology ring is a simple topology that looks like this。😊，Essentially。

 this with which P is processor and is memory in this particular case。

 so you can see that every node is connected to。😊，The node next to it right and then eventually the thing loops back over here it's like a ring stop every node is a ringstop right if you think about ring service it's essentially a bus that runss around town and basically it stops at every ring stop right similar concept basically it keeps looping and it stops at every ring stop。

😊，Each node is connected to exactly two other nodes。

 nodes form a continuous pathway such that packets can reach any node。

If you actually didn't have this loop back， then you could still need any node。

 but the problem is your bisection bandwidth width would be lower because if you cut this thing in half over here。

 you would have only one thing crossing， okay？Anyway。

 now you can see what a bisection bandwidth is right， an example。

 so this is cheap O cost as opposed to O square。😊，Compared to crossbar if you remember。

 but it's also high latency it's not01 anymore it's O right the average latency is the half of the nodes basically right it's travel half of the nodes which is really order n。

😊，🎼It's also not easy to scale because bisection bandwidth again remains constant。

 you keep adding notes， you keep adding wing stops right so this is not easy to scale unless you go to you introduce another concept which we will call hierarchy which can be introduced in any topology actually but we're going to be especially looking at hierarchy in rings。

😡，Okay， so this is interesting， so this is actually because of its simplicity。😡。

Simple networks are used in many systems， especially initial early multicourse used rings now rings are a little more complicated today as we will see so there are two types of rings one is well two types of rings in terms of directionality one is unidirectal ring essentially have a single directional pathway you go always from left to right for example right you cannot go from right to left。

😊，And if you have this simple topology and implementation。

 you get reasonable performance if N and perform needs are still moderately low。Because again。

 as you keep adding notes， this doesn't scale very well because your latency increases with ON I've already said a lot of this basically and divide by two average hops latency also depends on utilization。

 but if you look at how you inject into ring this node for example has a two by two router one is you're injecting from this node and the other is coming from this router on the left。

😊，And then you can go either into this node because you're actually communicating or you can go to the other side right it's a two by two crossbar as you can see over here in this case a buffer crossbar。

😊，Okay， so you can see that two by two crossbar is very useful in many cases。

You can build four by four cross from four by crossbars from two by two cross barss also。

Or four by four routers from the two by to routers， okay。

 basically people usually use bi directionional rings。😊，Unless theyre really wire limited， etc。

 usually not the case today， and bidirectional rings provide a multidirectional pathway。

 essentially you can think of it as multiple rings right one ring goes from left to right and another ring goes from right to left that's really multiple rings in my opinion you can do some tricks to save cost of course of multiple rings of it it reduces latency and improve scalability and now it gives you a slightly more more complex injection policy because when you actually are injecting into a ring you're deciding whether you go from left to right or right to left。

😊，And this could be based on a dynamic decision in terms of like congestion properties。

 if you know that information， it could be based on a static decision it could be I based on a randomized decision now this is your routing policy actually。

Now we're kind of getting intoring， we're going to talk about droughting and static dynamic and also randomization。

 although those are concepts that are employed。So Ring's existence systems。

 this is a bidirectional ring in Intel Alder Lake， and you can see the ring agents， et。😊，诶。Now。

 if you want to scale the rings or if you want to scale any topology。

 you can add hierarchy to it so you have a bus。😡，If you want a scale bus。

 you can actually add hierarchical buses right here you have a bus over here and then you have another bus and then you have another bus connecting those buses。

 right？😊，So this gives you more hierarchy we're going to see this concept in rings ring is a little bit more scalable than bus so it makes sense to think about that so these are different hierarchical rings and there could be actually a lot of design choices when you design hierarchy of rings right let's assume that you have a ring of four over here this could also be a bus。

😊，Doesn't matter this is just for demonstration concepts this ring is a local ring and you have four of these local rings and if you want to connect all of these local rings。

😊，Without， let's say increasing the latency that much。

 you can actually have another link that's called a globalrink。😊。

then you can add a ring stop over here， now this becomes an indirect network。😊。

Because these are just ring stops they're not node anymore so and you can actually increase the bandwidth over here for example。

 right because you may actually have higher communication across the rings。😊。

And if you think inside this box， this may actually be， I don't know。

 eight processors that are connected with a bus。So there could be another hierarchy level this doesn't need to be a single node it could be eight nodes that are connected with a bus over here and then you have an arbiter through an indirect network so this is actually cool I think because now this gives you opportunity to scale much better hierarchy enables opportunity to scale this is another way of designing 16 let's say note hierarchical ring as you can see it's more complicated on the global ring。

😊，But there are also multiple connection points this is another way of designing over here we call these blue ones bridge routers there are a lot of bridge route clearlyo this is more expensive。

 but you can see two rings over here two global rings connecting four local rings again。😊。

And this is actually 64 note， and you can see again a design choices look a design choice of higher chlors look like this you have one。

😊，Let's say node that connects four of these rings and then another one connects that connects。

I think。What is this 16 or English as you can see right this really the global one over here。

 this is mid level one。😊，Okay， so this is interesting as you can see。

 and this is actually nice because this enables much more scalability。😊。

It also enables lower latency compared to a ring right think about comparing this to a ring of 16 nodes。

 not so good in terms of latency。😊，It also enables you the opportunity to play tricks， tricks。

 meaning different rings and have different bandwidth right it's going to have let's say why they can be wider for example。

😡，The downside， of course， is more complexity now right。

 and there are a lot of design choices in terms of water around。😡。

Okay so this is interesting and we did a lot of work in this area I like this area quite a bit I don't have time to cover it and we wrote a lot of papers as you can see and some real systems real systems these days don't talk about how what kind of interconnect they implement but this is a paper very cryptic that talks about how they implemented。

😊，The interconnection network in Huawei's let's say I think this their machine learning accelerator right and they actually borrowed the concept of higher clearings one of the particular ones that we designed which is actually from this paper which I will again get to because this paper not just designs higher clearings but it also shows that you can actually make the routing much easier with higher clearings by doing deflection routing as we will see so in general when you design a network you need to really think about topology you need to think about droughting you need to think about buffering you need to think about flow control all of these come as a package and that determine your performance as we will also see。

😊，Okay， so we haven't introduced mesh， let's say for a minute this is mesh。

 well we have introduced mesh， but let me introduce it again and each node is connected to its immediate neighbors。

 that's it。😊，Similar to a ring but now you have four neighbors that you're connected to as opposed to just two neighbors right so this gives you a square as opposed to let's say it this gives you two dimensions as opposed to a single dimension with a ring。

 ignoring hierarchy， you can put hierarchy on top of the sauce circuit。😊。

This cost is again O in this case， an average latency is square root of n。

 so in that sense it's better than a ring as you can see and this also is to lay out on a chip。😊。

Because you can see that it's regular and equal lengthng links that's nice I mean rings are not that difficult play out either but this is also easy and this gives you path diversity rings especially bidirectional rings give you some path diversity but a single ring doesn't give you path diversity right there's only one way to reach or unidirectal ring doesn't give you a path diversity but here you have path diversity to go from this note to this note。

 you can take many different paths as you can see right you can enumerate them for fun。

 you can actually figure out how many paths there this is like I don't know middle school homework。

 something like that figure out how many paths from one note to another you can do that yeah okay basically path diversity path diversity is nice because you can for example。

 the circuit switching on one path you can do packet switching in another path so it can actually utilize these links nicely but now whether whether or not you exploit that path diversity well depends on your routing algorithm。

😊，How do you route？It packet from here to here， which route do you choose？

The best routerought depends on what are the other communicating what is the other communication that's happening between different nodes right and how do you know that information becomes a problem right because when you're routing from here to here。

😡，One way of trying to route in the best way is to avoid congestion rate if this area is congested。

 you route from this area。But how do you know that area is conges？

That's a good question right how do you know local congestion you can detect perhaps more easily。

 but more far away congestion or global congestion is harder to detect and your information may be stale。

Because in the end， there's a distributed system as you can see。

 right it's not you don't have a single bus that tells you you're congested for sure。😊，Okay。

 so it's fun actually think about networks so this is used in many on chip network prototypes it is Tyler actually had a mesh network as I showed you earlier。

😊，One of the problems with rings is， oh， sorry， mehe this。😊。

The corners or edge edge routers or edge notess。😡，They're kind of in trouble， right。

 meaning they have only two places to connect， especially these edges。

 but any edge has at least at most three places to connect。😊。

Now what happens in this case is usually they route toward the middle as a result there's a lot of congestion that happens over here。

 so you run into a lot of congestion because of these edges。

 so touristus elementslamates those edges attention。

Nash is not symmetric on edges so performances and also performance becomes very sensitive to placement of task if you put it on the edge your performance can。

😡，Become bad， let's say， so Taus avoids this problem by making everything symmetric。

 so you can see that now from the edge you connect to the other side。😊，From the edge。

 you connect to the other side， so every node or every router has four other neighbors it's connect。

😡，Sounds good， right？It also reduces the data placement problems。

 so it also gives you higher path diversity again bisection bandwidth is not bad to think about over here so for example。

😡，But if you think about the bisection bandwidth or ring， you cut the network in health in let's say。

 maximum number of connections and you severe  one， two， three，4，5， six， seven。

 eight links over here。Now， if you do that with Taurus。

 you add two more links because two more links actually cross。😡，That path， right？

So path diversity is higher。Of course the higher costs。

 it's also a bit harder to lay out on chip now right things don't look as nice。😡。

As you can see because they are not equal lengths， although you can get creative and start viewing the nodes like this so now you can make things a little bit more equal length。

 this is also a torus on one dimension。😊，They can think of the syllate。So people get creative。

Okay so there other networks we have seen clock trees and an H3 right these are somewhat more specialized potentially but still you can communicate with any node this is a hierarchical topology mesh doesn't have a hierarchy for example right or ring doesn't really have a hierarchy but you now we have a hierarchy right there are some nodes that are at the top let's say this is good for communicating between local node and as you go up higher you need to usually you increase the bandwidth of the links that's why it's called a fat tree basically at the top it's fat。

😊，Over here。This is a real term that's used in interconnection networks if you think about it there's also a cheap Owing cost。

 it's easy to lay out。😊，Roots can become a bottleneck， especially if you have a lot of communication。

 that's why they increase the bandwidth over here you may have a higher frequency communication for example interconnect over here。

 I think this is also good for some computation and communication patterns like if you distribute your computation and your computation is done on this node and then you actually like every node does some addition for example and then you aggregate the results it works nicely with this sort of network but it's a very specialized communication pattern and computation pattern if you think about it。

😊，So。This is an experimental processor connection machine。

 how many people learned about connection machine or know about connection machine。

This old stuff from 1990s but people actually building a lot of parallel machines at the time and this is a factory tree connection machines is actually a very like probably it's ahead of its time it's a parallel processor that had bit serial adders 64000 bit serial adders and their goal was to actually parallelze computation as much as possible in high throughput tasks like scientific tasks and latency didn't matter that much that's why every adder was bit serial and one of the things they also added was really fat tree based network that looked like this and you can see that it's not as simple as what I shown you over here now we can actually have a little bit more。

😊，pathth diversity in this network， as you can see， it had four by two switches。

 packet switch and there was some randomization throughout and it also support a lot of operations combining multicast reduction operations inside the switches over here。

😊。

![](img/55f4bae1d21abdc895bd40a5ca129290_3.png)

Again， if you're interested， you can read more， this is their picture。Over here。

 I'm not going to read this because we don't have time but you can read it on your own if you're interested。



![](img/55f4bae1d21abdc895bd40a5ca129290_5.png)

Okay so we're getting to closer to the end of the topologies hypercuub is one of my favorites。

 you can see this is an n dimensional cube or n cube in other words it is a lot of interesting properties latency is on the order of log n which is nice right so you can actually build very scalable systems and still have log n。

😊，number of links is N log N， Reddix we didn't talk a lot。

 but this is Reddix if you think about Radix is really a number of port that you have out of a note out of a routeer。

😊，If you think about， for example， point to point， radixes O， right order of n。😡。

Whereas here it's order of login， which is much better than order of n so you get a lot of high bandwidth。

 but now your ras becomes a little bit more complicated。😡，Okay。Not just。

So basically what are the benefits latency is low still it becomes hard to lay out in general。

 and I'm going to show you an example soon。😊，So this is one example as you can see with 64 notes this is from the cosmic cube paper again I would recommend if you're interested in reading this they were trying to design message passing based pro actually that's why connectivity was really important for that so ideally with message passing you want point to point communication you pass messages from node X to Y and you want immediately to send that message but they wanted to approximate that point to point communication as much as possible。

😊，Without having O n square complexity， and this is the interconnect that enables all log n。

 let's say complexity bit。So that's good， that's nice。Okay。

 and you can read more from the cosmic Q paper。Okay。

 I'll end with hyper cubee I can come up with more and more topologies。

 there's actually more over here because creativity of people is not limited and people are still coming up with topologies。

 but let's talk about routing any questions on topology。😊，So I thought yes。

 all thoseologies vulnerable towards the manufacturing issues， like if you have， for example。

 one court that you need to turn off because。この city level。

And then like the whole topology doesn't work。Not necessarily。

 I mean you can exploit path diversity for example right if one router。

 I think you're thinking of router not working so you cannot route the messages。

 I didn't talk about fault tolerance， but if you have path diversity in mesh for example。

 then you can actually go through different paths。😊，You just need to identify the fault。

 you just need to make sure that when you're routing， which we're going to talk about。

 you route around that fault， especially， but yes， some different topologies have different tolerance also topology affects your fault tolerance significantly。

😊，No question about that and there's certainly a lot of research in that period too I'm going to mention one thing when we talk about routing。

😊，But again， I will not go into a lot of detail。So your topology needs to be amenable to going through different routes。

 it needs to have path diversity and your routing algorithm also needs to support。😡。

Routing around faults， in addition to detecting faults。Anything else？Okay， let's talk about drafting。

So routing actually is also have a lot of design choices。

 one is the mechanism right how do you determine how to get from node X to node Y。😊。

And there are usually three types of routing mechanism well as arithmetic。

 basically you use simple arimetic to determine how to get from route x to route Y。😊，呃。For example。

 dimension order routing or X Y routing if you have a mesh。😡。

you have some coordinates for the source node and you have another coordinates。

 xY coordinates for the destination node。One way of routing is going through the x dimension first and then y dimension next。

 this called xY routing。Now clearly， you know the， let's say。

 xy parameters of the source and you know the xy parameters of the destination。

 you can subtract the x's from each other and figure out how to go right， which way to go。

So that's clearly every router knows where to send the data by just doing arithmetic calculations right that's it and then once you get to the right y level。

 then you do the routing across the column。😊，So this is called dimension order routing。

 you basically order the different dimensions and then routes， you can do also by X routing。Okay。

 so that's one example， source based routing basically is source specifies output port for each switching route。

😡，Which is essentially you have a source， and you have a destination and you figure out the path somehow。

 and you basically encode that in the message。That you're sending this is actually usually expensive because your message becomes。

Expensive but your switches become simple now。Your switch doesn't need to have a lot of control state。

They just basically strip part of the message and say， oh。

 this is the portion that I want to look at because the message came to me with this portion and this portion specifies which port I should send the message to。

😊，Somebody did the hard work of routing earlier at the source level。

 this requires of course knowing your topology， knowing your patterns， etc。

 which we're not going to get into this a bit harder to do and also it's large header。😡。

So usually this is easy， this is hard， this becomes easy also。

 except it's a little bit expensive in the sense that you have a table lookup that you do for each router。

 for example， you index into a table to decide which output port you go to， right？😊。

This way you can actually decide different paths， it doesn't need to be arithmetic it basically says you can update that table for example if you have a fault。

 you can say because the router on the east is faulty I'm going to route to the south for example and then you can router on the faults you cannot do that with arithmetic routing clearly because even if you have a fault okay maybe you decide okay I'm you going to switch to Yx routing but what if you have two faults now？

😡，Right okay， so basically table lookup page is much flexible and it's easier than source based and it's yeah it can be implemented so if you want to do some sort of like fault tolerance usually you need to go table lookup paste。

😊，But switches are more complex because of tables right now， okay。

 let's talk about something a little bit more interesting maybe routing algorithm。

 I found algorithms a bit more interesting mechanism you can come up with some way。

 especially if you have tables， but routing algorithm usually has three types and all of these types are employed。

😊，Deterministic means you always choose the same path for a communicating source destination pair。诶走。

呃。X Y routing is not just， it doesn't determine only your， let's say， mechanism。

 but it also determines your algorithm。😡，You basically go through the x path first and then go through the y。

 let's say that's deterministic， for example， you always go through the same route right not good for path diversity exploitation。

 of course， not good in that sense。But it's deterministic， it's good for some other things。

 as we will see。Olivious means you choose different paths potentially between a source destination pair without considering network state。

😊，So you basically say， for example， one way of doing this routing。

 which we will see it's called valient algorithm， many people know about Lily valient。😊。

No one yet sounds Turing award winner who invented the like boxynchronous parallel processing model he also did a lot of work on interconnection networks because these are very fundamental to parallel processing clearly basically this algorithm says I want to balance the network load I have a large network I have a lot of path diversity and I want to balance the network load so that every link is utilized equally let's say so what this algorithm does is it basically divide a network into some quadrants let's say it could be even smaller fine grain things and basically chooses one quadrant to route the packet to randomly。

So you could actually go to some other quadrant that takes you far away from the source。

 far away from the destination and then from that quadrant you get routed to the destination and while you're routing from your source to this mid quadrant。

 let's say intermediate quadrant， you may use XY routing for example。

 or you may use some other routing。And while you'reut you're getting routed from the middle quadrant or intermediate quadrant to the destination。

 you may use also X rout， but this balances the network load if you think and you can also keep doing this repeatedly you can randomize where you go although although this is not good for latency clear。

😊，Okay， so adaptive means you can choose different paths。

 adapting to the state of the network when you rot， for example， you look at oh。

 there's some congestion over here， so I'm not going to go that way I'll go this way。😡。

Now this adaptive， this makes routing more complicated， of course。

 but this is actually the highest performance probably depending on the algorithm again， algorithms。

 people keep developing algorithms and network routing this algorithms are also very much dependent on topology clearly because your topology restricts。

😊，What you can route in a ring you don't have a whole lot of choice in hierarchical rings you have a lot of choice now right your adding algorithm actually becomes interesting in a mesh you have a lot of choice in tos you have even more choice etca。

😡，Okay， so how to adapt， you can adapt using local or global feedback。

 meaning how much congestion there is， for example， or whether they're faults。😊。

Another issue is minimal， you always take the minimal path or non minimal path。For example。

 deterministic routing always takes potentially the minimal path right you could design it that way。

 but if you want to adapt now you can actually go farther from your minimal path is basically the minimum number of hops you need to take to get from source of destination。

😊，If you want to adapt， that may not be good。Because you may actually go non minimal to avoid some congestion and in the end this may be good for the overall performance of the system right you may have a little bit longer latency。

 but if you avoid congestion。And you love the interference potential。Okay。

 I think I have said a lot of these so let me go through this quickly the dimension order routing I've introduced this first Traverse dimension X and then Traverse dimension y。

 this was used in supercomputers like K T3D for example。

 many on chip networks were proposed to do this， but there are downsides to this as we discussed。

It's simple that's the upside the other upside is this deadlock fee meaning there is no cycles in resource allocation。

 I will cover this very quickly even though thiss been a topic that's really important for routing。😊。

Now the downside of dimension order routing is it doesn't exploit path diversity。

 and also it could lead to high contention。😡，Essentially related to path diversity thing right so imagine you have a mesh network and you're communicating between this node to this node over here it goes this way right and maybe this node is also communicating with some other node on that path and everybody goes through that right。

😊，But essentially， all those x Y links are congested。😡，And the entire network。

 the remaining part of the network， does nothing。If you think about it。

 you're not exploiting path diversity with this sort of rock， but it does give you that like freedom。

Okay， let's talk about Delock a little bit。This is interesting。

 so we're covering a lot of interesting issues， but we don't have a whole lot of time to cover them in deep deadlock means no forward progress and it usually is caused by circular dependencies on resources。

😊，For example， each packet waits for above or occupied by another packet such that you have a cycle。

😊，And the resource dependencies， for example， if you look over here。

 this packet is waiting for this packet to be routed over here on this link。

It cannot be allocated the buffer because the buffer is full。😊。

This packet that this packet is waiting on is waiting for this packet to be routeed on this link and the buffer is full again。

 this packet is waiting for this packet to be routeed and this packet is waiting for this packet to be routeed and how you have a cycle。

 everybody is waiting for each other in a circular fashion。😊。

You don't want to get into this this happens because you have some problem in your routing algorithm and you don't have you have some circular dependency that your routing algorithm put potentially puts you into and you don't have enough resources to avoid it one way of avoiding this is having enough buffer is that you will never have the circular dependency you will never get to a deadlock Exp way of solving the problem Another way of avoiding this is basically figuring out that this happens and breaking the deadlock。

How do you figure out this happens it's actually a heart problem you find the circular dependency。

 you need to actually have some deadlock detector once you figure it out you need to do something about it。

 what is doing something about it， maybe tell this packet I'm dropping you。😊。

Now that's the decision that you make now you need to send a message to the sender that I dropped your packet。

 so you add a lot of complexity to the system another way of solving this problem is to design a routing algorithm to be dead luck。

😊，whichhich is probably a cleaner way， but now it restricts your choices on what your doubting algorithm is。

😡，Okay， so I think I kind of said a lot of these things。

 you avoid cycles and roing dimension order roing， you cannot build a circular dependency essentially with dimension order roing if you do X y only。

😊，You cannot go by existentially That's the reason you cannot do this circular dependency。

 but clearly。😊，It has an impact on performance and full tolerance。

 so basically the idea is to restrict the turns each packet can take so that you cannot come up with the circular dependence。

I've already said this， avoid deadlock by adding more buffering。

 adding more resource or detect on bake deadlock。Okay， so if you're interested in this。

 there's a beautiful paper in Isca 1992 by glasslas and knee。

Here they introduced this turn model for adaptive routing and here the idea is to analyze directions in which packets can turn in the network and determine the cycles that such turns can form and essentially prohibit just enough turns so that you don't get into this circular dependence。

And again， they designed this for adapter routing， that algorithms are not optimal for performance。

 but they avoid deadlock。Does that sound good？Okay， my solution to that like is don't tell buffers。

Okay， I like that solution actually， but we'll talk about that briefly。

 but then you run to some other problem as we will see， which is also interesting。😊。

Which is called Livelock。If you don't have offers， maybe your packets can be circulating in the network without ever getting out。

So we're going to see that very brief okay let's talk about obli starting I already mentioned this but alienience's algorithm in this paper was developed the balance network load that's their whole goal here it's not to reduce latency it's just theyll set work load so the utilization all the links are similar to each other and I already gave you the idea randomly choose an intermediate destination。

😊，Rut the packet from source to that intermediate destination。

 then route it from there to the actual destination。😡。

And between source intermediate and intermediate， the destination。

 you can use dimension or the routing or some other routing mechanism。😡。

Or it can be obvious at a hierarchical level， right？😊，Okay， so the upside is this randomizes。

 balances network loads so you keep network utilized nicely overall。

 you reduce the congestion basically you reduce the hotspots in the network that's the big benefit of this。

😡，The downside is essentially a non minimal packet latency can increase clearly that's not your optimization goal。

 but you can actually limit when you do this right so usually。😊，A lot of algorithms。Are good？

When if you know when to use them。😡，So this's a very good algorithm in my opinion under high load for example。

 if you are very high load this could actually help you or you can restrict the intermediate node to be closed you can make a progress to it etc so there are actually ways of actually using this algorithm I think in general this is not。

😊，The best algorithm for general purpose use clearly。

 but there are some cases where this actually could be very useful。Okay。

 there's more on these papers if you're interested。

Okay let's talk about adapter routing so adaptive routing actually can be minimal adapter means basically adapt to the conditions of the network rate this could be minimal or nonminim so in the minimal adaptive version router uses the network state for example downstream buffer occupancy that could be an indicator of you look at basically the link that you're trying to send so okay you're going from one source destination there are two minimal paths potentially right if you think about a mesh for example you can go from the x dimension and the y dimension and if the node is over here there are both minimal paths right in the end so in that case there are two minimal paths。

😊，If you go this way that's not a minimal path if you go this way it's not a minimal path right so there are two minimal paths and you can choose one of the minimal paths based on whether the downstream buffer if you if you have information from the next router across each of those links。

 the next router may oh， I'm too busy over here send it and then you can make the decision to send it toward this minimal path right。

😊，So basically that's the idea over here， you pick which productive output port to send a packet to Product output port is a port that gets the packet closer to its destination。

😡，And if you think about a routing algorithm， you define a routing algorithm to be minimal。😡。

Assuming every router。Picks a productive output port。Okay， that's the definition of minimal route。

Non minimum means sometimes you choose non productive output ports。

 yet you're far away from the destination。That's the idea。

This is non minimal adaptive or sometimes it's called fully adaptive。

 I don't like fully because what does that mean non minimal is clearly defined。

 but you basically mis out packets to nonproduct output port based on network state or based on some other information again you could do random。

😊，Does that sound good， this exploits path diversity a lot more， of course， right because？😡。

You may actually have an uncongestive path that's not necessarily reducing the latency to the destination。

Okay， so the first one is aware of local congestion。

 but minimality restricts available link utilizationization load balance and path diversity exploitation here you can achieve better network organizationization and load balance and path diversity exploitation。

 but now the problem over here is，😊，If you're a non minimal adaptive。

 you need to guarantee live life week， how do you guarantee that a packet reaches its destination right？

If all of the routes are actually making a decision。😡，Not all。

 not all need to be basically the routes may be making a decision such that the packets。😡。

Is never reaching its destination because nonproductive output port is a choice that our router has right and the routes are not coordinated with each other in some way so the packet may be circling around in the network and never reaching its destination that's called livelock。

😊，And now we need to prevent livela。Does that make sense？Okay， it's interesting， I think。

So how do you prevent livela is a good question also。

 usually you prevent livela by having an ordering between the packets。

As long as you have some ordering， let's assume that all packets have a global ordering。😡。

And you know， let's assume that they have an age or timestamp。

And the router is always prioritize the lowest timest packet to get its product output port。

And you can prove that。The oldest packet will reach its destination when it becomes oldest to ensure that any packet can become oldest。

 of course at some point， but's that sort of ordering is important。

 but that sort of ordering actually makes her out a very complicated dose。Okay。Okay， route fault。

 so adaptive routing actually can avoid faulty links and routers and route round faults。

 we discussed this idea so I will not go through this quickly。

 I will not go through this in detail again， but deteristic routing cannot handle faulty components。

😊，So you need to change your routing title to disable faulty routes。

 essentially if you actually want to route your own faults。

 assuming that you can detect the faulty Lincoln router。So we actually did some work in this area。

 it's not an easy area to work on， but if you're interested there's more work in this area and we have a nice related work section that talks about this。

😊，Okay。Let's see how much time we have for buffering and flow control。

my phone is making an emergency calls， okay， any questions on routing。

 there's more clearly in routing， but we don't have time。😊。

But now you can see how integrated this could be with topal。No questions。

Okay let me cover buffering and flow control let's see how far we get ahead so we talked about circuit switching we don't have time to talk about that again and we talked about different kind of networks。

😊，We talk about packet switch networks there's actually a lot more to talk about in packet switch networks but packet switching usually you have a packet。

 it has a header which contains routing and control information and payload and some error code there's actually a lot of things that happen in a packet switch network I'll not talk about that but this just give you an idea so you actually have you can detect errors for example you can check some for example to make sure things are transmitted correctly et。

😊，What I will talk about is contention， handling contention is important。

 and this is basically the idea of flow control。😡，How do you decide let's say how do you control different flows that let's say contend with each other at out。

 so my simplest example is you have two packets that are trying to use the same link at the same time。

 what do you do？😡，Assume that both of these packets need to go this way。😡。

That's their product output theport， let's say。One it's coming from the south。

 the other is coming from the north and they both need to go west。So how many choices do you have？

Ber one， right because they're trying to use the same link at the same time。

 buffer one of them and let one of them go。😡，Clearly this has a design choice。

 you need buffers to accommodate this right？The other is drop one。Which you didn't talk about much。

 but you could do this also， this router says， I'm dropping one of the packets。😡。

And I'm going to notify。The sender， which is encoded in the packet that I dropped in the header。

 hopefully I'm going to notify the sender with a packet that I've dropped your。Packet story。

Please resend it。Assuming that packet goes to the centerer。

So you can see dropping actually affects things， you need to make sure that those control packets go back to the sender so that they can resend it。

 but if you drop that packet also，😊，What do you do you can run into this actually snowball effect。

Especially when things are congested， dropping may not be a very good idea。

Think about that a little bit， yeah。Fascinating， I think okay。

 so dropping is actually what Internet does right Internet when it's congested， Internet is。

 of course， another level of interconnection network， whichs a random graph。

 let's say it's not any of those topologies。 it's not on chip clearly and internet， for example。

 there's some congestion control mechanism that detects a route is congested when a route is congested It drops a packet and send a message back at least that's one protocol on internet like TCpiI for example。

 right Okay， but there's another interesting design choice that you can make and you can combine these choices also right and the buffer is will you drop you have some buffering and the number you drop right these are clearly extremes。

 but you can combine these。😊，The last one is misouting， meaning you have contention。

You don't have a buffer， you don't want to drop because dropping has negative effects。

 you basically say I'm not going to send you the way you want to go。

 I'm going to send you through the scenic path， go through some other port that will not take you to your destination closer。

 but eventually hopefully you'll make it。😡，ThereThat's the idea over here。

 so I like this Mr out quite a bit because it doesn't have a disadvantage of dropping right once you drop。

😡，You need to basically communicate that information and there's a lot of latency associated with whereas mis shout。

 if you miss out， maybe this packet goes here and then then the other router goes this way and then entire router goes this way and eventually makes this pack maybe there's some local congestion over here that。

😡，You can route around。 that's the idea over here。 again。

 you can combine this with buffering also when the buffer is full deflect。😡，Okay。

 so there are a lot of tradeoffs over here the big advantage of buffering is you don't basically missrut you basically handle congestion in one way misruting is you don't need eat out any buffers actually that's an extreme that we actually explored and there are actually a lot of interesting things over here。

So there flow control methods， we're not going to go through all of them circuit switching is actually a flow control method。

😡，You circuit switch and that's how you control the flow base。

 because you set up the circuit and the flow happens naturally。You don't need to change the flow。

 right？😡，Whereas if your packets switched， then you have a lot of different flow control methods。

Some of which we will call talk about， but let's talk about circuit switching all it so if you think about circuit switching you pre allocatelocate resources across multiple switches for a given flow right you really have a because you set up the path for this sort of pre allocationlocation you kind of see a global view of the network assuming you do the setup nicely。

 you pre allocatecate all the resources nice。😡，So one of the big events is no be to our buffer as we discussed no contention the flow's performance is isolated。

 you can handle arbitrary message sizes also with one terabytes I gave you that exampleemp right the downside is lowerlink utilization two flows cannot use the same link。

😡，And you have a handshake overhead to set up and tear down a circuit。

So above for lister I'll think actually。It's packet based you don't need a circuit。

 it's also a circuit switching is also bufferless but deflection actually enables things in a nicer way and this' is a very old idea actually it's in this beautiful paper by Paul Brown in 1962 it was initially considered for the internet actually it's called also hot potato oututing as we will see why essentially packets are never buffered in the network when two packets content for the same link one is deflect。

😊，So let's take a look at an example， these two packets， they both have this destination。

 they arrive at this route route at the same time， they both need the south link。And the router says。

I'm going to give the red one。😡，The self link based on some live like freedom policy。

 let's say because the red one may be oldest。And the red one gets to its destination and the blue one goes to a nonproductive path。

 its latency has increased， but later it makes its way to the destination right that's the idea basically you route around。

Let's say congeest if you think about it that way。Okay。

 and you inject new traffic when there's a free output link over here。

Okay so basically I will not go through the router design because we have only 10 minutes and route design will take I don't know well now 10 minutes。

6 minutes router and design will take more than six minutes for sure。

 but basically if you look at a buffer router， it's very complicated today and packets are buffer in pipeline matchesches and network linkss and bufferless routers so you basically eliminate a lot of the input buffers there's also a lot of design choice in the router you buffer the inputs you buffer the outputs you do both input and output buffer there are a lot of tradeoffs which we will not discuss but if you do deflection routing all those buffers are gone。

😊，Which is one big advantage， as we argue before in this paper。

Whi I'm not going to call about in detail， but there are issues in bufferalless startinging also one is livela as we discuss how do you prevent livela。

 this turns out to be not an easy problem。😊，Because deadlock is hard， but livelock is also hard。

How do you ensure that the packets eventually reach their destination and we have some solutions to that I will not talk about again and if you want to actually ensure livela router becomes a little bit more complicated it's not simple anymore because you need to do prioritization of the packet carefully so that you prioritize the right packet so that it reaches the destination every router。

😊，Okay I'm going not talk about it because you don't have time and then there's also one issue with bufferless roing if you actually don't have buffers。

 you cannot inject a lot of loads into the network well meaning your network doesn't have a lot of bandwidth right at high loads meaning if a lot of nodes are injecting into the network and you want to sustain that injection rate a lot of communication let's say performance goes down at high loads so if you want high loads you want buffers for sure no question about that if you don't have a lot of high loads and。

It can reduce buffers。Okay， this is one of our papers which I' will not talked about that proposed this bufferless routing and we actually designed routes to implement this in a nice way。

 if you're interested again， take the course or read the papers and then we figured out that okay。

 sometimes in research it's good to take extreme positions， right？😊，Meaning， okay。

 I'm going to eliminate all the buffer and see where it takes us。But also。

 you realize over time that maybe that's not the best design and you want some sort of buffer。😡。

And that's the idea over here we add some more buffer and over time I think we decided actually some of the topologies are more。

 let's say better with the sort of deflection routing so we designed this deflection routing based highererarch chlors。

😊，And if you're interested， you can read the papers。

And they have a lot of chapters also and actually this sort of deflection routing was implemented in this Huawei processor。

 so they they actually read our paper， they were quite honest they read our paper and they said oh this makes sense and they implemented it and they wrote a paper about it which is very hard to read but you can read it if you're interested。

And they cite this paper。😊，This one that essentially designs the cycle ranges with deflection route。

Okay。Okay， so there's more on bufferless networks， which you can learn about that there's also more on other on networks over here that I don't have time for。

😊，I'm going to skip this one because I want to talk about network performance before we part。

You can see there's buffer flow control， bufferuffford flow control is complex。

 that's why we want to eliminate it。😊，And then also if you want to do buffer Fcon if you have buffers you need to know the availability of the buffer before sending a message right you need to know whether the buffer is available in the downstream route so for that you need some communication bufferless routing eliminates that communication across the routes actually okay anyway let's talk about performance how many of you have seen this curve before this the load latency。

😊，On the X axis， you have load。or amount of load on the network or injection rates into the network。

 it could be specified in different ways one it could be， for example。

 how many packets per cycle every node is injecting in the network on average， let's say。

And on theAC， on the y axis， you have latetnts。So usually the curve is like this， actually do。😡。

Almost always my email latency curve is like this， if I will upload my latencies like this。

 sometimes you get lower latency on on average you get very high latency and I get saturated for example。

 it actually applies to a lot of real life things as well。😊，So if the network has low load。

 the latency is low， if the network has high load， there's a lot of congestion in network。

 there's a lot of buffer， there's a lot of weighting that happens。

 so latencies increase essentially average latency of the packet increase you can also apply plot the maximum latency。

 but the curve looks similar essentially in the end。😊，So if you think about this， latency。

 minimum latency is determined by your topology， this is your connectivity， right？😡。

If you are point to point， you have a link to every single other node。

 that link has some nanoseconds， and that's your latency Act。😡，That's minimum latency。

And that minimum latency， the cure may not be that bad in that case unless you keep injecting yourself。

 right？Okay， so that minimum latency is given by topologyene has another minimum latency clear。😊。

Mesh has another minimum latency clearly and of course this needs to be plotted for a different access pattern like what is your access pattern for a given access pattern there needs to be a curve like that looks like this but okay my point is you have minimum latency given by topology and then you do some routing on top of it that adds some overhead your routing algorithm add some overhead to your minimum latency and then you do some buffering and slow control flow control topology routing flow control actually that leads to your zero load latency this is your real minimum latency all of those design decisions that you make lead to your minimum latency over here injection rate is zero you still have some latency。

zero point， whatever， right。And here we're gonna to look at that also so this is your latency on this side and then there's a throughput on the other side which is injection network injection to the network so you have some throughput and this is actually called the saturation throughput the the injection rate at which latency kind of shoots up right this is the asympote of this curve throughput is given by topology topology give you some upper bound and then you have some routing algorithm dimension order routing doesn't exploit the topology very well so it reduces your throughput significantly for example right and then you have some more inefficiency based on flow control and buffer。

😊，So you're basically asymptoted based on your design decisions in the end and I like this curve nicely。

 so saturation throughput is the injection rate at which the latency asymptotes over here。😊。

So I will not again go into detail because we don't have time but there's ideal latency。

 there's actual latency， you load latency secure looks like this。

 but these are some real examples from different kind of networks。

 so there are different kind of traffic uniform random means different notes communicate with each other at a uniform rate and randomly chose destinations。

 you randomly chose XY pairs and then you have rate injection rate。😊。

If you look at that that's very randomized， it's ob surroundinging does great on this at high loads especially。

 but you can see that different kind of networks have different curverfs。😊。

Okay I will not go in detail and there are actually a lot of interesting analysis over here but it's good to think about that and these are some of the networks where I picked up that things let me finish with this because these were network performance metrics packet latency or onlatency saturation we put you saw that on the curve it's good to analyze the network which is very very interesting clearly but never forget that network is only part of the system performance in this course we talk about the system a lot right network is very interesting if you had time we would talk more about the application level performance execution time impact of the network for example。

😊，With those traffic patterns， you may get some packet latency， but your execution time may be okay。

 right？😡，It's good to think about that where are you operating your applications and what are the traffic patterns like that's really important so it's really important to actually think about application level performance and system performance and it's good to design the network as part of a system as opposed to network alone so in some cases when people design networks they think about the network as network and they actually do a lot of analyses。

😊，And they design the network without thinking about the application。😡。

Now that's not necessarily good， right because you design。

 maybe you over design the network if you do that。Or maybe you under designign the network if you don't take into the application as system requirements。

 okay， I will end here， I could talk a lot about networks clearly， but we're out of time。😊。

But feel free to send us any questions we're done at this point it was good to have you in class and feel free to please provide your feedback you can also provide your feedback by email as well but please definitely provide your feedback through the feedback form and maybe I'll see you in some other class in the future and if you're interested in research again please contact us。

😊，All right， and have a very nice summer vacation， which is going to start tomorrow。

 probably for some of you。Okay。I。Okay。

![](img/55f4bae1d21abdc895bd40a5ca129290_7.png)