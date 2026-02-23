# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p04 Lecture 4_ Branch Prediction II & Prefetching (Spring 2025).zh_en -BV1Xc19BnET7_p4-

Oh good， okay， we can start the live stream， I think it can be live for some start Yeah yeah that was okay。

😊。

![](img/41f97ad8c7218ec80efca8520c7479f3_1.png)

Okay， already streaming， that's good。Of。ど。Theres so many messages。😔，你啲什我我不表。you knowオ。嗯。Check。

speak the places this。你怖。系冇。Yes。是是。对。Yeah。就过这个。咁时用今。Yeah。Its。Whatこ。嗯。都未觉得冇。时分钟照。Oh good， Okay。

 I slept have three minutes， so it's good to prefe。Well， yeah， if we can finish branch prediction。

 we'll prefetch。😊，Oh是。It can prefe the range predictions also。对。嗯。嗯。Okay。个。好。哎，我想个。的。好。Oh。And点钟。

There spots here too。Okay后。是这。Yeah。え。Yeah。车哪。W。嗯。不。Oh。ま。Thank。See。Thank。🎼，🎼不在。Yeah。Okay。Okay。

 let's get started。So today we're going to continue branch prediction that Rahus started last time。

 remember you covered out of order execution and branch prediction and we were kind of in the middle of branch prediction。

 I'll pick up on that and hopefully we'll get to prefeting。I should say that these are two really。

Fundamental topics in microproor design， if you don't get these right， then your proor would be。

 in my opinion， kind of useless。Because it won't be high performance。Unless you're not doing pipeing。

 of course， which makes your processor kind of useless to begin with。

Use this in general cases right if you want to do general purpose computing but in many cases today you need performance you cannot really cope up with the data so you do need these techniques and these techniques have been very fundamental there's a lot of potential for growth in both。

😊，But more so in the prefeting part， branch prediction is a bit much harder to develop these days。

 so that requires a lot more creativity and innovation， in my opinion。

 but that's true for prefeting as well。😊，Okay， so you've seen some of these slides。

 I'm going to go through some slides relatively quickly just。😊。

Ft stuff in your caches let's say we're going to talk about well we have talked about compile time and runtime branch prediction and we said that runtime is good because it gets rid of some of the issues that you have with compile time which enables you to really predict branch is based on behavior of the program of the input data dynamically right but then this is more complex clearly and then we started developing predictors。

 one last twobit counter-based predictor building on last time predictor essentially one idea the easiest idea you can come up with perhaps is if you want to predictor branch you look at what happened to the branch last time right which direction did it go and we're talking about direction prediction in this case and last time predictor was what we a lot but unfortunately last time predictor is very quick to change its mind so we added。

😊，It is opposed to keeping only one bit。In terms of what happened last time， you keep two bits。

Like this is a twobit counter based predictor that keeps track of what happened in the last。😊。

N times right and then you can actually extend this by keeping mor bits， etc ceter。

 but this was one of the twobit counter predictors that we have discussed right so you have multiple states so if you have actually two opposing outcomes then you change your mind。

😊，You're predicting the branch taken and if you see it not taken twice in a row then you start predicting it not taken and vice versa okay so the Oes are easy clear and then we went into more advanced concepts this was kind of the state of the art until 1990s the previous one if I can get back to a twobit counter per branch。

😡，Was the state of the art you would store these in the branch target buffer which you have seen also last time and then people said okay this is not good enough so we need to actually develop better predictors and one will people realize two things one is actually this paper in particular was the first one to realize two things one is a branch's outcome can be correlated with other branches outcomes that you've seen in the past so it can correlate。

😊，Globally across different branches and you have seen this predictor today we're going to talk about local branch correlation and then we're going to go off to other topics on branch prediction but let me remind you of this global branch correlation essentially there's good reasons why these branch predictors work they're not magic in general although later it's becoming like magic because you really need to get to predictions so there's correlation across different branches so if the first branch is taken over here then the second is not taken then the second should not be taken also right so you can see clear correlations that we have studied last time。

😊，And this is one of the fun programs actually that was very。

 very difficult to predict using twobit counters and with a global branch predictor。

 it became very easy to predict。😊，So this is the equation to tooth table workload and spec workload in 1992。

 it was a very difficult benchmark for many processors until Pantium Pro implemented the global bench predictor。

😊，With four bits of history， and then this benchmark was kind of useless。

So you can see that benchmarks actually become easy targets if you actually have an improvement in architecture and the benchmark becomes not interesting once you improve the system right so that's the story of equation to truthth table which is one of the Boolean workloads in spec 92 it's gone now it doesn't exist so how do you capture global branch correlation the idea is to associate branch outcomes with global take not history not take history of all branches and you make a prediction based on the outcome of the branch the last time the same global branch history was in content so you keep track of the global branch history using a global history register。

😊，Each bit over there tells you which direction the last n branches went， okay？😡。

And then you used that to index into a table that recorded the outcome that was seen for that GHR value in the recent past。

 hoping that that corresponds to your branch and that's called the pattern history table。

 this is the same table of twobit counters， we used to index it using program counter now we index it using the global history Reg makes sense。

😡，Okay。Well good。Yeah， the reason it has two levels of history is there's one level of history encode in the global history register。

 and there's a second level of history encoded into the twobit counters which tell you what happened when you saw that global history last time。

Okay， so this is what the predictor looks like and I already said everything over here。

 this is the global history register and this is the pattern history table。😊。

You do index it potentially you could use hatchhing tagging as we will see later on。

 but in this case， if you have nbits over here， you can have two dN entries over here。

Okay this you have seen now we're going to get to the new items so this was our just to clarify everything this was our onele branch predictor right we use the program counter to index into this pattern history table that uses two bit counters for each program counter or for a set of program counters because you may use hashing to get there clearly because you're not going to have a if you're a program counters 64 bits you're not going to have a two to the 64 entry table of two bit counters so use hashing normally that's not shown over here。

 but this is essentially per branch one level of history。😊。

This is our two level global history bench predictor。You use the program counter to get the targets。

 but you don't use the program counter to get the direction。

 you use the global branch history to index into the direction predictor 2bit counters。😡，So。

That's the idea now something is missing over here you're not using any program counter information branch information to index into the direction predictor right and people quickly figured out that doing that is a good idea also in this beautiful technical report by Scott Markfling who actually went on and designed a lot of Intel branch predictors afterwards。

😡，Basically， the idea is to add more context information to the global branch predictor to take into account which branch is being predicted so if you go over here。

😊，Indexing the direction predictor using global branch history doesn't give you that context information。

 so this person wanted to add the context information and how do you add that basically you take the global history register and hash it or extort with the branch PC。

😊，It's as simple as this and this actually immediately provides an improvement in accuracy for multiple reasons first of all now you have more context information you don't just rely on the branch history register which is the global history register you also take into account branch address or more information gives you better prediction accuracy but there's also another benefit that you get over here which is better utilization of the2bit counter so if you actually just use the global history register as we did over here you don't utilize as much if you actually add more information you have better randomization let's say over here so you improve information as well as utilization now the downside of course is this increased access latency that's an XOR。

😊，It is on the critical path potentially， right because you need to determine the next fetch address while you're fetching the current。

😊，Instruction。Next sense。Okay， so that was new G sharere， this is called G sharere。

 and this is a nice technical report that I would recommend people to read。😊，Okay。

 that's what Tshare looks like basically with some hashing。

 you attach global benchtry and program counter and predict the direction。😊。

Okay now the question is can we do better， we're going to talk about another type of predictability there this much global correlation across different branches。

 but there is also local correlation for the same branch， for a given program counter。

 for a given branch， its outcome can be correlated with past outcomes。😊。

That you've seen for that branch。Makes sense clearly this is there is something that is already exploited for this。

 right with twobit counters kind of exploit that。😡，But they don't look at longer histories。😡。

So we're going to try to encode longer histories and this is a nice excerpt from McFarling's paper。

 essentially if you look at this loop， this loop test branch that's done at the end of the body executes a pattern that looks like this 1110。

 which is taken taken taken not taken right clearly it's the loop it raised four times right？😊。

So you can actually predict exactly。But the direction of this branch would be as long as you know where you are in this pattern right if it's 1110。

 the next one will be taken because you're going to enter the loop if it's 0，111。

 the next one will be0 because you're going to exit the loop right and that's the idea basically。😡。

Okay， this is kind of an unrolled version of that 1110 to predict a loop branch perfectly we want to identify the last iteration of the loop。

 this is just one example right there could be other examples that you can come up with for local branch prediction but loops are an easy example by having a separate pattern history table entry for each local history we can distinguish different iterations of a loop。

😊，And this nicely works for short loops， of course right if your history is let's say four and you iterate four times maximum。

 you can capture this if your history is 16 and you iterate 16 times maximum。

 you can capture this if your history is。256。Now you need to the 256 centuries over here or you need to be a little bit more clever。

 so this doesn't scale very well that's why people have developed up loop predictors as we will briefly see。

😡，Makes sense so how do you capture this essentially we're going to use the same idea。

 have a per branch history register as opposed to having get a global history register that keeps track of the last end branches。

 we're going to have a pro branch history register that keeps track of the last n times what happened to this branch right I already said this I think。

😡，You associate the predicted outcome of branch with taken not taken history of the same branch and make a prediction based on the outcome of the branch last time the same local branch history was encountered this is called the local history or local branch predictor again this uses two levels of history one is the per branch history that I'm going to show you soon。

😊，And then there's a two bit counter history at that history register belt。Okay。

 you could say that tooid country history is kind of redundant。

 but it still gives you hysteris in cases where you don't have these nice loops， clean loops， right？

Okay， so the first level， as opposed to having a single global history register。

 we have a set of local history registers ideally per branch。😊，But that's not easy to do of course。

 so we're going to have local history register per set of branches indexed by some program counter。

 think about that。Okay， and bits each， you select the history register based on the program counter of the branch。

😡，That gives you the local history for that branch。

 and the second level is the table of saturating encounters for each history and you over here the direction the branch took the last time the same history was seen。

😊，Makes sense。With hysteris， of course。Okay， those are two bit counters， I mean。

 they could be three bit counters， as you will see。

 there will be three bit counters for some alpha processor。

It depends on how your programs etc okay so this is what it looks like now this is what the local history predictor looks like you take the program counter。

 you index into this table of history registers per branch and based on some bits in the program counter you select the history register that's the first level of history using that you index into the two bit counters direction predictor now that gives you the highest bit over here gives you the take and not take prediction。

Makes sense， right？Okay， that's the local now we're taking into account two levels of local history。

So that's which direction's earlier instance of this branch went。😡，Okay。

 so that completes global and local prediction。And you can actually generalize this this is actually the next version of this paper in IsCO 1992。

 I still reference this because this is the earliest paper， it generalized it。

 it basically says you can have a branch history register that could be global。😊。

Or it could be per set of branches， or it could be per branch。😡。

And you can have a pattern history table that could be global or per set of branches or per bench right all of these can be per bench as well and there are different variations of it and the pattern history counters the twobit counters over here can be determined by the compiler or you update them dynamically that's what adaptive or static needs adapt them means you update them dynamically but you could imagine a case where the compiler determines them right it's a tough job for the compiler but you could imagine it。

😡，So that's why they don't use the S portion over here， though GAG， for example。

 has a global a single global history register with a single global pattern history table and these are all adaptive and this is the most frugal global history predictor that you can get。

😡，And this is what's implemented in Pentium Pro and that's what made partially Pentium Pro successful Pentium Pro was the real first processor that implemented。

Both out of order execution and aggressive branch prediction at the same time it was the first commercially successful out of order processor that made Intel rich let's say Intel having problems right now for different reasons but patent to probe as a good architecture okay so on the other extreme you can have a pattern a branch history table per branch right every single history register belongs to a separate branch over here clearly not realizable in reasonable hardware。

😊，And。And then basically you have this also a per branch。

 so that's also clear enough to realize them。😡，Thiss the most expensive form which it is not realizing。

 so usually what you have is some combination in between， it's usually actually SAS。

 which is not shown here。😡，You have a per branch history table per set of branches。

 and you have a global pattern history table per set of branches。In fact。

 Penduium Provo is actually for severalto branches， I should say to be really exact， if was GAS。

 it was not GAG。Makes sense。Okay， anyway you can read more about this。

 but this is a nice taxonomy now you can actually beautifully evaluate all different types of predictors。

 you have a simulation cluster and you have your workloads and you can figure out the bench prediction accuracy for all types of predictors。

😊，Okay， and this is the retrospective of that paper。

 its won the Micro Testest of time award it it's essentially implemented in all processors today。

Id recommend reading that， that's the entire retrospective in two pages。Okay， the question is always。

 of course， can we do better， any questions， by the way？😡，Okay， everything is perfectly clear。

 you're implementing this sort of this thing anyway， hopefully in your lapse。More interesting things。

 of course， today。😊，Okay， can we do better and people have figured out that they can do better I'm going to give you a several ideas over here One is basically。

😊，There's no good algorithm for every single branch。

 essentially predictability of branches varies across branches。

 some branches are more predictable using local history， for example loop branches。

 some branches are more predictable using global history， for example。

 branches that are dependent on prior branches that are executed like we have seen earlier for others the simple tibit count is enough。

 yet for others a single bit is enough。😡，In some cases。

 actually you don't even need branch prediction almost as Raul described， right。

 you actually you can do program analysis and say， oh。

 this branch is testing for an error or an null pointer。😊，And if that branches。

I am guessing that that branch is never going to be taken unless the program is wrong and if the program is wrong I have other things to care about than getting that branch correctly predicted right so if you can classify your branches nicely you can design different predictors to cater for different branches so basically there's heterogeneity and predict to behavioral branches and there's no one size fits all branch prediction algorithm for all branches。

😡，And the idea is whenever you see no one size fits all and heterogeneity。

 you can design think about a heterogeneous design so it can exploit heterogeneity in branch predictability by designing hybrid branch predictors。

😡，Which are essentially all predictors today， and this is what was also proposed in Mc Fararling's paper。

😡，In addition to proposing the G sharere predictor， he also said， okay。

 we need to design hybrid branch predictors for the reasons that I discussed in the previous slide。

 and the idea is to use more than one type of predictor to select and select the best prediction。😊。

For example， you can have a hybrid of2bit countries and global predictor you can have a hybrid of global and local you can have a hybrid of multiple of these et ceter。

 clearly this makes things more complex that's one of the disadvantages but this gives you better accuracy because of the reason that I just discussed different predictors are better for different branches。

 but there's also another benefit。😊，Which we kind of glossed over in the design of prior long history predictors right if you have two levels of history。

 it takes longer to train that predictor imagine a predictor with 16 bits of history a global history register in order to train that you need to see the different outcomes over time right and imagine now per branch local histories。

😡，That actually takes longer time to train so there's a warm up time to actually train the predictors such that you are operating at the steady state and if your predictor is not ready yet you can actually use a faster warmup predictor a faster warmup predictor can be backward taken forward not taken right we have seen that also in last lecture it could be some other hints。

😡，Something is simple basically。Clearly disadvantages complexity， more hardware complexity。

 even longer access latency， and you need also a selection mechanism。

 the question is how do you design that selection mechanism。

 which predictor to use is determined by a meta predictor or a selector。😊。

I'm going to give you some example then you're going to implement this predictor actually。😊。

This is what's implemented in Alpha 21264， all of these hybrid branch predictions actually implemented in all modern high performance processors。

 but the alphapha 21264 was a beautiful out of order execution engine and Al actually put a lot of information about it at the time so they actually explained how this works in this process minimum branch penalty was seven cycles but typically they saw in workloads 11 plus cycles。

😊，And this was one of the fastest processors of its time， actually， in terms of frequency also。Okay。

 they did some target prediction and this was what the predictor looked like and you can see that it's a global history predictor over here very similar to what we have seen 12 bits of history and then you have a local history predictor。

😊，We have a local history table and local tubit counters pattern history table over here。

So this used 10 bits of history over here and then three bits of。Counters， not2 bit counters。

 but2B counters。Why because they decided that that work better for their workload rate and then you need to do a choice prediction over here and they basically use the global history。

 they basically kept track of which predictor was doing more accurate predictions。😊。

Based on the last time you encountered that global history， again， that's their choice。

 you could come up with better mechanisms， potentially right？Makes sense。

 this is also a beautiful paper if you have time I'd recommend reading these papers。

 it's a very fundamental paper that talks about a lot of issues in high performance auto order processor design and we're talking about 1999。

😊，Today we're in 2025， right？😊，And people are designing pros of 2028。So a lot has been optimized。

 but this is a good baseline to think about。😡，Okay。

Let me talk about bias branches because this is one way of also making the predictor less。😡。

Let's say， do less work。So basically， people have found out that many branches are biased in one direction。

 for example， 99% taken， if you're doing a loop， for example。

 in many iterations that's taken most of the time， right？😊。

And these branches actually pollute the branch prediction structures。

 meaning made the prediction of other branches difficult。

 but because they call it interference in branch prediction tables and history registers right。😡。

So the solution to this is detect these bias branches with some quick detection mechanism and filter them out。

😡，And predict them with a simpler predictor， it could be a last time predictor。

 it could be a static predictor， it could be something that you design。Makes sense。

So how can you detect them， you can actually think about detecting them at compile time or runtime。

 having a simple detector is not that difficult。😡，Okay， this is proposed in this nice paper。

 micro 1994 again， we're talking about early times， if you're interested， you can read that。

And people employ these mechanisms that。The hardware。

 you don't want to waste your hardware for things that are easy right that's the idea over here。

 you want to focus your hardware for things that are difficult。😡。

You're going to see that idea more and more soon。Okay。

 so basically are we done with branch prediction so a lot of people said oh these hybrid branch predictions were done with branch prediction。

😡，Because they work reasonably well， maybe 90 to 97% prediction accuracy on average at the time on some workloads。

 I think the workloads today are much worse。😡，Frankly， some of the hardware workloads。

 but even then difficult workloads existed， for example。

 one difficult workload is a compiler GCC this takess a lot of different paths based on the input set and the paper I think this was McFarling's paper that show that maximum instructions per cycle you could get with tournament prediction is nine。

😊，If you remove some of the other constraints in the machine。

 but maximum IP with perfect prediction is 35， that's almost 4x。😊。

So this makes a good case for working on branch prediction。

And I think Raahhul made a good case earlier by showing you that in terms of like if you get to 80% you're still wasting a lot of instructions in the machine right so there's an energy efficiency case to be made as well。

Okay， so I'm going to talk about some other bench predictor types that are employed in existing processors again。

 so we talk about loops I'll go through this relatively quickly but you can detect loops people figured out that you can actually if the loop iteration count is predictable you can predict that iteration count and filter those loop branches up this works well for loops with a especially small number of iterations where iteration count is predictable and Intel PentiumM was one of the first processor that employed it。

😊，We're going to talk about preceptron。😡，That essentially uses very simple machine learning technique。

 how many people know about perceptrons。No，' not okay， you're going to learn about okay。

 one person knows， don't be afraid you're it's okay not to know。😊，It's its。

I guess it's not okay not to learn if you're interested to learn okay。

 basically it learns the direction correlations between individual branches learn， I guess。

 for one form of learning by assigning ways to correlations using essentially perceptrons。

 we're going to talk about that。😊，And then we're going to talk about using different history lengths because people also figured out that there's no one single history length to predict every branch。

 some branches are predictable with short histories。

 some branches are not predictable with very very long predictable very long histor。

 so you want to actually heterogeneity in histories also and this predictor actually adds heterogeneity。

😊，Okay， I will not talk about this， but essentially you can detect a loop。😊。

by monitoring backward branches and seeing how many times that branch is taken and keeping track of essentially a limit that you learn or record the previous time a branch is executed and seeing whether you have reached that limit the next time you actually started taking that branch makes sense。

That's a loop detector， your life may be easier if the compiler actually marked the loop branches right then and compiler actually hinted that your loop branches may be even predictable。

😡，Some blueprint are not that predictable， of course so this is employed you can look at that and this is a nice paper。

 This was during the time when people used to write。😊。

More or less informative papers about their architectures， people are a lot more。

 let's say protective these days of their architectures unfortunately。

 I think I think people it would be much better if people shared their architectural designs。😡。

Okay so this is kind of a little bit off topic we're talking about direction prediction but never forget the target prediction as well。

 there are index branches that exist in our systems and these have different targets you basically jump to a register right so people design predictors for that purpose as well。

😊，So some of the ideas that we have discussed can be applicable， like based on the global history。

 you select a target。From the BTB。But there are other ways of doing this。

 which are actually quite interesting， but we don't really have time to cover everything in this course。

 otherwise， we may have several lectures on branch prediction。😡，Okay。

 so this is Intel PenTMM and according to them， this is the branch prediction logic。

 I would probably say that this is probably the fetch part of the logic without the eyeCash。

 but it's actually as substantial as you can see。😊。

Like let's talk about more advanced branch prediction， feel free to ask questions， by the way， okay。

 yes。😊，It's probably a very difference。As you saw in the picture earlier。

 there's a lot service area taken from this time alone， wouldn't they also to be。

Proably less efficient of energy， but the places of course and then just course。

And I don't know if that'd be more probably less like the efficiency about assuming people have done that。

Yeah， I mean people haveve certainly done that right that's an approach taken by other companies like San Niagara。

 which is kind of dead right now， so basically the tradeoff is do you want higher performance in a single thread。

 which most of the world is？😊，Still， unfortunately。

 or do you have many core do you dedicate this area for many course and hope that people will write parallel programs？

😊，I was wondering the local， where's the story？it in the America。No， no。

 these are dedicated hardware structures， so you have an SM where you store that yeah exactly。

 so these are all dedicated hardware structures in the me predictor。😊，I mean。

 if your hardware structures are large， then you can think about potentially virtualizing the predictor and putting things into the L1 cache。

 et cetera， but complicates things a lot。😡，Yeah。Exactly。Any other questions？Okay。

 now let's talk about percept， since many of you may not remember or may not know it。

 This is developed in 1950s。 It's really the。I guess smallest type of I don't want to even call the neural network。

 it's a one layer a neural network basically it's a simplified model of a biological neuron as people understood at the time it's also a simple binary class classifier basically it maps an input vector x to a1 or0。

😊，So this input vector can be something and you basically classify it to a zero or1 and you interpret this zero or one in different ways。

 right？It could be， for example， an input vector of words and you run it through some weights。

And after the multiplication， you get a zero， am I seeing German or am I not seeing German？😡。

This is what kind of classifiers do neural network， but this is more of the simplest form of things。

 but let me make it more clear and let me put it in the context of branch prediction。

 so input is some vector x essentially a bit vector。😡，Perceptron learns a linear function。

 assuming one exists of how each element of the vector affects the output stored in an internal weight vector。

 so we have a weight vector also that is going to learn。😡。

Now this is kind of looking like rangeren prediction now。

 input vector can be the global history register。😊。

And output can be whether should I predict this zero or one taken or not taken。

 and the weights essentially map to how each bit in the global history register affects the output。

So you learn the correlations between that bit and the bench you're predicting。That's the output。

 that's how you calculate the output， you basically multiply the weight vector。

 internal weight vector that you learn with the input vector X， and then there's a bias also。

 but you could remove the bias， we're going to talk about that briefly。😡。

And if it's greater than zero， you predict the branch， okay， in the branch prediction context vector。

 it is branch history your register bits。😡，I'll put this prediction for the current batch。

Makes sense。So this is the paper that proposes an HPCA to2000 month。

 it also won the test of time award in HPCA， it's used in many processors today， maybe not all。

 but many。Essentially， the idea is to use a preceptron to learn the correlations between branches to register bits and the branch outcome。

And a perceptron learns a target boolean function of n inputs so let's take a look at this this is oh it's animating something so these are the inputs x's and this is the bias bit and this are the weights over here each branch is associated with a perceptron if perceptron contains a set of weights which are shown kind of like this here each weight corresponds to a bit in the GHR global history register it represents how much that bit is correlated with the direction of the branch。

So if that bit is correlated positively， meaning if that bit is zero then。😡。

You will likely take the branch for example， you store a large positive weight associated with that bit。

 you learn this， of course you train this， there's some training algorithm that I'm not going to go into but you can read the paper。

😡，And negative correlation means you have a large negative weight。😡。

So you express the JHR global history register as one taken and minus one not taken and you take a dot product of the global history register and the weights and if output is greater than0 you can predict the take makes sense right。

 assuming you've done the training accurately。Corresponding。They will not go through this。

 but this is the prediction function， there's a bias weight independent of the history over here this encodes the bias of the branch。

😊，And there is dot product function of the GHR and perceptron rates and you can see that based on the branch address。

 you get a table of perceptrons which are the weights。

 you select the perceptron and you multiply it with the history register and then you get the branch predicted branch outcome。

And then there's a training function， these could be different types of training functions。

 but you can read the paper for more details。Okay， hopefully this makes sense at some level。

 right You could train a commution neural neural network also。

 except it's much more expensive to drain that thing even this is expensive， right。

 we were talking about。😡，Now we start talking about multiplications right now。

 right we were doing multiplication to predict the branch and you were saying this is a lot of area。

😡，Well there's more area coming basically and how do you optimize these multiplications， et cetera。

 right？😊，People implement。This exists。Okay。So advantages clearly there's a more sophisticated learning mechanism to get better accuracy and this is real when I was doing my PhD I implemented the perceptron because I needed better branch prediction accuracy as we will see later on and I immediately got a 20% improvement in terms of branch this prediction rate yes so when I talk about。

😊，Is this predictor actually trained like on the fly while yes， absolutely？Yes， it's all online。

There's all hardware for that。And so just start for like the entire program。No for each branch。

 basically for each branch， you have a perceptron so if you look at this table over here。Well。

 each set of branches， right， you have a hash function that takes the branch address and there is a perceptron associated with that。

对。😊，It can get better over time if there is this sort of correlation。

Okay it enables long branches to your length actually。

 this is better accuracy in a different way because your GHRs can be very wide right now。😊。

Assuming you can tolerate some sort of aliasing in this table interface in this table。

 you don't need a huge let's say two bit counter so now we don't have two bit counters as you can see right that's gone it's a different way of thinking about the problem。

😡，Which is what we should be doing， I think， going forward in the future。

Okay there are disadvantages， of course， clearly there's complexity。

 there's an add to compute the preceptor on output， meaning a multiplier， people try to simplify it。

 there's a lot of work that tries to simplify it， but it's still not simple。😡。

There's latency also right how do you get the latency because it takes time to actually do this computation right？

There's another disadvantage that later works actually try to fix perceptron can only learn linearly separable functions because of the way it gets trained。

 it cannot learn extra type of correlation， for example between two history it's a branch outcomes or it cannot learn everything nicely。

 let's say even if there's this type of predictable。😊。

Okay but this is a successful example of machine learning in processor design。

 maybe the only real successful example today， only is maybe too strong， for example， Samsung。

 this is an interesting paper because this is a product from Samsung。

 none of the authors are from Samsung because they disbanded their architecture team which was not very forward looking for them in my opinion。

 but they actually tried a lot of interesting things in this Samsung architecture including a Perceptron predictor。

 and another thing is actually one of the ideas that we had written in ISA 2007 that was called virtual program counter predictionction。

 a way of doing indirect bad prediction by using the conditional branch predictionor and not adding additional hardware。

😊，At least large amounts of hardware so there are a lot of innovative ideas in this paper including perceptra later AMD also maybe not later。

 but they're on the same time they developed its own perceptron predictor so you can see that there's a hash perceptron predictor which you're going to implement in your lab there's also a T which we're going to discuss soon so they actually had two levels of prediction。

😊。

![](img/41f97ad8c7218ec80efca8520c7479f3_3.png)

Over here， so we can see that the prediction logic is getting complex because these processor need better prediction accuracy for reasons we've discussed in the previous lecture。

😊，And you can also see that BTBs are also getting larger branch target buffers。

 right there are multiple levels of BTBs to predict branches。

So what does it mean to have multiple levels of prediction， essentially if you actually。

You have one level of prediction to quickly predict quickly predict whether the branch will be taken or not taken and you start the other prediction that takes longer and if the other prediction is more accurate。

 you basically flush the pipeline earlier based on the better prediction right the branch is still not resolved yet。

And then you may actually resolve the branch and then you figure out that you flush the pipeline wrongly or correct。

 yes。Well， again， you can keep counters。Yeah，'s very similar to what we have done with the hybrid bench predictor rate。

😊，Earlier。You can keep culture as to which one's doing better。

 which predict is doing better for example， Okay， so this is I'm not going to go through this。

 but this is from some it essentially shows that there is a table of perceptrons and Z2。😊。



![](img/41f97ad8c7218ec80efca8520c7479f3_5.png)

And I kind of like what they've shown over here， even though it may not be perfectly correct。

I think there should be a plus over here as opposed to multiplication。Okay。

Okay so the lab one is nice because you will get to actually progressively improve branch prediction accuracy and maybe come up with your own ideas。

 we already start with a two level global history predictor and then you implement a two level local history and then you implement a tournament predictor similar to Al 21-64 and then you implement a simplified perceptcom predictor and hopefully observe accuracy improvements right。

😊，And then you can actually exercise your creativity and come up with better predictors。

I think page already exists， but I'm going to talk about that。Okay。Okay。

 let me talk about another idea that she' has been quite successful and the idea I've already given you basically using multiple history lengths。

 essentially people have observed that different branches require different history lengths for better prediction accuracy。

😡，and the reason for this is actually based on the program because some branches correlate with branches that are very close to them in the program。

 some branches correlate with branches that are much farther away。

Imagine that you're testing a condition。😡，Here in the program and there's a huge loop with lots of branches and that condition was somehow set before that loop right maybe you executed thousands of branches。

😡，呃。Until you get to the branch that test that condition right for some reason it could happen so the idea over here is have multiple pattern history tables with indexed with global history registered with different history lengths。

 intelligently allocate pattern history tables to different branches。So it kind of looks like this。

So you can see that this is a PC based predictor two bit counters， potentially。

 it doesn't have any history。😊，You can see that there is one level of history over here。

 short history。And then longer history and then longer history and then longer history and these folks show that with geometric history lengths。

 geometric series of history lengths， you can actually get a nice predictor because you can cover a large set of history lengths。

😊，And they actually add tags over here you can see that basically so you hash the PC with history over here and then you tag it So what happens is how do you decide which one to use you use the。

😊，Well， there are many heuristics over here， but based on the confidence。

 you can have confidence that we will talk about later。

 but you could also use the history length that matches your tag， for example， right？

The longest history think that matches your ten so clear this comp is the prediction accuracy prediction right now。

 but it turns out this gives you a better prediction accuracy。😡。

And this was developed by Andre Sesnik and Pierre Michel and these guys are actually kind of magicians。

 in my opinion of branch prediction， Andre designed a lot of branch predictions of very different processors。

😊，But this is an example right you use this history length for a branch like this so use this history for a branch like this so use this history length for another branch that may be more difficult to predict again this is not the best picture but。

😊，That's the idea。So the advantage is you choose the best history length to predict each branch。

 hopefully best， this depends on how you train this thing， how you actually decide what to use。😡。

Hopefully you get better accuracy and again this is real you get better accuracy in real systems。

 it enables long branches steel lengths and it gets you better accuracy so previously perceptron enables long history lengths by having large weight vectors right here you enable long history lengths by having tags for example。

😡，Meaning you can have a 1024 history length over here。

 but you don't need to design a two to the one to 2024 entry2 bit counter right you have a small table。

😡，And hopefully you only allocate things over here when you don't have a good prediction over here。

 here， here， here， here， here， here， makes sense， clearly you need to take that into account。😡，Yeah。

 exactly， hopefully this is kind of the last resource。😡，But if you have a good classification。

 hopefully you've been the different branches to the right history length over time as you train things。

😊，Okay。Yeah， okay， so there are two advantages basically。

 you take advantage of the different histories， you also enable long branch history lines because of the design of the predictor。

😊，Of course it comes with this intervention it more hardware complexity。

 right you could argue which one's more complex， perceptron or this。😡，呃。

I think perception is a little bit more complex because of the multiplication。

 this is in my opinion this is easier to implement as a result it's implemented essentially all procedures today。

😊，I cannot say that for perceptron exactly， even though it has been very impactful。

 it still has these operations that are not， let's say that we want to avoid in general。😊，Okay。

 so the question， of course， is around is that design design space is large you need to choose good hash functions and table sizes to maximize accuracy and minimize la。

😡，And again， this is another successful recent idea。So as I said， AMD Zen2， starting with Zen2。

 they implement T as well in addition to perceptron and they use Tage as an L2 predictor。

 I don't know if they still do L2 meaning level 2， so if the perceptron is deemed to be not so accurate for a branch。

 they correct it using T。Okay， this is again from that picture， I think they you got this one， right？

Okay， so why do we do this actually people have analyzed this is a beautiful paper that looks at。😡。

Predictability of global bench so clearly it takes a global predictor you could implement a local predictor next to it。

 but I will not talk about that as we will see we'll talk about the loop predictors soon。

 but there's this paper that looked at a lot of programs at the time and it's tried to figure out which branches really matter。

😡，So you may have 1024 bits history going back 1024 branches for some branches。

 you need to go 1024 for some branches， the just previously executed branches is the one that really determines your direction or that really correlates most with your direction。

😡，the problem is you don't know which ones which right beforehand that's why you need to have different types of histories and for different branches you have different distances between correlating branches so if you're interested you can read this paper it's a beautiful paper。

😊，呃。不给。Question is， can we do better all the time， right？Okay， basically。

 this is the state of the arts in branch prediction， I'll give you two ideas。😡，呃。

This is from Andre Sesni again in Cha Branch Prediction 2014。

 which you could participate in after you take this class。

 you're very close to state of the art at this point， you just need to optimize things better。😊。

But basically what this does is it's an interesting predictor。

 it starts with a main page predictor using global histories。

 it gives you a prediction and some confidence levels which you will talk about how confident you are in the prediction basically and then it has a statistical correction mechanism that takes into account a lot of things global local and what equals skeleton histories you can read about that in the paper and then there's a loop predictor basically it corrects the prediction over here using some more information and then it decides whether it's a loop bench or not and then it decides a prediction so you can see that there's a hybrid predictor it's a little bit different from what we've seen in alphapha 21264 but the hybrid idea still exists over here and then there's some correction idea。

😊，Okay， and this is all open source you can actually， it's actually implemented in the。😊。

Lb one so you can actually use this if you submit this you'll get zero credit for them or the last portion because Do exists。

 but you could potentially improve it。😊，Okay。So people have actually started experimenting with more things。

 so after this there's been a lull in bench prediction in my opinion。

 there's works but nothing that actually had the impact that perceptron and T had。😊。

More recently people have started developing ideas this is not implemented yet because it's a bit complex I'll just give you the basic idea as opposed to going into details because the details。

 devils and the details actually and there are a lot of devils in these details in my opinion but basically it's good to experiment so these folks said that you could train essentially the problem is if you have a large noisy global history identifying the correlation between a branch's outcome and what it correlates with this heart。

😊，So， but we can potentially use identify these correlations with things that we know identify correlations nicely today。

 right， convolitional neural networks。You use global history to expose those hidden equations but only for hard to predict branches。

 don't do it for all branches， if the branches is not easy to predict。

 use a commvolutional neural network for it so this is trained offline so you actually set the weights offline because online training is very expensive and you hopefully assuming you set the weights nicely you get better prediction accuracy that's what this paper shows。

😊，And they use Tage SCL for all other brancheses， which is this。Yes。🎼So。

a couple cycles so just evaluate right yes so how do you manage to do that in one cycle Yeah well you don't necessarily do it in one cycle you need to do a lot of pipeing look ahead predictions so there are a lot of works that try to that's actually true not just for CNNs by the way all of the predictors like percept on T these are actually long complicated prediction mechanisms you need to do a lot of stuff a lot of tricks to get the prediction before you really need it。

So it can apply some of the tricks but CNNM makes it much worse of course right so there's something called multiple block ahead prediction。

 for example， multiple you try to predict branches ahead much longer ahead so that you overcome that latnt that's a very good question though I mean people actually deal with these things designing this predictor any of these predictors is not easy conventionalvolutional neural networks makes it much worse。

😊，Yes。Just have their own own people。They have their own units。

Customized hardware for French prediction， miss。Okay。Let me yeah， but this was fun。

 I mean people actually， this is one of the funnest part of the pro design。

Maybe except for prefeting， I'm biased。Okay let me finish these slides because we're almost at the end。

 I will cover very easy concept comparative toly the idea is branch confidence estimation so we've been talking about hard to predict branch。

 hard to predict branches one way of estimating English is using confidence this is actually an idea that was all of the 1990s also and the idea is to estimate if the prediction is likely to be correct how confident the predictor is in the prediction。

😊，Why， because this could be very useful in deciding how to speculate what predictor to use。

 whether you want to keep fetching on this path， whether you want to switch to some other way of handling the branch。

 like some eager execution or pre execution， many， many other things basically。😡。

So this is one example estimator but people have used more recently perceptron based estimators also there many different types of confidence estimator。

 sot very similar to what we have seen branch address， global ban register。

 you keep a record of correct and incorrect outcomes for the past and instances and based on the correct and incorrect patterns。

 yes if the current prediction will likely be correct or incorrect。

There are better ways of doing it today， which I am not going to so one thing that you could do clearly is selecting which predictedor to use。

 right？😡，But another thing that you could do is what's called pipeline gating。Which is a nice idea。

 it it's harder to implement today compared to 1990s because today processors are not that simple。

 let's say， and the idea over here is you keep track of how many branches that you fetch into the machine that are low confidence。

And if it's greater than some threshold， you stop fetching。So that you don't。Waste execution。

 you could switch another thread also， you could do something else， etc cetera。Makes sense。Okay。

 so this is my last slide， so if you're excited about this and if you enjoy the lab。😊。

You're actually going to be using the infrastructure that this championship branch prediction develop。

 you can actually compete among yourselves， but you can also compete globally by submitting to this championship branch prediction。

 the deadlines May 2。The goal of this championship branch prediction this is I think the sixth edition right last edition was I don't know how many years ago。

 maybe five，6，10， 16 okay， 10 almost 10 years ago， so I didn't guess completely wrong so this is to actually develop ideas in this domain and encourage new ideas so that we can make more progress。

So if you're interested， feel free to talk to us， we may encourage some of you if you actually develop a predictor。

 for example， in your lab。😊，So we're not done yet， but the bar is pretty high。Okay。

But we're done with the first part of the lecture。Now let's be back when the bell rings and then we can continue with prefe。

虽。这东西就不这公司也支持一公司可以。说。ButBut just have。嗯。あ yeah， so。I think it's。咁你先食。I don't trust this hard。诶系 c嗰啲。

あてし。for most of the workflows that go below go all 150 area instruction。这啊。

1 year has gone for gone through 68 million instructions。对对。Yes。However， I found out if I。

So if I were to set this to like 5000， let's not tryry my laptop。And run it。It's your point。太好了。Yeah。

就是。我 when系 did it in the morning系。quite worried about， worried about it， actually。一这。

But it goes up to like 50 watts power draw and heats up to 100 degrees almost。

The why don't smoke this mine。不。Specific。there is this。这个是強先す要しし欢だ。那个。

The phrase that was going for a。现月定最近。 so let's do this instead。那位。S that。This boxは。Yes是要。イナ。なち。嗯。

Yeah。lash but the wordlash。算那为 get。50 million。先 hell let's let's。I mean。

 I15 goes free and like I mean。嗯是 minus H。And the trace territory is。えさ刺リテ刺ビティ。所。嗯，你可。对。There we go。

ThatYeah， that。上不要。好。一两计息费训你几岁之出呢。By study fine。没有。I think we should increase the heartbeat now。

 because I think the print segments of the heartbeats are actually more detrimental to the context。

This is创。Yeah，s we're all the way through now。Yeahs time yeah， it's1。



![](img/41f97ad8c7218ec80efca8520c7479f3_7.png)

So， no all this time。It上。な接。这块关来的关系，因为。

![](img/41f97ad8c7218ec80efca8520c7479f3_9.png)

いや話だけ。这点。喂下。5 million。I think now that' where。Yeah。我就清。对。That will probably take minutes。

How bad it goes from my here tomorrow。第。嗯。What。Yeah and an edit。哎呀，只是所以还有一句话嗯。L it on my power bank。

Yeah， the only thing I'm really worried about is usually like the max core temperature。

It's because this one spiked one under。on this fact because I would it was multiing everything at the same time the time。

听说的我。Yeah， so this is hundred1 million。Actually， so I。

Like this power draw is probably profitable yeah。Okay。再刷一点。一番 finishはるです。Yeah。

 it should make sure all the ones that you seen。不 for这些。嗯啊，一个都有。Yeah， if it is finishing earlier。

 it's mostly because trace doesn those so that's right if it is going modulate。

going beyond mean fine beyond that because like this was added by me of course it maybe actually disregards this to change this is。

I， yeah， I mostly like， I would think because this was， I think it was added either。可唔可以睇啲。Oh。

 maybe I actually did the。 I' actually maybe rose five。

be a problemYeah it just came to my mind because yeah， because we almost miss as well。

 if you course write 500 million， we don't， don't pocket。

 that probably that's probably Maybe you can listen。P it somewhere it its 15 million and just Yeah。

 I think if it' is going to finish the So this is。Yeah， he said 50 million， yes。嗯Yeah，我。So half we。

And yeah， were2。5。 yeah， yeah and we， we were at 140 seconds so。

I'm reading a physical that something。I think I think it's那于 email的程序。嗯。

It's okays Okay lab I you I emailapp I hoping I。给给咱你我不要建是那那一层。

What's the I think I send it to my private email so was subject what's it。Oh。

 this is a the figure I created I I wanted to ask if this is like what do you imagine this thing number of the instructions that are。

Yeah， no， so like basically this is just like head up how many instructors were executed and here's the MPT Kae。

8 five。清楚。if you want to a the state of the simply the was a request so I'm saying if you just want to see what is which is simply cool down everything like everything we going to I mean。

 it's still not good there。曜ビカメラデスぱん。This， I think it have short in like 20 minutes or minutes。

 I sent you a helpful talk to that work。This is called Whatsapp for focus。Wait。

 they can actually tell you how long its took。The CSD is quite extensive。

So like you see here execution times。I mean， of course， you federalies is a。

Nothing better that point。Yeah， itcept。嗯。long long asm assuming its really big。Hello，Ex，Yeah。

 but like this， of course， is parallellyzed。 So it might be like maybe all this sum divided by8 because I think I。

结构。Oh， no， no。 this， this should。If you， if you use the script， it creates new threat。

 It bombs everything over you have into oblivion。 Oh， by the way， by the way， finish。没呃，招商。

呃43 million80 by。Last yeah。有有意。phrase X。Okay。🎼All right， so just。🎼Okay。Oh。No。We got the entire。

Is everything okay online？Yeah。How about now， can you hear？Okay。不不道。Oh， is all good， Everything good。

 Okay， okay。Let's get started though。他是一。Okay， now we're going to switch to pre fetching。

 but I should say that branch predictor design as you have。Be figuring out is not easy。😡。

It's a very tight loop， especially at higher frequencies lower clock cycle times。

 how do you get that next prediction in a single clock cycle is not easy and it's difficult in general。

😊，Sometimes you may get bubbles， so it's good to have a predictor that can make a quick decision。

And then another level of predictor that can make a correction。

 and then maybe another level of predictor that can make another correction。

So you normally have in existing processors， multiple。

Different places where you flush the pipeline based on a potentially incorrect prediction。

 not just one place when the branches is resolved， but their intermediate steps where intermediate。

 increasingly better branch predictors make a better prediction。Okay。

 now we're going to switch gears and talk about another fundamental problem， which is prefeting。😡。

But I will motivate it with other things， okay？没。I kind of use memory latency problem over here。

 but you can ignore memory ignore latency。And then it becomes a problem。

 and that's the problem we're going to focus on the problem。

Whi is the real problem that we have in our systems today。

 how do we get rid of this thing and take okay it got rid of itself。😊。

You can call the latency problem， you can call the memory problem。

 or you can call the memory latency problem or you can call it the problem。😊，Pick your choice。

So basically memory latency lags behind， this is across let's say， 18 years of DM improvements。

 capacity has been improving， bandwidth has been somewhat improving。Latency has not been improving。

And these are real DM chips， I'm going to show you a better picture and refer you to paper。

And as a result， we are not able to feed data nicely and we cannot tolerate those latencies easily this is actually a study of 54 years of chips gear and chips。

😊，And I would recommend that paper if you're interested， this was done by Minsh Patel。

 who was my PhD student who' a professor at Rutgers right now。

 but basically you can see that capacity has improved pretty well over the course of 50 years。

That's a millionx capacity improvement on a DM chip。People have tried hard。

Kind of slowing down a little bit， but still people are pushing it。

And this is what happened to latency。8x latency improvement over the same course of 50 plus years。

A million x plus versus Ax。And more recent years， last 20 years。

 you can see that this is almost constant， some of them are going up。

So latency has become much harder to improve， partially because it's fundamentally harder to improve。

 the technology is not necessarily on your side and also because interconnects are not scaling as well as logic。

 let's say， or even the capacitors and also it's a design choice that people make because cost per bit is what drives the industry with a mindset。

😡，And latency is not the driver， let's say okay， this is a paper。

 if you're interested in all of that data and more， Id recommend looking at that paper。

Okay memory latency is clearly critical for performance。

 we're going to later see lectures on processing in memory et cetera， we're not going to do that now。

 but it becomes a performance bottlealneck and there are papers that are showing that this becomes worse with some new DM types because some of the new DM types actually increase latency so that you can get better bandwidth anyway。

😊，Like again， you can look at some of the papers。Okay。

 let me give you an overview of techniques you probably have seen caching in previous courses， right？

😡，Yes， you're a bored of caching。Somewhat okay if you're bored of caching， don't be bored。

 there's more to be done there。 Last week I was at the HCA conference highperforms Comp Arch。

 one of the major conference in architecture and IM had a nice paper and the industrial session on their Z series architecture IBM Z series is really on these are processors。

 very expensive processor like you buy racks of these$5 million or more and they're supply to banks。

 for example， transaction processing machines essentially。

 and the goal is really to get highper as much as possible。

 and these are heavy autoor processors with a lot of branch prediction techniques。

 a lot of prefeting and many levels of cash hierarchies like on L2 L3 L4 and they have virtual caching etc。

 there are a lot of interesting issues I recommend that paper for you to look at。😊。

So they are gigabytes of caches， essentially on chip because they actually coordinate many chips to actually form a large cash。

 large L4 cash。 Okay， I'm bored of caing。 So I'm not going to talk about caing。

 but I'm going to give you a quick overview of these techniques。 So basically。

 there are fundamentally three ways of reducing techniques in my reducing latency or handling latency。

 One is reducing the latency as much as possible， fundamentally。😊。

This is a more data centric approach， I'm not going to talk about that in this lecture。

 but if you're interested， look at the lectures we have in computer architecture classes。

 how do you reduce latency and I think this should be done more and more。😡。

The other technique is hide the latency seen by the processor。

 there' a more procentric approach because the latency is there。

 but you're trying to hide it as much as possible right so you do caching for example。😡。

And as long as you can fetch the data from a cache that is closed by processorer。

 you don't see the latency because you're not accessing that part， you do prefeting。

 which we're going to talk about。😡，Or there is another approach which is tolerating or amortizing the latency seen by the processor again this is very prostcenttic multi thread is one example。

 you still have the latency box。😡，By by doing something else like executing some other thread。

 you hide that latency from the system， let's say Auto execution is another way of hiding latency right that's really hiding latency。

 the latency is still there。😡，Me it could be a memory latency。

 it could be a floating point operation latency， but you hide that latency by executing something else while you're waiting for the data dependencies to resolve Well we're going to talk about run execution which is also a to mechanism。

😡，Okay， so this is actually from my PhD thesis defense and proposal， I worked on this topic。

 multiple of these topics actually， but there are multiple techniques caching we're going to talk a little bit about and then I'm going to refer you to lectures and then we're going to jump into prefeting。

😊，caching is a reactive technique， meaning you bring the data into a cache and then based on a demand request and then you try to exploit that data for other instructions that may use that data。

This is a reactive or passive technique， you don't proactively bring the data。

 so we're going to talk about proactively bringing the data。😡。

The people have optimized caches a lot over many years as you can see and all these ideas are developed actually into the 1960s。

 Wilke's is not the first paper but Wil's is the first paper that's very， very clear。😊，Okay。

 so a prefetch thing， we're going to talk about this。

 multi threadreading works well if there are multiple threads。

 but it doesn't help single thread performance and improving single thread performance using multi threading hardware as an ongoing research effort。

 which is not easy。😊，An automotive execution you've seen already， hopefully you loved。

And hopefully you're excited about implementing out order processors。Maybe。

So Out ofboard execution Act requires extensive hardware resource for tolerating long latencies as we're going to see。

 so let me talk about caching a little bit and there are many lectures on these topics if you're interested。

😊，So this is a modern memory hiery today。😊，Again， orders may change actually。

 but well the exact numbers can change， but you have levels and levels of caching today over here。

 right？😡，The closest caches to the processor are very tightly integrated。

 in fact L1C is really part of a processor today because you need data supplied to the pipeline extremely quickly and the design choices that you make in L1c are usually dictated by how you design your pipeline。

After that it becomes decoupled out of the pipeline and becomes part of your more encore hierarchy。

 so L1C are small but fast L2 cache are larger and slower and as you get to higher levels than the hierarchy you get larger capacity but larger latencies as well。

This is another picture， of course， when you could keep showing these pictures I has nice pictures in their HPC paper if you're interested。

😊，Okay and we actually keep adding more and more levels to the hierarchy。

 you could for example have a DEM that's a cache to some other type of memory or different types of DM or you could have different types of DM that are not necessarily caches to each other。

 but one of them is small and one of them is large we may see this later on so essentially we keep extending the memory hard and the reason I'm telling you all of this is because caching and prefiing principles applied to the management of all of these later go。

😡，Okay， so these are some slides from my DDCA lectures。

 let's talk about caches quickly so that you've seen set Associative caches， for example。

 at4way HY Associative caches， I like thinking of set Associative caches as systems where each block has a priority level in a set。

😊，It indicates how important it is to keep the block and the cache， right？😡。

And the key issue in general in caching is how do you determine and adjust the block priorities。

 right？So there are usually three key decisions you make in a set， when you insert the block。

 when you promote the block， I mean you evict the block or replace the block insertion is what happens to the priorities on a cache fill。

 you're bringing a new block into the cache。😡，What do you do what do you do to the priority of that block and every other block right。

 how do you sort it out clearly you've in LRU， for example， least recently used mechanism。

 that's one way of managing priorities。😡，But you could also decide not to insert the block into the cache because you have a predictor that says。

 oh， I'm not going to reuse this block， so let me drop it。😡。

Well let me drop it from this level of the cache， maybe I insert it in some other level of the cache。

 right？So where do you insert the block， what's the priority level？😡。

There are a lot of papers that talk about these things clearly promotion is what happens to priorities on a cash kit。

Basically， whenever you have a block that you access and it's in the cache， what do you do。

 do you promote that block to be the most recently used？😡。

Meaning the highest prior to keeping the cash or do you take some other action there are different policies over here again。

 which I'm not go into here， you could do random。😡，Clearly， con randomly change the priorities also。

Which may not work too badly actually， if you're thrashing the or cash。

People have shown that LRU is not the best mechanism if your cache is a really trashing。😊，Okay。

 evictionary replacement is whatever the priority is on a cash miss。

 which block do you evict and how do you adjust the priorities after eviction？😊。

So in DDC we cover some of these， I'm not going to cover this and you probably covered some version of this at least in your previous class where you learned about caches。

 but in multilevel caches you have other design decisions as about which level do you place the block into from memory。

 you bring the block for memory， which level L1 L2 L3， L4， where do you place maybe all of them。

Maybe none of them maybe a combination of them right which they will do you evic the block two from an inner level so if you're evicting something from L1 cache because you don't have enough space in the L1 cache do you drop it do you write it back somewhere else okay so basically you can bypass the levels not bypass levels there are many design decisions in a multilevel cache hierarchy also in addition to the design decisions that you have inside a single level right。

😡，Okay， so there you may have also seen inclusive， exclusive， non inclusive hierarchies before。

 yes or no。Okay， very briefly again， there's no magic over here。

 but inclusion a means that a block in an inner level cache is always included also in an outer level。

😡，Meaning any block that's an L1 is also an L2， any block that's an L2 is also an L3。

 any block that's an L3 is also an L4。😊，And hopefully in memory also love them yeah basically this simplifies cache coherence if we talk about cache coherence you will see that exclusive means a block but of course inclusive is not good for your replication you replicate the data many times across many levels so you're not utilizing your chip space nicely。

😊，Exclusive means a block and an inner level does not exist in an outer level， so L1 is exclusive L2。

 which is exclusive L3， which is exclusive L4。😡，Hopefully memory includes all of them though because memory is where you get the blocks from。

 right？And you could imagine a system where memory doesn't include that and you go to storage right。

 so memory you could be exclusive storage， but that's a design choice that people have not done taken yet。

But basically the exclusive is good because it better utilize the space in the entire hierarchy。

 there's little redundancy， but it makes cash Cos harder because you need to check all of the caches for keeping them current。

😊，Most processors today use a noninclusive approach or an exclusiveive approach。

 a block at an inner level may or may not be included in outer level。

 this relaxes a lot of design decisions like prefetching， for example， when you prefetch something。

 you evict a block， do you write it back somewhere else。

 you actually don't need to make a very strong decision to keep inclusivity or excluusivity。😡，Okay。

So there are a lot of works that try to improve cash performance， which we're not going to cover。

 but this is just to show you that this is also our rich area， yes。😡，non or with exclusive policy。

 it's clear like with the non inclusive policy。If the album entry is the newest entry。

 and maybe L two has an older entry that hasn't cleared yet。What happens if L1 entry gets cleared。

 sometimes it cleared pretty randomly。This would be wrong Well， all of these policies。

 you need to make sure correct me straight。If your L1 has a dirty data。😡，呃。

You should propagate it to memory in some way。Maybe you don't write a deel2 you need to emate deel2 so there's a queryance problem that you need handle yes so I'm assuming that there's a way to maintain correctness Yeah。

 you need to update basically。Okay， so there are a lot of ideas， again。

 some of which we cover in other courses， including DDC if you're interested you can look at DDC。

 but there are also other courses that we have on cash optimizations I'm not going to do that。😊。



![](img/41f97ad8c7218ec80efca8520c7479f3_11.png)

![](img/41f97ad8c7218ec80efca8520c7479f3_12.png)

Unless you really want to do that。But I'm going to jump to prefech， makes sense。😊。

Cashching is an area that there's been a lot of work on。Like it's at some point。

 the international symposium on computer architecture was called international Sposium on Cash architecture。

There were so many papers on caches， okay？Pre fetchting， okay。

 pre fetchting is a more proactive approach， meaning you try to fetch the data before it's needed by the program as opposed to relying on demand requests to bring the data that's why it's called a pre fetchch or pre load。

😡，Because memory latency is high and if we can prefetch accurately and early enough。

 it can reduce or eliminate that latency height， that's the hope。😊。

It can eliminate compulsory cachemist as you may have heard of compulsory cachemistes compulsory means basically it's a cacheist。

😡，That you have to have assuming what you're doing is only cashing if the demand miss your cash doesn't have it yet。

 so you have to wait for that to fill the cache。😡，It can also eliminate all misses actually。

 like capacity means you don't have enough capacity in your cash， conflict means conflict mismean。

 you don't have enough ways in your set in a single part of your set。

 coherence means you get a cash miss because some other processor invalidated your cash block。😡。

Prefeting can actually handle all of these。😡，If you design the prefe nicely。

 let's say it can target coherence versus it can basically can it can fix all of these。But of course。

 you need to predict which address will be needed in the future。😡。

Which of course means that this works if programs have predictable misad patterns。

 then the question is what does that mean， what's a predictable pattern， right？😡，Okay。

Now you can think about machine learning also to predict and we're going to do that also a little bit Okay。

 so one thing to keep in mind is as opposed to branch prediction which we have studied and this prediction prefeing doesn't affect correctness。

😊，You。Basically you get a wrong address， wrong data， but you simply don't use it。😡。

Does that make sense？Of course， you should not prefetch basically。え。

You should really not change the state with prefeting， change the architectural state with prefeting。

 this is assuming that you don't change the architectural state。😡，As a result。

 there is no state recovery， but if you mispredict the branch， for example。

 you go on the wrong path and you have to recover to go on the correct path again here you just simply don't use the data that you fetch。

😡，Okay。So in modern systems， prefetching is usually done at the cache block Gr la because we have caches and you try to prefetch blocks。

 essentially。😡，But it doesn't have to be that way also if you have sector caches for example。

 where you have smaller sub blockss， you can pre subbs， etc ce。

 it's a technique that can reduce both missrate and mislatency of caches and it can be done by anyone essentially it can be done on hardware we're going to look a lots into hardware。

😊，But it can be done by the compiler， programmer， or the system。😡。

It can be done at a higher level also right for example。

 we have operating systems and operating systems actually manage a lot of programs before I launch a program it may already prefetched the programs data that it expected me to launch at this point in time right Windows for example at some point had a sophisticated machine learning based prefecher that tries to predict what program a person is going to use and preloads that the data pages of that program from hard disk into the main memory。

And you can do that clearly at the system level we're going talk a lot about hardware in this course this is a very old paper that we wrote 2005 just to show you that prefetcher can be anywhere in the memory hierarchy and today we have prefechers everywhere in the memory hiarchy there's an example over here we were looking at stream prefeers I'm going mention that later on it basically monitors access coming into an L2 cache it also looks at what is missing in the L2 cache and it decides what to start prefetching at the lower from the main memory into the L2 cache for example。

😊，Well you could imagine prefetures everywhere in the system。Okay。

 there are four major questions in prefeing， I'm going to go through these and then we're going to talk about some prefeting algorithms。

 what， when， where and how。isWhat addresses do you prefetch。

 what is your algorithm to decide which address do you per when do you initiate a prefech request。

 are you early， late or on time？😡，Hopefully early。Or on time on time is the best actually。

 not even early， where means multiple aspects of where where do you place the prefash data。

 do you put it in a cache or prefit separate buffer。

 most processors today use caches because separate buffers complicate the memory hierarchy。

 which's already quite complicated。😊，Where do you place the prefeture。

 which level in the memory hierarchy today essentially we have prefettures essentially everywhere。😊。

You can add prefetures from into the L1 cache into the L2 cache into the L3 cache and also in the memory controller on the memory site a little bit。

😊，And then how is， how does the prefeture operate and who operate？😡，Is it the software。

 is it the hardware？Is it a hybrid mechanism， is it execution based。

 we're going to see some examples of this。Does that sound good。

Now let's tackle these questions a little bit more。

 so what address do you pre because this is critical in the end？😊。

If you don't prefech the correct address， you're wasting resources。😡。

Many resources that are critical， like Memi bandwidth。Cash or prefetched buffer space。

 energy consumption， and these could all be utilized by demand requests or more accurate prefetch requests right that's the idea over here you don't want to waste these resources。

😡，So accuracy is very important in prefetching， this is accurate prediction of addresses to prefetch。

 prefetch accuracy that will find us what is the fraction of prefetes that are used by the program divided by the total number of prefetes that you sent ideal you want this to be 100% but unfortunately you don't get to 100% unless you're very conservative and when you're very conservative。

 you may not be able to prefetch much。Okay so how do we know what to pre-fetch one way of doing this is to predict based on past access patterns right and we're going to see a lot of that or you can use the compiler's programmer's knowledge of data structures such that you can create a thread for example that does prefetching for the main program you can have a separate thread pre-fetching for the main program they're running on the same core or different course and one of them is pre-fetching into the cache before the main touches those blocks right that's certainly possible you could have purely software methods of doing that or hardware software cooperative methods of doing that。

😡，So a prefeing algorithm determines what the prefetch， we're going to see some examples of this。😡。

Including some things that are implemented in existing processors。Okay。

So let's go through this exercise how predictable are these access patterns。

 the first one hopefully you can predict what's coming next right a plus5 six。😊。

Hopefully you can predict this one also plus 42 so this is called a strip here you have a stride of one these are again these assume that these are cache block addresses and the process touching cache block addresses Aa plus 1a plus 2。

😊，So the stride is one here the stride is 42 and you can easily design logic to determine the strip。

 it's called the stride detector essentially。A little bit harder but also predictable， hopefully。

 so what do you have here plus two plus three plus four plus two plus three plus four？😊。

And it keeps going。So now you can actually have a way of predicting the deltas。😊。

The pattern plus2 plus 3 plus fort right。Okay， this is a bit harder， maybe。

At least you can get some patterns like I see X， Y， T， X， Y， T， X， Y， T， X， Y T。

 at least when I see X， I can bring Y and T， even though these address may have no stripe。

Asssoiate with them， right？Now think about the hardware implications。

 a bit harder to design hardware for， right？Okay， and then another one over here。

 which I'll let you figure out， but this is also doable I believe。

The interesting thing over here is A Z and P may have nothing to do with each other。

 but you're really touching。The same set of deltas from that base right you have a base A。

 Z and P assuming you figured out that。You're touching these deltas。Whenever you see Z。

Something totally different from a， you give these deltas and prefetch all of them at the same time。

 potentially again， this requires recording of these deltas。Okay。

 so all of these are predictable as you can see， except this is the hardest one， I would say。Okay。

 so let's think about now algorithms to prefe them let's move to when when do you initiate a prefetch request again I'm not going to give you answers over here。

 but there are tradeoffs associated prefetching too early least prefetched data not being used before it's evicted from caches for example。

😡，Prefetaging too late might not hide the whole memory latency。

 so you need to find a sweet spot to initiate the prefetch rate。😡，This is called timeliness。

 essentially when a data item is prefetched affects the timeliness of the prefetcher。

 and ideally we want perfectly timely prefets that bring the data into the cache right before the processor needs it。

😡，Prefe can be made more timely by making it more aggressive。

 meaning you try to stay far ahead from the processors demand access scheme。😡，In hardware。

 or you move the prefetch instructions earlier in the code， if you're doing software based prefeting。

 you normally have prefetch instructions。😡，And that goes earlier or if you're doing a thread based prefetching like I gave you an idea of you could launch the thread much earlier。

 of course the downside is if you do it earlier then you may not get to the。😡。

thinghing that is going to access that data right？Because there are branches in the code right， okay。

 let's take a look at this aggressiveness in this picture。For example， here。😡，You may say， oh。

 I'm going to be very aggressive， so I'm going to predict that this stream is going to last。

 I don't know， up to a plus a million。😡，And you keep generating prefetches。Early on。

 right a million prefes， and then the processor stops at a plus four。Sounds pretty aggressive， right。

 so that's hopefully that gives you the idea。You could do it with all of these excess patterns actually。

 you could multiply the stride by number of times you generate the request by adding that stride to the previous thing that you generated。

Okay。So that's one essentially。And people struggle with this when they design prefets okay where there are multiple aspects of where where do you place the pre-fetch data you could place it in cash or in prefetch buffer Ca is simple。

 no need for separate buffers， but of course the downside is can useful demand data it could cause cash pollution so people develop techniques to decide where to insert the prefetches so everything that I said promotion insert and eviction is affected by whether you're putting a pre-fetch into the cash right that affects your demands that affect your prefetch is also。

😊，Alternatively， you could make it clean and put things in a separate prefetch buffer。

 which protects the demand data from the prefetches。😡。

No cache pollution in this case so basically evicting useful demand data is called cache pollution unfortunately there's a lot of downsides over here which are kind of partially listed your memory system design becomes more complex where do you place the prefetch buffer if you have multiple prefeedgers do you have multiple pre-fetch buffer When do you access the prefetch buffer do you access parallel or a serially with the cache When do you move the data from the prefetch buffer to the cache。

😊，And there needs to be altered paths to do that how do you size the prefet buffer if your pre as aggressive this buffer becomes as big as the cache actually so there are a lot of issues over here and keeping the prefetch buffer coherent is probably the easiest one among these issues frankly so this is not done in general。

😡，Many modern systems place the prefeched data into the cache in the end because of all of these headaches。

😊，Okay。There's also which level of cash to preft and the answer to is。😡。

You can prefetch to almost every level， potentially using different prefets， right？

So you can see from memory to L4 L3 L2 or memory to L1。

 L1 is a bit special because it's very precious in terms of capacity。

 normally people use separate prefes into L1， but there could be separate prefe into L2 also because L2s are also quite small today relatively right things are becoming larger relatively but L2s are quite small L1 is the most precious thing because in the end L1 is really dictated by the pipeline design decisions that you make。

Okay， and then there's the where to place the prefash data in the cache we kind of talked about that briefly。

 do we treat the prefsh blocks the same as demand fetch blocks， bad idea in general。😡。

Because prefetch accuracy may vary， so you may want to actually decide the priority of a block based on the prefetch accuracy。

 for example， or timeliness， or you could use multiple metrics。呃。

And prefesh blocks are not known to be needed， for example。

 with LRU a demand block is placed into the MRIU most recently used position， is that a good idea。

 even processors that use very simple policies like LRU policies don't place the prefetes into the MRRU position when they bring the data。

 they put it somewhere else in between。😡，Okay， so you can actually skew the replacement policy such that it favors the demand fetch blocks in some ways。

Okay。Then then there's another aspect of where where do you place the hardware prefeture in the memory heartarch right again it could be everywhere in other words。

 what access patterns does the prefecture see L1 hits and misses L1 misses L2 misses again you can generalize this to anything。

😡，The key distinction I think is you see what kind of access pattern does the prefeture see if you。

 for example， see every axis that is made by the processor you see a complete picture。

But that's a lot of bandwidth also that you need to deal with because the processor is generating addresses every cycle。

 multiple letters， every cycle， actually。And if you have an aggressive process。

 but seeing a more complete access pattern can give you potentially better accuracy and coverage。

But pre needs to examine more requests， so it becomes more complicated to keep up with the processor。

😡，Seeing a less complete access pattern may not be that bad。

 you can find predictability because what happens is as you L1 cache sees all the axises from the processor right L2 cache sees a filtered set of accesses filtered by the locality that you can exploit in L1 L3 cache sees an even filtered set of accesses and the memory control sees an even filtered set of accesses so you can think of caching also the same way right。

😊，It makes no sense to have the same policy that you use in L1 to be replicated in L4。😡。

Because these are very different types of locality that you see actually。😡。

One is very filtered locality， the other is everything that the processor touches。

 so think about that's why existing systems use very different policies at different levels to manage the caches。

 although those promotion insertion eviction policies that I mentioned are different at different levels。

So a prefeting could be different also， and it is different actually。Okay。

 so this is our modern memoryarchy just to。Comp what I just said over here。

And then there's more memory and then there's more memory actually， today， data centers， for example。

 they don't stop at local notes。😊，If you don't have enough memory in a local note， well。

 why not have a remote node supplying you with more memory。😡。

This is what happens in large scale data applications， this is just to give you a bigger picture。

You may actually have a dissegregated memory also remotely。

 but this doesn't have to be disaggregated to be some sort of memory blade。

 or it could be some other node that supplies a little bit more memory。

 which is what's done in the IBM paper that I actually mentioned in HPCA。

 so a memory arc extends beyond a single server enables higher capacity。

 but now you have a prefeting another prefetching problem right？

If this processor touches something remote。How do you get it over here as soon as you can， right？

Okay， there are a lot of interesting papers in this direction if you're interested。Okay。

Now let's talk about help。How is also very interesting。

 you could also have a combination of all of these， but there's software prefetching。

 which I will spend less time on。😊，Because it's very hard to get it right in today's systems unless you have very。

 very regular programs。Hardware prefetching which is what's done in most systems today。

 well essentially all high performance systems today。

 and then there's execution based prefeting which is actually very interesting because it covers a lot of different things okay software ISA instructions that architecture provides prefet instructions and the programmer or compiler insert prefet instructions into the program。

This clearly requires some effort， right？And usually this works well for regular excess ps。😡。

Hardware you have specialized hardware monitors memory accesses coming from the processor。

 and basically whatever you pick memorizes finds， learns， add strides patterns or correlations。

And generates pre prefeched address automatic software is not involved in pure hardware mechanisms。

 right？😡，Basically hardware needs to answer all of those questions when do I generate the prefet request how aggressive I am。

 what kind of things can I detect et cea， execution based。😡，You could think of it as pure software。

 it could be pure software， it could be pure hardware， it could be hardware software cooperative。😡。

That's why I call execution based， but essentially what distinguishes these from these other ones is you execute a threat。

😊，ASoftware thread。Or hardware threat that could be invisible to software and to the operating system。

 potentially to prefesh data for the main program。😡。

It can be generated again by the software programmer or hardware and we're going to talk about that my PhD thesis was actually on execution based prefeting we'll discuss that so this is a prefetch instruction x86。

😡，呃。It's complicated。This is from one version of X easy6。

 essentially you can see over here move data from M closer to the processor using some hint。😊。

Kend of doesn't make sense if you read this right T0 hint T1 hint T2 hint and NA hint。😊。

And if you look at the description， it also kind of doesn't make sense， I mean， mostly art。

 for example， temporal data。😊，Prefched data into all levels of the cache as。😡。

In Pentium free processor。First or second level cash。

In Penium for Intel Zon processor second level cache。

 clearly the first double cache is not part of the all levels of the casher key。

 so this shows you that people are actually a little bit confused in the specification for a good reason because。

😊，It's hard to let's say relinquish control to the software completely as a hardware person doing this ISA description right so basically your goal is to enable prefetching from the software but again in at least in this particular description of the ISA you don't get a lot of control you cannot basically prefetch into the second levelve cache in later processors in earlier processor maybe you could。

😊，Okay。And essentially， they look kind of the same， right？Okay。

 but basically you can use these instructions and these instructions are non blocking in general。

 they generate a prefetch request and they don't stall the instruction window。😡。

Because they don't prefe data into our register， there's no register dependencies and in many cases。

If the architect。Is having difficulty getting the system right， they drop these instructions。

So you may actually insert a prefetch instruction in your program and the architect says， oh。

 this is not something I have to execute。Let me drop it。😀Yeah。😊，It happens， these things happen。

And there's a good reason for it。 Well one of the issues is basically software prefetching。

 even though it's been developed it has not been as successful because it's very hard to like I would recommend you to watch the EDCA lectures because we don't have time but because it's very hard to get it right。

😊，Where do you insert this prefet request right a lot of things is dependent so you have a program you need to fetch some data and you need to decide where to insert the prefet request the distance between those two instructions is dependent on the memory latency effectiveness of your caching all of the latencies that you experience or interconnect so it's very hard to decide a good distance in the end。

Unless your program is extremely regular and you actually control the caches using tiling blocking。

 etcter， so it is possible to do that but then。😡，Maybe you do better forms of prefeting right you don't need these pre fetch instructions potentially。

Okay so this is a hardware prefeure which we will talk about this is streaming prefeture again this is a high level concept over here and the idea is the processor is touching line zero line1 therere in L1 and the processor detected a stream so it keeps prefeting line two line3 line495 and then。

😊，The remaining lines from the memory， so it's really streaming data。

Initiated by the core for the next lines。This is streaming because the stride is equal to one。😡。

Stripe could be something else， and you could still be streaming with a larger strip， right？

So this is actually implemented in IBM Power， they have a nice paper about it when people used to write papers about processors。

 it's actually a very nice。Long paper about the power for micro architecture if you're interested。

 can look at it。Unfortunately， IBM stopped doing this Journal of Research and Development。

 which was actually a really nice resource for everyone。No。

So you cannot read about their latest postures except for the industry session of HPCA。Okay。

So this is where the stream prefiing idea was developed。

 this is a beautiful paper by Norm Juopy and again it's the same idea that is implemented in this processor and many other processors one of the reasons I am showing you this paper is basically to show you what things were like so these are times in 1970s VX was the king of processors at the time it built a lot of autoor processors you can see that the cycle time is 200 nanoseds over here cycle for instructions is 10 at the time memory time is 1200 nanoseconds and misco as six cycles。

😊，And misco in terms of instructions， 0。6 instructions。

 so instructions executing the process were actually cheaper。😊，N MM access in terms of latest。

 if you think about it。Over time it became much worse。

 so this is what the this thing is designed for stream prefiting。

 WI Western Research lab Titan processor this course about 12 cycles and in terms of instructions at 8。

6 instructions and the projection is 140 instructions so this IM paper at HPCA there many access latencyencies is about 700 cycles processor cycles at a 5。

5 gigHtz processor。😊，That's a very long memoryac latency。

And he said that they could cut it by probably 200 cycles if they optimized things。

 but not lower than that。So think about that today we're at actually at least 500 cycles when I was at Microsoft at Xbox 36。

 your memory latency is 650 cycles。😊，For a slower posture of course not 5。

5 gigertz but still these are very long latencies today so we are actually at a point where latencies are a bit crazy so this is an example of execution based prefeting these are actually a real ideas that have a real impact as you can see some implemented a version of what we have proposed in my thesis or papers actually before my thesis and they basically show that you can get better performance by keeping the same cache size or you can keep you can have a prefecure implemented with one megabyte cache and that gets you the same performance as an 8 megabyte cache without a prefeure so prefeure is a good way of potentially reducing your hardware complexity right as opposed to implementing higher and higher。

😊，Cost caches， maybe you design better and better prefet except that way you don't need to store out my state Again。

 we're going to talk about the scout， but this is essentially run at execution。

 But I think the reason I show you this。😡，Heres multiple reasons。

 one is execution based prefeatures exist， hardware based prefetures exist。

 software based prefeatures exist。😊，Effective pre and also the second reasons effective prefeting can improve both performance and reduce hardware cost。

😊，Make sense soft， right so the hardware you're spending on things can actually be。😡。

Buying your hardware somewhere else， right？Okay let's talk about metrics a little bit I mean the ultimate metric is really perform energy in the end right but there are auxiliary metrics that you use to try to optimize a prefeure potential right because ultimate metric may not be easily optimizable without knowing what's going on underneath right so accuracy we already discussed right the used prefech is divided by a cent prefes coverage is also important。

😊，What is the fraction of misses that you correctly predict out of all the misses that are generated by the program。

 right？😡，Ideally， you would like that to be 100% also， you would like 100% accuracy， 100% coverage。

 perfect timeless。😡，You cannot get all of them unfortunately， you can get maybe two out of three。

Okay， times， it could be defined in multiple ways， but they're very strict definition is。😊。

The fraction of one time prefets divided by total number of prefetches that are actually needed by the processor。

That's a strict definition， what is on time right it's actually in the cache when I when the processor access it。

 that's one definition。This doesn't cover the cases where。

The data was just being put in the cash one cycle after the processor needed it right so there's actually coverage in terms of time also。

 but there are multiple metrics there are also other metrics like bandwidth。😡，This is。

How doHow much usually prefeting increases bandwidth because you're not perfect accurate right and this is the memory bandwidth consumed with the prefeure divide by memory bandwidth consumed without the prefecher。

😡，Now this is not always bad， increasing the memory bandwidth is not always bad because if your bus bandwidth is id。

 sometimes you can utilize the idle bandwidth to do prefech in many systems today it may or may not be the case。

😡，呃。So don't count on bus Ben with being id。Especially in data intensive intensive of programs。

 so if you talk about cash pollution also these are extra demand misses due to prefetch placement in cash。

😡，It's more difficult to exactly quantify， but it affects performance because it depends on the time window you're looking at。

 right？😊，But it's possible to quantify approximately so these are all auxiliary metrics to keep in mind and if you have a very aggressive prefeure usually your coverage increases。

 your timeless becomes better， your accuracy tanks。Your bandwidth consumption increases。

 your cash pollution increases。If you are a very conservative prefeture。

 your accuracy may be almost 100%， your coverage is low， your timeliness。Not so good。

 probably your bandwidth consumption is good， cash pollution is good。😊。

But you're not getting much performance right so basically deciding on the aggressive of the prefecure is important。

😊，Okay， this is one paper that we had written， we're going to talk maybe more about that。

 but this talks about a lot of these metrics and how to use accuracy coverage， mainly the accuracy。

 timelines and pollution to decide where to how aggressive you should really make your prefeture and also where should you insert your prefetches into cache。

So I can dynamically adopt all of those。Any questions？Okay， so let's not talk about。

 we kind of talked a lot about theory，'s let's talk about some mechanisms。😡。

So I'm going to start with stripe prefeture， we're going to detect the stripes and you can already imagine a circuit that detects this basically the idea of this prefecture is to record the stripe between consecutive memoryaces。

😡，And if the str is stable， so you have some confidence mechanism again。

 use it to predict the next M memory axis。😡，AndIt depends on your algorithms， right？Okay。

 sounds simple， right， you build confidence， for example， you record Aa plus n and you say， oh， okay。

 the stride is probably n， but I'm going to wait。😡，And then you see the strip n again。

 you increment a counter saying that I saw the strip twice， well I'm going to wait。

You saw the strike three times okay， something is happening I'm going to pre fetchtch next next M incarnations of this strip okay so that's one way of doing it now even this actually has multiple versions。

 let's say。😊，You can determine the stride on a per instruction basis so you can do this for every PC program counter or you can do it on a per memory region basis right and these are different implications so this is instructionbased strip prefetching essentially you have a table that's indexed with the program counter and you have a tag for the program counter you look at the last address reference cache block address again for that program counter and the last stride that you've seen and you have some confidence level that I just mentioned so if you keep seeing the same stride for the same PC your confidence level increases and you keep generating prefetches that's the idea。

😊，I mean it may be a bit more complicated than this， but this is the basic idea。

 so this way each load or store instruction can lead to a memory access pattern with a different stride right so you can distinguish strides that are。

Potentially unique to different load instructions。😡。

Now you can only detect those stridees caused by each instruction， you cannot see stridees across。😡。

Different sets of instructions， right？So timelines of prefetes can be an issue but you could solve it essentially initiating a prefetch when the load is fetched the next time can be too late because you may be fetching the load very soon right so you need to look ahead in the instruction street and people have done multiple ways of looking ahead one way of looking at is basically don't you don't prefet just the next one you prefesh the next end ones right next and incarnations of that strip for that。

😡，Okay。So that was instruction based， you could do this on a memory region base。

 which is a little bit more complicated， but you divide memory into regions。😡。

And based on the cache block address， you index this region table for a given region。

 you have a tag and you have a stride in that region。😡，Meaning when I access this region。

 I have the stride and this is I'm going to add this stride to this address。

 there could be another address that you keep over here， of course。

 to decide what is the last address that you have fetched in that region and you're going to add a stride over there。

😡，Now the advantage of this is this can detect strideed memory access patterns that appear due to multiple instructions let me finish the slide and then we're going to stop for example here the str。

😡，Maybe happening where each access could be due to a different instruction， different load。

 right it's possible there are access patterns and programs that make this happen now you can detect it。

😡，Now stream prefeing， stream offers a special case of memory region based type prefetching where n is one。

 and that was ideaM Power form。😡，Okay， I think I've said all of this almost。

 but basically the latter is more hardware intensive。

 the memory region based is a little bit more hardware intensive but it's actually used in many processor。

 many processor actually use instruction based strike prefeching also， for example， Intel。😡。

An example where when they used to write papers， they talk about that。😊。

And also a memory region based stream prefection that we have seen。 Okay。

 this is where we will pick up。 We're going to get more complicated。 We're going to talk about。😊。

Like more advanced prefeting mechanisms， and then hopefully we'll conclude prefeting next time。

Any questions， burning？Nothing is burning， Okay， but you can ask next time。



![](img/41f97ad8c7218ec80efca8520c7479f3_14.png)