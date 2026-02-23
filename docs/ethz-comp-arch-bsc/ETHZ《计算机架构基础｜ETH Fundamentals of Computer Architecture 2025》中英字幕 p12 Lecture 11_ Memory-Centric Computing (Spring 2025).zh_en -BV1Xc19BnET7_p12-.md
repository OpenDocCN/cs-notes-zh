# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p12 Lecture 11_ Memory-Centric Computing (Spring 2025).zh_en -BV1Xc19BnET7_p12-

Yeah sure read different。

![](img/a1e29d1479bd7e3d4792bd1180a361b1_1.png)

And it was a terrible job even terrible job but you thats。ねあ大丈いやいや。

Looking at some of the lecture preciselys。Did's what did。は。Hello here is bitter。

 what should I do here， you don't know。Is it better， is it okay。

 well you don't know if it's better because I didn't try that one much。Okay。然后给你。新不真的。没有。两定两。跟时万年。

点解系や。Yeah。Okay。I still。看问一下。Yeah。系未咩嘅。嗯。ななすごで、すね。く。你想讲。美味しいか場す。Yeah。系呀。OkayOkay。Yeah。

Everybody's so quiet。And the bell didn't even ring yet。Do we hear it from here？Yeah。

It can prefetch and start early。Everything' is good online， okay？🎼Okay。

 now we can get started officially。Okay， this is lecture 11。I think we have only three lectures left。

Am I correct or something like that if you do approximate computing。

 approximately three lectures left。Now， you know why you don't do approximate computing that much because in some cases you want to know exact numbers。

😊，In many cases， in fact。Okay， today we're going to talk about memorycentric computing。

 this is going to be probably the most research oriented lecture。😊，Of this class。

 maybe with the exception of one more， let's see。Although I say this。This wasn't true。

 especially when I was giving these lectures in 2013 or so。

 but today we have memory centric computers。😊，In the sense that you can buy them。

 you can program them， you can put applications on them。You can even abuse the ERM to actually get。

Some computation done。So we're not that researching in the sense that。

Things are moving forward toward this， and I think maybe 10 years later， if we teach this course。

This may be the dominant paradigm let's see that's our goal essentially in research and it's because of the memory problem that we have discussed in this course and that we have looked at processor centric solutions to it。

 if you remember pfetching for example we spent a full lecture on that and you did an assignment on that maybe we'll do a memorycentric computing assignment in this course in the future iterations but not this one but if you take computer architecture you'll see a lot more material like this。

😊，Let's see if I can cover everything in one lecture。

So this is another way of thinking about enabling fundamentally efficient computers basically the problem we're targeting is computing today is vic by data and important workloads are data intensive and they require rapid and efficient processing of large amounts of data and this problem is getting worse because data is increasing you can hear me all right oh I'm okay covering the screen okay I should not cover the screen you need to find a strategic placement of data which is a problem in memorycentric as well as processorcentric computers。

😊，Okay， basically we generate a lot more data we can process and we need to perform more sophisticated analysis on more data people are basically very demanding in terms of what they want to do。

😊，And you've probably see a picture like this many times， I'm not going to harp on it。

 essentially requirements of neural networks， large machine learning models， foundation models， LLMs。

 whatever people call them today is growing in terms of both memory requirements as well as computation requirements as a result people are experimenting with new architectures like these folks from cerebus are looking at wafer scale chips so that they can put huge amounts of memory together with huge amounts of computation except the huge amount of memory they have is 40 or 80 gigabytes it's not that big basically it's very small if you think about it whereas the data requirements are growing a lot。

😊，And there are data generators that are very good clearly machine learning there's a lot of data generated。

 but in genomics a lot of data is generated as well。

 we're going to talk a little bit about the genomics very little in this lecture there's going to be overview lecture as opposed to a lot of detail lecture but I'll go into some detail on some techniques but basically you can have sequencers that looked like this and that can generate a lot of data and people have been using these sequencers to actually sequence a lot of genomes for example during COVID a lot of these were used to sequence many。

 many variants of the COVID genome etc okay basically I could keep going videos another example video cameras everywhere and that generate a lot of data essentially data access a major performance engineic but the way we design our computers so far we looked at in the last 10 lectures essentially waste a lot of energy because processors here memory here and need to move the data between the pro and the memory。

😊，This wastes a lot of energy because of the energy of data moment。

 this also wastes a lot of performance as we have seen and we tried to overcome with multiple different techniques like prefeting right this is interesting because I put this in parentheses normally we don't recognize energy waste。

Most people don't care in general and that's clear in the machine learning model that we do today right but I think people are increasingly interested in the energy because they realize it's also a performance because if you reduce energy you can add more pro but people I recognize the performance loss for decades and decades and what did they do they basically took a procentric approach to fix the problem meaning they added huge autoor execution engines we talk about that right a lot of。

😊，Big caches， many， many levels of cache hierarchies a lot of prefetures at all different levels。

 many levels of multith right we've seen all of these concepts actually so far and that complicatedlic the system a lot。

Now when these things work， they actually provide performance improvements and you've seen that in previous lectures。

 but when they don't work because the locality doesn't exist as much， for example。

 you cannot prefetch very well， a out of order execution has a lot of dependencies you cannot cover those latencies etc。

 then they're actually wasting a lot of energy still and also adding complexity to your system so most of the system is dedi the memory and storage so our systems are very complex most of it is there。

 most of that hardware is there to actually tolerate the memory latency in the end。😡。

And this becomes a vicious cycle， you actually add a lot more hardware to reduce the performance loss。

 but that actually increase your energy waste， so I think we're in this vicious cycle today we're wasting a lot of energy and people talk about sustainability right one of the issues in a sustainability one of the metrics is to reduce the carbon usage and if you actually have a huge processor most of it is dedicated to actually reducing the data moon problem your carbon is really wasted on。

😊，Tolllerating the memory latency。Okay， so hopefully I made a case。

 essentially today computing systems are very procentic， whatever your processor。

 computing unit may be， CPU， GPU， FPGA， pick your favorite ASI。

 you have to access memory to get the data over there and at great system cost you actually do the processing in one place。

😊，And this is my picture it is a picture that I drew in 2008 Xpic when I first through my NSF proposals。

 we were working on quality of service of our memory controllers， et cetera memory systems。

 but the picture kind of remains today at least in a proteorcentric system if you look at this picture。

😊，Course， or if you think about it today， heterogeneous course， accelerries， et cetera。

 are the parts that do computation。😡，This is a single chip if you you can think about SOC also。

 but everything else is there to move and store data caches interconnects， other cache。

 other interconects， memory controllers， other interconnects， memory， other interconnects。😊。

Storage if you do the calculation more than 90%， 95% actually of the hardware real estate of a single node is dedicated to these things that don't compute。

😡，It's amazing。So I like taking the perspective of a blank slate。

You have this picture and you have a 10 year old kit。

As the 10 year old kids and they will respond honestly。

 a lot of people who are invested in it may not respond honestly。

 but the 10 year old kid without any investment would respond honestly。

 give them this picture say I'm dedicating almost all my resources and energy to storing and moving data。

 this should not be a problem right。They will tell you， are you kidding？

This should not be a problem of course， right， but this is our problem today。😊。

So maybe the 10 year old kid would be honest and say。Scrarap this， do something better。Okay。

 so we're going to be like 10 year old kids。In this lecture。

 and I think we need to be like that going forward， otherwise。😡。

This problem will get compounded and compound and compounded and people will start keep complaining about how badly we're wasting energy etc cetera。

 carbon carbon and this will continue forever so I have to take a different approach okay let me give you that was kind of the hardware resource perspective right let me give you some data now this is the data I can give giving a lot of data but for the sake of a short lecture we're going to focus on some data points this is a paper I like it's 2015 Google published this beautiful paper where they analyzed the micro architectitectural characteristics of their workloads according to them all of their data center workloads。

😊，And they basically said that most of the time， on a cuttingage processor。

 these workloads are waiting for data to come back from the memory。😡。

These workloads are doing or the processor is doing what it's supposed to do。

 meaning finish instructions。😡，Only 10 to 20% of the time now again。

 let's take the hat of a 10 year old kid。Say I designed this processor。

 my goal is to finish instructions as much as possible。😡。

This process is doing what it's supposed to be doing only 10 to 20% of the time。

 am I doing a good job？😡，The kid will be honest with the N。Scrpt this， right？



![](img/a1e29d1479bd7e3d4792bd1180a361b1_3.png)

That's the idea of each。Okay， so that's performance， energy is much worse。😡。

If you think about energy， this is again some data， there is a lot of data over here。

 I'm going to give you more data on energy actually soon， but this is data from NVDdia 10 years ago。

 you can argue with all of these numbers but the trends remain the same essentially a complicated double precision floating point to athmetic operation is 20 pickcoules。

😊，And at the I me or right to 16 nanos this number went down， it's about one to two nanojoules。

 you can actually bring it down a little bit more， but still there's a huge discrepancy as you can see right according to these numbers。

 a memory axis consumes two to three orders of magnitude at the energy of a complexity and this actually is success of technology scale。

😡，Because we were able to scale the transistor sizes and energy very well。

 computation became not a problem in terms of energy。

 but interconnects and the memory technology did not scale as well as a result。

 you get these high energies。😡，That yes。Okay so that was complicated。

 let's talk about simpler arimetic operations because people want simpler today and for a good reason because they want to reduce energy if you go to simple。

 let's say 32 bits integer addition， then the discrepancy assuming the same numbers is 6400 x so you basically consume 6400 x more energy accessing memory now asking the question is important do I want to move two elements of data to do a binary operation to do operation on two values into the processor and then do the simple operation in terms of energy and right back the data once more I'm consuming three times 6400 x if I do that。

😊。

![](img/a1e29d1479bd7e3d4792bd1180a361b1_5.png)

And you can do the calculation an optimization problem in the end right how many times should I reuse this data so that I can overcome this energy differential now your reuse numbers need to be crazy on the order of thousands and in some cases you can get that when you get that maybe you can make up for the energy differential。

 when you don't get that which is many， many workloads and large data sets。

 then you cannot make up for the energy differential。😡，And again。

 we're talking about simpler artrimetic operations if you make this even simpler the differential actually increases if you make the arithmetic operation。

 let's say two bits， four bits， one bit， if you're possible。

 people are talking about1 bit LLMs if you can do that because they're wasting a lot of energy right this reduces the data moment cost no question about that。

 but this also reduces the computation cost and it reduces computation cost much more than it reduces data moment cost。

😡，Let's say divided by 32， computation cost divided by 32， but be moment cost doesn't divide by 32。😡。

Hopefully that makes unless you pack your data extremely intelligent and be very careful， et cetera。

Okay， let's go to these exercise basically。😊，Okay let's talk about some real numbers that we measure on asimild as well as real devices。

 we work with Google to understand the energy consumption of real workloads that are used by real people。

 let's say in this paper we show that on average use cases on a mobile system。

 more than 60% of the total system energy is spent on data movement in a procentric system。

 and this is average case。😊，That's not the worst case usage basically and the workloads that we examined were Chrome browser。

 for example， or Tensorflow inference， what else and video encoding and decoding so we're kind of exercising all of these right now。

Wasting a lot of energy， think about it。Destroying the environment。

Another way of thinking about is that think。Okay so we also repeated the study more recently again with Google and looked at their edge neural network models on an edge machine learning accelerator。

 the HTPU at the time， and we found out that the problem even worse。

 in fact more than 90% of total system energy spent on memory in large machine learning models I'm going to talk about this a little bit later as well。

 but just to give you an idea over here， for example at the time these are commercial edge edge edge neural network models executing on an HPU。

 we find out that especially in the larger ones， most of the energy spent on off chip Interconnect and off toP。

😊，And if you actually take a memorycentric approach， which I will describe later on。

 you can reduce it by about 5 x or so on those things。😡。

Okay so basically I think hopefully I've convinced you that I could give you lots and lots and lots of data and that will be a full lecture which is also interesting because people have quantified this problem many times except these are the more real recent results with actually some workloads that are intensive essentially the problem is processing of data is perform far away from the data and if you want to actually fundamentally solve this problem you need to take a different approach which is what we argue for which is a more datacentric computation paradigm you want to enable computation with minimal data movement to be able to do that you want to really compute where data resides I call it where it makes sense in other words right if you if your goal is this。

😊，What we're doing today is not making sense because you're moving data a lot so we would like to enable computation capability everywhere in the end and there are many places we could do it today we're restricting ourselves to a very small fraction of this Sstrm dominated chipt and you can scale it it'll still be the same。

😡。

![](img/a1e29d1479bd7e3d4792bd1180a361b1_7.png)

But there are other places like many parts of this is idle because there are huge caches over here and they're not doing computation。

 they're just serving the compute units， there's DM， there's storage， there's sensors。

 these are actually huge， right this is darkness that no one thinks about。😡。

It's good to think about that， maybe we'll have some lectures on storage， but。😊，Actually。

 a lot of things can be done here today we're doing nothing。😡，It's a bit sad right。

 if you think about what we're losing is we're losing energy。😡，We're losing performance。

 we're losing the huge bit double parallelism that exists in these places right there's huge amounts of bit double parallelismter and terabbits actually if you add all of these things together。

 all of those bits can be doing computation， why are we restricting ourselves to here even from a performance perspective。

😡，Maybe you don't need all of those caches， maybe all of these bits should be computing and that maybe you don't need that much locality also if you're。

😡。

![](img/a1e29d1479bd7e3d4792bd1180a361b1_9.png)

Orchesting the system that way。 Okay， so we're not going to do exactly that in the remaining part of this lecture。

 but we're going to treat memory as an accelerator today we're actually very good at designing lots of accelerators。

 but we would like to put some accelerators on the memory site as well。

 That's the idea that we're going to look at in the rest of the lecture。

 but I'm going to motivate a little bit more also。😊。

So basically it's a very high level slide that talks about this accelerator based near memory or processing in memory。

 let's say so you still have a processor， it executes the application it sends tasks or queries to the memory devices we're going to focus a lot on main memory and some storage today and basically if the main memory or storage capable of doing executing that instruction that query could be an instruction。

 it could be a function， it could be the entire application offloaded。😡。

This does its job and returns the results， it looks nice and it's easier depicted than done， right？

Because there are many questions over here， how do you design the memory that can compute there are a lot of interesting approaches over here。

 we're going to cover some of them， how do you design the controllers that can compute how do you design the processors and communication units that can enable this and maybe how do you simplify the processor once you actually do computation capability in all of these other places。

😡，How do you design the software and hardware interfaces to enable us。

 what is the ground laity of computation， how do you offload things？😡。

How do you design the system software composite languages to make this easier。

 for example for people or most people， and then also how do you map your algorithms to the computation substrate over here because the computation substrate could be quite different or similar。

 but still on the other side of the processor， right？😡。

And I think this is one of my favorites over here， theoretical foundations。

 if you think about how many people have taken a computer science theory course here。

 probably not many people kind of yes， so when you quantify the algorithmic complexity in another way。

 it could be called algorithmic complexity， so the way we quantify the complexity of algorithms。😊。

which should ideally correspond to the execution time a little bit at least or cost of the algorithm is by counting operations。

 big notation， big data notation， if you're familiar with this， these are basic counting operations。

 how many ads do you do。😡，But maybe we don't care about that right that's a very compute centric theory of computation today。

 so it this is how ingrained in our thinking is this compute centric paradigm。😡。

Whereas if you think about the data centric paradigm or memorycentric paradigm。

 maybe I don't really care about the number of operations I do or maybe that's a piece of the puzzle。

😡，What I really care about maybe data moments right if what I told you is true so far and is true actually okay so basically this is an exciting crosst problem there are people working on a lot of these areas and the good news is there are some machines right now that can do some of this at least maybe not exactly a but people are making progress。

😊，Okay I should also say that this' is not a new idea。

It's a really old idea whenever you think about ideas。

 there are a lot of smart people who have lived through this world and they may have added similar ideas。

 so it's good to think about that。😡，And some people in the 1960s thought about this is the oldest paper I could find if you find other papers I'd be very interested in looking at。

 these papers， this one and the next one， they talk about basically putting logic near memory。

 so this is crossing near memory。😊，And people have looked at this multiple times。

 why is it interesting today， like why should we look at it today， like why are we talking about it？

😡，Today I have much more evidence because when I was giving this lecture like 10 years ago。

 we didn't have these memory centric computers pin machines。

 but now I can talk about it much more let's say confidently I was confident before to okay but basically I think today we have nowhere to it。

😊，I've already given you the application and system perspective right I' already said all of these basically we're very energy limited data moment dominates computation energy and we want performance energy and sustainability today if you want all of these at the same time you really need to minimize data essentially let's talk about memory technology problems this is also very interesting because we're having a lot of difficulties with memory technology today this was not true in the past as much。

😊，But now we actually have a lot of issues I'm going to give you a detour into the technology side。

 we may actually have some more lectures on this topic later on。

 but essentially technology scaling is not going well as you want to increase the size of memory increase the capacity you want to reduce the size of cells once you reduce the size of cells。

 they become unreliable there's a lot of noise that happens and because of this noise your reliability reduces and you cannot scale the energy and as well as performance as well。

So the solution to this is really demanding intelligence。

 I'm going to go give you some examples of that， and then there are emerging technologies which are interesting that can enable some new functions in memory that are relatively new that were not there before。

 let's say in 1960s as much， actually they were there， but they were not considered as much。😊。

That's very interesting also， like a lot of these technologies that we consider today as new are actually old technologies that have that that let's say。

😊，For example， if face change memory that were improved over many decades so that they could be enabled。

 but then there are some integration technologies that we actually have come to like 3D integration。

 hybrid bonding， etc cea， because of the improvement in technology that can enable some new functions as well。

😊，Okay， basically were squeeze in the middle to me， does that make sense？😡。

Okay so let me give you example so to understand these technology scaling issues we've done a lot of work。

 I'm going to give you examples from our work， we built this infrastructure。

 I don't know some people are over here at Tak I can see his hat over there his smile has worked on this a lot these are our D testing infrastructures some of them and the goal here is to have FPGAs and these FPGAs can be programmble and they test memory chips。

😊，And this is actually the original infrastructure that we built in 2011 you can see that it's kind of makeshift and we wrote a lot of papers on it。

 these are the infrastructures are open source， we may have some more lectures later on。

 but basically these infrastructures enable you to discover and understand and analyze different types of problems and one of the issues is Rohammer。

😊，I'm going to go through this thread really quickly。

 basically you can predictably induce errors in most D memory chips， actually all of them today。

 assuming you don't have any， let's say solutions。😊。

So people make pictures like this hammering memory。

 you don't it of course that way the way you hammer memory is actually you activate one row so this is a DR sub or you can think of it as a DRM bank it's a two dimensional array of cells if you want to access one bit in one of the rows you need to activate that word line which actually connects the bit lines of each cell to the sensorifier so that you can read the bit line you can sense it。

😊，You don't need to know a lot of details over here yet。

 but essentially if you activate this wordline， you can read data。😡，Now。

 if you want to read some other role， you precharge the bank or sub and basically deactivate the wordline。

 apply all voltage to it。😡，Now if you keep doing this repeatedly。😊，high voltage， low voltage。

 high voltage low voltage， or activate precharge， activate precharge， activate prechar。

 which is valid in the U， it turns out some cells that are adjacent。

 physically adjacent to this row get correct。😡，You basicallyically the reason is cells are too close to each other and cells are too small。

 they store some charge and if you do repeated activation of an adjacent row。

 their charge gets affected， they leak charge little by little and if you actually do these activations enough times before the cells get refreshed。

😡，You corrupt the data because their charge gets depleted。😡，Makes sense。

 so this is the Ro hammer problem essentially， and this should not be happening the fact that you're accessing memory should not change the charge level of things that are around。

😡，That's the idea， but today actually this happens。😡，So as technology scaling becomes worse。

 meaning cells become smaller and closer to each other。

 the number of activations you need to do to induce a bit flip。😡，Reduces significantly。

 so we have shown experimentally over， let's say， 10 years there is 100 x reduction。

 meaning that you can induce these bit flips really easily。

 even benign applications that sometimes access a row many times can cause these bitfs。😊。

So this could be not just a security issue but a robustness issue okay this also a security issue a lot of people have picked up on and showing that if you actually have a bit flip you can exploit it and you can do a lot of bad things which I'm not going to talk about but maybe we'll have a lecture later on so that's our original paper more recently we've shown that the problem is actually much worse again using this infrastructure we've discovered another phenomenon which is row press how song is sitting in the back he is the first author and we analyze this and this basically shows that you don't need to activate at the maximumimal rate to a single row to get bit flips。

If you actually activate a row and wait for some time， keep the row active。

 this actually causes disturbance and adjacent rows， and if you do that。

 you can actually reduce the number of activations needed to induce a bit foot by one to two orders of min。

😡，It's also fascinating this is a different redistance mechanism so why am I telling you this because these disturbance mechanisms are going to come in more and more as technology scales and the solution to this is you really need to have some sort of intelligence in the memory controller we actually argue that from the getgo in our original paper we said that the solution to this should be architectural because all of the other solutions like device circuit level they're not there yet。

😡，It's going to be expensive。And this is one of the papers that we wrote describing that sort of solution。

 and 10 years later， the good news is industry is following。😊。

They're not actually they tried it a little bit and they didn't get it right over time。

 but they're trying to get it right at least and this is a paper that was written by SK Heinx in 2023 that showed that essentially they built a memory controller inside the DM chip to solve this problem。

😊，So now you have the solution at a high level， it's an intelligent memory controller slightly at a high level basically you have for each row we have some activation counter and the DM chip internally increments the activation counters based on the number of activations you do and if the activation counters greater than some threshold they decide to do take some preventive action like refreshing adjacent groups for example。

 I don't want to go into the solutions the detail we may have a lecture later on。

 but the point is now we have intelligent controls in DM chips。😊。

And this was more recently standardized by Jdtic， it's called PerarO activation counters。

Which is a step in the right direction， if you think about this the more memory centric solution right。

 it's not a proor centric solution because people try to solve this problem on the proor side in the memory controller。

😊，You could do that， but it's a bit difficult if you actually do this in the memory side and give some autonomy to memory you can actually do much better I'm not going to talk about that but we have better solutions than this called self managingaging DM that Atherbe presented at micro we might talk about that later The question in my mind is are solution good。

😊，Basically。Can you prevent all the bitfs？And I don't think that's easy to solve。😡。

So we actually analyzed these solutions in our recent papers。

 this was at HPCN proposed better solutions， I'm not going to talk about details。

But there are better solutions out there。And I believe there are better solutions to come as well as there are better more problems to come。

 so in fact in my opinion we're scratching the surface。

 this sort of bitflips are going to become worse and worse and we need more and more intelligent controllers now as you keep adding intelligent controllers。

😡，Why not also add computation in those intelligent controls， for example， for each row in memory。

 if you have some activation counter， why not add some metadata for each row？😡。

And that metadata can be useful for programs to exploit potentially They could actually enable computation capability with some metadata next to each row。

😊，We're not there yet， the mindset is not fully there。This requires some more changes。

Okay so a couple of things I think that's interesting， we found out that row hammer。

 if you keep hammering a row many days， the number of as you need to do to induce a bit flip reduces。

😊，So this sort of effectively need to be examined more。

 there's a paper on that by GiI and more recently we have presented a paper at HPCA led by ata again called variable redistance。

 which shows that the redisturance threshold the number of activations you need to do to induce a bitf changes randomly unpredictably over time so if you do the testing to figure out how many activations you need to do to induce a bit fliplip for this row that changes over time as you keep testing。

😊，So how do you actually， in the presence of this accurately identify this this calls for an even more intelligent memory controller than what is there today？

😡，And there could be other solutions to this， and you can talk thebe about that and just the paper。

So I think this is a very fascinating thing and you can say okay what about emerging technologies maybe we should stop the I don't think we should stop the and we should look at new ways of organizing D there's like 3DDM for example that's becoming interesting I think it needs to be examined but there are other memory technologies also like face change memory S STTMM and we've done some work in this area the problem is these technologies all have some problems similar to this。

😡，And as they scale to smaller technology node。Problems like this are going to appear redistbance。

 right disturbance， et cetera。 So you need intelligent controls actually to fix these problems regardless of the technology you have。

 my favorite example is flash memory。😡，We may have a lecture on flash memorym。

 although we have only three approximately lectures as you know in flash memory flash memory is a very interesting technology like it was an emerging technology for many。

 many decades at some point it emerged because people found good applications to it。

 but it's a terrible technology if you think about it， it doesn't work。😊。

Meaning when you actually manufacture the bits。The bits。They store on voltage levels。

 but to make it work you really need an intelligent controller。

 the intelligent controller needs to program these voltages carefully so that you don't get these bit flipps if you learn about flash memory you'll know what I mean。

 but essentially all of the memory technologies have this sort of problem。😡。

DEM is a bit lucky actually， D DM has been considered the perfect memory technology and that's why it' has been dominant for many。

 many decades， except we are noticing that as it scales the very small node sizes。

 it's not as perfect。😡，Okay so that's why I think this is our lab thanks to Imailile。

 these pictures are here each took these pictures this is essentially I think of this as laboratory for understanding memory and maybe discovering more issues like this so we do a lot of work in this FPJ lab and these are some of the memory chips as you can see。

😊，Hopefully they're labeled correct。Okay， so the read disturbance is very interesting and there are sessions now in HCA S+ and coming up at Ica that talk about this one of them is just my our paper on Podhammer。

 which is actually relevant to later parts of this lecture also I may talk about。😊。

And it's not only redisturbance， I should say redisturance is very interesting。

 but the reason we built this infrastructure that I showed you or earlier versions of this lab or discovery lab is so that we can actually characterize the data retention so if you think about DM DM is charge based memory if you actually keep the data over there and don't refresh it you lose charge。

😡，And we wanted to understand how bad of a problem this is as you scale the technology。

 and that's actually a pretty bad problem。But you discover other problems as you actually build this sort of infrastructure and ask questions right。

 what else is wrong potentially， and I think there's more to come。So that's fascinating。

But the detour I took was to motivate actually what is coming next。😊，Any questions so far？

IFeel like I spoke a lot， but hopefully it's clear。Okay。Okay。

 so if you have intelligence on the memory site， maybe you can do more。😡。

And now we're going to talk about doing more， essentially。

 which is doing actually computation and memory as opposed to memory work， keeping memory working。😡。

And for this， I'm going to define a terminology and we're going to examine two different types of doings。

😊，And I think there are only two different types， if you come up with a new one， let me know。

 but essentially crossing near memory is what we're doing today， you have logic， you have memory。

 you design them completely separately。😊，Any kind of memory is designed separately from logic actually。

 logic you do some computation logic and memory as a memory design process。

 in some cases fabrication processes are completely different also like DM for example， or flash。😡。

But normally you have different design processes， different verification processes。

 different maybe fabrication processes， et ceter。😡，The question is where do you place the logic？

Do you put it far like we do today， do you put it even farther you could。

 do you put it closer and closer， maybe design the logic inside the DM chip， for example。

 next to each page。😡，You saw a memory that's different from logic， they're designed separately。😡。

But they are closer to each other in processing near memorymi。

 such that the downsides of data moment is alleviated。😡，That's the idea of crossing the near map。

 yet closer and closer。Prorossing using memory is fundamentally different logic， memory， again。

 forget about logic。😡，Doesn't exist。I have this memory I've designed。

I can exploit the analog operational properties of this memory to do computation。😡。

This is fascinating。And we're going to show you some examples of this because all memory has some sort of analog operational properties that can enable computation。

 different types of computation。😊，But you can see that that's completely different。

Now you forgot the logic。😡，And this is a different way of thinking about algorithms also。

 so in the end， crossing using memory is very efficient because you're exploiting the memory substrate to do the computation。

 you're not moving data as much。😡，You can exploit the huge bit level parallelism。

 so there's a lot of parallelism， but crossing near memory can be much more capable in terms of the operations because you're designing logic。

 you could design the logic as you design today， just put it next to memory maybe if you have a 3D stacking technology you can have a very sophisticated processor in the logic layer and you can have memory on top of it so a capability of crossing near memory is better but the efficiency may be lower because it doesn't reduce the data moment as much in the end I think we need to explore both and combine both of these things in the best ways。

 but there's a lot of I think creativity that needs to go into both of them。😡，Okay。

 so this is a slide that shows where you could do pressing near map， for example。

 if you have 3D stack member， you could do processinging inside the logic layer or you could do processinging nearbank。

 whereas processinging using DM is restricted to the arrays， for example。

 as I will show you soon to basically take advantage of the analog operation over here。Okay。

 but before we delve into that today， there are a lot of prototypes that show crossing near memory。😡。

え。not all of them are 3D stack but 3D stacking actually is a very nice technology in my opinion and more theyre better integration technologies that enable things you have logic layer and you have memory layers on top of that and they're connected through some sort of interconnect they could be large two silicon Vs they could be smaller interconnects through hybrid bonding and in more better integration technologies they could be actually vias that are really small let's say so the density of this interconnect determines how much bandwidth you have between the memory layers and the logic layers and also the fabrication as well as energy characters depends on how much energy you spend so that's good。

😊，This doesn't exist as much yet but it actually exist except it's not at least productized。

 but people are productized for example this and we have a lot of work on this I'm not going to talk about that but there is this company called OpM in France they built DDR4 or DM and inside sight next to each bank in the DM you have a processor and this processor is a multiple instruction multiplely multi- threadrated processor that's general purpose it can do any operation essentially except it can do something better than others。

😊，Okay so this is actually very interesting and you can actually buy this and program it if you're interested in it and if you have some ideas we can discuss that also and then this is commercially available at least it was commercially available until recently and then there are other prototype that are developed by SK Hyix。

 Samsung， more Samsung Alibaba and these are more specialized DEM chips where next to each bank or next to a set of banks you have some acceleration logic like matrix multiplication or multiply and accumulate support so you can actually offload simple matrix operations for example to the chip and their goal is to actually accelerate neural networks or recommendation systems etc。

😊，This is a bit different， this is near memory still but here the computation is done in FPGA on the board and then there are a lot of memorymi chips next to the FPG so you can see that there are different types of processing near memory the good news is there are also a lot of experimental chips and startups that are doing things like this。

😊，But this is near memory， so it's near term。😡，Meaning it's easier to do this because we're not let's say exploiting memory to do something more analog and less reliable so if you think about trusting using memory it's going to be less reliable。

😡，Whereas this is， we know how to design logic reliably and you can do that inside the memory chip。

 even in a fabrication process like DM， you can do that。😡，Okay。

 and then there are also interesting things like CXL。

 which is a compute Express link which enables interfaces from a compute unit like a processor such that you can offload computation to somewhere else and people have done that this is another paper from SK Heyix that shows that they can offload computation to a near memory of PGA for example。

And we have some works in this area also， but I'm not going to talk about that。

Okay now let me give you some research results so when we first started looking at crossing in memory and especially processing near memory。

 one of the things that we were quite excited about is the technology。

 which is 3D stacking in this particular case。😊，I' already kind of giving you the technology。

 you have a logic layer and you have memory layers and you can fabricate that nice and we believe in the technology at the time the technology was not that mature we're talking about 2012 or so and there was hybrid memory cube which is bad today。

 but there's HM which is actually somewhat similar except it does somethings better。

 something's worse in my opinion， like the interface is worse。

 I think but anyway if you can stack logic and memory on top of each other with some connectivity。

 high bandwidth， low latency， low energy， can you do something about it like what can you accelerate？

😊，And what we looked at at the time was especially graph crossing applications。

 even though the system is quite general as you will see。

 we wanted to exc graph crossing applications and our vision was you have a host processor that offloads graph computation to an accelerator that looks like this。

 so what is this accelerator it's actually a distributed system of these cubes let's call these cubes。

😊，Each cube has a logic layer and the logic layer you have an array of processors that are connected to each other。

 they can communicate with each other。😡，And you have an array of these cubes connected to each other with some top interconnect topology is actually very interesting over here。

 we'll get back to that in a little bit， but the idea is you offload some graph computation。

 you partition your graph on top of these cubes and each cube you're partition your graph on top of the memory that belongs to each processor。

😡，Okay， and if you want to do some computation on a graph node。

 what you do is you don't move the data to the function， you move the function to the data。😡。

So if a processor wants to do some update on a graph node that belongs to this processor。

 it sends a message to this processor saying， update this node and here's the update you need to do。

😡，Now， if you do that， you move the data less， you move the functions more。

 but it turns out moving the data less is a good thing in this case。😡。

That's the idea so this is program using remote procedure calls which is actually a distributed system programming model that's used data centers today。

 it's a full system work so I'm not going to go into every single detail over here。

 but the cores over here are very simple in order course they communicate via this message passing and the reason theyre very simple in order course is first you don't need a lot of latency tolerance second。

😊，You cannot afford to put complicated cores over here due to thermal problems that you have and due to area budget that you have so it's good to think about that so there's still thermal problems the 3D tagging actually exacerb based thermal problem which is not a solve issue but you have to take that as a constraint and that's one of the reasons why you cannot stack a lot of memory also actually okay but even then we still need a prefeting mechanism because the late installers of an in order core is not good so a lot of the prefeting mechanism that we discussed are still applicable over here now let me give you some example results very quickly this is a paper that you can read it's 10 years ago it was rejected twice before it was accepted to thisca but。



![](img/a1e29d1479bd7e3d4792bd1180a361b1_11.png)

![](img/a1e29d1479bd7e3d4792bd1180a361b1_12.png)

What matters is what happens afterwards， being not when it's rejected。

 of course it doesn't feel good， but basically if you look at this system tester Act system。

 it doesn't look like any of the existing systems at the time or today because crossing and memory are coupled each other。

 right？😊，And then you have a distributed system of these processing here memory engines。

And you get a lot of bandwidth for 512 cores over here。Now， if you actually。

 we should have looked at machine learning over here， if you actually squint at it。

 this looks like a。😊，GPU machine learning excccelerator essentially this is how things are designed today if you go to industry and design machine learning excccelerators。

 you have a distributed system of GPUs connected to each other。😊，Each GP has an HPM next to it。

 except GPU is still a bit far away from the HM it's not next to each other right it's not near memory processinging I would say but it's near memory processinging than what you may think about when you think about CPUs。

 let's say， but it's actually similar in concept。😡，So that sort of machine learning excited。

 but we're going a little bit farther。😡，Okay， and we didn't really specialize a lot for graph processinging in this particular case。

 it's really an in order core。😡，Okay， but basically you get significant performance improvements on average across five graph processinging algorithms。

 numbers are large as you can see， but later works improved on this work， many。

 many works exist actually that improve on this work and that takes the number to 100 x or so and I stop following at some point but people improved a lot of stuff over here specializes etc。

😊，Energy reduction is also significant and again later works in prudent so basically you improve performance as well as energy assuming the collective works until 2022 or so you improve performance of graph processinging by100 x。

 you reduce energy by 100 x that sounds good right it's not a tradeoff anymore。😡，Okay。

 if you're interested， this is a paper and these good folks who rejected our paper multiple times also decided to invite it to 50 years of Visca。

 maybe they're not the exact same folks， but so they found value after it was accepted clearly over time。

😊，So if your work gets rejected， don't worry because。

Believe in the work and if it actually is doing something good。

 it may have a lot of impact down the road right a lot of these stories I can give you one one over here。

Okay so there's more you can do if you actually rethink the system and formulate your algorithms in a way that's more amenable to acceleration using processing in memory and also processing using memorymi as we will say see you can actually get a lot more performance improvement this is a collaborative work that we've done where you actually specify find instructions set architecture that's set based。

 you basically operate on set set union set intersection， and then you express your graph algorithms。

 for example Page ranknk， etc， in terms of set union set intersection。

 these are very simple operations， bitwise operations on sets。😡。

And maybe even a compiler can actually help you over here to compile applications or algorithms into set based operations。

 and then you can actually accelerateel those set based operations on the near memory side as well as using memory side you also become more clear when we talk about using memory because we will see a lot of bitwise operations over there。

 but for near memory this also very good so I think it's good to rethink the system。😊。

From algorithms to ISA compilers to actually how to to see how we can best take advantage of processinging in memory systems。

 this is one paper that does that。Any questions？I'm giving you a broad stroke so hopefully it's interesting。

Okay let's talk about machine learning inference there's another work that we did that I mentioned earlier with Google and we analyzed on Google HPU different neural network models at the time used by Google these are commercial neural network models so unfortunately none of this is open source Google didn't let us open source this one but basically we found out that。

😊，On these machine learning models， you have a huge diversity variation in terms of the characteristics of the layers of the model。

😡，For example， some layers have huge arithmetic intensity， you do 10。

000 floating point operations per byte。😡，This sounds good for bringing something into the cache and doing a lot of operations and you amortize the energy cost of bringing data。

 but then there are some layers that are actually exactly the opposite。😊。

You do very little operations in terms on a single bite that you bring。

And then there's a parameter footprint over here， the parameter footprint is very very large here。

 it's relatively small。😊，So basically the question is if you have this sort of variation。

 what kind of a system do you design when I see this sort of huge variation heterogene come to mind basically design different accelerators to cater for these different types of layers and that's what we're going to do essentially。

😊，And if you actually look at the variation in terms of layer characteristics within each model。

 you see that different layers have huge variation in terms of multiplying accumulate operation counts or arithmetic intensity floats per byte。

😊，So basically people normally design these TPUs or accelerators as a mothic accelerator。

 they try to cater to all of these different characteristics at once and as a result this xccator becomes again a monster。

 meaning it becomes big。😊，Because you need to have a huge let's say parameter cache you need to have many units over here to cater for many different things in the worst case。

 let's say of course they're not designed for the worst case。

 but that's the idea so our idea is basically instead of doing that have let's say n different type of excels in this case n equals three one of them is compute centric that caters for these layers that are actually very compute intensive and the others are data centric these are actually accelerators in the logic layer of 3D stack DM and they're designed for different types of data flows etc based on the characteristics of the layers and have a runtime system that distributes the layers that you're executing to different accelerators。

And we show that in this work， if you can actually do this statically or dynamically。

 if you know the families， how do you actually decide what layer goes where or which accelerator？

We have some clustering mechanism to do that there's more work to be done in this area， by the way。

 the schedule is actually really important over here in my opinion and also how do you exploit the parallelism that you have over here with this sort of scheduler is also important。

😡，え。But basically we have an algorithm to decide what goes to compute centric excccelators and what goes to data centric excccerators and in the end we show that you can reduce energy consumption by about 3x compared to the baseline HTPU。

 you can see that the ones that gain the most are over here large models。

And you can also improve throughput compared to the baseline HP。😡。

And it turns out here I don't have the results， but it turns out if you look at the area costs of those three accelerators combined together。

 it's smaller than the area cost of the monothtic acceric。😡，Cl， the complexity is higher。

 multi excator is not complex because you design one thing， but if you actually design three things。

 the total area cost， additional area cost is smaller if that means anything。😡。

But I think this is evidence to show that existing systems are overproed。to cater to data intensive。

 to cater to everything， whereas if you actually do computation in different places。

 you can reduce the area cost that you have complexityity increases no question about that and you need to actually program it。

 etc cetera。😊，Okay let me quickly go over a couple of things and then we're going to take away so there's more work in this area that we have done this paper that I mentioned this is actually the first paper that we wrote with Google if you're interested you can take a look at that if this were a longer lecture I would talk about that we have been exciting bioinformatics workloads especially as I said this a huge data intensive problem and we have looked at 3D stacking techniques for this and more recently we've been looking at storage and this is Nikika's work over there Niika's in the back you can talk more about these works but I'll mention one of these relatively quickly because these are very large data sets in genomics for example you want to compare the sequence genome or query genome of someone to a reference genome you need to go through a lot of data。

😊，And if you want to do this on many， many genomes， you basically， for example。

 I took a sample over here， and I want to understand what is lurking here， what kind of viruses。

 what kind of bacteria， to be able to understand what's here。

 I may need to compare to database of size hundreds of terabytes， right many， many different genomes。

😡，That's actually a very interesting comparison if you can do it in a storage right。

 you basically need to go to storage， gigabytes is not enough， terabytes is not enough。

 hundreds of terabytes is what you want。😡，I'll give you one example of Gentor over here。

 this is Nikika's work in NASpo 2022， but basically the idea is if you want to do genome sequence analysis。

 what do you do today is you bring a lot of data， which is genome， let's say to a computation。

 it could be a CPU， GPU excccelator， whatever。😊，But this clearly has a lot of computation overhead because the computation complexity of a bit distance computation。

 which is one way of analyzing the genome is high， it's usually done using dynamic programming。

 you can do a lot of actually exploration and filtering techniques etc。

 but if you do it let's say not so smartly you have a lot of computation over it。

 but you also have a lot of data moment。😡，Okay， now people do smart things。

 people do actually a lot of heuristics， accelerators。

 filtering mechanisms to reduce the computation overhead。😊。

And actually they do in memory processing potentially。

 this reduces the computation of it and a little bit of the data moment of it。

 but this doesn't do anything to the data moment of it from the storage system。

 there's still a lot of data that gets moved from storageorch。😡，In fact。

 this exacerbates the data moment forward， if you think about。

 if you reduce the computation overhead red with smart techniques。😡，Including processing in memory。

 let's say in main memorym， the data amount direct from the storage system becomes bigger about right that's MD's law for you。

😡，Okay， so basically the idea in this work is to filter the reads or reads are sequences or fragments of a genome that don't require line。

 add some smartness， add some computation capability into the storage system so that you do simple things over there。

😡，So， that's。Only very little amount of things that really require the processing capability to get moved over here so for example。

 what can you filter if part of the genome is exactly matching a reference genome that's very easy to detect right it's an exact match detector and that way you don't need to move things that are exactly matching all the way here to do a very simple computation。

😡，Makes sense if part of the genome that you sequenced is not matching and you can detect that very easily with simple techniques on the storage system。

 you don't need to move those also， so what you really need to things move to the computation are things that you cannot decide easily。

😡，So that's the idea， this is one way of partitioning the work。Okay。

 and this reduces the computational red as well as data moment of red。

 and it gives significant speed up and energy improvements at the same time。😊，Okay。

 so if you're interested to talk toika， this is her more recent work， which is even more emal。

 but I don't have time to talk about that。😊，But if you want to see more examples。

 we have this primer paper that talks about a lot of near memory processinging examples。😡。

Before I take a break， I will mention that since everybody is interested in large language models。

 large language models are also about nibi memorym。

 and we have some recent works that talk about how to design let's say processinging in memorym systems that accelerateate large language models。

 again if you look over here this a ppi system， again I will not go into a lot of detail over here but if you partition the computation smartly across highper processinging units its GPUs and some processinging in memory engines that have a lot of computation capability to accelerateate fully connected layers and also some other processinging in memory systems that can cater for lower arithmetic intensity part of your system attention for example。

 attention computation layers， that you require actually large capacity and also some computation but not as much computation as here or there。

 but you need large capacity and if you design a system like this you get significant performance as well as energy improvements in terms of LLM inference。

I think this is where I should stop because。We're already over time。

 any questions we've covered pressing near meme。As I said。

 I want this to be an overview as opposed to like gling every nitty grty detail of everything talked about。

 clearly that's not going to be possible because I covered a lot of works over here。

 but hopefully this gives you a perspective。😡，So let's take a break， let's say until。I't know。Okay。

 15， 17。Let's be back at that time and then we're going to cover， let's say， in my opinion。

 they more fascinating。Part， although I'm fascinated by pressing near memory with the creativity that people come up with new logic。

😡，But we're going to look at an even more fascinating thing a more difficult thing also。Okay。Okay。嗯。

嗯。不是第证据。嗯。That来是。Yes。Yeah啊。但是我该。需要他。嗯原。これない next。Yes。いですね。But there was more to do a。

 I think it is yes。But I think programming I think。Iimitation when。问题他会再一。

Patientsient impactact for prosecution。Some how and take a you know we need to fix real lives。

 So're trying to think how we can input some sense of in a specific regions for example process and then have a way to kind of propagate movement with the。

For example， a do similar person memory variations。

I think that's good actually if its in terms on area brand。

 I think it's good to explore because not of many people have explored this。

can quantify how much extent could be could be。Yes。But eliminating the subject of occupation is also。

And but extension because we're lyinging if keep relying on the don't have and not just kind of nature but memories' still not brushing memory。

 we're not using memory。question。may。やば。Youward you were， very between。There' Thursday。不不。对。不。一。Yeah。

他的消息。对。这个他。其他时对吧。这就。Yeah。How下。I heard知道。No， I。せ。そほ。所谓一。あら。s seven PM m。Yeah。Everything。そです。Okay。

 is there number of。消 don。じに。那个是。に使うっていう。我做中系中国 o唔系。是也。就别点。Okay。是。The text。Thepen。关你注意目。诶，你。Yeah。嗯。아。

好睇。シいい。This is。was the reason。あ。于是他们把验，那我们开始定。Just have make some more。Yeah。还什么东西？You're sorry。

I said extra property。你是。怎么。How个。Okay。I haven't similar it a year。I why here。あご是な。I mean。

 during this was And then after this was。快。So。他说下信己。啥你刚才说。好。嗯。还有没有这个。你当咩诶。は優者？不一定是这人。那我回来。就是そ change。

Yeah。Oh。🎼Okay。这。Yeah， we can。Whi you kind want everyone to meet。Right。Let it to。好ello。对。嗯。对。嗯。嗯。是。

Yeah。抖音的翻业不算。嗯。Ex。Yes。で。Oh good， okay。Okay。嗯。嗯。Okay， I think we can get started。Okay。

 that was a quick introduction to why we do processing in memory and some processing near memory techniques。

 there's a lot more actually I may give you some examples。

 there are a lot of backup slides so if you can also take a look at them。

 but let's move to processing using memory， which is a fundamentally different approach to approaching processing in memory。

I'll especially look at processinging using DM in the rest of this lecture。

But you can do crossing using SGM， pressing using flash， crossing using emerging technologies， PCM。

 RM。Andbit D I， et ceter。And they all are slightly different， but some fundamental principles apply。

 and I'm going to you show you some。Two at least two types of primitive operations that can enable data copying as well as computation。

So basically using DM using the analog computation capability of the memory substrate。

 we can support Bpitwise copying， initialization and zeroering。

 which is a special case of copying many different Bpiwise operations and or not majority nor end。

 I will show you examples， we can generate two random numbers。😊。

We can do physical and clinicalable functions and if you want to do more complex computation。

 you can add more logic to do lookup tables。😊，Most of this happens at low cost。

 you need to change the row decoder circuitry and maybe where you do the computation， etc。

And we exploit the analog computation capability that inherently exists in the DMm structures。

 and the key idea is really if we activate multiple rows。😊，You perform computation。

If you activate them concurrently， you perform some computation。

 if you activatectua them sequentially in quick sequence， in quick succession， you perform data copy。

😊，And that's the idea basically we're going to look at in some other emerging memory technologies you can also do matrix vector multiplication in the analog domain I'm not going to talk about that because we don't have a lot of time。

 but if this was a longer lecture there would be some slides I think in the backup slides I have some of those emerging technologies and the fascinating thing is。

😊，You can see these operations in commodity off the shelfM chips so using the infrastructure that I showed you earlier。

 you can abuse the timing parameters of DM， reduce the timing parameters。

 and we can see that you can do data copy， you can do bit twice and or not majority none nor even though the EMM chips commodity off the shelf DM chips are not designed for this purpose。

 nobody advertise them this way， but you can actually do the computation。

 this is the fascinating part。😡，Yes。R these instructions for like visual。对。Yes。

 basically you need to do something like that。I'm going to show you some examples of that but。Yes。

 you need to if you want to exploit that， you will need to do that。

Okay and you see significant performance energy improvements these numbers are out of date。

 but yeah let's start simple let's start with the simplest thing you can do in my opinion currently。

 which is data copying initialization， so we copy a lot of data in our systems for many reasons security is one reasons initialization basically whenever you delocate a page you initialize it or you randomized or set it to zero and Google in their paper that I mentioned earlier in 2015 they basically show that of course all of their data center workloads。

 a huge set of workloads only these two function called memo and memcopy。😊。

Occuppy 5% of cycles this is a huge number for two function calls it's not all of the data moment in this it's just data moment that's generated by two function calls and in that same paper they said that techniques like what I'm going to describe next they cite our paper are going to be more and more important into the future to reduce that sort of data copy cost because our paper was published earlier than their 2015 paper。

😡，Okay， so how do you do data moment today？😡，Again， let's take the hat of a 10 year old。

You're the 10 year olds。I'm telling you how I do the data moment today。

 I want to copy this four kilobyte page to this four kilobyte page。

And the way I do it is take it bitete by byte， go to the CPU， bring it to the L1。😡。

Take this bitete by byte， go through the CPU， bring the tail L one。

 do the copy and write back the destination。Over there。As a 10 year old kid。What would you tell me？

Okay， somebody said stupid， yes probably that's the honest answer of a 10 year old kid， I agree。

Basically，1 old kid would see。Let's just do this， let's not be stupid。But we are stupid。Okay， anyway。

 there are reasons why we're stupid， but that doesn't change the fact that that's stupid， I think。

 okay， basically if you actually do what a 10 year old kid would naturally probably do without having all of this baggage of how we design systems。

😊，You would do it inside the memory， you would basically save latency。

 you would avoid cache pollution， you would reduce the bandwidth utilization on one of the most important resources that we have in the system today and you won't cause unwanted data mode it's not always the best option but if you had this option you could actually figure out when you would like to do this right today we have no option。

😡，That's the problem basically the problem is not that we're not doing it all the time here。

 the problem is we don't have any option other than going through the CPU or the memory controller today。

 if we had this option then you can design a system that's probably much better than today like I'm not suggesting replace all of the data moment by doing it inside the memory sometimes people get anxious or you say stupid。

😡，Yeah， you can do it sometimes right， it's an optimization problem。

 why not enable enable options in the system。So we're not extreme in the sense that we're not saying do everything in memory。

 enable options。😡，Okay so if you actually do this inside the memory you can reduce the let's say00 nanoseconds 4 kilobyte page copy cost to 90 nanoseds unopimized and reduce the energy from 3。

6 microds to 0。04 microds so let's take a look at how we do it in the best case so this is a DM sub you've seen this before it kind of looks a little bit slightly different but it's a two dimensional array of DM cells and this is a row buffer which is a cifiers so whenever you actually activate one row。

😊，This brings the data into the row buffer， transfers the data and this row buffer to let's say crosscoupd inverters each cell over here is a very strong s fire。

 so the data is captured strongly inside this SGM type of circuit essentially that's step one you activate Bro now you capture Broway in the s fires。

😡，Now what I'm going to do is to activate row B， which deactivates row A implicitly and connects the center up fires to the destination row cells now if you do that the data that was captured that's very strong inside the SstrM cells over here drives。

😡，Into the DEM cells。Because these are actually very weak and these are very strong and you drive the data inside。

So by exploiting the chart sharing， this is called chart sharing。

 by exploiting the chart sharing principles of activating one row， and then activating the next row。

 you bring the data through the row buffer into the destination row。😡。

And this is the fastest we could do it， maybe there are best better ways。

 but without changing the circuit as much you can do that， so two consecutive activitiess。

 negligible hardware cost。😡，And you get significant latency and energy improvements。

And I'm going to show you later that you can actually do this by violating the timing parameters。

Today's DEM， there's an activate to activate timing parameter。

 and DEM data sheets tell you not to violate that。Because that's how you reliably read the data from the second activated drop right。

 but if you actually violate that parameter and ensure that source and destination are in the same sub。

 you can do this copying in existing DM chips almost perfectly reably as we will see later yes software。

Which one？No no， this is basically exploiting the existing data right Oh I see yes。

 there needs to be some software changes that you need to do right to be able to do this the source and data。

😊，Roves need to be in the same sub right and that allocation're not if they're in different subways。

 you won't be able to do this。😡，Exactly， if you need to change your systems such that the destination page is allocated in the same subway。

 this requires awareness。For your memory alligator so even something as simple as this requires some work in the software stack and that's an adoption issue it doesn't well to be able to do this reliably you will need some hardware but you could also able I will talk about that later you could build an FPJ prototype that could do this which othered next to you sitting you can talk to them that changes the software such that you could do this in existing DM without changing。

Let's say any hardware work except for the memory controller。

 you only need to change the memory controller。Okay， but you don't need to change of the arm chips。

That's a fascinating part Okay so okay you can actually ask a lot of questions this is a O clone paper which was rejected once after it was accepted later。

 but basically you can do a lot of questions， can you do a faster copy Yes。

 inter subway across subways I'm not going talk about this you can move data at smaller gra larities you don't have to do it at 4 kilotes etc ceter Can you do a better interbank copy across different banks yes。

 and but let's talk about computation can you do computation let's say。😊。

And let me give you the primitive for computation in DM， at least one primitive for computation。

 maybe there are others waiting to be discovered。😊。

Now I'm showing you three DM cells now we go into a little bit more detail。

 these are the capacitors in DUM and these are the access transistors for each capacitor and these are the word lines。

 except I'm showing you only one bit per word line and this is the bit line and this is the Senifier and this is the other end of the Sen file。

😊，Now， if you imagine three of these rows， three cells。

I'm going to concurrently activate these three cells and imagine this be happening on 4 kilobyte of data but bit twice。

 and imagine this happening on thousands of subs， so you could do this on millions of bits concurrently。

😡，Let's do one one bit， you can currently activate。These three cells。

 which means that you connect the access transistors to the bit line。

Now the capacitors share their charge in a perfect circuit， if at least two cells are charged。

 you get the charge date at the end。😡，If at least two cells are discharged。

 you get the discharge state at the end。😊，And based on what I just said logically。

 this is a bit twice majority function。😡，So basically the final state that you get on。

The end of the bit line is really a bit wise majority of the three sets。Makes sense。

And this is the majority inver， essentially。This is nice with wise majority。

 it's a beautiful function if you set C to1， you get the or of A and B。

 if you set C to z or you get the end of AN。😊，Now you have majority or end。That's good。

 What's missing is a knot。😊，Meaning meaning essentially inversion right so if you want to be boolean complete or functionally complete。

 you just need a majority and a not or end a not or a not， right？😊，Now that's a bit difficult。

 but in this paper we propose that how do you get the knots。

 nots is actually already there if you activate only C for example， let's give one example。

 you get the charge state over here assuming it's charged and youve got the discharge date over here so actually the inverted values over here on the other end is the sand down fly except you need to connect it somewhere。

😡，And in this paper， we propose an expensive way of connecting it to the sub。You can read the paper。

 so you can actually get the inmer。And if you actually have all of these things。

 majority and or an imversion， now you can actually rethink your algorithms to match this。😡。

And in this work we actually looked at databases also set operations as we will discuss。

 you can in databases， for example， you can do a lot of bitwise operations if you want to compare if you want to for example。

 find people in a database who are between some age who make some amount of money who go to ETH。

 you can represent all of those things as columns of bits and then you could do bitwise operations on those entire vectors to actually figure out which ones satisfy all of those properties so you can do bitwise operations on huge vectors and some database are actually designed for that purpose this is the bit viewing database。

 people design these databases to maximize the bitwise operations in the database so that you can actually use sophisticated FPJs or GPUs for it。

 we actually port that database to Mbits and we see significant performance improvements on that and energy improvements。

😊，But essentially， if you can rewrite your algorithms to take advantage of these blockpi operation and maximize parallelism。

😊，You can actually do a lot， we looked at databases。

 we looked at set operations at unions at intersection。

 people actually design web searches to maximize Wi operations， their encryption algorithms。😊。

And there's DNA sequence mapping， these are all a lot of bitwiseice operations actually。😊。

This paper doesn't cover all of them， but we cover different ones and different papers。

 so this is a paper Embit。😊，So how do you make it more programmable you asked some good questions earlier in the amI paper we talk about how to expose it to the ISA et cetera。

 it requires changes so that you can actually expose export these operations to the memory controller clearly。

 but we have a more let's say principled framework to export any operation。😊。

So imagine that you want to do matrix multiplication right you express your matrix multiplication using a circuit that looks like this and or not logic or convolution or multiplication or division。

 whatever you can express your hardware designer and hardware designs are good at expressing things using circuit right。

😡，You can do that and we take that and convert it to what's called a majority inverder graph and people have designed actually electronic design automation tools so that they can take advantage of the superconducting logic。

 this work was done by Naand De McKlless group at EPF。

 we used that to let's say optimize this majority inverder graph and then we convert to a sequence of commands。

😊，Like these are triplelar activations， row clone， etc cetera。

 you need to use row clone also to be able to do that essentially a micro programgram that's associated with the operation that you have we call Bobbitps operation。

 you start somewhere basically whenever you see this Bpips operation executed by the program you call this micro programgram that's executed in the memory control。

So a compiler or a programmer essentially inserts a Bpivis operation to the Bpivis multiplication。

 for example， right。😊，It gets shipped to the memory controllert and the memory controller executes this。

😡，Micro programgram。This way you can integrate it into a sequential programming model。

 as you can see， and a single instruction can unleash a lot of parallelism。In memory。

So this is one way of taking advantage of these operations and again I will not go into details there's a lot of evaluation in the paper。

 but you can get significant outputput and energy improvements as well as overall application and performance improvements compared to existing CPUs and GPUs at the time。

😊，Okay， that's Indiaia。Wwhichch is very interesting so now we are talking about some adoption issues like this programmability in my。

 how do you actually make this more programmable in more recent work Geraldo who just defend this thesis a few like last week not a few days ago anymore he basically developed this MIDM substrate which solve some of the other problems I will give you the key idea over here but basically one of the issues with this Opitvis operations is you're doing too much kind of you have too much parallels4 kilobytes or 8 kilobytes assuming the row size 8 kilobytes。

😊，But a lot of compilers cannot target 8 kilobytes whenever you actually exploit parallelism at the vector level。

😊，Usually your compiles can target smaller bitwis， for example， AVX is 512 bits， right？😡。

Sometimes even smaller actually， so one of the issues is if your parallelism doesn't match。😊。

The parallelm that you have in DM， you're wasting a lot of。

Thinks you need to pad your data such that you do something useless over here， right？😡。

So in this work their realization is that if you actually enable finer grain operations than DM。

 so if you look at a subway in DM you can actually it's partitioned into smaller arrays。

 so if you look at Dm there's a big array bank it's partitioned the sub smaller arrays each sub is also part in smaller arrays called MAs and the reason for this is so that you can actually have lower latencies and better reliability etcter I'm not going to go into that but these subs these maps are today not accessible。

😊，Individual， so what this work does is it says basically oh let's make them accessible individually such that if you want to only operate on let's say these two subways these two mats let's say 512 bits plus 512 bits。

 we can do only these。😡，And the way we do it is basically by segmenting the wordline。

 we put some isolation transistors our a way of。😊，Disconnecting this part of the bit line from this part of the bit line such that you can do operationspats over here without doing anything over here。

 That's the idea。 It's not a new idea it's called fine grain Dm。

 There are many papers I'm going to mention one of them。

 But once you do that you can do one outpatient over here。And maybe some other operation over here。😡。

And you can exploit the concurrency of smaller bandwidth with operations across different mats。

 that's the beauty right you can pack essentially multiple instructions。😊。

Opatating on different data right there's a multiple instruction multiplayied that's why it's called MinD and Autovaak has the sector Dm which works nicely。

 I believe with this one it's an example of fine grain DM architecture。😊，You agreed， okay。

Okay so this work does more， I will not go into details but for example。

 when you actually aggregate data， I believe you cannot do everything just this way。

 it's good to add some logic over here such that you do some aggregation or reduction and this work adds some low costst interconnects for enabling vector reduction and I think there needs to be this is a pressing near memory example over here。

😊，I think there needs to be more at it， but that's future work and then I think one of the big contributions of this work is because you've reduced the grandularrity of the Bi width。

😊，You can operate that inside the DM， now you can retarget a compiler， existing compiler。😡。

Like LLVM in this work such that you can do automatic vectorization using LLVM of applications that are suitable for it and you can target these 512 bit let's say erase maths and completely transparently to the programmer you can exploit the parallelism that you can execute in the that's the idea over here now can essentially you can target an existing compiler and they'real modify the compiler to be able to do this transparently。

 I'm not go into details you can download this source code and do better I think this is a good opportunity to do better in my opinion essentially I believe don't I'm not a huge believer in auto vectorization but this is an easy thing to do I think compilers are still not very good at vectorizing automatically and people need to do some of this in my opinion but again you can cut this part and the compiler can still do the code scheduling and data mapping to memory and do a generation of codes such that you can actually。

😊，Do the operations inside the memory using MIDM substrate。

And the results are quite impressive in this case， the results show that if you actually use every single sub in DM to paralyze these vectorizable workloads。

 you can get huge energy efficiency improvements compared to CPUUs and GPPUs。😊。

And the reason is essentially， you put every bit to work if you think about it。😊。

You're not adding a lot of computation overhead， there's no logic。

 no significant logic added to do the computation computation is happening in parallel across many bits at low energy。

 but if you look at a GP or a CPU there's a lot of。😡，Bagage。

That is required to enable computation there's a lot of control overhead。

 for example right there's a lot of overhead in terms of the memory hierarchy and that doesn't exist over here。

 you're completely paralyzing it again， take it with a grain of salt because these are highly vectorizable workloads。

 making it work for more， let's say irregular workloads。😡，With higher sparsity， for example。

 these are open problems that are actually very important in my opinion， in this area。Make sense。😊。

Okay， so in the remaining time， I will give you something that fascinates me and I think Imile and maybe other people over here also。

 hopefully I'll talk back to because he built some infrastructure that shows us。

 but basically we're not smoking pot。😊，Meaning this hardware actually can do。😊，Some of this， right？

Well， I say this because for example， when we wrote the Embit paper in 2015。

 the first time one of you said。This is useless。Essentially that was a just other review so it was rejected four times before we got accepted so we also decided okay can we actually do this in real DM chips and we were inspired by a paper from Princeton that it was called compute DM that initially showed that actually there's some capability in DM chips so auto back built on that work and basically provided this end to end FPG based framework where he essentially modified the software and the hardware such that an application can do a page copy called that it gets mapped nicely to the subway is in DM such that it gets translated into the memory control and the memory control does the copy by violating the timing parameters such that the source and sort page gets copied to the destination page in D this requires changes the operating system。

😊，Changes to the application a little bit and clearly changes to the memory controller。😊。

But this is a substrate that he'd be happy to help you with。

I'm putting words into his mouth right now， but if you're interested in experimenting。

 it's not an easy system to experiment with but still you can do it essentially so this doesn't use any non-commodity parts it's just wireless timing parameters and there's a bunch of changes to system software and slightly applications sos all open source even if you don't have access to T you can actually have access to the open source Gitub as long as you can go to the website and at Ti has some results in the paper showing that this is hugely improving the throughput and the reason throughput improvements are huge over here these are micro benchmarkchmarks but still these are huge throughput improvements is because the processor that you have in the FPG that executes the program。

😊，Is actually a very Vimpy processor it's like 50 megahertz right so it has no latency tolerance mechanism so if you actually have a very powerful processor over here it will have some latency tolerance mechanisms and you will not get as much improvement。

 but you will still get a lot of improvement。😊，So it's good to think about this。

 this is a prototype to show that you can do this end to end。😡。

And maybe other people can develop on top of this so that you can do more things in。Okay。

 the fascinating thing is you can do it right by violating timing parameters。

Okay that's P DM more recentlyMile who sits over there has shown that you can do even more in existing EMM chips。

 these are not end to and， but these are more characterization of existing DM chips show that show that you can actually copy one row not into just one other row。

 but also what 31 other rows， so you can actuallybo copy from one row to 31 other rows with almost perfect success rate。

😊，Meaning some bits are not correct， but most of them are correct。😡。

This is fascinating actually I think this is more than expected because there's a lot of variation that happens in the circuit right we're not controlling any of that we're not designing the circuit to do this operation。

 we're actually exploiting what is there provided to us and the person who designed this thing didn't provide it to us thinking that you're going to do copy it they didn't design this for copy。

 they designed it just for access a single accessory。

You can perform the not operation with many output top brands and you can perform 16 input and N or and no operation I'm going to give you examples of this because I think it becomes even more interesting once we go into why this happens so this is in the M row copy in row on what we used to do is we activate the source row which brings the data over here and then we activate this national which brings the data from here to here everything is sourced because you do the copy in multi row copy you activate the source row which brings data over here and then you do a multiple row activation by wide the timing parameters in a specific way which copies data from here to all of the other rows。

That's the idea and again， you can talk to smile to decide how to do this exactly。

 but there's a reason why this works， which we already discussed。え。In the sourcero over here。

 this is one subway， I'm showing you one cell in one subway， another cell another sub in DM。

 there's actually in D DM architecture looks like this open Bitcoin architecture。

 essentially you have one subway connected to one end of the ssiifier and then another subway connected to another end of the ss amifier。

You activate the source row which brings the data into the CM fire and now a is over here sensed and then a prime goes over there and if you actually activate the destination row。

 this a prime that you sensed gets written into the destination row in the next sub。

 so this is how we can capture and not operation except not gets captured in the other sub。

How to take advantage of， it becomes interesting， maybe。If people are so inclined。

Okay now another finding in this work is to show that if you activate two rows in quick succession。

 you can simultaneously activate multiple rows in neighboring subways so these are the neighboring subways I kind of generalize what I showed you earlier。

 a bunch of shared tensifiers here， sub X and sub Y and if you actually do a particular activation of row A and then precharging and then activation on row B in the other sub。

 and if you violate the timing parameters heavily。😊。

You basically can enable activation of multiple rows over here and multiple rows over here。

 and the reason is theres some hierarchical row decoder。😡。

That is here and which role you enable depends on the high designer of the road decoder again。

 is smile I can talk to you about that and the paper has some more detail over here right is smiled Okay good and then basically he's paying attention to something else maybe maybe coming up with the next。

😊，Next next way of doing in DM computation but why why does this work let's say let's assume that you can do this and you can do this in real DM chips if you let's take a look at two rows over here and two rows over here these are two different subways they' are connected through this s fire now you do multiple of activation all of these get activated concurrent。

😊，Now what happens to the sifier， sifier senses the average voltage AB。😡。

And compares it to the average voltage of x and Y that's how the senseifieratess。

 this is based on circuit charge sharing principles right each of these cells share their charge and you get an average voltage and then each of these cells share their charge and you get an average voltage here and sense fire compares whether a average voltage of AMB is greater than average voltage of X and Y right if it's greater this becomes one。

 if it's smaller this becomes one。😡，Now you can use this to bitvis our patients。😡。

Let's take a look at an example you basically violate the timing parameter assuming that you set the values over the reference sub to VDD。

 which is easy to do and VDD over two which is harder to do but people have shown that you could do it and is smile can tell you exactly how to do it correct can you do it reliably okay there you go very reliably so you can do this。

😊，This you can this you can believe but this is a bit harder to believe but there's a way to do it actually now the average voltage chair is set to 3 VDD over4。

😊，Now， the value you get over here and over here depends on what are x and y。😡。

Now for the value over here。😡，To be。One，3 VDD over4 should be greater than the average of x and Y。😡。

For the value over here to be0，3vDD over4 should be smaller than average of xM y。😡。

So if x and y are 1， that's the only case where the value over here will be0。😡，Which means that。

This is a n function right at the bottom and a n function at the top。

So you get the bit wise and and bit wise net yes， how do I ensure if I opt to activate all cells at once that。

Voltage mush to each cell， which is not the original do first copy always yes you need to you'll need to copy essentially yes。

 if you don't want to lose the data， you will need to copy to the places where you're actating。

No question about that so if you want to really design a system that takes advantage of it。

 it's going to be somewhat similar to what we delivered Mbit in my opinion。

 which I didn't go into the implementation details， but yes， you will need to do that。😡。

So Roone is always important in all of these primitives。😡，Okay。

 so now you have bitwise n and bitwises nant， but you can also imagine bitwisey or n bitwisey norm by setting this to zero and BDD over2。

 right？😊，Okay。Okay， I think it's fascinating now the question is does it work in real DM chips and isma showed that in some manufacturers work some manufacturers don't allow you to violate the activate the activate parameter。

 which is not nice。😊，I think everybody should allow these violations so that we can discover new things。

But in some manufacturers， I think this is average across many manufacturers right how many two in this case。

 but basically if this is robust or multiol copy and you can see that，😊，You get an almost perfect。😡。

Copy accuracy。So clearly copying is easier。😡，嗯。If you want to make it perfect maybe you need to modify the DM a little bit and it's good to think about how you would do that because clearly approximate computing doesn't work right if I tell you only well it doesn't work in many cases。

 it doesnt work in some cases。😡，It's good to find applications where it does work and it's good to also make it work for the general case。

😡，Okay， so end N or and nor is not as easy， clearly there's a lot of variation that can happen in the circuit right now because you're activating many rows and you're actually trying to do computation。

 but still the success rates are not terrible right in fact in some cases it's pretty high in this smile I can explain you why。

😊，They're so high， but still 94% is not good enough。To do computation。

 but the purpose of this work is not to show that， oh， you can actually use existing DM。😡。

To do computation to show that existing Dm has this computation capability。

 even though it's not designed for it。😡，Now the key is imagining what else can you do right if you actually design the memory substrate to do computation。

 can I make this more reliable， can I do some other things？😡，If I actually change the substrate。

 so these are actually fascinating questions basically。😡，Okay。

 so basically the answer is we're not smoking pot。😡。

I think that's another way of summarizing the thing。

But you could give that answer after some number of years that's the beauty of long term research right I cannot guarantee you that I was in smoking pot。

 but now we're not completely smoking pot。😊，But maybe there's more to do。Okay。Okay。

 so let's see how much time we have， any questions？😊。

Otherwise I'm going to give you some other examples relatively quickly。

 but basically you can do more things， it's good to ask this question in my opinion。

 these are commodity memories that are not designed for this purpose， we're kind of abusing them。

 but we're showing that they're fundamentally capable of some things copying initialization and or not then nor etcter。

 which is fascinating。😊，But we have also shown that you can do other things using again our infrastructure。

 in this work， we showed that you can actually generate random numbers in D and the idea over here is whenever you access the EM there's some latency parameter right if you obey that latency parameter you get the data reliable。

If you， let's say， reduce that latency parameter and access D early。😡。

Before the sense amplifier settles。In terms of what it's sensing。

You can actually sense some randomness。That happens in the bit and the sense amplifier and this work is exploiting that figure out how long you should access a particular cell D such that the result that you get is a random value。

😡，Sometimes it's a one sometimes it's a zero and you cannot predict what it will be and use those cells as random number generators it could be for example。

 you could use 10 cells in 0 subs and you could concurrently generate 100 bit100 bit random number that's the idea over here which is a fascinating idea and we showed that in real DM chips you can actually generate these random numbers again this doesn't require changes to the DM chip itself it requires changes to the memory controller to violate the timing parameter and like many two random number generators you need to do some post processing in the memory controller。

😡，Okay， and then Autoback also showed that you can do better by activating four rows concurrently。

 and that gives you better higher throughput random numbers。😊，And more recently。

M has shown that four is not the magic number， you can actually do eight rows and that gives you even higher throughput random numbers。

😊，So if you're interested， I think there's a lot of interesting things here and again integrating these random numbers to the system is important and this is NiA's work that talks about that we've also shown again on real DM chip set so randomness is actually very interesting whenever you have randomness you have the flip site as well meaning determinism。

😊，Meaning some cells are random number generators whenever we access them with some latency you。

Create some random you basically sense some randomness in the physical circuitry that's what actually makes it truly random if people have a hard time defining truly random but usually they resort I cannot explain this physical phenomenon and this physical phenomenon leads to true randomness。

whichhich is not always satisfying， but anyway， flip side is some cells。

 when you violate the timing parameter always fail。And those cells。

Are different and different DM chips， meaning they form a signature of the DEM chip。

 which enables an identification mechanism for attestation， for example， remote attestation。

 which is essentially what a physical uncloatable function。

 physical uncloable function is a function that you generate that identifies。😊。

A particular piece of hardware right and this could be useful for many security purposes。

 you're communicating with the rights， let's say hardware， et ceter。

 nobody swapped this hardware with something else。😡。

So we showed that this could actually be a very nice physical and clinicalable function and again there are a very interesting things in physical and coable functions that I'm not going to talk about but this paper discussed。

😊，Okay， if you want to do more in DM you need to modify things a little bit more。

 this is I think a very promising area and this works in my opinion scratches the surface and the idea over here is。

😊，To use DM as a lookup table so that you can do arbitrary computation。

 I mean clearly you take in digital design courses and in digital design。

 at least when you take my course for example， I talk about using memory as lookup table， right？

And if you use memory as a lookup table， you can implement any function inside memory。

 it could be a multiplication function right you just basically set the truth table of the function and then use using the input parameters。

 you look up the right location and memory and that gives you the result of the function。😊。

So you can do that over here too with some expense， I think there's more to do in this area。

 but this can enable like more sophisticated functions in memory。😡。

Okay everything I said similar things can be done in flash memorym in this work we have shown in real flash chips。

 real N flash chips that again concurrently activating multiple rows provides a bitwise end or bitwise or function and you can make this more reliable so you can actually get perfect reliability using single levelvel cell mode and flash memory because we modify the memory controller meaning the flash controller in this case such that it can separate the distances in terms of voltage across different flash cells this is fascinating I think existing flash cells are also capable but a slightly different way you cannot do the bitwise majority function at least the way flash cells are designed today。

 again I don't have time and were almost。😊，Out of time actually， but if you're interested。

 there's a lot you can do in flash memory。😊，And more recently Mayanc one of my students over here。

 not over here， somewhere over here， maybe online， he has exploited this to actually do homomorphic encryption。

 so homomorphic encryption is a very bobit vice encryption scheme and it's very expensive but people are trying to accelerate it so that you can do computation on encrypted data ideally if you have encrypted data if you have some private data。

 you don't want to decry it because once you decry it everybody can see it with some methods。

 if you actually do computation completely on encrypted data， homomorphic encryption enables that。😊。

And it's actually very suitable for doing it inside the F chip using these Biwise operations。

 and this paper describes how to do that in one way。Okay。I think I've covered a lot。

 but basically we've covered crossing near memory， processinging using memory。

 and there's a lot more in this， like if you are interested in emerging technologies。

 we talk about emerging technologies recently we've extended actually I should extend the author list because Geraldo helped extend this paper to from 50 pages to 99 pages。

😊，So there's a lot over here and there's a lot more to add actually。

 we couldn't add everything we wanted that add， it gives you an overview of the state of the art and processing in memory。

😊，Actually， we recently wrote a paper which is going to be presented in two weeks with Aak in his smile that talks about a summary of this。

But I will talk about something that's really important， which is really the adoption of this。

 so it can design any hardware in the end， but it may not be adopted some people may know the story of IDM cell right。

😡，It's a very interesting hardware it's a heterogeneous， probably the first heterogeneous processor。

 it was not adopted because these folks punted on the coherence problem that was one of the issues basically they said coherence should be handled by the programmer。

It was used by Sony PlayStation， but then it was not developed further， right？😊。

Adoption issue is really important essentially and here we're not just designing a new hardware right new hardware is only part of it it's really a new paradigm in the end you're doing computation somewhere else even existing theory doesn't explain how to do this in the best way so we're actually changing a lot in the stack so there's a lot of barriers to adoption the good news is people are designing hardware right now so people are exploring these issues once you design the hardware people can explore software issues also more easily。

😡，So how do you what kind of applications benefit， how do you write the software for P。

 how do you ease the programming so that most people。😡。

Can easily transfer to so a lot of Geraldo's theseses actually answered some of these programming and systems questions。

 how do you interface with it， what kind of compiler and hardware support do you provide to ease programming？

😊，How do you do coherence， which is Harry， how do you do synchronization。

 how do you do virtual memory， you covered virtual memory？😊，Well speak。

 you may actually have questions。 Okay， I'm executing something in DM who handled virtual memory。

 right， that's a very valid question。😊，And probably you've seen that virtual memory is a mess。

And I think virtual memory is probably the hairiest issue that we have in our systems today。😊。

It needs to be re-examined completely in my opinion okay other stuff like isolation。

 if you're executing multiple applications， if you're executing a single application and you're doing processing in memory and also CPU or whatever compute unit you have is accessing memory。

 how do you handle the conflicts isolation scheduling etc how do you design the runtime and completion systems how do you actually do the scheduling of code to processing in memory or processing using memory。

 how do you do the data mapping data mapping that you need for processing in memory engines different from the data mapping that you need in the processor centric system and these actually conflict with each other and how do you actually maximize locality so that you can do better processing？

😊，How do you do the access and sharing control， so there are a lot of actually interesting issues and then how do you design infrastructures？

So I think all of these need to be researched， they're being researched actually。

 there's more research that needs to happen in all of these in addition to the hardware， etc。

 but probably the hardest one is the mindset。😡，Meaning all of these are problems。

 can also you can see these as problems， but you can also see these as opportunities， right？😡。

So if you actually look at this and say， oh， I want to change all of these at once。

 it's not going to be easy， but over time these can be changed。😡，If you change our mindset。

You need to change your mindset， you cannot say， oh。

 I'm going to use the existing data mapping mechanisms and I'm going to make crossing in memory work it's not going to be easy。

😡，It's good to again take the 10 year old approach， what is the right thing to do？To enable thisす。

That's the researcher's mindset， and that's also a kid's mindset。

And they will be honest with you again， so it's good to be honest。

Because you're not going to be able to do everything without changing things， right okay？😡，Okay。

 this is Geraldos thesis if you're interested。😊，He graduated， I think， well。

 29th of April and you can look at his slides， this these is not available yet。

 but we'll make it available at some point。And I think there's more to be done in this area this is just scratching the surface also Gerald to develop some programming models also for memory。

 but let me give you some again， we don't have a lot of time but I'll kind of rush through some papers that talk about this if you're interested you can go this is a work that we visited MIDdia our goal was to actually offload computation from a compute centric GPU to these memorycentric GPUs inside there in the logic layer so that we can actually have reduced the data movement overhead in a GPU system and we did this completely transparently to the programmer it's called transparent offloading and mapping。

So there's。Some things to be gained if you do it completely transparently to the programmer。

 but it's not if the programmer goes and modify things， you can do better， I think。

This is Geraldo's work that I will not talk about but you can look。

 this is a framework that we develop for pressing in memory that's a high level framework that expresses operations in a high level。

 let's say primitives and that can get compiled compiled can optimize things so basically I think these high level frameworks are very important because you don't want programmers to inject instructions right either the compiler does that or programmer programs in a way that is easily compileilable such that it can take advantage of processinging in memory and this is not the best work actually Geraldo showed that this is better than simple pin but that's how research evolves。

There's more work on identifying like which workloads should benefit and what you should offload again I will not talk about this。

This is Nikika's work you can talk to Nikika over there with the hoodie so okay so this takes into account something that for example。

 Tom a paper doesn't take into account instruction of floating and the data movement overheads。😊。

And then how to keep it simple as important these are some works again I will not go into details of all of these but enabling instructions to be offloaded is important coherence now we're getting into hair issues these are some works that we did where we show that existing query mechanisms are not enough if you partition work between posture and memory so you need to come up with new coherence mechanisms。

😊，Schronization。😊，And again， virtual memorymy。 This is a Harry is dish。

 I don't think we have a solution to virtual memory yet。 So it's a good problem， but。😊。

Maybe rethink virtual memory for processor centric systems as well because it's not measuring up in my opinion。

 so if we do up a lot of infrastructure， these are actually sampling of our works。

 there are other works also clearly that will not fit in one lecture。

 but evaluation infrastructure is also important。😊。

Okay hopefully I've convinced you that you can you need to revisit the entire stack I'm almost out of time I guess I'm approximate computing I'm almost out of time I can use approximate computing to disadvantage advantage as you can see。

 but let me finish essentially we want fundamentally efficient and high performance architecturectic if you want both and also sustainability you need to be data centric and also I also think actually robustness security a lot of metrics can be improved by being more data centric。

😊，But that remains to be proven so we want to design architecture with the minimal data moment I've covered in this let's say dense lecture how to enable computation capability in memory focusing on DM especially and major recent advances are giving you some examples that show orders of magnitudeed energy and performance improvements these actually exist even in existing systems like upm so there are actually applications that benefit a lot from the limited capabilities of real processinging in memory systems today I did not talk about those。

😊，And fascinatingly， unmodified I'm the priority capable of computation。😡，So I think going forward。

 we should really be 10 year olds and answer the questions。

 how do I design things that can compute everywhere。

 let's say design memory as a combined computation storage subject， not as an inactive。

Dumb storage update So for this clearly a lot of things need change design mindset and flow should change also most importantly。

 the mindset should change。 I think the future is bright basically。

 but there's a lot of research and design that needs to be done。

I like this example because even though I don't know much about this。

 the people who know a lot about this say that there is no dichotomy between processing storage and communication in this thing。

😊，Okay， so we have a lot of tutorials， if you're interested， you can learn more。

 we have some upcoming tutorials if you decide to do work， you can present。😊。

And there are a lot of open source tools okay i'm going to skip this。

 but there's a lot of industry maybe this is good to look at there's a lot of industry interest in this。

 even though industry is in an interesting place right they don't want to change a lot。😊。

That's how they want to make money right if you don't change a lot if you've invest in the processorcentric infrastructure that's good but they also want to innovate so industry has a lot of interest in actually enabling this sort of crossing in memory today much more so than they used to be like10 years ago so there's a lot of I think positive movement in this direction there are even discussions in Gen for example which is the slowest moving body in the world perhaps maybe they will disagree with that but essentially they discuss how to interface with crossing in memory devices for example today。

Okay， I think a lot of people did this work， you can see some people here。

I'm already out of time and you can actually see some people over here。

 a lot of people around you are doing processinging in memory work and you can talk to them。

Hopefully this was interesting， I will not keep you longer。

 but if you have questions feel free to ask right now or later。😊，Okay， I'll see you next week， then。



![](img/a1e29d1479bd7e3d4792bd1180a361b1_14.png)