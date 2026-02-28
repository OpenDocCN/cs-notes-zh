# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p18 2024-10-21 - CIS5650 GPU Programming Fall 2024 Lecture 12 (Vulkan Lab II).zh_en -BV1sRtresE67_p18-

![](img/6cb40ed497ae887648330cfbd738ac69_0.png)

Yeah。Alright， let's go。Go back to Vcan and today we're going to mainly talk about command recording and also synchronization inside Vcan。

And those are like a pretty important part for Vcom because it's a like pretty asynchronous API。

 so you need to basically manually handle every synchronization for yourself and we start with the command buffer。

And for the command buffer to be useful by the GPU。

 like we need to actually submit the command buffer to one Q of the GPU。

 and it can record the sequence of sequence of commands。

 which can be like submitted to like any queue for execution。 But remember。

 the order of your recording is not the actual order of the execution。

 Your like the the finishing order of the execution can be like a pre arbitrarybit。

 So if you want to ensure some order between your like a different commands。

 you need to insert insert some like barriers inside。Comend buffer a recording stage。

And the command buffer is allocated and free from a VK command pool。

 which can cannot be corrected directly。The command buffer can only be allocated from the pool。

 it can now be like directly created。And we can。Record all of our commands。Like whatever it is。

 whether it is like a draw commands where some pipeline barrier between the V begin command buffer and also the V and command buffer。

 the command buffer， the concept of command buffer is pretty much similar to the concept of command recorder encoder inside the Web GPPU。

And here our command is being recorded at this like a code section， which is a。And。In between of。

 in between this。Command buffer， we can。We can actually look at the code of it。Oh嗯。O啊。Okay。哦。Yeah。

 like here we're building the command buffer for the graphics pipeline and we're basically just drawing like a full screen triangle。

 but there some there are some like resource ownership transfer。

 which we talk about it later those ownership transfers done by the pipeline barrier。

And we basically begin the winter pass。Said the viewport and set the scisessor of the screen。

 And then we find the descriptor set we created before， which is just one descriptor set。

 which is this graphics dot decscriptor set。 and we。By our pipeline。

And then we can do the actual draw command。 And this draw command actually just draw like a full screen triangle。

Which can fully cover the screen。 And we can use this as a full screen pass。 And this is actually a。



![](img/6cb40ed497ae887648330cfbd738ac69_2.png)

Yeah， this is somewhere we allocate the command buffer。

 But I don't think this is like too important for us to use because like， you can just allocate some。



![](img/6cb40ed497ae887648330cfbd738ac69_4.png)

Of the command buffer from the pool， if you need it。And the actual meat of the command buffer is。

 the all of the commands you are recording。 like in our example。

 we are doing compute retracing inside the compute shaders。 So we need to first。

Do the BK command dispatch inside the command buffer recording stage， which is a pre。

 which is a bit easier than the。

![](img/6cb40ed497ae887648330cfbd738ac69_6.png)

I would also always argue that compute pipeline is a bit easier than graphics pipeline。

 If you can go to the to do 5。1， which is a。

![](img/6cb40ed497ae887648330cfbd738ac69_8.png)

Basically， three lines of code， which first bind the compute pipeline and bind the distributor sets。

 And you can interchange the those two lines。 It wouldn't change like anything like。

And then you can do the actual dispatch， which is the。

Here the number 16 is our size of the work group， our。

workgroup size on the X direction is 16 and also on the Y direction is also 16。



![](img/6cb40ed497ae887648330cfbd738ac69_10.png)

So far are any questions for this。

![](img/6cb40ed497ae887648330cfbd738ac69_12.png)

Like this is a to do you can。Pretty much a few in the blanks in your code section。

It's pretty straightforward， I think。

![](img/6cb40ed497ae887648330cfbd738ac69_14.png)

Okay， let's continue。And another。And another code I've touched before。

 which is the another to do inside our graphics pipeline， inside graphics pipeline。

 before you draw anything and before you bind pipeline， by this group set。

 you always need to start a。

![](img/6cb40ed497ae887648330cfbd738ac69_16.png)

You always need to begin new like render path。Where you can use like multiple sub pass within a render pass。

 So you start with the V command begin render pass。

 And this is the render pass that we have created before。 If you look at the V。

 If you I look at this render pass begin info， you can see the。

We have a like a a handle to the render parts that we created before。And this。Yeah。

 and this beginning also contains about like a。Several different things。

 like such as the area and the areas offset and also the extent of it。 and also the。

This is where you specify the clear values for the whatever attachments we are trying to write to。

 Here is only the color and depth stencil。 And I haveve mentioned before that this one is pretty much optional for our。

Purpose， but。We are using it because it shares like some common base code for other examples inside this base code。



![](img/6cb40ed497ae887648330cfbd738ac69_18.png)

Yeah， and you can like specify the clear values inside the when past begin info and。



![](img/6cb40ed497ae887648330cfbd738ac69_20.png)

Another thing， other thing are just pretty much the same as the computers。

 You bind the discpancies and you bind the pipeline， and you can actually draw something like here。

 the VK command draw。 if you can， I'm sorry。

![](img/6cb40ed497ae887648330cfbd738ac69_22.png)

![](img/6cb40ed497ae887648330cfbd738ac69_23.png)

You can see the。A function signature by going to the。We can command draw。 You can see the。

 the first one is the command buffer， and the second one is vertex count。

 which means how many vertex you want to draw and。Soirer one is instanceense con。

And the first vertex and first index is just some offset into the vertex and index buffer。

And here we set them all to 0。And after we have finished all of the drawings。

 including joining the UI， and we can actually end the Ra pass， which。



![](img/6cb40ed497ae887648330cfbd738ac69_25.png)

We keep command and bring advice。And yeah。

![](img/6cb40ed497ae887648330cfbd738ac69_27.png)

Any questions for this。Winter past and also to draw inline。No， okay， let's continue。And yeah。

 the part 6 is the heart。 I think this is the heart of our broken language。呃。

Talk something about like synchronization inside Vcan。

 Like before we have introduced the concept of a queue。

Which means like each command buffer we have recorded can be submitted to a single queue。

 And then these queuees can execute asynchronously and also。Like。I mean， I mean。

 like for each command buffer。Their execution， the commands within them can be excd like inchronously。

 and also the commands on different like queues that can also run concurrently。 so we。

Need to synchronize within like a queue and also between queues。And also。

 CPU and GPU works concurrently。 We may need to wait for GPU work to finish sometime on CPU。

And so we need like different kinds of synchronization primitives。There are。

Different ways to synchronize a v program， like between different。Objects like CPUU or GPU。

 you want to use a fence or you want to synchronize between queue operations between different queues。

 you can use a sapho or you can use like a VK event to synchronize very versatilely within a single queue and at last which is I think it is very useful is the pipeline barrier。

 you can do a lot of things with like pipeline barrier。

But this pipeline barrier is actually a V command function call。 So you can only use them inside the。

呃。Inside the like a command buffer recording stage。 And also。

 the weekend event is also a B K command。Function call。 So you only need。

 you only can use them inside the recording stage。And let's talk about fence first because it is like pretty easy。

It just ensures like a CPU and GPU synchronization by signaling。

 signaling the CPU when a GPU task is completed。There are two states for the fence。 One is signaled。

 and the other one is unsed， like。The usage is normally we can first submit our work to the GPU and well in the submission stage。

 we mark a fence to track the completionilation of our GPU work and once this work is done by the GPU we signal the fence and GPU and CPUU can wait on the fence。

For the actual work you'll complete。哦。And in our example。

 like I think like two fences are uses for our program to ensure the synchization between different operations。

The first one is to is used to prevent the command compute command buffer from being used。

Been by use， I mean， being submitted to queue repeatedly。Before the last amendment work is finished。



![](img/6cb40ed497ae887648330cfbd738ac69_29.png)

Here we， we can look at the code like。

![](img/6cb40ed497ae887648330cfbd738ac69_31.png)

There's it to do for you， but。Yeah， so it's not that much。Yeah， inside the。

 this is the the the draw function。 So we need to first do the retreatcing in inside the compute queue。

 And then we can do the full screen pass inside the graphics Q。

 And here we are only using like one command buffer for the compute queue。

 So we are potentially going to run this function multiple times for like a very very short period of time。

 So to avoid this command buffer to be。Submitted like repeatedly， Where is the command。 Oh。

 this one to avoid it to be submitted repeatedly。 We can use like a fence。

This computer do to while we submit this， this command buffer。And we can。呃。

Send the also send the fence here。 So once this work is finished， it can signal the fence。 So in。

 in the next iteration， we will wait for the fence to complete and we will then reset the fence。

 This is pretty like a。A standard way of like using fence where you are like a wait for something。

 And after it is signal， you need to reset the status of the fence under the CPU。

And this can avoid we are using this one， this command will actually submit the mute for multiple times。



![](img/6cb40ed497ae887648330cfbd738ac69_33.png)

![](img/6cb40ed497ae887648330cfbd738ac69_34.png)

And yeah， and any questions for the， for this code were fence。It's's a privacy predatorors like。

Would device voice in and couldn。No， it is like a because it only wait for this sum to finish。

 But device synchronize， like synchronize everything on the。ButAll of the cus。Yeah， yeah， yeah， yeah。

 I think。It is like only for this current， like submission。It only signals the fence like after the。



![](img/6cb40ed497ae887648330cfbd738ac69_36.png)

Current work is finished on this current queue。And。And next， we will talk about pipeline stages。

 And yeah。

![](img/6cb40ed497ae887648330cfbd738ac69_38.png)

This pages stuff with some like a jargons like， unless let's work through it。

 And like every command you submit to Vcan。Basically go through a set of stages and these stages can be represented in in some item and the execution of the command in each of the stages can be called as operations。

 so we can basically submit a single command into a set of operations in different stages。

 for example， the dispatch command of a compr only go through the compute stage。

 but a draw command may go through like several stages。

 such as like a vertex stage or fragment stage。And which stage to be execute is defined inside the pipeline creation stage。

For GPU to GPU synchronization， Vcan allows programmers to synchronize all of the commands work all of produced more。

Correctly， to synchronize all the all of the operations in stage one with all of the operations in stage2。

 And if you don't understand， lets let's talk about it more and。

That means like Vcan can allow users to ensure the synization of all of the commands currently submitted in a QA of stage。

This is a， this is a set of stage like we can have like several stage inside X and also several stages in in Y。

But we can always make sure， like all of the。Commands submitted inside the queue。

 like complete the stage exit and before。The other commands， submitted in QB。Sts。Statewide。Yeah。

 that's a bit like a。M wasting， but we can talk about it a bit more like， for example， if we want to。

Let's go to some example first， and we'll go back to the。



![](img/6cb40ed497ae887648330cfbd738ac69_40.png)

嗯。Yeah。There's an example inside the pipeline barrier。So I I would just。

I'll just talk to you about some example with code like。



![](img/6cb40ed497ae887648330cfbd738ac69_42.png)

If we want to。For example， if we want to use a。A acquire blockchaincha image。啊 we something。Yeah。

So we have like stages here， which is a waste destination stage mask。

 which is we have like some kind of vector here。Yeah， it's just two stages。

The first stages is we is a color attachment stage， and the second stage is fragmentator stage。

 And what does， what does it mean like。We have two stages， and also。

We have two weeks somaphores here。 our somaphos is a。1， one is is present complete。

 and another is a compute complete some for， basically。What means is that like all of the stages。

Of the current command buffer will wait for the all of the。Will wait for the。

Swape chain image to be actually available so we can output the color to the attachment。



![](img/6cb40ed497ae887648330cfbd738ac69_44.png)

Okay， if you don't understand， it doesn't matter。 We can like， explain it like a bit later like。



![](img/6cb40ed497ae887648330cfbd738ac69_46.png)

So yeah， this is really a bit like mind twistings and moment of v and。😊。



![](img/6cb40ed497ae887648330cfbd738ac69_48.png)

Because moment， because Vcan doesn't like synchronize， like a single。

Single like command opera single command。Single command like function calls。 It like instead。

 it it will like synchronize stages。So we split we can split our commands into stages like for some command。

 it can split into like several stages like we can have if we are creating our pipeline only with a vertex shader and another is a fragment shader。

 then there is only like a two stages for this command draw command。But for the compute command。

 we only， we will only always only like have one stage， which is just compute stage。

So we are synchronized between stages of commands， instead of just commands。

And we can to ensure the synchronization means we can ensure an operation order and also a scoped memory order。

Here， operationeration order means the first set of operations。

Which means operations in those stages of X， we will finish before the second set of operation。

 which means like the operations in stage Y stars that's like a operation over odor dependency and another is memory order。

Which means。While we creating the synchronization primitive， we will specify a scoped memory access。

The first set of operations will have some first scope memory access and the second set of operations will have the second scope memory access。

We can ensure the memory access made by the first operations can be seen by the second set of operations。

Okay， this is like Superman twisting。Okay， so hypothetically like。

If if the scoped memory access encompasses all of the memory that is written to from the first one and is read from the second one。

 is that the same effect as the operational？No， average operation owner only like， determines the。

Determinines the first set of operation finishes。Before the second one starts。

But it does not like guarantee anything about memory。But only if you specify the。The memory access。

 the scope memory access， correct for the first and second set of operations。

 Then you can let the second memory access see the first like yeah。

 see the first set of operations do。嚟。Yes。😊，嗯。We will go back to this definition， but first。

Any questions like。Yeah， this is I don't know if it makes to do now。

 but like the website is done right now， any chance you can just drop a link in。



![](img/6cb40ed497ae887648330cfbd738ac69_50.png)

You mean the link to the slides。 Oh Alright， that's。呃 so。I don't think it's down。

You can also check the ad。 there's a post on ad too。There have a link to the。 Yeah。

 I believe there's a。那我们。

![](img/6cb40ed497ae887648330cfbd738ac69_52.png)

Okay， yeah， this is a， if you look at the v specification， this is actually something like a。😊，Yeah。

And we can。

![](img/6cb40ed497ae887648330cfbd738ac69_54.png)

We can go to this section 7， but it may take some time to load like just。



![](img/6cb40ed497ae887648330cfbd738ac69_56.png)

Fcus on slides for a bit。And yeah， the， the concept of pipeline stages is basically the core of vcan synization。



![](img/6cb40ed497ae887648330cfbd738ac69_58.png)

And oh， it is freeze， but let's just go back to our let's talk some of our first。

And we will like review this concept over and over throughout like our talk about Semapho and also pipeline barriers。

Sum For basically manages GPU to GPU synchronization。Between。

Between like mainly between different cues。Like for example。

 we have like a graphics queue and also compute queue。

 if you want to the graphics queue to wait for the compute queues drop to down。

 you need to use Sam of4。And it is something similar to the fence。

 It is it has a signal state and also an un signal state。And you can。

When you are submitting some word onto the queue， you can use some of。 You canmark some some of to。

Let the submission to signal this some of once the work is done。And also， you can wait for the sa4。

You can let certain stages wait for the sum of4。To be done。And we will look at examples for this。

And yeah。This is what I'm talking about。Its basically when you are submit submitting some work to the queue。

 you can specify the sum of words to signal。And when all of the operations inside this single submission to be completed。

And also， we can。Yeah。Specify the stage to wait for this sum of4 once this submit。

 once the sum of4 is signaled and this stages can continue。For example， we can for the。

 We can wait for the retracing commands of the computer queue to finish。Once it is finished。

 it will signal a se ofpho。And then we can start the fragment shader stage of the。Of。

 of the graphics queue， because。We， we need the storage image to be useful。

 so we can sample from the storage image inside the fragment shader stage。

 So we want the fragment shader stage to stars after this。All of the work on the compute to be done。

So we can use the sum of， and we can specify the stage to wait on。It's the fragment shader stage。

 So we， so after the works on the the recing work on the compute is done。

 we can start the fragment shader stage so we can sample from the storage image that we。

We are writing to in the computer。Here the first set of operations is all of the operations being submitted to the computeQ and the second set of operations is all of the operations being submitted to the graphicsQ。



![](img/6cb40ed497ae887648330cfbd738ac69_60.png)

Yeah， here's a typo。 This should be like after。Yeah， this should be after the fragment shader stage。

 including the fragment shader stage， because we want to ensure all of the all of these things。

 including the like some things happen after the fragment shader stage。

 including the fragment shader stage itself to be to happen after the。



![](img/6cb40ed497ae887648330cfbd738ac69_62.png)

All of the retraincing operations to be done inside the computer。And for the memory order to be。

And for the memory order to be valid， we also need to specify the memory scope of the。Oh， I'm sorry。

 Like this memory scope is already being， is being implicitly handled by the sum ofpho。

 Like for the sum ofpho， you don't worry， you don't need to worry about the。The memory order。

 it will like a handle for you。

![](img/6cb40ed497ae887648330cfbd738ac69_64.png)

呃， yeah。The the vcan specification have like a more complex definition of the。Yeah， just just FYY。

 I have already simplified it a bit for the pipeline stages and the first synchronization scope and the second synchronization scope。

 but it is still not that easy to understand， but。For this current example。

 do you have any like questions for this example？

![](img/6cb40ed497ae887648330cfbd738ac69_66.png)

We can just go to the code and to see if you have some questions。嗯。

Another thing we need to take care of is the swap chain。

 We need to get the next image inside the swap chain and output the output the output to the image once it is available。

But the operation of acquiring the next image is asynchronous。

And we need to signal a sample of once it is finished， so we can let the。

Color output postage to actually start after our image is available。 Okay， any questions for it。

And quick question。What is the first set of operations and the second set of operations we want to synchronize here。

Okay。Nick the first set is actually waiting to the texture because that be one thing like。

Here we are like query some image from the swap chain。あ。Okay。

 so are you saying that the first is actually acquiring members and fiscal？别的。Yeah。Yeah。

 the the second stage is actually。All of the stages inside the。

Current submission of the graphics queue， including the color output output stage and all of the stages after it。

Like we actually want like because。Because we want the image to be available before we actually。

I'll push through it。嗯， yeah， you get it。Yeah， the texture that you're ready to you have to actually pull from this watch。

Yeah， yeah。 but yeah， this is。です。Yeah， you， you need to like a because here we are waiting for the。

Swaapchas image to be available using a sepho。 So and our stages to be to wait on is the color output stage。

Color attachment， output stage。So。After our swapwacha image is available。

 we can actually start the color output stage。Any question for it。系。O。反正就是。Jo so。Just away。That like。

So I they might understand。For the first part。We were getting the next imageH trim swap chain Yeah。

 the ceies present complete。That's the Singapore we're waiting on。M for。

To basically have the next image to be right， right？Cool，Yeah， correct。 And so。Okay。

 graphics weight some floor。So W sum of4 is graphic submit info。

Wight sumit four iss that's for any sum fours that it's waiting on before to actually submitt。No。

Like， it will be instantly submitted to the GPU。 But the actual work。

Like the actual work after and including the color output stage will be postponed after the summer for is signaled。

 The， the submission is like a pretty。呃。Instant happen things。 But the actual work to be done can be。

Like we older by the GPU。The workers can。F all the work up until。Up until the color of full stage。

 it writes to the color of。Or wait up until up until the color attachment happens。Yeah， yeah， yeah。

 this stage， this colorter output stage and all of the stages after the。

This stage will wait for the sepho to， to be signaled。Yeah。Any， any other questions？And。If not。

 let's continue our。Discussions of pipeline barrier。 like this pipeline barrier is a。

Is used inside like Vki record command buffer， which means it is like a start is a function function call starts with V command。

Which means you only can use this one inside the recording of a command buffer。

So this one helps you handles the synchronization within a single queue。

 which means you can use this pipeline barrier to synchronization between different commands or different operations inside a single submission。

And you can specify the first set of operations and the second set of operations。

And the memory access of the。First and the second side。And。

This pipeline barrier will make sure the first set of operations。It's done。

 It's completed before the second set of operations actually starts。

And this barrier can also make sure that the first scoped access。

 scope memory access of the first set can be actually seen by the second scope of memory access of the second set。

And。Previously， we have mentioned that the same image accessed by different operations in possibly different stages。

It needs to be in like a different image layout。For example。

 if our image is used as a storage image inside the shader。

 whether it is fragment shader or compute shader。It needs to be in the layout， called general。

Which means this， in this layout， we can randomly rise to the image， randomly outputs to the image。

And another layout， which is super useful， is the present present words KR layout。

That's the layout you are going to use when you're like sending the image to the swatcha to be presented onto the screen。

And when the image is used as a color。Out for that attachment。

 the layouts should be in color attachment， optimal。In our example。

 we initially transformed the layout for the storage image using VK command pipeline barrier。



![](img/6cb40ed497ae887648330cfbd738ac69_68.png)

We can go back to the code to look at it。不。So。Here we have a some kind of helper function。And。Yeah。

 if you go into it， it， it is basically some image memory barrier and。And filled into the。

V he command pipeline barrier。So， yeah。So we can specify the old layout and the new layout here to finish the layout transition。

 And here， because we are basically creating a。AD dummy command buffer here。 If you can see。

 we are creating a new command buffer here， which is basically some dummy command buffer only contain this。

Image layout， like a。Transition command， which is。Which is。

 which means this command buffer only contains like。Only one this week command。Functional， so。

The stage mask can be。Yeah， so the， the stage mask is， is not a matter here。 Like for。

 for this current command buffer， because we're like basically transitioning the layout after we create the image。

 And this is something。 this is just a dummy command buffer。 we can。Yeah， but。

But in inside the actual， inside the command buffer， we are actually。Doing something， for example。

 our graphics command buffer or compute command buffer。

 We need to carefully specify the stages to the source stages and the destination stage。And。

If you are like specifying a wrong stage， the validation layer will throw error at at you。



![](img/6cb40ed497ae887648330cfbd738ac69_70.png)

Basically。And yeah。And you can。Yeah， and you can also do layout transition using a render pass。



![](img/6cb40ed497ae887648330cfbd738ac69_72.png)

And this is something very natural if you want to use some attachments with the graphics pipeline。

 because graphics， if you' are going to use a graphics pipeline。

 you will always need a render pass for it a render pass basically specify all of the attachments to use and also the the layout between。

A different sapas。If you only have one surpa that that is only like one layout。

 And if you have like multiple surpa， that's going to be like multiple layout for the image between different surpas and also the initial and final。



![](img/6cb40ed497ae887648330cfbd738ac69_74.png)

Layout of the image。 The render pass will automatically transition the layout for you。

 Let's look at the code。

![](img/6cb40ed497ae887648330cfbd738ac69_76.png)

Yeah， we need to actually find all of the references of this。This one。

 and this one is actually created inside the。Base pass。No我想 this one。呃问问。你。😔，Yeah。Yes， here。Like。

 here， we have。For our render pass。We need to specify the attachments and also when we are specifying the attachments。

We are actually specifying the initial layout and the final layout。 That means the。

 the input to this render pass is actually this layout。

For this for the first attachment and for the second attachment。

 the the input layout should be this one。 and here and defined is accompanied with a V attachment load of clear。

 which means we want to clear this image once we are loading it so we don't actually care about the layout of the image。

And the final layout is， it is the output of the render pass attachment。 Like， for example。

 for the first one， we are using the color attachment。So we want to present this。

 we want to send this image to the present queue and then show it on the screen。

 so the final layout will be VK image layout present towards KHR。And for the depth attachment。

 we will just set it to the layout that is used for the depth output。And。

Aside from the initial and final layout， you can specify the layout for each surpa。For example。

 we only have one surpa here and you can go to this suras description。And。You can see there's a。

One color attachment and and another depth attachment。

 And you can see we can specify the layout here。So now we have a， we have three layout。

 We have a input layout and output layout and a layout in between， which is the surpa layout。

 So the layout transition will be automatically handled by。

By wken if you specify the all of it inside the render pass。



![](img/6cb40ed497ae887648330cfbd738ac69_78.png)

OK。And another thing that pipeline barrier。 Yeah， let's go back to pipeline barrier。



![](img/6cb40ed497ae887648330cfbd738ac69_80.png)

About pipeline barrierer is that they can do resource ownership transfer。Whiish。Yeah。

 it's another complicated topic inside Vcan because when once you are creating some resource with V sharing mode exclusive。

 whether it is an image where it is a buffer。If it is using by one Q， for example。

 it is used our storage image is used by the compute queue。For retracing computation。

 And then it will be sampled by the graphicq using the fragment shader to sample the。

There's an ownership transfer between different queuees。

And you need to explicitly handle this ownership transfer。That means， like， a。Yeah。

 we have an initial layout transition for the storage image。呃。Yeah， it should be something like yeah。

 prepare storage buffers。嗯，那 know。Yeah， prepare storage image and。Here， we are doing a。

Initial layout transition from。Yeah， haven。 yeah， yeah。 Yeah。 Here。

 we are transitioning the layout from。I'm defined to actually。

This one this one is just layout general， which means we are transforming from some undefined memory layout data to this general things。

 which is means which means we can general thing means we can randomly rise to the。To the image。

 which means it can be used as a like a storage image。

And another thing we need to take care of because here we are using this create command buffer actually creates a command buffer for the GraphsQ if you can take a look at the implementation of it。

 it actually uses this command pool and this command pool actually its being created on on the yeah on the graphicphsQ。

So this command buffer we' are creating is on the graphicsq。But after this one。

 we need to use this storage image on the compute queue。

That means we need to transfer the ownership of this storage image from GraphsQ to the compute queue。

Okay， anyone， any questions。Okay， and and the transition will be。

We will create like a V image memory barrier and use the V command pipeline barrier and here the important thing to note is that we need to specify the source index and the destination index of different cues。

And here actually， we only need the。Because we are。

Here we are call we call this this barrier to be the release buffer， release barrier。 I'm sorry。

 release barrier， because we are doing this image barrier on the。On this command buffer。

 which is this command buffer I explained before is' on the graphics Q。

 so we are releasing this resource from graphicraphsQ to compute queue。So we only care about our。

The current access state of our resource， which means the source access mark and also the。

And also the source stage， like the VK Command Peplan barrier here。

 this is the source stage and this is the destination stage。Here。

 because we are releasing from this current queue。 And so we only care about our source access stage and also the source。

Access mask。And。As， as you can tell from the name， like， if we will have release， we have aque。

 and you can look at like the a barrier from the。Build compute command buffer or something。 Yeah。

 build compute command buffer and。Here we actually need to acquire the command buffer for computeQ。

So here our source family will be graphics， and the destination queue will be like the compute queue。

 And here we are this command buffer is actually being recorded on the。On the CPU。

 but it is only going to be submitted to the computeQ because it is created with some command pool that was created on the computeQ so。

Before we release the， release this image from the graphics queue。

 and now we need to query it on the compute queue。So， for。Acquiring this resource。

 we don't care about the source access mask because we cannot。

 because the barrier cannot handle some handle any synchronization between queues。

 So we only care about the destination。The destination of stages and also the destination access mask。

Which here is the shader red bit because we are going to output to this storage image， basically。

 and also the stage will be a compute shader。 and this one doesn't actually matter。And yeah。



![](img/6cb40ed497ae887648330cfbd738ac69_82.png)

And this is a resource owner which transfer。If， if you have a release buffer。

 you need to have a bar Aque buffer。 we can try to。



![](img/6cb40ed497ae887648330cfbd738ac69_84.png)

Delay， delete this release buffer。And to see what happens。



![](img/6cb40ed497ae887648330cfbd738ac69_86.png)

Yeah， it runs。It runs， but with some validation error。Yeah。

 you will see the validation layer will tell you。This acquire ownership of this of this image on the computerQ。

Cas no marching release buffer。

![](img/6cb40ed497ae887648330cfbd738ac69_88.png)

For e Huion。It will run， but it will run with like some validation error and for production code。

 you will like definitely need to eliminate all of the validation  error。Yeah。So。

 and another complicated thing is that we are running this inside a loop。

 So after we acquire this image from the computerbucu。

We need to release it again because it needs to be read。By the graphicq inside the fragmentator。

 So there's a release buffer from the compute queue here。

 And there's going to be another acquire buffer in front of the command buffer recording of the graphicsq。



![](img/6cb40ed497ae887648330cfbd738ac69_90.png)

Yeah， this is Boca。Yeah。And questions for it， ownership transfer。



![](img/6cb40ed497ae887648330cfbd738ac69_92.png)

哦。Maybe you don't hypothetically if you want to like。Not being used。

Not having any of you to install you want to actually have like。Like two different images in flight。

Yeah， like is there an intelligent way to be like， okay all？Acquire a like。哦。A particular far like。

Whatever image is available that's satisfies these conditions so I think are one of those two images or like you kind of just。

Vcan doesn't have like this mechanism to do it， but you can write your own like， for example。

 you can write your own rendergraph upon Vulcan to let like rendergraph to handle all of the resource。

Ex thingss to use like。 You can。Do like a。诶你先。And， yeah。Yeah， but that's not all of it。

 That's not like all of pattern barrier of。 I'm sorry。

 that's not all of like resource ownership transfer。 And you can amazing in question， Michael。Oh。

 I was just like。Yeah， I just like。So。To be able to， like， use。If I store something。

 if I write the image in。き？I have to。This pipeline barrier。呃。That basically says。

 I'm giving this to a grant cube。For， for。A later graphics for that to be able to like， Yeah， yeah。

 also have。A high area at the beginning， being like。Oh。

 I'm taking this image from the compute queue into a draft queue。Yeah， it is something like like， I。

 I handle you this phone now。 and you need to tell me that I will receive this phone。

 And Im receiving I taken this phone。 It's my phone now。 Yeah， yeah， yeah， you need to。

 And then I'm gonna do。 yeah and。Yeah and that's not all of it， aside from Pebble barrier。

 which is required in resource ownership transfer to synchronize between different cues。

 you also need to use some of for。Because pad barrier can only synchronize within a queue。

 so our ownership trace transfer by barrier but used must be accompanied with a semaphore。

By using some of four， we can synchronize between different cues。Oh。So， here we are。

Using like a summerpho for the。For the graphics queue， we can go through the draw function。And。

Here in the computer summit info full。We're actually signaling a semophore。Here。

 once the work is complete by this V TQ summit and this one is weighted by。Is weighed by the。

Graphsq here。And and， and。And the width stage for the graphics here is fragment shader because we're only going to use the result of the storage image in the fragment shader stage where we are sampling from it。



![](img/6cb40ed497ae887648330cfbd738ac69_94.png)

And any question for this summermapho？

![](img/6cb40ed497ae887648330cfbd738ac69_96.png)

Yeah， my speak a color。对。Oh， this one is a。This one is something we have talked before is that。

When we are trying to acquire an image from a swatching， this operation is asynchronous。

 so we will need our color output stage to wait for the。Acquire of the image to be。

The image actually to be available so we can continue the color attachment and also the stages after。

Yeah， this is a， this is a。This is a vector， which has two stage。Bit and also the， and also。

 we have two summer of words。 And this is a 1 to， one mapping。 And this。

 this sum of for maps to this stage。 and this summer of for。Maps to that stage。



![](img/6cb40ed497ae887648330cfbd738ac69_98.png)

Yeah， okay。Any questions for。If not， let's continue our surplss dependencies。



![](img/6cb40ed497ae887648330cfbd738ac69_100.png)

嗯。Yeah， and sub dependencies are just essentially pipeline barriers， like。

It will be translated by your driver into barriers inside pipelines， but just says。

Just as layout inside surpas， you can specify surpa dependencies to。Let the。

To automatically handle the memory dependency for you for some， for for the attachments。

 let's look at the example。

![](img/6cb40ed497ae887648330cfbd738ac69_102.png)

![](img/6cb40ed497ae887648330cfbd738ac69_103.png)

And here we have two attachment。 The first one is the。Its color。 And the second one is the depth。

And and we also have like two dependencies。The dependencies applies to like each dependency actually applies to all of the attachments。

 But here by specifying the stage mask and also the access mark， we， we can like limited the。

Memory access。 And also the。Stages to be synchronized。So for this one， it is。

 it is for the depth buffer。 So we are。Said we where， were here。 we are like the， the。

 the swirl surpaas is the external， which means。All of the operations before this winter pass。Like。

For example， we have a loop。 We have the first loop has render pass one。

 and the second loop has render pass 2。 and this， this。This short side pass for winter past2 means。

The run pass one means the previously previous render pass。 So we are synchronizing between the。

The previous winter past， so we can avoid it to be right to。Before。Before the previous ride is done。

Like。😊，The， the early and late fragment test speeds are just for depth testing and also depth writing。

And here by specifying the subpa dependency， we can avoid this attachment to be override by the by by by the next one in the loop so we can。

Yeah， so it basically just says like after the previous write is done。

 we can start our like core current like a read and read。And this one is pretty much similar。And。

Yeah， and the source access mark is zero and。Yeah， it doesn't make like too much sense to me。

But the validation error doesn't scream。嗯。yah星期四。Yeah， I think it is because we have some like a。

Depenency chain between like because previously， we have some like some ofs for the。

We have some summers for our swap image。 and also this this one。

 we like like to form some kind of dependency chains to avoid the。To actually。

 we can use to let us use the source access mass to be zero here。

 but that's a bit like complicated to explain， so。And。好。Do it。想。我机会。

This one actually applies to all of the attachments。 each each one。

 each one of the sub dependency applies to all of the attachments。

 But this one actually specify the test stages and also the depth sil attachment right。

 So it applies to the。Des， attachment。AndSo when you're。You are special。The三。

probably some thats there。This for。Yeah， yes。😊，Yeah， yeah， yeah。 You can。

 You can look at the because in， everything is very explicit。呃。There's a so for this current。

When they pass， we have a frame buffer。Yeah。We have。 we can find out。

 We can first find a spring buffer for it。 And to look at the。Image inside the frame buffer。Yeah。

 here。Yeah， the attachments will be。Yeah， this depth stencil， we can go to the。

 we can find where we created this depth stencil。呃。I think it's here。Yeah， we're。

 we're creating this depth stencil image with usage as VT image usage depth stencil attachment it。

 So we are， yeah， basically creating it with this flag。Yeah。



![](img/6cb40ed497ae887648330cfbd738ac69_105.png)

Alright， any other questions for。

![](img/6cb40ed497ae887648330cfbd738ac69_107.png)

Yeah。This is something for you to。Take a look at， if you cannot。诶货芦米。Yeah。

 any other question for Spa dependency？If不 want。Or we did in the last homework。我所。

Like doing a program or anything。这个。Right。And it deferred render and like。

 say we did the thing where。我个定。We did。We renteded out like tonight。Position。And then。

That was in like the first pipeline and then the second pipeline。We had。

 we took those attachments and then like， yeah。Yeah。So like。



![](img/6cb40ed497ae887648330cfbd738ac69_109.png)

Does that all happen in one rendered path and like can you？Create this like this render pass。

Se up the render pass so it's like， yeah。ition yeah， yeah， yeah， you， you can， you can。

 you can do it using subpa dependency。 Another way of doing it is using pipeline barrier。呃。Yeah。

 because you can。Because you are basically in inside the different the geometry path。

 the first one that us puts to the position normal or something。

 and the second shading path will like both on the graphics pipeline， basically。

And so if you want to want， want them both on the graphic pipeline， you can use the。

Pipline barrier to synchronize between those two。Yeah， draw command were。 and also the。

WhatRes attached to the different render path。Yeah， the。I'm pretty， yeah。

 those two are interchangeable， but the subpa dependency may be like it's just something like a syntax sugar that makes you easier to use。

Yeah。

![](img/6cb40ed497ae887648330cfbd738ac69_111.png)

Alright， and the last thing we want， I， I want to mention about synchronization is a VK event。



![](img/6cb40ed497ae887648330cfbd738ac69_113.png)

V event is。Is another like a finer grid of control you can get from Vcan is that you can even do some work in between the。

Plan barrier。That means you can like set an event and do some work and wait for this event。But。

I wouldn't like a。Discuss it that much because I personally that didn't use it that much。

 So I will leave it for you to discover， yeah。

![](img/6cb40ed497ae887648330cfbd738ac69_115.png)

![](img/6cb40ed497ae887648330cfbd738ac69_116.png)

Yeah， lastly， we have。We need to destroy a lot of resources for Vcan。



![](img/6cb40ed497ae887648330cfbd738ac69_118.png)

Because。Vcan is just， it doesn't have like any like garbage collection mechanism mechanism or even like a smart pointers for you。

 So you you only need to， you need to like manually destroy all of the。All of the。

Objects you created yourself。 And this one is not that difficult。 So I will。



![](img/6cb40ed497ae887648330cfbd738ac69_120.png)

呢 it to you。And。And I think the last section is debugging。 And it is not that。

 I think it is not that difficult to enable。 You can even enable it inside the book SD D K。

 So I will leave all the。Last few slides for you to discover。

And I think that is for our work introduction。And yeah。

 there are a few more like references to for you to reference。And you can feel free to look at them。

O。召看咁 if youこ度我。Deci don't Thank you very good。No。Yeah I think I think我看 starting。呃这个的是。

New slides together in one more than you've ever had class so。了ぱさ。嗯。O， so。6。6。

 let's take a nine minute break feedback at 635。The second part of。还款关系的。は。そ。



![](img/6cb40ed497ae887648330cfbd738ac69_122.png)

![](img/6cb40ed497ae887648330cfbd738ac69_123.png)