# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p16 L15_ Parallelism, Heterogeneity & Bottleneck Acceleration (Spr 2025).zh_en -BV1Xc19BnET7_p16-

So this is an area that has clearly had impact， but I'll give you a history of it also a little bit。



![](img/208ed3af25019f89320ebb22fd05b2f8_1.png)

But before that， let's wrap up prefeing， as I said， and for prefeting， we've covered a lot。

And these are some slides that I added this year， we normally don't talk about instruction prefeting。

 but I think it's good to talk about a little bit also because it's an important area。

 maybe it has less potential in my opinion than data prefeting because data is very wide right data sets are huge instruction sets are usually smaller but that doesn't mean that all instruction sets are smaller。

 especially with let's say code bloat and these。Languages that make programmers life easier。

 there's a lot more instructions to process。And also， I think I guess in some models。

 some execution models where you execute short pieces of code and not very long pieces of code。

 instruction Pfeching can be very， very beneficial。But essentially instruction prefeting。

 the key idea is very simple， you predict which instructions will be needed by the program and fetch them proactively as opposed to data and all of the questions we discussed apply all of the techniques we discussed apply the major difference from data prefeting is instructions are really access sequentially whereas data not always the case in fact not usually the case and this happens because of the One Neman model right there are two key principles of the One Neyman model if you took DDC you would remember those principles anybody remembers those principles anybody took DDCA。

😊，One is the sequential。Execution and the other is a stored program computer。

 you store the program and you execute it sequentially essentially。Unless， of course。

 there's a control flow change。When there's a control flow change there' is an explicit redirection of the program counter。

 in fact program counter， the top program counter points to the current instruction that's executing right it's called the counter because you sequentially incremented essentially normally and that's why instruction prefeting sequentially works very well but of course when there's a control flow change this is broken so you need to predict the branches and figure out where the next instruction may be coming from。

Because of the sequentiality of the sequential nature of instruction execution。

 simple streaming or next time preaging is usually effective。😊。

But we will see a little bit more than that so our next sequential instruction prefeure we see next sequential data essentially always prefetch next n instructions in this case after a demanded instruction。

😊，This works well and program executes sequentially without branching we've seen this for data also if you're streaming through data。

 this also works nicely。And this is actually a very old idea。

 the first incarnation that I know of is really IBM 3691 which is a beautiful processor。

 it's one of the first out of order execution processors it's not the first but it's one of the first and there's a beautiful paper that talks about this if you're interested you can read one of these papers it also implements Tommo So's algorithm but you can see that there's instruction fetch buffer over here but those are really some of those are really used for prefetching。

😊，And again， I will not go through this， but at the time processor used to be less complex where you could actually specify the flowchar of the sequential instruction supply function like this and you can read it if you're interested they actually look at whether the bus bandwidth is available to the next level and then they decide to do prefeting etc。

 but today it's very difficult to specify things like as easily like this。😊。

It's good to think about that。Its from 1967。Okay so people I've been doing actually sequential instruction prefetching for a while these are more recent papers again I will not go through the details a lot。

 but a lot of ideas that you've discussed apply so okay you don't want to prefetch every end blocks when you're prefetching next sequentially end blocks maybe you want to figure out which ones are actually going to be useful and one way of figuring out which ones are going to be useful is whether the instructions that you have pre-fetch last time were used before so basically you add some metadata into the cache or the prefech buffer and you basically keep track of which cache blocks that you prefetch were useful using one prefetch bit for cacheline。

😊，And if you think whenever you see， whenever you go through those instructions again。

 you decide which ones to prefetch and which ones not to prefetch based on past useful。

 this is somewhat similar to throtdling that we have used。

 but it's a little bit different also in nature so this aims to be more accurate than an naive prefetcher next endline prefeter I don't know why they did just four lines。

It's very a little bit hard coded I don't like that's kind of hard codingding in general in papers but that's how it is but of course the downside is now it's more complicated you need metadata to identify which blocks are used right but that was true for feedback rates prefeting right as we have discussed right that's that word。

😊，And then people also applied other ideas like correlation prefetching to instruction prefetching。

 this is an interesting paper that talks about again， building on the next end prefecture。

 they basically say next end prefetture might be late because again you're running ahead and as a result。

😊，YouBy the time the prefetcher starts the next end fetches。

 the instruction engine is already there almost right you don't or you don't essentially you're not timely enough。

So in this paper， what they do is they essentially do correlation prefeging they identify。

An ICash mis address， basically they correlate whenever they find an ICash mis address。

 they correlated to an earlier early enough ICash access。

That hopefully is going to cover the latency。Of the prefetch。 That's the idea。 And for that。

 they have some mechanism to predict or calculate how long an I cash miss will take， et cetera。

 You can take a look at it if you're interested， But the basic idea is doing correlating a cache miss with a much earlier access so that whenever you see that access again。

 you start that cache miss next time。 So it's very similar to Marco prefeting in a sense。 right。

 we've discussed this idea， except it's specialized and applied for instruction prefeing。

 And you can read the paper。I'm going through these quickly， you could actually imagine other ideas。

 but I'm going to talk about one thing that is actually employed that has been employed in many processors。

 which is fish directed instruction prefetching。😊，At the instruction level。

 whenever you're in the front end of the machine， you have actually a lot of information about what you can do and fetch directed instruction prefeting essentially executes or exploits that information。

😊，So the key observations is that whenever you execute instructions。

 you essentially have a series of consecutive cash block accesses you have because it's all sequential sequential cash blockss。

 but then there's a gap sometimes， meaning you jump somewhere else in the program due to control flow。

 if you can somehow identify those gaps and predict those gaps。😊。

You could actually prefetch things early so we already do that actually with branch prediction right branch prediction already do that does that So the idea over here is to run the engine run the front end of the machine faster。

呃。And prefech the instruction into a queue while the backend of the machine is stall。

 you can keep prefetching instruction into this queue and you can keep predicting so the idea is actually really decoupling the front end of the machine and the back end of the machine back end of the machine can be stall for many reasons that we have discussed memory for example。

 but front end of the machine can keep going。Almost forever。

 the back end of the machine can be actually stall for a million cycles。

 but the front end of the machine can be fetching instructions。

 predicting branches and execute essentially going through the control flow of the program and feeding instructions into a queue。

 which is to fetch target queue， for example， instruction buffer。

 as long as it can actually predict instructions and keep fetching。😊。

This way what you can do is while the back end of the machine is stall。

 you're really overlapping the latency of the backend execution with the latency of the instruction cache misses if you're thinking about it and this way you can also overlap the latency of the branch predictions so this is a general idea of decoupled front end you're really decoupling the front end from the back end with a queue in between and and by doing so if you're really bineck by the back end。

😊，Hopefully you not you'll not be boic by the front end unless you miss predict branches， of course。

 whenever you miss predict the branch。These things may not be very useful right Okay。

 so this is I've already described actually a lot of things that are going to come in the next slides。

 but if you look at the execution of a program。😊，These are basic blocks control flow blocks。

 you can see that there are a bunch of instructions and there is a branch there are a bunch of other instructions there is a branch and there are a bunch of instructions there is a branch。

 so what you're really trying to do is go through this basic blocks and the instructions may look like this you basically predict this branch taken and this branch also taken。

And the idea as I've kind of said is you direct a prefetcher by predicting branches among prefetched instructions this also could be called branch predictor directed instruction prefetching。

 but as I said it's a more common philosophy not just directed that prefetching but the philosophy is really decoupling the back end of the machine from the front end of the machine and that's really the principle and that actually provides a lot of other benefits like。

Running the front end faster while the back end is stall or running the front end while the back end is stall and that way you can actually pre fetchch instructions and predict brancheses does that make sense？

Okay， so that's a very simple idea if you think about it。

 but I'll show you some interesting results from a recent paper from ArM， which shows that this idea。

 if you actually implement it nicely， maybe you don't need other prefets for instructions。

 that's what they suggest。😊，If Raho was here， we would also ask his opinion， he's not here。Okay。

 so basically， I think I've already said this from the current instruction you start prefeting sequentially。

 if you encounter a branch instruction， predict the target edge of the branch and keep prefeting sequentially until you encounter another instruction。

😊，This way， fetch engine can run far ahead of where in the program the execution is actually executing。

And as I said， this is decoupling the fetch engine from the rest of the pipeline。

And what what do you do with the instructions that you prefetch in this case you put them into a fetch target cube and this target queue is' really a FiIO cube it's really the predicted instruction stream and you can also decode them actually you could actually put the decode stage into the fetch part as well as long as you。

You need to decide where the decoupling happens between the back end and the front end of course。

 and the next stage， it could be a decocode stage or it could be the rename stage for example an outward execution processor consumes entries from the F target queue and processes done there should be processes done over there。

😊，Okay， so thiss an example， probably a picture is worth a thousand words over here here。

Theres a fish target queue this is one example implementation it's not the only example I think there may be better implementations actually。

 this is from a recent paper that talks about it essentially you have a fish target queue it creates a bridge between the instruction address generation unit and the instruction fetch unit and what you do is this address generation unit keeps on generating instruction addresses using the branch predictor and essentially it puts the instruction addresses over here and then the prefetch requests are sent to the eyeC and the instructions are essentially buffered over here or over here。

Okay， I'll go through this real quickly because I've described the ideas same So once you have a mis predictiondiction。

 of course， there's a downside right this decoupling doesn't help if you if your branch predictor is not accurate if you have a mis predictiondiction。

 you're back to square one， your fish target queue is flushed。😊。

After every instruction that comes after that misredted bench is flushed and you'll need to really start fetching instructions again。

So mis predictions are not useful for this case because you're really using the branch predictor。😊。

Okay。So this is an old idea， this is one of the papers that described the idea as you can see from it's from 1999 and it talks it received a test of time award deservedly recently。

 you can read that paper and this is many processors today。

 especially IDM processors were one of the first to implement this。

 these are not the oldest papers but you can see that they've been implementing in disease series。

 theyre main mainframe processors for a long time they actually have a very sophisticated front end that they used to describe in some old papers。

😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_3.png)

It's not just IBM， it's also AMD， Ar， Samsung， they've publicly shown that they've implemented this fish direct in this instruction prefitch。



![](img/208ed3af25019f89320ebb22fd05b2f8_5.png)

Now， the interesting thing is if you have fetch directed in instruction prefeting。

 how do you combine it with other prefeters？So this paper from Ar recently showed that if you actually implement fish directed prefetching with a large fish target queue size and with good enough branch prediction accuracy。

Maybe other instruction prefets are not that good， so this is data from their paper。

 we have not verified it， essentially if you have a small fish target Q size and if you disable fish directed prefetching。

 you basically have very big differences between different prefets。

 if you have a very large fish targetq size。Buffffering of instructions between the decoupled front end and back end and if you enable F directed prefeing essentially there is not that much difference between different types of prefes these are different types of prefes you don't need to know exactly what they are。

😊，So this is interesting， I think。it's good to think about how do you design the front end， right？😊。

So a jury is still out over here。Any questions？Yes。😊，好费。就是。嗯。Yeah。死。嗯。Yeah。嗯。😊，No。好有。

I mean basically the same everything we discussed about memory applies to instructions is also right if youre miss the instruction cache then you have to go to memory。

 it takes a long time。The question is how often does that happen I think that's what you're asking and the answer is it really depends if your workload for example has a small instruction working set very high locality which is usually the case actually in general then this is not a huge problem but there are some workloads where the instruction working sets are actually quite large some commercial workloads for example some database workloads where you actually keep doing a lot of different things in the workload and you're touching a lot of different places in the code this may not fit in your eyeCash。

😊，And also it may actually cause a lot of let's say accessing different parts of the code in that case this is actually a problem and these papers talk about that problem and it could be it could be as bad as the data problem actually one of the downsides of instructions is that's different from data is essentially with data you miss。

You can overlap that latency more easily with instructions， if you have an instruction cache miss。

 you're not filling the pipeline anymore， right？😡，So it could be more severe， but the occurrence。

 I think the frequency of occurrence of instruction cache misses are in general。

 much lower than data cache misses。😡，That's why we deferreder it to this late and we have not talked about instruction prefeing as much in prior。

 let's say years， but I think it's important to talk about it。😊，Okay， any other questions。

 that was a good question。People are still trying to wake up from the hibernation in the cold。Okay。

 it's going to get colder。Okay， so there's more recommended material on prefeting。

 some things we have not covered are in old lectures。

 but I'm not going to talk about that there are a lot of interesting things here。

 but we don't have time。😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_7.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_8.png)

If there are no questions， I'll very quickly pitch if you want to do research in these areas or other areas。

 talk with us， I know some of you are talking with us。😡。

Basically we do research in all aspects of computer architecture， not just memory centric aspects。

 procentric aspects also， in fact， we're going to talk about some papers so think about that and also I think one of the things that's interesting with prefeting is it's。

I cannot really classify prefetching as a completely processor centric aspect given a memory centric computing system right if you have processing near memory processing in memory。

 you may still need to do prefeting right。Prefetching by itself is not processor centric because you may need to execute something in memory。

 but then the data may not be there， right？Basically it's really targeting the data may not be their problem and data may not be there for many different reasons。

 not because you're procentic it's because someone else modified the data as we will see later on for example so I think this is an area that needs to be re-examined a lot in more memorycentic computing systems and I think that's true actually for a lot of the procentric concepts。

Okay， prefiing maybe somewhat procentric comparatively。

 but there are a lot of other procentric concepts like caching， for example。

 like out of order execution， they need to be examined within the context of memorycentric systems。

Okay， so we're always looking for bright and self motivated students who have a passion for rigorously solving problems。

 hopefully， and who're willing to do proper justice to scientific exploration。

 evaluation and communication。😊，And as opposed to what you may hear， unfortunately。

 we cherish working with everyone all over the world。There's no。Basically。

 we can get students from all over the world and we work with them there's no discrimination。

With diverse backgrounds。And I think we have an open and inclusive environment that fosters values creativity。

 free exploration， collaboration and rigor， so if you're interested in all of this work with us。😊。



![](img/208ed3af25019f89320ebb22fd05b2f8_10.png)

And we've already covered some of these slides so I'm not going to talk about this。

 but you can read more about us in the newsletters。

 we have actually quite a few of these newsletters right now。



![](img/208ed3af25019f89320ebb22fd05b2f8_12.png)

Starting from 2020。And we have some new alumni recently we've graduated two PhD students and a postdoc。

 they go a different place again， I'm not going to go over them， but I'm proud of all of that。



![](img/208ed3af25019f89320ebb22fd05b2f8_14.png)

And you can learn more about us from。Clearly， many。



![](img/208ed3af25019f89320ebb22fd05b2f8_16.png)

Lectures。And this is a recent interview and a bunch of other interviews， et cetera。Okay。

 so basically if you're interested email me taking take our courses online or in person。

 I think critically using papers and trying to develop ideas a really important component。

 so if we interview for example， we'd like to see how you're thinking you may not have a lot of background but how you're thinking is really important for me for example。

 that's kind of thinking is really important。😊，Okay again i'm not going to go over this because we've talked a lot about this and we have a lot more to cover but you can find this information one thing I will mention we have some thesis page online this is not very up to date we actually do a lot of work but we it's very difficult for us to keep a thesis page separately up to date so if you're interested in these general areas we should just talk with us。

😊，And then there's also this opportunistic nature of research。

 I think a good researcher is always opportunistic， meaning they don't say， oh。

 I work in these areas only。There's maybe some other area over here right that's actually very interesting and that area may be brought in。

By clearly exploration， but also they could be brought in by new people。

New people who may have new ideas or interest in different areas can enable exploration essentially a machine learning system if you think about it right you're working on in one area you develop expertise。

 you keep exploiting that expertise and clearly exploring within that expertise。

 but then there's there's some other exploration happens by randomly。😊。

Or somewhat randomly or guidedly choosing some other areas right so it's good to think about that so。

That's one of the reasons these CAIS topics are not up to date and the other reasons we're busy doing research we cannot update all of the CaEAs over there。

And some of the thesis just happen naturally， in fact I think the best research really happens organically。

 you come and you have some idea， maybe or you have some topic that you want to work on and you study it。

 you study a bunch of papers and you say oh， I have a better way of solving this problem。

What is this instruction prefeing， I can actually do this much more efficiently right？😊。

And that's the kind of research that can have a lot of impact in the end I think。

 but that's not the only way of doing it okay， so we have an application site。

 especially for people who are online， but with if you're here already then we can talk to you。😊。

Any questions on that？Otherwise， I'm going to jump into parallelism。

 heterogeneity andvolic acceleration。Wwhich is a different topic。

 but it's a very core topic I think we're going to talk more about terrorism after today also after we finish Boneck acceleration。

 but I wanted to do this bottlealneck acceleration first because it's going to make all of the other topics go a little bit faster in a sense we're going to accelerate some of the bottlenecks earlier and then we're going to talk about other topics that are related to this a little bit more。

I mean clearly we've been talking about parallelism but we're going to talk about a specific type of parallelism today and we're going to try to analyze parallelism and we're going to be more protracentric but the heterogeneity concept itself is not really prostracentric so this is our agenda we're going to talk a little bit about issues in parallelism and then talk about heterogeneous multi corere systems their evolution as I said I was giving this lecture like 15 years ago and I was talking about heterogeneity I was actually giving lectures on asymmetry everywhere you can find some of the slides in the back and we were doing a lot of work in that area also and。

There were clearly people saying that this is complex we don't want to design multiple cores etc ce but now everybody's designing multiple courses and there's a good reason for it and there are multiple reasons I'm going to give you one of the reasons that I believe is very important one of the general not just a single reasons but general collective concept of reasons as you will see and then we're going to talk about bineck exploration more detail these are some of the readings as you can see we're going to cover some of these。

😊，But let's start to start with heterogeneity even before we start with parallelism because we're going to talk about parallelism later on also。

 so heterogeneity essentially is I use the word heterogeneity but we use asysymmetricmmetry interchangeably in my opinion they have the same meaning at least for the purposes that we're going to use and it enables specialization。

😊，So a contrast heterogeneity with homogeneity and symmetry essentially homogeneous means everything is the same right symmetric means everything looks alike right this is really a system design concept。

 a very general one like a lot of the concepts we've been discussing in this course and also a life concept as well。

😊，Essentially， the idea is instead of having multiple instances of a resource to be the same。

 in other words， homogeneous or symmetric， design some instances to be different。TheI。

e heterogeneous or asymmetric， this is the design perspective。The other perspective is。

Because I cannot design all of the resources to be the same。I'm going to let them to be different。

Or I don't have any control right you can also think about it that way right。

 and you've kind of seen that right with refresh， for example。

 I cannot make every single DM cell the same。😊，Liage。So I'm going to live with whatever I have。

Now this a heterogeneous environment clearly there is a lot of heterogeneity in the。

 what we do is treat it homogeneously。😡，Meaning make the refresh equal for everything。

What I'm going to talk about is really exploiting that natural heterogeneity。

So we have already seen exploiting natural， so essentially heterogeneity exists in nature。😡。

I think of like transistors as nature， but you will see that heterogeneity exists among people also as you can see。

 right， the question is are you exploiting it in a heterogeneous manner？😊。

And we have seen that in refresh retention of our intelligent D refresh。

 you refresh the cell according to its leakage。😊，So now that's a method that exploits heterogeneity to gain benefit。

 which is energy， power， performance， quality of services。

But then you can also design things to be heterogeneous。

 I mean I've already also seen that right we've seen for example。

 tiered latetencydM right adaptive latetencyM youre really well adaptive latedM actually is exploiting a natural heterogeneity but tiered latetnt CdM is really designing a sub to have two components one is fast one component is fast。

 the other component is slow now you added heterogeneity that's a very conscious design。😊，Okay。

 so you can design heterogeneia or you can exploit heterogeneity that's already present。

Now regardless of whatever you do， different instances can be optimized to be more efficient in executing different types of workloads or satisfying different requirements and goals and we've seen this already。

 we're going to look at a more specific instances， essentially this fact。

 the fact that different instances can be optimized for different purposes enables specialization or customization。

So why do you want to do this， essentially there are two major reasons we've all have kind of seen that also。

 but I'm putting this into words right now， different workloads executing in a system can have different behavior。

And systems are designed to satisfy different metrics at the same time right so the first one different applications can have different behavior。

 different execution phase of a single workload or single application can have different behavior the same application executing at different times can have different behavior due to input set changes or dynamic events that the application sources right there are many examples of this like locality predictability of branches。

 instruction level parallelism data dependencies again I'm not going to talk about this but we're going to cover serial fraction and parallel fractions today interference characteristics that we may have seen。

😊，And also systems， whenever you design a system， you're really trying to satisfy different metrics at the same time when we design memory controllers。

 for example， we said we want performance， but we also want fairness。

And then we also want low complexity and you can keep adding more and more and that kind of leads us to more heterogeneous design as you have seen there's almost never a single design goal depending on the design point if you remember the earliest lectures we had a list of metrics like maybe 10 metrics but clearly 10 is not enough today。

 and here there's more。😊，O。So basically the problem with symmetric designs is it's really trying to fit everything into one type of design。

 one size fits all。I already sent this to all workloads and metrics you're trying to fit that design。

 but it's very difficult to come up with a single design that satisfies all workloads even for a single metric。

😊，So assuming you don't care about any other metric but performance。

 a single design is still not good enough and we're gonna to see that today more now this becomes even more difficult when you actually have multiple design metrics if you want to really get the best of multiple design metrics at the same time a single design cannot satisfy this another example we discuss for example。

 the machine learning inference accelerators right we talked about Google HTPU if you remember and a single molecule processor centric design was not able to really cater for many different types of machine learning models and layers so we decided to add heterogeneity into the accelerators so we designed three different accelerators in that particular case one of them processor centic two of them are datacentric and the goal was to really satisfy different parts of the workload so that you can get better performance and better efficiency at the same time and we also gained area efficiency if you remember but of course the cost was always complexity and you need to decide what to execute where and that's not going to change here also。

😊，The cost is going to be complexity and you need to figure out what component。

 what different component to use for a given thing task， for example。😡，Okay。

 so this all true for different system components or resources。

 essentially everything can be reexamined。😊，To be heterogeneous and also policies and algorithms。

It's kind of like a general principle right we've talked about a lot of general principles in this course。

 memory centric computing was one of them， I think heterogeneity is also an all encompassing principle。

If you look at all the resources that could all be heterogeneous， of course。

 this will increase complexity， yes。Okay， so let me give you a pictorial example again。

 a picture is worth probably  a thousand words， this is symmetric。😊。

This is slide that I prepared in 2008 or so。You can see that in this case it could be corears。

 but it could be anything actually， it's one size fits all and energy ands is suboptimal for different workload behaviors。

 essentially。😊，If your workload needs greater than this box， C， for example， two bad。

You don't have anything that is greater than this box C if your workco doesn't need as much as C it needs one10th of the C too bad it's wasting resources of the sea essentially。

So if you do asymmetric this is one example where this could be static or it could be dynamically configured to be asymmetric essentially this enables now customization and adaptation rights because processing requirements vary across workloads you can find that one workload that needs something as big as C1 should be scheduled here one workload that needs something as small as C5 is scheduled here of course you can actually go even lower right。

Okay， basically， hopefully you can get minimal energy and adequate performance by doing this。Okay。

 but now you've also seen that complexity increase right what is the ground laity at which you do this is it static。

 is it dynamic or there are a lot of actually interesting questions that open up。😊。

Okay we've already seen examples before I'll go through this relatively quickly。

 but something that we have not seen in this course is actually a very old principle if you've taken DDC we've talked about vector processing。

 which is really the core of today's GPUs today's GPUs are essentially vector processors。😊。

Even matrix vector multiply engines are essentially systolic vector processors kind of。

 but basically query1， which was designed to be a vector processor。

 I guess I have it in the next slide had actually a scalar pipeline as well。😊。

Because they figured out this wide vectors are not good for scalar instructions if you're operating on one piece of data elements。

You don't want to fetch 64 of them， or you don't want to waste 64 functional units for executing an instruction that requires a scalar value。

I'm going to show a picture of this you may have seen earlier。

 so modern processorors also have scalar instructions and Sdi extensions。

 which is essentially very similar to K one design from 1970s。😊。

We've seen decoupled access execute and DDC again， I don't want to go through everything over here。

 but basically you specialize the access part of the pipeline to a memory access。

 and then you specialize execute part of the pipeline to execution instructions。

All of these ideas are employed in existing process to different degrees we've seen t cluster memory scheduling。

 so I'm not going to talk about that radar heterogeneous latency DM hybrid memory systems and there are many different types of hybrid memory systems that we have seen also。

😊，Hederogeneous cash replacement policies， this is not up to date as you can see we've seen hybrid prefetching earlier also all of those are heterogeneous examples and these are all employed actually in neural systems and people don't think about complexity as much right when they actually do this well they do think about complexity of course。

 but they actually make the decision to actually have heterogeneous components。😊。



![](img/208ed3af25019f89320ebb22fd05b2f8_18.png)

Okay。So this is the cravon picture that you had seen in DDCA which I find fascinating because this was designed to be this is the supercomputer of the day right 1970s and you can see that this is the vector processor which is the major chunk it has 864 element vector registers you operate on 64 elements at a time but if you're operating on one elements at a time you don't want to use this because it's very wasteful so they add a scalar registers and this is heterogeneity at the ISA level as well as microarchitect level。

😊，It's not only that they added those scalar registers。

They made that scalar part of the pipeline the fastest of its time。

Because of what we're going to talk about later on today， which is a serial bottlealneck。😡。

Seymour cry was a very smart architect， he was more of the let's say intuition based architects who has been designing things so in my opinion he's kind of like a architect that。

Can make decisions without requiring a lot of data。

This is also good to think about because you don't you cannot predict all the data in the world you're designing a computer for 20 years down the road。

 maybe。Can you really have data to actually make a decision？

That's also true for architects who design buildings， for example， they design buildings。

Based on some intuition， also of course there's math， et cetera， and mold。

 but they can't model everything， it's impossible， hopefully they model earthquakes。

That's not true in all parts of the world though， sometimes they claim they all earthquakes。

 but then， you know， okay， so basically going back。😊，They they designed this vector process。

 the goal was to execute scientific code fast， which is paralyizable code。

 but they figured out quickly that。😡，The real balneck。

Assuming once you accelerate the vector code is really the serial part。

So the serial part sequential bottleneck will see that also we'll accelerate it in a different way。

 but we'll also use the same principle of heterogeneity here， they basically said oh。

 we really need to execute scalar code also fast。😊。

That's why they designed the scalar pipeline to be the fastest of its time in the 1970s。



![](img/208ed3af25019f89320ebb22fd05b2f8_20.png)

So it was the fastest vector processor and also a fastest scaling processor withs type。



![](img/208ed3af25019f89320ebb22fd05b2f8_22.png)

Okay， so we've seen hybrid memory systems， we've seen。

Thread cluster memory scheduling basically our goal was to design a policy that's good for different metrics and different threads if you remember and we've used heterogeneous policies for that again i'm not going to go through this in detail but clearly there's a lot of heterogeneity in this policy。



![](img/208ed3af25019f89320ebb22fd05b2f8_24.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_25.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_26.png)

呃。Well， there are different policies for each cluster to impact right if you remember。

 and then we've talked about radar， we've talked about tiered late and CDdM。

 these are just to jog your memory， these are all heterogeneous designs essentially。



![](img/208ed3af25019f89320ebb22fd05b2f8_28.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_29.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_30.png)

Okay。There's something that we're going to cover in later lectures， which is actually very important。

😊，Interconnects I've been trying to push interconnect earlier in these computer architecture lectures。

 but sometimes you need to figure out how to do that interconnects are actually very important because this is part of the communication bneck and there are heterogeneous designs for this also I'm not going to go over this right now but depending on the access patterns communication patterns you have you may want to have different types of interconects for example this Tler design from 200s early 200s。

If you're streaming data， the communication pattern between one core and another core is streaming。

It's much better to have an interconnect that's kind of dedicated to that streaming data and we'll see that circuit switching is one way of satisfying that。

😡，For other data， maybe you need different types of interconects。

 basically they had five different types of interconnects networks on this chip to deal with five different types of packets。

 cash requests versus responses versus IO versus core corere messaging versus streaming。

 essentially okay。There's also examples from real life that we could do a lot of。

 but I will go through this again quickly， it's abundant in real life， we're all heterogeneous。😊。

Genomic variation for example right but also other variations cells are heterogeneous this is I like this example also these are specialized for different tests you have a lot of different cells。

😊，Organs are heterogeneous， cars are heterogeneous， you can imagine why， right？

The buildings are heterogeneous for different purposes， rooms are heterogeneous， et cetera， okay。

 I don't want to harp on this more。Okay， now let's go into。

A little bit more essentially asymmetry is really a way of enabling specialization right there's always this tension between general purpose and special purpose it's always been there。

😊，Since computers were。Being let's say implemented initial computers are actually quite special purpose right they used to signal processing for some task they used to be analog etc and over time people said okay we don't want to design a computer for every single task so general purpose computers started to dominate but now we're actually back in if you look at the historical perspective we're in a position where probably special purposes becoming more important than general purpose it's already become more important maybe because of the applications and because of the lack of technology scaling in the general purpose domain so general purpose scaled really well because of technology scaling but then both applications and technology scaling has been pushing general purpose squeezing it now we're actually more special purpose today so aymmetry is really a way of enabling specialization it really tries to bridge the gap between purely general purpose and purely special purpose。

Purely general purpose we've already discussed is a single design for every workload or metric。

 purely special purpose single design per workload。😊，Maybe per workload per metric， right。

 so you could actually different have different designs for each workload， for different metrics。

Okay， so asymmetric essentially kind of is somewhere in the middle。

 multiple sub designigns optimized for sets of workloads or metrics and glued together。

 this is one way of looking at it。😊，And the goal of good asymmetric design， what's happening。

 is to get the best of both general purpose and special purpose， in my opinion。

So let's take a look at the general overall advance and disadvantages。

 so overall you can enable optimization of multiple metrics as we've discussed。

 you can enable better adaptation to workload behavior。😊。

You can provide special purpose benefits with general purpose usability and flexibility。

 that's actually interesting because you have some set of components and they kind of look general purpose。

 but the compiler， for example， or some system can actually take care of the scheduling。😊。

But there are also disadvantages we've discussed and overhead and complexity in design and verification is unescapable。

 I think。😊，There's higher overhead management scheduling on tastesymmetric components and there's also overhead of switching if you wanted to really switch between components okay I execute this workload over here but maybe now it should be executed over here for whatever reason because it went into a phase that is better fit for this type of core or cache or memory now you need to switch and there's always overhead and switching there's no free lunch unfortunately and these are the three major overheads I think。

😊，Complexity， scheduling or management overheads and also switching overheads and we will see this over and over and over in any heterogeneous designer yes mentioned。

The same system。Yes， is there。should be。一到发多回。嗯。Yeah beside that could be right。

 certainly if that input is provided you can maybe configure the resources。

To maximize some of the metrics that are important。

You still need to have some asymmetric components that you can play with。

So then the system or the scheduling or the test management becomes more important and they have to really be aware of what metrics are required and then do the scheduling the design can also be that way。

 but that's a bit difficult right？If you actually like you can。

 one vision is basically everybody has their own computer designed specifically for themselves。

This is actually expensive probably if you have an FPG that could actually enable things。

 but FPJs have their own overhead reconfigurability。

 but if you have an asymmetrictic design at least you have space for optimization for the metrics。😊。

Okay。Okay， another example， this is actually an old example today you have general purpose scores。

 CPUs and GPs together right this shows heterogenes in execution models and ISAs。😊，呃。In fact。

 increasingly we have other things also， but I'm going to contrast this with heterogeneity in only my architecture。

 basically micro architectures maybe heterogeneous and something。Upstream。

 the compiler or the system can basically take advantage of these different micro architects here。

 the programmer needs to write code potentially differently right for CPUs， GPUs， maybe FPGs， etc。

Memmocentric computing also adds heterogeneity to the system right if you have processinging near memory we never propose to get rid of everything else。

 so it's another accelerator potentially rate。I'll go through this also relatively quickly well we still have time that's good essentially I think we have three major problems in future systems and they can all be solved with energy you need。

😊，We've talked a lot about the memory system， we've talked a lot about efficiency。

 but we're going to talk a lot more about it today。😊，呃。

And there's predictably aroness we also talk about。

Essentially heterogeneous designs can cater for all of these more asymmetric designs。

 but today we're going to focus especially on efficiency and especially on performance efficiency。

 but energy will actually follow in many of our results。

 and efficiency is always an enabler for scalable， meaning if you're more efficient in the execution of your workload。

😊，You can finish it faster and those resources could be available for something else。

 or you could use resources in a much more frugal manner。And then if you have a set of budget。

 you can execute more things in parallel。So scalability is really a function of your efficiency always。

😊，And we're going to see really concrete examples from real workloads today。

So today actually we have a lot of examples of asymmetric designs。

 this was not the case in let's say 2008 or so。😊，But again。

 I'll go through this relatively quick these are some early examples or heterogeneous multicore。

 but today I think everybody's doing heterogeneous multi corere even in like large general purpose systems。

 as we will see some examples。😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_32.png)

Okay， I think we've already seen this picture also there's increasing heterogeneity in everywhere。



![](img/208ed3af25019f89320ebb22fd05b2f8_34.png)

And that's going to not change， in my view。So this is a real example。

 I didn't have this example in 2008 or even 20 maybe 19 or so。

 but you can see that there's a lot of heterogeneity in this thing right there's the high performance course over here there's they don't call it low performance cores because it doesn't sell a I guess efficiency course and then there's a GPU and then there's other stuff like neural engine so there's a lot of both micro architectural heterogeneity which is between high performance and low performance core or large versus small cores as we call them。

😊，And also architectural， like ISA， visible programmer visible heterogeneity。

 which has GPUs versus neural engines。And that's true for other general purpose SOCs also if you look at this。

 there are large cores over here， you can see that there are large and then there are small cores over here。

 more efficient cores， and then there are other engines like media engines。

There should be some other accelerators over here that I cannot see right now。Okay。Any questions yes？

Dyynnaically contributing。是。嗯哼。😊，关毕的。呃，预经。Yeah嗯。Yeah。

Yeah that's a very good question I mean i'm not going to cover some of those things。

 but that's a very valid question when it comes to heterogeneity because they could really enable dynamic heterogeneity in a much easier way。

 I think certainly programming。😊，FPGs or FGRAs much more difficult in general right whereas if you have a fixed function process my definition called fixed function like a fixed IA。

😊，A lot of these FBGs and CGIs lack the fixed ISA and that abstraction level has made programming easier for the masses。

😊，I think with FPGA and CGRAA that abstraction level is gone and that abstraction level once that abstraction level is gone you don't have a specific set of instructions now you have to compile your entire data flow program or whatever high level program into the substrate。

😊，呃。And we have not unfortunately developed good enough。Flows。To enable high performance。

Translation from high level code to let's say circuits people are working on it clear there are many people working on it。

 but I don't think it's there yet still。So that's a good question I don't know I think yeah I'm not sure if the fabric that is designed today is also the best fabric right because if you look at FPG there's a lot of overhead。

😊，In in really design， right there's a lot of overhead to execute a simple function。

And configuration doesn't get rid of that overhead right the area is still large so I think there are issues in multiple levels now the goal was of CGIs cose grain reconfigurable exploration was to get rid of some of that overhead right if you have coarse grain blocks that have much less overhead depending on what you do you can get rid of some of that hardware overhead for reconfiguration but I think the compilation issue still remains over there and maybe figuring out what are the blocks that should be there for CGRs has been difficult also right。

😊，But these are all great topics actually， very interesting topics。😊，In my opinion。

 yeah we need to be more efficient， we need to look at more efficient FPGA designs and also look at how to really compile。

 but that's also a tough problem。😊，This is an area where abstraction actually helped a lot the ISA abstraction。

😊，It's kind of really nice， you have it like for a compiler， you have a very nice target。

Now everybody at the higher level can target that thing and optimize that thing once that abstraction is gone。

What do you optimize for right it becomes difficult， you need to know the hardware essentially。

Which is a very interesting concept。Maybe it's an idea whose time has not come yet。嗯。Okay。

 any other questions？I mean， even this idea took a long time we we will see this asymme the course Okay。

 so let me give you some historical perspective these are actually slides from older times but essentially。

😊，While I was doing my PhD， people were actually working on multi course also and multiCse were becoming a thing。

 let's say in industry because scaling a single thread performance was not easy and people were building multiC and these are simpler and lower power than a single large core and it enabled large scale parallel on a chip and today everything is a multicore of course but the approach people were taking at the time were actually more symmetric approach except for this one over here。

 which is an interesting exception which we may talk about when we get to coherence also。

So with many course on a chip， what you want is really scalable performance， ideal scalability。

 we're going to talk more about that in multiprocess actually。

 essentially you want n times of performance with n times the course when you parallelze an application on end course。

😊，That sounds beautiful， ideally that's what you want。

This is called linear scaling also as we will see more， but what you normally get is。😊，M does law。

Hopefully people know about M D's law I'm going to show that this is really the serial bneck。

 your parallelization is limited by how much you can paralyze if there's a part of your code that you cannot paralyze that really bonecks your performance。

😊，So you want n times the performance。バ。50% of your code， you cannot paralyze。

Your n can be infinity and you get two x perform。And then this is you can do the calculation over here。

50% of your code is paralyzed， meaning 50%， you can paralyze an infinite number of courses that goes to zero。

Your 50 other percent remains， so you basically have 100 divide by 52 x right that's the idea。

It's always good to think about infinite perization now the problem is not just MD's law MDda's law is very optimistic。

😊，I mean it's a nice way of thinking about it's a model right it's a model of thinking and not all models are not always accurate。

 but they can be very useful anddell used this model to argue that okay we should really be focusing on single process in his 1967 paper he said a 1965 paper he basically said。

😊，In fact， the title of the paper was the validity of the single processing approach。

 I forgot everything， but I forgot the exact thing but okay the validity of single processor approach to achieve large performance capabilities on a chip he basically said on many workloads you cannot paralyze more than 70% so we should really be focusing on that getting that single processor right。

If you read that paper， you will see， but okay， assuming you got the single processor right。

 you parallellyze your program 100%。😊，You got rid of the cereal ballneck good luck I've never seen anyone to get rid of that serialreal ballneck yet even though they claimed to have done so they were actually when DPs were coming out what some people were saying。

 oh this is great so we're going to get rid of all the ballnecks。😊，Well。

 ce bonics are still there in GPus。But then there are other things。

 like okay assuming you've gotten rid of perfectly the ceonics， they're parallels。

 theyre bionics in the parallel portion， which we're going to focus a lot on today。😊。

And we're going to see some of that okay so this is MDda's law essentially this says your speed up is limited by the parazizable fraction of the program we're going to see this more。

 but before we see this more essentially have a parallellyizable fraction of a program and is the number of processors。

😊，The speed up you get with n processors is looks like this， you can make sense of this。

 I already kind of calculated with particular values F was 0。5 and n was infinity earlier。

 but basically the parallel portion you can parallellyze the execution time or the parallel portion can be divided by n。

Exec part of the serial portion cannot be divided by anything， as you can see， that's a model。Okay。

So this says that basically， as you parallellyze your program。

 parallel portion goes to zero as n goes to infinity。

And your ballne becomes f essentially right so if you take the limit of this as n goes to infinity。

 you'll get F。😊，Or one do I buy one my that right that's what you would get。Okay。

So basically it says maximum speed up is limited by C force in the next lecture I'm going to show you some beautiful graphs。

 but you can again put some numbers over here F is 99%。😊，That's a pretty high。

 you would be lucky if you have a program that looks like this。And maximum speed up you get 100。

Imagine you have  a thousand corere processor， you'll get100 next。

You're wasting 90% of your course if that's the case， okay， and that's not all。

 unfortunately there are bottlenecks in the parallel portion also it's not usually perfectly parallel。

We'll talk about more of these， but there's synchronization overhead。These cores。

 these things that you parallellyze across different core。

 they need to synchronize with each other right we talked about locks， et cetera。

 we're going to talk a lot more about that today。😡，One of them may need to wait for another。

Now you serialized that code it cannot be perfectly parallel left that's the case right perfectly parallel means there is no synchronization theres no communication and you're perfectly parallellyzed that as we will see there's no contention also between them right so there are three major reasons why parallel portion is not perfectly parallel and these are very fundamental synchronization you could also call it communication。

😊，Lord imbalance。Meaning imperfect parallelization。Yeah， one core， you parallellyze your code。

 one core takes 10 seconds， the other core takes one second。

Why because I don't know there's some data dependency and one data is harder to access for one core。

 there could be many reasons， of course you have not perfectly divided the work that could be another reason right there could be many reasons their load amounts happens because of programmer or the micro architecture and anything across the stack potentially。

And we're going to see that also。Actually， we've kind of seen that when we talked about memory scheduling for parallel applications。

And the third reason is we've covered this a lot， which is resource sharing， right？😊。

These things that you parallellyzze don't execute without interacting with each other。

Apart from explicit interaction， they also implicitly interact in the shared resources once you have contention。

 one core can be delayed over another core， you have serialization essentially。

 and that contention that we were trying to solve nicely when we design memory controllers， caches。

 etc leads to this n this equation to not hold essentially。

So it cannot be easily to a simple F by N at that point。

So that's this is actually a nice slide that summarizes all of the caveats of perism that I know。

 if you come up with something else， please let me know and we happy to modify the slide。

The slide has been around for 15 years so far。Okay。😊，Okay， so basically。

 let's talk about these serialized code sections， essentially many parallel programs cannot be paralyzed completely。

😊，We talk about sequential portions， serial part， I'm going to give you examples。

 there's also critical sections that we talked about earlier locks。

 essentially only one thread can be updating the shared data and another thread that needs that shared data needs to wait。

There are barriers when you have to paralyze your program。

 partition the work and all of the threads do something and when they need to go to the next stage of parallelzization。

 they need to do something else。For example， I think one of my favorite examples here， okay。

 I'll give it today， not tomorrow， you have a program that you've written and your goal is to count the number of letters in the book in a book。

Right。One way of writing this program is actually take the book。

Let's say it's a thousand0 pagebook and you're dividing it across 100 processors。

 give each processorer 10 page， 10 pages。This is actually very commonly used in parallel proy it's called the bulk synchronous paradigm of execution you give a chunk of work to each processor and let's say you serially sequentially distribute the chunks the first 10 pages go to processor zero。

 the last 10 pages go to Pro 99。😊，Not a terrible way of ferilization， right。

 and then each processor counts the first 10 pages。And then after all of the pro finished。

 you try to merge the results。So the first barrier you get is until all of the processors finish their pages right of course you can optimize this like you know you can a subset of processors et ceter。

 but let's assume that it's a first cut at this program all the processors need to be reach the barrier so they update their local histograms of the count of every single letter right that I say word letter it should be letter earlier so you're counting the letters。

Now all of the bottlenes exist over here， one processor， the first processor。

 let's say first 10 pages are empty in the book， what does that do。

 It's done very quickly right it reaches the barrier right away。

The next processor unfortunately gets the most heavy pages。The next browser gets five pictures。

 so it's also easy。 So now you've broken the load imbalance immediately in that picture right in that task and this is a difficult task。

 How do you achieve load imbalance right in this task。😊，Think about it。

 even the simple problem of counting letters in a book。Okay。

 and then you're when you're updating the histograms， like shared histograms。

 you need to access the critical sections。And then when you're distributing the tasks to different processors。

 you have a sequential portion who distributes the tasks。

Do the processors get their task on their own？Yeah， you can try to paralyze it。😊。

And then when you're actually trying to solve a load imbalance problem。

What might happen is you may actually add more sequential portions。

Because if you want to solve the load inbal， let's say dynamically for summary you figure it out okay。

 my load in mouth was incorrect， it's very hard for the programmer to solve the load inbalance problem in the problem that I described right the programmer doesn't know the input。

This may be the thousand page book it may it may have this imbalance another book may have a different type of imbalance right so basically if you're trying to solve the old imbalance problem with some dynamic mechanism you make your program more complicated you can do test steal for example。

 you basically chunk things in a way such that smaller chunks can be scheduled to different processors but then you have overhead of managing those chunks right now。

So these are all fundamentals of parallel processing if you think about it。

 and all of them are limited by all of these serialized code sections。😊，Okay。

 serialized quo sections， if you're serialized， basically your performance reduces。

 you waste energy and you limit scalability as we will。😊。

So let me give you one example very quickly its one of the papers that we're going ask you to eat MySQL is an open source database it's relatively old right now but people still use it you open some database tables and you perform some operations you don't need to have exactly what these are but this part of the program is parallel this part of the program is more let's say critical section base you need to access this open tables cache which is really shared a lot across a lot of processors and whenever you really open a database table you need to market as I open this database table so nobody should else should really change it so you have actually you're going to write to this table so there' is a critical section that protects it。

Again， the paper has some more detail， but this critical section is really limit to your performance。

As you add more processors， meaning increase your chip area， let's say。

Your speedup increases after until some point and then after that point it starts reducing and one of the major reasons the speedup starts reducing is proous content for this critical section。

This critical action becomes a b。I will show you that using simple asymmetric designs can actually increase this。

 This is an unopimized version。 Basically can scale up this is called a scalable curve in parallel processing。

Essential， you're computing the speed up compared to a single processor version of multiproor versions。

😊，And this is where the performance scales up I don't know what that core is， but 16 cores or so。

 right， 16 core area coolants。With asymmetrictic multipressor， you can do much better baseline。Okay。

 we'll see more examples。Okay， so let's take a look at what fundamentally do we want right fundamentally in a serialized code section。

 you want a powerful large core， yes。😊，Yeah。This example， okay？I。Ssymmetric or， yes， exactly。

Actually have。You get worse performance because your bottleneck is really the critical section。

And what happens is you're really ping ping data， we've discussed ping ponging in an earlier lecture。

 we're going to see more， but youre really ping ponging share data as well as locks。crocro the pros。

There's also contention effects that are also taken into account here。

 but that's not the major reason why the performance goes down。But this' is a very common curve。

I mean， in aysymmetricmatictic also at some point， you would go down。

 but maybe not at 32 for this workload rate。😡，Okay。That's a very good question。

 so basically we want in a serialized quote section， you want a powerful large quote。😊。

The question is what should that powerful large code look like in app parallelel code section you want probably any Vimpy small chs right depending on the code section。

 if you parallellyze it really nicely， wimpy small chs could be good。😊。

And these two clearly conflict with each other right if you have a single powerful core。

 you cannot have mini core and a small core is much more energy and area efficient than a large core so this is what we're going to assume a large core is a large out order execution core with a lot of techniques for instruction level parallelism and memory level parallelism small core is very simple。

😊，In order， I'm going to show you more examples of this。

 maybe not even a branch predictor right it has it may have fine grain multi3。

And this is kind of a rule of thumb， it's not of course correct for every workload。

 but this is kind of an assumption that we're going to make for some calculations now large cores are power inefficient。

 essentially you get 2x performance with a large core for 4x area。😊。

Area could be first order thing for power let's say predictor of power and these are some results from Intel actually this is paper in 2004 they basically talk about large versus small cores in a different context as we may see later on but this is what looks like a large core over here and this is what looks like a small core you can see the pipeline with pipeline depth you can see the normalized performance I think they're quite optimistic over here but the five to 8 x normalized power is much larger and normalized energy per instruction over here so basically large cores are not very efficient but they do get high performance even I'm not true about the5 to8 x I don't know what code there any。

Okay， but when multi core systems were being designed。

 this was one of the earliest multiC actually the IM put together a very nice multico system in 2000 earlier than 2002 actually it's a symmetric multi course but basically they added two powerful course this was one philosophy we're going to keep the course powerful but we're going to have few powerful course。

呃。And you can see some of the parameters of the score which we'll not go into in detail we've already seen the screen based prefeting that they employed actually in IBM Power for but this is for that time it's a pretty powerful core。

 many coreds did not even have eight wide instruction fetch at the time。

IBM Power5 made each core a bit more powerful and they added multi threadreading simultaneous multithreading so that was the philosophy essentially there was another philosophy which was sun as we've also discussed these guys were bought by Oracle unfortunately as you remember so they were innovating quite a bit actually but they stopped innovation that's very sad a company buys another innovative company and makes it。

😊，Nonexistent that has happened multiple times also。 I think more recently。

 it happened with VMware versus Brocom Brocom bought VMware and VMware is dead now kind of yeah。

 meaning the innovation is dead。 So it's good to think about also those things。

 So if your company gets bought that doesn't mean innovation in the company will continue。😊。

That actually happens in a lot of startups also some some big companies buy startups to。

Maybe kill the innovation because they're not competitors anymore， right？

Okay it's good to think about it sometimes maybe not all systems are designed with good principles in mind okay anyway going back Sun these guys were actually because Sun was a very innovative company that's a lot of innovations before this also but they were designing these simple wimpy core processors if you look at these course they actually had eight processors over here each processor was four way multi threadreaded and if you look at a single processor it's very simple it's four way fine grain multi threaded for six stage dual issue in order there's no branch prediction there's very little data dependency checking because。

😊，At any given time you have you don't have two instructions from the same thread in the pipeline so there's no need to predict branches there's no need to do data passage this is basically fine grain multithread as you can see it even at a shared floatinging point unit among cores and that turned out to be a bnick so they actually replicate in the next instance of Niagara in Niagara too so this is a very different design philosophy as you can see right it's very simple course but many of them and they claimed this was good for let's say their commercial workloads so over time they figured out okay maybe this was not that。

Good idea so let's improve let's make cores more and more and more powerful and that's where they were going with Runnerhead for example they added runnerhead to make each core more powerful and then they were actually adding this simultaneous speculative threading that I mentioned when we talked about runnerhead to make each core even more powerful so they figured out these small cores were not really that good in the end because of the Balnecks。

😊，Okay， but ideally we don't want to essentially either extreme approach it。

 what do we want and remember， these are our demands right？

And we've already said everything over here， the question is， can we get the best of both worlds？

Let's take a look at best of both worlds a little bit。

 so we're going to make some assumptions over here small core takes an area budget of one and has a performance of one。

 large core takes an area budget of four and has a performance of two。

This is the tile large approach like IB and also other folks。

 as you can see these are some early multiple processes。

 you get high performance on single thread serial code sections， you get two units of performance。

But you get low throughput on parallel program portions， eight units。

Why is eight units because you have four cores and you have two units of performance。

 so you have four times two right， eight units。Tile small approach。

 you tile many small cores in this case， because of the area constraints。

 this is area four by four is 16 base core area and this is 16 small cores now。

Some folks also had this idea， Tyler have we discussed it was actually ultra small course。

 Intel had actually a very interesting project at the time。

 which unfortunately didn't go through their goal was to actually have many。

 many X8 small course to compete with GPUs unfortunately the software stack was not optimizable as easily so they couldn't compete with the GPUs and this project kind of。

😊，Not dye， but kind of transformed into something else that is not as influential at this point。

But the point is there was a lot of innovation going on also still， so basically if you look at this。

 there's high throughput on the parallel part， if you're parallel you get 16 units， right？😊。

That is working for you， but unfortunately on the serial part。

 you get a single thread working on a small course so you get one unit of performance。

So your parallel part performance is high， but your single core performance is 50%， right？Okay。

 so basically we've already said this right this is kind of putting everything in the same slide tile large has benefits on single thread but low throughput on per portions tile small has high throughput on the per part。

 but low performance on the serial part。😊，And one of the reasons why major companies didn't want to go tile small is you get reduced single threat performance compared to your previous processor。

 right single threat processor， because large processors were there already。

So the idea is very simple， you can kind of guess it based on the context of the lecture。

 have both large and small cores on the same chip。😊，This is performance asymmetry。

So that's what brings us stasesymmetric multi core I'm going to give you some examples and then we're going to take a break。

 but in one incarnation you can provide one large core and many small course。

 this is one example right？You have you car watchs four small cores that make it a large core。

You can do it statically， static is easier， you can do it dynamically and people have actually looked at how to do this dynamically it becomes complex。

 but it's possible to do there's a paper called Morph corere in microcro 2012 if you're interested in that before that there was a paper called core fusion in ECO 2007。

 which are actually very interesting ideas but statically it's easier clearly right you can design a large core statically and maybe multi threadreaded。

Okay， so if you do this， you can exc the CL part using the large core。

 so you get two units in CL code sections， which is the same as lock tile large。

And you actually get 12 plus two units in the parallel code sections， 16， almost oh sorry， 14。

 which is almost 16。And if you actually play tricks on the large core and have multi threadreading。

 you could actually almost get 16。So we didn't play tricks。

 sore going we're not going to assume multi3 in the large core。

 but you could actually assume that and you're going to get the best to both worlds almost。😊。

So basically， if you want to exc serial bottlenecks， whenever you have single threats。

 execute on the large core and whenever you have many threats。😊，Basically。

 schedule them on the small course regardless of your pers。

And then when you get back to a single thread， let's say this is the parallel part。

 this is the serial part， you go back to the large core right that's the idea now if you do this。

 I've already giving you these results actually。So a tile large。

File small and ACMP ACMP gets essentially。The same C performs as a tile large approach and almost the same。

😡，Parallel performance of tile small。As I said， this could be increased to almost 60 with multi threading we're not assuming multi threading in the large if you assume multi threading。

Maybe these can be you could get four units of performance over here。Okay you。

And I think multi three is the right approach actually but we want it to be actually harder on the on the the asymmetric side so if you modify MDds law for an asymmetric multi processoror。

😊，呃。serialial portions execute on the large core， parallel portions executed on both small cores and large cores。

And L is the number of large processor， S is the number of small processor and x is the speed up of a large processor of a small one now this is what you get now1 minus f gets divided by x over here。

Our baseline is a small core of course rate， whereas this gets divided by something more complicated。

Which is the number of small pro times x times L， which is the number of large pro times the speedup that you get。

But if you assume multi thread this needs to be modified a little bit more。

 so now you can actually draw cures with Mda's law， which I'm not going to do。Yeah。Okay。嗯。

So other parts of the code actually can also benefit from a large core， for example。

 critical sections that are contended， parallel states that take longer than others to execute。

 they could be shipped to the large core right if you have a large core and we're going to see that and the general idea that we're going to examine in the rest of the vector after the break is dynamically identify quote portions that cause serialization and execute them on a large core。

😊，So this is a good place to take a break we're going to look at like progressively different ideas starting with a small one which is excing the serial bond only and then do it more dynamically through hardware software code design。

 but when we talk about these it's always good to think about。

We have looked at one way of doing this which is really software has a lot of information。

 provide that information to the hardware， which I believe is the right way of doing it。

 but clearly this is not easy to adapt right whenever you modify both software and hardware you may be able to modify nothing in the end there are other ways of doing it potentially like purely in hardware purely in software people have also looked at after our works but it is a bit hardwriting so we're going to see a lot of ideas so hopefully you'll think maybe more ideas。

😡，But now let's take a break， I'll take questions after the break， let's take a break until 1445。

 16 minutes。And then we'll continue oh from that room or just， oh， okay， I see it。I see that O。😊。

More sequential processing here。H。😊，I see。😊，Is that a big problem？Oh。

Could be depending on the situation right， depending on the workload you're executing。😊，Okay， well。

We have heterogeneity in the rooms Thursdays here， Friday there。Okay。

 so now let's jump into some ideas。I'm going to cover a bunch of readings。

 let's see how much we can cover。😊，But this is the caveats of perism。

 remember we talked about the serial balneck， we're going to start with the serial balnek and I've already given you the idea actually。

 but we're going to actually execute the parallel balnecks as well and we've already covered this slide。

I'm going to start with the first idea， accelerate critical sections。

 this is a hardware software code designed to accelerate critical section execution。😊。

But let me give you something that will motivate this This kind of picture is always good to motivate things。

 even though you may not have exact numbers。You may reason about things right， for example。

 let's take a look at a code that has 12 iterations。

And 33% of instructions are inside a critical section。

 which is only one thread can be in the critical section that's all you need to know to look at this if you execute。

😊，This code in one processor， P equals one， the execution looks like this。

Critical section is the red part。Now， if you parallellyze it in two processors。

You can parallelze the parallel parts， but only one thread can remain in the critical section。

所谓以上的事实我具不记。But you still get pretty good speed up as you consider it。Now。

 if you parallellyzze a little bit more on three processors。This is what you get again。

 parallel portion can be executed in parallel， but red parts cannot be executed in parallel。

Red parts are serialized， as you can see， always。So it gets some more speed up。

But not as much as going from two to three， actually。Now if you execute them four processors。

You get no speed up。And the reason is when you were at three processors， oh， sorry。

When you were at three processors。There was no room for parallelzing the parallel part even more by adding one more processor。

If you look at this critical section， there's always one thread that's executing critical section at any point in time。

 right？And this is an optimistic。Example， meaning when you go from three to four。

 your performance doesn't be great。In many real cases， your performance actually degrades。Because。

Basically， the reason you cannot your performance cannot improve is because you cannot parallellyze the parallel portions because you're limited your boneck by the critical sections as you can see so threads basically weight more here this thread even though it finishes。

At this point。It cannot enter the critical section because the fourth thread that you added is in the critical section。

😊，Same happens over here so you basically have some waiting time that happens in each thread because you're really biic by criticalit sections and this is if you're lucky as I said in most cases。

Your performance actually degrades。And the reason is now you're communicating more across different threads。

 right these whenever you want to enter a critical section， you need to take a look。

Whenever you access the grid section you access some shared data and that needs to be communicated across more processors now。

 and these processors have their own private caches so there is this pingpononging effect that we discussed last time and we're going to discuss more。

So even thiss an idealized case， so basically if your performance is limited by critical sections and if you accelerate critical sections。

 this is what would happen with a single processor， let's assume you have some magic mechanism。😊。

That's x critical section by 2 x。In a single processor you get some performance gain that's good in two processors you get some performance gain that's good in three processors you get some more performance gain and now the realization is that with three processors。

You're not always in the critical section at any point in time。

So there's room for more parallel if you parallellyze more。You get more performance improvement。

 as you can see， and this performance is at least in this cartoonish picture better than three processors。

And you're still not b it so you could actually paralyzze even more so this is a nice intuitive example that shows that yeah I've already shown this what I already said accelerating critical sections actually increases both performance and scalability right scalability to define it more rigorously it's really the number of threads at which your performance saturates becomes maximum。

😊，This could be expressed in terms of number of thread number of amount of area， et cetera。

 as we will see Okay， so hopefully this motates contention for critical sections lead to serial execution of threads in the parallel program portion。

😊，Contenstion for critical sections increases with the number of threats and limit scalables。😊。

This was the data from my SQL I showed you over here right it I'm not going to repeat the same thing but basically this is the reason your speedup starts degrading significantly after I think 16 areas it could be 17 don't quote me on it。

As you keep adding more threads in My SQL， and we're going to get something like this and you kind of already know the idea。

 I think。So basically the case for aymetry is execution time of sequential parts。

 critical sections which we're going to focus on and limiter stages must be short。

 and you can say it's always good to actually when we were doing some of this work。

 some of the comments that we receive us this is programmers responsible programmers should do this。

😊，But it's very difficult for the programmer to do all of this actually， first of all。

 programming is difficult。😊，And then getting the programs correct is difficult getting a single thread perform program high performance is difficult now you want the programmer to get the parallel thread performance。

😊，Hi。And also scalable， keep adding threads and you're going to scale。

And there are many reasons of it for it actually first of all it's difficult right the second is maybe the programmer doesn't know exactly about how to optimize a program right they need to really be domain experts to optimize a program。

😊，For example。Some companies like I'm going to pick on Oracle again。

 some database companies actually hire a lot of programmers。

 some expert programmers who try to minimize these critical things as much as possible and they've been doing this for many decades。

 three， four decades or so。😊，And they're still doing it。

Meaning this is a difficult problem actually even when you have domain knowledge and even if you actually improve the domain knowledge because it's just the nature of communication and nature of synchronization across threats on top of this there's variation and hardware platforms okay you may optimize for this hardware hardware platform but another hardware platform has different kind of caches different kind of synchronization instructions to do the locking etc different kind of processors and then your critical sections become different politics potentially right it's very difficult for programmers to take into account limited resources meaning what should the programmer really be doing it's a good question and on top of this there's a performance divbugging tradeoff yes you can always get more performance。

😊，At the expense or more bugs。And synchronization， this sort of synchronization across threads is one place where。

You're almost guaranteed to get bugs。How many people have done parallelil programming here？Okay。

 how many people never got any bugs？With fer old programming。

 hopefully you're not brave enough to raise your hand， but you can be。

 but it's very difficult basically it's not it's easy to get bugs over here。😊。

Many people have written operating system kernels where they had to really， let's say。

 synchronize across shared resource across different threads， allocate resources。

I recommend thinking about that。Not easy， basically。

So you can always get performance at the expense of more bugs。 Another way of looking at this is。

If you actually have a mechanism that's。provide you。

Better parallel performance underneath the programmer can be more liberal in the sense that they could say okay I'm not going to do aggressive things that will cause bugs but hopefully I'll get better performance right that's the idea over here so you're debugging you alleviate some of the performance debugging problems。

😡，So basically that's why having mechanisms that aid the programmer is much better。

 essentially a mechanism shorten ceonics without requiring programr effort with program effort you can hopefully do better。

 but we should aim for these mechanisms in general。

 this's true for processing in memory right one of the issues we discussed with processing in memory is a programming effort right ideally you would like to minimize the programming effort。

Okay， so basically the idea in this work is to excite serialized code sections by shipping them to powerful cores and asymmetric multi corere processing。

😊，Okay， let's take a look at what this idea looks like。

 hardware and software cooperatively ship critical sections to a large powerful core in an asymmetric multi core architecture。

😊，And the hope is that the large core can execute the critical section as much faster。

And hopefully that reduces serialerization due to contented locks。

It reduces the performance impact of hard to parallellyzze sections。

And hopefully the programmer doesn't need to heavily optimize apparel code。

 you get fewer bugs and improved productivity， so it has higher level benefits source。

And all of this is conditional upon。The large core。

 powerful core executing critical sections is much better。

So now there are actually interesting questions over here can you customize a large core to be much better at critical section execution right we didn't do that as much but I think there's opportunity here also and maybe different types of code should go to different types of cords right so I can actually specialize this we're going to use general purpose course in this but you can actually I think in the ideal incarnation of this you really want to specialize as much as possible to the critical parts of the code。

Maybe non critical parts of the code can be executed in parallel processors that are wimpy。

 but critical parts of the code， those are the parts of the code。

 maybe where you really don to actually accelerate things of it。😊。

Assuming you can determine that so this is the idea essentially you have a large processor and a bunch of small processors and you have a critical section request buffer large processor。

In the extreme version of this idea is dedicated to executing only critical sections and also serial parts basically it's a server processor you send to the server processor things that are critical you can think of it that way and all of these are clients if you think about it and the communication model is kind of like that also。

😊，So basically normally you have an entercritical section。😊，And the leave critical section。

 which entercritical section actually gets the lock and leave critical section releases the lock。

 assuming you're doing locking， but clearly you can do other types of critical sections like Se ofphos。

 etc ceter， and then there's some code in the critical section in this case you're inserting into a priority heap which may take some time depending on the shared data right。

😊，So what we're going to do is processor two。Execcuts this entrance， yes。

 we're going to add an instruction called critical section call to the ISA In at Archit。

And Proster2 sends this critical call section request to the CSRB。

 essentially it's a message saying that I want my critical section to be executed knowing you， right？

CSRB is a critical section request buffer and then at some point processorer one schedule that over here it could be a50q we're going to change that queue later on in this particular incarnations a50q。

And Pro one executes a critical section， and once it's done， it sends a critical section down signal。

😊，And Proor2 can continue。Hopefully that makes sense right just a simple execution model it's very similar to what we've seen in Tester Act。

 for example， right this remote function called。😊，You're doing a remote function call especially for critical sections and you need to provide all the mechanisms to enable this of course so let's take a look at an example of this in the programming model compiler can actually translate everything of course especially if you're programming nicely with libraries to do locking and unlocking etc so this is what's executed in a small core lock you acquire the lock you execute the critical section with some input data that could be generated in a shared in a non-critical section not yeah and then once it's done you unlock and then print the result this one example right。

😊，Now， what small corere does in the Xated critical sections model is。

This is one way of doing it there could be other ways we're going to communicate between small core and the large core through the stack shared memory essentially it's computes a which is the data that's computed in noncritical section。

 it pushes the value input value of the critical section function call onto the stack so that the large corner can can obtain it by doing a pop from the stack and then it basically sends a critical section call request。

😊，For this particular critical section lock X let's say and the critical section starts from target program counter。

 this is the program counter at which the large core should start executing when it decides to start execute executing that critical section so this gets sent over the interconnect you send the X lock which is the critical section ID in other words。

 target PC the stack pointer and the core ID and then this weights in the critical section and request buffer and the large core for some time。

Hopefully not too long。But if your critical sections are content actually it could be too long right if you have a lot of contention for your critical sections。

 everybody can be sending requests to the large core。

 but at some point the large core decides I'm going to execute this critical section。

 it takes it out of the5 Q and it starts executing basically from target PC and target PC code is modified this critical section code is modified such that you acquire the lock。

😊，Just in case because you really need to maintain the semantics of acquiring the lock。

And then it pops the input， so if there are multiple inputs you need to send of course。

 multiple inputs you need to push all of them and you need to pop all of them and then you execute the critical section and then push the result on the stack。

 you release the lock and then execute a critical section return instruction。

 which communicates a critical section down response to the small core that initiated this request。

And then the small core pops the result。Offf the stack and print the result。Looks good， right？

So if you're really executing， if you're really programming nicely。

 this could all be done by the compiler， clearly you could all do this as the programmer as well。

 right？😊，Now the question is can you do this purely in hardware， that's a tough thing to do， I think。

 but potentially doable and people have tried， but one of the issues in hardware is。

You need to have some instructions that are actually directly locking a lot of hardware today actually doesn't have lock instructions necessarily。

 they have they execute a sequenceequel of instructions that do locking。

This is some food forethought basically， how do you identify a critical section basically remains a problem still。

We may talk about that more and later。Essentially later lectures。Okay， so this sounds good， though。

 it's doable clearly。😡，So one of the issues that you run into if you do this sort of thing。

 whenever you decide to execute critical sections on a single cord or a server， let's say。Actually。

 there was some later work that did this purely in software and across different processors。

 which showed results that look kind of similar to what we did in simulation。

one of the issues that you run into is large core can become bottle next。

 right if you send too many requests to the large core。

You can a like now this may be okay if all of those requests are for the same critical section。😡。

For the same luck， lots of presss are trying to acquire the same luck， they should be serialized。

Because they're going to be serialized anyway， right in fact。

 it's better that they're serialized on a large core with large caches because this critical section lock always remains on the large core right this one of the other benefits。

Of executing critical sections in one place， Lock remains on the same place。

 It doesn't get ping pong。Shared data that you're accessing your on the same place。

 it doesn't get ping pong so you actually solve the ping pg problem。

 but you it comes at the expense of false serialization。

Meaning independent critical sections can get sent to the server processor。

 now the problem is what happens if you have independent critical sections？😊，Essentially。

 a critical section B can be waiting for critical Section A to execute。

And these are completely independent if they were executing on their local small processors。

 they would be paralyzed completely。Now we're serializing them， very bad。

One way of handling this is actually there are multiple ways of handling。

 one is doing multi thread on the large core， right？

Meaning you execute critical section call a concurrently with critical section called B by doing multi thread and we do that in some later works that actually alleviates the problem as the downside is。

😊，You're not using the entire large core to accelerate a single critical session right so each of them can be accelerated less。

 but maybe it's better than false serialization so in this work we have another mechanism which keeps track of how often this false serialization happens。

😊，呃。So this is the critical section request buffer， it gets input from small cores。

 it executes the critical section on the large core， and we have some counters。

 saturating counters to keep track of how many times a particular critical section was falsely serialized。

 meaning it had to wait for the large core because some other critical section was executing on the large core。

So you get a critical section called a。😊，Something happens。

 you basically decrement the calendar because this can be executed。

 You get a critical section called a。Seerializing these is fine in fact that's exactly what you want so you get decrement counter now you get a critical section called B unfortunately this gets serialized assuming this's a 5 forq again。

😊，You increment the culture。Now， once your counter is larger than some threshold， large courses。

To the small core， don't send these critical sections to me。And。

Small course stop sending the critical sections， that's one way of eliminating false realizationization right。

😊，You can have a combinational multi threadread plus data of course。O。So I keep that in mind。

So essentially the pluses， if you get hopefully faster critical section execution。

 I'm saying hopefully because the assumption always is that large course faster。😊，But always think。

If your ballneck is really memory， maybe a large core is not that much faster。Thenhan the small car。

It's good to think about it。It's still probably faster， but maybe not that much faster。😡。

If your bottleneck is really computation large core can go really fast of course shared the other benefit I already said shared locks stay in one place so you get better lock local counte it's actually a big benefit and we demonstrate in the paper once you read the paper you will see that some benefit comes from making the critical section faster some other benefit comes from actually keeping the shared locks。

😊，And also share data in the large course caches。 you get better locality。

 better shared data locality listing points， yes。と。O。Could you say again why do you even need locks。

 okay， that's a very good question， basically for correctness purposes。😊，the reason， okay。

 so we acquired a lock over here， essentially maybe we discussed this in a footnote in the paper。

 but there could be well actually actually there are two reasons， one is false utilizationization。😊。

Once you have false serialization， you still need locks to execute so there could be some lock executing here another lock executing here for the same critical section potentially and the other reason is really correctness purposes we don't want to eliminate locks。

😊，Because we cannot maybe guarantee that someone else may not be executing the critical section。

Because there's a large view of the system right there， maybe something。

Some other code that's written by someone else that may be locking， right？Potentially， yes， yes。

 that's right， exactly。But yes， if you're extremely aggressive， you can get it over the Ro ox alsosa。

And that will like you buy you more perform。Okay， so minuses in this particular work we dedicated the large core for critical sections。

 meaning your apparel through it reduces， you may decide not to do that。

 but then you have a problem right， you want to exc critical sections and you're executing some other things。

😊，On the large core， meaning those things contend with the critical section execution Act。

 so that's the reason why we decided to dedicate critical sections。😊。

But we will see that there are other things you can exc in this large core when we go to the next word。

😊，Clearly theres some transfer overhead right you're transferring the critical section you're doing a remote function called。

 you need to send the critical section call and critical section down signals。😊。

We're going to analyze those trade offs a little bit。

 and then there's also some other thing that needs to be transferred。

 which is the threat private data， meaning data that you input to the critical section that is generated outside the critical section。

This is different from shared data， this is that data that's shared。

 this is really the data that you're inputting to the critical section to the computation on the shared data。

😊，This becomes worse meaning it needs to be transferred to the large core。

 and in this particular case we did it to push and pop instructions， as you can see over here。

 there could be other ways you could directly send data into registers， et cetera。

 but that complicates the communication paradigm， but essentially now essentially you're trading off share data locality with private data locality。

If you had executed the critical section in small course。

Private data doesn't need to be transferred anywhere， but share data in our ping pongs。😡，Now。

 the question is which one's worse？And the answer is it depends。

So this's actually an interesting analysis I will show you a bit so these are the performance tradeoffs with accelerated critical sections you have fewer parallel threads because we're dedicating the large core for critical section execution。

 but on the upside we're accelerating critical section right so this is the trade off。😊，え。

And what we see in results， unless you're extremely area constrained。

 exc critical sections offset the loss and throughput。呃。

And there's another benefit over here or trend if you keep increasing the number of cores on chip。

 the fractionional loss and parallel performance decreases because hopefully you're not going to dedicate a huge fraction of your chip to the large core for mainly design constraints it's very difficult to design a large core that occupies a huge area of the chip today as you've seen in all of the pictures of today right today even large cores are a very small fraction because people don't know how to design an extremely large ch that can take advantage of a large fraction of the chip。

So basically increased contention for critical sections also happens as the number of core increases。

 so this tradeoff actually is good with technology scaling。

 it's better to dedicate a large core for critical sections which can accelerate critical sections。

 something is happening here。😊，Okay， the second tradeoff is you sent CS call and CS done signals as opposed to locking and unlocking。

 we're still lacking and unlocking， but we're adding some more overhead essentially okay I should say that we're still doing locking and unlocking them basically get better lock locality right we're adding CS call and CS done that's additional overhead but we also get better lock locality。

😊，呃。And essentially， we avoid pingponing of lux。So there' is clearly trade off over here。

And then let's take a look at the last one， if we get more cash misses for private data because we're communicating that。

😊，Because the private data is actually produced in the small core。

 and it has to be transferred to the large core， right？

But we hopefully get fewer misses for shared data because now assuming you execute all of the critical sections in the same core。

 the share data always remains there it never needs to be communicated somewhere else。😊。

Okay so let's take a look at cash misses for private data usually the cash misses for private data is actually a smaller fraction。

 but not in all cases it depends on how much the programmer optimize the code etc ceter in some cases the programmer has a large critical section and lots of things are private data inside the critical section etc okay so let's take a look at one example over here if you're trying to add for example a node to a heap。

😊，The shared data is the priority heap private data is。Hopefully one elements。

Assuming your shared heap is large。When you add this private data。

 you actually touch a lot of shared data as you can see right in this particular case。

 we touch six shared data nodes。While we touch only one private data node。So in this case。

 keeping these six。In the cash always， as opposed to ping ponging。

 a subset of them is probably better than。😡，Keeping the private data and the cache so this is a case where communicating with private data。

or keeping the share data， the benefits of keeping the share data on the large core outweighs the downsides of communicating the private data。

But of course， this is not always the case if you're adding a huge thing and your share data is small。

 then there could be difference。Okay， so basically cache miss is reduced if share data is great or touch share data。

 the share data that you touch is greater than the private data that you touch。😊，Okay。

 this problem actually can be solved， we're going to see that they're actually interesting things that can happen it's actually becomes a more general problem as we may see depending on the time。

😊，I'm going to talk about that paper actually I really like this paper this is actually applicable to I think a lot of communication that happens across threads so hopefully we'll get to it。

😊，Okay， let's take a look at the performance so yes， please。😡，Yeah。want to chat。Sure屏。

You mean the critical section or not ship the critical section Yeah potentially yes。

 I think if you understand your workload well potentially。😊，Yeah。

 and we are going to kind of see that in the next next work we're going to try to really identify what should we really ship to the large core in this case。

 we blindly ship all of the critical sections except for the false serialization。

Hack let's say that tries to fix the problem， but in the next work we're going to really be more methodical about what should really be shipped there we're going to collect more information about critical sections you could also do more as you will see。

😊，Okay， so let's take a look at the results， so this requires a lot of simulation and Arthur who did this work。

 which is part of his thesis did a lot of simulation， it's not easy simulation in general。😊。

So basically， we're going to compare to these symmetric small core processors。

 an asymmetric multi corere processor that looks like this。We've already discussed this。

 but largecore here in the ACMP， larger corere executes the serial parts of the code。

 but not the critical sections。Sial part is accelerated over here here an accelerated critical sections ACS large core executes both the serial parts because that is actually good as you will see in the results in general。

 and also accelerates the critical sections with the mechanism we discussed。😊，As I said。

 it a simulated developmentotment actually takes a lot of time for this sort of work。

And you can see more in the paper， but these are the large core versus small core parameters we kept the frequencies equal。

 but that doesn't need to be the case， but the main benefits of the large core is essentially。嗯。

Large caches and also large instruction windows and there is an on interconnect that you need to model nice。

Okay， and we have 12 workloads at our critical section in。Okay。

 so let's take a look at these results， so it's always important to classify your workload here。😡。

There are some workloads where the programmer was lazy， let's say。

 or the programmer was a regular programmer。And there are some workloads where the programmer was less lazy。

Meaning here you have cose grain locks and here you have fine grain locks fine grain locks are always harder to do because you run into the problem of debugging etc ce and getting it right Cose grain locks。

 you start your program you write it， you lock everything。

And your entire program is a single critical section。That's the lazi program， or terrible idea。

 of course， right？Even that， you can parallellyze in hard work。Like later probably not today。

 but maybe in later lectures， there's this nice idea of speculative lock collision。

 speculative parallelization， basically the idea is programmer was probably conservative when they actually placed the locks。

So in hardware， let me specly execute the critical section。😊。

It's kind of like run ahead execution when you see a lock。Don't stop。

 checkpoint the architectural state and keep executing。😡，And but not exactly right ahead。

 the goal is not just prefetes， you could also do prefets with Rhead。

 but the goal is to really buffer results。😊，And after you execute the critical section。

 if no one really conflicted with you in the critical section。

Just assume that you executed everything in the critical section that's the idea that's called speculative lock collision it's a beautiful idea I think it adds complexity of speculative execution more than run head execution actually because you need to keep the results buffer etc。

 but even if you have a conservative lock you could actually accelerate。😊，Actually。

 the critical sections does something different and there are actually trade offs between the two。😊。

Okay， so I've given you some other ideas you can see right you can read the micro 2001 paper on that topic speculative aage。

😊，So let's take a look at the results over here here we're going to look at a chip area of 32 small course。

 SCMP symmetric CMP is 32 small core， ACMP is one large and 20 small course basically。

 so you lose some parallel throughput with ACMP of course and also with ACS。But the overall。

Especially on programs that are not optimized， and also I should also say that this' is really important。

😡，We have equal area comparison， but for each。呃，system。

Like the baseline and the when you accelerate the sequential tunnels and then when you exc the critical sections。

 we pick。😊，The number of threads to be the best number of threads for a given system and a given workload。

Meaning， for example， the number of threats that is best in the baseline system may be five for a workload。

 even though you have an area 32。Because the workload is not scalable in the baseline。

 right if you actually whereas the number of threads with ACS could be 10。

 right that's the best threats。Now， if you compare both of them at 0。32。

 meaning if you actually execute 32 threads in each。

The performance improvements of ACS is actually potentially much larger。

But that's not necessarily a fair comparison I mean。

 you could argue it's fair and what's not because now you need to pick the best threat in a given system。

 which may be a difficult problem as later works and previous works showed so this is what we did for fair comparison as much as possible。

😊，And i'm going to show you some scalability results that show that so basically if your workload is not optimized if you have a lot of course grain locks you get a lot of benefits over here so the light blue bar or turquoise bars over here show this excation of the sequential part like the serial bonding so you get a lot of benefit even by excating the sequential part right。

😊，On average， not a lot， but there's some workloads that gain a lot。

And there are some work code that lose slightly because you lose performance on the parallel part。

 and these are actually more parallelizable than others。

But acceleratingctuaating critical sections buys you a lot more performance on top of acceleratingating serial parts。

So that's good hopefully， but you can see that the benefits are lower if if the program has fine grain locks。

 but they're still not negligible， so there are some workloads where you get about 20% for example。

And these are some online transaction processing workloads like that use database type of things。

Okay， so I think I covered a lot of this and I've already already covered this one also。



![](img/208ed3af25019f89320ebb22fd05b2f8_36.png)

Okay， so these are the scalability curve which are also interesting I will not go into a whole lot of detail。

 but essentially you have the number of threads on the x axis and the speed up compared to a single thread single small core version as you can see and you can see that。

Let's take a look at some examples here is one example over here in this workload ACS x in critical sections shift the curve to the right。

Meaning you get much higher performance。And the number of threads at which the performance becomes the highest changes。

 right your scalable team improves。But still， you lose performance as you keep adding more threads。

 right？So the performance comparison points we have is probably here versus here so the best points on each curve that's what I meant earlier okay here there are more interesting threads so here as you can see we improve scalability significantly for example let's take a look at this OLTP workload baseline SCMP symmetric multi core and ACMP look like this look very similar ACMP is slightly better by excing sequential bionics and here performance keeps improving as you can see。

Which is nice。And as I said， the comparison point is from here。To hear as opposed to hear， to hear。

Does that make sense this is a fair versus unfair fair compares？

We could have easily reported a much higher results by saying， okay， everybody executes 32 threads。

 but thats probably is not what you want to do if you actually are to try trying to optimize your program。

 right？Okay， so I could go over this， but essentially scalability team improves in seven workloads over here。

In some cases， these programs are not that improved as you can see。Okay。

So I've already said all of this， so I'm not going to go through this。

 essentially we can improve both performance and scalability by exc critical sections。😊。

And these are critical sections now we're going to generalize the idea because critical sections are only a part of the bottleneck right。

 can we ex all bottlenecks？😊，Or ideally critical paths by executing them on a powerful cord。

 I think in the ideal incarnation of the idea， which is not going to be the next paper。

 next paper is going to move the needle compared to the previous one。

 but it's not going to identify all possible critical paths。😊。

Because I think there are critical ideal you would like to do this for even a single thread program right if you have a single thread。

 you figure out what are my critical path， what is my critical path and maybe accelerate it。😊。

In some specialized core， maybe a large core， maybe a more specialized core。

 it's good to think about that basically。But we're not going to do that for single Ted programs yet。

Okay， so this is a paper， you can read more about it。

Let's talk about generalization unless there are questions。Yes。几到后。是的。All。对。No。The site， yeah。Yeah。

 yeah， that's true。Yeah yeah， I think it's not easy basically。

It's basically it depends on what workloads you're targeting， but these are general purpose scores。

 so they're normally targeting quite general purpose workloads。😡，呃。Essentially。

 I don't have a good answer because I don't think anybody has a good answer on this one。😊。

You run a bunch of normally the way general purpose design happens is you have a target set of workloads。

 which is quite diverse。You run traces， for example， you collect traces from your customers。

 you add your traces that are from benchmarks， for example。

 there could be easily thousands of traces in your trace set or workload set。

And you do some design space exploration based on those traces。You run。

All of those traces and you try to figure out what kind of performance。

 what kind of energy you get and that's very intensive to begin with right you need to simulate things you cannot you cannot really run them on real hardware so people have actually designed simulation clusters。

People use simulation clusters to do this sort of simulation。

And then you still have limited design space exploration in the end。

That's why you need to use some intuition， but here intuition may not help easily also。

So if you look at those pictures， I think Apple had 16 high performance scores versus eight small core。

Sometimes it's just also an area constraints， right？😊，I have enough area， so let me add more。

This also this is also a little bit this sort of data driven exploration is also not necessarily representative of what workloads are going to be executed right because you're looking at past workloads to design architecture for the future。

And the future architecture may be executing completely different workload right parallelization patterns may be different。

 et cetera。 So there's no perfect way。 unfortunately， it's a combination of。😊，呃。

Methodical simulation plus intuition。Plus， some luck。Yeah。

 that could be said of all architectures probably， but some problems are easier， yes。😊，Okay。

 so the next unless there's another question， let's talk about how we accelerate all types of synchronization boonicics and I think we really tried to cover all here and I believe all types of synchronization bionics can be expressed with the framework that I'm going to describe now this is a paper that's called Balneck identification and scheduling。

😊，呃。I've already said a lot of these， essentially any quote segment for which threads content。😊。

Is could be described as a bottlene in a multithed scenario in a single thread scenario that's actually broader right because there's no threat contention right now you talk you talk about critical paths etcter。

 Basically any quote segment that makes some thread weight。

 this is identified as a potential bomb making serial portions clearly。

Everybody else wait because there's nothing thing nobody else only one thread exists。

 this is on the critical path by definition。Critical sections that ensure material exclusion。

 they're likely to be on the critical path if they're contented because they make some walk weight。

 but their severity may depend on how many threads they make wait for how long， right？😊。

Not all critical sections are equal because some critical sections make no one wait right if the critical section gets executed and no one is contending for it。

 sounds great。😊，That's what speculative lock collision exploits right critical section executes。

 no one contends， so you don't need to do any waiting。😊，But actually。

 what specul La exploits as two critical sections execute。😊，The same critical section。

And there's no conflict between them one of them is modifying this part of the tree。

 the other one is modifying this part of the tree， and in the end if you execute both of them concurrently。

😊，You'll get the correct result， right， but the program I needed to be。Conservative。

 because programmer didn't know that， yes。Yes， when we talk about that。😊，Essentially。

 you check whether you get a data conflict if someone requests the data that you've updated or read。

You can take that in a real processor。Be through coherence messages。

That's how they did in that paper。Okay， we can talk more about it when we discuss coherence et okay。

 so that's critical section barriers we've all seen barriers essentially they ensure all threads reach a point before continuing the latest thread arriving is on the critical path of the barrier。

😊，And once you fix that critical path， there could be another latest thread arriving for that。

 so it could actually barriers are interesting also and finally pipeline stages。

 we've seen that also different stages of euperation may execute on different threads。😊。

And slow stage makes other stages weight and that could be that is on the critical path。

 so basically we want to identify those。Court segments。

That are on the critical path in multi threaded programs。There's also one more thing over here。

 these bionics can change over time。😡，So this is a let's say cooked up example that Jose developed to Jose led this work a while ago。

 essentially whenever you come up with a cooked up example you'll find versions of it in real code these things exist code come up with a cooked up example and you'll find some some type of code that exists in real life。

 but in this cooked up example we're going to look at copying data from a full linked list to an empty linked list。

 essentially what we will do is we're going to lock the。😊，List A， which is initially huge。

 populated a lot， youverse traverse the list and remove x from a。And then unlock it。

And then do some computation on x and then lock list B and move data or copy data from B to sorry copy data X that you've updated into B。

Essentially you insert， you do a remote operation from a shared list A and an insertion operation for a sharedless B until a is empty。

So you can see that this is kind of a cooked up example， but it's a nice example also。

 and all of the threads are going to do this。😊，And these are different critical sections clearly。

Now the purpose of this was to show that critical sections change ball exchange over time。

 so this is the time of execution with some input data。

 I think there are maximum 32 threads over here and this is contention number of threads waiting for the critical section blue one versus red one。

As you can see， initially blue one is very contented。

 but as you keep removing things from the blue one。😊。

The contention over here reduces because the size of the thing reduces。And after some point。

 the red one becomes contented， so there's a part where both of them may be contented and red one becomes less contented after some point also because you're adding less stuff。

So as you can see in this example， lock A is the limiter for some time。

 like B is the limiter for some other time， and then there's some area sometime where both of them could be limiters at to different degrees。

Okay， so that's just a cooked up example， here is the real example from MySQL。

 which is actually more complicated we're just looking at two locks over here and 16 threads and we're looking at how many threads are waiting for each of the locks。

😊，And this is a fine grain as you can see， it's millions of cycles。

 you can see that there are some points where the red lock is contended a lot。

 there are some points where the blue lock is contended。

 and there are some points where both of them may be contended to various degrees。Okay。

So the goal is to adapt essentially you cannot say a critical section will be critical for good for long。

 so the key insight here is actually very simple we're going to go to the fundamentals fundamentals what causes thread weighting is not good。

😊，Because thread weighting is probably loss of perils。If a thread weights， that's not good。

 it reduces parallelm and is likely to reduce performance。

And the other intuition is that code causing the most thread weighting is likely on the critical path。

 this is not always the case of course， but this is a heuristic that we're going to use to decide what code to prioritize to accelerate。

You could use different things， of course， as we will see。

 so the key idea here is dynamically identify the bottlenecks that cause the most thread weighting。

And accelerate that in this particular case， we're going to use powerful cores in an asymmetric multi corere processing。

But you could actually do other things， as we will briefly discuss you could。You could， for example。

 increase the frequency of the core that's executing this poly neck。😊。

And if we get to it clear there are benefits of that right。

 so you don you don't move the code somewhere else， but then you lose the benefits on data。

 shared data and shared lock， etc。Basically， you can do other things。

 assuming you identify bottlenecks that cause the most thread weighting， you could do other things。

 keep that in mind。😡，So in this sense， this work is a bit more general framework。

 it's not saying just accelerate every critical section on some other cord。

 it's basically saying identify the bottleneck and do something about it。Okay。

 so how are we going to identify the bals， that's a key question over here。So we're going to do。

 again， a hardware software cooperative approach。Compilr， library， hopefully not the programmer。

 but if they wish so the programmer。😡，Can annotate the ballneck code and we will see what kind of annotations were used and they're going to implement waiting for ballnecks this implementation of weighting will counts essentially associate a counter with each ballneck and that counter will。

Count how many weighting cycles that this smallneck causes for different threads。

And then there will be a binary containing these bi ballneck identification and scheduling instructions。

And in hardware， when that binary gets executed with the annotated code and weighting implementation。

 the hardware will measure the thread weight cycles for each bottleneck。😊，And dynamically。

 figure out which which one they cause the highest thread weight cycles and accelerateerate that。

Okay。So it's a nice framework unfortunately it requires changes to both hardware and software as you can see。

 let's take a look at the software changes。So this is a critical section。

 we try to abstract the away as much as possible， so while you cannot acquire the lock you wait for。

😊，Essentially， we wait by watching an address and then you acquire the lock。Once you're done waiting。

 and then you really locked great。Now we're going to outline this call。

 you don't necessarily have to， but for making things easier， you outline it using a ballalne call。

Essentially， bne coal， we're going to associate a balonic ID with each critical section。

And we're going to。Call the ballneck and then the code remains the same and then we're going to do a return ballneck return sounds nice right this way we can identify we can give an identification for every single bottleneck in a program。

Okay， that's symbol ballic ID。Now we need to do something else， this is not enough bottlealneck call。

 whenever you get to a bottleneck call， now you can say， oh， I'm going to call a bottlealneck。

Do I think it's critical at this point right so this can enable acceleration clearly。

 but where is the input for the， do I think it's critical？😊。

And that will come from the site basically。Butne return of course。

 assuming you exc it now you can actually return the bottleneck， et cetera。

 so those are easy hopefully this is the part where we're going to change。😊，While the。

A thread is waiting for the small Nick， it cannot acquire a lock， it's waiting for BID clearly。😡。

We're going to basically increment a counter in hardware。

 There's a specialized instruction called Bne weight。

While you're waiting for that address to be modified because that's the synchronization that happens。

 you increment the thread weightings vehicles for that particular block。

So now we have changes to the instructions that enables。

 this is used to keep track of waiting cycles and these are used to enable acceleration。Sounds good。

 right？And this simple mechanism can actually be used for not just critical sections。😊。

But also for barriers， this is an example where you have a barrier， a little bit more complicated。

 but again if you look at the code it's not that bad in the paper we have the basic code and then the change code。

 but essentially you have a bone call for the barrier here there's a code running for the barrier this basically everybody executes this code。

 different threads。😊，And when the barrier ends， you do a bottle length， right？呃。

So this is really the parallel portion of the cult here。Now。

 once youre done with the parallel portion， you return and you enter the barrier。

 this is the really waiting point。And if not all the threads are in the barrier。

 you're really waiting。😡，So the thread that is executing still。

Is really exercising his bottlealkck this way you can identify the balkck and the paper discusses more on how to handle barrier。

 I'm not going to talklock more， but you can actually handle。Okay， that's barriers。

 this is pipeline stages， which is also again using this framework， you have a bottleneck call。

 this is really the pipeline processing in a pipeline processing you have an input queue and you have an output queue you check your input queue first。

 get some work。If your input queue is empty。😡，Maybe you're running too fast compared to the previous pipeline stage that's supposed to be feeding you things。

 so you're really waiting for the previous ballonic ID right。Now you do the work。

 assuming you get some work over there， you do the work， which is a parallel part。

And you check whether the output is full， if the output queue is full。

 then you're again probably running far ahead from the。😡，Thing that's waiting the result from me。

Because if it was actually matching your throughput， it wouldn't have a full queue， right？

So basically the next balnek is your balnek， so you're waiting for that balneck now。Clearly。

 you could be waiting for both at different times， right？

So that's the idea this is I think it's a beautiful framework to really mark instructions this way。

 Okay， so now we annotated this let's say let's take a look at what the hardware does。😊。

With this information， the hardware can do all our texture。😊，As I said。

 identification and exploration are independent tasks。😊。

Exation can be accomplished with different ways， you can increase the core frequency voltage the that's of the core that's executing the ballneck that's identified。

😊，You can prioritize that Bne and shared resources as we have seen actually in not thread cluster。

 but parallel application memory scheduling， these works are actually done concurrently。

 so prioritization and shared resources you can prioritize a thread in the memory scheduler that is executing a Bneck for example。

😊，And you can migrate faster course， I could actually do a lot more， I think， but it's not limited。

 you can imagine things， so we're going to migrate faster course。Let's take a look at this。

 how do you measure thread waiting cycles for each bomb？I'm going to give you an example。

 you have two small cores， one large core， we're going to add a bottleneck table。

 we're going to modify things a little bit。😊，The bottlealneck table is going to keep track of how many thread ratinging cycles each barneck has cost。

So small core executes a bialonic weight for a given bialic ID。

The waiter count gets incremented and thread waiting cycles gets counting until the small court staff waiting for that public。

Okay， so you keep counting basically as long as you have a waiter for that bondck。

 you can implement them various ways， it's not that hard。

Now you keep counting now another course starts waiting for the bottleneck， same bottleneck。

 you increment the number of waiters and you keep counting incrementing the thread weighting cycles by twice every cycle。

You could of course quant things et cetera， which the paper does。

 but I'm not going to go into that once a course stops waiting for the bottleneck it's basically notifies the bottleneck table saying I'm not waiting for it anymore so the decrements the waiters count。

And then you go back to counting in a different way and once the other core stops waiting for the ballalneck。

 this gets communicated again through the interconnect to a balneck table。

 which is located somewhere。😊，Closer to the large core in our implementation and then now the number of waiters is zero right。

Now this way you can count the ballonics because you've annotated the code so that you can keep track of the bottleoniccks。

😡，It's nice， it's expensive， I not cheap clearly， but it's doable okay。

 now how do you decide what to accelerate？😊，Now， you assume that you have some thread waitinging counts。

 which may be periodically reset， et cetera， which I'm not going to go and say again。

 but yeah multiple bottlenecks。One of them clearly has caused more thread waiting cycles than the other one。

And small core gets a bne call to 4600， right？The first thing it does is it queries the Salneck table asking should I execute it or should I send it somewhere？

And the ballneck table coordinating， it says basically， oh， this's not an important bottleneck。

 go and execute it yourself right， don't bother me with it， execute locally right？😊。

And then it gets another ballnek this time it's 4700 again it's asked the question。

 should I execute it myself or should I send it somewhere and the ballne cable says this is important。

 let me handle it in the large core。😊，That's the idea and this way of course it's not that easy。

 basically it tells a small court execute remotely and remote execution is very similar text rate critical sections basically you need to execute you need to send the things related to the bond。

😊，Now， similar to critical sections， we have a bottleneck scheduling buffer in the large core。😊。

It gets essentially the Balneck ID program counter that it's should start with。

 a stack pointer because the communication is done again through the stack between the thread private data and shared data in the Balne。

 and also the core ID so that this large core can tell when it's done， you can stop waiting， right？

At some point， this gets scheduled on the large part。

And then largecore executes the bottleneck return， remember that bottleneck return instruction we added。

 which sends a signal。To the core I that's initiated that ballalneck and small core can stop。

呃 waiting。Hopefully， that makes sense。Of course， this bottleneck table becomes a bottleneck itself。

 at least in the communication。 So what we do is we try to。😊，Make the decisions local。

You don't want to go to somewhere else to decide whether you execute locally or remotely。

 so we add essentially cash。Of parts of this biic table。

 whenever the bionic T identifies that a particular bionic ID should be accelerated look remotely。

It sends a message。To all of the acceleration index table saying that this should be accelerated remote。

Meaning the default is local execution unless you find it in your acceleration index tape right that' why you don't need to communicate too much。

 hopefully with the bottleneck table。And that reduces the ballalneck table from becoming a ballalneck by itself itself。

Okay， sounds good hopefully so basically we've discovered we've discussed both of the mechanisms。

 basic mechanisms， thread weight cycles， xing bottlenecks。😊。

But there are also other things that you need to improve the performance and generalality of this in the paper we talk about that。

 I'm not going to talk about these in detail， but dealing with fossilization is still a problem。

There's preemptive acceleration that's important for especially barriers and I'm not going to talk about that。

 barriers need to be more preemptively accelerated。😊，Critical sections。😊，Depending on the history。

 you can excate them later， but barriers while the barriers executing your balonic things are essentially balonic weight cycles are accumulated and there's a thread that you need to determine that's the latest so you need to preemptively get there。

And there's support for multiple large core so in this case we actually added support for a multiple large core so that we can accelerate things multiple bionics in parallel hardware costs in the paper and I'm not going to talk about this in detail again。

 it's not that much everything is off the critical path。

 especially after you design the Bneck table the way with caching using X index tables。😊。

So the 12 storage cost is not a lot， but there's complexity， of course， right？Okay。

 again you have tradeoffs over here， which are very similar to ACS so I will go through this thread quickly now we have faster bottlealneck execution versus fewer repairel threads。

😊，You have better shared data locality versus worst private data locality。

 we're going to solve that problem in the next work and you have benefit of acceleration versus migration las。

Okay， so we've already， I think I should actually mentioned this one also migration latency is usually hidden by waiting。

 meaning you migrate， but then because if something is a ballne， it should wait，😊。

It should not wait unless should not wait if Taalk is contented right。

 basically migration latency is not hidden if you're not going to wait on thealk。😡，Buts。This is bad。

 of course， but this is likely not on the critical path。

And assuming you're doing your accounting correctly， hopefully you have not migrated， right？

So that's the interesting part over here by doing this accounting better。😡。

ACS Xray critical because Xrays everything， right？😊。

Here we basically do some accounting and based on that accounting， we actually。

Decide to migrate and I think overall migration latencies reduce significantly。

So this idea is actually more general we've talked about speculative lock collision right one of the issues with speculative lock collision is deciding。

😊，Whether you want to actually speculatively execute a critical section。In some cases。

 this is a very bad idea。Because the critical sections are going to contend with each other and when the critical sections actually contend with each other。

You run into a situation where you go back and serialize everything， so you have to recover。

So if you can actually identify whether critical sections are actually going to contend with each other with this sort of mechanism。

 you can guide this lock illusion。In a much better way。

 so it can specully execute critical sections in a much better way。 So this in that sense。

 this mechanism is actually a framework that can enable better parallel execution。😊，Okay。

 so we evaluatedd this again using a bunch of workloads。

 these are other workloads that we added to the suite。And again， we have large cores or small cores。

 you can read more about them， these are the comparison points。So asymmetric multi corere。

 we already discussed that it accelerates serial portions and there's accelerated critical sections。

And then there is something else called feedback directed prefetching。

 which is applicable to pipelining， so critical sections accelerated to critical sections was not applicable to pipelining。

😊，And feedback directorive pipelineing here， actually it's a nice idea。

 the idea is actually in software identify which pipeline stage has the lowest throughput。

And if that has the lowest throughput， xray it in a large core。That's the idea。

 it's applicable only to pipeline parallel workloads， not to critical sections。Of course。

 a workload can have both pipeline parallel and critical sections， in that case。

 these ideas are applicable together， of course， right？😊，Okay。

 but we're going to talk about that also later， hopefully。

So this is the performance improvement you would get on these workloads。

 ACS accelerated critical sections and feedback ratefiing by you performance， which is good。

 which is actually similar to what we have seen earlier。

 but maybe we have more improvements in the baseline here。😊，呃。

And if you do bottleneck identification and scheduling， you do better。

And there are some workloads where you don't get a lot of performance so and then there are also workloads where ACS is dominantly applicable versus feedback directed pipeline is dominantly applicable。

So there are a bunch of workloads where limiting bottlenecks change over time。😡。

That we have identified and here this actually provides a lot more improvement。

And here you have barriers where ACS cannot accelerate。What's interesting。Okay。

 these are the results， I' will not go into more detail。

 and it's improved scalability on four of the benchmarks， which is not shown here。😊。

Now there's also more analysis which is actually a very interesting analysis I think it's good to do this sort of analysis。

 we wanted to understand why does it work， meaning we wanted to analyze a fraction of execution time spent on predicted important bionics and this is what this shows。

😊，This is easy to get， this part is easy to get ACS or FTP。😊。

The fraction of execution you can also see this as the。Amount of time。

 the large core is busy doing something。You can see that if you exit only critical sections or pipeline stages。

That fraction is relatively small， especially with critical sections。

 because most of the time there is not something that problem the core is not a core is not in a critical section。

😊，With this， that fraction increases。In general， not always。Meaning we keep the large Cops busy more。

 right？😡，O。What fraction of that is actually critical is I mean one of the reasons we keep the large core busy more because we ship more than critical sections to the large core right not just the critical sections。

 we're more frugal in which critical sections we ship but we also ship other stuff to the large core。

 but you can see that the large core utilization is still not 100% in many cases or not even close to 100% so there could be more than on the large core as you kind see。

😊，Now what fraction of this is actually critical， that's a much harder question to answer。

Because you need to somehow figure out okay you execute something is this really critical is this really on the critical path of a program this analysis is actually very difficult it needs to be an offline analysis and it cannot be a perfect analysis because of the dynamic nature and dynamic changes on the critical path。

 but if you do some sort of analysis that is close enough we define coverage as a fraction of program critical path that is actually identified as well next。

😊，And that increases from 39% to 59%。So it's this green bars， these green bars over here。😡。

So we identify a larger fraction as balnecks， which is probably good because there should be some balneck in the program。

 hopefully。呃。And accuracy is the identified binecks that are on the critical path over total identified boniccks。

Which is basically total identify bottlenecks is this blue bar。😡。

And the green bars fraction is about 72%。With Wallneck identification of scheduling and scheduling。

 we increased coverage while keeping accuracy almost the same。😊，Okay。

 that's the best we could do with the accuracy analysis may not be very easy to do this analysis。

 but basically the takeaway is that。We can identify 60% of the program critical path as B next。

And about 70% of that identification is correct。Which means I were still leaving a bunch of stuff on the table。

 right？You can multiply 60 by 70， you get about 42% right。

Some of the things that we're shipping is identified incorrectly as a program critical path。

So we're wasting resources and some of things we're not even identifying well okay it's good to keep this in mind so we have a bunch or more results。

 so as you have more small course you get better performance because contention increases and loss of parallel through it reduces。



![](img/208ed3af25019f89320ebb22fd05b2f8_38.png)

I'm not go through this if you have more large course。

 that's actually good because you can exc independent ball mixs。😊，Without reducing parallel through。

 but because you normally have enough course for perism and also you can do multi thread。Okay。

So I think we have covered this。Essentially， I think I will probably say this last point over here。

This is a mechanism that gives you fine grain polyonic acceleration with no programmer。

 hopefully no programme effort， if the programmer program has libraries。

 you could actually do all of this in libraries。😊，You could design a library， locking library。

 barrier library， pipeline parallel programming library that the programmer uses。

 and all of these instructions are already compiled， right？That's ideally how it should be。

But if the programmer tries to do a lot of tricks in the low level code， then。Clearly。

 this is not going to work。But if they' are doing tricks in a low little code。

 maybe they can add these tricks also to a low little code， it's good to think about that。

And this gives you a more finer grain ballneck acceleration with hopefully no program effort。Okay。

 I think I've covered， this this is a paper。There is an improvement over this。

 making better exploration decisions。I think I'm not going to cover this。

 I'm going to let you study it on your own， this is utility based exploration the basic idea is to I'll give you the basic idea and then we're going to end early today but I could take questions The basic idea is to identify the utility of exploration。

😊，Here， we。Made an exploration decision based on thread waiting cycles right and then next question is that good？

😡，Because we're using thread weight cycles as a proxy for getting identifying a critical path。

But maybe there's something else， so if you can identify each code segment。

 associate a metric with a code segment。Saying this is the performance improvement I would get if I actually ship this code segment to the large core。

 that's really what you want， right？And this is what we are trying to approximate in this work。

I'm not going to talk about this right now because we've talked a lot a lot。

We may start with this tomorrow， or I may leave it for you to study on your own。

But we're going to continue this lecture tomorrow， any questions？Yes。嗯，Yeah，Yeah。More large course。

 yes。诶。Yeah， I mean these works that's true， but we also evaluated more large course so we basically always said that if you have more area you can also put more large scores。

 yes， so I think in the end if you have area， so when we were doing this work it's like 2000。😊，8，7，8。

 because of multiple rejections of the papers。 The first paper was published 2009。

 It was rejected four times， I think， but basically 2007 and 2012 time frame。 at that point。

 we didn't have that many transistors。😊，Right now， I think because there are so many transistors。

People can afford to put more large course for sure。And also I think examining multi thread。

 because today multi thread is relatively common in large courses。

 maybe not huge levels of multi thread， but two maybe before。

 so examining multi thread together with large courses is useful， I think in these。

Hopefully that answers your question。Today people do it because they can and some work benefit actually。

😊，Yeah。Any other questions， yes？Okay， can you speak up， I cannot hear very well。被告。不是。Okay。

 we've shown examples of this in prior lectures also today， but a critical section is。😊。

A part of code that enables mutual exclusion， meaning if only one thread can be executing that code。

And no other threat。And the main reason to have a critical section is to protect。

Share data to do updates to share data accurately。Yes。嗯。操对题。嗯，嗯。对。法律个回。That's right。Yeah。Yes。不。我。不。

Actual instructions for which other。So what we ship is， let me go back， I'm going to go very quickly。

We actually ship the actual instructions that make threads weight。So maybe that was not clear。

 but basically you can see that Boneck coal， this is really the cold runninging for the barrier。

 meaning the parallel part of the code。Does that make sense， hopefully that's clarifies it。

 but barrier instructions are really here， you enter the barrier。

And this is where you actually do the synchronization。

But this is really the parallel part of the code。That's right that sharp that part assuming this ballneck is identified as a。

Bottleneck， that starts getting shipped。To the large core， the parallel part so in that sense。

 ballaloniccks barriers are a bit different。But also a pipeline studies are also a bit different because you also ship the large part to the pipeline。

Essentialial in critical sections， the critical section gets shipped in various years。

 the parallel parts。😊，Until the barrier gets shipped。And in pipeline stages。

 the code in the pipeline part gets shipped。Yeah， but barriers are a bit tricky that I didn't want to go into there's also some preemptive acceleration that you need to do because what happens you already entered the barrier。

😊，And you want to。Essentially。And you get identified as a threat right that is Baldnik。

 what do you do in that case？You're running on the smaller core， so I let you think about that。

 so you need some more software modifications to indicate like which threads are running behind。W。

Yeah， or you need higher level software contractss。

 meaning this is the work that's assigned to me and this is the amount of work that I've accomplished。

And that's a measure of progress basically you need a measure of progress for threats。Yeah。

Varries are interesting。Okay， any other questions？I want it to end early and will end a bit earlier okay。

 I'll see you tomorrow so just to jog your mind， we covered heterogeneity yesterday。

 we're going to cover more of that。😊，But our focus will be a bit on Balneck acceleration。

 these are some of the readings that we were covering。

And we were talking about asymmetric multicore and these are some papers we covered so we started with accelerating critical sections we actually started accelerating serial bottlealnecks and put them on a large core which made things faster and then we actually critical sections kind of blindly put them on a large core which made things faster and then we kept asking the question can we generalize this to all types of synchronization balnecks in multicore in multithd applications and we came up with a solution balneck identification and scheduling and that made things faster for different types of bnecks as we have discussed yesterday and that was the paper and we also asked the question yesterday at the very end can we make better acceleration decisions and I mentioned very quickly that you could actually take into account utility I will not go into detail over here but I will show you something that we briefly discussed yesterday so we were talking about bottlenecks right this is a parallel program a parallel program may look like this。

😊，In barriers， you may have different critical sections that look like this。

 the red parts are critical sections， this is one way of one type of program you may not you don't have to have barriers also of course。

 but here the critical path goes through the critical sections as you can see。😊。

And you can accelerate them， you can accelerate them better with a bottleneck identification and scheduling as we've discussed and then there's another bottleneck which is really the。

😊，Barrier over here。And the last thread reaching the barrier causes a problem and if you actually improve just that last thread a little bit。

 if you identify too late， your improvements may not be very high。

 you kind of discussed this yesterday。So these are essentially different polyoniccks。

So we've also discussed actually here you can see that bottlenecks are combined。

 you have some critical sections and then you have a barrier at the end。

 so this last thread can be accelerated and also critical sections can be accelerated together with it using the Boneck identification S so we've discussed all of this yesterday。

 both of them can be accelerated。😊，Now we've discussed also of this， but we didn't go into a lot。

 I will illustrate it a little bit， there's actually more potential if you look into this sort of application。

 maybe get rid of the critical sections， you have a box synchronous parallel program like we've discussed yesterday。

😊，And。If you know how much work， how much progress is expected from each thread。

 you can kind of mark that progress and it can identify a potential vne much earlier。

 this is called lagging threads。😡，It may be difficult to do。

 it really depends on whether you can correctly identify how much progress has been made by a given threat。

😡，For example， if you can somehow magically identify that processor two made only 30% progress in its task。

 whereas some other processors have made more progress。

 maybe you predict that thread too that's executing on Pro two is actually the orbitbalment。

And you can somehow accelerate it， well， if you know how to accelerate right。

 you can ship that to the large core， for example， right？😊。

So this is something that is discussed in the papers， but I'm not going to talk about that in detail。

 but you can also identify lagging threads essentially。

 so that you can optimize this execution until the barrier much more nicely until something really becomes a limiting vneck。

 does that make sense？😊，It gets more progress。😡，Determination， right？Okay。

 so the question of course becomes there may be many many of these things that happen at the same time in a program do you accelerate the ballneck or do you accelerate the lagging thread right and in a program that kind of looks like this you can have both of them you may have ballnecks in critical sections and you may actually identify a lagging thread also in this case they're probably the same but in some other cases they may not be exactly the same right。

😡，So that's one question so things become more complicated and then things become even more complicated if you have multiple applications right which application do you accelerate so far we have not talked about multiple applications in this polyonic accelerating lectures even though we had talked about them earlier when we talked about resource sharing a lot。

😊，Now we're going to kind of combine both， although I'm not going to go into a lot of detail over here。

 basically you may have two applications that look like this。

 one of them may have critical sections of Balneck another may have a lagging thread or a barrier as a Balneck then basically you need to make a better decision than what we have done before actually we didn't have a mechanism for making a decision before who uses a large core becomes interesting if there are multiple large cores of course maybe you send two things to different large course。

 but then as applications increases the number of applications that may be demanding a large core maybe more than the number of large coreds that you have。

😊，So in the end， acceleration decisions， better acceleration decisions probably need to consider both。

😊，The criticality of a code segment， how important that code segment is and how much speed up can you get by accelerating that code segment both of these are important if the code segment is not critical for performance maybe accelerating that is not going to buy you much if the code segment would not get performance higher performance if it gets shipped to a large core then maybe its not worth accelerating that much right so this paper takes a methodical approach for both bnecks different Bnecks that we've examined plus lagging threads for any running application I will give you the basic idea and I like this approach actually it's a very methodical approach I believe this sort of approach needs to be applied for other things in later works we applied it to hybrid memory management basically we developed a utility-based hybrid memory management technique that considers utility of moving a page from slow memory to fast memory in terms of how much benefit you would get so we're going to do something similar over here basically our goal is to identify performance。

😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_40.png)

Bnes or lagging threads from any running application and accelerate them on large core of an asymmetrictic multi corere processor。

 but of course， you can add different methods for acceleration as we discussed yesterday。😊。

And this paper introduced a utility of acceleration metrics that combines speedup and criticality of each code segment。

 I'm not going to tell you exactly how this is computed。

 otherwise we would take a long lecture on a single paper which I don't want to do today because we have a lot of other fundamental things to cover but basically the basic idea is it breaks down things in an easier to compute way because this utility of acceleration may not be directly easily computable but pieces of it may be computable。

 essentially we define the utility of accelerating code segment C of the length T。😊。

I want an application of length large T as。A combination of these three things。

Whi kind of look funny right， but basically if you really understand what's going on。

 this is the local speed up that you would get by accelerating that segment on a large core。😊。

This is the fraction of execution time that's spent on the segment。

 the importance of the segment for the application。

And this is the global criticality of a segment essentially。

 which is a more global measure of what's going on in the machine。😊。

And there are different ways of estimating each of these， which I'm not going to go into。

 but I like this methodical approach and if you do that。Basically。

 there are two things that this paper does， it identifies balnecks。

 it selects a set of highest utility bottlenecks， it identifies a lagging threadsre using a different mechanism。

 it balneck identification is done exactly like we did with bottleneck identification and scheduling lagging threads adds a little bit more sophistication because you need to really understand how much work is assigned to each thread and how much progress each thread is made based on that amount of work which may not be completely accurate。

And once you understand once you have a set of high utility balnes and high utility lagging threads。

 there is a coordination mechanism that decides which one to actually send to the large core。

 assuming you have a single large core， if you have multiple large cords。

 the problem becomes a little bit different。😊，But again。

 you can still find out which ones are the highest utility bottlenecks and lagging threads and then decide how many cores to use for that。

Does that make sense， I wanted to cover this yesterday I said maybe I shouldn't cover this。

 but I had to cover it because this is really the state of the art and on identifying。😊。

Did I do something。On identifying Vnecks and also it's a methodical approach right it's a more methodical approach to understand the important benefit that you will gain from acceleration。

😊，And the results are actually reasonably good， these are the comparison points， essentially。😊。

There's a multi multi program aware bottleneck identification and scheduling that's the red bar that's what you've seen yesterday plus some multiapplication awareness and there's another work thats that does performance impact estimation that's around the same time and compared to both of those approaches you get higher benefit in most applications this is an S curve as you can see these are about 55 workloads over here and usually whenever you actually evaluate a mechanism and compared to some baseline in this case。

嗯。Actually， I don't remember about the baselines， but I believe it's ACMP in this case。

 it maybe be ACS I'm not sure don't quote me on it it's in the paper probably it's ACMP。😊。

you see that some applications actually lose performance and some applications gain performance and usually this is the curve you get it's kind of like an S curve that's why it's called an S curve actually the curve looks like an S and you can see that overall doing utility based exploration provides better performance but not in all cases。

 so there's still room for improvement as you can see。Excess。

Okay so I think the sort of utility-based metrics are interesting and important to use people have applied this sort of utility to cash partitioning in fact a paper won the best test of time award at micro this year it's called utility-based cash partitioning in past lectures when we actually talk about caches we will talk about it but we don't have lectures on cash is probably this time but if you're interested you can look at that also and later works also try to understand the utility of different decisions so if you can somehow figure out the utility or performance benefit of making a decision and compare it to performance benefit of making other decisions you can actually make much more principal decisions I think the question is how easy it is。

😊，This clearly is much more complicated than thread waiting cycles。

 right thread waiting cycle was easy。😊，It's relatively easy to compute once you have the mechanisms in place to actually keep track of them in this case you need to keep track of a whole lot more。

And that's true for any kind of utility basedase metrics if you look at utility basedase cache partitioning there's additional hardware that you need to add that's more significant than keeping track of how much we use you've had in a cache line。

 for example， if you look at utility basedase hybrid memory management。

 which is also another paper in 2017 that also adds a lot more hardware。😊，Okay。So the question is。

 of course， always， can we do better？😡，But before that， maybe any questions on this？Okay。

 now we're going to tackle another issue， which is actually something that had been bothering us while we were doing a lot of this work and the bothering part is really this private data locality that we discussed yesterday。

 right？😊，What we do when we accelerate a code section is we move we keep the shared data and shared locks in the same cacheh because you accelerate that at least important code sections on the large core。

 this is good so improve shared data locality but this comes at the expense of private data locality because now you need to transfer things that are produced by a thread locally and then consumed by this critical section or Bneck on the large core from the small core to the large core。

So that's the issue over here and this paper develops a mechanism for handling this nicely。

 I would say， which I think is actually a more general mechanism that we should think about in general。

😊，Because if you can keep the shared data in a single place and send the operations that work on the shared data to that place。

 you've solved that shared data locality problem as much now your problem really becomes your bone really becomes the private data and I will show you some examples of that。

😡，And I think there should be more improvement in distraction also。

So this's actually a very general problem so I'm going to generalize the problem even more。

 this applies I think also to single thread applications multith application。

 any application in the end， so I'm going to introduce something that we call stage execution model and I think the goal in essentially parallelism is to speed up a program by dividing it up into pieces。

😊，And the idea usually is you split a program code into segments。

 you may call it many different things threads， tasks。😡，Dynaically form tasks etc。

 for critical sections， but we were going to call it segments in this particular case to be general and your goal is to run each segment on the core best suited to run it right and we've kind of done that in earlier works。

😊，And one way of doing this is actually to have each course to be assigned a work queue storing segments to be run。

This doesn't have to be the case， but we're going to kind of assume that you don't have to assume that in the end。

The benefits you get as we have seen in earlier works is you can accelerate segments or critical paths using specialized or heterogeneous units that's what we've seen in the last lecture clearly you exploit inter segmentegment parallelism even if you don't ship it to a large core。

 the stage execution model segmenting your program why your parallelism across different cores right that's the classical multi threadreading。

😊，呃。And if you actually try to run each segment， if you actually partition your program nicely。

 says that segments that operate on the same data are scheduled onto the same core。

 you can improve the locality of within segment data。😡。

And that's what we get with putting critical sections that operate on the same share data to a large core。

 right？So we can get a lot of benefits which is nice。

 this is actually basically if you look at these benefits these are very fundamental concepts going from bottom to top。

 you get locality， you get parallelism， you get heterogeneity towards specialization。😊。

Now there are examples of this clearly we've discussed a lot of examples。

 multifiing is a very general example of it， but exc critical sections。

 bionic identification scheduling， pipeline parallelism， producer consumer that we've discussed。😊。

Other task parallels and models that these are old slides so people have been using interesting task parallel models。

 they're still use actually， to parallelze workloads and special purpose core on functional units actually can be thought about it this way also because if you think about a single program。

A functional specialized functional unit is really executing a segment of the program。呃1。Okay。

 maybe core should be more generalized also on a functional unit that specialized for the execution of it right so if you think about it this model can be broken down into even smaller pieces than cores we're not going to do that in this。

 but I think it's good to think about that。😡，Okay， so let's take a look at the stage execution model you have assuming you start with a single program。

 I'm just showing you the loads and stores。😊，You split or someone splits the code into segments。

 it could be the programmer， it could be the compile， it could be the hardware。

Assume that programmer has done it Now you have segment S or S1 S2。

And they communicate with each other and maybe you segment two or communicates on the same type of data right。

 you can think of it that way some similar array， and then you communicate something to segment one and then something segment two。

And then you assign instance of segment zero to a core， instance of segment one to another core。

 instance of segment two to another core。And then you hope you can hopefully exploit intra segmenteg parallelism。

 right？So this is one we have spawning segments when you execute segment zero。

When you get to the end， maybe you spawn segment one on corere1， you spawn segment two on corere 2。

It's going to be very similar to ACS very soon right。

 but the pipeline parallelism is also kind of like this。

 maybe you don't necessarily have a spawn instruction， right？Okay。

 so let's take a look at two examples over here actually critical sections。

 the idea here is to ship critical sections to a large core asymmetric CMP multi corere processor。

 you can think of segment C or as non critical section and segment one as critical section right？😊。

Any critical section is segment one， any non critical section of segments C， you can further。

Classify different critical sections， of course， right？呃。But this is the general idea。

So the benefit you get is clearly a faster execution of critical section， reduce serialization。

 and improve lock and share data locality as we have discussed。😊。

Produc your consumer pipeline parallel， we've also seen it。

 but to a lesser extent perhaps and we've seen the idea multiple times before。

 you split a loop iteration into multiple pipeline stages where one stage consumes data produced by the previous stage。

And each stage runss on a different core and usually in these cases a stage has a set of data that it operates on。

 so it's really exploiting locality in this case segment n is really stage n。😊。

So you can have millions of segments potentially assuming you can do that parallelzization nice。Okay。

 the benefit is really stage level parallelism now。

 and you also get better locality because you're executing hopefully each stage is operating on some shared data。

😡，That doesn't have to be the case， of course you may not get better locality。

 but you can still get good perils this way。So you get faster execution so the problem with all of these models is locality of inter segmenteg data that we have discussed i'm going to show it a little bit more rigorously。

 essentially if these stages execute on different cores。😊。

When stage one requires data that's produced by a prior stage。😡，It essentially gets the cashs。

And this cache miss as we have discussed in earlier lecture is a communication Miss right it's really or coherence myth as we will see coherence later on。

 so you don't get rid of these cache miss by making caches bigger。😊。

There's no way you cannot manage the cash better。You need to do something else about it。

 you need to be more proactive about it。😡，The reason it gets to cachem is because this other state is producing that data。

And when this stage。Start executing the load it will detect that it will get a cache miss and it will send a coherence request to the cache that houses the latest value of that y makes sense right so we're going to see coherence methods later on so keep that in mind。

😊，え。Okay， so as stage two executes， it's load Z， it will also get a cache miss because this is really a communication miss。

 the data is produced by a prior stage。😡，In this case， it's nicely produced by stage one。

But it doesn't have to be。 it could be produced by some other stage also， right， maybe stage -1。

 It's not in the slide。 Okay， basically。In accelerated critical sections， as an example。

 critical section incurs a cashmist when it touches data that's produced in the non critical section。

 right thread private data， you've seen that。😊，In producer consumer pipeline parallelism。

 we never explicitly said that， but a stage incurs a cachem when it touches data produced by the previous stage。

😡，And performance of stage execution is limited by interegment cache misses in the end。

 and we have some analysis of this in the paper， take this with a grain of salt these with small core results。

 essentially if you eliminate all interegment cache misses， you can get significant performance。😡。

We're going to get very close to that performance， but this problem actually becomes bigger as you scale up the number of cores as you make things more finer grain。

 that's why I say don't get stuck on these small numbers over here 10% to 20% becomes much bigger as the number of cores increases and as you want to parallellyze on finer grain。

Okay， so let me define some terminology I'm going to give you a mechanism to do this。

 but this is just one mechanism there could be other mechanisms that people develop and again I will also ask you to think about we're going to develop a hardware software code design method。

😡，But I believe actually this can be done purely in hardware in a nice way as well。

 maybe purely in software that's very tough， I think。

 but purely in hardware is easier and maybe there are other mechanisms。

So let's define some terminology， so I'm going to define inter segmentegment data as cache block。

 we're going to still operate on cache block grand laity since things operate on cache block grand la today。

 but maybe if you go into processing and memory we should not be thinking of cache blocks right it's good to let's say distract some of these concepts as we go into different environments。

😡，But we are still procentric in this， it's interegment data is a cache block that's written by one segment and produced by the next segment。

😊，So clearly， cash blocks that house address Y and address C are interegment data。And ideally。

 we would like to identify them。And。Do something about them such that the processors that need them don't get a cash miss。

😡，那是第二点。Okay， we also identify define a generator instruction as the last instruction to write to an inter segmenteg cache block in a segment。

就。Clearly why？Is an Y is part of an interegment cache block and it's generator instruction。

In this segment is the store instruction rate。😡，And Z is also an inter segmentegment cache block and its generated in instruction is the store instruction。

Now， there could be multiple generator instructions。

 which makes things more interesting and complicated。Because of control flow programs， right。

 you may have if and health structures and if。Part of the program can produce。

One data with one store instruction and else can produce another data with another store instruction clearly when you're executing the program。

 only one of them will be executed。😡，So because based on the branch you've taken， right。

 but there could be multiple generator instructions。Makes sense。

And that's going to be part of the inaccuracy of the mechanism that we're going to discuss， so okay。

 yes。Ex one， right。Yeah。And that history requires that case。He is not the last instruction。

So that's fine basically the definition of the generator instruction is it's the last instruction to write to a particular cache block not the last instruction to execute so in this case it happens that these are also the last instructions but it could be somewhere in the middle yeah that's right exactly we're going identify these generator instructions and you can identify these two data flowl in a compiler。

😊，Okay。Yes， maybe the figure should be nicer so that's the generated instructions is also not the last instructions but。

Okay， so basically this work makes a key observation that the set of generator instructions is stable over execution time and across input sets。

 basically the generator instructions that generate these values are producer instructions。

 you can also think of them that way， and then they're consuming the instructions on other segments。

😊，And if you can somehow identify these generator instructions。

What you can do and we're going to identify this in software actually。

 but you could do this in hardware also I think in hardware you can record the cache blocks produced by the generator instructions。

And it can proactively send such cash blockss to the next segment's core before initiating the next segment。

And that's the idea over here。And this the idea that's discussed in this paper again。

 I would like to blur the hardware software boundary here earlier。

 I said maybe you cannot do this on software， maybe today's architectures yes。

 it's difficult to do it in software but you could potentially think about recording cache blocks produced by generated instructions and software。

Assuming you have a hardware buffer that's visible to the software and you can have a push instruction。

😊，That basically pushes。From that buffer to some other core that's executing the next segment that needs that。

 so you could actually imagine a programming model assisted by hardware。😡。

That could enable the purely software， assuming that hardware is already in place。😡。

In current hardware， you don't have that， unfortunately。You could also think about this as。

A fundamental principle is really passing。The data to another place right it's kind of like you're passing the message in a sense right well that's not maybe that's not a good analogy you're you're really passing the data you're really pushing the data to some other place as opposed to pulling the data。

So existing models of execution usually is based on pulling the data right the program basically says load store load store stored is actually kind of pushing the data。

 but not to another processor usually to memory now actually if you have mechanisms for communication that push the data from one processor to another processor then you can actually enable a lot of this in software as well。

Which is very interesting。Okay， I kind of got a ahead of myself。

 but let's take a look at the mechanism I think I gave you the basic idea so it's going to be very easy from this point。

 so compiler profiler and hopefully not the programmer， but again the programmer can if they want to。

😊，Identify these generator instructions and insert marshallial instructions。

 we're going to talk about what that is， marshall instructions is basically pushing the data to the other core。

😊，That is going to need the data。You generate a binary containing generator prefixes and martial instructions and hardware。

 when it sees these instructions and prefixes， it records generator produced addresses。

And when it sees a marshaial instruction， marshahals are recorded blocks to the next core。

Okay so there needs to be some destinations etcter there are some interesting issues over here that I may gloss over but you can ask questions okay let's take a look at how the compiler can do this this can be done exactly actually it don't need to be profiling but we did profiling in this particular case you can exactly figure out which instructions are actually generator instructions in the binary by doing static analysis assuming you can disembiguate addresses that may not be always the case depending on the programming language and。

呃。Mem access semantics that you have Okay， so in this case， for example， if you profile the program。

 you will find out that。This load Y touches some data that's produced by a prior。😡。

Store and clearly this is inter segmentegment data you can identify inter segmentegment data easily。

And you can mark this last store as a generator instruction， not the store。

 right in this particular case。😡，You can mark both of them。

 but then you may be sending some useless data unnecessarily。😡，Okay。

So assuming you' identify the generator instructions。

 then you can insert marshaial instructions and marshall instruction needs to specifyify when to send。

😡，The existence of the martial instruction basically says this is the time to send the data。

 so I can actually put it in an appropriate place and also it specifies where to send the data in this case。

 core one。😊，This needs to be some virtualized idea of the core。

 it cannot be physical otherwise program is really using physical。

Assignment onto the course so there are issues like this which needs to be taken into account。

But you produce a martial instruction。 Okay， this doesn't have to be the last instruction。 Also。

 again， it could be somewhere in the middle。 In fact。

 it's better if you can schedule it much earlier， right， because。If it's the last instruction。

 the segment is ending and the other segment is probably going to start very soon and you're not going to overlap a lot of latency probably。

😡，Okay。So that's the idea so clearly the spans across the stack in this particular implementation the profiler of the compiler needs to identify generators and insert marshaial instructions。

 the ISA needs to change also and you need to have a generator prefix and need to add some push instructions I like calling them on push instructions also but marshall instructions and as I said library and hardware needs to change such that you can bind the next segment ID to a physical core。

😊，So that the programmer doesn't need to know which core a particular segment is executing it。

So there's some hardware analysis that I will not go into a lot of detail。

 but we're going to use this marshall buffer which stores physical address of cash blocks to be marshaled you're going to see an example of this and we see that you don't need a whole lot of entries for this but in some cases you do so there are some communication patterns and programs where you may need more than 16 entries and that's where we're not going to get a lot of performance but if you increase the size you're going to get a lot more performance。

Clearly， you need to execute the new things， you also need to have the ability to push data into another cache。

 this is a part that is not exposed to programmers as much today。😊，In many ISAs。Okay。

 so theyre advanced and disadvantages one is hopefully you get timely data transfer。

 so you can think of it as a prefeting mechanism also， right？😊，Except prefeting is not done by。

The core that needs the data， prefeting is really done by the core that produces the data。😡。

Prodducer induced prefetch in a sense， right you can think of it that way。

I still like calling it producer induced push of data somewhere else。So basically。

 you're pushing the data to a core before the core needs it。

Another advantage is you can mars any arbitrary sequence of lines。

 so we actually looked at ways of doing this with pattern identification， so for example。

 if you know which cache blocks are going to be touched you can record them for example。

 and you can replay them kind of like a memorizing prefeure but in this case we're really executing the generator instruction and then sending the data。

😊，So it's more arbitrary it's more general and it actually has lower hardware costs。

 so essentially there's no need for hardware to find the generator instructions。

 but as I said that has a downside also now you need to modify the software。😡。

So it may be actually better to have a hardware approach completely。😡，That way。

 you don't need to modify a lot of things on software， right？

I don't think it's that nice to keep adding hardware for everything。

 but there are some realistic reasons why you may want to just modify the hardware because now you don't modify anything else in the system。

 right？Okay， there are clearly disadvantages like profiling and ISA support and you're not always accurate because what we do is profiling based identification。

 but even if you don't do a profile- based identification may not be as accurate depending on the path you've taken so a generator said is really conservative in our case and if you push some data that's not needed by an next score。

 you essentially cause pollution。😊，And the cache of that core， right？

And you also waste bandwidth on interconnect， clearly， this is not good for performance or energy。

 but we find out that this's not a huge problem because the number of inter segmentsegments blocks that are communicated are actually usually small。

 yes。😊，要去。Yeah。嗯嗯。嗯，Offline yeah， profiling is offline major yes， that's right。

 yes there are particular approach offline you could of course， have an online profile as well。

 but that's not what we examined。I think online software profiling。It's probably a bit heavy handed。

 but online hardware profiling， if you do this profiling in hardware， it's probably easier to do。

 and it's probably better for perform。Because you don't have the overhead of software profiling things。

嗯，还没。Yes， exactly something like that essential， yes。Yeah。

Those are all interesting things and just in time compile is also employed。

 but if you keep adding more and more stuff at a fine grain to just in time compiles。

 it may be expensive。That's why we went with static profiling here okay。

 but of course you always have the downside of profiling whenever you profile as we have discussed in earlier lectures like inputs that representatives okay so let me give you an example of how this works very quickly these are the binaries that are generated for two segments over here noncritical and critical。

😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_42.png)

Ass an example of ACS， we add the marshall buffer to small course。When。

The non critical segment that's executing on that small core gets to a generator instruction。

It puts the address。😡，of that instruction into the marshall buffer and and there could be multiple of these that are put into the marshall buffer when it gets to SES call instruction。

 which is critical section called for a particular critical section。It basically。There's hardware。

 special hardware， as this instruction executes， there's special hardware that goes through the marshall buffer。

 takes each address， accesses the small course cache。

 and takes the data and sends address and data to the large course cache。

 L2 or L1 depending on the analysis that you've done。Well。

 depending on which which one which one you want to push the data in write。

 ideally album actually in this case， but we're showing L2 is over here。😊，Okay。

 and hopefully when the critical section starts executing on the large core。😊。

It gets a cachet when it does a load white。It all depends on， of course the distance。

 but you start the access earlier。😡，And this critical section may not start executing right away because it may be delayed。

😊，Especially if it's a contented critical section， there will be other instances of the critical section that's executing on the large core。

 so the timeliness of this prefeure actually becomes better。😊。

Because of contention and ideally you want to send the contented critical sections to the large core。

 right？😊，What you're trying to do by bottleneck acceleration is actually going well nicely with what you're trying to do by pushing the data。

😡。

![](img/208ed3af25019f89320ebb22fd05b2f8_44.png)

Okay。So we evaluated this again using similar workloads to ACS and we see this improves the performance of ACS significantly。

 some workloads better， some workloads it doesn't matter， maybe it's not a big problem。

 but clearly on workloads where it matters you can get the performance benefits and ideal is actually the blue one so we get very close to ideal。

😊，So that's almost perfect mechanism， which is nice。Yes。我这还你们小。嗯。😊，Yes， but you can identify that。

 right？Maybe when you get a martial instruction， so one part that I omitted was basically when you get a marshaial instruction。

 you need to do this translation from the virtual core I to the physical core ID。😡。

It can easily identify whether you're in the same physical court。That's a good point， I think。

You want to avoid extra pushes to your own cash， right？Okay。



![](img/208ed3af25019f89320ebb22fd05b2f8_46.png)

Okay， so let's take a look at an example with pipeline parallelism also because this it's actually more beneficial with pipeline parallelism there tends to be more communication pipeline parallel workloads because the workload itself actually is consisting of these pipelines right whereas critical sections may not be the major thing in even critical section intensive workloads here we essentially add marhal buffers to the small course。

😊，And again， when segment zero gets to a generator instruction， it stores the address over here。

And when it gets to a marshaial instruction， it marshals。It access its own cache。

 gets the data associated with address Y， and marshals the data to the next to the corresponding course caches。

And hopefully again， when this segment gets to load， it gets to the instruction that's loading y。

 it will get a cache hit or at least reduce access latency。



![](img/208ed3af25019f89320ebb22fd05b2f8_48.png)

Okay， we validated this again with the same workloads that we did well。

 or or pipeline parallel workloads， and you get more benefit over here。And here。

 because there is more communication a 16 anti buffer doesn't work for some workloads as much。

 so you still get very close to ideal as you can see。

 but you can actually improve this by adding a bigger marshall buffer for workloads that need that larger marshall buffers because there is more communication that happens across segments。

😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_50.png)

Which isn't just。So there's more analysis in the paper that I will not get into but you can see that the coverage is actually pretty high over here you can cover almost all misses accuracy is relatively low because of the profiling so you could do better over here and timelineless is usually quite good as you can see whenever you want to access the data that's coming from interegment data you get a cachet essentially。

😊，呃。And medium accuracy could be bad for performance， but we see that that's not the case usually。

 but it's bad for energy， of course， right， whenever you're not accurate。

 you're transferring something that's wasting energy on the interconnect。O。Any questions？

I think there's more work to be done in this area， don't be fooled by the close to ideal results there are many different types of applications that are communicating I think integrating this in a general purpose way is actually very important。

😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_52.png)

So okay， yes。能。The means。

![](img/208ed3af25019f89320ebb22fd05b2f8_54.png)

Ash this is already issued。That's right， toos。Exactly， usually it's well。

 actually it could be it's still in flight or it's not in flight yet， yeah。

So we didn't break it down that much， at least in this particular picture。

 it means basically whenever you issue the access， the data is not in the cache。😊。

It could be mostly done。对。improve theThat's right making sure that you that's right exactly yeah and also there's scope to improve accuracy and also there are different workloads or we examined the set of workloads that。

But then some other workloads may have much more complex communication patterns right。

 and that exists actually， I know that's very well。😊，Yeah。我成先。



![](img/208ed3af25019f89320ebb22fd05b2f8_56.png)

Yeah， so in this case， it's I think it's a ring base network， yeah， it's a bidirectional ring。

 so enthusiasm is yes。But it's not as much as what you would support with some other network。

As we will see in the interconnection Network lecture， yeah。Okay。Okay。

 so we actually have interesting scaling results in the paper。

 the performance improvement of data marshaing actually increases with more core。😊。

Higher interconnect latency and larger private L2 caches。And the interesting thing is。

This all of these are happening， right？Meaning this is an idea that could actually be much better in the future and whenever you I think analyze some ideas it's good to look at the trends clearly we're adding more core to systems today。

 we're having higher interconnect latencies today and we're having larger private L2 caches although with memorycentric computing we want to get rid of them as much as possible。

 I think with memorycentric computing we want to get rid of especially the second two。😊。

More cores are still useful I think because you want processing near me。

 but still I think these are these trends are a bit hard to change and the main reason why is with all of these trends inter segmentegment datats has become a larger volume。

If you have more course， you paralyze your program more and you get more communication essentially。😡。

If you have higher latency， you get longer stalls due to communication。😊，And as I said earlier。

 as you get a large L2 cache。These misses are the type of misses where larger cachees are useless or better cash management is useless。

😡，Because these are not capacity conflict or coldnesses。Well。

 you could consider that coal miss from the perspective of the core。

That actually executes the segment， execute that load。 Yes， that's true。

 but that from the global perspective of application executions that are called myth。😊。

Somebody else is generating。This data that is causing the miss。So I basically said communication。

And I think these misses are going to be more and more important in the future。

 that's one of the reasons I spend some time to discuss this。It's a harder area to do research in。

 but I think it's a very important area。So in the paper we also discuss other applications that I'm not going to talk about。

 this could be generalized to other stage execution models。

 like clearly task parallels and models that people use in the field。

 I'm going to briefly talk about that when we talk about multiprocesors I think。😊。

And special purpose remote functional units， there are also other approaches in literature that are interesting。

 but I'm not going to talk about。😊，And I think if you actually reduce the cost of this sort of communication。

 including with this approach， this could be an enabler for more aggressive stage execution。

 meaning more aggressive parallelization right and this is kind of what people really wanted to do when they initially started with multiprocessing。

You really want to paralyze your program as much as possible， one instruction in one core。😡。

Core or functional unit what's the difference that much andvidia used to call their execution lanes as core and I used to joke with them I don't think their core basically so GPUs used that this huge core many。

 many cores right but yeah maybe from a perspective functional unit can be considered a core also right it's good to think about that but basically the reason is you lower the cost of data migration or communication and this is really an important overhead in remote execution of code segments and you can always think about parallelism as remote execution right。

😊，What does parallelism mean， You're really executing some piece of code somewhere else。

 and that's remote。😡，It's good to think about that。

And if you actually make remote execution of finer grain tasks more affordable。

 more feasible by reducing the overhead that's caused by them。

 you get much finer grain parallelization in multichoords or whatever you're communicating I think a lot of these ideas could be applicable for example to models where you actually do parallelism in memory as well right because。

In the end， at some point you're going to communicate local data hopefully is not a problem if you've done a good job in partitioning your data in memory。

 but at some point you need to communicate。😡，Across different， let's say。

 processors or execution unitss in memory and your ballneck will be this。to think about that。Okay。

So I don't want to go through this in detail， I think we've discussed all of this。

But I think basically what's even more interesting in this sort of approach is you can enable new models。

 very fine grain new mode execution， as I kind of mentioned。

Okay and that's the paper if you're interested you can read it。

 I think it's going to be part of the homework you can as an optional one。嗯。Any questions？Otherwise。

 I'm going to switch。To other things in heterogeneity Albert。Okay。Okay。

 so let me switch to other things clearly heterogeneity is something real today。

 right people are having heterogeneity。😊，In both micro architectureit as well as architecture。

 ISA and existing systems in a widespread manner。呃。

But I will mention that there are other uses of asymmetric。

 so we focused a lot on performance scalability。😡，And also energy efficiency that comes with all of that。

😡，But。😡，Even if you may not get performance。😡，There are good reasons to use asymmetry。

 and one is energy efficiency。So there are works that discuss this and clearly these works are important。

 basically the idea is to implement multiple types of cords on a chip。

Monitor the characteristics of a running threats。For example。

 by sampling what kind of energy you're spending， what kind of performance you're getting。

Periodically and dynamically pick the core that provides the best energy performance trade off。😡。

That you think will happen in the next phase in a given phase of a program。

So in this score best score， of course， depends on the optimization。

 whether you're optimizing for performance or energy or energy delay， et cetera。

 you could optimize four different metrics clearly。

 that's the beauty of energy and A as we discussed right。And this is a nice approach clearly。

 so when this was proposed。It was proposed by folks who were actually working on alpha processor also。

 and they basically demonstrated these different alpha courses。These are called EV4， EV5， EV6 EV8。

 which was never built。呃。Because I guess they were bought and then somebody didn't want to build those processors。

 actually they were bought by Intel and then Intel didn't want to continue this line clearly。😊。

But maybe they should ever reconsided in hindsight2 knows okay。

 but basically if these cores are already built Ev4 Ev5 EV6 Ev6 is alpha 21264 I think EV4 is alpha 21064 I don't yeah that's true I think so this's the out of order processor thiss a heavy out of order processor these are the relative sizes of the core scaled to 0。

1 micron。😊，Which is still pretty large today， right？

You can see that these are EV4 is actually very small， it EV8 is 80 times bigger。

So there's something to be said about area as well。

 and these are what's reported in the paper in terms of peak power。

 average power and performance across some workloads。呃。

I think these numbers are a bit more realistic compared to the Intel paper that I mentioned yesterday。

 although I'm going to mention that paper because that that paper has value independently。

 but you can see that these folks say EV4 has a peak power of this and performance is normalized to that EV5 has a much higher peak power but performs a 30% higher and EV8 has huge peak power as you can see comparatively I don't know if these numbers are correct actually because EV8 was never implemented so keep that take that with a grain of salt。

😊，But performance is also a double， let's say。Anyway。

Basically you have a variety of cores with variety of performance and energy and power characteristics now you one way of utilizing these cores assuming you've implemented all of them on your chip since you already designed them in the past。

 why not put them all of them in your chip right that's one way of easing the design of heterogeneous course。

😡，呃。Now what you can do is you can monitor what kind of performance you get on different course for a different phases of an application and this is one application I don't remember which one but you can read the paper it shows what kind of instructions per second performance you're getting clear there are some phases right there are some phases where EV8 is much higher performance than EV6 EV5 EV4。

And there are some phases where their performance is similar。

And this could be because you don't have a lot of instruction level parallelism to exploit and eviiate in some particular phase whereas in some other phases。

There's a lot of instruction lo players and takes exploit， et cetera。

And the idea is basically to determine those phases where。You would。

Want to schedule the code on a different core based on some metric that you're optimizing and then you schedule it on that particular core。

 So their dynamic mechanism， if you look over here， if you want to optimize for energy，chooseoses。

Some of these cores， so this is basically I think their dynamic mechanism。

 it decides to choose EV4 only very infrequently， it chooses EV6 most of the time as you can see and sometimes choose EV8。

And this is if you want to optimize for energy delay products。Okay。

 I'll let you think about it that's the paper clear there are advantage and disadvantages to this now you get more flexibility in energy performance trade off。

😊，And it can execute computation to the core best suited for it in terms of energy。

 I assuming doing you're taking into account energy directly。Where are there disadvantages。

 but this is true for disadvantages for a lot of heterogeneity if you do an incorrect prediction。

 you get to the wrong core， you get reduced performance or increase energy This is more of an issue in this case because。

😊，Well you're not really picking a critical section of a program right you're really picking some program you may be migrating a program from one place to another and really wasting performance so if you do the wrong decision this is not good。

😡，Clearly， if you do the wrong decision in critical sections。Yes， it's not good。

 but you're not migating the whole program。😡，We for migration because if you do that now。

 you need to warm up your caches in the other core also。Okay。

 there's overhead of course switching which is part of whole program idea。

 so these are actually relatively similar to the disadvantages that we see I think incorrect predictions are actually very dangerous here。

😊，Yeah， you need to design multiple cores， but if you already have them。

Maybe that's good or you could argue that that's good at least it reduces your design effort you need to have phase monitoring and matching algorithms。

 I think these are important actually to develop independently of whether or not you do this identifying the phase of a program。

😊，And deciding what kind of hardware to use for a given face is really an important problem that's still not completely solved。

😡，This could be done at a coarse gra laity like this。

 you identify okay this is my face and in this phase I use a large core right。

 but you could also do this phase driven configurability at smaller gra las this is my face and I think in this phase。

😡，This prefeure configuration will work nicely， you don't have how to migrate things to a large core right so there's a lot of benefit to doing good face prediction。

So what characters should be monitor is important once characters that are known how do you pick the core in this particular case？

Okay， any questions？Yes。不是。我の。

![](img/208ed3af25019f89320ebb22fd05b2f8_58.png)

That's also true。 yeah， I think in this case， they they did like。

They choppped the execution time into interval basically。That's one way of doing it， but of course。

 if you have more information， if you can identify the changes like in behavior。😡，Of code。

 potentially with software support， you can do better。In fact。

 that may be even better because you may make less or more informed decisions。穿的信就他没多。

Exactly yeah exactly， so this doesn't consider utility for example。

 I think you you mentioned some other thing maybe more utility based。Mt could be better， right？



![](img/208ed3af25019f89320ebb22fd05b2f8_60.png)

Okay。But there's a room to improve， as you can see。😊，Actually。

 later work kind of looked at the utility， that's performance impact estimation work that I didn't talk about。

 but we compared to in the utility based acceleration。

 tried to understand the performance impact of moving from one court to another。With some metrics。

 it was not exactly the utility。But it was getting closer to utility。Okay。

 so we've talked about asymmetric and symmetric core。

 let's start wrapping up a little bit clearly if you have asymmetrictic core。

 you can provide better performance when threat parallelism is limited。

 you can be more energy efficient also at the same time。😊，disadvantage is of course。

 more complexity I think we've kind of seen this earlier， but you need more complexity。

 you need to design more than one type of core if you already have them that's great。

 but if you already have them that may not be a good match also right。😊。

Maybe you don't have the right core for extremely high perils， right？As we have seen earlier。

 like EV4 actually in this particular case， Ev4， let me go back is a core that's still。

Abit expensive， let's say it's not out of order execution， it's an order execution。

 but it does branch prediction et cetera， so it's expensive though。Maybe you want very。

 very cheap core， right。The really design， but maybe the design effort of cheap course is smaller。

 you could also argue that。So scheduling should be more complicated we've already seen this also what computation should be scheduled on the large core small core who should decide this hardware versus software。

 managing locality and loan balancing can become difficult if threads move between cores。

This's actually interesting， we have not discussed as much but。Especially。

Instead threat's keep hopping between cores， now you have another problem because your working。

 data working set and instruction working set should also be hopping between cores。😡。

Meaning whenever you get scheduled on another core。

 you may not have your you may get a lot of cash assistance to begin with， right that's locality。😡。

There's load balancing also， programmer may hard may have tried hard to balance the load。

Assuming that your code is executing on multiple courses now underneath you're moving。😡，Tings。

 how does that load balancing change， right？So load balancing is a tough problem as we will see a little bit more。

And cores may have different demands from shared resources also that's something important to think about。

 like how do you actually provide access to different core to shared resource like the memory controller。

 caches， etc。Okay， with that， I think let me talk a little bit more about how to achieve aymetry。

 we've discussed this a little bit yesterday， you can have static aysymmetricmetry。

 you can have dynamic aymmetry。😊，With static means that your type and power， of course。

 are fixed at design time， dynamic means these change dynamically。

With static people have looked at two main approaches for designing faster course。

 basically you have hard coded high frequencies， static higher frequencies for some course。

 or you can build a more complex powerful core with an entire different microarchitecture。

 including frequency potentially。WithAnd then there's some natural asymmetry arts as we have discussed yesterday。

Even in course there's variations in tip frequency so some cores may naturally be faster。

 some cores may naturally be slower depending on the variation and if you can identify that maybe you。

Have higher frequency and higher voltage for some chs and lower frequency and lower voltage some other courtds if it's static。

Dynamic is， of course more powerful in general。basicallysically， one way of achieving。

Dynamic asymmeries by boosting frequency。I'm going to talk about that a little bit that's an easy way of achieving that's why everybody did this earlier now people are doing asymmetry also so both of these are done well not the dynamic combining that part is not done but boosting the frequency dynamically is done and static asymmetry is done today。

😊，But also there is another way of dynamically achieving aymmetry which is combining small core to enable a more complex powerful core。

 I think it's a very interesting approach that needs to be reexamined perhaps again。

 but I'm going to mention some papers that I briefly mentioned yesterday also but I'm going to put them on a slide we'll not go into that that much today okay。

😊，Maybe there's a third， fourth or fifth approach that I don't know。So the second approach。

 combine small core to enable a more powerful complex core， there's actually works in this area。

 which I believe are interesting。😊，I'll just leave it here and not talk about it。

I believe more of course actually the state of the art approach is the latest compared to all of these and it actually is a more implementable way of doing it some of these are actually very interesting ideas but much harder to implement like core fusion I think is a very interesting idea but much harder to implement。

😊，呃。Okay。Let me talk about asymmetry via frequency boosting because this actually opens up interesting issues。

 as I said this already employed in today's systems。😡，Today's systems， for example。

 when there's a single thread running。😊，呃。The frequency of the core that's running that thread is boosted significantly。

😡，It's called Tbo boost at Intel， I don't know what's called an IMD， but it's kind of similar。

Essentially， you do tubo boost and you increase the frequency of that core。

And the reason you can do that is because you now put all the power to that core and the other cores are not running。

 essentially they're not consuming power。😡，So this was okay， before I go into that。

 there are ways of doing the statically due to process variations scoress might have different frequency and statically tight。

😊，And simply you can hardware or design the course to have different frequencies。😡。

And then you can migrate an application from a low frequency core to a high frequency core whenever you want it to have high frequency。

We would of course have some cost or migration but it's possible to do dynamic is already done by doing dynamic voltage and frequency scaling that's nicely described in this paper by Intel you can actually achieve this so let me go over this elder basically the idea in this paper was also interesting Basically their goal was to minimize the execution time of parallel programs while keeping power within a fixed budget。

😊，And their observation is similar to what we have discussed earlier。😡。

You want the best scalealar performance when you actually have a single thread。

 you want the best throughput performance when you have many threads。😊。

And there could be some intermediate points also。And the idea is to。

You normally have fixed power budgets。😡，And what you can do is you can have a lever to play。

And this lever to play could be energy per that's consumed。

So by changing the energy consumed per instruction。While the power is constant。

 you can change how many instructions are executed per second。Does that make sense？

And that's the idea over here。Now this may not be intuitive mapable to asymmetry。

 but it's actually easily mapable to asymmetry also if you're in a high throughput phase。😊。

Reduce the energy per instruction。And execute things in many small cores that require low energy。

And this naturally enables high IPS instructions per second grade。If you're in a let's say。

 low throughput phase， increase the energy you spend for each instruction。

 but you're going to execute probably a smaller number of instructions。

 meaning executing a large core for example or multiple large core， et， that's the idea over here。

So I've already said this I think for a fixed power budget。

 run sequential phases on a high EPI processor， high energy per instruction processor。

 and run parallel phases on multiple low energy per instruction processor and now we have asymmetrictic multicore again。

Okay， so that's one way of achieving， right？So clearly。

 you can do this energy per throdling using DVFs as well。😡，Not asymmetric multi corere。Actually。

 in this work， they didn't really talk about etic multicards much they achieved it through DFS。

 but I like this approach because this applies generally as we will see later on also。😊。

The key is really， if you think about asymmetrictic multi core。

 really modulating the energy per instruction。😊，To match the IPS that you really want， right？

But there could be other ways of modulating the energy for instruction and that's is through DVFS。

 for example， dynamic voltage and frequency scaling in phase of low threat parallelism。

 you can run a few cores at high supply voltage and frequency。😊，And in the extreme case。

One thread exists， you run one core at the highest supply voltage and highest possible frequency without within the power budget and thermal budget in phase of high thread p。

 you run many cores at low supply voltage and low frequency。😡，Okay。

 so there are other ways of modulating things， which is also interesting。

 this is not a comprehensive list。😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_62.png)

But this paper， this other paper that's actually earlier from also Intel。

 discusses other ways of modulating the EPI。One is voltage jump frequency scaling clearly when you do voltage jump frequency scaling。

 you may increase or lower voltage jump frequency in this case they basically say they say lower voltage jump frequency so that they get a lower EP。

😊，呃。This is according to them the EP range， the range that you would get energy construction from one to four。

 take all of this with a grain of salt。And then there is also a time to change the energy per instruction。

 right， meaning time to achieve that state where you're running faster or less faster。

And according to them at the time， it was 100 microseconds， you need to ramp up the voltage。

 essentially great。This changed over time， but there's always time to actually throttle the API。😡。

So this is Wall frequency again you could do asymmetrictic course and according to them again。

 EPI range is higher so you can actually get higher performance。As well as energy range。

According to them。Migrating a 256 kilobyte L2 cache takes 10 microseconds or so。

 so there's some more effort over here again， take all of these a grain of salt。

 but there's more time according to them and we already discuss the action and then there you could have a variable size core meaning you can have a single core but when you don't have enough instruction level parallel for example。

 what you can do is。You can reduce the size of the structures of the core。

They're not talking about caches over here， but they're talking about。😡。

Maybe changing the sizes of different structures internally。You can， for example， change the width。

Of issue， you can change the size of your instruction window so that you can make things in order。

 maybe。I'm not sure if they're talking about that over here because I don't remember。

 but I don't think this is in order， it's really still within out of order。Okay。

 so basically theres some cost to it et cetera and then there's speculation control which is reducing the amount of speculation that also changes your ETI in some way basically you say。

😊，I want to I don't need a lot of performance over here。

 so I'm going to reduce the speculation that I do on the processor。

When when I get to a branch I stop fetching， that's one way of reducing the speculation， et cetera。

And this is clearly the fastest， one of the fastest ways of doing it。Okay。

 so there are different ways and if people are interested I'd recommend looking at that paper。😊。



![](img/208ed3af25019f89320ebb22fd05b2f8_64.png)

![](img/208ed3af25019f89320ebb22fd05b2f8_65.png)

And some of these techniques are actually implemented in modern。

 actually I think all of these are implemented in today's process。

 but the numbers take them with a grain of salt。😊。

![](img/208ed3af25019f89320ebb22fd05b2f8_67.png)

Okay， so we're specifically talking about frequency boosting frequency boosting is clearly implemented。

 this was the first thing one of the first things that was implemented。😊。

This is very simple to implement， no one needs to design new core clearly。😊。

And the other big benefit of boosting frequency is parallel throughput doesn't degrade when TLP is when you have a lot of thread level parallelism。

 you still run a core with low frequency and you still have a high thread level parallels。

 you don't need to dedicate cores， you don't need to dedicate the space of many small cores for a large core for example right？

And it preserves a locality of the boost of threat。😡，Which is nice， right， so this yeah。Of course。

 this has disadvantages and one of the biggest disadvantages is frequency。

 improving frequency helps with instruction level parallelism if you memory。

 if you're compute bound especially， but it usually doesn't help with memory bond workloads。

 so if the phase of your program is memory Bo，😊，You're still memory b you may generate more requests more quickly to the memory system and get better parallelization。

 but the effect of that and the grand scheme of things is actually much smaller。

You're better off doing something else with memory， basically。

And also another thing is it doesn't reduce cycles per instruction this is another way of saying that you didn't design a different core right basically frequency is only part both of these points to the fact that frequency is only part of the performance equation right if you remember the performance equation you can improve the performance of a single thread by changing the number of instructions。

😊，Times， the cycles spent on each instruction， times there。Time spent on each clock site， right？6地。

Performance equation that we have。Clearly， we're not changing the number of instructions here because the binary is the same。

 we're changing the frequency。😊，Hopefully things will improve。

 but cycles for instruction fundamentally doesn't change， actually it increases。😊，呃。

Because now your frequency is probably larger， maybe you need to do something else in your pipeline right。

 it may increase so basically it's good to think about that。But fundamentally。

 you're not improving cycles for instruction， whereas if you design a different core。呃。

 hopefully that他。Maybe the same frequency， I don't know， maybe better frequency。

 but maybe also a better cycles per instruction。😊，Okay。Okay。

 this is also interesting to think about changing frequency and voltage can potentially take longer than switching to a large cord。

😊，The debate is still out over here。It's good to think about that there's a tradeoff over here right clear there's time you spend for changing frequency voltage ramping up voltage。

 especially ramping up voltage takes time right and if your frequency range is very large you need to ramp up voltage from a very small value to a very large value。

And that is actually。That is a lot of issues， not clearly it takes time。

 it takes time to do it reliably because now you're actually inducing a lot of noise in the system and that noise may actually lead to some power issues。

Where switching to a large core doesn't require changing the frequency。Okay。

 there are interesting issues， as you can see， even with this trade off that we go into。

 there are a lot of issues。Okay， any questions？Oh， wow。

I spent more time than expected so I think i'm not going to cover the remaining slides over here。

 but i'll go through that we've already covered a bunch of these this is more of some vision slides。

😊，That talk about asymmetry everywhere。I'll let you study it。

 but essentially I think maybe I'll cover some of these things very quickly， not all of them。😊。

I think one of the biggest interesting things in asymmetrictry， these are slides actually from 2010。

 I think I put these slides， I presented these slides in a workshop on。😊，Essentially。

 the question in the workshop was。What is the future of computing something very general and my one of my visions was really asymmetrictry everywhere essentially each component should be design asymmetrictry that's the goal to fit different computation access and communication patterns for different power performance reliability characteristics there's nothing you have not heard of so far but asymmetry I think also subsumes configurability and partitionability。

😊，And then you need you design the runtime system to automatically choose the best fit components for each phase。

 so for a given phase， let's say you determine you dynamically stitch together a best fit chip for that phase while satisfying the performance SL with minimal energy。

 that could be one goal。😡，So I like thinking of it this way。

 I'll go through these again relatively quickly， for example。

 phase one may want high power high performance score。

 some lean cache hierarchy optimized for some access pattern。

 maybe some lean interconnects and maybe some type of memory。😊。

And if you have some heterogeneous things， you can actually dynamically。

Identify the phase and match computation to it。Phase two may require a very small core。

 but a bigger memory hierarchy， right？😡，Phase three may require a lot of course。😡。

But's very lean memory hierarchy， maybe a streaming phase with large capacity requirements， et ceter。

Now， if you could actually design the hardware to be able to do that。

 it would be nice and then maybe when you go back to phase one， you still incarnate this hardware。

And then you can also morph the software components to match asymmetric hardware components。

 You may have multiple versions of software for different resource characteristics。

 I think it's also very interesting。Essential， I think you want flexibility in hardware and flexibility in software also match the flexibility in hardware。

 So version one may run here。😊，Version 2 may run here with mini small core and version 3 may be heterogeneous ulcer right。

So there are many interesting research and design questions over here。

 again I will not go through these in detail some of these be covered in a very limited manner in what we have discussed。

😊，But I'll give you some simple examples like serial and parallel。Of courseourse。

 we've kind of discussed this， right？But you could also have a single core。

That has auto order capability and a VIW capability。

 and you can dynamically figure out which one to use VLIW is very long instruction word so a compiler schedules the parallelism。

😡，Or it could be all out of order and in order， and you could switch between that， right。

 depending on the face。😡，And there works in this area。

You can design the memory hierarchy differently for streaming versus random access you've kind of seen examples of this with prefettures etc ce。

 but I think there needs to be more over here if you remember the for example stream buffers they were getting rid of the caches right earlier it's good to re-examine some of these things today we have these huge caches。

😊，And。People don't re examineamine some of these fundamental decisions， in my opinion。

Huge guys are used to build and easy to。If you have area， let's waste the area。

 let's put it over there， let's forget about all of the cost of it。😡，Whereas if you're streaming。

 those caches are useless and they actually hurt performance and we don't have a way of actually stream easily into the processor today。

Okay。So we're going to talk about interconects， you can have latency optimized versus bandwidth optimized interconnects。

We've talked about memory controllers and you can partition the memory bandwidth or interconnect bandwidth across latentcent when web bandwidth sent to workloads differently thread cluster memory schedule kind of does that。

呃。You can have different， we've kind of also talked about this memory scheduling policies that are tailed differently for compute intensive versus memory intensive workloads。

And you've talked about hybrid memories， right for different purposes。Okay， well。

 we also talked about reliable DM versus less reliable DEM。

 and we've also talked about heterogeneous latent DM， a heterogeneous refresh rateM。

 so we have a lot more today。😊，I l here but this is kind of a vision that I have I don't think it's easy to achieve this vision in the short term it's a much longer term research vision。

 but I believe it can actually yield a lot of benefits going into the future I think the works that we've discussed today are kind of scratching the surface right and the good news is these are already in real products。

😊，So asymmetry in both frequency scaling， core sizing。呃。

Speculation control and also asymmetrictic course finally are in products。Who knows maybe in future。

 we'll have a lot more， let's say， fluid hardware and fluid software。



![](img/208ed3af25019f89320ebb22fd05b2f8_69.png)

Okay， okay。Any questions？Otherwise， this is really the right time to take a break。

Let's take a break until 1445， 17 minutes， and then we'll come back。



![](img/208ed3af25019f89320ebb22fd05b2f8_71.png)

With lecture。