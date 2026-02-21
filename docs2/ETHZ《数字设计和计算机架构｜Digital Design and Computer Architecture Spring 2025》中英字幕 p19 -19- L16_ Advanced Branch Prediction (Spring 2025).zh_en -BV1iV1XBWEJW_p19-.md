# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p19 -19- L16_ Advanced Branch Prediction (Spring 2025).zh_en -BV1iV1XBWEJW_p19-

![](img/387006f5726e351c112c1926823defef_0.png)

No， but no， good。All good online， it's very loud。Okay， we have a sparse lecture today。

Is there some event going on？That you guys are missing out on。Maybe a big party。Okay。

 I guess maybe you'll learn about it later。I have a big deadline， so I know that。

 but nothing else other than that。Yes。Okay， we're going to cover a topic that's quite exciting that you guys yesterday started。

 just a topic that has fascinated many people for many， many decades。😊。

It's a tough topic right now because it's very difficult to improve on it。

 but it's very important to improve on it as Muhammad mentioned yesterday。

 and as I'm going to hap on today， also， which is predicting branches。

 basically predicting the direction of branches and so that we can keep the pipeline full without stalling the fetch engine right。

😊，You guys studied this yesterday and we're going to go into some more techniques and hopefully we're going to finish branch prediction。

 even though there are a lot of other things that we can talk about in branch prediction I'll leave you with the backup slides if you're interested you can study the backup slides。

😊，And these are some of the readings that I would recommend your books don't go into this topic as much as we do。

 books usually are older whereas topics move， and you will see that more and more as we go into a little bit more interesting topics like GPUs。

 well GPUs， systoic areas， etc in these lectures， those topics are not covered well in your books unfortunately。

 even though they are the cornerstone of how we do computing today， right。Okay。

 so basically we were talking about guessing the next fetch address and we talk about branch prediction and we talk about the importance of this problem。

 we talk about especially what does it mean to guess the next fetch address right you need to basically guess that the instruction that you fetch is a branch。

 you need to guess the target address， you need to guess whether that branch is taken or not taken assuming there's a conditional branch right？

😊，And if you don't do it well， as we have studied with this basic example yesterday。

 even with 90% accuracy in your guess， you will basically not utilize your 20 stage pipeline five white pipeline very well your fetch IPC is only 1。

6 as opposed to five and you would fetch 200% extra instructions so 90% is a large number today we're going to cover how to get to 90% but getting higher than 90%。

 especially in difficult workloads where branches are hard to predict is not easy today。😊，Okay。

 so it may actually some of the implementations in real industry looks like black magic because you're trying to guess what's going to happen and you need to really use a lot of information and we're going to see some of the information that goes into the prediction mechanisms that are actually used in microprocessors in hardware today okay this was essentially our fetch stage with a branch target buffer remember yesterday we' introduced a branch target buffer which basically is indexed with the program counter of the instruction you fetch。

😊，If it's a branch， you get a hit over here and if it's a branch that was executed pretty previously you get a hit and you get the target address。

 so it's really a cache of target addresses， if you have a target address over here。

 it gives you information about two things， one is you executed this program counter before and it's a branch and here's its target address because you compute it。

😡，If you miss in the broad branch target buffer。You don't know it could be a branch that you never executed or it could be something else right then you use the prediction PC plus instruction size。

 which means you go to the next sequential instruction becauset you don't know whether it's a branch or not。

😡，Concurrently you use the program counter to index something called the direction predictor which we're going to develop today It tells you whether the branch was taken or not taken the previous time you had seen it。

 we're going to enhance that today and if the branch has taken then you use the target address that you get from the BTB which you had cached based on the previous execution which you had kept stored based on the previous execution and use it as your next fetch address if the direction prediction says oh you should predict this branch has not taken then you use PC plus instruction site which is PC plus4 in the MIPSia so hopefully this is clear this was covered yesterday so I will not go into it today we're going enhance this a little bit more and yesterday actually we didn't even build this direction predictor yet we're going to build it today but this direction predictionor can be compile time which we have covered some of examples of yesterday I'm going finish the compile time predictors today and then we're going to go into runtime or dynamic predictors which are implemented in hardware so hardware actually。

Re what to do when you fetch this instruction based on what has happened in the past。Makes sense。

You can of course combine compile time in run time。

 but we're not going to do that today so this was one slide that was covered yesterday by Mohammad essentially we saw that there's simple static branch prediction techniques that don't require much hardware for example。

 always not taken you always predict the branch to be not taken you always fetch PC plus poor basically unfortunately this is has very low accuracy 30 to 40% for a conditional branches because it turns out most of the conditional branches are taken and the main reason for that is loops whenever you implement a loop it's a conditional branch that is taken right if you actually need to iterate over the loop it's a taken branch you take the branch to the beginning of the loop and you keep taking it unless until you go out of the loop。

😊，And since loops usually iterate more than once， twice， three times， four times， five times。😡。

10und0 times most branches tend to be taken。But this is very simple clearly。

 but it's not very good performance if you can do the opposite。

 you can always predict the branch taken here you don't need direction prediction。

 but you need target prediction and this gets better accuracy clearly because it's the opposite of not taken and essentially this is better but 60% as we have seen earlier is not enough right。

😡，And then people play the trick off backward taken if you see a branch that goes backward in code basically the target address is earlier in code in terms of address compared to the branch。

 you predict its taken because this may be a loop branch。

 otherwise you predict it's not taken because this probably is not a loop branch and this turns out to be a little bit better than either of these mechanisms。

 but these are all static mechanisms still meaning you don't need direction prediction hardware for this。

😡，Okay there's another static mechanism that's profile based and this is the last thing that was covered yesterday I'll go through this relatively quickly again the idea is compiler supplies a prediction based on the information that it gathers during compile time compiler essentially looks at all the direction branches it profiles the code using some input set basically it runs the code using some input sets that's provided by the programmer or the user and says under these conditions under these input sets。

 I say this branch is likely to be taken this other branch is not likely to be taken this other branch is likely to be taken and encodes that direction as part of the instruction encoding instruction andcoding as a single bit saying that it's a hint bit that is filled by the compiler if the compiler thinks that branch is likely to be taken it sets that bit to one otherwise it sets that bit to zero and this serves as a hint to the hardware saying that compiler supplied this bit as a prediction for the branch。

😊，Now this has the advantage of being per branch for each branch you can individually determine this bit right for each program counter basically。

 so this could be more accurate than the mechanisms that we have looked at over here。😡。

Assuming the profile is actually representative of the actual execution of the code because you determine these bits based on profiling the code。

 the compiler runs the code several times and says， okay， this branch is like to be taken。

 how does the compiler run the code， it assumes some input sets right if the input set that you actually run in real life when you actually execute the program is different。

 completely different from what the compiler profile the code on。

 then the input set may not be representative and those direction bits that are encoded by the compiler may not be good for the thing that you're running in the field。

😡，So this profile I presented to this is a problem that's always there if you actually do compiler based optimizations because compiler doesn't know what's running。

 right， what's going to run， you compile the code， you generate instructions。

 you put these hints based on some information。😡，If that information is quite different from what actually happens and when you actually run the code in the field。

 then your input set may not be represented。😡，Does that make sense？ There's always an issue。

 And keep that in mind whenever you have this。So the the upside we discussed that the downside is this requires Hibits in the branch instruction format。

 meaning you need to change your ISA most ISAs have this inputbit today and accuracy depends on dynamic branch behavior and I'm going to show you several examples over here so these are two instances of a branch this is one instance of a branch。

😡，Assume that the branch in the first 10 executions was taken in the next 10 executions that it was not taken。

The compiler can encode one bit only in this case， it doesn't matter what it picks。

 can it can say this branch is likely to be taken or likely to be not taken。😡，Pick whatever you want。

 you get 50% accuracy on this。😡，But you can see that this is actually quite predictable right if you actually have a runtime predictor。

 dynamic predictor that kind of recognizes pattern， you can do much better than 50%。😊，Okay。

 another example is a branch when it executes， it alternates between being taken， not taken， taken。

 not taken， taken， not taken， again， if you encode this with a single bit in the compiler。

 the graphls of whatever compiler selects you get 50% accuracy。😊，But again。

 this is quite predictable when I look at this， I can say I do the opposite thing that I did last time。

 right， potentially。Okay。😊，So and also accuracy depends on representative of the profile input set to demonstrate this。

 you can see a branch over here that's taken 18 times and that's not taken two times。😊。

Assuming the compiler。Had a representative input set， it would encode the branch to be taken， right。

 the likely direction to be taken， and it would get 90% accuracy if that's the case。

 which is not bad。But if the compiler makes a mistake because its input set is not representative and it says。

 okay， branch is likely to be not taken in real life you'll get to only 10% accurate。😡。

So your accuracy can be terrible， as you can see if you make a mistake at compile time。

 because the profile that you have is not good enough。

So that's the downside of profile based mechanisms。Okay。Okay let me give you another idea。

 this is actually a cool idea I think it doesn't work in many cases， but it works in some cases。

 but you can actually do the analysis of the program you can analyze the types of branches in the program and decide this bit hint bit that your supply to the hardware I call this program based or program analysis based prediction the idea is to use heuristics based on program analysis to determine the statically predicted direction by the compiler again the compiler can do this or you as a user can do this。

😊，For example， this paper from PLDI in 1993 says that if the branch is branch up as branch。

 less than or equal to zero。😊，Predict that as not taken because usually negative integers are used as error values in many programs and if you predict that's not taken。

😡，This is better than tapeating it as taken。 Okay， so this is a heuristic， right。

 You don't need to do any profiling。 You just look at the up code and the up code says this。

 and you set the bit based on the up code。Another luaristic， right。

 if there's a branch that's guarding the loop execution， if some condition execute the loop。

 otherwise don't execute the loop then。😊，Predt the branch to be taken to execute the loop。

 why because programs usually are written based on loops and if there's a guarding branch that's stopping the execution of the loop。

 it's probably not taken， meaning you're probably going to execute the loop again this is a heuristic that you develop based on your analysis of the code。

😡，Okay， no need for profiling here， so if you compare a pointer。

 a pointer that points to a memory location an address with a floating point number that's a complicated number。

 then predict that this is these are not going to be equal for example， who does that I don't know。

 but if someone does that probably you're not going to get an equal number between these two things。

😡，Okay， so basically the key idea is this doesn't require profiling。

 which is good because input set representatives goes away。

 but now youre very much dependent on heuristics and these heuristics might not be a representative or good and it may not apply to many branches right？

😊，This requires still compiler analysis and ISA support。

 but that's true for other static methods as well。So if you're interested in this。

 I would recommend reading this paper from 1993 and it's very nice， I think。

 and it shows that at the time they got a 20% mis predictiondiion rate， which is not bad at the time。

Okay， one last static branch prediction method is programmer based， basically as a programmer。

 whenever you're programming， you guess whether the branch is going to be taken or not taken。😡。

And you communicate this information for each branch to the hardware using some constructs in the programming language and many programming languages have these constructs called pragmas essentially you can specify I'm going to show you in the next slide you can specify whether a branch is going to be likely not taken or likely taken right if you're a good programmer maybe you can do that but again this not also perfect right programmer may not know the data inputs coming into the program so this doesn't require profiling or program analysis programmer may know some branches and their program behavior better than other analysis techniques if they have a good hunch of what whats are going to happen potentially。

😡，Unfortunately this requires even more support， it requires support from the programming language。

 it requires support from the compiler to take what's provided by the programming language and encode it in the ISA。

 so it requires support from the ISA as well。😡，So clear this burdens the programmer now。

 right because programmer needs to think about whether their branch is going to be taken or not taken。

😡，Okay， let me get into the notion of pragmas， basically how does the programmer convey this information。

 essentially a lot of languages programming languages provide keywords that enable programmers to convey different types of information to lower levels of the transformation are meaning hardware in this case。

 you can convey this information to the instructions at architecture and instructions like architecture encodes it and you can actually communicate with the hardware from the program saying that oh。

 I think this is going to be taken， for example， so this is an example， if likely X。😡。

This is a prag man C language， essentially。In this case， you're testing X。

 if x is true you execute that code in the brackets and you say I think this is going to be taken。

 meaning execute the code in the brackets， so you're providing a hint of the hardware so the compiler that compiles this pragma basically sets the bit in the branch that executes that if statement to be one meaning that that's going to be taken and you can do unlikely error for example。

 if there's an error do something and most of the time you don't get errors in the program hopefully and if you get errors you don't care about performance anyway so basically you can set that to be unlikely。

There could be many other hints and optimizations that can be enabled with this sort of pragmas this is an example but another pragma will give you is whether loop can be paralyzed this is a pragma that the compiler that the programmer says I think this loop is parallellyizable so a compiler please try to parallelze it with your techniques this is a pragma that happens that is there in many parallel programming languages Openmp for example and this is how it's specified and this is description directly from the openmp manual this parallel directive explicitly instructs a compiler to parallellyze a chosen segment of code of course the program compiler may or may not be successful but now the programmer guides the compiler to try to do it。

Makes sense， that's another performance optimization， yes。Plyize。Anyway，Yeah。

 I mean it may be too difficult， it may actually lead to some code load， for example。

 if the loop is not really paraizable， the compiler may need to do a lot of tricks that actually increase the code size。

 etc ceter， so thats they're undesirable effects。😊，If it's guided by the programmer。

 you may actually avoid some of the undesirable effects basically。😡，That's a very good question。

Complies are not good enough yet because they don't have a lot of information about dynamic execution。

 right。😡，And depends。Okay very good so now we are almost done with static branch prediction essentially all previous techniques can be combined you can be you can have some branches predicted based on profile some branch based on program analysis some branches based on programr information the question is of course how would you do that there's work to be done here and。

😊，There's a common disadvantage of all three techniques which I've given you actually already。

 even though branch may be quite predictable based on dynamic information。

 none of these techniques take into account dynamic information。

 meaning they cannot adapt to changes in branch behavior they basically encode one single direction for the branch whereas the branch may change behavior while it's executing right it may be taken for the first million times it's executed in the next million times it may be not taken right I give you an example 10。

10 but imagine it's million and million right essentially we want techniques that can adapt to changes。

😡，So of course， if you keep recompiling the code while it's running。

 meaning having a dynamic compiler， a binary dynamic binary translator we have seen at a high level earlier you could mitigate some of this you could basically the compiler compiles the code after at some point it recompiles the code while the code is running and it can change it can adapt to some of these changes in dynamic behavior in branches right assuminging the branch changes behavior at a course granularity that's made maybe okay like every million branches。

 every million executions you switch from taken to not taken。😡。

But what if you switch from taken to not taking every other execution？😡。

That's very difficult to account for， even with a dynamic compiler that recompiles the code once in a while。

So a dynamic compiler also has its overheads。And what's a dynamic compiler。

 essentially a compile that generates code at runtime that changes the code and there's a support in modern machines for these。

 for example， Java language as a Just in time compiler。

 Microsoft is a common language runtime and this class we've seen a binary translator actually multiple binary translators that actually compile code dynamically and adapt to hottS code that may actually be executed a lot。

😊。

![](img/387006f5726e351c112c1926823defef_2.png)

And Vdia for example， the dynamic code optimizer that we discussed briefly again in the past does that。

 it basically finds out which parts of the code are executed a lot and it optimizes them if you actually know information about which direction the branches are going you can change the Hibits when you're compiling the code or when you're compiling the code。

😊。

![](img/387006f5726e351c112c1926823defef_4.png)

Okay。So okay so there is a way to make the static prediction more dynamic by having a dynamic compiler that keeps recompilling the code but there overheads associated with it so now because of that we're going to move to runtime and techniques you can combine runtime techniques with static techniques also and choose the best we're going to talk about hybrid branch predictors later on but we can be a hybrid of static and dynamic as well。

 but let's not get ahead of ourselves。😡，Okay now I'm going to move to runtime techniques which can adapt to behavior of branches dynamically and we're going to start with the simplest mechanisms and we're going to build able to advanced algorithms that are used in current systems like perceptrons and geometric history length predictors etcter this will become more clear when we discuss it Okay what is the idea I think I give you the idea basically predict branches based on runtime dynamic information collected。

😊，By hardware in many of these cases。So there's the big advantage here is you can predict based on the history of execution of the branches。

 if a history indicates a pattern that could be predictable。

 you can do better than static prediction。And you can adapt to dynamic changes in branch behavior。

 if the branch behavior changes， you can adapt to that change。😡，There's no need for static profiling。

 so all of the input set representativeness problem goes away right or relying on the programmer。

 relying on heuristics， all of those problems go away basically。😡。

Of course there's a disadvantage here， clearly this is more complex because now you need to have additional hardware to do this prediction and if you really want to do this prediction very accurately the hardware becomes larger and larger and larger and that's where we are today the hardware is actually quite large in existing systems I'm going to give you an example of that when we go to later slides。

😊，Makes sense okay， now let's jump into the simplest predictor you can design this is the last time predictor the basic idea is yes that the branch will take the same direction。

As it was executed the last time you executed it。😡，Okay， it's the same branch， same program counter。

 you keep one bit for that program counter， you could store this bit in the BTB or you could store it in the direction predictor as I showed you earlier。

😡，This sp indicates。Which direction the branch went last time it was executed so you execute the branch and you figure out that oh it's taken。

 you record that bit has to be taken next time you fetch the branch。

 you check that bit because you have the same program counter is's the same branch or it says taken meaning that last time I executed was taken so I'm going to predict thats taken right I'm going to do what I did last time essentially what or what I should have done last time you can think of it that way essentially if you look at this thing this execution profile I'll call this an execution profile branch is taken for the first 10 executions branch is not taken for the next 10 executions you get 90% accuracy in this case right。

え。Assuming you start with predicting the branches take right。

So basically you are accurate until this branch over here not taken actually 90% accuracy assuming that you execute in a loop。

 let's say， so you basically what happens is you basically predict all of these correctly the last one the first time the branch changes behavior you'll predict it incorrectly because the last time you execute it was' taken。

 you think it's taken but it's actually not taken so that's a mistake you make and then when you actually go back like this usually we think of it as executing in a loop。

 when you actually go back and execute it when the branch changes behavior again。

 you get one more mistake。😊，So you make two mistakes out of these 20 executions。 That's 90% accuracy。

 which is much better than 50% with a single static prediction bit， right， Okay。

 we're going to do better than 90% soon。Okay， so basically what I just said with an example is written over here。

 you always mispredict the last iteration and the first iteration of a loop branch， right？😊。

Because last iteration， you keep iterating in the loop， you keep taking the branch。

 once you exit the branch， once you exit the loop， you need to not take the branch。

 but because you took the branch many times you think you're going to take it again。

 so you make a mistake when you entered the loop again， last time you executed the branch。

 it was not taken because you exited the loop， but you should predict it taken because you're going to take it while iterating in the loop so you make two mistakes。

😡，Okay， so accuracy for a loop branch with n iterations is n minus2 over n。😡，Clearly。

 if N goes to infinity。You're almost 100% accurate， right？So basically。

 this is very good for loop branches for loops with larger n number of iterations， okay？😊，Now。

If you have a small end then you' a problem， so you go back to  zero%。

 even though this is again very predictive， as you can see， right？😡，So if n is two in this case。

 yeah， you go to zero percent as you can see， so you can actually check with the equation。😊。

So basically this is not good last time is's not good if the branch is always doing the opposite thing what it is last time。

 right？😡，But you can probably predict this with a pattern matcher。

 I'm not going to go into the pattern match， we will get to perceptron， et cetera later on。

 but we're going to fix this problem partially with the next predictor that we will see。😊。

Okay so how do you implement the last time predictor there are multiple possible implementations This is one example basically now we actually need a direction predictor you take the program counter and pro index index an array and this array records which direction the branch went last time it was taken based on a part of the program counter used as the address so this direction predictor says whether the branch was taken last time whether this program counter led to a taken outcome last time okay now you could actually you don't have to have this direction predictor separate from the BTB BTB remember you use the program counter to index memory structure。

 this memory structure gives you whether this was a branch and whether you have a target address for the branch。

 whether you execute it it could also tell you whether it was taken last time right so it could actually be part of the branch target buffer and this is one way of implementing it basically this is your program counter。

😊，What you could do is you index into the program counter with a part of your address。

 it gives you an entry over here。 This entry tells you the target address and also the last time what happened to that branch and a tag so we're going to see the structure later on when we talk about caches so don't worry about it if you don't quite understand this yet。

 but you can think of this as indexing a memory array using an address address is determined by part of your program counter。

And essentially you get the taken bit and you get the target address and if the bit here is set。

 that means the branch was taken last time so you use the target address as your prediction。

 otherwise you use PC plus4 as your prediction。Makes sense okay。

 we're going to look at the structure later on when we get to the caches this is a very classic cache structure。

 but again， I don't want you to think about implementation details right now because our focus is really on algorithms to do branch prediction today okay you're going to have a lot of fun with this sort of structure later on。

😊，Okay。So basically， you need to update this branch history table that it's part of the BTV or the direction predictor that is outside the BTV。

 depending on how you implement it after each execution of a branch。😡。

So if you think about this for each branch you have kind of like a state machine right one state says predict the branch has taken because that was what we did last time the other state has predicted not taken and you can basically think of moving between states if the branch is actually taken you stay in the same state predicted taken next time right if the branch is actually not taken you go to the other state saying that next time predicted not taken so you can basically fill out the state diagram for every branch you basically have a state machine when I say every branch of course every branch in the program may not be possible for every entry you have in this direction predictor table and different branches with different addresses can potentially map to the table right because you're using part of the program counter as your address okay but in the purest sense it's for every branch。

Okay， so there is a problem with this and people have figured this out。

 essentially it changes its mind very quickly。😊，With a single opposite outcome。

It basically moves from one state to another state。

 basically it doesn't believe in staying in the same state if you think about it。

 right this is kind of like a broken air conditioning so if you actually have air conditioners，😡。

You set the air conditioning to be 20 degrees Celsius， for example， right you want to stay there。

And if it's a little bit higher than 20 degrees Celsiusius。

 your air conditioner may start cooling down， right？😡。

If it's a little bit lower than 20 degrees Celsius stairs， conditioner may start heating up。😡，Now。

 what if you're right around 20， 20。00001， what should your air conditioner do。

 should it start cooling down immediately or should it wait a little bit？😡。

So basically people have figured out that it's a good idea to wait a little bit why。

 because there's a margin over here around 20 degrees Celsius。

 and if you too quickly change your mind and start cooling down，You cool down and then you go to 19。

99999 degrees and then at that point what do you do quickly change your mind again and heat。

 you could do it， but basically you would be switching between cooling and heating and cooling and heating and cooling and heating and cooling and heating all the time。

 right？😡，And that's exactly the same problem we have over here and people have a name for this it's called hysteris essentially you don't change your mind quickly。

 you add a hysteris to the system saying that you wait a little bit。

 you basically monitor what's going on if you actually go to 20。

5 okay maybe Im doing now actually maybe the temperature is increasing so maybe I should take in so that's the same idea over here don't change your mind quickly okay that's what basically the idea of improving the last time predictor means and this actually made a huge difference that's why I'm actually harping on it this makes a huge difference and energy consumption of air conditioners also as you can imagine right。

😡，But basically a last time predictor changes prediction from taken to not taken or not taken taken too quickly。

 even though the branch may be mostly taken or mostly not taken right so you may imagine a branch taken taken taken taken not taken and then taken taken taken taken and then not taken once in a while if you change your mind you make two mistakes if you don't change your mind maybe you'll make one mistake right？

😡，That's the idea here， add histeris to the predictors so that the prediction does not change on a single different outcome。

 wait so that you actually accumulate some more information and some more evidence that you should really change your mind。

😊，Okay。So how do you accumulate that evidence， well there are multiple ways of doing it。

 but the simplest， one of the simplest ways of doing it is use twobits to track what happened as opposed to using a single bit。

 right？😡，So essentially， you can have two states each for taken or not taken instead of one state for each。

And this was introduced by this seminal paper in Ica 1981， and after this。

 all of the microprocesors implemented this and they actually had a huge boost in branch prediction accuracy。

😊，So this is also called tubit counter based prediction each branch is associated with a tubbit counter。

😊，One more bit provides hysteris， a strong prediction does not change with a single different outcome。

 it's also called bimodal prediction， so there are multiple words。😊，But basically。

 the idea looks like this， at least a two bit counter implementation。

 So you have four states with two bits。😡，And four states so these two states， for example。

 and quote that the branch should be predicted taken right these two。

These two states endote that the branch should be predicted not taken。

So there's a maximum value over here。That you can go to， you saturated at that value。

 and then there's another maximum minimum value over here， and then you saturated at that value。

 This' is also called saturating arithmetic。Meaning you basically have a true maximum and minimum values and if you actually at a state where you're at the maximum value and you want to reinforce that maximum you stay at that state。

 essentially so this means in branch prediction terms。

 if you're in this state it's also called a strongly taken state meaning that I strongly believe that this branch is going to be taken right you can think of it as belief right and if you see that the branch is actually taken you stay in the state。

😊，If you see that， the branch is actually not taken when you execute it。😊。

Your belief is modified a bit。 and you go to a weekly taken state。 Oh。

 I think this branch is going to be still taken。 I'm not going to change my mind because I've seen this。

That it was taken for at least twice。 Now I'm going to move to a state where I'm a little bit less believing that it's going to be taken。

 but I'm still believing that it's going to be taken right。😡，Okay。

 so one opposite outcome takes you to the weekly taken state now if you see that you predict that branch taken again。

 but if the branch is actually not taken again， then you change your mind right so basically you change your mind after seeing two opposite outcomes to what you kind of believe based on past information。

Does that make sense and you can do the same analysis for the predicted take。

 these are actually balanced states as you can see。Okay。

So that's the hysteris basically and as I said， if you're in this predicted taken state over here。

 you're thinking the branch is strongly taken so you don't change your mind。

 if you're in the weekly taken state， you change your mind。Now。

 of course the same problem exists right here， you can basically flip flop between predicted taken weekly taken state and weekly not taken states if the branch actually changes over there。

 so you don't perfectly have hysteris in that case。

 but you eliminate a lot of the downsides if you actually add more bits， three bits。

 three bit counter you can solve that problem but as you add more bits。

 it takes time to actually train the predictor as well because you need to see a lot of outcomes。

We're going to see an example with three bits later on from real processes。

 but that's the basic idea if you want to add more hissteres， add more bits。

 right then you change your mind even less frequently。

 but that may or may not be good depending on the branch behavior of course， right？😡。

Does that make sense？O。Okay， so basically bit each branch is associated with a two bit counter。

 this can be stored in the BTV or can be stored in the direction predictor that weve shown earlier I'm going to show that again。

 this one more bit provides hysteris and a strong prediction does not change with one single different outcome。

😡，Now let's do an analysis of this。呃。This is a loop with any durationerations。In this case。

 for example， you have 19 of these you execute the branch，19 of them are taken。

 and the last one is not taken。And you get 95% accuracy over here right basically you get all all of them correct steps except for not taken one right okay。

 assuming the country is initialized the weekly taken there's an assumption over here。😡。

If you look over here， assuming the country is again。

 it initialize to weekly taken or in this case strongly taken also， you basically get 50% accuracy。

So basically， you recover from 0% to 50%， right？😡，That sounds good and you basically small for Luke with few iterations。

 you make one less mistake if you think about it， and that may be actually quite large if n is small。

😡，If F is very large， none know this matters that much， right？Okay。

So basically now we have better prediction accuracy， but we have a trade off。

 we have more hardware cost right essentially counter can be part of BTB entry but still it's more hardware cost。

😊，Okay so then the question is this good enough， it turns out in at least in 1980s in many programs you get 85 to 90% accuracy with this prediction that's why it was implemented immediately in many processor today this sort of prediction doesn't work well in modern workloads modern workloads are actually much more intensive in terms of their branches they're much more complicated people actually as you add as you provide more performance in hardware at the software level people actually add a lot more complexities so workload becomes more complex so it becomes a chasing game essentially right you provide more performance and people need more performance because they make their software more complex right and branch prediction is an example of that branches are becoming less predictable compared to 40 years ago。

But okay， let's assume that this is 85% 90% is it good enough well。

 basically we go back to what we did yesterday， assuming a 20 stage pipeline with five bite fetch 80%。

Well， you get an IPC of fetch IPC of one as opposed to five。Doesn't sound good， right？

And you're fetching 400% extra， not good for energy， not good for performance， okay， assume 85%。

 still not good， assume 90%， still not good， right？😡，So we want to get as close as possible to 100%。

 especially as n increases and W increases， and these are actually higher in modern processors。

 both of them。Okay， so basically can we do better and we're going to talk about an idea called two level branch prediction that is again revolutionized how things are done about 10 years after that 1981 paper。

 this is a seminal paper in 1991。😊，And basically， the idea is to exploit another level of history history or predictability。

 so last time andtubit counter predictdors exploit last time predictability， right？😊。

But people realized starting with this paper that a branch's outcome can be correlated with other branches outcomes。

😡，Meaning if you execute some other branch at some other program counter。

 that can give you an indication of where this branch will go。😡，It's actually pretty cool。

 as we will see with some core examples， so this is called global branch correlation and you can actually build predictors that take advantage of it。

😊，IfPeople also realize that a branchs outcome can be correlatedre with past outcomes of the same branch other than the outcome of the branch last time it was executed so you can look back into the history a little bit more that's the idea basically it's also called local branch correlation so let's start with a global branch correlation because global is a totally different type of correlation even though you can say locals maybe similar to last time but you add a little bit more history right？

😡，Okay， so what is global branch correlation， the basic idea is if you're executing a branch。

 a bunch of branches， you have outcomes and recently executed branch outcomes and the execution path are correlated with the outcome of an next branch。

😡，Let's let me give you an example， so if you look at these two branches。

 the first one is testing some condition and doing something based on that。

 the second one is testing that condition and some other condition。😊，Now。

 if you executed the first branch， that gives you an idea of where the second branch might go， right？

😡，If the first branch is not taken second is also not taken right if the branch is not if the first branch is taken。

 then you don't know the second one， but at least you have some information now。😡，Okay。

 if you look over here， there are two branches， one is testing x less than1。

 the other is testing x greater than1。呃。And then another branch over here。

 So if you look at this one， if the first branch is taken。

 the second is definitely not taken right that's true for here Also。 if the first branch is taken。

 then a is set to two， then second is not definitely not taken。

So this is the reason why global branch correlation works。😡。

Of course we're not going to track everything that enable us to do this prediction we're going to summarize the information about where prior branches went using a bit vector we' are going to have a bit vector each bit in the bit vector will indicate the direction of different previous branches and based on that information we're going to index into a table and that table will tell us whether we should predict the current branch based on this past history has taken or not taken that's the idea basically okay one more example over here these two branches if y and z the first two branches are both taken then x is also not taken you can study it if。

😊，If y or Z， the first two branches， either of them is not taken， then x is also not taken。😡。

So you can see that actually， there's a lot of information that you have in the program。But。

Summarizing this information in a way that's hardware friendly is not easy right the key kind of revolution of this particular global branch correlation is two things。

 first realizing that there's global branch correlation Second summarizing this information a hardware friendly way such that it's easy to implement and if you have an idea that needs to go into hardware you should really do both basically okay let me give you a fun story this was a benchmark that people used to benchmark it's equation to truth table it's actually part of the electronic design automation suite that people used to design processors at the time and this was a benchmark and the spec workloads that people used to essentially compete measure the performance of different microprocesors with and most microprocess failed predicting this third branch over here。

Which is testing if A is not equal to BB， right？Now。

 after people start implementing these global branch predictors， this became very used to predict。

So if you look over here， if B1 is taken， is testing it whether a is equal to2。😊，If it's taken。

 then a is set to zero。😊，And if B2 is taken， then BB is set to zero。

 then this is going to be not taken， right because test is checking whether A is not equal to BB。

 right。😡，So if you know where these two branches went， taken， taken。

 then you know that you're going to predict that not taken。

And it's interesting that this benchmark was removed from the suite after people came up with a global branch predictors because this benchmark was not interesting anymore。

Because everybody got it right right so that's an interesting lesson also you can develop benchmarks to benchmark performance。

 but once the processor becomes good enough to execute that benchmark that benchmark becomes not interesting。

😊，There's another way of actually saying what I just said earlier。

 processor performance improves to adapt to workloads。😡。

But old workloads are not that interesting after some point because processor is optimized for them。

 new workloads actually challenge the proor much more right that's why it's always good to be forward looking as an architect because what that's what matters。

 what matters is the new workloads， not the old workloads in the end。😡。

Unless all workloads have something fundamental that doesn't change of course right in this case it was broken let's say okay so how do you capture this global branch correlation。

 let's take a look at an example as I said you need to summarize this information about global branch outcomes so basically we're going to summarize this in a bit vector we're going to call the global history register it's a global take not taken history of all branches01 essentially you encode each branch with a zero or1。

😊，You make a prediction based on the outcome of the branch the last time the same global branch history was encountered。

 I'm going to show you a picture soon， but basically you keep track of the global taken not taken history of some number branch I say all over here。

 but we're going to limited it to some number164 let's say 16 we're going call the global history register 16 bits each of them identifying a prior branch that was executed and each branch is encode as a zero or one if it was not taken it' a zero if it was taken it a one I'm going to show you a picture again and you use this bits vector as an address to index into a table that recorded the outcome that was seen for each for that GHR value in the past so last time you sold this global history register value last time you saw this pattern of outcomes the branch was taken or not taken you basically keep track of that。

So we're not using the program counter to decide what happened to the last time to this branch。

 we're using this pattern， the pattern of last 16 branches that were executed， taken。

 not taken pattern。😡，As an index into what happened when I saw the history last time right if I saw the history last time the branch was taken。

 then I'm going to predict thats taken if I if if the branch was not taken when I saw the same history last time。

 I'm going to predict that's not taken okay， that's the idea basically， but of course。😡。

You may still use to have two bit counters as opposed to one bit counter like I just said。

 you may still use history histores in this one and many works actually use that so if this is the global history branch predict it's also two level meaning it uses two levels of history global history register and plus the history at that global history register meaning what happened to that branch when you saw that global history register value last time so let me give you the picture essentially this is the first level of history you have a global branch history register M bits this is the direction of last end branches taken or not taken outcomes basically。

🎼It could be 16 bits。 Let me finish this and then we're going to take a break， but basically you。😊。

you shift in the last previous branches outcome whenever you execute a branch and you should talk the oldest branches outcome from this register。

 so you keep it always looking at the last end branches that you've executed。😡。

And you use this to index into a table of saturated encounters for each history entry。

 so if this is 16 bits， you have two the 16 entries over here。😊。

And each of these entries basically encode the direction the branch took the last time the same history was seen。

 This could be a single bit。Just like the last time predictor。

 but this could be also multiple bits like two bit counters that we have seen for hysteris purposes。

 okay？So you're going to have exercises in your let's say homeworks and maybe even exam questions it's going to be fun。

 it's not that difficult I think， but you'll see it。

 but this paper combining branch predictors that I recommend explains things nicely so as to why this work and how does this work so if you look at these easy prediction mechanisms。

 if you look at when you're testing I equals 100 and assume that you've executed this multiple times。

😊，Clearly this for looppe， this branch is usually taken right。

 you're going to iterate because 100 times， let's say。😊，But if you look at the global history。

 at this point， this branch is testing I， if you look at the global history register。

 it should look like 1110 mean because last three branches test J。😊。

And those outcomes should be taken， taken， not taken based on this information。😡。

And the previous outcome was taken so taken taken taken not taken and you predict taken for I so whenever you see taken taken taken not taken you predict taken for I now you shift in the taken outcome for I so this goes to the end over here one of them this earlier taken drops out so the next history is taken taken not taken and you see that history when you fetch the next branch which is beginning of this for loop the first branch in this for loop and this should be taken because clearly you're just starting this for loop so whenever you see the history taken taken not taken taken the result should be taken in this code structure and then you go to the next branch you shift in the outcome so the history becomes you shift out the first one you shift in the next one the history becomes taken not taken taken taken again the result should be taken over here so basically I kind of simulated part of it but essentially you can get almost perfect accuracy using this。

Structure。Okay， let me finish the Pentium Pro branch predictor and then we're going to be done essentially Penttium Pro we discussed yesterday or earlier that this is the first processor modern processor that was successfully implemented the out of order execution paradigm it was an out of order superscalealar processor。

 this is what made Intel actually extremely successful it was one of the best let's say money making processor in the market it actually input performance significantly the reason is not just out of order execution the reason is they also implemented this twole global branch predictor。

It was published in 1991， it was implemented by Intel four years later， immediately almost。😡。

Essentially， this was a two level global branch predictor， it had four bits， global history ages。

 not 16， but only  four bits。And it's had multiple pattern history tables of two bit counters。

 which pattern history table to use is determined by the lower order bits of the branch address。😡。

We may talk about that later but essentially it's the same idea and as a result of auto orderder execution。

 superscalear execution and twole branch prediction plus precise exceptions using the reorder buffer。

 everything we discussed so far and this branch predictor actually completes the full picture this was a widely commercially successful autoorder machine and it's actually in performance greatly compared to the previous penttium pentium which was pentium2 actually which was an in orderder superscalealar processor without this branch predictor it had a twobit counter branchch predictor。

😊，Okay， and this is the picture of Pantium Pro。So basically let me summarize and then we're going to take a break。

 essentially this is what we were doing， we had a program counter based predictor。😊。

We change that direction prediction， We don't use the program count training or use the global branch history to actually index into a direction predictor now this direction predictor has to be separate from the BTB because it's indexed completely differently from the BTB right let me just animate it again This is what happens if you do one level or last time type of branch predictor This is what happens if you actually use global branch history。

Okay， so this is a good place to stop， let's come back when the bell rings and we're going to try to improve this global branch predict's accuracy。

 and then we're going to talk about local branch predictions。😊，Okay。Okay。

 let's pick up where we left off at。Is everything good online okay？Okay， just to jog your memory。

 we covered the one level predictor which looked like this。

 use the program counter to make a decision in terms of the direction now we enhanced it with another level of history which is we use the global branch history to make a decision and then the history at that global branch history。

 okay。😊，Now you can actually improve this a little bit。

 there' is a paper that came out two years after that seminal paper that introduced two level prediction。

which remains as a technical report， it was never published anywhere。

 but it had a huge influence in the field， and actually I show you this description that I showed you is from that paper。

 for example， it introduced the idea of adding more context information to the prediction。😊。

And the idea is don't just use the global history to make a prediction。

 but also use information about other things one other thing obvious thing is the program counter of the branch basically take into account which branch is being predicted in addition to the global history and this makes actually a big difference also it turns out it's called the G sharere predictor。

 you basically use global history register hashed with the branch PC hashing means XOing for example you can do a bit twice XOR of the branch address program counter and the global history register and then you use that to index into this direction predictor which is called the pattern history table or branch history table。

😊，That's the idea over here， so why does this make sense because you use more context information？😡。

For prediction， you don't just use the history register or branch address， you use both of them。

 and this gives you better information about what's going on in the program essentially。

You could actually use other things also， but I'm not going to talk about that。

 but this is the state of the art again in terms of using context information this also gives you something else which is very interesting if it turns out if you only use one of these。

😊，You don't utilize your table very well because the values that only one of these takes is not very well distributed。

 let's say， across the entire address space of this table。😡。

assumee that each of them is 16 bits you have two of the 16 entries over here your branch history patterns may not be covering entire two of the 16 space but if you actually do an Xor you use some randomization this randomization is not just random it's really taking into account context taking into account useful information it's also distributing the information to different entries in this table so you get better utilization of the table you can better distinguish things。

😡，Okay， this is very interesting downsides of course everything is the downside and upside clearly you get better information over here to make the prediction。

 you get better distribution of the information in the memory that you have dedicated for your branches。

 but you increased access latency now because you have an extraorgate。😊。

In front of your access to the memoryme that stores your， let's say， two bit counters。

Yeah so but this is not that bad so we're going to make it much worse actually we're going to have sophisticated branch predictions that makes the access latency much worse。

 but this actually had a big impact also in improving prediction accuracy。Okay。

 so this is what the G sharere branch predictor looks like， you take the program counter。

 take the global branches tree， program counter is the address of the current branch。

 global branches trees is which direction earlier branches went， you exhort them。

 and then you index into the branch predictor direction predictor and if it's says taken you use the target address from the BTB as your next fetch address。

😊，Makes sense so flu right。Okay。Okay， so that was global branch correlation。

 let's talk about local branch correlation， I'll not go into this a lot of detail。

 but I'll give you one example essentially in the same work where global branch correlation was introduced。

 local branch correlation was also introduced and essentially the realization is that a branch's outcome can be correlated with the past outcomes of the same branch。

😊，So this is also well explained in this technical report that I mentioned。

 so if you look at this loop branch over here， I'm going read it from the paper actually if the loop test is done at the end of the body the corresponding branch will execute the pattern 1110 to the n times 111 where 1 and0 represents taken and not taken respectively and n is the number of times the loop is executed hopefully this makes sense right you basically three times you take the loop branch last time you don't take the loop branch so you get out of the loop you do something else eventually you return back to the loop right because the program structured like that。

😊，Clearly， if we knew the direction this branch had gone on the previous three executions。

 then we could always be able to predict the next branch direction。😡。

Because this is an easy to predict bench actually with this sort of mechanism。

 so basically the key is really identifying these numbers over here so let me give you how local history works。

😊，So this is again from the paper， this is a loop closing or loop ending branches history。

 it's always doing 1110，1110，1110，1110 as you can see right taken taken taken， not taken， taken。

 taken， taken， not taken because the first three times is' taken the last time it's not taken。😊。

Bup it ratess four times the session。To predict a loop branch perfectly。

 we want to identify the last iteration of the loop essentially。

 So by having a separate pattern history table entry， twobit counters， essentially。

 for each local history， we can distinguish different iterations of a loop。😊。

This works for short loops right so you need to basically keep track of the history of the branch at that program counter because some other branch may not do this right some other loop branch may be doing 11。

1，10 11，1，10，11，110 et ceter。😡，So the reason this works is if you look at these different points in whenever you do 1110。

 whenever you execute this branch multiple times you see different histories right so if the branch if the past four branches past four times the branch executed was 1011 you should predict that's taken because you're still in the loop iterating if it's 1101 it's taken it's 1110 it's taken again only if the last four executions of the branch was not taken taken taken taken the next time you should predict that is not taken and by having the local history index into different locations you can identify different loop iterations in which this branch is executed that's the idea it's not the easiest way to identify this sort of loop later as we will see people introduce specialized loop predictors they basically try to identify branches that go backward and that iterate like this and they basically have a very specialized predictor for that we will see that but this is one way of handling the local history。

😊，Okay， so let's take a look at how do we capture this， essentially you do the same thing。

 you have a per branch， you have a history register。

 this history register encodes which direction this particular branch went last n times so it's a per branch history register as opposed to a global history register that collects information from all different branches。

😊，You associate the predicted outcome of a branch with a take， not taken history of the same branch。

😡，And you make a prediction based on the outcome of the branch the last time the same local branch history was encountered。

 so it's called the local history or local branch predictor again， it uses two levels of history。

 one level per branch history register。😊，The second level is a history at that history register value。

 What happened last time I saw this history for this branch， did I take the branch。

 did I not take the branch and you can add hysterosis on top of that。😡。

Okay again the picture looks looks like this it is opposed to having a single global history register now we have many local history registers。

 one per each branch I know why this wants to okay maybe it's going to cover up again essentially the first level is a set of local history registers each of them is Mbits you select the history register based on the program counter of the branch because we want to have per branch information the second level you use the history register you selected an index into a pattern history table。

😊，This is a table of saturating contrast for each history NP p， essentially what I said earlier。

 the direction the branch took the last time the same history was C and hopefully you can identify the ending iteration of the loop for example。

 assuming it's a loop branch， there are other cases where this is useful but it's a little bit harder to think about loops are easier to think about。

😊，Okay， hopefully this makes sense right so the structure is very similar as you can see。

 the key is really encoding this information in a nice and clean way so that the hardware doesn't become complex these history registers that encode taken and not taken with a single bit and you have a bit vector for what happened to the branch last end times you executed it is a nice way of encoding the information and you index into a table so everything becomes simple if you think about it。

 Of course things structure become much larger if n is very large if you want to keep a history of 1024。

😊，Then you have a the 1024 entry。Cattern history table。

 which is not realistic right that's why the histories are usually initially it was four。

 we will see 10， 12， et cetera today it to actually be 16。

 but there are other methods as we will see that actually makes those histories larger but not this method。

😊，Okay， so this is what a two level local history branch predictor looks like。

 you take the program counter address of the current instruction。

 you index into an array of local history registers。😊，And you pick one based on the program counter。

 which directions earlier instances of this branch went。

 it basically specifies which directions earlier instances of this branch went。

 and then you use that to index into a pattern history table。

 which tells you what happened the last time you saw the history for that branch。

 and then you decide whether or not it's taken based on the status of the single bit or two bits or three bits over here。

 depending on whether or not you use hysteris。So now you can see that that's much more complicated。

 right？Earlier what we did let me go back to that picture it's gonna take some time so we make things more and more complicated so this was our program counter we just use a program countered index this is our global Benches register we just use it to index This was yeah and then we exhort them together and index them that's G sharere and now if you want to do local history it's a little bit more complicated you index into one table to get the local history register and then you use that to index into another table to get the direction that you want。

😊，So this is a little bit more expensive than global history。

 but it does make a difference as we will see this is also implemented in modern processors。

 modern processors usually implement a global predictor。

 a local predictor and some sort of loop predictor and some sort of other mechanisms as we will see soon。

😊，Okay， so this paper that introduced the tool level prediction ideas actually generalized the concept。

 I will not go into a lot detail， but this is actually a family of mechanisms this is a global predictor basically I showed you earlier you have a global history register。

😊，History registry can be essentially global and you have a pattern history table。

 this is a direction predictor， two bit counters， that could also be global。

A global predictor is the simplest， both all of these are shared across all branches， essentially。

 all branches contribute to them。😡，And then on the other hand。

 you have something that's unimplementable， meaning extremely expensive。😡。

You have a pattern history table over here no sorry you have a history registers。

 you have per branch is here registers， every branch has its own history register so that's very local and then every branch has also its own pattern history table to bid counters so for every branch you have a separate。

Now that's clearly very expensive right and there could be thousands of thousands of branches in program you're not going to have hardware to accommodate that in some programs there could be millions of branches so what's more realistic is somewhere in between essentially and they're actually different ways of thinking about that in between so if you're interested you can look at this paper but this paper had a lot of impact on processor design it was selected as one of the test of time award winners for the microcon and if you're interested you can read the author's retrospective on this topic。

The second author is my PhD advisor。Okay。Okay， the question is， of course。

 can we do better now I've gotten you to the 1990 s， right， we're at 1990s。😊，The question is。

 can you do better than all of this， and that's always what has enabled better and better performance processors。

 right？And the answer is yes， of course， right if you actually put enough creative people on a problem。

 they will come up with good solutions， even on very difficult problems。😊，Okay。

 so basically let me give you some other ideas， essentially there are different ways of doing better。

 one is to realize that different branches have different types of predictable。😊。

Some branches are more predictable using local history。

 you've seen that with loop branches right shorter loops for example。

 some branches are more predictable using global history if for example the correlation。

 global correlation leads to a better prediction right clearly there are cases where that global correlation is much more important than local correlation for some others a two bit counter is enough maybe a one bit is enough right last time the branch always does what it did last time right never always not taken。

😡，An error branch， for example， is testing for an error if it's taken。

 that means that you're going to quit the program because there was something wrong。😡。

That' probably always not taken and when it's taken， it doesn't matter for you， right？

Yet basically a single bit is enough right so that could be encoded using static profile information。

 so the observation is that there is a lot of heterogeneity in the predictability behavior of branches so don't use one size fits all hardware to cater for everything。

😡，When you have heterogeneity， you should always have heterogeneous hardware essentially to cateror four different things in the end。

😊，So basically there is no one size fits all branch prediction algorithm for all branches。

 exploit this heterogeneity and predictability behavior by designing hybrid or heterogeneous branch predictions。

Which is essentially what we have in all processor today。

 so the idea is to use more than one type of predictor and select the best predictor。😡，Clearly。

 this adds complexity now because you design multiple predictors and you also need to design a selector。

 Me predictor to decide which predictor to use for a given branch that you're predicting。😡。

So for example， you can have a hybrid of two bit counters and a global predictor。

 right that's one example I'm going to show you a more sophisticated example soon。And again。

 this was introduced in this technical report， which was quite infial。

 so advantageous essentially this gives you better accuracy because hopefully you can use the best predictor that you think is the best for each branch at a given point of time。

 there's also another benefit which we didn't discuss earlier。😊，If you have a long history。

 it takes time to warm up the predictor， meaning you need to see those history， see the history。

 different outcomes of the history so that you can actually warm up the bits。

 right the prediction bits。If you don't actually warm up the predictor。

 you may actually make not code predictions， you may want to use a simpler predictor that warms up quickly until you see the entire history because if you think about it。

 if you have 16 bit history， if you're actually exercising a lot of those bits。

 that means you need to see a lot of outcomes to actually warm up the predictor。😡。

So that's another benefit than accuracy， actually， this impacts accuracy also right because if you use a simpler but slightly more accurate predictor while the bigger predictor is warming up。

 your accuracy also increases。So while there are clear disadvantages to hybrid branch predictors。

 you need a predictor to select which predictor to use。

So now you need to predict which predictor is better。

 right that's another level if you think about it， which is fascinating。

 how do you design that becomes interesting also right？😊。

It's longer access latency because you have multiple things and more hardware and more complexity。

 so whenever you have heterogeneity， that's usually the case。😊。

But this idea was also implemented and it's implemented existing all of existing processors actually all high performance processors and this is a beautiful paper that I recommend the Alpha 21264 microprocess's one of the fastest processors of its time it was competing with Intel at the time is digital equipment Corporation and this was their flagship processor processor which was faster than Intel at the time it implemented you can see that at the time their minimum branch penalty was seven cycles so it's a smaller pipeline。

😊，They can fetch four instructions per cycle， but typical branch parentties longer and you can see that target address are stored in the instruction cache which we may get to later on but basically this is what the predictor looks like you have let me start with the global one you have a global predictor over here you have 12 bits of global history much larger than what Intel implemented in their Pentme Pro and you can see that the global predictor has two to 12 entries each of them is twobit counters it supplies one prediction。

😊，Using that history and then there' is the local history table basically you have 102410 bit counters based on the program counter you pick one of them that's your local history for that bench and you use that to index another。

Local predictor table， which happens to have 1024 entries and three bits。In each champion。

 so therefore based on his churches， et cetera， they decided three bits is a better idea over here and you basically make two predictions。

 one is a local prediction for the branch， the other is a global prediction。😊。

And depending on which predictor you think is more accurate， you select the final prediction。

So how do you determine basically they have what is called a choice predictor。

 it turns out that takes the global history。And based on which predictor was better。

 the last time you saw that global history， it selects a predictor。😡。

To choose this may not be the best heuristic， but this is what they found to be working for their system。

 right There could be better heuristics， of course， right， you could imagine。

But this is a reasonable predictor at the time in early 2000s in late 1990s。

And you can see that it's complicated much more complicated than what we've seen so far right we started with no bits at all now we have a lot of bits。

😊，And it's going to be more and more bits。Okay。There's another idea that actually is very powerful。

 which is basically get rid of things that you don't want to spend resources on。😡。

This is called filtering。There are some branches that are easy to predict。

 don't spend your valuable resources on them， filter them out。😡。

Many branches are biased in one direction， for example， 99% taken。

These branches pollute the branch prediction structures。

 basically they make the prediction of other branches difficult。😡。

By causing interference in the branch prediction tables and history registers。

 because there might be some other branch that's really important to predict and it's very hard to predict because maybe it's 50% taken right。

 but now you're actually using part of your resources to update the counters and the global history etc for a branch that's almost 100% taken right。

So the idea is not do that， detect such bias brancheses somehow either through compiler。

 which is always a danger because compiler may not have perfect information or in hardware。😡。

Monitor branches and figure out which branches are ease to predict you could actually add another predictor that predicts which branches are easy to predict。

😡，And filter them out， don't use these sophisticated structures because these branches are easy to predict don't pollute the other things Okay。

 that's the idea basically use them use predict them with a simpler predictor。😡。

This book called branch classification， again， and another influential paper that talks about it。

Okay， so basically are we done with branch prediction I'm going to go into more sophisticated ideas essentially the Mcfarling paper。

 the technical report that I mentioned showed that you get 90 to 97% prediction accuracy on average again there's old workloads today that number is still low actually if you look at graph workloads for example you do large scale graph analytics。

😊，A lot of branches over there are very difficult to predict because you actually are trying to traverse the graph and the input pattern in which you're trying to traverse the graph is hard to predict because it's dependent on what you're searching for in the graph right。

 think about a social network you try to find I don't know who is close to you at a given time you traverse this graph and it may not be not you may not have a very predictable patterns right。

😡，So at that time there was no such thing， no social networks， et cetera。

 basically you get 90 to 90%。😊，But the same paper shows that difficult workloads still suffer a lot。

 for example， a compiler at the time one of the difficult workloads was compiler。

 so this is a difficult workload， the maximum IP with this hybrid bench predictor that they showed in this paper was nine assuming all of the resources are there to execute。

😊，But actually if you can do perfect branch prediction， you could get to 35。

 35 instructions per cycle， assuming you're not limited by other resources。

 you could execute any instruction that you want with any resources that you want so branch prediction still limits performance significantly on some workloads even at the time。

😊，Today is much worse。So basically， people kept introducing new ideas。

I'll go through a few of these so loop branch predict I kind of mentioned this essentially this is a predictor that detects loop branches and basically says。

 oh， if I have a predictable iteration count I can filter these out of any of the other predictors basically detect a loop branch that is backward branch and then say the last time I saw this backward branch it executed it was taken four times so count how many times this branch was taken next time you see this branch start counting again and when you actually get to that limit predictable branch has not taken because you're not going to iterate again。

 this is assuming that you're gonna to have a predictable iteration count on the same loop this works well for loops with small number of iterations where the iteration counts is predictable but there are enough of these that it was implemented and many processors starting with Intel PeniumM。

😊，I will show a picture of this， but I will not dwell on this that much we're going to study especially perceptron branch predictors because this is going to be one of the most successful applications of machine learning to hardware today。

😊，Essentially， the idea is to use what is called a perceptron， how many of you know perceptrons？😊。

Okay。This is a single layer network basically today we have neural networks perceptron is the predecessor of all of those neural networks。

 essentially it's not multilay it's a single layer there are multi layerer perceptrons also but what we're going to see is single layer so essentially the idea is to learn direction correlations between individual branches or at least more accurate the history bits and the current branch you are predicting and you assign weights to correlations using simple machine learning it was introduced in this another seminal paper now we talked about 2001 we talked about 1981 1991。

 2001 we're getting closer to today。😊，And then people have also introduced different history lengths。

 people understood actually that a single history length doesn't work well。

 there are some branches that you need to look at close by history。

 there are some branches you need to go a thousand branches ago。😊。

So how do you accommodate those very different history lengths and this paper introduced a geometric history length branch predictor with different tables and each table caters to a different history length。

 essentially。And both of these are also implemented in existing processor。😡。

So this is Intel PeniumM I already described the loop predictor at least at a high level。

 but essentially it's similar to what I just described， it exists。

 it is implemented in many processes， I will take a very quick aside over here。

 we've been talking about conditional branch prediction。

 but there are also indirect branch predictors in existing process so when you do a jump to a register value。

😊，It's not conditional， you always do it the target， condition is not a problem。

 but the target is a problem over there because target is different in every execution of the branch。

 so how do you predict the target？😡，So there are target predictors in existing processors also。Okay。

 this is to show you that the branch prediction logic in an existing process is actually huge。

 according to Intel at least， this is this part is dedicated to branch predict。

 branch prediction logic， all of the structures。😊，Okay let me jump into perceptionceptron since many of you don't know it。

 this was actually a simplified model of a biological neuron。

 it was developed in 1950s and Rosenmbblt has this beautiful paper that talks about it。

 this is when actually people were thinking about neural networks。

 how do I model the behavior of a neuron and how do I actually make it useful in computation。

 how do I design an artificial neural network， not even an artificial neural network。

 where people were not talking about networks at the time， artificial neuron。

 how do I model it right？😊，It's also a simple binary classifier。

 basically people thought of neurons as binary classifiers。

 meaning you take an input vector x and map it to a1 or z。😊，呃。

Input is essentially a vector x you can think of as bits。

And perceptron learns the linear function if one exists of how each element of the vector affects the output stored in an internal weight vector so it basically checks how each of the elements in the input are correlated with the output essentially by storing an internal weight vector and learning those weights it's very similar to a neural network except a single layer right how many of you are familiar with neural networks。

😡，Probably more yeah， okay， you're going to learn it at some point。

 but this is the simplest you can get let's say it's not a network yet well。

 I mean one layer network。😊，So basically， output is determined by。Multiplying the weight。

With the input vector we're multiplying the weight vector with the input vector and checking whether that's greater than0 you can optionally add a bias this is basically saying oh there's a bias towards0 or1 essentially you can actually say that so let's take a look at it in the branch prediction context so you could use this for example to detect a language the input vector could be words that you see you may have actually x words weight vector maybe actually the probability that that word belongs to let's say a language German language and then the output maybe if the output is greater than0 when you multiply the input vector with the weight vector if the output is greater than0 you have a good confidence that oh it's probably German you can think of it that way you're classifying some inputs in this case you're classifying whether this set of words that you input belong to a language X or not。

😊，In the branch prediction context， we're going to use bits a single bit。

 essentially vector x is the branch history register bits， this could be a global history register。

 it could be local also but global is easier to implement as we have discussed earlier。😊，诶。

And I'll put this prediction for the current page。And the idea is to learn these weights。

 internal weights。That basically learn how each of the branches history register bits correlate with the output of the branch by assigning weights to each of these bits。

😡，So okay， let me give you a pictorial view essentially use a perceptron to learn the correlations between branch history register bits and branch outcome。

 you essentially learn a target boolean function of n inputs so if you look over here there' are some internal weights that you modify。

😊，These are the inputs。😡，These are the essentially X input。

 each of them is a bit in the branch history register。

And by multiplying x's with the internal weights， and then there's a bias bit。

 basically you can determine which branch is biased one way or another， let's ignore that for now。

You do this calculation essentially， you multiply the x vector with the weights and you check whether y is greater than the。

 each branch is associated with a perceptron， a perceptron contains a set of weights， WI。

 each weight corresponds to a bit in the global history register。

 it represents how much the bid is correlated with the direction of the branch。

 so these weights actually store the correlations。😊，So a positive correlation means。

That bit has a large positive weight， meaning that bit if that bit is one and you have a large positive weight。

 you're likely that this bit this prediction should be one right unless some other bit is negatively correlated and then you do the complete calculation negative correlation means you have a large negative weight and you keep learning these weight space on the execution you adjust the waste there's a training function which I will mention but I will not go into details about but you can read about so how do you do the prediction essentially you express the global history register bits as one or minus1 in this case taken not taken because multiplication needs one or minus1 multiplying by zero doesn't give you much information。

😊，Essentially， you take the dot product of global history register and weights。😊。

Which is what is shown here， if the output is greater than zero。

 that means the positive correlations kind of dominated。😡。

Or positive correlations are higher than negative correlations as a result you predict take。

Makes sense， right？So basically have as any neural network or classifier。

 you need to train the network using some training function， which I will not go into again。

 you can read the paper， you can look at it， you can make there are different ways of training it also but perceptron is simple。

 so training functions is also relatively simple， but still it requires multiplications as you can see。

So far we have not done any multiplications in branch prediction now we're doing multiplications right okay prediction function also requires multiplications as you can see right and then there's a bias weight which now I will get to it's the bias of the branch independent of the history so you can actually encode a bias for the branch also。

😊，But you can see this is the branch address， using the branch address。

 you index into a table of perceptrons， you take the perceptron associated with the branch。

You select the perceptron and you multiply it with the history register。

 compute why check if it's greater than0 that gives you the prediction and when you have the branch outcome。

 you take the selected perceptron and adjust the weights。😊，Okay。😊。

So you could replace the perceptron with a multi layerer network that is used for other things today。

 but that would make things even more complex， this is already complex actually。😡，Okay。

 so I've showing you the dot product of GHR and perceptmates and then you compare the output to zero so okay。

 so this actually works。😊，This is one of the things that I implemented during my PhD because I was actually doing some things that we will discuss later on memory latency tolerance and branch prediction was very important to me。

😊，And I implemented this and immediately I saw a 20% reduction in wren misrediction rates。

It's fascinating， many things don't work immediately when I implement it。

 but this is one of those things that works。😡，Okay。

 the advantage is you get more sophisticated learning， better accuracy。

 now you can distinguish which bits actually are better correlated with the outcome of the branch that's what you're doing here essentially。

😡，It also enables long branch history lengths of course if you have multipliers because now your tables are not indexed using the history length。

 right your perceptron can be wide it could be a 102004 entry， perceptron。

 your multiplications in multiplications increase， but your table can be relatively small。😡。

So it gets you better accuracy that whales this advantage clearly is complexity now you need a multiplier adder tree to complete the perceptron multipliers are essentially ater trees。

😡，Also there are some learning disadvantages which could be alleviated with other learning methods。

 so perceptron turns out to be it cannot learn linearly inseparable functions again if you don't understand that don't worry about it。

 this is a theory of learning a little bit essentially you cannot learn extra type of correlation between two attributes and the branch outcome but you can actually by making your learning model more complex you can overcome the solve so more complexity overcome some of these things。

😊，So this is a successful example of use of machine learning and processor design it's implemented in some processors I'll give you a couple of examples this is a Samsung processor which was actually had a lot of innovative ideas and then later Samsung decided oh we're not going to have a processor team anymore so if you look at this paper none of the authors are affiliated with Samsung you don't have any Samsung name even though the papers of other Samsung processor which is funny for me these guys all work from the processor and then this move to very different companies afterwards but they actually had a lot of innovative ideas including this perceptron predictor implemented the Samsung processor they also implemented one of our ideas on doing indirect branch prediction virtual program counter predictionction which is if you're interested you can read it I'm not going to talk about that。

😊。

![](img/387006f5726e351c112c1926823defef_6.png)

But it's also implemented on processors that do exist， which is AMD。

 so AMD implemented a perceptron branch predictor， you can read there， so you can see for example。

 they actually have multiple branch predictors， they have a hash perceptron。

 which is one way of implant care seron， but they also say that you can get significant branch prediction accuracy。

😊。

![](img/387006f5726e351c112c1926823defef_8.png)

So this is some pictures that show essentially how perceptron operates from one of the websites that analyze this AMD chip if you're interested you can look at this。

 but this is essentially what I said earlier， I just put these on these slides from that website because they're kind of nice because you can see it and they actually are reasonably accurate if you look at this。

😊。

![](img/387006f5726e351c112c1926823defef_10.png)

So it turns out this AMD processor also implements something called T。

 so they have multi level branch predictors。😡，Not hybrid， they have hybrid branch predictors。

 but they also have multilevel branch predictors， meaning they have a branch predictor that's relatively quick perceptron that makes a decision and then at the same time they start access to another branch predictor that's relatively slow。

😊，And if that branch predictor that's relatively slow but more accurate says the previous branch predictor is incorrect。

 they flush the pipeline quickly and they refreshch， but this is still a prediction。

 they don't flush the pipeline based on the outcome of the branch， the branch is not executed yet。

 they flush the pipeline based on a more accurate predictors prediction。

So you can see how complicated our fetch engines and processors are today。

 right you have levels and levels of prediction。

![](img/387006f5726e351c112c1926823defef_12.png)

Okay， now we're going to talk about that T predictor's actually that AMD thinks is more accurate。

 but slower。😡，Any questions， I'm going through a lot of ideas， as you can see。

This is fascinating as you can say if people have come up with a lot of creative ideas。

 so let me talk about this， this is very interesting because it turns out this is a little bit more accurate than the perceptron maybe we haven't figured out how to do the perceptrons yet this is implemented many processors。

😊，And the idea is to use multiple history lengths so far， we've been using a single history length。

 right？😊，The observation is very fundamental， different branches require different history lengths for better prediction accuracy。

And the idea is to have multiple pattern history tables indexed with global history registers with different history lengths and intelligently allocate pattern history tables entries to different branches。

 so it's going to be a little bit more complicated as you can see。

 so you have some base predictor that use only program counter information。😊。

You have another predictor over here that uses a small history length。😊。

A program counter hashed or exhort with a small history length。

 and then you index into the table and then gets the prediction。

And then you have a tag to match the index correctly， so these are actually relatively small tables。

 but you need to be very accurate in matching that you actually have the entry over here。

And then you have a little bit longer history length it's in fact these history lengths form a geometric series in the original paper so that you can get to very small history lengths。

 larger， larger， very large history lengths quickly because of geometric series。

 nature of the geometric series， and you can see that you make many predictions。

 and then you decide which one to use。😊，So it's a little bit complicated， you have many tables。

 this could be 10 tables， 20 tables if you want。😡，Okay and this is introduced in this paper geometric history length predictor so there are a lot of policies here in terms of which predictor to use。

 which predictor to update， et ceter， I will not go into that there's a lot of let's say heuristics that you need to make but if you actually design this carefully this could be very powerful and very accurate。

😊，And the key idea is there， basically the key idea is really use different history lengths for branches that need that work well with different history lengths。

 then the rest is implementation， but implementation matters a lot too because you can see that there's a multiplexer critical path over here。

 right？😡，Okay， so this is also implemented and this is again from that website。

 So let's talk about the advantage so you can choose the best history length to predict each branch better accuracy。

😊，It enables long branches history lengths， better accuracy。

 so this actually enables long history lengths much more efficiently in a sense than a perceptron because you can add more tables and you can actually have a geometric series of history lengths or a different series of history lengths so you can actually be very frugal in terms of hardware。

😡，The disadvantage is that design complexity is not low and getting it right is not easy。

 a lot of heuristics are here。😡，You need to choose good hash functions and table sizes to maximize accuracy。

 mini latency， even then minimizing latency may not be easy as we have seen with the AMD picture earlier。

 but this is a very successful recent idea also relatively recent we're talking about 2006 or so that is used in many modern processor designs as well so again AMDs then2 had the perceptron as the L1 level one predictor and the T as the level2 a lot of Intel designs also use T I believe。

😊，Okay。So this is actually a nice picture from this Wiiki chip that analyzed the AMD processor again。

😊，I will skip this， but basically there is a lot of analysis of how global branch predictors work these folks as early as 1990s analyzed which branches you should really use to predict the current branch。

 it turns out。If you're predicting a branch， you can look at a few branches。

 but isolating those few branches can enable you to predict this branch really well。

 The problem is which are those pre3 branches， they actually differ for every branch。😡，Some of them。

 for some branches， those three branches are very far away， for some branches。

 those three branches are very close in execution and for some other branches。

 those three branches are kind of randomly distributed in execution。😡。

So figuring out which branches to actually use information or take not take information from is not easy。

 and again these are old programs， new programs are actually quite different new workloads。😡。

But it's good to do this analysis to do better understanding， I think the next big。

 let's say revolution and branch prediction will come from better understanding。

Okay the question is always can we do better right so this is mostly the state of the art of what we have in branch prediction today so this is an ugly picture it's a beautiful paper but an ugly picture let's say but it's kind of convey idea this is called page statistical correlation and local loop branch predictors it's a very hybrid branch predictor you use basically PC and global history and use this tagged geometric history length predictor you get a prediction and a confidence level in the prediction。

😊，And then you apply some statistical correction methods to it that I'm not going to go into。😊。

And that is going to be part of your prediction and then there's also another prediction that comes based on some information。

 you also take take on other stuff like global history。

 local history and something called skeleton history that I'm not going to go into detail again you can read the paper if you're really interested and then there's a loop predictor and basically the final prediction is an outcome of deciding which predictor works better over here so there's a lot that goes into this a lot of things that we discussed is there actually almost everything we discussed is it there but there's more as you can see right in fact in particular I'm going to talk about confidence which is actually a very important concept。

😊，But this is 2014， as you can see now we're in 2010。

 and this is actually very close to the state of the art in modern Pros today。😊。

People are experimenting with more sophisticated ideas like convolutional neural networks。

 if you're interested you can look at this， essentially they're actually targeting。

 identifying what I just said earlier， identifying the correlation between a branchess outcome and a large noisy global history as art ideally you would like to identify which branches affect this branch。

😊，And they use convolutional neural networks over global history to expose hidden correlations for hard to predict benches。

So again， I will not go into detail， but it's a commvolutional neural network that's used in vision。

 for example， it's very similar。😊，呃。You use this only for very hard to predict benches and you predict everything else with。

😡，This monster。So everything else is also hard to predict if you think about it right for other branches you use a huge heterogeneous monster branch predictor and for even then there are some branches you cannot predict and this thing that's even more complicated can be actually。

😊，Helpful。Okay， and they show good results in this work， which I'm not going to go into。

 this is not implemented yet， it's very expensive， but there could be a path for implementation in the future。

😊，Okay， let me give you another idea， this is actually very heavily used for many reasons。

 and the idea is bench confidence estimation。😡，Essentially。

 the idea is very similar to the meta predictor that we have seen if you have a hybrid branch predictor。

 you decide which predictor is likely more accurate and choose that predictor right here we estimate if the prediction is likely to be correct。

😊，So estimate how confident you are in the prediction assumption， so why would you want to do this。

 it could be very useful in deciding how to speculate， for example， meaning which predictor to use。😡。

Whether to actually keep fetching on this path， maybe you wont say， okay。

 I think I'm very likely on the wrong path right now， and I don't know how to correct things。

 let's say I'm going to stop fetching。😡，Let me save energy， at least， you could do that。

Or you could use some other methods of handling branches which we kind of discussed yesterday and clearly we're not going to have a lot of time to discuss today。

 but you can use the backup slides if you're interested so basically this is good for decision making and this was introduced in the seminal paper again another paper that won a test of time award from the microconference。

Because it's implemented and essentially all modern processes so basically how do you estimate confidence there may be many ways of estimating this conference in this particular paper they kept their record of correct incorrect outcomes for past and branches and instance of the branch and based on the correct incorrect patterns guess if the current prediction is likely to be correct or incorrect and I have a misspelling。

😊，Oh， I don't know how this misspelling sur so many years。There you go。It's amazing。

Whenever you go back and read an older paper， you figure out oh you could have written this better misspelling is a bit harder to spot。

 maybe okay。😊，Okay， let me remove this。Okay so basically this is an example it's very similar to if you think about it the way they designed the selector in the alphapha 21264 predictor right these are concurrent works actually Alpha 21 to64 was being designed when this paper was written essentially you use a global blank history register and exhort with branch address and basically you have a table of confidence counters basically say'm based on what where I am I think this I'm very confident the prediction right again you can use a lot of information for this purpose but this could be useful this could be useful for deciding which predicted use。

😊，This could be useful for deciding whether to keep fetching。

 so this is another paper in 1990s that introduced the concept of pipeline gating。

 the idea is very simple again， so you basically count how many low confidence branches you have fetched。

For every branch that you fetched， you make a prediction。

 you keep fetching at some point you say the probability of me being on the correct path is pretty low and I don't know which branch to correct because I have so many low confidence branches。

 so I'm going to stop fetching。😡，At least I will save energy withs the idea over here。

 and it could be a good idea depending on the probabilities of branches that you fetch like the accurate like probability of correct predictions。

😊，Okay， so I give you a big idea， like another big idea， let's say so。

We're not done with branch prediction yet， people are actually still organizing contests so if you actually want to participate it may be difficult at this time in your let's say career。

 but I've given you actually a very concise summary of where we are in branch prediction you could participate and maybe even won win if you're interested the deadline is May 2 I would prioritize EDCA but again you don't need to let's say have an exam on May 2 but this is fun and this sort of contest actually enables a lot of new ideas in branch prediction data prefiting etc。

😊，I think this brings me to other ways of handling branches， which I'm not going to cover。

 but you can look at delayed branching in the backup slides over here。

 and we have actually other lectures if you're interested on how to do better branch handling。😊。

So I will see you next week I think these are all backup sites I'm going to put them up if you're interested you can look at different ways of handling branches。

 so don't think that branch prediction is the only way。

 but it is really the dominant way it's the way that has been successful because you don't need to change anything in software for any of these if you think about it。

😊，Okay， have a great weekend， I'll see you next week。



![](img/387006f5726e351c112c1926823defef_14.png)