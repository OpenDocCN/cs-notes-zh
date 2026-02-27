# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p06 2024-09-11 - Guest Lecture 1-Introduction： NVIDIA  NSight Graphics.zh_en -BV1sRtresE67_p6-

![](img/496db206779fbd8c3e4f6920c270de8a_0.png)

Let's see。好。好。everybody welcome is our first guest lecture so just for context in the history of565 more try and bring the industry。

It's like the re I gave you last time so gas section are part of that that we bring up for more than five years now。

 so time for all the gas we very special one one of our own now and we' here on the assets de to team so we the classroom here。

 usually two years ago and graduated in 2021 2022。Undergrad。

 I will explain yes one of my best students worked on a final project that was about radar sensing。

And then we join them video。 So really excited to have you here。

 He's going to be talking to us about graphic sea burning。 So I showed a same thing on regulara。

What he's going to show is a lot about how graphics APIs are but especially with like a visual art but it's not somethingne or very large data。

 so how do we think that， how we profile and stuff like that。So be welcome。

 Im turn it forward to you。All right， all right， hi everyone。

 some of you have probably met me at the sort of start of the event， start of the school year event。

 but most of you are new to me so hi and welcome and thank you for showing up。

So today's presentation will be on NVIA Ins graphics and I will give you guys sort of a brief。

 well not so brief， it is one hour long total and sort of a lecture on what that is and how to use it and how to use it in your own profiling and debugging workflow。

So just a quick introduction of who I am， Professor Muhammamed gave us like a really good overview of who I am。

 so my name is De and I graduated in DMD in May of 2022。

 and then I graduated from CHGT the year after in 2023 so that means I took GPU actually in the fall of 2022 and currently I work for NVIDdia and I work on their graphicsDevelop tools team。

One of these fun facts is that during S wrap of this year， my team。

 my entire team had dinner with Dr。 Lane and they all took a picture together that was very sweet。

 this is my coworker and this is my manager。Yeah。So first of all。

 we'll sort of talk about an overview of what I'm going to do today。

 so what is the motivation for this lecture in this class you will learn KUDA but in order to fully take advantage of the GPU you should really learn about its behaviors。

And so the overall discussion will go like this。I will talk a little bit about what EnSI graphics is and how it fits into the sort of overall Insight toolsol ecosystem。

 and then we'll take a walkthrough of all of the UI and general features of how to use the two main features in NSI graphics。

The first one is called freeing Debugger and the second one is called GPU tracece。

 my team specifically works on GPU trace， so that one will be the more like will be the bulk of today's presentation。

And then wire the first section will mostly be like a walkthrough of the UI and in general how to use it。

So as some of you guys might know InsSight is like you guys have probably heard of Insight in some capacity at this point in class Insight is basically the name we give to all of the tools the developer tools that we give to so that coders can use them to basically better understand how their applications are performing and potentially also debug it so the three big ones right now are Insight systems and compute and In graphics there is also like Insight visual Studio which are visual Studio extensions but those are sort of like the starting point of how Insight used to be before kind of it really got off and became its own applications。

 but today we're mostly going to talk about InI graphics which is a standalone application。

That you can use to profile graphics things。so。NNSI systems is used to basically examine CPU workloads whereas EnSI compute is used to analyze ka kernels and enzymeI graphics like I was saying before is used in graphics and games applications so typically the workflow starts like this one would start with NSI systems and then basically then they can figure out their CPUU Bo or GPU bound and then if you are GPU bound then you can choose for your particular use case to use EnsI compute or NSI graphics。

For more detailed analysis。So Enographics has two main features well actually there's like three but the third one is is in beta mode so we're not going to talk about that today frame debugger on a very high level basically gives you a draw by drawaw pass over a single frame of your application it will allow you to check for rendering bugs and check resources in pipeline states on the GPU this can basically be really helpful when it comes to ensuring that you're using your graphics APIs properly。

And that you've done basically the right set stages for your pipeline so for example。

One such use case， let's say， for example， you might say， oh。

 I want to use a compute shader to draw a checker pattern and then I will later on render this checker pattern to my screen。

Then you want to make sure did my compute shader actually work the way I thought it did。

 did it actually draw something that I can later read from。

 this would be a good place for you to check that。嗯。GPU trace， on the other hand。

 is a profiling tool， which basically means that you're using it to figure out how quickly things ran and what kinds of what the throughputs were on each of the hardware units and for your shaders also gives you like a per shader line performance information。

We'll talk about frameme debugger first and then we'll move on to GPU tracece。

For some of you guys who have used other similar tools such as like Microsoft Pics or rendernder Doc or Xcode。

 I know has some builtin tools and AMD also has their own profiling situation and even web graphics also have their own stuff。

 you probably recognize that most or some of them have these two features and sort of like an all in one situation。

 but for N video we kind of like separated them into two separate applications。So yeah。

 let's take a walkthrough of the frame debugger。I'll show you some of the available functionalities。

😊，So when you open up En graphics， the first thing you're going to see is basically the landing page right here。

 so to start a new session you'll just press the connect button。And then for each of these things。

 this is the window that's going to pop up。The connection is basically just telling you that you're allowed to also do remote debugging。

 but for most intents and purposes， the machine that you're using is the one that you're going to be launching the application from also this is where you basically paste in the path application executable。

 your working directory any command line arguments are at my need。Then。😊。

You'll see basically a list of the activities and from what I was mentioning before frame debuggger is one of them and GPU trace is another one。

 so in this case we'll use frame debugger and you can also choose your per API settings or your general sort of how you want to make your capture and then once you're ready you can basically press launch frame debugger and then this is what comes up。



![](img/496db206779fbd8c3e4f6920c270de8a_2.png)

Um， then once this pops up， that's your that's the application being launched。

 you can just press F 11 when you're ready to make a captureer。Once you have a capture。

 you'll see that there's this sort of play by play or draw by draw kind of a replay of the frame that you just captured。

 sorry， a slightly more complicated example using the Vulcan scene。



![](img/496db206779fbd8c3e4f6920c270de8a_4.png)

Um， yeah， as you can see， slowly pieces kind of start coming in， draw by draw。



![](img/496db206779fbd8c3e4f6920c270de8a_6.png)

So yes when things are popping up in this， is it like a new draw call each time， yeah。



![](img/496db206779fbd8c3e4f6920c270de8a_8.png)

![](img/496db206779fbd8c3e4f6920c270de8a_9.png)

， I will show you on the API list in a second。

![](img/496db206779fbd8c3e4f6920c270de8a_11.png)

So the general basically the look of frame debugger is like this and we will go through basically。

 you'll see it's a lot of information， but we'll go through all of these little parts together。

Just for some general settings in the very top， disconnect basically stops the frame debugger where your program continues to run。

 terminate will just stop the program and stop the frame debugger session。

The next frame basically analyzes the next frame， and then resume allows your application to resume so you can make another capture like manually。

You can also export your frame as a C++ capture so you can isolate it and step through by yourself。

And then we'll talk about profiling traders。At the end of this section and the end of the next section。

 it is a little involved。嗯。So the first thing you'll see is this event viewer。

 it's basically a list of the APIs that you've recorded to your command buffer as well as things related to setting up your command queue。

So。You can sort of use it to control and navigate your session。

 like if you click on one of these events， it's going to automatically highlight them in the other parts of the program。

And so it basically provides you a list of all commands in order of execution with respect to the frame。

Now here very difficult to see I understand， but I was hoping to show you basically a correspondence between what you expect to be writing in the code and what you can expect to see actually show up in the API list so for example in the Vulcan triangle sample in the render function the first thing you'll see is this like Vk weight for fence which is at the very top right here and the VK acquire next image which is how we acquire the next render target that we want all of our command buffers to be drawn to and then。

Your reset fence and then reset command buffer， which basically just cleans everything up you submit any before you record any commands to it。

And then finally your begin command buffer for command， which is right right here。

 so you can see the order of all of these things are exactly as you wrote them here with the exception of VKQ S。

 which we'll talk about in a second。嗯。Once you begin your command buffer。

 then you can start recording commands to it， so right after begin render pass。

 you will do your set viewport， your Sees or all of these commands。

 draw indexed and render pass and all of these will appear also right here in order。Now。

 once you're done， you click you say end command buffer， which is also right here。

And now going back to Q submitmit， so when you're writing the code from your perspective。

 you have to record the commands to your buffer before you submit that buffer to the queue， however。

 from the GPU's perspective， it receives that Q submission first and then starts executing all the commands on the buffer。

 which is why all of these guys come after your Q submit call on the API list。

Now last year your wonderful TA Andrew had a really good question。

 which was what happens if you have multiple draw calls or multiple APIs that get executed at once the first question you might be having is given that many applications tend to pipeline their frames which just basically means before you even present。

The first frame you actually begin working on on the frame after that so you might be having some sort of interleaved APIs that are happening sort of concurrently at the same time right the way that I believe and the way that I believe frame debugger does it is that you're able to isolate the API calls with the frame that's associated with by looking at the render pass so we only show you the frame that you captured and the API calls corresponding to that frame and then secondly。

For two APIs being executed at the same time， this often happens with draw calls。

 so while frame debugger doesn't necessarily show it to you concurrently。

 if you look at it on GPPU tracece， it will show you that this point at this particular draw call。

 we don't give you like a discernible， one of them happen before the other。

 this is all sort of together at once。You will see later on what I mean。

Yeah that is the event viewer then the scrubber is basically just a horizontal view of the event viewer where you can click through all of the events they're sort of indexed by their ID and we'll take a closer look at this。

You can it gives you all of the events in either Qcentric or threatcentric hierarchy and then you can pick whichever view you want to see them。

 there is a correspondence between the tick marks that are used here as well as how they're used in the API list。

So for example， if you had an application that has a compute shader and then it uses the graphics pipeline afterwards。

 then you'll see， oh， I did some work on my compute queue。

 and then afterwards I did some work using that on my graphics queue and it'll show you separated by the cues。

嗯。y。And then the current target view basically just shows you what's currently being put onto your screen and also gives you like the outbound targets like your color。

 your depth and your stencil buffers。嗯。And then event details allows you to basically see which parameters were passed into each of these calls。

 and you can also click on these individual links to actually examine each of the parameters themselves as well。

The API inspector is where the bulk of your information is going to come from， so for example。

 if you had a graphics pipeline or if you had a command that was on a graphics pipeline。

 you'll end up seeing things like this right like sort of on the left side on the left column。

 your input assembler， your viewport ver text shader， Raster fragment shader， things like that。

And we'll talk about sort of what each of these tabs kind of offer you in terms of information。

So first， the pipeline information is exactly as you exactly as it says。

 whatever you set up your pipeline to have should reflect to here。

 so this will be a very good place for you to check to make sure that you've actually set up everything the way you thought you did and that things are matching what you wrote。

Um。And yeah， and also checking to make sure that the shader stages that you bound to this pipeline are matching what you're expecting。

The same situation goes for the render pass where you。All of your setup stages should match as well。

The input assembler now。This stage is where you should start seeing the vertex the vertex information go in。

 so for example， your vertex findings you go in and you see that there's this link right here that links to the buffer。

 well what could this be？This is。The positions of the triangle。

 like the vertex of the vertices of the bookan triangle。

 and then as well as the colors of each of the points of the triangle。

 so as you can remember from the picture before it was red， blue and green，嗯。

Theport same as exact situation， most of the time is just going to tell you the width and the height。

Now for the vertex trader it's going to tell you the expected inputs and the expected outputs as well as any other uniform variables that you're using so in this case you're like hey wait a second I have some uniform variables what could this be they're your projection model and view matrices and things like that so this will be a good place also to sanity check that you've actually that you're actually passing in these variables properly and they're going to be they're being used properly。

嗯。Rster state， this includes your polygon draw mode and your front face， death bias。

 things like that。And then your fragment shader， which also tells you the input and output。

 you can also view the source code here if you want to， you know， very general。Pixel operations。

Things exactly how you would set them up here。And information about the current context that you're on。

 so this will give you information about the physical device in Vulcan， your device。

 the queue that it's on the command buffer that you're currently on。

 the pipeline pipeline layout that you've set your pipeline up with， I think， and the render pass。

And you're frame debugger。Now if you have a compute shader。

 then you're not going to or if you're on like a compute queue。

 then you're not going to be seeing any of that information from before you're going to be getting like specialized compute shader stuff。

So in this case， very similar， you can see that the stage， the pipeline Shar stage is compute。

 you can check your source code， you can look at the compute module， things like that。

And then lastly， this will be relevant for your bulk and homework， which I think is homework five。

 if you have control youreslation control and teslation evaluation as part of your graphics pipeline。

 they will also show up here and again the same information from before will apply again here。

APpiI statistics will give you an overview of roughly how long things took in CPUU time and in GPU time。

 but this is not the place to be doing profiling， but this might be a place to maybe start thinking about profiling these will tell you essentially like which one needs APIs to calls to how long to execute。

Another cool view is the geometry view， which basically allows you to sity check that your thing is actually trying to draw all the right triangles。

嗯。Now all resources will allow you to see the resources that are bound to the GPU， so for instance。

 I believe these guys represent like the different like the pipeline frames that are waiting to be drawn。

And then other things such as like your transform matrices or like you know。

 your vertices and things like that will also all show up here。嗯。

And it also gives you a per revision view of each of these of the resource that you've chosen。

And then in a similar vein， that means you're also allowed to check the pixel history of a single pixel on these resources。

 so if you open a pixel history it'll bring you back to the resource selector。

 then you can choose the resource you want to look at and then you'll see all the different revisions you can check。

 click on whichever one you want and then check the target。And then pick the pixel。

 and it will give you。The exact revision history of that single pixel。

 as well as which draw calls or like which calls modified those pixels。

If you have an acceleration structure， it will also show up as part of your resources。

 you can click on it and it'll bring you to this cool acceleration structure view。

Now the shader profiler。So this is what this allows you to do。

 so the shader profiler is something that both the GPU trace and the frame debugger has in common。

 but the frame debugger version shows you less information than the GPU trace version。

 but what the frame debugger version does let you do is it lets you live edit and live compiled your shaders。

Soum。For example， when you navigate to source View。

 you can choose the shader that you're interested in editing。

And then you'll see this little pop up window show up where the left side is essentially the original view and the right side is anything that you can edit so let's say for example。

 I have a my bulkcan compute particles sample and I decide I don't want the colors to be this rainbow color I want them all to be blue for instance。

 then I can edit it here， then press compile。And then the resulting replay will give you the changes that you've just made。

Okay， that was information。说了。Hi， Mikey， yes。他会。A revision is just any changes that have occurred to this image。

So like every pre。Not quite every frame， because in one single frame you're going to see multiple draws right so like it's every single time this thing has changed。

嗯。Okay。Oh。I think they have to be， so I think it is based off of distinct。Calls， distinct API calls。

 if you catch my drift。Her draw called。But I was going to say there might be other things that modify it。

 I would think， what on。Yeah。Actually， where's the example， let me pull it the example。

So begin render pass is something that can， for example， that's not a draw call， but it can。You know。

 do something to it。And the following that draw indexed， right？So it's not， it's not necessarily。

Restricted to just draw calls。嗯。诶的没对。好可。好。你讲就 ok 啦。This。

Or it is like from the example if we have a like example。

Amberline theater the and is it will lead from plant image and if we use it kind of。Data profiler。

Take a revision and build it like after we made our revision kind like is the O data those。

That is a very good question。I think that if your shader depends on the last frame。Information。So。

So as far as I know frame debugger can only capture one frame so if you were to make changes to this particular so any of your shadedr changes that you make apply to this frame right so let's say you take a capture you'll see you go to next frame and take capture the next frame I'm pretty sure it will just take the original application because what you're modifying is a replay it's not the original application right so when you press next frame to take like a frame debugger section of the next frame it's going to stick with the original application data so it's not going to read from your your newly modified like like your newly modified shader information。

Yeah。就谁上出来嘅。Yes。好 the same。Yeah， and and it essentially basically allows you to rapid a prototype if you want to make changes actual changes。

 you probably have to go back to your source code， but a lot of the times I guess the goal here is to mitigate the amount of time people spend doing code modification。

 build， deploy look， right， that kind of removing that kind of friction。系呀。

What's the support look like for briefra pipeline1 I know you've had the acceleration structures shortly。

 it's not traditional aspect。UNo， I do not have an exact example of it。With me。But。IBelieve， I mean。

 we can take one right now， I guess。If I have an example but。

The other corresponding shader stages will show up as well because they all are part of the graphics pipeline。

 so it's just a matter of adding more and more of the individual stages in between。

 so instead of seeing like teslation control text tslation evaluation you'll see like the rage end。

 hit miss， yeah， things like that。Okay， one question for me on。

On the shader deparer and I did a really powerful tool， right， just like you were saying for that。

 I think， is there， are there any limits to how much you didn't modify。

So they don't do any validations， that as far as I know is true。Yeah， it will say that I can't hey。

 I couldn't compile this， this doesn't make sense， it'll say that in the compile results。

But as far as actual like it doesn't do an additional validation besides that。

Are you in modify multiple changes that once to see how they。Oh， actually。

You can definitely modify multiple of them， but I don't know if you can do them at the same time。

 like I'm pretty sure you can like you make your modifications， you press compile。

 and then you go to the next one， you modify it then press compile， then you go to the next one。

 modify and press compile。You can definitely edit and compile multiple ones。

 but I don't know if you can make it the all compile at the same time yeah。

 but you I don't think you have to go back to your like source code and rebuild or anything。Okay。

 so GPU trace， this is the part that's going to be a little longer and slightly more involved。

 so GPU tracece is essentially a tool that lets you profile your application。

 it allows you to see unit throughput and warp usage on the GPU and also gives you shader profiling information。

Some of the motivations here is like why do we care about having GPU trace right。

 well GPU trace allows you to observe workloads are running on the GPU over time， whereas。

 for example， frame debugger only shows you event indices。

And then it also lets you basically see which workloads are taking the most time and resources and where exactly in the frame they're occurring。

This way we can determine basically performance limiters。

 whether you're like math limited bandwidth limited， etc cetera， starvation bound。

 the end goal here is basically to decrease your frame or workload runtime or increase your FPS。

 right？So before we get into it， the overview of this section is first we'll talk about how to take a trace。

 then I'm going to tell you a bit about some of the important units and metrics that you should keep your eye on and what they mean。

 and then I'll do a quick overview of pixel shaders on the GPU and then we'll talk about the actual important part which is a method to actually triage workflows on the GPU it's called the peak performance percent method and then we'll go over with a case study。

And then we'll finish with like a walkthrough of the UI and features。嗯。So。Again。

 quick walkthrough of the settings I'm sure you guys can also check back on this and figure it out。

 choose the GPU trace Pror and then you can set per GPU settings most of the time it can detect what GPU you have so you don't really have to modify it。

But the section here， which is called trace settings， will allow you to basically say。

 do I want to do a manual trigger or do I want to like wait for a number of frames or wait for a number of sums？

And then real time Shar profiler， you should turn that on that usually gives you Shar information。

So very similar to frame debugger once you're ready， just press F11 and unlike the frame debugger。

 though， there will not be a draw by draw replay GPU trace is not really built off of a replay mechanism。

And then this is the view that you're going to see once you have it open it's very similar at a glance to frame debugger mostly because we added the API list。

 which was not a thing last year， but it is a thing now and we before we get into the nitty gritty。

We will talk a bit about some GPU concepts。So first of all。

GPU starvation means you're not giving enough work to the GPU latency limitation basically means it's taken the GPU a very long time to complete certain operations。

Thput limitation is basically kind of saying the unit has basically exceeded the maximum number of operations can execute at once。

So when you see latency， think time and when you see throughput， think amount。

And I have some examples here。Now metrics that you want to keep an eye on first is G active that just basically means how much of your。

 you know how much。Is your GPU basically being used your unit through put and on the GPU exactly which units are kind of performing at their maximum？

SM instruction throughput is a logical next step to unit throughput。

 which gives you a further breakdown of the SM unit's performance。

And then an even further breakdown of that is the SM Warp occupancy。

 which tells you basically on average how many warps were active on an SM at any any given moment and what kind of warps were they？

So unit here means the hardware， the individual units in the hardware。

 and we'll go through which units we actually show yeah。

And then so a quick just a really quick overview of the duration of what usually happens when your pixel shader is being executed by an SM。

 so a pixel shader or think of this as a kernel as well it's really you sort of similar at the end of the day。

 so first your SM will begin to issue instructions and your threats will start being active and when a threat requests information that is not like local to it it will go itll make a request to L1 if it's on L1 it'll make a request to L2 and if it's not there go to VRAMma global memory and at the end it will return this information back to the SM you do your computation and then your pixel gets output to the screen by the CO unit。

Now。Let's talk about the P3 method， which is the peak performance percent method。

This was developed by a dev tech his name is Louis Bba and he also works for NviIDdia he presented this at GDC in 2019。

 but I thought it was really neat and would be a very，Nice way to introduce people to how to sort of。

Optimize your workload the beginning， so you would start by looking at GPU active if it's less than 95%。

 go to NsI systems and figure out you know where you're sort of not giving enough word to the GPU。

 if it's greater than 95%， then you can start looking at top unit throughput。

If your top unit throughput is less than 60% that means this unit is not really completing a lot of operations i'm either giving it i'm either not giving it enough stuff to do or it's taking a really long time to do what it currently has and so for example if the unit is VRM you want to reduce your VM access you know。

😡，And otherwise， you should try in some way to reduce latency， increase parallelism。

If your top3 is greater than 80% and your workload is still kind of slow。

 then you know that adding more stuff to it isn't necessarily going to make it faster。

 so maybe what you can do here is essentially shift work away from this unit and maybe put it somewhere else so that that work can be completed faster by a different unit。

We will go through an example of this right now。So you guys probably know where I'm going with this。

 but as of SGraph this year， and EnSAGs officially where GPU tracece officially has CUDA support。

 which basically means we for any CUDA and graphics sort of interrupt applications。

 well show you both coUa information as well as your graphics information。UYeah。

 so that's like things like， you know， your shaders。

 things like your actual API getting executed and what time， things like that。

This is something you guys are all very familiar with or you guys should be familiar with at this point this was my flocking project from 2022 okay and so。

Here is so here's the thing as part of your project。

 you had to go from uniform to coherent sort of memory accesses， right？

This is particularly a trace that I took on debug mode。For the uniform grid with 500，000 voids。

So as you can see here。It took my coa kernel about 252 milliseconds to execute my I was having basically little to no frames per second at this point。

 right？Now， once we shifted to a coherent grid with 500，000 voids。

You can see that my kernel has gone down by a little bit， but not by very much right。

 it's now 200 milliseconds。However， when you're in release mode。

This difference becomes a lot more drastic， so the uniform grid was at about like 38 milliseconds。

Whereas my coherent rate with three milliseconds， that is a factor of like 10， more than 10。

So what exactly is happening here， we will take a look at。Sort of live right now at what happened。嗯。

So if you guys can see， I'm going to move this down， sorry。U。Sore。So this is the uniform。Oh no。

 I don't have it off on the screen， yep， there we go， there we go。Okay。

 so this is the uniform grid version。Starting from the P3 method。

 we know our GPU engine activity is greater than 95。

 so we know that you know this is reasonable to look at on NSographics。On GPU trace。Next， next。

 let's look at top level throughput。What is this， why is this the way it is。

 We are seeing a lot of L2 throughput， a lot of VM throughput。😡，But suspiciously low S throughput。

 even though we're executing this kernel right now， right， that is kind of we don't really like that。

And， furthermore。We can see that you know most of our warps active are coudo warps。

 which is very regular， very normal。Average word latency。

 this is a metric of absolute shader performance， this metric here basically tells you for this particular segment color。

It tells you on average， how long was a warp living for and in this case we're seeing that it's about 1。

2 million cycles， so a single warp。The life expectancy of a single work at this point is like 1。

2 million cycles that's kind of long。Lastly， SM Warps install the issue stage。

 this metric tells you if an SMM was unable to make warps active， why was it waiting for something。

 what was it waiting for？The top metric here is long scoreboard。

You've got about 72% or like you know， on average， a lot of warps were not really being able to be launched because it's waiting for a long scoreboard。

So we'll talk a little bit about what long scoreboard and short scoreboard is so that you guys can have a better comprehension of where this is all coming from。

So on so we have these sort of instructions that are they either fixed latency or their are variable latency instructions law scoreboard and short scoreboard instructions basically are。

Instructions that are。For short scoreboard， they are variable latency instructions so things like fixed latency instructions are things like ads and subtracts and then for variable latency instructions。

 short scoreboard refer to those that do not lead the SM。

 but long scoreboard refers to those that do lead the SM so short scoreboard are things like square roots and you know transcendentals I think and things like that。

 but long scoreboard are like texture reads and like cache reads right？

So what did we learn from looking at this？We learned mostly these three things are really important instead of executing instructions。

 we actually spend most of our time fetching data on average。

 a single warps lifespan is really high and instructions depending on data might leave the S。

So what are some possible causes right one of the first things we think about is cash thrashshing which is when your boy is reading a neighbor's position or a velocity。

 it let's say for example， it needs to go to we can see that it's trying to access L2 and VRAM right whenever a single one of these accesses happens it brings in a cache line roughly 128 bytes。

 but kind of varies depending on the unit like L1 is smaller than like L2 and things like that。

That means it brings in a chunk at a time。😡，And if you guys recall。

 at least the way that I had done it was a single Boy has this like loop logic where it loops through its neighboring boats within theoc or whatever。

 right？If your next neighbor， as we're looping through。

 if your next neighbor's data is not nearby in memory。

 this cache line is going to have to get replaced， so that means you're constantly making request a global memory and back and forth。

This leads to cash thring。Secondly， there's also think about memory latency and why random memory accesses are not very good for you。

Whi is that the memory controller just really can't predict and prefetch data， for example。

 a memory controller can do prefetching data by using hardware counters just count how many times like my thing was accessed。

 stream buffers or pre-fetch tables and things like that。

 but those are sort of implementation details。Now， now that we know those things。Yes。哦，呀。不能跑你。Sorry。

 the live view。This one。好的。Yes， so in the SM work occupancy so that is。哦对你一路化。So that saying 71%。

That。So that many works are active on VMs。But yet the rating because there's an so basically these metrics。

 the reason why I glossed over them was because they're talking about。For active Ss。How many。我了。对た。

Yeah呢个是聪。对，啊。You were showing that it was either Vam or texture。VBM L2 up here。

So is it a correct entrance to take away that？We're doing based on this graph。

 we're doing a lot more memory operations than compute operations。I believe it's a raw count。

So like for example， the percentages let me hang on。

As far as I know these percentages don't add up to 100。

 so these are like within the performance of that particular unit。

 how much it's like is it achieving its maximum， right？Does that sorry。

 does that answer the question？yeah。啊。Question吧。Okay。While for uniform。

We actually this is prior to sorting your positions and velocities by the neighbor like by proxy right because inherence incoherent you actually end up sorting them based on location so in this case I was going through the example of just like what happened before versus after you did that sorting。

Yeah， one way to think about this。you get up on the floor and then you have all communication for。

But when you're writing a custom algorithm， you're not going to know that you're going to start with uniform and then you're going to figure it out or slow and something like this is very useful for figuring out the answers to that Yes and I think your suggestion will probably improve things even further。

To be fair， it's just so happened to not be the the thing that was done in in this particular homework。

 but。Yeah。Yeah， sorry， let me go back to the presentation。

So given that you have looked at all of these things， what is the logical next step thing to do？

P line analysis of your co kernelnal。So if you were to open the shader profile， you'll see。

Or especially even right here， if you look at hotspots。

 you'll see that what hotspots shows you in a shader profiler is。

You're having a lot of samples landed on this particular line。You know， like why is that？

When you open up the shader source it'll tell you per line。

 you can think of samples as a proxy for how long something took。

 so I'll just take a really brief into but basically when you're doing profiling activities the way that we do it at NVIDdia is this thing called PC sampling and a lot of places do this their papers on this where essentially we just take a snapshot of what's happening the program counter that's on the GPU at that point and then we basically just saym at the sample my program counter was here and I take a lot of those samples at a regular interval and then at the end when I accumulate them and I attribute them to them to each line。

The number of samples you have per line is sort of a proxy for。

Perhaps your thing was actually taking a long time if PC samples where you keep landing on it， right？

So。From here you can tell that accessing this position of this position vector is taking a lot of samples like 1。

7 million samples， and so what do we do as a result。

 we arrange position of velocity such that information from boys closer together or boys that are more likely to read each other is closer in memory。

And then what is the result？Now， percentage is a lot lower。And the total samples have also decreased。

 we will see later on what that is because total samples also decreasing， like I said before。

 use that as a proxy for taking less time。And then the before and after looks like this。

This picture makes me very happy， mostly because I like pink， but if you guys were to look at。

This final result， SMm throughput is now at 83%。And L2 throughput is down to 18%。

 VM throughput is down to about 4%。U。And sorry， let me keep going。

Precisely these are the results we went from 38 milliseconds down to 2。7 milliseconds。

 Sm throughput went through a lot， V Ram throughput went down。

 L2 throughput went down avatar latency， I forgot to show that also actually， but this also。

Went from 1。2 million cycles。Down to。About 85，000 cycles。And then， oh my God， how you switching。啊。

And then。Warp stalled long scoreboard also went from 33 to about 9。2 or like 68% down to 20%。

And these are the results。Which is really awesome and really cool and I hope you guys all got to experience this when you were doing your project。

嗯。Or you can try and help yourself on your projectep。

And mean maybe just worth re emphasizing what you said earlier。

ToMake sure you're profiling the same release mode， not in debug mode。

 because while debug mode can have all of that big information， you're not。

Now that is an interesting point， I will discuss that in just a second。Now so。

Debug mode versus release mode that kind of depends on a few things。

 so I know that NviDius couta compiler when you use the regular I will I have slides at the end which tell you how to include how to change your settings so that you can actually get your couda stuff showing up actually so NviIious couta compiler which is called MVCC。

Has separate flags for compiling with debug symbols and compiling with debugs symbols that do not affect performance they have a special one and I include special one at the end so。

What you can do is you can modify your like build release with debug info so that it builds your co kernels with debug information while still while not inhibiting the the debug or like not doing any sort of。

Bad stuff to your application to actually inhibits its performance。

 so there's totally a way to go about it。Yes。Yeah， I think our projects are configured in C to do the room。

Yeah， exactly。嗯。Yeah。Now， of course， GPU profiling is it。It is not as easy as we had it here。

 it's a somewhat complicated process， people do get higher for it as an actual job and for example N VDIdia Devtech。

 they're the ones who know really well how to do this kind of thing and so whenever you have a question there' trace analysis which will then give you a performance analysis of your report and your projected percent frame gain if you were to apply those decisions down here。

Now， let's actually talk about the UI and the features and the walkthrough。

 so very similar to frame debugger you're going to have a timeline except the difference here is that now you actually get to see how long everything took。

So if you have your graphics and compute queue， those things again will show up separately。

 in this case you have compute work being done before your graphics work and you know very self explanatory。

the GR active， which we took a look at earlier， that's g duration。

 which graphics or copy engines were active， you're seeing copy engine。

 your asIN copy engine are like in charge of coamM copy and things like that。

And then top level through Po， which we looked at a little bit earlier。

This is essentially what each of them represent and yeah we use an example of how we're going to be looking at this earlier on。

 and then this is also like a breakdown of what each one of these which units these ones actually include。

AsM instruction throughput。Yeah， this is a further breakdown of the units on the SMM itself。

 so SM instruction issue stage throughput is basically just its ability to issue instructions， ALU。

 your integer math， and then FMA， your floating point。

 and then your FMA heavyav user also includes your integer multiplication dot products。

Special operations like reciprocal square roots， transcendentals。

 and the tensor pipe is like mixed precision。Type of worked。SM Warp occupancy。

 like we were saying before， basically just tells you for average， for a typical active SM。

 how many warps were actually active on it， and what types of warps were they？

You'll see that there's actually two different ones。

 there's a regular one and then there's a sampled one。

 and so the sampled one is an approximation that gives you a more detailed breakdown of the type of warps they were。

Because we are limited by the hardware to not be able to separate vertex teslation geometry wars from each other。

 but in this view we are able to。嗯。And then like we were saying before。

 aortar latency is just an absolute measurement of shade performance。Now。

 specifically what this is is like you can really only measure the average lifespan of a warp over some time。

 right， so you'll notice that these guys。For each of these little lobes。

 they're actually the same number all across， and that just represents， hey。

 there was a shader workload here and on average， how long that was a single warp living for？

And the warpps launched is just the number of warps launched。Wps issue stall。

 we also looked at this earlier and essentially， you know， like I said before。

 it is basically saying if my SM was unable to issue warps， why was it unable to issue warps。

 what was it waiting for？Yeah， this is a view of what it looks like on the timeline it's kind of big。

Now there's also metrics info， which is。Before your timeline information。

 you can see that they're all discrete values， but the metrics info is basically just an average of all of them。

 either over the frame that you've selected or like the duration you've selected or over the entire like report。

By the way， I just want to say really quick that your machine being plugged in or not does affect the duration of your frame because it does affect performance。

 so make sure that you don't forget to。Either always plug it in or always not plug it in to have any sort of comparable results。

嗯。有噶。我的S一。Front end。Ft end pipes， yeah。嗯。And very similar to the frame debugger。

 we also have an API event list， except in our event list you can see that all this command buffer corresponds to this command queue and these draws correspond to this command buffer so we kind of give you like a hierarchical view of what's going on and like going back to what I said earlier about API is being executed at the same time。

 you'll see here that this V command draw indexed one to two is lopped together and they will show up as one tag。

Instead of having two separate distinct taskss because they were happening at the same time。嗯。

Specifically， when you click on these very similar to F debugger you can it gives you like a list of all of the parameters as well。

 and there's also to some degree like a pointer to other to objects that get passed in。

 we kind of flatten them so that you can read them properly。So the real time Shaar profiler。

This is a little bit different to how we presented it on the Ephrame debugger。

So the first thing you'll notice is this thing called instruction mix。

An instruction mix basically just tells you what types of instructions took up the most of your shaders essentially。

 so for example， oh what types of instructions were here， like what pipes they lived in。

And how many samples were on it？嗯。And then hotspots gives you a per source line breakdown of which source line is taking the most time。

 essentially。The flame graph gives you， there are many， many ways to see the same thing essentially。

 so the the flame graph gives you all the shader functions in order of their execution。

And the length of each of these bars represents how many samples or like approximately how long they took。

 and each of these little subsequent bars on top are just any of the sub functionss that were invoked。

You'll see up here that there's also top down and bottom up。

 so these guys are actually function sort views where you can basically see like oh。

 this particular function took a long time， but it functions as this type of pseudoca stack where you can see where it was called from and then you can see you can see that in top down or bottom up view。

Now shader pipelines and shader objects and shader source。

 this is the comprehensive view of all of the shaders that are living in your application。

The gray ones， I believe， are the ones that we didn't detect anything for。

 didn't detect any activity for， so we don't think they're active。

And you can choose to see them in terms of a pipeline object or shader object or shader source。

 in this case it's pipeline object so you can see exactly which shaders were on whichever pipeline。嗯。

And then the shader source view， the difference here is you can't actually edit the shader here。

 but what it will give you is a source view versus an intermediate language view， so if you have coa。

I actually I should not have used that example， we actually do not take coUDA PTX。But for example。

 in Vulcan， you'll see your GLSL view and your Sve view next to it， and then you've have DX 12。

 your DX 12 and Dixel， things like that。And then finally。

You have a trace compare which allows you to basically say I before I made my optimization。

 I take a trace after I made my optimization， I take another trace and I can compare their performance and it'll give you basically the ratio and comparison of all these metrics between the two trace files。

Okay， that was a lot in conclusion we talked about the frame debugger we talked about GPU trace for frame debugger we mostly went through the render issues。

 pipeline issues， resource inspection and live Shar editing and then for GPU trace we talked about shader profiling using the P3 method to analyze the performance of GPU workflow and we also kind of did a walkthrough of the flocking project and exactly。

What that looks like when you're actually looking at it from a profiling perspective。So。

In response to me having definitely burnt out a lot of your brain cells just now。

I was definitely gapapping a lot。So I have arrived with some career advice， I really hope。

 career in general sort of life advice， I hope that will help you guys。

So and I hope that they're well represented in each of these sponggeebob square pants images。

The first one。Buildill things from scratch， that is definitely something that I say as someone who's experienced undergrad。

Probably might not apply as much to the CGGT CGGT students but definitely build things from scratch。

 figure out how to build you know your own ray tracer from the ground up with all the framework。

 things like that that will really set you apart from all of the other applicants especially those who are freshly coming out of college because I think the general Penn experience has been that a lot of the classes they give you the homework and you fill in the empty functions but what you don't know about is actually how to set up that framework and oh my God you know my windows are not popping up maybe I have to do some windows specific analysis and things like that。

Okay。Spend time with your peers and random folks and hopefully they don't hate you like Squidver does。

 which I really don't think they will。This is going to be basically unavoidable you're in CGGT。

 you're a pen， you're going to be suffering altogether and the special thing about CGGT and D&D in general is that people really like each other and want each other to succeed and so when you're spending time with your friends and doing homework together you're learning from each other and you're also sharing in a lot of your problems together so other people can learn from your mistakes you know don't worry everybody is probably just as close as you are and just as you know worried about the future as you are。

Work smart and use your tools， make sure that you live by the debugger or work like live by your tooling if there's some simple step you can take that will make her life a lot easier。

 like changing your setup or adding like a Naz to your you know visual studio so you can analyze it so you can look at a variable more easily。

 definitely do that。In the long run， this will decrease so much of your work time。Nche knowledge。

 this one is about knowing how to do things that other people don't know how to do or going the extra step that most people wouldn't go the extra step for I saw this oh actually all of these I saw these from my fellow CGDT and DMD students。

And so， for example， there were students who were you know building their own path tracers。

 but not just building their own path tracers， they're building from scratch， they're polishing it。

 they're making it available and open source for people to use。

 and they're basically taking the next step to do things that other people would not do， you know。

 and that really also sets them apart。It's that realist expectations maybe don't like not move like the rock but the job market is very much a lot。

 a lot of the times really really good candidates will get rejected for various menial reasons or another you can't possibly do everything so don't expect yourself to do everything。

Speed of light， given what you have， what is the best that you can do， right？And then lastly。

 there's no such thing as wasted time when it comes to learning one of the things I really struggled with in undergrad and trying to live like a human in grad school was essentially that I felt like any sort of going back to using tools。

 I was like oh no， but it'll take time for me to learn how to use tools or it'll take time for me to figure out where exactly my problem lies。

But the truth is there is no wasted timere when it comes to learning something。

 it will always come back eventually to serve you in some way， that's kind of my experience。And I。

 yeah， I hope that these things resonate with you and that they're at least entertaining to look at。

Um yeah， thanks， I know I really sp through that， but thanks good luck and well touch Vulcan grass。

 which is a it is aum maybe a homework for this year， it was a homework。Yeah。

Such's a problem I'm sure students have a lot of things take questions about both what we spoke about in terms of the safety Bar and praise。

 but also on clear advice and these experience interviewing， working at T Whitia。



![](img/496db206779fbd8c3e4f6920c270de8a_13.png)

Or anything that didnt have on。走没事的位。Yes。Hi， Matt。This is a career oriented question I'm just curious like how you decided that you wanted to for it in videodia。

 also where where。Oh， okay， so they let me work remotely from Philly。

But the reason why they did that was mostly because my team is in Europe， most of them。And。Yeah。

 that's where I'm currently located， that's why I'm here， you know。

 things are pretty easy to coordinate once you're here。

With respect to when I decided I wanted to join a video。So I decided， I think in'm a junior year。No。

 yeah， pretty much by my junior of college that I was interested in this。

 and this was kind of before or very much like a little bit before the AI boom of it。

And I think that basically what I thought was， well， what is something that。

What is something that I think？Very few people can really do what makes a really good engineer like because maybe at the end of the day that's all I really want right and I was like based on my current situation in my current peers。

 I don't see a lot of people going in to do graphics hardware or graphics like API related things。

 most people in my year for some reason that year they decided to many of them sold out to big tech and I guess in the case in a sense of the word so of I but for example。

 previously you know people went to they work for Pixar they work for game studios。

 but in my year not so much。And I think that I was like。

 if one day I decided I wanted to pivot and do something else。

It will probably still happen at NVIDdia because NviIDIdia does all of the graphic stuff that I can probably think of。

Doing。And when I first interned for them， I was on the Linux reteer team and I did like Linux graphics drivers。

 that was very， very hard。嗯。And then that was also when the higher freeze happened。

 so then afterwards I ended up getting hired by the  developer toolsol team instead。

 and now I'm very happy because everybody I work with is super super knowledgeable and they're very。

 very happy to share and it really makes you think very hard and deep about everything that you're doing and the quality of your own work which is at the end of the day you know fulfills all my goals so I guess my judgment of them was correct。

Does that answer the question， thanks？It may be inified to as a follow of question。

Were there any specific questions you asked during your interviews to help with that judgment Oh right okay。

 so remember the whole spent time with your peers and random folks。

Something that I did before my interviews was like if they told you who your interviewer was。

 I looked them up on LinkedIn。And I kind of like stocked them a little bit。

 so that's how I found out that my current manager wrote the original perforce library。

 which okay let me go into that really quick， so PerFs is the hardware like the hardware counter library that all of our tools are built off of。

It's also being used by Microsoft Pics and it's many。Many， many things well。Maybe not many。

 but like multiple things are are using it so then。

And then that's how I also found out that my tech lead was at Intel for like。A very。

 very long time and had patent with Intel。and then that's how I was like oh， yeah， okay。

 that's interesting so given once you know a little bit about that person's background to kind of have a sense of what they know and what they don't know and what they will probably ask you。

And so， yeah。Yeah。Deep I can add for that， just as kind of your advice and。

All of you would be interviewed， right？If the HRRO whoever is shadowcheduling your interviewer doesn't tell you who you're interviewing with and what the structure of the interview is。

 please ask it's like if you don't ask and you don't know who you're meeting with。

 it's like going into a boss panel in your favorite game and you have no idea what s you want to use right so it's a keen important deep set fantastically like roll with them up on LinkedIn if they have a website check out that。

Even even if that doesn't tell you anything about what they are going to ask。

 it'll give you person view what to ask to them about their career and what they're doing in their current role。

There are some cases where at least I found this to be true now is that a lot of the employers actually have stopped updating their LinkedIn and now they don't have a picture。

 they don't even say anything， they just sayS aVI， and that's it。And then it becomes kind of hard。嗯。

Yeah。不确嗯。Hey yeah， maybe a bit of a silly question。

 but what's your favorite feature that you've worked on？

I've worked on quite a few things at this point。嗯。Let me think about them。

So one of the big things I made the ator btency metric， and that is a metric that is not。

While the thing is okay， some of our metrics are synthesized and some of our metrics directly come from hardware。

 so the ones that directly come from hardware come from Perworks。But in addition to those。

 because of hardware limitations， we can't exactly schedule every metric we want because。

We have hardware performance monitors that are built into the GPU itself。

And we can't really exactly we need to work around it， so what we do is we synthesize metrics。

 and so I made the aort work latency synthesis fake well， not fake， but like approximation metric。

That was actually one of the first things I worked on， maybe like a month into me starting working。

And。I also worked a little bit on the coUa support as well。

 where I was mostly in charge of collecting the shader code for the couda from the driver。

Fcoded from the driver yeah those were fun I worked on some other not so fun but really really like involved stuff。

 so for example things like for example when you collect metrics you need to know how much space it's going to take that kind of stuff and then reworking a lot of the logic there so。

嗯。I don't know if I should have said that， but yeah。If I can ask a similar question。

 what would you say of the feature that？Surprisingly。

 got used a lot more than you thought would a Pla。Yeah， I was like， h， I feel like， feel like。

I feel like it would be maybe some time and I need to refine it before it's like used morebi a devtexs already using it。

嗯。And。Yeah， and it's still sort of a work in progress on my end。Actually now they think about it。

 but yeah， but I think that that goes to an important thing in industry that as engineers we want everything to be perfect right we want everything to be pixel it perfect in the way we render。

 but a lot of times。That perfect can be then good enough you want to you want to ship software you want to get it in the head of like said and get that feedback and then you know what direction you want to go and as you mean what the direction is and trying to go too far and then not shipping the software Yeah definitely for sure like I battled well with like perfectionism but like you really just got to get the stuff out there and then fix it later well maybe not like that but like get your stuff out there get your manager to approve it that kind of stuff and something else I worked on was like having NGX Shar Shar support which is like。

In videos like internal SDKs and things like that， so for example DLSS is an example and getting that to be supported through En graphics and GPU trace。

嗯。Yeah， now I have to do a bunch more synthesized metrics。Yeah， all really fun。

 really interesting work that really。Challenges your understanding of the GPU for sure。Yeah。吃。Oh。

So you talk a bit about。Since you have taken on projects from like building page strategies and tools that are out there。

哎，重新。Describe。Yeah。这一块。嗯mhm。😊，ok。So for example。I'll be someone nondescript about this in the work setting。

usually have to write a design doc which many people don't like， but for example。

 one of the things I have to do now。What I did was I wrote the design doc for it and I guess it was lucky because we had some guidelines for what you had to fill out and that forces you to do like a bunch of research。

 right？嗯。In the initial research stage， definitely do your research well。

 that's like I call that like the triage or like the probing of like what I can do and what I probably can't do。

And then once you have done that initial triage， you basically come up with a list of things that you think you're going to need to do for you to get there。

 you don't have to know exactly what each of the steps are， but even from a mental perspective。

 knowing that I am here and I have to get here is already a pretty good like first step and so what I do is then I write like okay。

 here's what all of the individual steps I need to do to get there。Now。

 which steps can I do first and that I sort the list， I also do like a number of days estimation。

 then I sort the list for what can be done first and what can be sent off a review first。

How I can break down these things into smaller reviews so that。

 you know I introduce them in a non invasive way to the code base。And。Pretty much once you have that。

 you have like a game plan， you have an idea of how long things are going to take for you to do。

That's how I would， the first step I would do for a big project in a work sense。嗯。At this point。

 my dev environment is already pretty like。Like it was pretty set up at this point。

But if there isn't。Then you're going to have to spend some time on the research on that as well。

 but yeah。Yes thank you。对。Yes， I wanted know a some thoughts that I wanted to share like。

 I love your passion。 there's so much information by the way you delivered it made you want to appear more good。

 excellent。😊，Yes， I hadn't。I yeah， and it definitely really helps to have your coworkers also be sort of similar that they're also all really。

 really into this and they。Like spend a lot of time， they're very good at what they do。

 they love it and they care for it you。Yes， another oriented question so imposter syndrome is very common in this field。

 I was just wondering if you feel comfortable speaking to this like how you felt coming into your job versus now in terms of。

like whether you feel comfortable now， what what the curve is like， Yeah， well， okay。

 this might be kind of， I guess kind of weird， but so。嗯。My company is mostly guys and so。Coming in。

 it was definitelyhan like I definitely felt like I had to prove myself and I really felt like why I don't think I know anything to some degree。

 I still don't think I do， but。Um， what I will say is like what I ended up doing was like， okay。

 I know I'm going to feel this way， how am I going to mitigate this and especially coming out of school。

I didn't have a very good way of like sorting out my mental。

Like stress and having that like it not being the way of my work。

So what I did was like I came up with like a first three month or first six month plan of how I was going to approach everything and I was essentially like whatever they throw out me。

 I'm going to get results first， I don't really care how I do it but I'm going to get results first and then I can figure out what is the proper way to do it after by getting code reviewed and getting advice and things like that learn I have to learn my environment well enough so I can ask questions。

But getting results first will set up a lot of confidence， especially that your team has for you。

 so like your team is not gonna know what you know the nitty grities of what you do every day。

 but they will see oh this guy has like you know pictures being sent into the group chat and things like that he has results and he he is figuring out how to do them right having that like confidence from your team also is really important so having initial successes I would say at least what I did was focused on getting results first unless getting bogged down in the details。

Of whether that was it's the right way to approach things， right？

And then you'll and then you'll hit so you'll have like a really good beginning and then you'll plateau down to basically。

 oh no， now I have a million comments on my code reviews and I have like， you know my you know。

 maybe my tech lead says， oh， this was not the right way to do things I feel terrible about you know my inability to perform and things like that。

 you're going be in that least for a little bit or at least I was。😡。

And then that's where like now you have the confidence to say， okay。

 I have done this crazy driver stuff， I've done this stuff。

 I have the confidence in myself to figure out step by step。The next。

 what would be the who to talk to， how to learn what the next steps are。

And then you kind of slowly just start picking yourself up from there。

 and then you'll get back up again to actually where having like a stable sort of procedure for everything you do。

Actually having knowing stuff in your team that maybe other people don't know anything about and then becoming like a designated person for something。

 the process is a bit like this I found for me， so I think。I still definitely have Ha， really。

 really bad impothra syndrome。But I think that you also reach a point in your year。

Where you're just like， I'm tired of being this way。

And you start to separate like your brain starts separating。

How do I feel about myself versus what do I have to do from here just to keep going？Yeah。

 I' can after that so watch syndromedro， I think is a very fashion topic for me。

 but I still it right。Let's be honest， Like every day I learn new things。 I feel like。

 or should I be in this， I work with some really smart people， and I'm telling them what to do。

 Does it look always feel right。So imposter syndrome is it real。

 it's more about how you deal with it rather than how you get over it because you get over it once。

 you get promoted anything in your new role and your learn。

So I think I think what these you said towards the end is absolutely true the curve is absolutely a snake because it's an knock and downhi。

The the important thing to remember is that。Your value。To any company or even in personal life。

It's almost never judged by a single moment， never judge single failure or a single success。

And getting compliments from your manager or your manager's manager feels great， right？嗯。

Getting a bad review on your prayer request and 1 thousand comments feels bad。

That's how humans have being programmed is to understand how other people feel about us。

The real difficulty and how you should think about this is。How do you not met either of those F？

Those are comments about your work， not about you。Right your passions， your values。

 who you are is completely separate from your word， don't allow your words to define who you are。

And it's not easy， it's extremely difficult， but the more you practice that。

 the more you understand that hey， just because I made one bag request。

 my company are' going to find me。Pretty much every company in the world。

Things that itll take you about two years to actually be productive at the company。

The amount they invest in you in learning， they're almost not going to see a return on that for about two years and then youll start growing。

It's okay to take risks， it's okay to ask questions， don't be shy， reach out， ask for help。

 it's not a bad thing to look stupid。Don't be reckless。Right be smart。

 do your homework and then co health you want to be respectful of other people's time in that don't just knock on somebody's door every five minutes。

 do your homework， do your prep be like hey here's what I did here the results here's the problem are you able to have and that't get you a long way going forward so imposter syndrome will never go ahead but learn how to how you want to be。

Work very well spoken and you seem like know what you're talking about Yeah。

 I was going to say you should start writing a book program。Well， I'm on the Discord。

 you guys can hit me up whenever you want so and I'm in Philly。There's that also， oh。

 I forgot something I was going to say and now I don't remember what it was。啊。

I guess I don't remember， sorry。我没。Yes。Is there anything。

Any niche knowledge before you get hired you。Wellow。I honestly don't。Okay。

 I don't remember what it was before， but I do remember what I would recommend。Well， for my job。

 at least， generally what I think for developer tools。

 what they tend to look for is like driver knowledge。Driver operating systems， computer architecture。

Graics APIs like Direct X 12 in Vulcan。嗯。So for example， actually， okay。

 I had an intern this summer and she was very， very young and very very new。

 So I think like some of the things， for example like。

Some of the things that I saw that we were that the engineers on my team had to take into consideration every day were things that she didn't really know about。

 right， so for example。implementation details of standard string and then like she you know she was like why do we use why do you prefer the use of a switch statement over if statements here and I was like well let's talk about the compiler details of this how does a compiler write this and then this is going to give you motivate certain like good coding practices that we have and things like that so like if you're suddenly seized by like a desire to learn about compilers where a desire to learn about like operating systems just do it like the internet is full of resources some good some bad but the internet I think the biggest step the biggest issue here is just to。

Like， don't。don't get in your own head about learning， take things at your own pace like I said。

 like the time you put into learning is never wasted time and have fun with it it's supposed to be fun yeah those things that I listed just now。

So I like to think to what you said， but great answer one clearly that's specific to D the roles you get will be when different so the best thing you can do is ask your whoever you're interviewing with the tech leader manager a question like how can I actually my onboarding if I were to join or what are the skills that that you find in successful developers in this role so those kind of questions will give you enough  tibits of things you want to explore？

The other thing I'll say is as somebody who's onboarded probably 50 developers at this point。

We don't assume that you'll have those steps。Even if you're learning it before you join。

 well make sure that you have those of knowing it beforehand will give your leg up。

 but even if you don't you graduate， you want to take a vacation hiking Ma Fuji do it right when you start your work。

 there'll be enough resources to help you get on board。

Then youre like to you have a question what were the things that you get in school and outside of school that kind of make you feel prepared for your job and getting。

Hello。Iically， I feel like。I feel like there were definitely way more qualified candidates than me even in my class。

 but like definitely GPU class helped me a lot， actually with regards to having projects that stand out that you can just readily share especially with performance analysis Tibits because at least in my interview they asked about it and I was like heres a great section that I already wrote that I can refer to。

asideside from that， I honestly feel like it was pretty unremarkable in other ways。

 I was president of upgrade which is the game developing club here at the time well't know the year before but。

I think that。At least what I feel like the benefit of that was was like project scoping abilities and ability to know what's viable and what's not viable。

I think with regards to things that。That I think as someone on the other side of recruiting has heard。

Entrepreneurial being entrepreneurial is something that's kind of that is kind of nice like we said。

 ability to build things from scratch， so if you really like games and you're a mater。

You know or if you're if like we said like taking initiative to do something new and that hasn't really been done before for you or something like deciding hey。

 I want to learn about this so I just learned it right that's also pretty nice what I say I do outside of。

Oh， okay， here's something that's kind of interesting。

 I have a tendency to just talk to people sometimes。 So for example。

When I went to visit the video headquarters I。Bumped into Rev again。

 and I had a chat with Rev and he introduced me to some people on Omniverse RTX。

Oh yeah Rev Rev is the VP of Omniverse and he used to do guest lectures or at least he did one in my year and then when I joined I messaged him I was like。

 hey revv like I'm coming to visit HQ do you want to have a coffee I don't wantan to take up too much of your time I'll just come and say hi。

And so that's how that happened。And I also randomly reached out to Jim Fan who is also。

 he is an AI researcher at NviIDIdia， he does embodied agents， and I was like， also， hey。

 do you want to have coffee and then we did。So a lot of the times people might ignore you。

 they might not。But if you don't reach， you know， you can just talk to people and say， hi。

 especially if you know like what they did， that will definitely help you。

For job searching also especially and and I swear I didn't talk to you about all the reading tips and stuff I showed you kids last week that all one point if I can add one pit there B。

Be good at explaining the decisions you made。 Yes， like if I asked you。

 why did you work on a feature， don't say， oh， I thought it was cool， right。

 like that that doesn't give me anything。 being like， hey。

 I wanted to take my project in this direction。 I research X， Y， Z ideas。

 I thought this one was cool。 I spoke it out。 And here what I did。 That's a much better answer。

 And it's okay to also talk about bad decision you made being like， hey。

 I made this decision with this information in my。When I found out X， Y， Z。

 I changed and I totally open to say that that shows that you're flexible and you're open to new information。

Other questions。You're getting way more questions than I get。Sard one， scored plus。系 ok  hi。😊，有啊。

系明白嘅。啊，就说呢。Carley， I was going to ask some， but like， yeah。

 like does ZV have just like picture I wasn't stop on？They do， but it's very scarce。

Or I think it's pretty scarce， so Louis has his recording from GDC 2019 where he talks about the P3 method。

U， but because that wasn't really， they use samples that of course you guys don't really know about。

 it would be very hard from outsider's perspective to understand the triage workflow。Actually。

 but you can you can still watch it like it's fine。

 he also runs a blog that has a lot of like performance analysis methods。

 but some of the blog posts are a little old to use older versions of the tool。😊。

And then we do every time we do a release， we highlight features。

 but we don't really go into depth on。How to use them？So usually what people do is they go to SGRAff。

 they attend the Ns lab sessions。And they don't really I don't know if they record those。Yeah。

 that's。That's kind of also why this tu so long to put together。

 but yes here the9 you have to stand out pay the tools and write your own documentation and make it public that too。

Just how was your day how was my day， thank you for asking。嗯。What did I do today？Oh， yeah， okay。i。

Well， I tend to wake up early for work because my teammates are mostly in Europe。

 so I usually start working by seven。And then that means I can just end early and it's great and it's fun。

But I was kind of nervous so I didn't actually do very effective work for like the latter half of the day today and then I came here with Leonard。

 we just walked here and then met up with professor and now I'm here and talking to all of you guys so。

佢 one last。系系。Whatマ you。My favorite thing about the GPU。courseOh the course。

 okay good good clarification， thanks。W。Kind of similar to your question earlier。Before I came in。

 I had really no real idea what happened with the GPU， okay， I basically had zero knowledge。😡。

And I think that as a result of class and as a result of working。For a while now。

 I so you were asking about imposter syndrome， how I felt when I first entered and how I feel about it now。

Well， it was very bad then and it's slightly less bad now。So going to a question about。

The class itself。I love that it really gave me sort of my first way of learning my first real touch to GPU hardware and as a class I definitely feel like is very unique and unlike anything else that Penn offers maybe except。

Like operating systems and then my favorite thing was I remember。

Looking at parallel algorithms when you were teaching them。

And all the and then the different sorting algorithms and like the diagram of all of them step by step。

 and I was like mesmerized by， I was like， oh my goodness。

 this is like so different from you really have to rethink everything， most things。

That you would know from taking a typical data structures and algorithms class on the when you have parallelism in play。

 everything changes and then it becomes this like insane like like map of things and I just remember that being very very standing out to me a lot I did that on Monday Oh yeah have nightmare and yourre saying yeah oh that was beautiful I was like look at that like that is that is that's what that's for。

Yeah， I don't know， maybe a little insane behavior but yeah。Let'sI down hill from here， yeah。

But no no the Pa trace will be a lot of fun， I've heard a lot of work is being done on that and。

Oh yeah， I had dreamss about the Pa tracer that one for sure。系。啊，哎。

I that like when you decided to be like you wanted to going into this group because like people other people in your ear weren really going in that was the most successful I was wondering like。

But what did you like realize you were more interested in doing like lower level stuff the I don't know。

 more artistic or like higher level like things that are not maybe necessarily with hardware and like。

What was it before you took this class like OS or it was before。

 but it wasn't that much before it was because the summer before I took this class I was interning for。

 you know， the Linux graphicics drivers team。And I think before that。

 I didn't really have really much of a clue heading in。

 I just sort of knew vaguely the direction because I knew what people were doing what they were not doing so like。

I will， I will say though。I feel like Penn's curriculum seems to tee in between this kind of like really hard like hardware based or like algorithms based。

You know that you get with like 461 and you get with like461，0 and you get with。

Like computeruter animation。And also you get with procedural graphics。

 you teeter along the edge of that with like other classes and it seems like it really doesn't seem to lean one way or the other。

 so for example，I just don't think Penn had a very good infrastructure to do technical art type of classes。

At least when I was deciding at the time and so I think that because that was really kind of lacking。

I didn't really see a way to go in that direction anyways， but I also think that。

I think that the state of film。Or the state of like a lot of current day animations， oh my god。

 is this going to be controversial？I don't know， I don't know if I love like the the stuff that's being put out these days by big animation studios anymore。

And I think that if I wanted to do the artistic side of things。

 I just want to do just that and I wanted to keep that a bit separate from。From this。

And I think I just didn't do very well my brain， for some reason just didn't like the idea of this technical art mixture of things。

But I can't really explain to you why。Um，Its in my mind， I was like， oh。

I was thinking about Coalline， you know， Coalline is pretty much mostly just like claim well not clayation。

 but like animation， like physical animation。Yeah， I liked that， but this is， to me feels different。

I'm so sorry， take you so much time，因咩。So oh yeah， I see Logan in the back there， you know。

 hello Logan， when I was talking about directors 12， I was thinking Logan。Yeah。好。我个看。都ll。

Which spongeebob are you today？すご。All right。All right， let's thank you once again thanks for coming。

Its a lot of time， yeah。Let's take a break， let's take a slightly longer break maybe 10 minutes or so。

 and then when you come back we'll do the rest with Han for project2。

And that's going be a very different project。 Well all numbers are no doubt。

 So it'll be a fantastic time using these tools that。H， right。哎我。你。

