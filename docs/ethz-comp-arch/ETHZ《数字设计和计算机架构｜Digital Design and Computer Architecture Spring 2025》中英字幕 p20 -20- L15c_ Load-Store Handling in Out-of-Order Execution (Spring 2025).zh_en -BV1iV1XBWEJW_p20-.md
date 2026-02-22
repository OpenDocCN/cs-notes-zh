# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p20 -20- L15c_ Load-Store Handling in Out-of-Order Execution (Spring 2025).zh_en -BV1iV1XBWEJW_p20-

![](img/5893f678ef651b89f755a2d59b185cca_0.png)

Now， let's talk about the most hairy part of an out order engine。

 which is handling of loads and stores。Now， this is going to be。

 I don't want to spend a lot of time on it， but it's really important to understand that memory is the really most hairy part。

呃。So let's we talk about registers。 Actually， handling registers added a lot of complexity to the system。

 right。But it's actually the easy part。So we considered mainly registered as part of the state。

 What about memory， Theres a fundamental， There are multiple fundamental differences between memory and registers。

The first one is really interesting because it's going to cause a lot of complexity and headache in the design。

 Register dependencies are non staticically， meaningan you look at an instruction。

 It sources register 3。😊，You know the sources。 You know the destination。Good。

 you can do renaming easily， right， because， you know everything at the front end of the machine after you decode the instruction。

But memory。You need to execute the instruction a little bit， to get the address。

So you don't know the memory address of an instruction at the beginning of the pipeline in the de stage。

 And this is the cause of all of the headaches that we're going to have。On top of this。

 these address are not small， they're large。So register state is very small。

 We looked at 32 registers，64 registers。 Memory state is huge。 The addresses are very large， right。

 So this is going cause， this is going to double our headache。A little bit。And the register state。

 this is。Also interesting， but we're not going to tackle it as much。

 If you look at other threads or processors。They don't share the registers normally。

 When you write a multi threaded program， for example。Different threads don't share registers。

 So you don't need to worry about them。 But memory state in a shared memory multiprocessor。

 which is most of what multi processors are today， is shared between different threads and processors。

And this could cause headaches if you update memory state in an out of order manner。

 but we don't want to update memory state out of order anyway。

But we' are not going to tackle this one， But this is another difference between registers and memory。

So the first two problems are going to cause us headaches with auto order execution。 The last one。

 we can perhaps handle。 There are some issues over there。

 but you really need to take the advanced architecture class to understand them。

 And those are also hair issues， by the way。Okay， so let's。

 so what what are the issues that are caused， Basically， if you have an out of order machine。

 you're executing instructions out of order， you need to obey these memory dependences also。

 it's not just about registers。 You need to， you need to ensure that memory dependences are correctly obeyed。

Meaning that a load may be depend on a store。 And you to ensure that load gets the correct value from the correct store。

Now we handle this nicely with registry re naming。But these are not registers。

 These are memory addresses， right。Registry addresses we know at the beginning of the pipeline so we can rename nicely to other namespace。

 memory addresses， we don't know。Until we execute the instruction。Okay。

 and we need to do so while providing high performance。 So that's the problem， Basically。

 the key observation and key problem is that the memory address is not known until a load or a store instruction executes。

So first corollary is renaming meiaus is difficult because of this。You cannot do it at decode stage。

 If you really want to do renaming， you need to do it over here。But that's too late。

Because things are already out of order over there。

 The beauty of renaming was when you're doing the renaming。

 it's in order so I can link the procedure producer to the consumer correctly。😊，Here。It's a mess。

Okay， because one instruction may have generated an address in some way。

 Another instruction may have generated an address in other way。

 So let me switch to this very quickly。 I think we're gonna switch back and forth a bit。



![](img/5893f678ef651b89f755a2d59b185cca_2.png)

![](img/5893f678ef651b89f755a2d59b185cca_3.png)

So， let's assume that。We have a program。 You have a store instruction here。

 It basically computes an address based on R 5 and with some offset。 And then it writes。

 I don't know， R 10 over here。 And then we have a load instruction that computes its address。

Based on art， I don't know， 25。And then write the result into our whatever register is not important。

 thiss also not important。So the key question is。This。When this executes， it generates an address， A。

 when this executes， it generates an address B。Is this address A dependent on B。Well。

 if you knew address A And B， that's great。 You could compare them。But what if this executes earlier。

 Because you're doing out of order execution， this storm may be dependent on something that takes 1000 cycles。

But this load may be dependent on something that takes two cycles。So this load is ready to go。

 It generates its address。 It generate a。The store is up there still waiting for our 5， for example。

 or even the source register。 maybe both of its source registers， it's waiting for。

 So you have no idea what the address of the store is， and you want to execute this load。

There's a problem， right？Because。If， if the addresses are going to be the same。

 you want to get the value from the store。

![](img/5893f678ef651b89f755a2d59b185cca_5.png)

So what do you do， And that's the key problem。呃。

![](img/5893f678ef651b89f755a2d59b185cca_7.png)

So we're going to take a look at that a little bit。Okay。So essentially。

 determining the second corollary， what I showed you is determining the dependence or independence of loads and stores has to be handled after their partial execution。

 I say partial execution， because。ELo kind of has to it generates its address。

 and then it loads the value in that address to a register。

But address generation is just partial execution of it below it。

 The next step is going to the memory and getting that location。

 But if you don't know if a store is writing to that address。Then maybe you should wait。Okay。

 and there's also another correlatedrollary3， which makes， which is also what I discussed， actually。

 when a load。Let's assume we are talking about loads right now。 When a load has its address ready。

 there may be older stores with unknown addresses in the machine。

And the other way around also works When a store has its address ready。

 there may be younger loads with some unknown addresses in the machine。



![](img/5893f678ef651b89f755a2d59b185cca_9.png)

The first one is more， more serious， of course。 So let's take a look at this。 Basically。

 this is essentially the example that I showed you when this load has its address already。



![](img/5893f678ef651b89f755a2d59b185cca_11.png)

It doesn't know if the store is writing。 What may be worse is there may be another store whose address is also not ready。

And this load may be reading， let's say， I don't know，4 bys over here。And1 B may come from here。

 and 1 B may come from here。So it's actually much more messy than you may actually initially think。

There may be actually many stores right to these locations。 So you need to actually get。

The value correctly。To be able to do that。Okay。

![](img/5893f678ef651b89f755a2d59b185cca_13.png)

So two basically you get the correct result， right。Okay。

So we're not going to solve the entire problem。 I'm gonna give you the complexity of the problem and some approaches to handle it。

 but。Believe me that this is the messiest part of an Auto word execution engine。

 and this is the least scalable part of an Auto word execution engine。

 If you thought that it was really the tag broadcast logic， you're wrong。

 It's really this logic that disables the scalability。😊，Okay， so the key question is。

 when do you schedule a load instruction and auto order execution engine， As I said。

 the problem is a younger load can have its address ready before an older store's address is known。

 This is also known as the memory disambiguation problem。

 You disambiguate addresses or the unknown address problem。 I like the unknown address problem。

 because it's simple thinking， unknown address。So there are multiple approaches to this。

 one is the conservative approach。Which is terrible for performance in general。 You stole the load。

Until all previous stores have completed Compd their addresses， You can do that， right。

 In this example that I've shown you， I'm not going to switch to it， but。

There are a bunch of stores in front of older than this slot。

 You basically wait until all of them compute their addresses。

It doesn't matter if it takes000 cycles，5000 cycles， you just wait。

And when all of them have computed their addresses。Now， you know。Which store you're depend on。

 You need to do something to know that， of course， But， you know， or I mean， if。

 if you're even more conservative， you just wait until all of the stores are out of the machine。

 meaningan all of them have retired and updated the memory。But that even takes longer。

 as you can imagine。 So this is the conservative approach， and this is terrible for performance。

Aggressive approach takes exactly opposite， it basically says。I'm a lot。 I know my address。

 I'm gonna assume that I'm independent of。Any other previous stores。

I'm going to schedule this load right away。O。😊，That's aggressive。Basically。

 the prediction is that hopefully the load is not going to depend on any of the stores。 Of course。

 if you do this， you need to check later on。Did I actually predict this correctly。

 This is a method of this this is an example of predicting something in a machine。

So this actually also doesn't work extremely well， although it's usually better than the conservative approach。

But it adds additional machinery to check。 Basically， if you're wrong。

We should re executeec this load。And get the correct value。 So if you're wrong。

 you flush the pipeline， basically。Okay， there is also an intelligent approach。

 which pretty much all existing machines employ， which is essentially more intelligent。 As I said。

 you predict with a more sophisticated predictor if the load is depend on any unknown address。Okay。

So let's take a look at this a bit more。 as I said。

 a load dependence status is not known until all previous store address are available。

 There are two questions。 actually， One is， how do you detect the depends of a load instruction of a previous store。

 You wait， you wait until all previous stores are committed。 In this case。

 theres no need to check for address match。 The logic is simple。

Or the second option is you keep a list of pending stores in a store buffer。

 This' is also called a store queue and check whether a load address matches a previous store's address。

So basically， okay， I'll， I'll get back to this later on。 And this And the next question is。

 how do you treat the scheduling of a load instruction with respect to previous stores。

 You assume all load load is in dependent on all previous stores。

 You assume load is independent of police stores or you predict the dependence。 Of course。

 if you want to predict the dependence somehow， you need additional logic for that。

So let's take a look at this one。First， if you assume a load is dependent on all previous stores。

This is good because you don't need to add any logic。

 You just wait until all previous stores are done。But it's true conservative because it delays independent loads unnecessarily。

 right， Again， in this example， these stores take 1000 cycle。 This load is ready。

 And if it's independent， you basically delay this load for 1000 cycles。If you do option 2。

 assume the load is independent of every previous store。It could actually be simple。

 and it's common case。 There's no delay for independent loads。But。

We have to pay the tax for recovery。 If you're wrong， First of all。

 you need to figure out that you're wrong。So you， there needs to be some additional logic that says。

You， you sent this load。 You executed it， but you were wrong。

 So there needs to be some checking that needs to happen。When the store computes address。

 it needs to check。Okay， whether if， if there was a load that actually assumed that it was independent of the store。

So that's a mess。So basically， it requires recovery and re execution of the law。

 So existing machines actually flush the pipeline whenever they are wrong。

The option 3 is the intelligent option。 You basically predict it depends of a lot and an outstanding story。

 I'm not telling you how to actually do that。 There are mechanisms for this。 Actually， this， this is。

 this was the subject of a very prominent legal battle between one university whom I will not name and a bunch of companies。

That the university claimed that they actually patentanted this work。And the companies。

Use some sort of memory disambiguation。 Then there was a huge legal battle that lasted for a really long time。

You can probably figure that out。Okay， but this is more accurate clearly。

 because load store dependencies actually persist over time。

 people found out that if this store is writing to a location that this load is going to read。

Whenever you go back to the same mode and store in a loop， for example。

 it's going to happen again and again and again so you can learn from past executions。But， of course。

 if you're wrong， you still need to recover and re execute。

 And there are some very interesting papers。 for， for example， the alpha 21 to 64。

 if you read this optional reading， you will see that whenever it executes a load， initially。

 it assumes that the load is independent。It figures out if it's right or wrong。 If it's wrong。

 the next time it says。I'm not going to assume that it's independent。

 I'm gonna to assume it's dependent。So it basically learns over time， a little bit。Okay。

 so this is very quickly。 this is showing the conservative approach， no speculation。

 aggressive approach and the perfect approach。 And this is performance on the Y axis instructions per cycle。

 And these are some workloads that people have used in 1990s。 As you can see。

 Some of them are interesting， like go benchmark。 This is the place go G C is a compiler compression。

 So these are actually still used some of them。😊，But basically。

 if you look at this conservative approach is actually terrible。

 aggressiveive approach is a little bit better。But perfect approach has a huge gap。

 So that's why you would like to handle this well。So simple predictors that actually can achieve actually most of the potential performance。

Okay， I'm not gonna talk about how to the prediction。 You can leave that to your imagination。

 But let's talk about data forwarding between loads and stores also。

 So if we cannot update memory out of program order， clearly。

 that we cannot even update registers because that would violate sequential semantics。

 which means that you need to buffer all store and load instruction and instruction window。

 And we know that we could use the reorder buffer for that。Now， I'm going sidestep the problem。

 I'm going to say， even if we know all of the artists of past tour。This is still complex。

So when we generate the address of a little two questions still remain。1 is。

 how do we check whether or not it's depend on a store。

So there needs to be some way assuming that you would like to schedule the load。

At that point in time， we don't want to be take the conservative approach。

And how do we forward the data to the load if it's dependent on Stor。So for this。

 you need a special structure。And these special structures are usually decoupled into load queue and store queue for this。

 It can be combined between load stores。 For example。

 Pentium Pro in Intel had it was called a memory ordering buffer mob。😊。

So you had a mob in a processor。But you can combine and separate basically。

 you have a load chance to store you。So whenever you want to， you produce the address of a load。

 what you do is you search the toque queue。To check if there is any store。That you're dependent on。

So that you can schedule the load。And a store， when it finishes execution。

 search when it computes its address， it searches the load queue to see if there is a load that's dependent on it。

 This is the the second one is needed。 If you're doing prediction。

 If you're so that you can check your prediction， right。

 If you predicted this load is independent and you've executed it。

 But then the store address became available， and then the store needs to check if any of the loads got the wrong value。

 because they were predicted to be independent of the store。

So I'm not going to talk about the second case， but it's also needed if you're doing intelligent prediction。

 But the first case is needed， even if you're not doing prediction。

 you just want to be able to decide whether this load is dependent on its store。

And even assuming that， you know， the address of all of the previous stores。O。

So when a store instruction finishs execution， it writes us the address and data and reorderable entry or the store to entry。

 When a later load instruction generates its address。

 it basically searches the store queue with its address。

So we're going look at how bad that search is。It accesses memory with its address。

And it receives a value from the youngest older instruction that draw to that address， hopefully。

So to be able to do this。You need the complicated search logic。And this is actually the。

 remember the content addressable memory that I introduced in the previous lecture。

 This is the worst content addressable memory that you have to enable out of order execution of loads and stores。

😊，So content is really memory address， but you also need other stuff like the size。

 like the age also。 So let's take a look at this。

![](img/5893f678ef651b89f755a2d59b185cca_15.png)

This is called the store to load forwarding logic。

![](img/5893f678ef651b89f755a2d59b185cca_17.png)

So， basically。Now I'm going to make it simple， this is a torque。

This is an in order list of all of the stores that are in the machine。 You have a head。

 Its all hardware。 of course， you have a tail。And what do you have over here？ Clearly。

 you need to have a valid bit。Whether this is valid and then address of the store。

 which could be 64 B。And then a data value of the store， if it's available。Which could be 64 Bs。

And the well is one bit。嗯。And， of course， you need to also have valid bits to see whether the address of the store is valid and whether the data of the store is valid also。

Which makes it really interesting and complicated because the store executes。

If the store hasn't computed its address yet， its address is not valid。

 but the data may be available， right， You're in an autoboard engine。 the data may already be ready。

Okay， so。Whenever a load instruction。 So let's assume that you have a store here at address A。

 Let's assume that address are all known。 I'm gonna make it even simpler。

 And let's assume that you have another store here。 Okay， ABC， D， all sort are here， X。

And we have a load over here。That computes its address。

 And let's assume that I don't want to call it。 Let's assume that it， it computes an address C。

The key question is。Can this where should the date this load gets its value from。

So what it needs to do is it needs to compare the C。So all of the addresses over here。So basically。

 for each entry， you need to have a comparator， right？

That sounds terrible already it's going to become more terrible。And this is a 64 B comp。

 assuming your address is 64 B。 I mean， I exaggerated because normal machines don't use the entire 64 B address space。

 Let's assume that it's 48 bit。 Okay， that's more realistic。So it's a 48 bits comparator of address。

And you do this。But is that enough？That's not enough， right。

 I've given you an example earlier where one store is riding to one bite over here。

Another store is writing to another bitete。And this Lord is reading。These two bys。嗯。

So you may actually match in multiple places。That's the first observation。 It's not a single match。

 You really need to match in the multiple the latest locations that you're trying to eat。😊，So it's。

 it's really， there could be multiple locations。 And also， youll need to get the multiple。

 the latest。Stores that drive to that location。And also， what makes it a bit more complicated is。You。

 you need to ensure that the size also matches。 So let me actually go， go back over here。

 I'm not gonna build a complete logic over here。 Clearly， if you get a chance to build it。

 build it for sure。But basically， this is the complexity of the search。

 It's a content inter disible search based on the load address。 As I showed you， It's a range search。

 meaning based on the address and size of both the load and the earlier stores。

Because you may partially overlap with the address， right。

 This Lord may be accessing bys  8 through 12。 The storm may be riding bys 11 through 12， right。

It's an age based surge。 You want to get the last written values。

And that's essentially what you need to build over here。Now， on top of this。L data can。

Let me go back actually over here to the Doyche。So you need to find the latest stores。

 So assuming that let's， let's say you're loading addresses Z， Z plus 1 Z plus 2 and Z plus 3。 Oh。

 you cannot see it。 Okay， sorry。So basically， you want to access addresses Zz plus one because it's a4 byte load。

You need to be able to ensure that you find all of the stores that are writing to all of the latest。

呃。Riders to each of these locations。 Now， you may be able to find one that's writing here。

 Another that's writing here， another that's writing here。Okay， three stories are writing here。

 where do you get the fourth month from？Well， now you need to access memory for that。

Because there is no load store that's writing。To that one。

 So it's actually to be able to get your data value。You need to search this。

 and you also need to access memory。That's why this is one of the most complicated parts。

 And when you search this， of course， there may be no match。Then you access memory， of course。

 to get all of it， right。Because。There may not be any stores that are writing to the location that you're reading。

At that point， you need access memory。 So this search may be useless。

But you need to do it to ensure that you get the correct value for the load。Makes sense。



![](img/5893f678ef651b89f755a2d59b185cca_19.png)

Yes， so the sort of view isn't just used to check that there are any risks。 Basically。

 so it's also it cannot。

![](img/5893f678ef651b89f755a2d59b185cca_21.png)

Exact exactly。Exactly。You could use it to check， of course， but。If you have a match。

 you need to get the value from somewhere。So it， it serves two functions。 Basically。

 it serves a function of， can you schedule this load。

 And if the load is actually dependent on its store， give the value。For data forwarding。Okay。

 I already said this basically。 This is the last example that I gave。Any questions。Is this clear？

The complexity。I'm not going to ask you questions on the load store forwarding logic。

But you should really know that。 This is really the。Tough part。

 People tried to scale the size of the instruction window。Yeah。

 they can scale the reservation stations。But it's very tough to scale this logic。Much harder。

 much larger。 I believe existing processors maybe have a 24 MP store buffer。

 even though the instruction window size may be 256。Or so。

But it's very small compared to other parts of the machine。

 And you're usually limited by how many stores you can put into the machine because of that reason。

So if you keep putting a lot of stores into your machine。

You're probably destroying the performance of your machine。So try not store， try not to store much。

Your machines。And the reason is because of this， basically， this is very hard to scale。

 And you cannot， The machine cannot have a lot of stores in it。



![](img/5893f678ef651b89f755a2d59b185cca_23.png)

Okay， if there are no questions， this is a good place to stop。



![](img/5893f678ef651b89f755a2d59b185cca_25.png)