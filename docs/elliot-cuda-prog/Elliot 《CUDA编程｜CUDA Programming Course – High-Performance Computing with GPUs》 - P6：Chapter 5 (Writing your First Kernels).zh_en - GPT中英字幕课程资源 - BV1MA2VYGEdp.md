# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P6：Chapter 5 (Writing your First Kernels).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

Okay， so now things are going to get a little more technical。

 but I figured we would kind of enter smoothly by just doing a fun and useful activity。

 So I pulled up a bunch of Wikipedia articles on various GPU architectures and we're going to dive into what does your GPU actually look like Like what what are the stats of that。

So just like looking at these in general， let's， you know。

 we're just looking for things that are like useful to know some maybe some little history。

 kind of like the intro to GPU section that we previously did。

So like Pascal was an older one that we used to have。

 there's a bunch of cool stuff about this so like the 1080 and the 1070 were both based off Pascal you know you have a bunch of information about you know where it's from all of this but what's really cool is if we scroll down you have all the technical details on these things it's crazy how much Wikipedia has。

But yeah， like you， we have these tables。That will。That will essentially tell us like which。

 which generation， which generations had what。 So like。No。Texture cast per S M。

 which we'll go into later。Dedicated shared memory per SM or streaming multi processor。

 L2 cache per chip right， So you have all these statistics。

 and you can sort of compare these over time。 So if we jump up to M here。

 which is actually what my GPU， My R T X 3070 is based off of。You scroll down， and。呃。

You get the same thing， right， So like L2 cash。And then L2 catch So like 512 kiloBs。

 And then this one is。40 megabytes， right？You get some interesting comparisons here， but。Yeah， these。

 this is just kind of the stuff you want to be looking at when it comes to like GPU specs。

 especially if you don't have one， right， you're going to find a lot of useful information here。

You know， going to am here， like you have these A100s that have been used to train very big models and that's it's amPre 100。

 right， that's that's what it's called。So。Bunical statistics。

 which different precisions and data types do they support SoL？比诶。Like for example， Volta。

Vta supports。Vulta doesn't support Braf 16， but a 100 does support Braf 16。

 So interesting stuff like that， which you can sort of just do a side comparison of ate a lovelace。

 This microarchure is what is used in the 40 series cards。 So amp Pire is like the 30 series。

I believe if we actually go to Volta architecture。Volta micro architectureitecture。

I believe this is used in the 20 series cards。The20， it's gonna be somewhere。Okay， maybe not。Anyways。

T。You can find a bunch of cool statistics on these8 levellaces， the 40 series cards。

 You get a bunch of info on that， like the the L2 cache。

 It's again bigger instead of 40 mebytes around here。 it's 96， which is great。

 L1 cache is actually what matters more。 So you know， 18 mebys and so forth。😊，And then Hopper。

 which is actually what the state of the art GPUs right now or closest state of the art is。Well。

 the state of the art is actually the blackwell microarchitecture。

 but the Hopper is like also very like a second most recent one and these are what the H100s are based on these are used to train models like GT4 etc so you can you find a bunch of statistics on those without actually going and using one。

But if we actually want to print some stuff about our GPU。

 we'm just going to open a new terminal tab here。I'm going to drag this to the side。

If we pop over to。Cut the samples， you。

![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_1.png)

This gonna print some stuff about your GPU。So。If we take this and we just just get on it。

It's going to take a second to do that， but we can scroll down in the meantime and we can see if you're on Linux。

 you would essentially Cd into your whatever director you desire and then and then make to actually make the binaries for running stuff with it。

 So if we print this out here， let me actually make this。Bit bigger。嗯。We can seed into ha samples。

 and then inside of here， we have samples。 So we go into our sample directory as seen there。

 So Cd into samples。And then， we have。We have a bunch of different ones。

 So there's things you can experiment with here。 I don't know how how easy these are to use。

 I haven't played with them yet， but we're going to see them into utilities。

And notice how we have this device query thing here。 So this is actually going to turn into a。

We can't execute that yet， but if we make。Then we actually can。

 and we can see a bunch of details about our GPU。So I recommend you to do this on your own system。

 but。One co capable device， so there's one GPU plugged in my motherboard。 that GPU is the G4 RTX 370。

The couda driver version is 12。5 as well as the runtime version， Kuda capability。

 So this is actually very important。 This 8。6 here。 yours is it might be different。

 You might have the same GPU you might not but this 8。

6 is actually very critical in how we and how we know like what is supported on our GPU So there might be some operations that work and there might be some that aren't。

 So if I just drag this over to the side here。 we don't need to worry about the rest of this as of right now。

 maybe some maybe some of this later， but Ill I'll just give you that information so。If we go to the。

去的。capabilityability。Compute capability。嗯。What's it call。Sure， cheap horse products。嗯。See 8。6。

 just like that。

![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_3.png)

I have to go back to the Kuda docs to actually get useful stuff about this。Good the docs。

So if we go to the。Kuta C， I'll just sure。 we'll do Kuta C plus plus。嗯。No。

 we're not gonna to do K to C++。We're going to go down to。Could us see。Cud see programming guide。

And inside of the Kesy programming guide， yes。Aerability。So like this， for example。

 this is what I'm looking for。 So thread block clusters in in2， and then you go to 2。2。

1 is thread block clusters。You only get these if you have a compute capability 9。0 or higher。

 So the higher the compute capability， the better so。

I cannot actually use thread blocklock clusters on mine because the architecture doesn't support it。

 So these are critical things you're going to watch out for。 And you know， as you。

 you might actually be able to take advantage of some features that someone else can't。

 Like if you have an A 100 and someone else has a V 100。

 you can actually do things that they can and you can do things faster and more efficiently because of things that the architecture actually supports。

 So these are these are things you're going to watch out for。But anyways， with that being said。

 we can actually jump into some stuff about the just essentially how does the Kuda architecture work。

 how do we write code and how does that whole thing fit together？



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_5.png)

So now we can actually get really into what couta is doing and the whole hierarchy of that。

 So inside of here I've pulled up chapter 5 writing your own kernels and then Kuta basics and then just to read me and the ID Xing or indexing file。

 So if you do， I believe control shift V on this or control。Control， I don't know what key it is。

 Control Al be。Control shift fee。 There we go， okay。And then we pull up this one on the side here。

 just just for reference。Let's go through this cut sort of hand in hand。So。Im zoom in。

We just printed this out。 We just printed out device query。 So we don't need to really cover that。

 But when it comes to。Sort of the more easy stuff to get a grasp on。

 I mean we already went over this， so you have the host。

 which is the CPU and uses those Ramticks on your motherboard。

 and then the device or the GPU uses the on chip fee Ram or video memory for desktop PC。第。

The surface level runtime。Typically goes。You you define some input on the host or the CPUU。

 which you then later want to run on the GPU， but first you have to actually define it on the whole system memory。

 and then you would copy that over to GPU memory。嗯。And then， you would。

And then you would execute using that on GPU memory。

 you would execute you would launch a couda kernel and that ka kernel would use that GPU memory and do stuff with it and maybe do some useful computation and then once that's done。

 you would ensure everything is all synchronized up like nothing is nothing is still waiting you would synchronize everything and then you would transfer it back to CPU so that or the host so that you can print it out or do something useful with it。

 This is typically how the runtime goes and you'll see this in our later chapters。嗯。

The naming scheme， like how we actually what we actually name our pieces of data is quite critical。

 So typically what you'll do is you go host or H and then underscore whatever the variable name is。

 So if it's like matrix A you do H underscore matrix A that means it's defined on the host。

 So you're going to do your Malik your C Malic with this。

 and then you're going to do a coupa me copy， which we will see later in a second and that's where you take this host and you essentially transfer it over to this other to this other variable device So device a that's the GPU version of that。

 So it's just exists on two different pieces of memory。嗯。

And this is just for the set variable name A。 Now we have this global。

 which you might have seen already。 this is visible globally， and this is very broad。

 this is typically what a kernel is going to look like unless you are calling say a separate calling a separate kernel inside of another one you would use。

 say device， but in this example， we'll just stick with global。

 you you can read a little bit more into this if you want。

 but we're going to use global for the most part， device we might see that later in the course。

And then host is only going to run on CPU。 So don't don't really worry about that。

 it's it's kind of just telling Ka that you're going to run on on the CPU。

 but you you may not actually need to because you're just going to use， you know。

 like the void instead of instead of global void， right。Now， this， this kudaic term。

Memory allocation on the GP V Ram。 So that's the global memory on the GPU itself。So。In this example。

 you do define a bunch of a bunch of。Essential， essentially as。 So a pointer to a device。

 a float array， which is a pointer。On the device。And it's for A， and then the same thing for B and C。

May you do。Kutta Malik， meaning you allocate it on the GPU。 So you do the memory address for that。

 So you put in the memory address for this thing。嗯。

And then you go essentially whatever the you know let's just say you have a size defined above right like maybe it's like a matrix。

 for example， and it's size it's like a you know square matrix size n by n and all you're going to do is say you know we want to allocate this much memory this memory address and that's just going to be a square matrix of let's say you know 128 times 128 times the size of whatever a float is So in that case I think it'll be4 because a float is4 bytes where each byte is 8 bits you have a floating 。

32 number do the math and then you end up with the total amount of bytes that she will need to allocate for this device a matrix and so on through B and C as well。

Now Kud mem copy can copy from both device to host。

 host to device or device to device for edge cases so。You know， you would。

 you would slide a little term in here， K M copy host2 device or coM copy device to host。

 and that's that's how that would go。 we're actually going to see usage of this in a second here but。

Understanding Q to M copy is just to just going copy things around and then coa free is obviously just going free memory up on the device。

 So when you're done with something or you don't need it anymore just you know free that up if it's a big it's a big you know if it's just like an integer or whatever like just a float like a float a equals one or something。

s like you don't need to free that but if it's a big array like this。

 you're gonna to need to free that。Now。The N VCC compiler is something we'll dig into maybe a little more in the future。

 But this is all you really need to know。 So the host code is essentially the these。

NVCC will compile all of this down into something that the GPU can actually execute。

 but the CPU is going to run it。 So CPU is going to interpret what that is saying and it's going to launch things and tell the GPU to do things。

 It's not just going to compile directly down to GPU， right。

So when it needs to run on GPU when it actually needs those instructions as to what to do。

 it's going to get compiled them to PTX， which is parallel threat execution instruction so that's like the GPU equivalent of X86 or assembly you know as it is for CPUU or host and then it's further going to compile that down to shader assembly。

 which we're not going to worry about。And this is just and this is stable across all of the different NviDdia GPUs so you don't need to worry about that and then just in time is just a type of compilation so。

Kuta hierarchy。 Yes， this is， this is where things start to get a little bit intuitive， so。

Imagine you have like imagine you have this giant 3D。

 like a cubic volume and inside this volume is called a grid right inside of this grid。

 you're going to have a bunch of these smaller cube cubic volumes。 Those are called blocks。

And those blocks or organize， you know you can make them whatever size you want it's just like essentially can think of it like like a prism or something and you have a bunch of these organized in this giant 3D volume which is the grid and those individual blocks have things inside of them called threads and those threads are going to do your math operations for you so there's a lot to impactpack here but the individual threads can communicate inside of these blocks and that's an important part to remember for later when we're optimizing stuff。

But essentially， the reason why we have all these different pieces inside of this massive grid is so that we can get the parallelism of GPus。

 So when you have this block doing this， you know， doing this piece of the puzzle and then this doing another piece of the puzzle。

 and they all kind of do their part。 And at the end。

 if they all do their part successfully and they're all like synchronized。

 and you make sure that everything works correctly。You know。

 it's better than having a single CPU thread going through each individual thing in that problem and doing it one by one。

Or as you have like a bunch of these blocks or these threads inside of blocks。Which are doing， know。

 little independent operations。 It's doing a smaller number of operations。

 and they have a lower clock speed。 But they it's going to solve the problem much quicker because it's in parallel。

So that's the whole idea here is you have this 3D volume called a grid inside of it。

 you have have these other 3D sort of cubes or rectangles， whatever。

 and inside of those you have threads and those threads are going to also do things。So。

I need to breathe， but。We'll go into some more technical terms in a second here。

 So going into these technical terms， we can see this grid dim exists here in our kernel。

 in our global kernel。We have a block I X， which is， you know， these， these three and。

Block dim exists here and here and here and here and here。 right， you have all these。

 and then thread I D X。 So this grid dim is the number of blocks in the grid at， you know， say。

 like a grid dim dot。X is going to be in this， in this volumetric grid。

What is the x dimension of that？ So like， what is the length And then grid dim dot y is going to be like。

 what is the height And then maybe grid dimm dot Z is going to be the depth of that， right。

And then the block IDX is going to， it's not actually about the block itself， but like where is it。

 Where is the block within the grid so。The grid dim is like how long is it。

 what is the size of the grid itself that is run on the GPU。

 and then the block IDX is where each individual block。

 so a block will have a block IDX in both the maybe X， y， and Z dimension。

 and that'll be essentially its coordinates within that grid。

And then the block dim is how big that block is。gridrid fits a bunch of blocks into it。

 A block fits a bunch of threads into it。 So the block dimm is like how。

 how big is this like smaller cube or this or this rectangular prism。嗯。

the thread ID X is like which which thread is it within that block。

 So you can see how this like spatial hierarchy goes down。

 you have this 3D in the grid and then this 3D in the block。

 So it's like kind of 60 if you think about it that way。

 I don't want I don't want that to be intimidating though like six dimensional。

 I don't want that to be intimidating。 It's just kind of how thes it's an efficient way of running things in parallel and a way of visualizing it as like a software abstraction right's that's the idea there。

嗯。And then。Threads like， I mean， I assume that this kind of this spatial idea sort of makes sense now。

 So now we can go into like why this works。 and sort of like the more nittygri of that。

 So each thread itself has local memory on it。 So registers。

 which are very fast and is private to that individual thread。 So， for example。

 if you wanted to add a and B， where it's like 1，2，3， and then all the way up to n。

 which is like length。 And then 2，4，6， So counting by ones， and then count B is counting by twos。

 each thread would do a single add， So like thread at index， say 0。

 would be like a at the at the thread index， right。

 And so the thread index itself tells you how to index into data。

 And then you can use that element that it gets like from its own index from the thread index in that whole space。

And you can actually do operations with that。 So it's like a little hack of， essentially both。

Both getting the right elements of data and adding and doing math operations on them at the same time。

 So we end up doing you know， one plus two， right？With a single thread and' and it's accessing this index the index。

 the data on based on the threads index， and it's adding them together。 and then same thing for。

 you know， maybe thread thread2， right。So that's just like kind of how the whole。

That that's how the whole like indexing thing pans out。 That's why it's so cool。 And then warps。

 And it's kind of interesting。 If you， if you look at this Wikipedia article， it's like。😊，Wars。

Warps and weft， right， So you have。um。You have these warps that are going through。 So like these。

 these。These， these warps that are going through it like up and down。 and then the we is like。

What the warps are waving through， so they're like interlocked like this。

And so you could sort of think of the wars。As the as like what is， what is going forward。

 So you could say like a warp is a group of threads。Wp and weft。 the vertical warp yarns。

Plural are held in stationary。And the horizontal we is drawn through them。

 So you essentially have all these warts like a bunch of threads essentially。

 So a bunch of threads that are that are going。In and out and you can think of these threads as like doing their own math operations and you have a bunch of them grouped together in a war。

 right， that's the whole idea there。So， you know， like I said in the。In the Wikipedia article。

 Warp is a set of yarns。Instead of yarns or other things。

 stretch in place on a loom where the weft is introduced during the weaving process is regarded as the longitudinal she in in a finished fabric with two or more sets of elements。

 I don't expect you understand that。 It's just like the idea of threads are grouped intowarps。

 And then the the weft kind of like。It's that other perpendicular part。Um so。

Worps are inside of blocks。 So remember we have the the grids and then blocks and then threads inside of blocks。

You have warps which take care of threads。 So the blocks themselves aren't entirely handling the threads。

 It's actually the warps that are doing a lot of that work， so。

You typically organize a warp as like a group of threads， like I believe the maximum is 32 threads。

 so a warp will handle 32 threads at once within a block。嗯。

There is no way of getting around using warps。 The warp scheduler makes the warps run。

 So you could think of like maybe the warp scheduler as the as like the weft， right so。

It's it's sort of like going through and making sure they don't get like disentangled in all of this and ensuring that everything like works out properly。

 you can use whatever analogy works。 but the warp scheduler ensures that the warps which are group of threads run and then you would have typically four warp schedulers per SMM and SMM is like the smaller like the streaming multiprocessor on chip that's what those are and you can have four warp schedulers per SMM so you know do the math that's。

H28 threads per Sm。嗯。Then we have blocks， so blocks are interesting。

Each block has shared memory visible to all threads within that thread block。 So all of these。

 you know， thread one can see the same stuff that thread 32 can they can or or even thread like。

 I don't know。Like 500 for that matter。They can all see the same data so like within a warp can they can kind of see their they can communicate faster。

 but within a block， they can still communicate very fast through this shared memory。

 which we call the L1 cache and I'll dig into that in a second here when we go into the next section。

 but the L1 cache is very important for speed and optimizing kernels。So。Yeah。

 essentially just the same thing what I said。 short memory， short memory is， is more efficient。嗯。

It's faster。 I think the maximum memory bandwidth you get with shared memory is like on the order of like 15  TBab per second。

 and then a global V Ram。 So like when I do NviDdia SMI like this。You can see that I get。Like this。

 This is my， this， this is actually going at like maybe 6 or 700 gig a second。

 The shared memory is like 15  TB。 So it's like really fast。And。And blocks use a shared memory。

 which is， you know， on an individual S M。 so S M will handle that。And then， grids。

During the kernel execution， the threads within the blocks within the gridit can access global memory。

So that's just like universally applied。You can， can make things know more advanced if you want to use threads。

 but it's going to default using the GP of V Ram that 8，192 megabytes that you just saw。

It's going to contain a bunch of blocks。UmAnd。The whole idea here is that with。

 with grids and blocks and threads is that you， you just have to worry of like conceptually。

 what is it doing， You don't have to worry about how things are handled on the hardware because this whole this whole kupa hierarchy is a software abstraction。

 right， So the So the hardware doesn't actually look like grids and blocks and threads。

 like it doesn't objectively look like that。 It looks different and is compiled down to shader assembly。

 which doesn't actually look。Close to。Close to what this， what this is right now。

 And that is actually born on the hardware， right， So there's。

 there's various different levels here that is hard to sort of navigate through。

 But this is a lot of， this is kind of why I'm showing you this stuff is to give you better grasp on that。

嗯。So。Let's dig into what this ID Xing script is actually doing Now going into the actual couda indexing scheme like we saw with threads。

 except we're going on the level of grids， blocks and threads so everything this script in particular is designed to print things useful things out for us so as we can see。

 ID， you know， all these different block IDX。All of these and I'm going to go into these in a second here。

 but essentially like you， you have the if we go down， we have。

 we have all these terms that we define， right so。啊。Block x。Block Y， block， Z， right， So B。

 and then T is for threads。So what I particularly mean here is this is this is the block dim。

 So inside of the grid， you're going to have x like the length of the x dimension is going to be2。

 and then the height dimension is3 and the depth dimension Z is4 right So you're going to have this grid volume and it's going to be of that shape and then in each individual block inside of that inside of that grid。

 you're going to have。These thread dims。Which this is essentially the block dimension。

 is the this is the grid dimension and this is the block dimension。

 So the inside of each block you're going to have essentially four long4 high and4 D right so it's going to be this this perfect cube essentially。

And so。We go down。 We calculate， we can calculate the total number of blocks per grid， sos。

Essentially。based times width times height， your classical formula and same for threads per block and we can get the total number in each of these and then we go ahead and print them out right so blocks per grid threads per block and then total number of threads so we have a certain number of threads per block and then if we times that by the number of blocks we get the total number of threads。

Now we have this other type down here called D3， which is specific to kuta。

 but this is essentially just the same thing as we saw before。 So blocks per grid。

 So we have this these these grid dimensions， x Y and Z and then same thing for threads within a block so block the block dimensions meaning x。

 Y and Z and so we plug these into our kernel， which is called who am I。

 we have this global we have this global header， and。We do these three。

 we do these these three symbol。 I can't remember what these are called。

 It's like the less than or greater than symbol。 And then you put the total number of blocks per grid。

Or the grid dimensions as the first parameter。 And then the threads per block as the second。

 and then there's some other ones which you can do after and you'll see those in a second。

 but these are all all you have to worry about right now。

 So the grid dimensions and then the block dimensions。

And then we co a deviceynchronize to ensure that everything is caught up and we can continue with whatever else we need to do that would be used like practically。

So now when we actually go up to here， this is where things get a little bit spatially intuitive。

 Okay， I'm not going to lie。 This part might be like one of the hardest to grasp。

 but I'm going to try my best to explain， so。This block I D。 What is this well。This is essentially。

 you can think of a bunch of apartments in a apartment complex。

A bunch of floors within each apartment and then a number like a room on that floor， right。

 And so we're trying to find where we are within that in part apartment complex right so you can think of it as。

You know， your apartment is like a like a pain， right。

 It's like a singular pain in this in this volume。 And so you。In this one， you。

In in the apartment complex， you essentially do。Grid dim dot X。 So this， this length part。

 and then the y component。And then times whatever Z is。

 So the block I D X dot Z is wherever the block position is。 It's not any， it's not like how big。

 how big something is it the actual index or the position。 So you have this pain， which is x times Y。

 And then a depth， which is Z。 So it's like， however big the pain is。 And then go that deep。

 So it's like these paines that are like layered on top， going depth wise， right， It's going deep。

 And so you have these paines that are like going that way。 And then you have the。

block I D X dot y times grid dim dot X。 So you can think of this as like the grid dim is。

 is like this， like a floor， right， a floor within that apartment building and the block I D X dot Y is like which。

 which floor is it。 So you have to go up that number of floors to get there。 So it's like。

You essentially start from the bottom， you go like this many and then this many， and then this many。

 it's like each of those is like a bunch of rooms that you go through to get to the next floor right。

 and you eventually wrap up to this one and then you And then once you get to the actual ex position。

 which is like the X is the length。 you actually stop there。

 So it's like you've went through like a number of pans like pains deep， rose high。

 which is the number of floors And then you end up with like this this final part。

 which is like okay， well what is the offset at this floor。

 which which my apartment is that's like right here， It's like depth and then goes up。

Deepth goes up number of floors， and then like this is where I am。

 and how you that's how you find your block ID。Like which apartment complex or which apartment building are you in with that in that entire city or the apartment complex。

 right in the 3D scenario。This block offset is essentially the number of。You。

 you take the total threads per block。 So the block dimensions， how many threads is in each。

 you know。ThisThis many threads and X， this many threads and Y， and as many threads Z。

 you multiply those together， you get the toe threads per block or say people per apartment。

And then times our apartment number。 So it's like。The total number of threads up to your like essentially which。

 which thread index。Does your like how many threads are before your apartment。

 How many people are before your apartment or apartment number， that that's what we're saying here。

 So we calculated this block Id from before。 And then we， we just find like that。

 But on the level of threads instead。 And that's the block offset for calculating。

You know what thread were at。 And then we can continue that and use the same analogy that we used in block I。

 except for thread offset。 So you know， it's like a thread I D X Ot X block I D X dot X。

 It's like these are just like mapped essentially except it's like a lower level in the hierarchy。

 It's down to threads instead of。Instead of blocks， right。 And so you can。

 you can calculate which person you are within that individual apartment， like if if it's like a。

If it's like a big apartment with like multiple floors and there's like multiple layers in it。

 you could use that。 but you get the point it's a 3D analogy and we can find which person we are within that or which which thread essentially in that block。

 it is。 And so when you add the block offset。 So the total number of threads leading up to your apartment plus which one you are within that within that apartment number。

 then you can actually find which thread you are in the entire grid。

 And then you can do so with that， right。And that's what we says sign the global ID to。

 so global Persian ID in the entire apartment complex。嗯。And that's that。

 So there's a lot to unpack there。 Feel free to rewatch some of this or even try to visualize some of this on your own。

 Maybe write it out。 But when we actually go into。When we go into our terminal here。

 we go into five and then co to basics。If we go N BCC dash O， we go0， we go 0，1 and then。

Sero one like this。嗯。It'll compile this binary， which we see here。

 We can just go ahead and execute that， and it'll show us precisely all this that we just that we just unpacked。

 So， I mean， I can't。I cannot put all of this on the screen， but like， for example， if we look at。

Like how it counts upward， right， so。You have， you have all of your different dimensions here。

 and you can at the very end， I believe it outputs the。The particular thread offset。

 So we notice that it's like 63， and then it jumps to 32， right？ So it's like 32。

 And then it goes for。It goes for。A。32 numbers。 So if we go 3 minutes。It's technically， like -1。But。

The， the best analogy you can use here is this is 32 threads， right。嗯。That is a warp。

 So when we talked about 32 threads in a warp， this is exactly what it looks like。

 So go back to here as well。 You'll see it stops it exactly 32 and you'll go up from there。

 So it'll be like0 to 31 So it's like 0，1 to 34。 So it's like 1 to 31。

 It's 31 elements and then you'll have the additional0 which makes it 32 that's just the indexing scheme right And then when you go from 32 to 63 it's the same idea because you go from 0 to 63 instead of 1 to 64 So you do actually have 32 elements 32 threads per warp in there。

And then you can just see the global threat ID in the entire grid。 So when we。

 when we actually multiply these up， we have， you know， in the in the grid， we have two times 3。

 which is 6。 and then that times 4 is 24。24 times 4 times 4。

 so that that is 16 and then 16 times 4 is 64。So you can see 1536 in this entire thing right and so if we scroll like backwards。

 we can see 1535 ends right there and that is the final one。 So like for example。

 blocks this has two elements so it's going to be0 and one。

And then this is going to have three elements。 So it's going to be。0，1，2。

 And then this is 4 elements。 So it's going to be 0，1，2，3，4， right， And then the threads。

 because those each go up to 4。 It's going to be 0，1，2，3，0，1，2，3，0，1，2，3。

 And then you end up with essentially whatever that number is in the end。

 So you can see how this kind of all adds up and how this indexing scheme works。

 and how we can use these two index pieces of data。 using like the actual thread and block indexes。

 and then， and then do really fast parallel math with that。 That's the whole idea here。

 Let's go ahead and jump into kernels now。Okay， so now we're going to do a little bit more math and we're actually going to。

 you know， see what these kernels actually doing and seeing how they work under the hood。

So it's actually very simple。 This is the most simple it gets。

 but essentially we're just going to do some vector edition as a practice。

 So adding these two together element wise 1 plus 6，2 plus 7，3 plus 8， etc cetera。

 And we get all this Very， very simple and easy to understand。 can we have a CPU example here。

 which is obvious and easy to look at。We have a GP PU example， which。It's actually a little weird。

 It it's different than this because here we have a for loop， and here we have this， this I term。

 which is I D block I D X times block in plus thread I X。

And I'm going to explain this in a second here， but this doesn't have a for loop。

 And essentially what this is doing like I've talked about before is this just unrolling this loop。

 So you know CPU is going to like do this iteration in this one and then this one and then this one。

 the GPU is going to take all these individual iterations and distribute it across a bunch of blocks or cotic courses。

 you could say， and it's going to parallelze that operation and make it really。

 really fast So instead of doing separately like 10 million different operations like in order。

 it's going to take roughly 10000 time units。 So you had you know10000 co courses to split this across。

It's like。Well， that's that's actually a lot less。 Now。

 That's only about 1 thousand0 time steps you have to do。

 So that it's sped up an insane amount just by distributing it across。 And that's theoretical。

 of course。But。You know， we initialize vectors。 This should be。

 this should be very intuitive if you' written like any random stuff in random gens and C before。

 It's going to essentially take a random integer between 0 and a random max。 So random max is this。

um。Very easy to understand it's going to be a floating point number。And then a timing function。

 just to measure execution time again in the script， we are benchmarking。

 So perform one at warm up runs， get things， you know fired up and then benchmark CPU to GP and see how well it does。

 But this isn't really the important part here。 What I wanted to mostly expand on is。

What what things specifically here replied to Kuta and what do you really need to understand。

We have this kuda Malik， which is the same as Malik， except it's on GPU。

 so it's going to do that it's going to allocate memory on the global D RamM or the V RamM on the GPU and all this really has is a device pointer and a size so。

We have this。 we have this device a that this device a vector or array is declared here。

 which is a pointer。 and then we set the size for that right。

 And this is just the memory address of that。 So we allocate device memory with komal。

 And then when we actually want to move the stuff that we've created on the host because remember we initialize these vectors on a global or just just a regular void CPU function。

 So we actually have to copy these over now。 And how we do that is we just literally look at this。

Destination， source， how big it is and what， What kind of copy do we want to do。

 So destination is device。 hence the D， the source is host。It's size big， like we declared here。

 and then KM copy hostst2 device， so CPU is going to move to the GPU and that's it very simple。

We define this nu blocks， which is a little bit different than what we did in this indexing thing because it's not actually this dim3 type。

 as we saw before。It still works， though。The whole idea with this is that， if， instead of， say。

If instead of having like 2，3，4， if we just wanted it to be like length of what is this， This is 24。

2 times 3 times 4 it's 24。So you would， you could essentially set this to 24 and then set these to one and just having a nu blocks and then putting this in in that in the kernel launch actually just converts the integer to like dim 3。

 and then it's like。It's like nu blocks and then one and one。 So it's just like a。

 it's just length only。 And it's still like， it still looks like volumetric。

 but it's just laid out linearly。 So it ends up looking like a line and could to interprets it has a line in hardware。

Then you might ask， okay， well， how exactly do we calculate in nu blocks？ Well。

 this is very interesting， so。We have a bunch of things going on here， and this seems a little funny。

 So we have n plus block size， -1。And I'm going to illustrate this out here。

not just to clear up what the this numb block things means。

 I actually laid out some calculations for this。 So block size is the number of threads inside of a block。

 It's the size of the block itself， which threads are going to fit into right So we have。

 let's just say instead of 10 million elements that we have up here。

 let's say we have 124 elements right If we're trying to fit 124 elements across 256 threads per block。

 that means we're probably going to want four blocks right。

 they'll split it evenly because 256 times4 is 1024。

And so we have to actually calculate this manually。

But we have to keep in mind that we are doing like。

We there are more things we have to keep track of in case， say this number ends up being like 1025。

 right， So I actually wrote out a script that does， that does this math perfectly for us。

 So let's first look at this。 So you have this。1024 plus 2056。

 That's that's the length of the array plus the block size， right， birth threads per block。

 And you're going to do -1。 And whatever that is， divide that by the block size and then。A。

The the compiler is automatically going to lower this answer。 It's going to truncate those。

 those decimal places off。 So if you get like 4。99 or whatever， it's going to take that 0。

99 and just trunet it off。 you're going to end up with  four。 So if we were to do， for example。

 like 1000。1024 plus 256。 Well， what's that，1000 plus 200 is 1200 and then 56 plus 24 is 80。

 so we get 1280。 And if we divide this by 256， we end up getting around what's the answer。

Divided by 56， we get。We get this number。 But remember， we have the one here。

 which I actually forgot for a second there。 We have the one。 so it technically is。79。

 So you end up with this 099 part and it ends up just being  four because you truncate that off。

 However， if you end up having this as like 1025， then this number is actually going to end up as 1280 because you're just adding one back to you know。

1，2，7，9 and you end up with 5。 So in case you end up adding an extra element。

 you want to allocate space and resources for that。

 or else you will not get the answer that you want。 So that's all this is doing up here。

 and we make sure and this is just like a careful calculation to make sure that everything goes as as we want。

And so this is just a little script that I wrote up to test this， but I don't need that anymore。嗯。So。

Going further。We essentially in this kernel here， let me slide up。So， in this colonel。

We have just this， this X dimension laid out， right？ So what you're doing is you have this blocks。

 block I D X， which is which block it is in that， in that line of a grid。

 And then you're multiplying that by the size of the block。 So。

 how many threads are there per block times the number of blocks。

And then plus whichever whatever red we're at right So this gives us the thread in that in that like line of a grid right and so we end up with whatever place we're at and we use that thread index to then access elements in A and B and C and then we just do an add operation So whichever you know it might be in some cases this might be like you know 2。

5 million and in some cases it might be like three in which case they're going to be the same number and then they're going to add and we're going to get the answer that we expect。

 it is might not happen in the order that like a loop might right so instead of doing like the first the first index and the second index and a third it's going to like scatter and distribute these and it's just going to be fast right So that's what the whole idea is there。

And if we go ahead and actually run this script。Go 0，0， and then we can just go 0，0 vector add。

And then enter， we'll just run this file we're forming one of runss benchmark and CPU benchmark and GP。

 so the CPU average time is about 0。14 milliseconds。

 which is really fast however the GPU average time is significantly less than that about 143 x speed up almost 144 and the results match up when we compare them index index wise or element wise so we just verifiable results here we ensure that the absolute value of the difference between those two is greater than1 times 10 to the negative5 which is just a common verification so you'll see that when we're comparing things you know more like as we go more into Kuda it's going to be this idea of U benchmark you get like an average time across all the runs and then you make sure that you're getting the correct results by having this tolerance factor so sometimes this might be like super low or it might be super high。

Um， but that's that's typically how we'll do it。Then we have the second example of vector edition。

 which is very much the same， however， instead of just having this one dimensional like x axis thing where we have1。

2，3，4 lines。 we have a lot more So going back to that example from indexing where we had three dimensions if we actually apply this to vector edition。

 we get a noticeable slowdown。 So the first thing you'll notice is that this has way more lines。

 but you're like Elliot， certainly this is gonna to be faster right it uses up the whole space instead of just instead of just a little bit right well the issue with this is that couta is not really going to struggle with scheduling things and making them run fast and piling down to something that's going really work at speed。

 it's more so like what are the calculations that you're actually doing in a single thread right So this is what's gonna to happen in a thread。

 noticeice how we do1，2，3，4，56 operation。So three ads， three multiplies and three stores。

 so equal sign as well。And then this one， it's like， you have a bunch of these comparisons。 And。

 and it's just like a bunch of math。 it's it's like hard to read， right， and。The point is。

 this does one。1， multiply， one store。Or one multiply two stores and two ads significantly less than this one。

 So the point is， only use the 3D aspect when you absolutely need to。

 when it is like dependent on your algorithm and you don't need to when you when you actually have something that is like。

Baally 3D， then you can use something like this because it might actually work a bit easier and you won't have to do all these calculations to end up laying out this 3D space into like this one dimensional thing。

And you have to worry about like things wrapping around and strides and all this so that's like that's mainly the bottleneck there and I just really did a comparison between the 3D and the 1D vector edition kernel so we can go ahead and actually compile this here。

嗯。So we notice that they're both a lot faster， however。The speed up CPU versus GP 1 D。

 like the GPU 1 D is 106 times faster， but the 3D is only 102 times faster。

 So this is actually faster than the than the GPU 3D， not by a crazy amount， buts， you know， by。

By like 3，4%， maybe。 And if you scale up your numbers， it might grow。 but you get the point。

 there's a lot of。Unnecessary calculations there。 and it's just kind of simpler to go down this route with the 1D kernel。

Now we dive into something a little bit more intuitive algorithmically called matrix multiplication。

 You might have already done this on which case， you know， this might just be some simple review。

 you might want to skip ahead。 it's up to you really。

 but I'm going to go over this no matter what because some people may not know。

 Ands sometimes it's good to get a little refresh on now。

 So we're essentially going to write the naive version。

 the naive version of the matrix multiplication k kernelnal， which is the slowest one。

 but it's the most basic and intuitive to understand。So。A matrix。Looks like this。 You have row。

And you have columns， right， me actually zoom in a little more here。So rows and columns， for example。

 a is3 by2 because it has three rows and two columns， right， So it's like three high and two long。

 It's like width by height， you could say or height by width。And then we have B， which is a2 by4。

 so it's two rows and four columns， right？And the idea is is that as long as these two inner numbers are the same。

 then it actually works， we're allowed to do that matrix multiplication。

And you'll see why in a second here。 and then these outer dimensions。

 these three and four would end up being the new size of the new output matrix C。

So we have you know1，2，3，4，5，6 and 7，8，9，101 12，13 14 and what we do here is is it's very simple。

 you essentially go 7 and 11， you take this you have this this B。

 it's like this and then A is like this。And so you take the 7 and 11 in B， and you rotate it。

And you do a dot product with one and two。You take this 7 and then the 11， you flip it over。

 And so the 7 is going to multiply with the one， and then the 11 is going to multiply with the two。

 right， So you're just like it's like sideways。 And then when you multiply one with one with the 7。

 you get 7 and  two with 11 gets 22， and then you would add those together to get 29。

And we can see that right here as the first element。

So notice how it's like the first column and the first row aligned together。 And so it's like。

They're， they're like pointing at one spot。 It's like the first。

 it's like the first row up here instead of down first row。 and then the first column。

 and they meet together。 and you get this top left corner thing。

And that's and that's where we end up with this 29 value。

 And then you essentially just do this for the rest of them。 so you go 8 and and 12。

 and then you flip that flip that sideways and you'll multiply with the one and the two。

And then you put that here。You have the second column and the first row So it's going to it's going to meet in the second column and the first row right And then you just continue doing this for the rest of them until you end up with your final answer。

 So you're essentially just like flipping a column of B onto a row of a and you're doing a dot product operation where each each of like the like element wise。

 you're going to multiply and then you add all you reduce and you add all of them together and you squash it。

 and then you end up with this final matrix which is of shape3 by four。

 So three rows three rows high by four。Columns wide。 and that's how you do a mat。

So when we go into the， I mean， typically when you're writing out。You know。

 hard to understand algorithms like this when you're trying to fit this all on your head。Ideally。

 you want to write it on the CPU first。 If you just jump't straight into the GP and try to optimize。

 you're probably going to mess out。 You're probably not going to get the answer you're looking for and things are going to be weird。

 So you write out the maybe even go back to Python and write this out in Python first so you can visualize it and make sure that yours matches like Pytor or nupy or something and then you write this out and see and you say。

 okay， well， how do we do a mapmo on the CPU here。See of' A and your B and your C matrix。그。

And then your shapes and K N， so。嗯。Is this this how high a is So M in this case would be3。

A would be 2。 So 2 and 2， and then n would be 4。 right， so you end up doing this like。嗯。And yeah。

 just like this， autocomplete。M times k。 And then you multiply that with a K by N matrix。

 and you get an M by N matrix。Just space this out。 So it's easier to look at。And that that。

 So when we look at our our nested for loops here， we can see that we iterate over M。 So that's the。

That is the。Height of a， right？ That's the number of rows we have。

 And then we're going to I plus pulse that each time。

 And keep in mind when this is laid out in memory， it's not actually going to be a matrix。

 it's going to be an array。 So you're going have like 1，2，3，4，5，6 instead of 1，2， like as an array。

 and then another array below it。 And then another，'s， it's not like that。

 It's just laid out at once。So you have to actually manually consider like the wrapping over。

 So you have to actually keep that in mind when you're writing these。 And that's a tricky part， too。

嗯。Then you have J， which is going to iterate over n， which is。In is。The number of columns here。

And then we plus plus that。like each iteration， we， we make this accumulation sum。

 So we're going to accumulate into the sum， right， because you're going。Youre essentially。系。

Accumulating things as you're like when we do the ad operation and we have all these multiplies and we fuse and add them together。

 that's what this accumulation sum is for。And so when we iterate through K。Which is。K is the。

The the x dimension， you could say in a or the number of columns。

 And then K and B is going to be the height or the number of rows。

And so you iterate through that and when you do your sum。

 you essentially add it and you you do essentially this is where the dot product comes in， right？

You do a。 So that's I wherever like whatever I is， let's say I is like I is 0， right。

 So I is going to be。I is going to be whatever this is right It's going to be the first。

 the first one times whatever K is and K。K in this case is going to be well，2。 So when you have 0。

 the0 with。When， when I is 0 and k is whatever number， it's still going to end up equaling 0。

 And so you have L afterwards。 And that's going to be whichever spot at whatever wherever it is through a K。

 that's where it's going to end up at。 So like the offset through the row。嗯。

And it's going to multiply the same thing it's going to do。L， so L is where it's at through K。

 which is going to be the going up and down instead of left rate it's going to be up and down。

And then you have this n term， which we could say is maybe also zero if you're just doing me first one here。

 like the top top left corner。And then say J in this case is 0。

 So it's just going to end up hitting the。 it's going to end up in hitting the same value。

 So you end up just getting the first， the first points。 And then you you multiply them together。

 and then you add that。you multiply them， you multiply the first。

 the one and the seven together and the first one， and then you end up hitting the second one。

 which is the two and the 11， and that gets summed up together。

And you're doing this every single time this for loop， the second for loop triggers right。

 So every time this goes through an iteration， you're hitting n and N is just。And is just。

Whichever value， whichever value is essentially coming next， right。

 And so you're just getting this one and then this one and then this one and then this one and so on so forth until the end。

And then you end up just writing this out， so you you essentially assign the value C to whatever that sum is that you can compute the next dot product。

 So this this is like very visual， I encourage you to I mean if this doesn't completely make sense if you haven't like taken a。

Introduct real linear algebra course。 I completely get it。 You might want to just pass us through。

 you know， language models or look at some some intuitive videos on the Internet and just sort of understand what's going on here。

 Try to understand。What like how things are wrapping around when they。

 when they do like a stride or something， that's， that's very important to pay attention to like this like the K。

 when the K is wrapping， for example， K is。K is here and K is essentially this， this length。

 So it's going to be like whichever whichever whichever row you want you want to wrap around that entire row。

 you want to go to the length of it and wrap and then your offset is going to be that and then same idea here except instead of rows。

 it's going to be like columns column offset right。And that's the whole idea there。

And then we go into the GPU implementation， which is a little bit different。

 but we're essentially using instead of just an I or an ID a single IDX term。

 we use rows and columns。 So in this grid， we have the block ID X dot y times block dim dot y block ID X is you know where the where the block is at and。

Or the essentially where the block is vertically。And we're just getting essentially the vertical thread。

 like which thread we do we want within considering like this vertical grid and all the blocks that we have。

 right， going back to what I said before， and we do the same thing with X。

 So we have this we have the thread in the vertical and the horizontal direction。

And then we as we want to， this is actually very， this is actually very。This is required。

 You actually have。 you need this instant statement here。

 because if things go off track or if you have like too many threads。

 then they might go and compute values that you don't want。

 Like it might go access other parts of memory。 It's not restraint， right。

 So it's not going to stop when you think it should stop。

 You actually need to put careful restraints on it and say， okay， well。We。

 we want to stop it once the row gets to M because there's no other values outside of that。

 And then same for column as well， right？ So like when we go up here， we have。We have M by N， right？

 So M is the。M is this part。Whi is the。u。Where to go。Yes。M is rows。

 So row is y right this this y this height part， and then n is is that the width the horizontal part X。

 And so that's that's columns which maps to x right And so you have to this is just the kind of thing that you have to be careful with。

Kuta handles us very well， but you just have to include this if statement。

And then you essentially for each thread， because this is itself in the thread。

 you're going to just do a。Essentially a dot product between elements and you're going to do like essentially a row of a row of a and a column of B。

 and this is going to be done per thread so each different thread is going to have a different maybe a different row and a different column of B to compute。

So you have this。You have this K term which is from here and you're cycling through that and you just essentially apply the same wrapping。

 but instead of worrying about all of these nested for loops。

 you worry instead about the rows and columns so these are your actual these are the you know the way we index with threads as I was talking about before。

But yeah， this is， I'm going to dig more into sort of the intu intuition behind this later in the course when we end up optimizing matrix application。

 this， this is this is called a naive kernel。 It's， it's very， it's very limited。

 It doesn't have a ton of optimizations。 It's not like it's not fast。 It is like。

It's like1 hundredths the speed of what state of the art is it's actually quite slow comparatively。

 And we're going to optimize this later on。 And this is going to be the most intuitive thing you will probably learn in this entire course as matrix application in Kuta。

 So don't worry if this doesn't entirely click right now。

 Just kind of worry about where these threads are。How we're getting。

 how we're getting the row and column values and then this wrapping that we have here and then the offset part。

 right， wrapping and offset。Offpset。And yeah， that's that that's pretty much all you have to worry about for now。

 And then we just do。You know， the same route perform warm of runs benchmark it across 20 benchmarks or across 20 runs。

 benchmark CPU versus GPU， and then return the average time in microseconds。

 So if I just open up a terminal here and go N BCC。还有。To。wo。嗯。You ahead't run there。From Ro runs。

Okay， this is very， I actually made a very large major receipt。

 but we should shrink these a little bit。We can go。我 see， maybe。56。At 12。256。Yeah。

 the CPU is not going to like that one。And so it's benchmarking CPU and so that takes 89。

000 microseconds and this takes 88 microseconds so we get just like out of the box with these small matrices。

 we get a 1000 x speed up with using Kutuda。嗯。And that's that So this is kind of how we test stuff but。

Yeah， now we're going to go ahead and jump into like， how do you profile these。

 I know we haven't gone extensively into like how could actually works under the hood completely。

 There's still more to do， but。In a little bit， we're going to hit up profiling。

 I would like to cover。Actually， some more stuff before we do that。 Let me close this out。

We pop into the read me here， just close this， or close this。Ex it。Think out a little bit。Sure。

So again， we have these， these dim three types， which I was talking about before。

 these should make sense already， these should not be like too hard to grasp。

This is what it normally looks like， right？You put， you put this in。You put this in。

 like I said before， it's going to simplify to a dim3。

 So this is going to look like a 16 by one by one tensor， you could say。

 And it's going to add that to the kernel launch configuration。

 This is the kernel launch configuration。 There's more stuff we can add to it。

 alreadyy covered this stuff already。呃。And then you have more stuff you can add to it So we have the grid dim。

 the grid dims in1 to 3D Bd and 1 to 3D， and then this Ns So this is the number of bytes in shared memory that is allocated per block for this call so you're going to explicitly allocate memory。

Or a block in shared memory， which is really fast。 So typically， you would omit this。However。

If you have a specific production， like you're trying to deploy a curcur in production to run something really。

 really fast， you might actually want to capitalize off of this because it'll give you more explicit control over what happens。

 And you can measure performance a bit better。 and it'll get maybe get some little performance gains out of that。

 And then there's this S term， which is the stream it's in。

 And I'm going to cover streams actually in number5。 So don't worry about this too much。

 but streams are pretty cool。 They let you do some interesting stuff。嗯。And then this。

 I didn't talk about this entirely too much。Cuda device synchronize and sync threats。

 So coa device I synchronize。Ensures all the kernels or all of the threads for one problem are all of the like all of the all the different parallel computations for a problem are done before you begin the next。

 So when you when you launch a kernel， it's going to have a bunch of blocks in parallel and a bunch of threads in parallel run this massive problem。

And they might not all finish at the same time， like some of them just like due to physics theyre they might like not finish at the exact same time and so you have to explicitly synchronize them。

 you have to add this little barrier this this essentially preventing a a race condition。

So if you have a bunch of threads。Like， for example， in this one， when you're bit shifting。

 when you're like moving this one over here and then this one over here and then this one over here。

 it's like， well， ideally you'd want to do this in a certain order and not like store something before it's not supposed to be stored like if for example。

 if I do this one and then this one is supposed to happen after。

 but it ends up doing this one first because we didn't synchronize properly。

You could you'll end up with the wrong answer， right。

 So you have to purposely synchronize the thread so that all of them。

 regardless of like this one might be like way ahead。

 you have to wait for all the other ones to catch up in order for hit the same spot。 So you say。

 okay， this one's done。 but these ones aren't。 we're gonna to wait for all of these to synchronize up together。

 And then we can continue the next step right That's what coudter device synchronize synchronize will do after you typically put this after launching a kernel and then sync threads is put within a kernel for threat execution inside of it。

 So one is like out like when you're trying to synchronize the whole grid。

 And then one is like synchronize all the threads within within like。Within a warp。

So as you might have been able to tell， I was a little bit unsure about that last answer。

 So I decided to look it up and sink thread is actually on the level of。

Thread blocks instead of warps， so you can do sink warps instead of sync threads actually pop back to here。

And we go。At sink， the sink threads。You can actually do。If you want to do warps， you can do。Thank。

Wars。嗯。To sync all of the thread within a warp。 And then this one will do that as a bit of the same thing。

 but a thread block instead。The reds。It in a war。嗯。And then this is for an entire thread block。

 So just just a piece of clarification there。 other cool thing I came across when studying Kuda is how you can actually add in explicit flags and can you can actually convert something like a log to log F using compiler flags。

 And I know that there's a little bit to unpack there。 But if I just go back。This compilation here。

Actually， no， we don't even use， we don't even use any of those。

 but if I were to say do like a log inside of a kernel。

 that would go slower than if I were to use log F。 So log F is like a device operation and log is a host operation so designed to run on CPU on CPU course。

 right？So we can actually do use fast math as a part of the compiler legs so I can go。你 use。

Use fast mat like this。And of course， we won't really see any difference， but。Yeah。

 like same 10106 x same thing， but this will actually convert this to this in case you don't in case you haven't done that yet on your own so this actually comes from the KUa math API reference manual。

So。呃。If we look at， say like。Some of the。Single precision。Intrinsics。Yeah， so。

Single precision intrinsic functions that are supported only in device code。Right。

 knows how it has like co F X exponentiiate with base 10 F， E， X P， F。嗯。And then， like。You know。

 F add round towards 0， right， all of these these are， these are designed to execute on device。

 and they have F at the end。 But if you were to just do。I like。Just coast， for example。

 from the math dot H library in C that wouldn't。 that wouldn't run as fast。

 So this is another little thing you could add to your kernels if you're trying to say you like。

If you're trying to do like softm or something in a kernel。

 or if you're trying to maybe do like like some digital signal processing， right。

 you can add these and and get some benefits。That's why it's out of those。嗯。And same thing here。

 like if you wanted to do a fuseed multiply ad， this will like tell the actual this will actually。

Like pour this into the instructions where instead of doing like separate multiply and add operations。

 you're ref fusing them together So you can do little tricks like this and just speed things up performance wise。

 but。Yeah， now we can actually dive into profiling。

So I actually forgot to do the tiled matrix multiplication by hand。

 so I figured I'll just squeeze this in now and let your mind sit on this for a little bit before we actually start using it and applying it。

 But before we had this this idea of a matrix multiplication， which was you have like a。

You have like a matrix a。And。Can you see that。Be not。 I'm going to move this now。

Let switch marker here。诶。Matrix a。It was with some numbers in maybe。Yeah。And a major to be。

 And the whole idea here is we do product this with this。This with this。 This， with this。

same thing and bring it down here， do do do do do， right？All the way till the end。

That is one way to do matrix multiplication， however。

 you can actually make this more efficient by using something called T。

So I'll provide some examples on this later in the course， but this is the idea here。You have these。

 you have these two matrices， A and B， I'm just going to。

You have to look at this a little bit differently but。This is what it looks like。就。We have say。

Let's just say this is a and this is B。And you have the C matrix。

And how do you compute like the first element right。

 Well you would you would typically take this row and then this column and then you would put that there because that's where they intersect right。

 but what you can do。Is you can actually take a chunk。

 You can take a chunk like an actual square or rectangle of a。 So like maybe this。

 I'll just put this into like separate pieces。Say this is like a， you know， maybe a nine by nine。

and this is also。So technically each of these is technically like a three by three tile or a matrix on its own。

 right， and so we're just spliting this up into tiles。And so what you can do here is。You can。

As I've wind out here， you can。You can go one。Time。You could do a matrix。

Matrix here times the matrix there。Like A and B respectively， like you do a times v。

 and then you add that to the matrix multiply of two and two。

A and B respectively and then three and three。You start with these， and then you。

 then you add them to these and you add to these。 So it's like。A1。A1 times B1。You multiply those。

 and then you add it to a two times B2。And then add that to A3 times B3。

 and then you end up with this with this C wine here， and that's the output。

And that is exactly what I've written out in this sort of cube format is like you've laid out some matrix A right here。

 which is like a row， and then you've laid out some matrix B here。嗯。And you're just， you're doing。

This times this and then add to this times this and then add to this times this。

 And that's and then you just end up with C1。 And so what you can do with like the reason why this is so effective is because you can you can actually put these tiles and you can pop them over to a faster memory like like shared memory and then they'll end up running like ridiculously fast and you can end up doing these computations like way faster。

 So if you split it into little tiles and let each little like streaming multiproble or on the chip actually take care of the individual tile or multiple tiles。

 then you can actually get a lot more useful you get a lot more。A lot higher compute throughput。

 you could say。 but don't worry about this too extensively。 This is just the intuition behindtyling。

 like the difference between this and the normal version we were doing where we like take a whole row。

 and then we take a whole column and we dot product them together。 This is different than that。

So that I just wanted to put that in your head for later so that it's not a complete surprise when we try to make this faster。

Now we dig into how can we actually profile the performance metrics of our own kernels？

 So how do we optimize these right？ And we're going to use NviDdia Insight compute for this。

 If you're on Windows， you might you might not have this and might look a bit different。

 I haven't tried it on Windows yet。 But this is what we're going to use on Linux here。

 So this is kind of what it looks like at the end。 You can see a bunch of details about things。

 It's very， very interesting。 but we're going to dig into this in a second here。

 I'm just going to close these off。And we'll go ahead and get started。Let me close these here。

We'll see in this， in this number 5 kernels chapter in profiling， we have a bunch of files。

 So we're going to start off with this one。 the N V T X Ma。 So what is。What the heck is Nvy T X。

 You guys already know what matrix multiplication is。 I'm not going to go over that。

And VTx is like the custom profiler for ka kernels， right？And what this allows you to do is。

 it's actually quite straightforward。 If you look at what's happening here， like it's。

 it actually makes a lot of sense what's happening。 So we're able to push this into a range。

 like essentially the timeline。Push matrix multiplication。 P memory allocation， right。

 So we're doing the。嗯。This is the whole， this is the whole matrix multiplication thing from start to finish。

 We push things into a range。 So memory allocation， and then we pop that。 We pop that out。嗯。We copy。

 pop that out， so it's like start and finish。And then we do our dim threes。We start kernel execution。

 and then it's going to stop that once we've launched the kernel， run it。

 and then synchronize all of our like our everything in our grid。And then copy back to host， right。

 So this is like very straightforward。 Li all you need。 So mean， keep in mind。

 like when we start this one， we have another one afterwards。

 So this one is only going to target the recent one that was put up。

 right So it's not going to jump back to the first one that was ever pushed in。

 It's going to be like kind of like brackets， right。

 So you have one layer of brackets on the outside。 And then one on the inside。

 It's like it kind of that's kind of the structure of these of this NvT X tool。

So when we go ahead and NVCC this， we want to pass in the link NV tools extension。

 That's what NVTX stands for。 So NviDdia tools extension I'm gonna compile that We can go ahead and you know run this it'll it'll run as expected good and then we can actually if we pop back to this readme file。

 We can do Nsys profile stats equals true on the。It's not mammal， it's 0，0。

 But if we go in and run this。We will notice that there's a bunch of cool stats that pop up。 Now。

 if you're running from a remote machine， you could， you could use this。

 You could just look at this directly from the terminal。 However。

 the Nvidia Insight compute app itself is actually a bit more informative than this。So。

What we can do is is type your Windows key， then go windows and then type NC and then press enter。

 and it should bring up inside compute and it。It， popped over my second monitor。

 I just brought it over here， but this is what it should look like。 And what you can do from here is。

I'm just going to put this on the second one and then drag the report Nss rep file。

 so not the SQ light， SQ light is for a different thing， but we drag this into the sidebar here。

Now it's in。 we can see it at the top。 And now there's a bunch of interesting things in here that we can look at。

 So this， this text might be a little small if you're on a phone， but just bear with me here。

So we have bunch of stuff on threads， You know， N V T X。

 what is like what's happening sequentially here。 We can actually zoom in and see。

You know the memory copy kernel execution takes about two milliseconds and we can see everything right。

 so all these are actually pushed into the range and we can see what's happening。

And then of course the you know the memory allocation takes a while and then the matrix small application from start to finish like highlighted it in the code so that's that's how that's what NVTx does。

 You can push things into a range and you can see how long it actually takes you can see like when it's happening on the timeline and you can look more more and more detail as like what's happening there right so。

😊，Anyways， if we go to the Kuta hardware at the top here。

 we can see it consists of kernels and memory。 So there's like。嗯。Copying， so K a M copy。

 And then there's the matrix mu kernel。That we can see here。 And if we click on this。

 we go show in events view。

![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_7.png)

You can click on this down here。Zoom to select it on timeline。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_9.png)

We can right click。Let me go profile kernel。And there's a bunch of interesting things here。

 and this might little might be a little overwhelming at first， but there's common filter， metrics。

 PMm sampling， warp sampling other。 So we're just going to use PM sampling right now。

 PM sampling is performance metrics sampling， So it's going to give us very detailed metrics about things and be able to optimize from that。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_11.png)

So it's going to use this binary 0，0 file that we made before during compilation。

 and it's going to bring up this new menu here， which is different than the timeline one。

 So is timeline view， and then this is different。 So in here。

 you know we can see all of our kernels at the top。

 So in case we were like maybe profiling two different matrix multiplication kernels they might both show up here。

 like the runtime， the lifetime of our program。 that that's what would pop up here。

 and all the kernels inside of that。

![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_13.png)

So if we go to， you know， say summary， there's there's some interesting stuff here。 Maybe we don't。

 maybe we don't care about this too much。 There's there's details。 So you have throughput。

 So overview of throughput for compute and memory resources， PM sampling， so performance metrics。

We can bring this down， and we can see things like Sm throughput， pipe throughput。嗯。

A bunch a bunch of metrics I don't even understand yet， but。We have things like cash hit rate。

 which which is really useful， But if we go to like speed of light throughput， for example。

 this is for the memory resources， we have the compute throughput as a percent。

 so that's at about 9097% and then memory is also at about 97%。So。Um，You know。

 we we get we get to see cool things like this and and it'll make more sense in a second here。

We go down too。Memory workload analysis。 we can see memory throughput in it like very detailed memory。

I guess memory metrics。 So gigabytes per second。 How much。

 how much are we able to transfer back and forth， right， bytes。D Ram by per second。

 So that GPU V Ram， how， how fast are we accessing that And that that speed is about 41 GB per second。

 which。Which is not super high。And then we have like L1 hit rates， L 2 hit rates， all this。

 And we can see a memory chart here。 There's just like a whole bunch of metrics that we get access to。

And so， if。can we can pay attention to like this number 41 but we'll keep this number in our head for now。

 there's also a source too， so you can look at the actual assembly instructions and see you know how many registers does it taken up a bunch of very low level stuff which I'm not going to dig into right now。

But。Yeah， there's so many settings to dig through。 Anyways， we're going to keep this number。

41 in our head。Now。We close this out。 we'll just put on the side for now。We have some other。

 we have some other scripts as well。 So I have a naive mammal。

 So this is the one that we wrote previously。 This is the exact same， just our direct copy and paste。

And then we have a tiled mamel， which I'm going to cover a little bit later。

 it's a bit more advanced but。We're going to compare the performance metrics of the naive versus the tile mammal。

 so。We go ahead and pop into here。We go NBCC。0，1， and then 0，1， link Nvy。Wol was。runun successfully。

 and we can go end this profile and then put in 01 right there。

 And I'm going to go ahead and drag this so we pop up another one。

 I'm going to go drag this into an insidesight compute。And。We check out our Ka hardware。

 go to kernels matrixtri multiply。 This is the naive version。 Remember， show an events view。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_15.png)

Zoom to selected。Profile。啊。We run the PM sampling again。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_17.png)

It's going to run that。 And then we take a look at our new stats。 this。

 this is the exact same thing without Nvy T X。 but just for context details。Memory workload。

 So we get， you know，30，37。 it's， it's pretty close to what we had before， right。

 maybe a little bit lower。 but when we。When we compile the tile mammal。It works as expected。

 and since profile。I'mre going to get a number three here。

I'm going to go ahead and drag this into Insight compute。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_19.png)

We open this up。Pop over to our kernels。Majors multiply optimized， show in events。

Soom to select it on timeline。 We can see the length of this。 By the way， this is how long it takes。

 It's going to go from you know， 430 milliseconds，430。24 milliseconds all the way to 431。

57 milliseconds。 So that's actually how long it takes。 And you can。

 you can sort of see the length of the timeline there。



![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_21.png)

嗯。Profile PM sampling。

![](img/74a26ba8101bf8d14b5973c5d3a3c1dc_23.png)

And。Give it a second。We open this up in details and we can see in memory workload analysis。

 this is significantly higher than it was before。 So these are the types of things you want to look out for when you see your memory throughput drop after you change something。

 It's likeugh we maybe we shouldn't do that。 you know from here it went from the naive。 it was at 37。

 And here it's at 60 right So that's making a better use of memory and we'll see more optimizations later on。

 especially in this in this faster mapel chapter as to how we can seriously get this number up。嗯。

But yeah， this is， this is how you profile。 There's a bunch of cool things you want to look out for here。

 It really depends on which algorithm you're working with with matrix multiplication。

 there's some more like there's some more。Fine grained optimizations that are just proven to work。

 So we just。We can just run those and and kind of compare the difference。 But you have。

 you have all the resources out your hand here。 There's tons of things that you can use and learn from。

 so。Yeah， this is。This is how you profile C kernelnals using NviDdia ands compute。

I have a readme file here with just pretty much everything we went over， so。The NSS profile command。

You can profile Python as well。 So N profile， and then you can。

If you have like an MLP script in Python， you can profile that。Funny enough。

And it'll just use the whatever NVIDdia library is as that Python file is using。um。Then we have just。

 you can do this some stuff over the command line like this， so。NCU。

 kernelon name and you can do stuff over the command line。But yeah。

 there's a bunch of useful tools here。嗯。So this might be updated later on。

 It's not in like the best format yet。 so this might look a bit different when you see it。

 but these are kind of the main ideas。 And then just to I guess leave it on an endnote C Pti or couda coa profiling tools interface。

 the PT at the end。 This is for like creating your own creating your own custom profiling and tracing tools that target specific co applications。

 So you can you can design your own profiling tools with this。

 if that's something that catches your interest， you might want to look more into it。

 So I'll leave this here， but' that's how you profile coa kernelnels。 next up。

 we have this thing called an atomic operation and atomic operations are used in very specific cases。

 someone going try to cover these as best I can。 by atomic。

 we mean the indivisibility concept in physics where thing cannot be broken down further So you have an atom。

 It's like， oh。I mean， technically， there are quas and stuff， but you don't worry about those。

 It's just like the indivisibility concept of this thing。 you cannot cut it in half， right。

 There are parts maybe inside of it that that make it up， but you cannot you cannot cut it in half。

 And that's what this atomic operation is and it operates as a software abstraction for us。

 So the hardware and the coupa compiler take care of all of this for us。嗯。Essentially。

 an atomic operation ensures that a particular operation on a memory location is completed entirely by one thread before another thread can access or modify the same memory location。

 This prevents race conditions。 So remember before。

 when we were talking about how they are like multiple threads that like one might end up being faster and hit the goal before this one。

 And it they sort of need to like not modify each other's， not。

 they need to like not mess with each other's things。 So that that's what this idea is referring to。

 so。Cannot access or modify the same memory location of an over it。 That's very，'s a very key point。

 right。And we're going to see a very crystal clear example of this in a second。

We might lose some speed， so。If we limit the amount of work done on a single piece of memory or unit time through put an atomic operation。

 we're going to lose some speed from that right， if we're locking things down and limiting how fast the program can finish by just having everything like not wait for everything else。

 then it just finishes faster， right so。When we use atomics， things will slow down。

 but it is guaranteed to be memory safe， and that's ultimately what you might care about in some cases。

 it might be better to get the memory safe aspect instead of the performance gain。

So there's a bunch of different atomic operations that we have。

 I we'm just going to make this a bit easier to see。You have atomic ad。

 So essentially what this is you have a you have an end， a pointer to an end。

 some memory address and you have a value and all you do is adds value to the value at address。

 So when we when we pass in like， for example， say the number4。

 and then we get the memory address to that which is some hex code。

 we put that we put that hex code in here。 And then we put a value， let's say like2。

 And so what that'll do is it'll say， okay， well we have memory address。

 lets let's get the value for that memory address， which is four。

 and then we're gonna to add the value to that。 So it's just like this memory address stays the same。

 there's nothing new being created。 it's just you're taking this value and you're adding it on top。

And that's that's kind of the whole philosophy of everything in here。

 So substitution exchange and and the return value will always be the old value。

 So when we do like atomic add。 And then we say like put into equals atomic add of whatever is in here。

 it's going to return the old value of whatever this was。

 So it's going to essentially return the value at address， right。

 so we can sort of compare in contrast。's it lets us do that。

 or you could just not like return anything， that's fine。

 you could just if you just want to add value to that to the value to the address value。

 then you can just do that。But these are all of the these are all the operations that come with atomic。

 these are all the atomic operations。There's also floating point， atomic operations。

So you can think of atomics as like a very fast hardware mutual exclusion operation and I'll dig into Mu textex in a second here。

 but essentially how this goes is you lock out of memory location， you set old value。

 the return value equal to like dereencing that memory location。

 so like the hex code and then you get the value for that。

 you set this old value that you're going to return equal to that that dereence value。嗯。And then。

 we set the。We set the dereenced memory location。 So that value that goes with that hex code to the old value plus the increment。

 which is， which is Val， right， This is int Val。 And then we unlock memory location。 We return it。

 So it's just like during this part where we're incrementing and we're storing the old value。

 we're going to lock it down。 So nothing else can interfere with that。

 It's just this has to complete。 This is priority。 And that'll that priority will exist through however many coar threads we have。

 right，s that way they can't interfere with each other。 So one has to finish。

Before another one accesses it。And then we just return that， right？And。In terms of mutual exclusion。

 there's a nice YouTube link on here that I found， which was very good。

 Mu is is like a like a shared relationship between entities。 So all of us threads we're going to。

The act of keeping something out or preventing access。

 So we're going to exclude everyone else from accessing each other's thing。

 We're going to let each other finish， right， Thats that's that's mutual exclusion。

 This applies to atomics， right。So you don't have multiple threads accessing the same thing at once。

And there's like an intuitive example here of like what this might look at a lower level what this is actually doing。

 So if we go over to our atomic ad over here。IfIf I MBCC， you compile this。

We'll see like first of all， that we import whatever we need to， the kudto runtime。 H。嗯。

We have a number of threads， so1 thousand0 threads per block。

 and then1 thousand00 blocks in the grid。These are are macros that we define so if there are 1000 blocks with each 1000 threads inside of them。

 then we're going to have a total of million threads right and then we have two kernels here so one is going to increment a counter nonatomically so it's going to take an counter。

It's going to store that old value as the de referenced counter because this is a pointer， right？嗯。

We're going to set the new value to whatever this is， whatever that actual integer value is plus one。

 we're just going to increment by one。And then we're going to update counter， right？嗯。

And then there's an atomic version of this， which does the same thing except it locks instead。

 So this part here， this is actually like you're adding， you're essentially adding。Not blocked。

And this is not。Not unlocked。Right， so we're supposed to lock here and then unlock there and return whatever that is。

So。Then if that's。I think that's correct。Yes。So。We go down， and everything here is fairly intuitive。

 We have our nu blocks and our numb threads。 And it's the idea is we're going to have a million threads that are each trying to update this same。

 this same counter， because we pass this， this counter。

 This is a single variable or a single pointer that we pass in。

 And all of these threads have to have to modify the same thing。 right。 So when we actually run this。

You're going to see nonatomic countervalue is 41。 So this means that all of these threads are attacking the same the same memory address and they're all performing modifications on at the same time。

 but atomic， it's going to take a little while longer。

 it might take a million operations instead of 41， but it's going to ensure that we get through this properly。

 So it's going to say， okay， well this thread wants to access it。

 So we need to lock down only this thread can access this value。

 and then all the other threads instead of racing to it。

 they're going to just wait because it's an atomic operation， right。

And so this one gets to complete first。 And then maybe this guy and then this guy and then this guy。

 and they， and they all sort of complete。 And then you end up with the actual true answer。

 which is 1 million， right， because it increments it increments from。Incrementments from zero。

So that's pretty much atomics。They're pretty cool。Maybe you can think of a way that you could use them right now。

 I don't know。 But that's that's just something that's super important to cover。

 because that's that's one of the the risks with kernels is that you have a bunch of these。

 a bunch of different threads accessing the same， the same thing and making changes that maybe you don't want to it and not like getting any errors or warnings about it。

 right， That's that's a danger that you have。 So atomics helps secure that and lock that down。

So now we go into couda streams， and kuda streams are one of the most useful things for performance。

 optimization and maybe even large systems， right， So is actually。

 this especially works in large systems。 And you're going to see why it's second here。😊。

So you can think of the intuition here， so you can think of streams as river streams where the direction of operations flows only forward in time。

 so you have this this timeline。And。The idea is。Normally。

 you would copy some data over from host to device。

 and then you would do something with that data like a kernel launch。

 and then you would copy that back from device to host to do something useful with it。

 And what you have here is you have these little dependencies where it's like you have to wait for the data to come in before you actually start the kernel launch。

 But wouldn't you always want to be running kernels。

 And wouldn't you always want to be doing computation。 Well。

 streams actually solves that issue for us。Instead of just having one little timeline。

 you can have an extra layer underneath it too and even more。

 they can have as many layers as you want。 And the the whole idea is you can copy some。

 copy something over， do a kernel launch。 And then during that kernel launch。

 like when when that stuff gets copied over， you can start copying the next stuff over in a separate stream。

Right， so you can， you'll be doing some computation while you're copying stuff over。

 And then when this stuff is copied over， you can do the next kernel。

 So it'll it'll look like sort of a staircase。 And I have an example of this in the。

InviDdia documentation here， the NviDdia streams and concurrency slides。

And essentially looks like this， So you have。This thing called Ka mem copypy async。

 which is asynchronous。And normally， if you're doing a serial program。

 which is what we've worked with so far， you'd be doing。

 you'd be going in this fashion where you're not always doing， you'd be like copy something over。

 do something with it， copy it back， copy something over， do something with it back。

 And then in this example， you'd like copy a bunch of stuff over， host to device。And then， you do。

Maybe a。Maybe it's better illustrated in this example is like you you copy some stuff over， you know。

 you do like， say， like three kernels in a row。 And then whilst a kernel is running。

 you're always copying new stuff over。 So you're not like you're not you're always doing work across all the streams。

 right。And this is super useful， especially when you have something like。When you have things like。

Training a massive language model， right when you're trying to。

 when you have this data loader that is like constantly loading big chunks of text in。

 you don't want to be waiting for that。 You don't want to just do your your training forward and backward pass。

 And and then wait for it again。 You want like you want it to be loaded in while you're doing your forward and backward pass。

 Like you want it to be ready for you。 So that way you can just start， you can just do it again。

 So it's like nontop forward backward you never want to stop doing that。

 And that will that will greatly increase performance。 And so this is where coudus streams come in。

 right so。This this whole idea that I'm talking about with like fetching data before you actually need it like literally called prefeting。

 software abstraction called prefeing so you move data around before it is needed and this hide the latency of moving data around like cotam copyright。

So。We have this。 We have this kernel launch configuration。You this before。You have a grid size。

Of a block size， right， and then there were two other things that I talked about。Which are here。Now。

 this is the。The number of bytes in shared memory， right？

 So you're you're doing stuff with shared memory， which don't do more about that right now。

 And then there's this other one S， which is the associated stream， right。

 so you can actually put a specific kernel on a stream， as we showed in here， right。

You can have these are all the different streams， stream1， stream 2， stream3， St 4。

 So you have you' launch this one on stream  one and etc cetera。

 right So that's that's the whole idea there。嗯。And this this， this is just a super easy。

 easy way to interface with the streams when we do our kernel launches。 So there。

 there's multiple things that come in here when we're dealing with streams。 So you get this。

 this thing of priorities。 So create streams with different priorities。 And if we go into。

I don't know if it's in this one， maybe this script， we if we look at the get priority range here。

 we can see this takes in a pointer to a least priority int， just a variable。

 and then a greatest priority int。And so it's like， this is the least priority。

re going we're going to plug this in here。And then we have a greatest priority， which。

 which we plug in here， right， And that's our range。 And so。We can feed these in， so that。

Kud do will actually manage which ones get marked priority over others so if you want to load into a bunch of data first and that's your initial priority。

 you want to like get that part done as fast as possible you can actually prioritize that with like least and greatest priority right。

And then we go a little bit。A little bit further down。And we have some examples here。

 So let me just touch on。The basics here。So。There's some stuff that you may have not seen before。

 which Ive probably used earlier， but did mention it。 These are macros。

 These are the error checking macros that we have to essentially make sure that operations go through successfully。

 So when。When we do like a kudamal， we want to make sure that that that that one successfully， right。

 And that'll just this will。This will return a coupa error type。

 meaning either success or error like failed， right。

 just indicating whether that went through or not。 So that's what that is。And then。

If we scroll down a little bit more and see where the actual streams are happening， keep in mind。

Up here， we we use this kutuda stream type， right， so it's a kuda stream type。

And we define two streams with that stream one and two。We create。The stream。

 So we actually have to have custom handlers for this to say like， okay， you made this。

 you made you defined it。 It's like now you have to actually create the thing。

 It's it's a weird context thing and Vdia has but it ensures everything is safe and handled properly by the compiler。

So。We get this other term kam copy async。 And this essentially just allows us to have like these asynchronous copies。

 I mean， when you have these order， like if you go coam copy async on stream 1。

 and then later on you have like a like like a kernel launch like right underneath it。

 It'll actually go in that order。 So it won't just。

It won't it won't try to do like the kernel launch before because it's asynchronous。

 It'll just be asynchronous， meaning in the context of streams so you can have things sort of。

Happening， I guess， concurrently， but it will still follow that sequential order within that stream as long as you assign them to the same one。

So then we have our threads for block and blocks for great configuration。

 We have launched this on stream 1。And we have this this B， this B array on on stream 2。

we can do stuff with that as well。 So and then notice how we have a comment copy input puts the device asynchronously So this is just a little cheat where instead instead of copying copying a from host to device then copying B to from host a device sequentially you do them at the same time So A gets copied and B gets copied at the same time and then you don't have this extra barrier here where like nothing no work is being done you can just get right to kernel computation So we see that here we have a stream1 and stream2 and this is all done on stream1 So all all this memory is going to be shared。

And。We we go down further to this， you know we copy back， we copy C back asynchronously。

 but there's only one so it doesn't really matter which stream that's on we just do async because why not and then the stream synchronize so we're going to ensure that all of the streams are then caught up and then we can and then we can do something with that right so we're going you know3 the device Vi A BC and then destroy both of the streams and and then it's done so if I go ahead and actually compile and run this。

Test passed， and we got everything correctly。 And we did this vector edition。

So it's just kind of what what we all we really did here was just this is where the magic happens instead of loading A and then B。

 we load N B at the same time。 and then we go into。What's it call。Advance。

So I'm going lower this a little bit so you can see。 So when we go into advanced streams。

 things get a little weirder， but it's not too crazy。

 So there's a few things that I want to introduce here。 We have pinned memory。

 So it's essentially saying on on the CPU global D Ram。 It's going to preserve this piece of memory。

 We're going， we're going to pin it using kudamalic host。Sented just saying， you know。

 this is a part of Kuda。 It's reserved for the GP to use later。 So we're not going to modify that。

 We're not going to let the operating system or anything play with this。 We're just gonna pin it。

 Nothing can touch it。 And then we're going drag that over somewhere else for later。

 And we're just going like reserve that。 right？ So we're gonna to use this。

 We're gonna to need use this for later so don't play with it。 iss a good way to think about this。嗯。

Events are a critical part of using streams， so。We can measure kernel execution time。

Given this given this example here。 So we have an event type start and stop。

 So these don't actually time anything， but they are they're part of the input to these event event record functions。

 So we go and create these with the memory addresses of start and stop。

 And then we can plug in whatever stream， for example， to stream or stream 1 or stream 2， we。

We do an event record。We do we launch our kernel on this stream， and then we do another event record。

In this stream。And we can take these values， start and stop， and they might carry some metadata。

 I don't know exactly how couda handles this， but start and stop。

 we can synchronize we can synchronize everything， and then we can plug it into couda event elapsed time。

 which takes this milliseconds float， which is going to be a milliseconds。

 and then you have your start and stop。 and that's going to tell you how long your kernel took to run。

 right。So instead of launching it instead of going into the NCU profiler。

 you can just do this instead if you want to。And will this will not have any computational overhead。

 or it's very minimal， so this can be run in like production environments。

 it's not really going to cost you anything。And then you have the synchronization between streams。

 So essentially， these events will synchronize that they will be placed in individual streams。

 So instead of the whole device or across all the streams， it's just one specific stream， right。

 that that's the whole idea with these。 And then， of course。

 you can overlap computation data transfer with the prefeing idea， which we talked about before。

 which I believe。Prefeing， yes。So。Events are great for that。 And then we have callbacks。

 which are used slightly differently。 You， you can essentially set up a pipeline where the completion of one operation on the GPU triggers the start of another on the CPU。

 So this is going to have some more overhead， but。If you want to log when something happens。

 when you want to log when something happens on your GPU， then you can use a callback。

 So in this context， we have a kernel and then。You know， in like we， we have a like say。

 say like some stream like stream1。 And then we place this callback right after the kernel。

 So in the timeline， it's going to show up as kernel and Kudos stream at callback just as the way they are from like top to bottom in the code。

 And if they're in the same stream。And we put this this call back in。

 and that's essentially going to say when this finishes， when when this finishes。

 we're going to call this function。嗯。And it's just going to print GPU operation completed， right so。

That's that's like one you use case of callback， you might not use them all the time you're probably going to use events more if you're really trying to get those optimizations out。

 but let's go ahead and look at the advanced section here。嗯。We have current one。

Which is going to multiply by two。And we have kernel 2， which is going to add one。 All right。

 very simple operations。We have our callback here。Stream callback operators completed。

 just print print out when something happened， right and then just sort of like flowing from top to bottom here。

 we do our our kuta stream types， we just declare some streams。We have our Kuta event type。

 which is going to initialize an event。We can print out whatever that event is I was testing earlier so this that's why this is still here。

 We do our kudalic host for that pinned to memory。We could a our device data。

We do our greatest and least priorities like I was talking about before。We create。

 we actually create the event itself using this previous event type that we initialized here。

And then we do our， you Kuta M copypy async。We we launch a kernel and then this is where things start to get a little tricky and I'll do my best to explain。

 So when we do coa event record， that's going to place a little marker like a little tick right in that stream。

 So we have the stream one here this this is on stream one this on stream one this on stream1。

 So you're going to do your your copy from host a device and then you're going to do the kernel and then you're going to put a little tick mark right here。

 And what that says is。we went want to do something when when this gets reached。

 So notice how this is right below our kernel。 So when the kernel is finished， when it is done。

 this is going to this this is going to trigger right。

 And then we have this stream weight event as a little dependency。

 So it's essentially going to wait for everything up to stream stream 1 to finish。

 and then it's going to begin on on stream 2。 So stream  two has to actually wait for is to happen。

 notice how we pass in a stream which is stream 2， So stream stream 2 will start doing its things like kernel execution and and the callback but we have to wait。

For。Where did it go。We have to wait for this event to trigger first。

 and that's essentially all this is， is it just waits for it and then it begins on screen2 when all of these previous ones are completed。

 right？Or at least everything else in stream one， so these two。So。

Then streamam 2 comes along after this is done after we've actually done our。Or an execution。

And then stream 2 is going to run this second kernel。 So it just。

 it's just kind of ordered in that way。 So you have the async could have M copy kernel 1。

 And then it's going to wait for that to finish and then drop down in stream 2。 It's going to start。

 It's going to start the second kernel execution。 And then when this is done。 So when when。

Once we complete this point， this is like another marker in the time line。

 It's going to wait for all that to complete。 And then it's going to say， okay， awesome。

 we can now do a callback。 and then it's going to go up to this function here。 and it's going。

 it's going to run that。😊，嗯。So that's just kind of like stepping through one by one what is happening there。

嗯。And then we'll just copy back to host with kuta kuta mem copypy async。 And then to finalize。

 we always want to synchronize our streams。 So we have all these streams that are happening。

 We have just added another layer of complexity。 We need to synchronize those up to， right。

 So there's the whole device， synchronize， which is like you synchronize all the threads in the device。

 And then there's this one， which is on the level of stream。 So you have like maybe stream 1，2，3，4。

 and you like wait for all of them to like finish before you before you continue， right。

 and you wait for all them to catch up by adding a little barrier blocking。

And and that's what's happening here。 And then we just destroy all of these。

 We just essentially remove all these contexts and then good to go。 So that's that's how stream work。

 That's how this advanced thing works under the hood。 if I go ahead and run this。

So we notice how when when we are printing out， where did it go？When're printing out the event。

 the event is just a pointer。 So it's it's like a， it's just like a memory address thing。

 And then we got our R。Operation completed。 So that's when we do this with when we do this callback and then we end up with the test passed afterwards。

 So， you know， just referencing back to that Nvidia diagram with all the。

 all the different streams like that。 that's essentially what you care about， right。

