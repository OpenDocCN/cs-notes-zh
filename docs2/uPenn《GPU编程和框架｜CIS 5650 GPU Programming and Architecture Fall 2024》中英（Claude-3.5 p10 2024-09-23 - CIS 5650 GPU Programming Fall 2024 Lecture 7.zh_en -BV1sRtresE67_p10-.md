# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p10 2024-09-23 - CIS 5650 GPU Programming Fall 2024 Lecture 7.zh_en -BV1sRtresE67_p10-

Or from the。

![](img/bb4f2a016824f794f04b491deb09f3dd_1.png)

😀嗯哼嗯。😊，good so what can we infer from the difference between the L1 to L2 memory transfer size and L2 to device memory is that just some things is there there's some things that are cached in L1 that we don't need to go to L2 for？

Probably that would be my guess because you may have situations where。嗯。

And I think it's more on the right side than the read side because the read side is generally optimized right side is randomized because that's where we are changing our index。

What may happen is that something may have been cashd from an earlier war and may not may have been a cash hit rather than a cash miss。

Okay， so even though it says hit rate 0。00% on cash。

 maybe there is some hit that okay so so what you're likely seeing is on L1 because the hit rate is zero because you're never reusing memory you're reading from A and writing to B so there's no reuse whatsoever。

Whetheras for L2， you the it may have。Cha have some memory through you know。

 what's the term I'm forgetting prefeing and stuff， so that's where you may have a hit rate。O。

Any other questions？I think， no question。Okay， the other thing I'll share here is that you know you want to whenever you're profiling you want to run the kernel multiple times。

 so I'm going to jump to let's say the middle kernel which is five out of 10 runs and you want to check for that profile as well just in case there are any any differences in that。

Okay。嗯唔。The other so if we go back up， it said check schedule statistics and W statistics so let's look at schedule statistics first。

And here what we are seeing is。We've launched active ws for active active ws per schedule is 6。67。

 And you can， if you highlighted， you can go through all of the。Actual details here。

 and no eligible percentage。 So this is really important here。

 So no eligible percentage means how many times was the scheduler waiting for a war。

And know what was available。Remember when we said， hey。

 you want to have as many warps as possible to be able to take advantage of all the parallelism。

Because。A copy kernelel is so。Compute unintensive。 There are no eligible board。

 even though we have like 4096 by 4096 matrix size， which is 16 million elements。

 there are no eligible war when the schedule wants them70% of the time。And one or more eligible。

 about 30% of the time。So' that's something you want to pay attention to when you're doing your kernel and as we go through optimizing transports。

 we'll see how that makes a difference。And then there are a few charts down here about the state of the scheduler most of the time。

 and again you can highlight these to read what they mean and get the details in that。

B see statistics is important because they will tell you。

What was happening during the life of the war， and I don't mean just the compute life。

 I mean even the weight life of the war okay？嗯。So。One of the key things I want to show you here is by expanding this。

Here， so again， in the copy kernel， the main operation that's happening is。

A CO is global memory read right and as you can see， majority yeah very select portion。

Just wondering how you're getting all of those statistics on your details。

So I just hit the arrow button here on the left。Is that what your question was？

Wick I think you have to run the full analysis then when you start the thing you have to on the details have。

Mster。Yes， if I， if I go to。New activity。T that's。 And if you go to metrics。

Now my windows are too small， but if you scroll down here。

 you'll see full and that's what you want to run。对。

Any other questions before I jump into W state statistics？Okay， so。

What I want to show you here is that because we are doing a copy kernel which where the main operation is globally memory read and write。

 the main thing that's happening in the warp is stalls right and that's kind of expected is that the stall takes so much time compared to everything else and there are different cohort boards and stuff here again you can highlight each one of them to take a look。

About what they mean but as expected most of the time during the life of the kernel all we are doing is waiting for global memory reads and rides and that's what this the summary tells us here as well on average each warp of this kernel spends 13。

7 circle in cycles being stall waiting for fixed latency execution dependency fixed latency execution dependency in this case is a global memory read or right so again very obviously telling us or shouting at us to be like hey go fix your latency issue is add more compute or optimize it further。

All right so。That's that there's a bunch more statistics here tell you all the launch statistics so we had grid size of 16。

000 blocks there is a question。Okay。On my machine looking at the warp state statistics。

 my stall long scoreboard is like eight times longer than stall weight and I was like wondering I'm also running the solution branch is there a reason like that might be？

So I have used the scoreboard too much， but of course， which GPU you run on changes quite a bit。

 I think I have a。30， 50 TR or something on my laptop。

 so I'm trying to see if this pop up is moving way too quickly for me to read。Sorry。

 let me when when I zoom out， let me take a look at that and see， but ultimately。

What you want to take away from this is that。Were't necessarily doing something bad in the copy kernel。

The use of the copy is as reference to say what the transpose kernels should look like， right？So。

So that's what I'm trying to set as a reference here。 So start about whether something is bad or not。

 So even if there's a lot of stall weight， it is just expected stall weight like there's nothing we can do to。

Optimized that copy colonel further。We could if we have shared memory。

 all we are doing is adding an intermediate step between a global memory readerdirect right without actually using the shared memory at all。

 so use the copy kernel as a reference， but I will come back to this scoreboard once I can read it a little bit。

Any other questions？I think no other questions。So looking at the other details here。

 so loan statistics are pretty good because it'll tell you how many blocks and wars and how many registers per thread you have。

And then it'll also tell you occupancy based on your GPU and what you're running and some。

Probably suggestions of what you can use。嗯。The other thing you'll see is in the GPU and ME workload。

 again for a copy kernel you're going to see that there's going to be a lot more weighting and a lot more global memory deeds than compute cycles。

 so that's what we have here。All right， so now we've done copypyCon using this as a reference， right？

I'm going to select our matrix transport 9。 Now， when we get matrix transport 9。By a name。

 we know it's the nightva of doing。A transse kernel。

 so now let's see how the inside computer tells us not or what is it complaining about？

So starting with the GP speed of life through foot。

 I mean it's what it's saying is the kernel exhibits low compute copy。

 but that's what it said even in the copy kernel so we know that there isn't enough work actually happening in each kernel totally fine no problem but let's dig in a little bit deeper。



![](img/bb4f2a016824f794f04b491deb09f3dd_3.png)

嗯。And so let me do this before I show you that further。



![](img/bb4f2a016824f794f04b491deb09f3dd_5.png)

When to装。This is from Biland Studio。To get some numbers。



![](img/bb4f2a016824f794f04b491deb09f3dd_7.png)

Okay。So。First I run some benchmark， these are all using API。

 so first we have pageable copy host to host my host CPU Ram does about 35 to 39 gigabytes per second。



![](img/bb4f2a016824f794f04b491deb09f3dd_9.png)

Ageable transfers so these are between host and device I'm getting about seven to eight and P memory transfers like you see like we've discussed in the class are much faster these can be even faster on some devices is just my laptop is this way。

And then device device copy is 162， which is five times faster than the CPU。

 so now you can see how know how much faster you can even expect global memory needs to be when they are done when。

right， CPUU transpose。P at and of course CPU transposes in our case is unocimized as well we are not using multi trading or anything。

 so using it as reference。Is 0。869。 Again， if you compare that to your CPU usage， that's。

 that's a lot less。 There is scope for optimization， no doubt。

 But we'll use this 9 CPU transpose as a base。Then for device for device copy。可能对。We are getting 62。

61 gigabytes per second。So now ideally you want this to be as fast as device per device mem copy right I don't have a great explanation for why this is slower normally it's as fast as the MEM copy function。

 so let's come back to that in a。And then we look at matrix transpose9。Now， look at this， he said。

Transpo kernels should be。We want it to be as fast as the device kernel。

 but our matrix transfer was 9 only gives us 24。36 gigytes per second that's approximately three times slower so now we want to get into y right that's what we want to use inside compute for。



![](img/bb4f2a016824f794f04b491deb09f3dd_11.png)

So let's look at。Let's look at In compute。嗯。We know that the core of the operation is memory。

 so let's go look at the memory。嗯。嗯。All right。So， here we have。A new suggestion， right。

 So I'm going to go back to， let's say， copycon。Where。The kernel， sorry。

 not speed of right through work。Memory workload analysis didn't have any suggestion for us because we were doing something straightforward。

 but if we jump to our。Mattrix transfer is naive。 now it has a suggestion， it says。

The memory access pattern for global stores to L1 might not be optimal， on average。

 only four of 32 bytes transmitteded per sector are utilized by each thread。

This goes back to our diagrams in the presentation， it's saying， hey。

 you you're not using the memory that you're actually reading， right？嗯。

Let's take a look at something else。even even in the Wstate statistics， it says on each warp。

 the kernel spends 26。6 cycles being installed on a memory barrier。

 a memory barrier again is a global memory feed or right in our case。嗯。

And then on the workflow distribution， again， here you can see some statistics on how much time was spent in each part。

So just based on this suggestion from the memory workload analysis。

 we know that there's a problem in global memory。What's a good way to optimize that？

It is to perhaps your shared memory， so let's jump into that。



![](img/bb4f2a016824f794f04b491deb09f3dd_13.png)

So I'm going to come back to our slides。And let's talk about shared memory and how it applies to trans post。

So this slide I've left in you for reference and memory。

 but I think all of you know how to use sharedd memory by now。

Its purpose also is interblock communication and caching data for return memory access。All right。

 how does it apply to matrix transfer So matrix transfers very simply is you flip the rows and columns of a matrix like a memory copy。

On the CPUU， this is how you would do it， you would say transpose I of J equals matrix J of I with a nested for loop。

 it's often squared and it's low。And the GPU can optimize it because there's obviously embarrassing parallelism built into this。

So on a GPU transports， on a9 GPU transports。What we are doing is we are launching one set per element。

 we compute the index， we compute the transpose index。

 and then copy the data from input to transpose matrix and under GPU circumstances of one panel will compute。

So essentially， all the kernel is doing is one memory copy from global memory to global memory。

So the question is， why isn't it fast， We've already seen the numbers on my laptop about how much slower it was。

 So why isn't it faster。So I have aqui for you guys on an interactive qui。

Ha the QR code up here and this links to like a what is it's like a word cloud I think。

 I want you to go put that about how much faster。The GPU。

Transfers is going to be compared to the CPU transfers and。

Comparing CPU knifeive transpose to our optimized version of of transpose。

 so put your answers in there， I'll quickly pull it up on my laptop。



![](img/bb4f2a016824f794f04b491deb09f3dd_15.png)

So that we can see all of your solutions coming in。



![](img/bb4f2a016824f794f04b491deb09f3dd_17.png)

嗯Let me let me leave the。The PowerPoint on the screen said that you guys can scan the QR code。

And just put a number in there， you don't have to type a biglock answer or anything。

And if it asks you to put your name in there and start just skip everything I think the settings will open。

 I tried it out in talking into more that you can just go and type an answer。

So I'll wait for a minute for of you guys to do that。I I going to local？

I think most of children them already skin。All right so。You're seeing 25，200 faster， much faster。

 600%， 2500%。Slower， I'm interested to see who said who by does it slower。Yes。All right。

 so good guesses， keep going with it we'll come back to this at the end of the class。All right。都。

So now we want to see。How we improve this right so just looking at transse kernel。As code。

 we kind of walked through this when I was showing you the code sample。

 but we have in in J were calculating the input and output index and then we are copying so here's the visual diagram of what that looks like。

I assume no questions on this， but I'm happy to pause if there are any。Okay。😊，All right。

 so the problems we discussed at per inside compute is that。It's saying hey。

 your memory access is not good， it didn't say that in the copy kernel。

 it says that in the transpose kernel。So let's， let's look at it。Here's a question for you guys。

In a N GPU transpose， which of these access patterns are being used？And there's more than one。

 but not all six。I fortunate want to answer that？I'm going to guess six。I'm going to give six， okay。

 six and when。哦。诶。But further the right on the right。Okay， six is a good one next。Any other guys？

There's not a trick question， honestly there's there's more than one so I'm just trying to I'm going to say game number one for the read。

Number one for the real good， that's you know something within a block that's all consecutive Yeah one one is an obvious one along with six。

What else。Any other guys？So Nick， I think you answered that。What happens with on the diagonal blocks。

 Which memory pattern happens on the diagonal blocks。So one happens。On all reads。

 completely all the read are very sequential， six happens on pretty much all of the right blocks。

2 happens on the diagonal blocks， where。The blocks that are reading the memory and writing the memory are writing to similar locations。

But。Within the block there's randomization， so thats that's why two also happens， so one。

 two and six are all patterns that happen in knife GPU transports。So。

And4 also happens when if the L2 is used。Okay。So here's kind of a visualization of what's actually happening on the read。

 we are reading very sequentially， we are reading continuous values。But on right， were jumping now。

 We are striding because there is a transpose。So now this is the random memory access patterns That is bad。

 We are writing on called memory。 So， so this becomes very， very slow。So。The problem is。

We have non coilless memory， and the obvious improvement we want to make is to have coilless memory。

A way to do that。Is by using sharedd memory。So what we want to do with sharedd memory？

Is to use it as a temporary storage。To coalesce the memory for the output， right。

 So what we're going to do is。We rid compute the input index， same as knife transpose。

And you are going to copy that data into shared memory。

The difference is that once we compute the output index。

We transpose it shared memory so that we have coalesed memory Act， right。So read into shared memory。

 transpose in shared memory and then write out so you might be wondering how does this work。

 how do different blocks communicate blocks don't communicate。So。First。

 visualization is kind of this， where we have。Different blocks reading memory or different ws reading memory。

 those go into shared memory。Once we write to sharedd memory。

 remember the cardinal rule always have sync threads。Once they're in shared memory。

 then we transpose within shared memory。And and shared memory is random access。

 So that shouldn't be a problem。 We're not actually transposing or what we are doing is using different indices。

 And from there， we'll write continuously to。The global memory。

 so now you can see that the bottom arrows are in in sequence， they're not jumping around。

So this is kind of how it looks at the global level。

 so we this slide was more at a block level here is here it is at a global level。

Matrix transpose should be broken down into like sub matrix transpose where what we are doing is we are creating sub matrices。

And you transpose their entire sub matrix and then even within the sub matrix you're transposing it。

 so that's the concept of using blocks or tiles like we also did in matrix multiply。Said this。

Block here。Will become this block in the output。So you take the entire block and you transpose the block and then within the block。

 you're transposing values。Any questions on this so far？So I asked earlier saying that the tiles。

 I thought have to be square， but you said they don't have to be like， yeah。

 what does this look like if the tiles are rectangles？

So here's the distinction and maybe this was lost in translation。The ties should be squared。

The block。Size， and well see this later in in our matrix transfer example。

The template values don't have to be squared and we'll see why later。

 but here in our case we are making sure that the tiles are square because they'll be easy to transportse。

Okay， that definitely higher five things。好的。😊，Okay。All right， so you have the chor that we look at。

So we're going to declare some sharedd memory， which is the size of the tiles。嗯。

And then we are going to compute the indices for both the inputs and the outputs。

 and then we are breaking them apart so that we can also use the indices in the shared memory。

So first thing we are going to do， like we discussed was copy the input into shared memory。

Then we are going to do syn sets to make sure all the data is copied。And then。Also。

 checking the bounds。 we are going to transpose within the shared memory。

 Look at how we are transposing。X or y， and then x on input。But X and then y on the transpose。

 And then all we are doing on the flip side of the block is we are flipping the block。Inds。

 like we showed in this diagram。So here we have J times size x plus I。

 here we have J times size y plus I。What that means is the rightss are now going to be coalesced。

And that's going to be a good thing。

![](img/bb4f2a016824f794f04b491deb09f3dd_19.png)

嗯。So let's go back to our inside compute。

![](img/bb4f2a016824f794f04b491deb09f3dd_21.png)

And actually， let me show you the output here first， so knife trans was this fast。

S memory transports， all right， we are improving that right， so we came from 24。36 to 33。67。

Let me close this and then run it again to see if it produces different numbers。Okay。25 and 31。 Yeah。

 so about in in the range of what I' call range of error。 So it's it's done some improvement。Right。😊。

But it's still not as fast as device to device copypy。 And we need to figure that out。

 So let's go back to our friend inside compute。

![](img/bb4f2a016824f794f04b491deb09f3dd_23.png)

And then amputs fall down。And find one of the matrix transports shared kernel。Let's look at again。

 this is all about memory， right， so I'm just going to jump into the memory analysis。

And I'm going to expand this。 So let's look at this chart first because now we are using sharedd memory。

 right？

![](img/bb4f2a016824f794f04b491deb09f3dd_25.png)

嗯。Before I do that， let me change my display settings to make it slightly smaller。

If you guys not read it， please do let me know。

![](img/bb4f2a016824f794f04b491deb09f3dd_27.png)

All right， is this still legible？I think。People in backroll can guys see it clearly。Okay。😔，Okay。

 all right， thank you guys。 So now what we are going to see is。

We still have similar device memory leads into L2 and L1， but now we have shared memory。

There is some memory going from L2 directly into shared memory。

 and then we can see this reads and writes。And similarly， global memory here。嗯。

Now let's look at the analysis。Hey， we have a new message here。

Shahard back load bank conflicts the maybe access pattern for shared loads might not be optimal and causes on average 32 way bank conflicts remember how we spoke about bank conflicts in the last class and how many we have two way bank conflicts and8 way bank conflicts we have 32 way bank conflicts。

That means all 32 draws or all 32 threads are trying to access the same bank。

 but different addresses at the same time。That's horrible right and this results in 16 million bank conflicts so every element was hitting a bank conflict and basically was sequential the whole kernel was becoming sequential。

嗯。😊，So this gives us an obvious answer to be like， okay， let's go fix our bank conflict。Okay。😊。

So now this is where the real performance lab starts where I actually show you how you want to fix it and teach new stuff。



![](img/bb4f2a016824f794f04b491deb09f3dd_29.png)

All right， so let's come back to the slides。So the problem is bank conflict， right？嗯。

I spoil that so we want a remove point bank so let's discuss bank complex one more time I kind of showed these slides last lab。

 but were discussing again because now you have to the concept of a transpose and you can relate here。

So within each block， you're going to be sharing the submatri right。

 and that sub matrixx is going to be distributed across the 32 banks。

And here's an example of how we total 64 elements， of course。

 in a 32 by 32 kernel or a 16 by 16 kernel， you're going to have something similar。Um。

So when we have this， let's say we have our block size is 32 by 32， we have 32 banks。

Each bank is going to store 32 values， right， so 32 by 32 elements。

Here's some indexing math for how that works out where we've taken different examples of indexing and seen it here。

So this example here results in a two way bad conflict。This example。

 which is what we are doing for our kernel。 Remember I said x comma Y when we would talk。

 let me come back here。See how you're doing thread IDX， thread IDx。 y。

This results in all the banks being why for all different addresses。

So this is a 32 way bank conflict that In computer is complaining to us about。

So now the question is how do we solve this？Does anybody have any suggestions on what you think might be possible solutions？

Can we do some kind of hash on the indices that we write to in shared memory？今 you do还。You could。

But there's a simpler solution。嗯好的好。But you're thinking along the right lines， basically。

 you want to change banks that each bank is scoring each value。There's other angles。

Just put a little offset at each row Okay， and what what should that offset be？One on the row one。

 if we index if the top rows row is zero， but one on row one， two on row two，3 on row three。

 et cetera。Yeah， good， good call。 So what， what， I'm sorry， I didn't catch who was speaking。

 but what you're seeing is。Let 0 start in bank 0。 But value 32 should move to bank 1。And then here。

 63 would or 64 would be here， right，64 should move to bank 2 so that now you're reading across a dialagonal。

Right。So how would we do that， there's a very simple method to do that anybody have ideas。

It's very similar to a last answer。Okay， so let's， let's talk about that here。 So this is。Again。

 our original kernel and giving the context here for what we're going to change。So。

TD ID point represents the role T ID extraX represents the column and the bank number。

So in the output third IDX dot x represents the back number and the column and that's why we have the 32 way bank conflict remember xs first right third IDX dot x is changing first and y remains the same and that's why we represent the bank or we get into the 30 way2 way band conflict。

So how do we solve this？嗯。So indeed， no bank conflict。In right 32 Bay Pan conflict。

 that's what we end up with。So the solution here is。To change the amount of shared memory per raw。

To be 33 elements。Okay。This is our table before right have we are allocating 32 by 32 in our shared memory。

And what that results is all the banks being y， so the same value。But if we change it。

 let me move this。To block size x plus one。We are not changing our tile size。

 We are not changing our block size。 What we are changing is the amount of shared memory we are allocating。

Only on the。The minor dimension， right， so what that means is。

Each of the x dimension will have one extra element。

And then the by dimension will have 32 elements each。What that does is。呢一年。

So these two columns here in our table show what was before。Whereas。In our output。

 all we have to do for the math and again we are not changing the indexing we are just changing how the math changes because of this extra memory space here。

Is that because we have size x plus one now？All of these do exactly what the suggestion was before。

 they create that offset， so the value is going into the ti。Let's look at it more visually。

So the suggestion was create that blank space so that it creates an offset。So we have。

The first straw remains the same。But because we allocated this additional one element。

 that one element is this gray value。This gray value is no longer used right we are going to do x and y just the same way we had previously。

 so this value actually won't get used。We never use。The value， something y comm 32。

that would essentially go into B1。So needss as offset。 and now in the out。All your reads become di。

 so this is how we avoid shared memory。Without bank conflicts。Let me pause and take any questions。

It's a pretty simple but very powerful solution and we can see how it affects performance in a bit。

Any questions。I think no question。Al right， so let's take a look at the only change in the code we are going to make is add this plus one here。

 That's all two characters。

![](img/bb4f2a016824f794f04b491deb09f3dd_31.png)

嗯。So let's go back。To the performance。And see shared memory transpose is 31。93。

Shehad memory without bank on 32。

![](img/bb4f2a016824f794f04b491deb09f3dd_33.png)

That doesn't make a lot of sense。 I'm going to try to run this again。

Sometimes GPS can do that to you let me make sure I have my quote correctly shared memory transpos。

Shared memory transfers with our bank cards。 So here you can see， I've assigned this plus one。Yeah。

 everything looks good。 I mean， front this was really used just in case。



![](img/bb4f2a016824f794f04b491deb09f3dd_35.png)

All right。Running without release was was in it or running with release or debu and for wasA initial so I'll change my advice from before run with release only so now we can see device to device copy is 146 compared to 162 on the API so this is much closer N transposes 46。

Sdment transport is 91， so already2 x faster even without fixing bad conflicts。Now。

 let's see with bank conflicts fixed。 We are at 1，33。So compare 133 to 146， we're almost there。

So we fixed we fixed global memory memory or global memory uncoalesed memory using shared memory and then we fixed shared memory bank conflicts and that has us almost all the way optimize to be as quick as。

嗯。As quick as the copy T。Now let's go back to shared memory。



![](img/bb4f2a016824f794f04b491deb09f3dd_37.png)

Yeah， and I'm going to go to without bank conflict and we look at exactly the memory work analysis and now no more suggestion。

 no more bank conflicts and you see the similar memory utilization actually let me go back to one of the shared memory ones and see throughput。

嗯。Nothing notable here， I think was just bank conflict so。Sharre memory without bank conflict。

 So again， now we see very clean new recommendations。 and we are almost up there。So。At this point。

 we've pretty much exhausted most ways of fixing global memory access。But according to insight。

We haven't really fixed。The the compute side of things， it seems is still saying， hey。

 you're not doing much work， right？So can we increase more work in the kernel？

So that's going to be the question for the next part of this。

 but let me pause and take any questions。

![](img/bb4f2a016824f794f04b491deb09f3dd_39.png)

Can you explain again how we get the one NT element per ro through adding that one rove I think I just I missed I didn't understand no no absolutely that's it is it can be confusing but I'm more than happy to explain again。

The thing you have to remember is that。Your block size and the amount of work you're doing per block is not changing your block size is 32 by 32 and this kind of transpose you're doing remains 32 by 32 okay。

Now， what I want you to imagine。Is。Let me see if I can do annotate here。

 I want you to imagine what if。Now you're adding X， right， So let's say this is X major。

And I'm adding a fake。Ghost row of elements here。 These elements contain nothing and they won't be transposed。

 but imagine what we had something like that， okay。That that's kind of the trick。

 so let me close annotation。Okay， let me clear that sorry one second occasion。Cl all drawings。

All right， so now。What that extra row is doing is in memory there is that extra row okay so if you want to access that extra element。

 you're going to do zero for column zero and then the index of that element。

 which is gray would be 32。Right。So in think of it also as linear indexing in a way。

 so the gray element is 32 or column0。For column one， it would be 64 and so on。Book。

Your matrix index。Still uses X and Y and would remain the same。So if I come back here。

To this diagram。 So let's say we have。I come back and draw this G drawer here。Okay。😊，Lya indexing。

What what is this index in zero， right？Linear indexing what is zero， it's four。So far so oh sorry。

 not for tea。Right zero index， what is the value of this？This is Ford now。

Which used to be the value for this element here。This element here now in linear indexing gets stored in five。

Now does it start making sense that are x and y， so x and y for this still remains。Zero and x。

And one on why。Right， we are not changing the coupleple here。

What changes is the linear indexing of the memory at which it's stored？

Does that make sense or should I go a little bit deeper and explain it？

So the like the the value three there in becomes five and because there's an empty space taking up like four。

Right， right， so for the index， the fourth memory index。Will always remain empty。

And so on will will the memory index for this and the memory index for this and the memory index for this。

 and that's what is creating go。What is fixed is the size of this square block of matrix。

As well as the number of banks we have， so banks remain 32。So by adding this ghost memory。

Let's look at it down of the way。 let's say our bank， we have four banks， only four banks， okay。

Let me choose a different color and choose red。This will go into bank zero。

This will go into bank one。 This will go into bank2。 This will go into bank3。

 This was what will what was happening in even in the previous。

Without Bquet or with B on for example， right？By adding this course row here。

Which bank is this element getting stored in？If we have four banks。Oh， bank 0， exactly。

 So this is going in Bank seated door。Now， which bank is three going in。

Then it would be in bank one exactly。 So this is in bank 1。 This is in bank 2。This is in bank 3。

 Now which value is this three going in？Back to zero， back to zero。And this is in bank one。

This is in bank 2， bank 3。バゼロ。So you see how this diagonal is getting created already。Okay， I see。

 So this is the band zero diagonal。Where that offset is being created， whereas。And again。

 let me clear all the drawings here。Previously， all of this element would have been Bank zero。

 all of these would be bank one and so on。Okay， I see that makes more sense。Other questions on this。

 thank you。So this is just one way of solving shared memory bank conflicts。

 this is with respect to transpose only there would be other ways and other kernels that you'll write which may need other ways of solving sharedd memory bank conflicts so that will need some creativity this is just one way of doing it me any any other questions in the class。

I guess no question。Okay。So of you've seen how we went from uncoaled memory to using shared memory to gain a little bit of speedup that wasn't enough。

 we looked at the profiler and it said hey go fix your shared memory bank conflicts， we did that。

 we got pretty good performance， we got roughly over 90% of what a copy kernel could do。

So we are very close to production ready， but our compute says， hey， you don't have much occupancy。

 you're not doing more。A lot of work， can you do more work， it may help。

So that's where the concept of loop controlling comes into play。Do remember in last class I said？

You may reduce the number of thread you launch if they do more work and that results in more performance。

 so here's an example of that。So what we want to do is。Not reduce the number of blocks。Okay。

 we want to keep number of blocks really high。But we want to assign more work in each trend。Okay。😊。

So that way we have a little bit more of that compute copy overlap remember from last time we said prefeing and compute copy overlap will help performance so that's what we want to do。

So here's kind of the visual representation of what we are going to do。

On the left is what we currently do， we have one element， one thread per element。

And that block transposes the entire sub matrix。And does it want per element？

What we are going to do is a block size or the number of elements a block at on will remain the same。

Okay， so that' are seen by the shades of reds and the shades of yellow。What we are doing is。

We are going to reduce the number of threads we launch in each block by a factor。

 we'll call it side here， and that's the number of threads we launch。

 but the total operations we do within the block will remain the same。So that means。

Just using four threads each in each block， we are going to transport 16 elements。

And that's as simple as writing a for loop in your kernel。 So let's take a look at some code。So。

First to walk through on the host， same number of blocks， number of blocks remain say。

 what we are changing is the number of threats per block okay？On the device。

 again we are allocating the same amount of shared memory with or without bank conflicts。

So that we can store the same number of elements。You're going to compute the indices same way。

You're going to copy the data and to share memory using the same， but doing it in an unrolled index。

 so we are going to add a K factor to the Y。Then we compute the output in piecess and then copy global memory from shared memory again。

 using that K follow。Any questions on that？Or I control show the code and we can see the specifics。

Okay take a look at the code Okay， so this will look slightly different So now we have the template kernels being in tile inside and in our example。

 we are going to do 32 tile and8 side so our the number of elements we act upon will remain tile tile。

Tile， times， tile。 So 32 by 32。Our sharedd memory allocation is similar but we have that plus one offset。

Our input compute， our input index is similar to before。

 but now see if we are using tile instead of B in。え？

And then we have this fall loop for doing the reads。

 so we are doing a hashtag unroll to tell the kernel， hey， you can unroll this loop。

And note how we have tile， which is a template inside， which is also a template。

Which means the compiler will know how to control the loop at compile time。 This is really important。

 If the compiler doesn't know how to control the loop， no matter how many pragma controls you put。

 it won't control that for loop。We checked the out of bounds and then once that's done。

 we use the factor K to read the entire。Assigned memory for that block into shared memory。Okay。

 once that's done， do a trends。Then we compute the output in that indices and do the phma for loop again to now do the right。

So this is where we've added more work per thread， instead of doing one read and one write per thread。

 we're not doing essentially four reads and four writes per thread。

So let's take a look at how the performance changes for that。 We'll come back to the command。



![](img/bb4f2a016824f794f04b491deb09f3dd_41.png)

Our unroll loop transfers look at this 164。5。Compared to even we are faster than even device or device copy。

And pretty much within the range of error or a device to device map copyied。So basically。

 we have 100% bandwidth now。By doing more work per thread。

But and keeping the number of blocks the same so it's really important to think about all of these things could our device to device copy get there if we did a loop on road yes absolutely because it has less overheaded it can it can get there too but on our objective was how do we optimize transpose to its maximum and using the profiler and the simple techniques we were able to get there。

Let me pause and take any questions。Could you visually go through how the the like the side。

 the unrolling works again？

![](img/bb4f2a016824f794f04b491deb09f3dd_43.png)

Yeah。So what we had quick to do and I'll use this right side diagram here。So remember that our。

In this example， we launch four threads。And the four threads have to act upon 16 elements， okay？

So in the first for loop k equals0， we are going to read the first row into shared memory。Okay。

 and that's this line here。This first first for loop。Then。In the next iteration of K。

 it's going to read the next row。In the next iteration of K it's going to read the third row and so on。

 it'll read all the four rows using that K4 row so again if we see here。

We see that the condition is 4 k equals 0 k less than tile k plus equals ps 32。Now， in this example。

 we have B row and doing four times。In this example， we have。32 threads in each row。

 And we have 8 rows in each block。So what we have to do is take eight rows and move them down eight and eight rows each。

 so let me let me try to annotate that。So， let's say。We have。This is 32。

Sorry for the bad writing and this is 32， right？What we're going to have is in the first iteration。

We have 8。Draws off tents。And they' they'll copy these。Elements into sharedd memory in k equals zero。

Then you're saying now Kate。Plus equals size， so K becomes8， so K k equals0 was here。Now k equals 8。

 so the copy is going to happen for rows 8 to 15。I'm going to draw a horizontal line here。

 And now in the second ithaleration。It's going to。Hopy these elements into shared memory。

And this is all within a block。Then in the next iteration。It's going to copy eight more rows。

Let me use this color， so I'll copy this。And then in the final one， your screen。

 it'll copy these eight rows of elements。DoesDoes that make sense？Yeah。

And then same thing happens in the right as well， it's just doing more more work per thread。

 so let's say thread zero comma0 which is here right is's going to operate on this element it's going to operate on this element。

 this element and this element and so on。Any other questions？嗯。No？All right。

 so let me clear all of these drawings。Don' not find the patients。Okay。

 so here are some numbers from an older laptop that I had about the benchmarks and you can again run this on your laptop and see how it works for you。

嗯。This is on a 1080t that had access to and again see that you know because the device to device memory copy for this GPU is 380 gigabytes bottom right here and loop controlling got us to 354 so not always are you going to surpass device to device memory copy but you'll get pretty significant speed up。

And then。Reviewing all of your predictions。嗯。So we had 200% faster， 2500%， 600% and so on。I mean。

 the freshing case there were more。Oh。😮，So in。In the case of just 108 ETI。

 we got 600 times faster than a CPU。嗯。In the case of my older laptop that I had we were 86 times faster so the exact comparison is going to vary by your hardware on this laptop as I was running it。

 we had 8 milliseconds compared to 1428。 so if I launched the calculator。



![](img/bb4f2a016824f794f04b491deb09f3dd_45.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_46.png)

Yes。Or two eight divided about eight so we are 17880 times faster on my laptop that I'm running this on so again the values will vary for you。

 but the fundamentals are there about how you take the take a kernel take the profiler and try to optimize it。



![](img/bb4f2a016824f794f04b491deb09f3dd_48.png)

Any final questions on transpose before we take a break and then do reductions？Oh no。All right。

 thank you everybody hope I hope that was really useful thanks for pair with me as I'm doing this remote。

 I wish I was there in class it's a lot better。Is that question for？O。

So I guess like I ran mine multiple times and i'm reliably seeing that my unrolled loop transpose is faster than the device device mem copy I was wondering if like there's a particular reason why that might be and it's like not by a small margin there's like a decent amount better so it's not it's not unsurprising that that happens I've seen that happen before on other GPs as well。

嗯。I don't have a big。Like a confident guess as to why it's a question I've never actually asked Nvidia。

 to be completely honest。Where it might be something around that we are able to do more a block what I don't think it should be faster than ever should be the theoretical bandwidth on the specs that N video publishs that would be scary if that happens and that's probably a result of hey you're doing something wrong but seeing it being faster than device to device me copy not surprised because I've seen it before as well。

系， thank you。嗯。Any other questions？I don't think。Right。

 thanks everybody for betting with the issues let's stay。

Six minute break approximately and be back at 847 according to my clock。

And then we'll do reductions in the same way。哎哎呀。呃，今在还有。然后。没。Yes， that's。I saw an。

you agree this upon that。😊，Yeah。

![](img/bb4f2a016824f794f04b491deb09f3dd_50.png)

I。嗯百分。WhatWhat's kind of。

![](img/bb4f2a016824f794f04b491deb09f3dd_52.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_53.png)

不。

![](img/bb4f2a016824f794f04b491deb09f3dd_55.png)

あろんな。

![](img/bb4f2a016824f794f04b491deb09f3dd_57.png)

这你。First like you might us like you know， light ray sample like inside the same kernel let scatter a ray or anything that's fine。

系lo。要那 you。嗯。It's like definitely like it's not good for。

work di buts not like unlike you know the regular， it's not like it can actually fire words so I don' think。

系啊そ年。know会。嗯。你为。可以。然后。😔，你看45没。为什么。응。发。Yeah。有。可以。你说对。喂。好。周。哦我讲会了。所你们问。嗯，对。嗯。呃反不可。嗯。Well not，Hway。嗯。对那。

で的不是。你不我我就。な。诶不不。要怎不有个。这个。Oh， we where is。俾啲电唔系贵啲。所以有。嗯。乜要冇楚咧。是我知道。😊，Where than。

s theres someone there or is there？😊，No， because he said being what he said。Oh。Crystal made over to。

系度。你可啊。Yeah， is there way to start up like BU costs that？Yeah， but it's really funny to balance。Good。

这个房子是个。行。啊。你们。不会跟持啊。嗯。嗯。嗯。So I wasn't part I never died。I think isn other。对 ok。😀Yeah。😊，嗯。你你方嘢有。this。

Oh。两个。不行。Can everyone clap once if you can hear me？All right， let's get started。

iceSo we discussed transpose in the previous example。

Now we' let's take a look at a very different example where we had we do have a lot of computers。

 so transpose was just one read one write。And then we optimize the production。

 we are actually going to be doing a lot of work and we want to optimize that。

So let's take a look at that and let's see how the profile is going to help with achieving that。



![](img/bb4f2a016824f794f04b491deb09f3dd_59.png)

Okay。So reductions， I know this is the third time we are covering this。

 so I'll breeze through the conceptual stuff and let's try to get into the court pretty quickly。

So reductions， it's a set of operations where you work on a set of elements and the result is a single element that can be something like sum。

 a maximum minimum average and so on。嗯。On a serial reduce， on a CPU。

 what you could do is have a serial follow and off and follow and keep adding two elements each time it's pretty decent。

But as we've seen before， there's a good way to paralyze it and we want to dig in more。

So in parallel reduce， what you want to do is you want to add as many elements as possible in parallel and then recursively do that more and more。

So that you get this parallel poll loop that you iterate on log n times。

 and then you'll get the final result。嗯。So。The main performance block in production is also GPU memory bandwidth。

So we do want to optimize that that's what we are going to use as a metric for optimizing performance。

We are going to work on large arrays so that we keep the occupancy busy。

And because it's not completely arithmetic intensive， it's still。One ad。

 but because and we'll do it in looping at， right， it's still memory back when pounded。

So here's kind of what that might look like if you do it recursively。

 which there is an example in the performance lab if you want to look at recursive introductions。

You can have multiple blocks and then where you do the addition of the different blocks that can be on the CPU or on the GPU。

 depending on how many blocks you have。In a Nive version or in not a I would say a N version。

 in our first pass of reduction optimization， we are going to do the second level here on the CPU。

 but the recursive reduction is's going to call the GPU as many times as needed until it's within the scope of a block and then it'll do it on the CPU。

UOkay。So serial reduce runtime complexity of off n， like we believeve see discussed。

 and then for parallel reduce the runtime complexityities of log n。So we are now going to see。

Our nine version works and then we'll take steps to optimize it。对。嗯。So let's walk through the code。

Let me pull up visual Studio first。if this is not legible， please please let me know。

For this example， we'll run 32 million elements and I'm going to use a block size of 256 threads。

Same helper functions that help us print results and errors to make sure that we are doing the correct thing。

嗯。And then。All right， what we are going to do is instead of calling a naive or shared memory and shared memory with bad conflict。

 well do stages of optimization。State zero is going to be the most unoptimized and then we'll go deeper。

So in stage zero， we have some shared memory。We are going to read the index into shared memory。

Call the Seds， do the follow loop as we discussed both in the previous class as well as the audit introduction discussion。

We'll do the follow to add all the threads and then finally we'll drag the result only for the first thread in the block so that because the reduction of each block is going to be one value。

 we'll drag that。I'm going to scroll down a little bit。To show you the CPU side of it。So。

These comments help you know identifying which region is where， then with theX start rate。

 I will shown it in the profiler， but I'll tell you where that will show up。

We'll have a map copy to clean up all the memories set the bys。

 and then we'll do the kernel and then finally we we'll do the。Performance benchmark in this section。

 So the first time it's checking for correctness。TheThen the fall loop will actually do the performance checking。

And then it'll free up the memory。So let's look at the code itself and I'll do that in the slides。

We'll divide the kernel into four parts。First， we'll declare shared memory and compute the index。

That's never going to change， there's nothing to optimize in that that's going to remain the same。

Part two will be how we load input into sharedd memory。

Part three how is how we do reduction in shared memory。

And part four is popular as start of each block into the global memory。

 that's the single line of output again， one and four never change will only change parts2 and three。

So let me come back and show you that in digital Studio。So stage one。This is part zero。Okay。😊。

This is part one。Where we are copying input into shared memory。This is sorry。I use the wrong index。

 part one。Compute index and allocate shared memory。Part two。

 which is copy input global memory into shared memory。Part three is reduction in shared memory。

And part four。Is copy the value into the output。 Again， there's nothing to be optimized here。

 So we are not going to do anything to4。 So all of our optimization will happen in parts 2 and 3。

All right， so let's go to our slides。So in stage zero。

 we're using what we call interleaved addressing and we've seen this even in our slides before where we add two neighboring elements。

 go to the next stage， add two neighboring valid elements。

 go to the next stage and so on right so everybody familiar with this， any questions at all。

I don't think no， okay， so looking at this in code and I just brought you through this。

 but let's take a look again。Part one， shared memory and Cal index， not going to change at all。

Part two is read shed memory and call the sync threads。

Part 3 is reduction in global memory and part 4 is right output。

So this is interleaved dressing and let's look at the performance of this。



![](img/bb4f2a016824f794f04b491deb09f3dd_61.png)

Okay。So I've just run it here a little bit ago during the break。

Our CPU reduce gives seven gigabytes of speed。Reduction state0 is already 28。Completely unoptimized。

 right？Is already 28 GB per second。 Remember that our at least on my laptop。

 the device for device bandwidth was 164。 That's what we want to aim for。

 So this is clearly at least eight times slower， approximately。

So there's a lot of optimization to be made here。So looking at the code。



![](img/bb4f2a016824f794f04b491deb09f3dd_63.png)

If any of you remember from the last class， what are some optimizations we can make？

We said that the interleaved indexing is not great so we have the modo being bad and the fact that we're doing it interleaved means that we have a lot of white warp divergence and can't retire warps so if we like pack everything to the left then that'll make things better。

You said all of the all of the problems。 So here's a comp for your reference from a previous benchmark。

And so interleaved address has all of these problems， it's interleaved address， which means。

Wbs don retire early， it also means divergent warps。

 which is not great and it has a lot of instructions which is not helping the performance example modlo。

So what are the solutions？Will move the module operator。

And we would remove the non diivergent branches so that they retired early and there's better occupancy。

So let's talk about what divergence and revisit it a little bit。

So side blockslocks are broken down into 32 threadwalks， as now that's been drilled into all of us。

And wars are executed physically within each SM， so wars don't jump around SMs。

 all the wars for a block reside on the same SM and that's when they can share the same shared memory。

If you have a divergence like this or what， let's say in our war， there are eight threads。

 what's going to happen is all the threads are going to hit the F statement。

But only half the threads will execute the first statement。

And then the second half will execute the second statement。

 so we are essentially serializing this in a way。If you remember the transpose example。

 the back conflict flick does something similar to。

Whereas if you have two warps and the condition is something like this where T IDX is less than warp size。

Then those wars will execute。In parallel and only follow one part of execution。

 So that way you don't have what divergence here。So the goal is to make the third per block multiples of Chedu。

 and I mentioned that in the previous class as well。An incomplete war will have wasted cores。

The goal for us in programming co kernels is to make sure that we can always rely on the fact that our warps will execute in lot steps so they won't have divergence。

It's not impossible to。 it might be impossible to remove all divergence。

 but at least we can try to minimize it。All right， so stage one。

 so we stage zero completely optimized stage one， let's remove the mod。Right we said modular was bad。

 It takes a lot of time。 We wanted to remove the modular。

 And so of the sport we saw in the previous class as well。So this is a quote from part one。

From stage  zero， so stage zero part one， we have the scored where we go sequence1 C less than block in。

 and then we are doing third IDX modo two times C。Right。Here's how we want to change it。You want to。

We're not changing though。We're not changing it left right。 We' are not doing that yet。

 We saw that in the previous class。 we will do that。 But first， we just want to remove the material。

So for that， what we are doing is。The follow loop remains the same。

 notice how I have the blue box here that shows the previous chor。

The follow conditions remain the same。What we are doing is we are changing the if condition。Okay。😊。

The reason I'm showing you this at this micro benchmarkchmark level is to show you how bad modular can be。

 Okay， so we did the if， and then we are doing the less than for that。

So let's look at the performance for this。

![](img/bb4f2a016824f794f04b491deb09f3dd_65.png)

So stage one， we already go from 28 to 38。Just by removing a mod operation。就。

I hope I' drilling from the point that wherever possible， remove the modular operation。



![](img/bb4f2a016824f794f04b491deb09f3dd_67.png)

Any questions about this？Iing no questions。Okay。So I did that here's a benchmark on a couple other GPs on 1650 we went from 6。

5 to 9。2 and on 1080 TiI we went from 8。3 to 14。3 speed so that's the times of speedup compared to the CPU。

 the actual benchmark 2728 to about 39。5 and 40 to 70 so on different GPs you may find different performance gains as well。

Okay。

![](img/bb4f2a016824f794f04b491deb09f3dd_69.png)

Let's also run。Our computer profiler。

![](img/bb4f2a016824f794f04b491deb09f3dd_71.png)

So I'm going to start a new activity。Let's try and release here directly to see if it gives us enough information。

re。Then on the common I'm going to change transpoal reduction and I'm keeping everything else the same。

 So let's launch that。

![](img/bb4f2a016824f794f04b491deb09f3dd_73.png)

And I'll hide this so that it's not spoiling it。

![](img/bb4f2a016824f794f04b491deb09f3dd_75.png)

This may take a little bit to run， so let me take any questions on the module optimization we've done。

No questions。s your day。Oh my day was good。 I mentioned that I'm here for a conference。

 lots of good takeaways。 So yeah， me if if you ever reached out to me for career advice。

 I'm sure I'll be able to share those things that not not very GPU specific， so I don't want to。

Take everybody's time for that。What conference are you at？

So this is called the industrytry conference， it's hosted by a group called the Product Collective。

They need a couple more minutes to wrap this up。Any other questions in the meantime could be about performance lab or anything else we've fled？

Okay， all right， let's just wait for this。 We have a few more optimizations to benchmark and then well have the profile already。

RightI think we have two more stages so should cope pretty quickly。All right。All right there we go。

 so let's take a random state zero and I'm going into the details and let's look at some of the early results again compared to transs this is going to have different things so now。

In the GPU speed of light， look at this， computer and memory are well balanced。To reduce runtime。

 both computation and memory traffic must be reduced saying hey。

 optimize both things and it's asking us to take a look at both of these。

Comp work analysis let's expand that in here it's giving you different types of compute that you're doing ALU is an eologic unit FME is point floating multiply and ad right so that those compute units are what are doing the reductions and so on。

嗯。It also tells you how much utilization there is memory workload analysis。

 so let's take a look at this。Memory access pattern or global stores to L1 texture。

 which is the cache might not be optimal So it's saying hey。

 your memory needs are not optimal and that's because we've been doing。Interleaved address， right。

 so so we want to fix that。 So that's one of the things we acted upon， of course。

We spoke about war divergence so let's look at what state statistics and it's already telling us threat divergence expected speed up 17。

76% quite fitting for Philadelphia， right？嗯。Instructions are executed on war which are groups of 32。

 blah， blah， blah， basically saying， hey， you have lots of what divergence exit。嗯。

Let's look at instruction。So we want to look at so this doesn't have the modular removed。

 so I'm looking for modular operation to see if it says anything here。

Let's in teacher multiply an ad。In teacher compare and set precate。

 I think that might be the modular operation。 I forget which one it is。Yeah。

 I think that might be the one I should be， so even though it's one modo。

 it's taking up that much time in the kernel。So that's another clue that you want to be looking for。

Okay， so now if we look at reduction stage 1。We can again， go back to。The instruction statistics。

It might not be the Comp that may not be modular。I should， I should look this up。

 and maybe I can tell you in the next class， Which one of is。

 Sometimes they they change these registered things， and I get confused。嗯，不ok。

Let's see if there's anything。 And one thing I didn't show in the trans kernel was the source。

 remember in project 2， I made an update on a discussion that I enabled the line for fixed the linening for。

 So now if you click any kernel， any line in the kernel actually take you to the exact。

Human readable line of code in the source so I can and then for each line。

 so let's say we do this index computation， it shows what the assembly lines are as well。

And how much stalls there are and stuff like that for， for that instruction， too。 So something like。

A global memory read， which happens here。You can see that there is a huge amount of stall happening on the SDS。

Assembly code so again， different ways of looking at what your benchmarks are showing。



![](img/bb4f2a016824f794f04b491deb09f3dd_77.png)

All right， so let's get back to our slides。So we remote modular。

 so that solves our instruction problem， but let's。



![](img/bb4f2a016824f794f04b491deb09f3dd_79.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_80.png)

Look at the memory， because I have a line that says。对 you may have。And conflicts。

 so let's take a look at where we should look for that。



![](img/bb4f2a016824f794f04b491deb09f3dd_82.png)

Compute workload now on memory analysis。 So look at this。It's telling us in state zero that we had。

Bad memory access。 But now we have bad memory access and bad conflicts and both on read and write。

 So we have load bank conflicts and right bad conflicts。 So we have a 3。

9 ways or approximately four way and a 2。8 way on on right。 So we have in in transport， we only had。

Band conflicts in one direction。Whereas introduction， we have bank conflicts in both directions。

Which need to be fixed right so that's what this profile is telling us。

So that's a new problem we provided。Okay， so so this is how addressing works in stages zero and1 right it's all interleaved but as we saw in the last class we want this addressing。

 we want sequential addressing that's also non diveivergent okay。So here's the question for you。

We still only need to change part two because all we are doing is changing the fall loop structure。嗯。

Of the reduction， right， not of the load of the reduction we are changing。 So now the question is。

If we need to change the for loop。What is the start， what is the step and what is the end。

 so who wants to take a guess for that？So let's start with what is the starting condition and we saw this in the last class。

What is the starting condition of the offset？The green matter should help。And over two。Yeah。

 so it's blocked in over two right that's the initial offset thread zero adds thread the index zero plus index blocked in by two。

What's the step？How is how is the offset changing at each state iteration we divide the offset by two every time。

 divide the offset by two， but can we do it faster？哦 digitalital。

We can also do a bit shift by one day。 Yep， good， good answer there。 Do a bit shift。

 We know that our block sizes are going to be multiples of 32， ideally powers of two。

 So that way the big bit shift as well works。 What is the end condition。When do we stop。

At C equals zero。At t equals0。Either C greater than0 or C greater than equal one。

 either of these work， but optimized version is C greater than0。Okay。

 so that's a follow and that's all we have to change so again compared to the block the blue block which shows the quote from stage one part three。

嗯。What we are going to do here is a new photo and in this case we don't even have to do this index compute and index compare All we are doing is thread ID X text is less than the offset。

And you're going to change。Or we are going to copy。Sorry。

 or and we are going to add among within the shared memory。Right， so that's the change。 So let's see。

How that there is a question。 Yeah， go ahead。 Yeah Does does dividing by two not get optimized into a bit shift by the compiler because like I。

 I know like on AMD architecture， it does like， I don't know。

 It'd be interesting to look at an inside compute。I'd love for you to try it out and let me know。

 I don't have a direct answer for。If the compiler can guarantee powers of to and do it， or if it。

If the compiler is scared that the value may be different and then it won't optimize。

 it'll be interesting to see how that works。Any other questions？



![](img/bb4f2a016824f794f04b491deb09f3dd_84.png)

Okay， so let's look at how the performance was improved so recap stage zero was 28。

4 gigabytes per second stage one was 38。04 gigabtes per second stage to 40。

63 gigytes per second so slightly faster not too much but still still faster。



![](img/bb4f2a016824f794f04b491deb09f3dd_86.png)

嗯。And then let's also peek into our profiler。And go to stage two and let's see what it says that it's still saying our global memory access pattern has issues。

 but now it's saying our bank conflicts may may have gone away so here we can see that shared memory still use but no more bank conflicts because of that。



![](img/bb4f2a016824f794f04b491deb09f3dd_88.png)

Okay。So coming back to slides。

![](img/bb4f2a016824f794f04b491deb09f3dd_90.png)

So here's another example of a couple more GPUs。So。We said。I'll interlea Their dressing is now fixed。

 right？However， do we still have divergent quas？Anybody want to answer if we have divergent warts？

And I put the cord in there so that it's a reminder her。Thinking about divergence。嗯。I mean。

 if we don't start with the power of two at the beginning or if we're like near the end， then yeah。

 but we probably won't have that many。Right， so most vers won't diverge， but the last war will。

 like Nick was saying then， so there is large warb divergence。

But how we want to look at thread usage as well。 Remember。

 one of you in the last class pointed out that。嗯。The。For if we launch 1024 threads for 1024 elements。

 automatically half the threads are wasted right， so we want to take a look at that。So in stage two。

 what is happening is first iteration of the threads of per block are unused。

 they're helping lot the memory。But they're actually not doing any computation， right？😡。

The second iteration three quarters， third iteration 78 so and so on。

 so we are wasting a lot of warps by not doing much work just because they' are loading memory so we want to reduce warp wasteage so what's the solution anybody want to suggest one？

So the problem is we are doing one3 per element。On Lord。

But half the threads because they've done the load are no longer doing any addition and that's being wasted so any any suggestions for how we optimize maybe we could add more than two items per thread。

Yeah， exactly。What we want to do is。Something like this。

Where we launched the block with only half the threads。But at least thread below two elements。Right。

And the question is how do we load that data into shared memory。

 this goes back to a loop and roll from the transpose kernel so let's take a look。

So this is called add on load。Where each thread。You Lordd its value into she memory。

For the next half。You just add it into shared memory。

 you're not you're not storing it even in shared memory。

 you just add it directly to the original shared memory that you did you don't have to preserve that original value because reduction again is。

Essentially， compressing that result， right， so you don't have to keep that temporary memory around。

It also doesn't increase our global memory usage compared to before because it' we're still reading the same amount of memory。

So now we modify part two of a kernel and see how that goes。Visually。

 here's kind of what it looks like。First， adaptations in the first part。In the first read。

 we are doing these parallel ones。And then the second read。

 you'll add these offsets directly into the value。And that way。

 youre only storing the shared memory for these many values， so essentially。嗯。O。So。

Let's look at the code。In the old part， part two。We were doing if within bound。

 she memory equals input from global memory。 And then we do the sync threads。 Now。

 what we are going to do is。If in written bounds。Read shared memory from input。

 and then if the offset is also within bound， add it。

So see how there's no temporary variable or anything， you not even extra shared memory space。

 you're directly adding it into the first part of shared memory。Right。😊，So。The question now is。

You don't actually have to。Stop at 2。If you can add two elements on load。

You can also add multiple elements on。So that's where we'll create what we'll call the states three tile factor and we'll put that inside a fall loop so we'll initialize the shared memory to zero。

 start with identity so in addition it will be zero in multiplication it will be one and so on。

Then we'll do this follow where we can do n copies onload。So again。

 similar to transposeers unloing or unrolling the loop。We're going to do that similarly here。Okay。

So let's take a look at the performance for this。

![](img/bb4f2a016824f794f04b491deb09f3dd_92.png)

This states three。 and look at this， a big jump。We went from 40 gigabytes per second to 74 gigabytes per second。

 so we're making moves in the right stage， I want to open the kernel and look at stage three and my stage three tile is only two right？



![](img/bb4f2a016824f794f04b491deb09f3dd_94.png)

What happens if we do it with four， so I'm going to save that。And let's try to run it。



![](img/bb4f2a016824f794f04b491deb09f3dd_96.png)

So just between two and four as well， we are going to see a difference so I don't know why my Vi studio is doing that。

 so I'll come back to command prompt and run this。So we have stage three， look at this， it's 124 now。

对。Just by doing multiple ads。Multiple ads per load。

 right or on load its it's changing the performance drastically。



![](img/bb4f2a016824f794f04b491deb09f3dd_98.png)

I'm going to leave it at four and。

![](img/bb4f2a016824f794f04b491deb09f3dd_100.png)

And then。So it has the exact code for multiple ones。And then this is benchmark so on this。

 I' again showing two elements per thread， but depending on how you want to configure it for your GPU or other GPUs。

 you may choose a different factor of how many ads you want to do on load。

So that's kind of the question and this is an exercise for you to do try one，2，4， eight。

 one is basically the previous stage two is what we are doing here or816。

 you could try that out absolutely。So that。With multiple ads on load。

 you improve you're reducing the number of threads you launch。

 you're also doing more work per thread， you're also doing compute compute and memory latency hiding and that's why you get a big performance boost。

So looking at the problems， we solve a bunch of them out。However。

 the last warp is still divergent and that's probably why we are still not hitting if I compare this 124 to 164 that I had for device memory copy。

 we are still not hitting the optimize level。

![](img/bb4f2a016824f794f04b491deb09f3dd_102.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_103.png)

So。The last warp。那个是。If we go back to one of these diagrams。Sorry， lots of slides。If we。

 if we look at this diagram on the right and let's assume in the last word like heres 16 threads。

 right， if you add one more level above this， it' would be 32 threads and there's not much we can do。

 the work seems very divergent， There aren't really any options other than it not be divergent。

 but there's one way we can optimize it。 So let's take a look at that。We' quickly jump forward。

All right。So we want to basically unroll that last form。

And let's take a look at how we can do something like that。 and this is pretty。

It starts getting into a little bit of how we can use compute to help optimize our kernels。

So in the previous stage， we had this for loopia。Which was due in multiple。Ass onload。

 but now we're going to split it。Our kernel is going to stop at C greater than 32， right？

This essentially guarantees that this for won't be divergent。Different wars may do different things。

 but the last warp can't be divergent at least in this fall loop， but it will exit early。

And then we have to actually do the last warp reduction， otherwise our answer will be wrong。So。

When this fall loop exits， that's when we have to take the last war and what happens at part 3B is that the last warp is going to do compute。

 but all the other wars will exit。Because of that condition。Any questions on this？

Because this understanding is critical to how we are going to explain how to unroll that last word。

Okay。All right， so when C is less than or equal to 32， which is only in the last warp of each block。

嗯。We are going to create a new function， a device function， not a kernel。

 a device function that we call war produce okay， so reduce within a war and we'll call it here。Now。

 what does this look like is going to look something like this。

We're going to say we're going to tell the kernel by using this volatile declaration。

For compile not to reorder or change the behavior of this function。Okay。😊。

And this is what the code will be in what produce。At each shared memory。

 we don't have any if conditions， we don't have any all loops or anything。

 You're just adding a thread Id。within the shared memory with its offset。And this is correct code。

Why does it work？So you hear are the questions I want to ask， why do you think this code works？

Why don't we need any if statements or bound checking at anything for this state？No guesses。

 I'm happy to share why。So。What's happening here is that because all of this is happening in place in the shared memory。

Once。😮，The end part。Or the iteration in the reduction is done。

 we kind of don't care about the memory that comes after it。Okay。Let me jump a couple slides ahead。

So what's happening here is that let me pull out the annotate， so let's see our what size is 16。

 right？Once this calculation is done， this calculation。What happens to these elements？😮。

We don't care。Because these elements are no longer used。So in our next it。

 what's actually going to happen is。This is the relevant part， the blue is the relevant part。But。

Because we have no if conditions to say， hey， only the first four thread should actually do this。

There will actually be all of the trends doing this。Okay， and。Let me draw a few blocks。Or few tense。

This Ted is going to add this。This thread is going to add this。Add this， add this and so on。

 and this will right here。This one right here。Right here。I'm right here。But notice this。

We don't use these elements anymore。😡，These elements in green， we don't care about them。

Because their usefulness is done。 so even though these values are going to change。

It's totally fine for the sake of performance and removing warp divergence。

We can overwride to shared memory as long as the relevant results。

 which kind of follow this trend line， right， they follow this。

As long as that part of the memory is sensuous。So that's why this works。

Let me pause there and take any questions。What exactly does balltail do and why is it used here again？

So volatile， at least in this scenario， is telling the Nvidia Ka compiler。

That I know what I'm doing do not reorder my statements。

And do not get rid of any statement so I've told in previous times Edward the NVCC compiler will remove certain lines of code or can do instruction reordering to better optimize it in this case the order matters a lot。

So what we're saying is shared memory is volatile。And I know what I'm doing do not optimize this and follow everything that I've written exactly the way it is。

So any statement that directly edits that whatever variable you declare Voltail will not be touched by the compileer at all。

Exactly， yeah， okay。Other questions。Does everybody understand how we came up with this？Okay。

 all right， so let's take a look at。You go ahead。 Yeah， sorry， can you explain how。

 how the concept you just explained relate to the code。月兽。Let's see。

For the sake of theoretical argument that the compiler decided to execute。This statement2。

 before one， for whatever reason， I'm just saying a theoretical example， right。

What's going to happen is it's going to also add。The elements before they stop becoming useful。

 and then you'll get memory corruption。Let me clear this。You all my drawings。 And then let's take。

 let's do a statement 0，1，2，3。 Let's do3 before 2。Okay。😊，So。

What it's essentially saying is this compute， this is statement three， should happens before two。

Okay。😊，What will actually happen is。For these values here。喂。These values will get a them。

Which shouldn't happen。Right。Because if these words would get added to these before step two happens。

 then that's memory corruption。And you won't get the right result。O thank you thank you。

Any other questions？嗯。

![](img/bb4f2a016824f794f04b491deb09f3dd_105.png)

All right， let's take a look at performance， so we。



![](img/bb4f2a016824f794f04b491deb09f3dd_107.png)

The tile 4， actually， let me compile this again to make sure that I have tile 4 on stage 4 as well。



![](img/bb4f2a016824f794f04b491deb09f3dd_109.png)

So we have this war produced function here。嗯死。Actually。

 let me do two and then we'll come back and do four again。



![](img/bb4f2a016824f794f04b491deb09f3dd_111.png)

え了。😔，All right。All right， so stage two we had 122 with four， remember four at two we had at at 70。at。

Do at。Two ads per thread we are already at 117 on stage four now let's go back and recompile this with four。



![](img/bb4f2a016824f794f04b491deb09f3dd_113.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_114.png)

嗯。All right， let's read on it。And look at this， we are now at 140。Compared to 121。 so again。

 slow but steady performance schemes， that's that's the big messageen here。

We are already now very close to within like 0 80， 85% of peak memory bandwidths， right。

 just using this。

![](img/bb4f2a016824f794f04b491deb09f3dd_116.png)

For the sake of。Discussion， let's do8。 Let's see， Let's see how that changes performance。2。



![](img/bb4f2a016824f794f04b491deb09f3dd_118.png)

So it didn't add such a big benefit。 It just meant to 145。 so there's going to be some。



![](img/bb4f2a016824f794f04b491deb09f3dd_120.png)

Point of diminishing returns that you want to look for。 So I'm going to report this back to for。

Let's go back to our slides。So here's more benchmarks。

Extremely highly races to 32 threat per element， so basically an entire warp at the time。

 that can be a bit extreme but。What's trying like you can go that extreme。

So we have unroll the last warp as well， but again， we are at 80， 85% performance。

But not completely right， so what are things we can do。嗯。Are there。

 are there any things in the stage for improvement that inspire you to do more， basically how we。

When crazy with the shared memory ads， are there other things that inspire you to do that？

As well as take any ideas from transpose on what we could， what we could potentially expand。

What ideas do you think you have？No。All right， there is an idea。So嗯。Let's just go crazy with it。

What we did was we removed the for loop for the last warp， right。

Who's to say we can't remove it for the entire block。And this is why we'll go a little bit crazy。

 but good crazy。So。This 512 of course is for the old GPUs， our blocks are limited 1024 heads。

 so basically we want to get rid of all the four loops。And just do。All of it。In。In a nondivergent。

 unrolled way。So let's take a look at that。Okay。First。

 we want to make the block sizes known to the compiler。

 so that that's why we had this template support kind of like what we were doing in transpose as well so and we'll call that stage five okay so we are going to make the block size constant at compiled time。

Then we're going to do something like this。喂。For each of those powers of two。

You are going to do an audition and she memory。The lower part of the sharedd memory is going to remain same。

 so number of ads per load can remain the same。But的。This is part 3 a that we are changing。

 so part 3 B what reduce remains the same this is part3 a that we are changing we are removing that for。

So this' is what it looks like before I explain this。I have that question there。

 have I committed a cardinal sin here and what is that cardinal sin。Anybody want to take a guess？

I'm guessing you be in the Cardinal center as Warp divergence and you haven't cons all the if statements are multiple to 32。

So there is no war divergence here。So which part is the cardinalton？

I guess you could argue that the cardinals spin is that you have a ton of if statements。

 but like I think the compiler is pretty smart so I don't think those should be evaluated at run time。

That's correct so。Could the compiler will optimize them away？But what's the Carnson？

And some of the formatting might be throwing you off。Look at the sync threads。

 syncc threads in different branches。I put a synchronous inside an F block。

 something I've told you explicitly never to do， and this is kind of the exception for that。

The reason syntron in this case is OK inside a F block is because the block size is a template parameter and the compiler will optimize it away。

So we won't get into a kernel being blocked forever， basically hanging because of what divergence。

 So this is like the one place。Where or the one way you can use threads without it causing issues。

So the way this works is essentially war produced， but blown up to the entire block。Before this。

 we would have read the memory into sharedd memory， right so you have all 10。

24 elements of shared memory populated。And now， instead of。Having the addition in the for loop。

You're having the addition inside these if statements that are unrolled。

Because we know block size can only go up to 1024 if block size could have been infinite。

 this wouldn't have been possible because you wouldn' need a flexible follow loop but because we know there's a hard limit of 1024 size per block。

We can optimize this in this way by removing the fall loop completely and removing that overhead。

So it's like what produce， but on a block radio scale。

So I think I've already mentioned that so let's take a look at performance again。

 so stage5 with two elements added in the read part is 135 compared to 145 for。



![](img/bb4f2a016824f794f04b491deb09f3dd_122.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_123.png)

![](img/bb4f2a016824f794f04b491deb09f3dd_124.png)

8 Ts in stage 4。 So now with stage 4 being4， let's make stage 5，4 as well。Let's build it。

And here you can see the full code here where we go from 1024， 512 to 56， 128， and then within 32。

 we call the war reduce function。

![](img/bb4f2a016824f794f04b491deb09f3dd_126.png)

And then finally， this divergence we can't do anything about。 So we are going to just leave it there。



![](img/bb4f2a016824f794f04b491deb09f3dd_128.png)

All right， let's lump this call。All right， so this time we got 135。6 and 135。4。

 so not not a huge gain。

![](img/bb4f2a016824f794f04b491deb09f3dd_130.png)

嗯。But let's change this。😔。

![](img/bb4f2a016824f794f04b491deb09f3dd_132.png)

嗯。To say， let's say we， let's go extreme。 Let's go 32。Okay。😊，嗯。That's grim。Yeah。

 at this point I think at least for my GPU I've saturated it as much as possible for a reduction so I'm not seeing huge gains。

 but here's a benchmark on two other GPUs right so on GTX 1650 so it remained the same again 1650 is a laptop GPU I have a laptop GPU remained the same on a 1080TI we got a slight gain from 264 to 269。



![](img/bb4f2a016824f794f04b491deb09f3dd_134.png)

So yeah， now basically what that means is we are hitting a point of diminishing returns trying to optimize it much more is in where to yield a whole lot of performance so this is kind of where you you make the decision okay is this good enough do I need to go go drive it more and stuff like that。

Here's a chart of the different millions of elements on the right and the time in milliseconds on top。

 so lower is better。So that's why we see state five taking that time。Okay。Allright。There is。

One more way to improve performance that we kind of said at the start。What was that？

For doing like the final part on the CPU。Exactly， we are doing the final part on the CPU。

 So there is no reccursive reduction。 We are only doing one reduction and then adding all of the blocks at once。

 So in our in our performance testing， we are doing 32 million elements and blocks of  trend24 elements。

 right， So we are literally talking about 32000 blocks。

AndDoing 320 reduction for 32000 elements on the CPU。

 when we know that those 32000 elements are already on the GP。

 and we can do another reduction on that on the GPU before we copy it back to the CPU。

 So that is recursive reduction。So the way it worked。

All we have to do is essentially call that kernel one more time before we pull the cord back onto the CPU。

嗯。So let's take a look at it in visualual Studio。 So have this recursive production pile and the change is mostly on the CPU side。

 So let me。What I've done is essentially， let me go to stage five directly。For each of these kernels。

 both the naive reductions as well as the optimized reduction have' created these wrappers。

And then within the wrapper， what happens if it checks up for how many elements are left？

And depending on the number of elements left， it's either going to call the GPU again or going to call do the operation on the CPU by doing a Qa copy。

So let's run this， I'm going to set this as start of project。Let's start with I equals2。

 I'm just confirming that yes， I equals two everywhere。Let's build。



![](img/bb4f2a016824f794f04b491deb09f3dd_136.png)

rent that build and now let's run it。Allright， so with tiny equals2 we're actually seeing a pretty big gain between stage four and stage five the one thing I also want to do is show you the performance difference between without recursive reduction and with recursive reduction so we saw 28 38412142145。

State zero stay stage one same stage two was 40 that remains the same。But for stage4 and stage5。

 we are seeing gains。 Now let's go back and let's change。



![](img/bb4f2a016824f794f04b491deb09f3dd_138.png)

Acursive reduction tiing to4。For all of these。

![](img/bb4f2a016824f794f04b491deb09f3dd_140.png)

All right， so a pretty big gain in stage four， but not a huge gain in stage five。

Because we are now doing the recursive reduction， that performance is becoming more equalized。

So so that's how you can gain more by doing that recursive reduction one more thing let's try I'm going to increase the number of elements let's go to 128。



![](img/bb4f2a016824f794f04b491deb09f3dd_142.png)

And see how that changes it。Because now our。Second stage recursion on the reduction will have more elements。

Which means compared to the Nive version or the nonrecursive version。

 the CPU will do more work and the GPU will add performance and I'm going to actually go into production and change it here as well。

So128。And I think I need to change all the tiles to four So stage3 tile is 4， stage four tile is 4。

That changes us。

![](img/bb4f2a016824f794f04b491deb09f3dd_144.png)

All right， let's come back here。😔。

![](img/bb4f2a016824f794f04b491deb09f3dd_146.png)

And we're going to do it this way。😔，Theying to hide this。



![](img/bb4f2a016824f794f04b491deb09f3dd_148.png)

Yeah。😊，I'm going to do run recursive reduction here。So for 128 elements。

 now we will get a comparison。So you're seeing a slight improvement on the left side。So stage 1， 62。

7， 62。6， basically within the error。Slight improvement in stage two， 65 versus 68。

Stritton proven in stood 3 with 1，58 to 1，60。And for stage four and stage5。Now remember。

 our device to device copy was 164， so for 128 million elements。

And doing recursive reduction we're able to hit that mark now so when when we go back to the readme and I me saying hey you need really big values and size of array to take advantage of the GPUs here's a perfect example of that while 32 million is big。

With 128 million and recursive reduction， we are actually able to gain more performance from it。

But even without recursion， even without recursive production。

 we were actually able to gain more performance because of the bigger sizes on the T。

 you actually see more optimization there。

![](img/bb4f2a016824f794f04b491deb09f3dd_150.png)

All right。So here are again， similar results on the GPUs。

Comparing recursive and nonrecursive reductions。Here's the benchmarks。

 here's charts to show single pass versus recursive reduction so the red and blue are for 32。

 the greens are 428， so you can see that there's a bigger speed up speed gain on these GPUs for recursive reduction on the unoptimized stages。

 whereas for the optimized stages that that gap reduces。Okay。

There's one final thing that you can take into account。

Which is telling the compiler which kernels are read only and not。

Who can tell the difference between these。Yeah， so in the first one it's the float that's coned so that means that like can't change the you can't change the actual like floats the second one。

 the pointer is con so that means that like you can't change yeah where the values pointing to in memory and in the third one both are con。

嗯。Right， so let me repeat that all for everybody to get in。You almost want to read it backwards。

 Okay， and this is called the clockwise or spiral rule。If you just have float star X。

Forge the constant if you just have float star x。It's a pointer to a float， right？

And you can read and you can change put the value in of the variable as well as the pointer。

 which is the address to the variable， you can change port。When you have load star。

 which is the second line here。Float constar says it is a pointer。To a constant float。

Which means you can change the pointer address， but you can't change the value that the pointer points to。

So constantt x value is constant， float star not constantt， so the pointer is not constant。

So you want to read it backwards。The first line cons short star x means。That you have。呃。

Pointer to a float and the pointer is constant。 You can change the value inside whatever the pointer is pointing to。

But the pointer can't be changed。The address of the pointer can't be changed。The final one。

 both the address is constant and the value in that variable is constant。

By telling the compiler these things， the compiler can better optimize and use constanttrain memory and other things on the GPU to essentially prefetch memory in advance。

Any questions on that？Okay。There's also one more， it's called the restrict flag。

So kind of like volatile。But in this case， the restrict flag tells the GPU that pointers that you're giving for specific memory。

 which is represented by the restrict flag do not overlap with other pointers。

Now here's here's a metal model to think about this， so we did transpose， we did reduction。

 we did matrix multiply， right？And in each of those， what we did was we did。Kuda Malik。

 we assigned memory for each of those individually we did multiple Malic calls。喂。😊，We could also。

 if we wanted do one bigger manacol， two times the size， for example。

Get one pointer and send the second pointer just to an offset。Off it to basically the second half。

That's a completely valid thing that you would do in everyday programming。

 have one valid call for that it's allocating all of the memory。

What the restrict flag does is say this memory is exclusively represented by this pointer and another pointer would get to it。

Written the bounds of clean memory access。So you're essentially assuring the compiler that， hey。

 you can do more optimizations for these variables。Because I've guaranteed my court is safe。

And that will also improve certain performance by reducing some compiler and runtime checks that are going to take place。

So to wrap up。There are lots of things。You can easily do inCUa to get started。

 but very quickly you want to identify where the performance bottlenecks are and the profile is a great tool for this。

You also want to understand which peak performance metrics you want to use。Today。

 both the examples that we saw use memory bandwidth because they were memory limited essentially。

 but sometimes you may have things that are compute limited and you'll want to use compute metrics to determine the performance。

 so identify the type of bottleneck。嗯。you want to take step by step optimization。

 try to identify what is the biggest game blocking you and optimize that and then we use templates are really in in a performance lab that is a good option for you to use to benchmark for different GPUs and different configurations so you can use them gracefully as well。

So that brings us to the end of。The performance lab。

 here are more resources for you to read the programming guide， the best practices guide。

 I should have also linked to the Insight read me， by the way。

 the Insight read Comp read me is great。Try it out， run these tools on your code。

 see what they tell you， try to understand what they're telling you because at this point the amount of ka you know。

 you are able to understand these level of metrics and then you can use those to optimize。

So that's all for today's class， let me pause and take any last questions before we order depart。Yes。

 Crystal， thanks for facilitating reminder that Wednesday we'll have the special office hours Crystal and I believe Han might also be there。

 so please use the time， please ask questions on Ed discussion。

 I think in all of my years of teaching the class for project three especially。

II think this is probably the fewest questions we are receiving I don't know if all of you are super motivated and doing an amazing job or if you're not asking questions remember if you don't ask questions and you're struggling with something。

You're going to be at risk right ask questions we are here to answer you。

 I want to res that as much as I can。If you don't ask questions you're stuck and you're spinning your wheels you're going to lose out and I don't want that I want you to ask a question and get answers quickly thank you to the person who also shared the GLTF resources that's a great idea please share other resources that you find that may be helpful to other students too。

So with that， good luck for Project three， looking forward to all of the pull requests used the office hours and I'll see you all next Monday for Eric Hanes's guest lecture。

Thank you for the lecture。

![](img/bb4f2a016824f794f04b491deb09f3dd_152.png)

Thank you through。