# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P8：Chapter 7 (Faster Matrix Multiplication).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

Give yourself a pat on the back if you made it this far。 This has been a lot so far。

 and we've covered， we've covered actually an insane amount。

 And now we're going to cover one of the more technical parts of the course called matrix multiplication and how we optimize it。

So this is going to be one of the most technical parts。

 mainly because we're looking at like low levell optimizations。

 how do we actually speed this up on the hardware And so it's no longer just like the general idea of how it works。

 We're actually using our knowledge and additional knowledge that I'm going to share with you on how we can make on how we can make the fundamental matrix multiplication or the matal algorithm really。

 really fast。 So this algorithm is proprietary and deep learning。 It is everywhere。

 And so I figured the best way to teach you how to optimize kernels would be to use this as an example and luckily。

We have。We have a repo by Simon Bohem。 I think that's how you pronounce it。

 This guys a this guy's a performance or kernel engineer at Anthropic。

 So he probably knows what he's doing。And he made this really cool repo called S Jem Kuda as well as a blog post to go along with it。

 So I'm just going to be following this。 And I was kind of lazy and not gonna like write all of this from scratch on my own。

 So I kind of just went along with this。 And I want to explain to you the steps of going through this and how we actually。

😊，How we how we progress through these different steps。

 getting up to pretty close to coublo performance and gigapflps， or perhaps even surpassing it。

 depending on which hardware you have。 But this is going to be the goal。

 So you might have come across this article already， but。In case you haven't or in case you have。

 maybe this was too hard， I'm just going to go over this and we're going to we're going to go super low level。

 Things are going to be super clear after you finish this part。

 You're going understand how to optimize Kuda kernels。 So let's get started。

 We're not actually going to occupy the kuda course repo with this。

 I'm going to link it in the readme files that you can follow along in case you're just going through the in case you're going through this this course repo。

 but I'm actually going to take some steps back here。

 And I'm going to clone it into my main coa directory here。

 So I'm just going to delete the old version。And we're going to get clone the other repo in。

 so it's just that literally just pop in here， copy， paste this in， go in and get clone that。

And then we're going to go ahead and。Open this up and open this in VS code。

So I'm going to drag that to my side monitor here。Go'ing to close this。And open this one up again。

Now， inside of here， we're going to look at the readme first for setup。

 so we can see that it in the in the build instructions， we have to do， we have to do。Make directory。

 build。See the endtu it。And then we're going to see make。It's going to take take a second there。

 and then we go dash， dash， build。Period， and it's going to build everything for us。

Now the idea here is to build everything， show all the different benchmarks。After。

 after we actually go through each optimization。 So we're going to。

Essentially print out the Kublo performance， and then we're going to print out naive。

 and then we're going to print out the next optimization， and we're going to print the next one。

 next one， next box until we get to the end， and we're going to compare all of them see which one is the fastest。

So。We can go in and start off with。Just going in，2。Just going into here。

So a bunch of different kernels。 We have naive。 We have a global global memory coalesce。

 So if we actually go back to the blog post， which is what， you know。

 I kind of expect you guys to follow， there's not too much here， it's mainly just the code。

 So if we go back to the blog post。We're doing。we're essentially just going in this order。

 and he does it in this order， too。 So the naive implementation， I mean， we've already done this。

 right。I can actually go back。 And if I like， make this full screen。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_1.png)

And I go out of this。And I go into the cota course， writing your first kernels and then Maal。Notice。

I'm going to copy this for a second。

![](img/0f9ea5e8bacc4cc914094ea7b918190a_3.png)

And then。We're just going to paste it inside of here， just for reference。

So we have these two kernels and I just want to and I just want to make sure that we're all like caught up here。

 The one I taught you before is the exact same one that we're showing here。 So this takes in A。

 B and C。This one takes an A， B and C。 It takes an alpha and a beta as well。 I mean。

 it's doing it's doing a different， it's slightly different operation。

 So it's not exactly matrix multiplication， but it's it's essentially doing this this essentially the coub loss Mamal that I showed you before where it does the alpha term like times every single element in in in the matrix that we calculate in an actual Mamal output and then it adds。

Beta plus plus a C matrix。And then assign C to that new one。 So it's a slightly different。

 it's a slightly different operation that we do。 But we're mainly going to worry about the matrix multiplication mechanics that get us to this temp variable。

 So when we look at this。 We have M， K and N。 So it's a matrix of shape。 So a is shape M。

 So it's like M vertical， That's like the batch size you could say。

 And then it's like K as like the length number of columns。 right。

 And then the B matrix is going to be K vertically in n long， right。

So we essentially pass it in the same way。 and we index them same way。

 But in this example in Simon's example， we just pass these in differently。

 So it's like M and N as like the edges and then K is the middle one that we want to pay attention to So we save that for the third one。

 I guess maybe thats the thought process there。 But anyways， we have we have x and y。

 So row and column the y is the same as the row here。

 So which which y index is it at because a row like row is vertical could be this row。

 this row like vertical scale right， And then the X is is column。

 So which which column is it at this is horizontal。And so we make sure it's not out of bounds。

 And then we continue with what's inside of that little chunk of memory。 and we proceed， right。

 So we have this accumulator sum。And then we have this L term。

We could say that's the length and and then we have this k which which is the length of a and then the height of the height of B right So when you're dot producting you're taking the the row a row of a and a column of B so you're iterating over you're iterating over K and a and you're iterating over K in B right so that's where that that comes from that K stuff and so you're just itating like。

In a row， you're going through a like this。 You're going through each piece like each number。

 And then in B， you're going through each number vertically， right。

And then we just plus plus each time。And then theres sum output。

 this accumulator is just going to be。Essentially， B。 So A， we're looking to multiply the first。

 the first element here by the first element here。 and then。

 and then advance and then advance and then advance and then advance。 right。

 That's what we're trying to do。You could also think of it as like a nice way I like to visualize this is like a two by two tile。

 So you have， you have like a two by two tile you have。

I'm going to try to visualize this from your perspective。 You have like a up here。

 and then you have B down here， and it's like。Is that。Is that correct。Maybe it's。Maybe it's， yeah。

 it's a here and then B here。 And so when a has like a row。

 that row is going to like point to like the。The a Y coordinate in C and B is going to point to the X coordinate in C。

 So when they like， when they like intersect， it's going to find the the index in C that you're going to calculate that dot product result from。

 That's a cool way I like to visualize it for。But， anyways。Then back to the point。

 So we have this row times times k。 So like which we're over at the length of the row， right。

Or sorry， which which row are you at。 So which row relative to you know the the couda architecture itself。

 And then K， which is the length of it。 So you're going down， you're essentially like wrapping。

 you're striding around and you're doing this as many times as you want to as depending on which row you're at。

 And then you add the K offset to it。 So you might not be all the way through the the length of it。

 And so you stop。 And that's where that plus comes from。And then same thing for here。

 we have this L term， which is K。 So how essentially which column are you at， right。

 So here we have rows。 And then here we have columns。 So it's L， which is。

Essentially the the length of of that vertical the length of a column。

 and then you iterate over you iterate over n times， right？ So N is the n is the length there and so。

You essentially， you essentially advance as many times you need to to the。To the。

 I guess you could say to the right。 And then you offset at whichever column index it is。 So。

 so same idea， we're just， we're just advancing instead of。Instead of going rows。

 we're going columns。Right， and then we just essentially assign whichever。And see。

 we index it like we go row times times n。 So it's an， it's an M。 It's an。It's an M by N。

 So it's going to be。Like M is here， and N is here。So it's going to go。Row number times n。

 so it's going to stride in every time it wraps。And then it's going to do plus the column index。

 which is that x component， right？And that's how you do the naive again。

 just just to give you a little refresher there， That was a while back。 We did it。

 And then the same idea here。 So you have。M and N， M and N。You have the accumulator。

 we have this i term that iterating through， and we have K。And then we go， we have this temp term。

 and we go x。 So x is the same as rh。 So notice how rh is so assigned to Y， then x is。

Where I actually got a little bit stuck there。 I was looking at the the block and thread indexing scheme here。

 and it was kind of misleading。 So like notice here how we have rows And those are by the y index。

 So whichever y position it's at， That's like the row that it's going to pluck out or the column it's like x。

 So it's going to pluck out a row or sorry a column in this in this example。We do like X。

 So that refers to like right here。I。Is picking out like it kind of makes sense， right。

 like X matches up with X and y matches up with Y。 But when we look in here。

 like in comparison to this， it's like the row times the stride of K。

 We're going to stride the K length over and then then come back to the next one and then offset with L。

In this one， we have X， which is like a column index， right？ So it's like， why would you do that。

 We want to we want a row index， But this actually works。

 And we don't have to worry too much because this is a square matrix。

 So because these values are actually the same because the grid and and the thread index in both the the x and y dimensions are equal。

 We don't actually have to worry about that。 So this is something you don't want to pay it under to in rectangular matrices。

 But we don't have to worry about this right now。 So just kind of assume that we can kind of just say that this is like y and treat it that way。

 But I'm not going to edit this because we might have to deal with this later on in in future kernels。

 So。You kind of get the idea though， this is very similar to what we were doing before。

 don pretty much just don't worry about the indexing scheme， it's going to be fine。And then， we。Yeah。

 literally the only change here is that we write out using alpha beta and C right。

 So that's really the only difference there。So let's go ahead and actually run this now。So。

We pop into S G Kuda， and then we go into build。Now we can go S Jim， and then we go number one。

 So this is the naive kernel that we run。And we can see that we're going to do a max size。

 So dimensions M equals n equals K， right So these are。Okay， I might have liked there for a second。

 but yeah， I mean， as we can see， dimensions M equals n equals K right So these are all the same just like 128。

 essentially， and then 256，5 to 12，1024 all the way up to 4096。

 And we can actually see the throughput and giga flops per second。

 So what this means is how many billion giga right giga is  one times 10 to the 9。 So billion。

 and then flops is floating point operations per second。And this is on a given size， right。

 So on size 128， we get on average，46。2 gig billion floating coin operations per second and on 4096。

 we get about 166 billion floating coin operations per second， which sounds like a lot。

 That sounds like a lot of operations， right，166 billion per second。 Wow， that's really high。

 But the answer is that's actually not that high。 It's going to get a lot higher than this。So high。

 actually， that it， it's going to seem like this is minuscule。 It's going to be seem very。

 very small， and actually slow。So notice how this took this took。8 about is 0。

83 seconds to do 50 runs， right？So very very slow or no per per run， sorry， So not for 50 runs。

 but for for each run that it did， which there were 50 of， it took about 0。

83 seconds to do that on 4096 within Aive kernelel。

So a few other points before we actually jump into this， I want to first look at the。

I want to first look at the blog post here， so when we're calculating the output in the9 ofmentation。

 I mean， like even just like looking at this is like really intuitive， I love this example。

 but anyways。When we actually look at the simple naive kernel。Essentially， we're trying to。

We're trying to find。A certain part inside of。We are trying to find a certain index inside of C that is going to be the output。

 So we're saying。We want to do the fastest possible calculation to get， say， this number。

 this index calculated in the C output right in C。And so right now， the way to do that is to load in。

A row and a column。 And then just just calculate that。 That's。

 that's what we found out naively so far。 And it takes very few lines of code to do that。

 And so we just kind of iterate through， like I was saying before。

 how you put a on the side here and you let it， you let them sort of act as coordinates。 That's。

 that's what I was referring to there。嗯。But anyways。

That' that's kind of one of the goals we want to keep in mind is how do we calculate the output index it'll help you it'll help provide some context on how we actually get there because when we deal with marked complex kernels。

 you'll actually see there's a lot of steps to actually get to a certain place and so it helps when you're able to keep in a consistent frame of thought where it's like okay how are we actually ending up at a result and then you can sort of backtrack through and see what's happening。

So instead of just like going and like reading like a novel from the start of the kernel to the end and just seeing like。

 oh， I guess like we'll see where we stumble into。 It's like you actually want to see what you're trying to calculate in the end and that helps。

 And and this blog postified of context on that。 So another little note I wanted to add is like don't worry about 3D structures too much。

 So when we have the like the dim3 type。 And we have the Y X and Z dimension is all populated with numbers greater than one like 4。

2 and 3。 It's like don't worry about that。 We're not going be dealing with3 It's not going be that complicated。

 It's gonna be more so like how do you transform one dimensional and two dimensional。

Dimenssions and index efficiently。So don't worry about 3D stuff。

 we're not going to do any of that and then。The actual indexing scheme here。

Is giving us coalesced memory access。 So I'll jump into this in the next term a little bit more in depth。

 But essentially what's happening is when we when we're doing this like row calculation， for example。

 what it's when it goes through each row， essentially what's happening is we have this。

 we have this like X term from here， and we put this X term in， all of the like in couda。

 when you have adjacent， meaning like in the X dimension in in like the length part， horizontal。

 when they are next to each other， you actually get coalesced memory accesses。

 So when you're accessing a。You've actually you can actually in in assembly。

 it's actually going to group multiple of those together into one。

 So when you have like when you have a a block inside of that。

 you have a warp and inside of the warps， you have。You have 32 threads per warp， right。

 and so we can。Like in inside of the actual warp itself。

 it it's going to coalesce memory access if possible。 And when things are adjacent。

 it actually makes that possible。 So that's kind of why we're seeing the weird indexing scheme here。

 again， doesn't work for rectangular matrices， but in this case。

 it's kind of an efficiency improvement for indexing the a matrix。

So before we pop over to the global memory Coles kernel。

 thought I should probably highlight something。This is important to know for all kernels and even the previous ones too。

 but this is just kind of like how memory is laid out right， So when we have a two by two matrix 1，2。

3，4 in memory， this is going to be laid out as literally just a vector，1，2，3，4。So when we want to。

 like， for example， in a， when we want to go to the next。

 essentially the next row and then do an offset。 what we're doing is we're going a current row。

Times K， which is this dimension here， the the the horizontal one。

 So we're doing let's just say we want to get to the number  four here， right。

So if we want to get to number four。It's going to be current row。 Well。

 the current row is going to be0 and1 right So current row is going to be1 and then K is two long。

 So it's going to be one times2， which is going to give us this index。

 So like the array at index 2 is this is like 0，1 and2 And then the offset from that it's going to be the column index。

 So that's going to be one。 it's going to be two plus1， and it's going to give us array at index 3。

 So that's just kind of what I mean by strides。 It's like how how you go and you like jump across the whole row。

 That's kind of what I mean there。But going into this globe memory cholesterol kernel， F down。And。

And I'm just going I'm kind of going to like skip this part and this just laid out for you。But。

The whole idea here。 and this is the critical concept。 So the matrix memory layout。

 as I just highlighted， it's going to be， it's going to be consecutive memory like this。

 it's going to be it's going to be laid out like that。And this is not going to be consecutive memory。

 right， So when we do dot product of this and this， it's going to go to the third third row。

 and this is going to go to the third column and we get this value， right， This is a consecutive。

 This is not。In the naive kernel， we jump through these and weerate through we iterate through a。

 so we start this like B column and then we go2。And then we go to the next one。Right。

we index in that fashion and we advance through the arrays in that fashion and what we end up with in the output is we get this like we get this stack of blocks right and this is what it looks like when we write to the output it's going to be a stack of blocks because we write vertically as the rows in A。

 that's what we prioritize。However。If we instead。Coes the memory accesses。呃。

We can get we can get these laid out in this fashion。

So essentially what we're doing is we're changing the indexing scheme here。

 All of this essentially remains the same， except we change the way that this is indexed and we ensure that we're using thread ID X right So remember when we did when I was previously talking about how all of the essentially all of the all of the the X like the thread Ix or X component that those are grouped together in a warp。

 So if you have like， for example， block size 32， there's going to be 32 threads in a warp。

 that's the maximum and so in in like blocks， if you have this like this square block。

It's like 32 by 32。And you get the X dimension， you're going to get the maximum number of threads in a single warp if each element there is dedicated to a different thread。

 right， And so this way， you're maximizing the memory accesses because you can put all of those together and you can make that load you can make that data transfer operation。

 much more efficient when you let an entire warp take care of it。

 It can do all the values at once or group them together and make them like way faster as opposed to going through each individual each individual like Y component Right when it goes like thread ID X dot Y。

 It's actually。It's actually not as efficient， right。

 And so we kind of just change the indexing scheme here with these。

So to sort of illustrate the previous point， I wrote a little table for like what's in the brackets here。

 so this division of thread IDX and block size then the mod or the modulus of that So I just kind of wrote at a table here of what these would actually look like in practicality So if we just assume block size is4 which mean it's not in this case but we can to simplify and understand what's going on that way I don't have to write it like a bunch of numbers we assume block size is4 and so because block size that the size of an individual block is4 that means the thread IDX is going to have four indices in it so it's going to be thread IDX0 and then12 and3 it's going to have four inside of it right。

So when we divide， we're going to floor the operation。

That's just what's going to happen naturally is this is going to get floored。

' it's going to truncate the end of it because we're doing integer division。And。We're going to get 0。

0，0，0， right，3 divided by 4 is 。75。 It's going to tru it 75。 and you're still going to have  zero。

 And then we jump up to when like this advances。Then it's going to be， well， the block size is 4。

 And when the I X jumps to1， then it's going to it's going to be1 times 4 is 4。 and then plus 0。

 and it wrap it kind of just like resets right， except it's plus  one。 we have that going on。

 And then we have the modulus as well。 So modulus is you divide。 So 0 divided by 4 like integer。

 and then what's the remainder of that。 So if we do one divided by4。

 that doesn't actually equal a whole number。 So you end up with the remainder of one。

 And then you do that for the rest of them。 So like3 divided by4 is earth 3 mod 4 is 3。

 and then four mod 4， since it just equals 1， there's no remainder left。 So which is is0 right。

 And you get this thing where it's like 0，0。0，0，00，11，1，1， and then here it's like0，1，2，3，0，1，2，3。

 right？So。When we actually look at this example here inside of the。Where is it， no。

 not this one inside of the coal kernel。Notice how in I'm going to show you a second in our code。

How this row does not actually change And what we're doing is we're just indexing very carefully these values。

 So when we're， when we have different threads that are like because each thread is going to calculate its own dot product。

 right。Like this thread and this thread adjacent to each other in the same warp。

 They're going to access adjacent values。 So when they're accessing adjacent values in the same warp。

 you can actually group all these together。 whereas instead。

 if you just did this one defeated this thread and then this thread and then this thread。

 that means that the first index of all those， all those threads。Um， you cannot actually。

 you cannot actually coalesce that because you have to do like a stride and they're not。

 they're not adjacent， right？So that's essentially what we're doing here。

 And then we end up with this， like instead of a stacking like blockss。

 we end up with this with this horizontal layout。So I'm we go here。

 we can see that C row so this is only actually going to change every every time we advance right So this is going to stay at0。

 which means that C row that's going to stay at0 and then the plus I part that's going to advance with with the dot product itself and then here I is automatically going to advance So that means it's going to it's going to advance a column each time while the row is going to stay at the same place because C row is staying at zero And so you can kind of see how this works out we have C column or current column and this is actually going to change over the threats。

 So it's going to go0 it's going to go 0，1，2，3，4 and then it's going to jump to the next block block IDx right and so what you end up with is literally what I just demonstrated。

You end up。By essentially， each， each thread within that warp is， is accessing an adjacent value。

 And so you can group those in， and coesce or combine the memory aes together。

 And we get more performance efficiency with this。 So that's kind of like what this article that this section talked about。

 And if we。If we bump back to here and actually run this， so kernel number two。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_5.png)

We can see we're actually getting a lot higher biggerap flops on this one。呃。

And then we can see that we get about 1183 gigapopps here。

 So that's actually a pretty big increase of performance， I think。Previously， it was in the。

 it was about 100 and。What was it like 1 80 or something or like 1 hundred and60。 I can't remember。

 But it was very low。 So this is actually like a significantly， it's like 10 almost 10 x higher。

 This is like maybe 5，8，10 x higher than what we had before on the 4096 square matrix， right？

 So that's actually a crazy performance improvement。

 We were previously at like  point83 seconds per per。Per run。And now this is at point about 012。

 So if you you actually do the math there。It's。83 over。12。

 that's about a7 a increase in performance and throughput， so。That's pretty good。Now， we can。

Now we can move on to shared memory cache blocking， which introduces a different concept。

 still uses what we've currently done， but introduces a whole not paradigm that's going to really help accelerate and speed things up。

 The next picture I'm bid to something called shared memory or SRAM。

 And this is absolutely critical to take care of when we're optimizing algorithms for performance。

 So let me just kind of explain what the deals with this。So。

Right now we're using global memory right the host is just our little Ram slots going to the CPU and that's like really slow。

 that's about 5 gigabtes per second， still fast but very slow compared to this 200 gigabtes per second that we get with our VRA this is what we're using now。

 or you can get even faster and use shared memory which is around 1。

5 TBabytes per second memory bandwidth or registers。

 which is about 8 terabytes per second of memory bandwidth。

 but we're just going to focus on registers right now。Or sorry， share memory right now。嗯。Now。

 in this blog post， he had about 700 gig of glove memory bandwidth which is really fast compared to this。

 And then about。12 ter of 12。1  TBytes of shared memory bandwidth， so。Or sorry， not 12 terabytes，1。1。

1。2 terabytes memory bandwidth， terabytes per second。Now。How do we capitalize on that。

 How do we actually use shared memory。Well， it's actually easy。

You use this little keyword called it's not here， but。I have it。 It's called a shared， so。

Shared memory is literally just how you use the that shared that little L1 cache。

 So when we look up at the actual architecture of this， I could open image in new tab。So。

You have your globe memory。 So like the big chunk of memory that you have。

 that's about00200 gigabtes a second。 then the L2 cache for like a transfer medium。

 And then in each little S M or streaming multi processor。嗯。

These have their own little L1 cache or the shared memory。

 and this is very small compared to these two， right。

 but they are extremely fast and they connect directly with the registers and again the cores on your GPPU。

So when we can utilize these， there's actually far less travel distance you have to go。

 so instead of like every time you need to access a float。

 you go all the way through like Smem or shared and then dialL2 and then to global。

 you literally just store a bunch of them temporarily S in shared memory。

 have all of the threads use them for like essentially do a ton of work with the memory that it has。

And then once you're finished with that， you can replace it， you can write new values from global。

 so instead of writing from global every time you need to access something。

 you instead you preemptively load a bunch into shared memory and then you use them for a bunch of work and then you replace them with a new one once you advance。

 right？And。Sort of the goal here is just making sure that we do this properly。

 So if I just go out again。Shirt memory is located on ship。 much lower latency。

 high memory bandwidth。嗯。He this on avault to GPU。 So to go over how exactly we'll be using shared memory。

 it's actually a bit of a different philosophy。 Now， I'm not going to like， do like。

 write this out and everything because it can get like quite， it can get quite。

Intensive when we write stuff out。But。This is essentially what we're doing。

 We're doing a little thing called tiling， which I demonstrated earlier。

 where you have little tiles that you do matrix multiplies for in a bigger matrix multiply so。

Instead of doing， instead of doing rows and columns。

 we actually goat and do something a bit different。 And instead， what that is is。

 is say we have this， this chunk in C here。 And And so what you would do is you would essentially like。

 if you have。Say a。Let me try to use the current VS code thing as an example so。We have this。

 We have a， we have a C， right now， going back to。Going back to this one。

 I'm going try to explain is tough to explain。 to bear with me。

We're essentially going to load in tiles and we have this little C like the coordinates here and all we're going to do is we're just going to multily multiply these two together and then multiply these two together and multiply these two together and then like we just essentially multiply every matrix and then that like coordinates up to this final thing here So we go we go like through this way and we sort of we start at the very like the very top of B and the very left of a and we multiply those together and then we add it to the next ones we go in and in and and in and until we like maybe cross or something and then that like intersection point。

That intersection point right here。That's where C is right And so when you have a bunch of these smaller。

 less intensive mamals that can be actually done on blocks on thread blocks。

 then it actually makes the job a lot easier because what you can do is you can be smart about it and actually store these blocks in shared memory right if you're doing individual rowsor columns。

 I mean sure you could do that， but it actually allows us to distribute some of the work more when we're using blocks when we're using literal tiles of the matrix right？

So let's go ahead and dig into how this actually works under the hood。

 You're going to understand sort of how tiling works more once I explain it and how I explain how everything advances as as we dig more into detail。

 but。That this is the idea here， we we tile and we store these blocks temporarily in shared memory and do as much work with them as possible。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_7.png)

Okay， so this is a code for a shared， a shared memory cash art or tiled Mamal， you could say and。

Pretty much a lot of it well not a lot of it， but the start is pretty close to or actually the exact same as as the last crole we wrote。

 So we have this the row maps to block ID X dot X。 the row maps to block ID X dot X and C column is dot Y。

 C column is dot Y。Now， we have this。The column。Is。

Maps to the mod operator and then row maps to division operator。 right。

 So row maps to division and column maps to mod， right， So these are these are the。

We essentially use the same idea as before， and then we add this additional piece in。

 which is going to allocate some space in the shared memory。

 which is going to be of size block size by block size right So it's just giant thing you could say that like each of these little rows just like wraps around and you have this like super long thing laid out in memory。

 but we're going to treat it as an actual block like a square。

And so why we use block size by block size is because if we just say I mean， we're to lower。

 we're going to lower what we interpret block size to be in the examples just for intuition purposes。

 but in practicality， this would be 32 right block size will be 32 you have 32 threads that fit in a warp。

And maximum1100024 threads per block。 So if you actually divide。If you divide 1024 divide by 32。

 you get 32。 So what we end up doing is we have a war a warp takes care of these。

 warp takes care of these warp takes care of these。

 and we have like we're literally taking up the maximum amount everywhere just by using block size or a shared a shared allocation of block size by by block size right that that's the idea there。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_9.png)

And so we go down and I'm just going to pull this up on the side here just for reference。So in A。

What we do is we say we're going to advance the pointers for the starting positions， right so。

Essentially， we're going to multiply。C row， we're going to do C the the the current row times times oh then zoom out the current row times K。

 right， So K is going to be this dimension here， this， this， this long one。

 the the sort of the horizontal one。And so if we multiply the current row by K。

 let's just say we have like a current row of。If we have a current row of。

If we want to do current row of one right so we want to do current row times k which is this length so it's going to jump down to this one and then we want to do times block size which in this case since we split it into a bunch of tiles is going to be two right it's going to be two by two and so we end up jumping two instead of that so we go the current row is going to be one so we're going to do this this one here so it's going to jump the length of that。

Times the number we want to do， which is essentially one。 So we want to jump down one。

 And then that doubles because we have blocks size equal to  two right。

 So it's going to jump two rows， and then we end up exactly where we want。

 We want to start at the first number。On the first， on the first like essentially tile of this row。

 right， and then B。we advance that pointer to the current column times block size。 So in this case B。

 let's say we want B to be like two right， So the current column is is two So we do2 times 2。

 which is4。 So we go0，1，2，3，4 and we end up there right So very intuitive and then we have C。

 which essentially combines the two。 So in this case we want to do C。

 So it's going it's going to be like。It's going to be this row and this column here。

 So we're going to end up。 It's going to be the the first row and then， and then this column。

 So it's going to be this tile。That we want to take care of。 So it's going to jump。

 It's going to jump over to this one from the。From the。

What's it called from from the a matrix that we're going to jump all the way to or what was it。 No。

 no， no， in B， we're going to jump all the way here。 And then in a。

' we're essentially just going to add the we're going to add the offset， right， So we want to。

We want to jump down to。Because this is the end dimension。 So instead of multiplying by K。

 we would do。We would do， we would do times n。 So it ends up being like essentially this。

We essentially this plus this， right， except instead of instead of using K。

 we use n because that's that's the length of C， right， So that's the idea there。

 And then we end up at I believe it was this， this tile the 24， 25， 34，35。

So we continue to go down and this is where we define our accumulator， right。

 so the temporary accumulator we have。And then stuff really gets interesting we once we get inside of this for loop。

 this is where the magic happens。So we have this term block IDX and we're going to iterate over k right so k is that k is that the row the sorry the column the columns number of columns in a and the number of rows and B right so we're going to advance block size each time we're sort going to advance block IDX by block size each time。

And so inside of here。Initially， we want to store the stuff in SRAM， right or shared memory。

 So we want to store it in here。And literally， all we do is we look at the index inside of here。

 So thread row， which row is it times the block size。

 So block size is going to be that stride or that wrapper。 And then plus the thread column。

 So which offset do we want to be at， right， It's going to pick out a certain spot in there。嗯。And。

 luckily enough。I picked a block size of two， so it's going to be two by two and that actually makes our job a lot more simpler to understand。

 I mean you can abstract it up to like 4 or 8 or even 32。

 but we're going to stick with block size of2 for now。

 and this means we're just going to have we're just going to have two a threat index threat IDx do x of0 and1 right？

So very， very basic threads to work with here。 And so we're essentially just going to load into this this shared memory which we defined up here。

 and we're just going to essentially that that little spot inside of it're going to we're going to pick that out from A and B。

 So in a it's going to be the thread row times K So K is going to be that that that length right。

And then it's going to be。Plus the plus the thread column offset right。

 so just that that essentially the same idea as what we're doing here。And then we're gonna have the。

Same idea for B， which is going to be N。 So N is that again， N is the。And is the top one here。

 And then K is the top one here。 So K corresponds to A and N corresponds to B， right。

 I hope that kind of makes sense。 And then afterwards， we just sync up everything。

 this part's a little weird because we're doing like sync threads， but this kernel itself。

 like everything in here up till now is like a thread。

 So what this means is that in the entire block。 it's going to make sure that all the threads catch up to this point。

 It's gonna to make sure that it's going to put a barrier and make sure all the threads have like put what they needed to in memory。

 or else if we start doing other things。 then you might have like a zero value there where there's like there's nothing that exists at that place in memory。

 And you're using that to do operations， which is then going to make your answer wrong。

 So you want to make sure that all of the threads within the block are actually caught up to here。

 So like these are on the level of threads。 But we're essentially telling couta that we want all of the different threads that are doing all these parallel operations to catch up within the fore loop。

 That's what we're doing。嗯。Then we advance a。Then we advance a by block size。

 So this is just like advancing it preemptively。 We already have all of the stuff there stored in shared memory。

 So we can actually just advance a。 we can advance we can advance the a pointer because remember A is a pointer。

 right We can only actually use like the index to get the values。 But a itself is a pointer。

 So we advance that in memory， we advance that in the memory space by block size。

 So a is so a is like this this side one that's like going to point inwards to C。

 and then B is going to point downwards。 So A is going to advance a single block。

 So if a is like here， for example， A is going to advance block size。 So two。

 it's going to jump here。 right，And then， B。B is going to B is going to do the same。

 but it's going to jump。 So it's going to go。It it's just going to it's going to jump n， right。

 So it's going n is like this length。 It's going to do block size times n。 It's going to jump。

 It's going to jump down to right， and's it's going to do exactly what we want。

 So it's going to advance the tiles in the directions that we expected them to。

There might have had been some confusion about how we're just using like the thread columns。

 And just a reminder these， this a term is already advanced to the correct position， right。

 So once we're advanced to like this， this tile， for example， then we can just。

Then we can pretty much just use threads， we can use the thread indexing scheme。

 and that'll give us exactly what we want。SoNow notice inside of this for loop。

 we have the same indexing scheme as we did in the global memory coalesced kernel。

When we when we're just efficient about going through the columns and having the C as like as like a horizontal layout instead of like a vertical stack of blocks that we're just doing the exact same thing here。

 right？And so you might be wondering about this temp variable。 So this temp。

 this temporary is just is just going to start off as nothing and all we're doing is each thread essentially each thread has its own temp variable right。

 that's going to be stored in the register Each thread has its own temp variable and it's going to accumulate this temp variable for it's going to accumulate a dot product。

 So what this is going to do。I is not actually going to multiply matrices together。

 Instead of what it's going to do is it's going to just accumulate as it goes through tiles， right？

 So as it goes through， it's going to like accumulate each value in the output of C as it as it goes along。

 right？ So based on the thread， it's going to say say one is going to do like the row of this one。

 and then the column of this one， right， And so when they when they interact together or when they when they interact。

 they're going to end up at like this top left part， maybe。

 and the thread holds the temporary value for that specific part。

 And what it's going to do as like as it goes down through the tiles。

 it's going to accumulate this dot product， right， So you get the first。

 you get the first dot product。 And then you add it to the next one from the next tile。

 because you're essentially just doing the normal naive matrix multi。

 But you're just accumulating through the tiles。And so in the end。

 you end up with just this accumulated temp。 However。

 this is only for a single dot product operation。 This is only for one tile。

 And the reason why we have this for loop inside of this one。

're being very clever about this is so that we can actually do this accumulation through the tiles right。

 So that way we can kind of be we could just be clever about how we go about doing that。

 And then after we're finished， we can just go ahead and you know sync up all the threads。

 make sure that they're all caught up before we actually write this out to C。

 So I guess just going a little like iterating over this again。

 the thread row So that's like which which row within the tile do we want times the block size。

 So that's going to be our wrapper and then the dot IDx is going to be how reiterating through it。

 So a is row。 So we're gonna that's the dot ID X we're going to go through this way。

 That's going be the offset。On the horizontal part。And then B is going to be。

Dot I X times block size and then plus that offset as we were doing before。

 right So we're maintaining that global memory access that access pattern that we had before and we're and we're just simply writing out that temporary variable as it accums through the tiles right So that that's the idea here is we're accumulating through the tiles。

 So now we can hopefully that makes sense。 feel free to watch some parts of that。

 feel free to plug it into something like chat G or clo onnet or something like that and try to。

Jd to visualize what's happening。I have I have a separate additional like diagram here just of like what this looks like laid out I decided to add this to to the course assets folder inside of the faster mat section。

 So if you want to check this out， I might add other ones to it thats this is yeah this is the shared memory blocking K kernel。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_11.png)

So now we can actually go in and and profile this thing。

 So pop up into here and just go S gemm number 3。We run this for a second。

 It's going to be really fast。 And so if we actually compare this， give it a second。

 it's doing the the last one there。 So if I actually compare this to number 2。Which wasn't。

Give it a second。Yeah。So our number two， with just a co memory access was achieving about， you know。

 1200。 And this one is achieving about 600。 So we have a decent improvement from that， right， but。

I probably should have done this earlier， but just to like spoil， to spoil the surprise。

 kubloss is actually a lot fast。 Everyone the00。Kublos is about 11400 gate flops or 11。5 terra flops。

 which is really fast， especially compared to our previous。あ。Our previous naive kernel， right。

 this is extremely fast。Now just to iterate， before we move on this this shared memory kernel。

 this is not implementing like the full version of Tling。

 This is just implementing like a partial dot product version of tiling known as blocking So when we when we accumulate like dot products that's not actually like the full like the what you would into it as tiling right Tling as I described before is when you like take the matrices you multiply them and then you you advance and then you multiply again and you like add them every time they multiply。

Eleement wise。And this is not what we did here。 What we did was a partial dot product。

 So keep that in mind。 the next one is going to be a little bit different， though， so。

1 D1 D block tiling is a bit more advanced， but we'll get through it。

 So just to help get tiling crystal clear in your head， I'm going to use two matrices as an example。

 just to show how this intuition works。And I've actually written out， I did a little。

 I was testing a little bit， and I did the math wrong by hand。

 so we're just going to use use the computer for that。But I wrote a matrix A here， so 1 to34，5 67，8。

 9111231516， and then this one B， it counts by  twos but it goes backwards so 2，4，6，8。

 1012 1416 and then continuous up to 32。So I've written these out here in the terminal and if we just do a。

老怪皮。We notice that we get this out result。 And these are pretty I mean。

 these are pretty easy numbers to work with， right？

 So what I want to do is work specifically with this upper right tile， the 200184，56，404。

 That's exactly what I want to work with。So how we're going to do this is use we're going to use an idea from here。

嗯。To get this top right piece， we essentially want to cross inward， right。

 So we're going to start off with multiplying a this， this a portion。With， with this B portion。

 we're going to multiply those together A times not B times a， A times B。

And then we're going to add that with the product， the， the major small product of。

This piece and this piece， right？ So if we start out first by doing 1，2，5，6。You can go。Stay。A。

At tempemp。Forch dot， tensor。And then inside of here， we're going to have smaller ones。

 So it's first going to be 1，2，5，6。And then we multiply that with four shots， tensor。Torchaw tensor。

42，1210。Right。And if we print out a1。We get this results。Now we do B1。Tor up， tenser。

And I'm just gonna print the actually， I' I'll， I'll just print the layout here。 We'll do8。

 We'll do the same idea for a temp。 but I'm just going to remove these values。

 and we'll replace this with with B temp。So this is gonna be。Three， four， seven， eight。

Multiply that with 2018，2826。201828，26。 All right， Okay， awesome。 Now we print out V1。No。

And then we do a temp。What's B1。And we get the result that we were expecting，2001，84，56，40，4。嗯。201。

88，4，56，404。 And that's a top mammal。 that's really all there is to it。

 Its just helps when you're able to draw this out by hand and understand what the purpose is when we like。

 advance， for example， when we advance pointers by like a greater offset than like one or two or three or4。

 It's like when you're skipping entire rows and you're going to like a certain when when we。

 when we do that stuff， this will help you understand why we're doing it。But yeah。

 we can go ahead and begin。 Asome。 So now let's go ahead and look at the boilerplate code for this。

 as well as the runner script for this so。

![](img/0f9ea5e8bacc4cc914094ea7b918190a_13.png)

In the runner script willll actually pop down and you can see each little like function and how we call everything in here。

 So like the Kub losss function， for example， there's like different ones。

 it's like FB32 Braflow 16 tensor float 32 right and then we have like the naive of the coales the shared me cache in which we just recently did and then we have the one D block tiling right So notice how in the shared memory block we just have 32s everywhere we have 32 32。

32， 32 and 32 right everything' 32 because everything is a square。But in this one。

 we actually mix it up a little bit。 So we we have these essentially this this block。 so M。

 it's going to be this this block on on a so it's going to because it's specific to A and C。

Becauseuse when we do our， our like our matrix multiplication shapes。

 we're going to cancel out the inner ones K。 and then you're going to be left with。

We're going to be left with M and N， right。Just pay attention to these shapes here。

 We also have the8s down below。 So just just like be aware of this， we use。

 we use different shapes here to help speed up operations because we introduce a new concept and that concept is。

1 D block kling for calculating multiple results per thread。

 So if we actually go back into the shared mem blocking of when we write the output。

 we have the specific index per thread that we write out。 It's just one。

 We write one output of that block。 or or sorry of that tile。 and that's it。

 We just leave it at that。 There's no iterations。 We're not we're not running multiple per thread just one。

Now if we go to here， we notice that we're actually writing multiple。

 so we go over this res or this result IDX that essentially goes， it iterates through TM。

 which is this term that we found in here， which is essentially threads per M dimension。

 you could think of it that way。In short， we're going to be writing out multiple results per thread and that's going to speed up everything a lot。

 So like imagine if you had to do you had to issue a new thread every time you're going to write an output of this entire matrix。

 So if you have 486。By 4096， that's going to be about 16 different threads that are writing out。

 that is a lot of threads。 You have to get。There's a lot going on there。 So when we。

When when we use when we iterate over， we can get one thread calculating multiple and make things more efficient。

 it does make the indexing more complex and this is probably one of the most intuitively difficult kernels to understand。

 but once we get there it should be a breeze。So going up for our boiler play code。

We have this C row is block ID x dot y。 So we're going to use blocks。

 Each individual block of threads is going to calculate a specific tile on the output right。

 So we have this block essentially the current the current row and the the current column。

 So current row is like。It's like like vertical， which row are we selecting。 And that's why。

 right that's vertical。 And then a colon like we' doing before it's。Horizontal dimension。呃。

Now we go to here。Which is。Essentially， the， the threat。The。

 the lower level thread column within that。 So we have this， we have this B， N term that's used。

 And this B， N term， we remember back to here， was 64， right。So let me pop back to this。This BN term。

We see it in both the B matrix and and the C matrix， right， this is B N， right。

 It's that length right there。So， when we actually。When we do mod Bn。

 what that's going to do is it's like if if Bn is 64。

 it's going to be like3 ID x like0 divide by that。 it's just going be0 right。

 and then it's going to go 1，2，3，4，5 because we just have this remainder that's like not 64 right So once we pass 64 then then it's going to loop So it's it's going to iterate through all the columns and it's going to go up like 0 to 63。

And then once we actually hit 64， it's going to。It's going's going to divide right。

 so it' going to up， it's going to floor to zero for each of these indices leading up to 64。

 and then once we actually hit it。It's going to divide and it it's going to go to one。

 right because it's going to floor down to one。 And we're gonna to be。

 it's going to be like a bunch of zeros and then a  one， right， And we use this to pick out our rows。

 So the columns， it's like 0，1，2，3，4，5 all the way up to 64。 And then the rows。

 It's like every time we stride this many。 It's going to， it's going to bump up one。

 So the division is going to go up to like 1 and then 2， and then 3。

 every time we stride that 64 length。 And then it's going to increase the row index So it's going's essentially going to be like。

 like I said， a row index。 It's going move us downward， right。In C。

 and this is this is kind of why we we have this here so。Moving further down。

We have the A shared and the B shared。 So just the normal shared memory that we allocate So it's going to be M by K and then K by N。

 right，' that's the space we're storing。And then in specific in this specific thread。We advance the。

We had。We advanced the block tile to the beginning of A's row and B's column， right。

 So we did the same thing in our past one， where we advanced everything forward， right？

 So this is literally。This is literally the same idea， right？We're doing the exact same thing there。

 We're just using a little bit different terms because it's now rectangular tiles。

 These assertions here are pretty much in place to say we don't want to go out of the blockdm dot x range right it's just like essentially like you could think of it as a boundary checker So when when we iterate through BM or Bk we don't want to go out of range。

 we want to make sure that these kind of add up， we want to make sure that when we have this like 2D structure that when we flatten it out it stretches the length of blockdm dot X and that's pretty much what's happening there。

We we assert both of these。 So essentially when we go back， it's like。嗯。

You know n and K are the same and then M and K are also the same so。That kind of lines up there。

 and then and then for these ones， the same idea as what we were doing here。 So the thread column。

 So we do this this dot x divided by the X dimension there。

 which is Bn' that's the trailing dimension in C， it's going to be M by N And so in here we just do thread IDx divided or for for the column index of a。

 the inner column index of K or a sorry， we're going to do thread IDx mod Bk。

 So Bk is that that horizontal dimension in A because it's M by K。And then。The inner row in a。

Is going to be just the division of that。 So whenever we stride the length of K。

 it's going to notch up1 it's going to tell us which row index we're at， right， that's。

 that's kind of how we， that's how we use the threads to decide which index we're at。

 And then same idea for same idea for B here， except we use the trailing dimension in B。

 which is N instead of K and the a matrix， right。And then in in。

We essentially hear we allocate memory。 This is going to be very important for when we write things out later on。

 so notice how we iterate over this term TM。 we're going to make thread results like like an actual thread local cache that has the size TM TM is very small right So in here TM is TM is actually8 so that can that can easily fit in registers。

And then we just initialize this with a number， I'll just say zero。

 and then we're going to populate that later on right。

 so we just initialize this beforehand and then we're going to change it later。Now。

 we actually jump into a little bit more advanced stuff。 So this entire， sorry。

 this entire loop here is where a lot of the magic actually happens。 So when we're。

 when when we're in a single， when we're in a single。😊，When we're in one of these iterations。

We are trying to calculate the complete tile for an output in C， right within a block。

 That's what we're trying to do。 a block， a block in like a certain block I X within the grid is going to calculate an output tile in C。

 That's the goal here。 So we out we， we loop over these block tiles by iterating over K， right。

 K is that。K is the horizontal dimension in a and the vertical dimension in B， right， so we。

We iterate over those and we advance by this much each time。

 We're not actually going to use We're actually going to use block ID X。 like as you can see。

 we only actually have it in this one line here。 it doesn't show up anywhere else。

 So this is just for making sure that we don't if we just like iterate by one each time then it's going to go out of range。

 we're going to do this loop way more than we need to。

 So we just want to do it for as many blocks are for as many blocks as we need， right。

We then populate the shared memory caches。So this is within this is within a single tile， right。

 so notice how we use the inner row a times k right。

 so that' the that's the that's the which row are we at inside of it。嗯。And this is the。

These are like these are like very small ranges of indices， right。

 and that's going in a it's going to loop around K。

 and then that extra column index is going to tell us which position we're at right relative to the threat。

 of course， so we can like parallelize the actual loading part。

And then we do the same thing for B all right so we have this they have this row and we we have like which row are we at and then we want to essentially stride that number based on n and then end up with that offset column index so that's what this is here。

We sync everything up。 So this is again at the at the block level。

 So so a kernel normally runs at the level of threads。But because we're doing sync threads。

 it's going to apply to all of them。 So all of the threads within this within this block are actually going to line up。

 They're all going， we're going to put a barrier and they're all going to meet up and they're going to synchronize at the same。

 same spot， right。And then we just advance the block tile for the next step。

 So when we when we need to do this load again， this is already ready and we don't want to we don't want to like worry about this anymore right Okay。

 so remember a and B are British pointers right when we scroll up we see A and B are pointers to float arrays right So when these are laid out memory they're not like it's not like an array of arrays or like an array of pointers where each pointer inside that array is a new array like we did in in the C and C++ review chapter it's not like that。

It's， it's literally just a it's literally just a pointer。

 and it's the pointer is at the start of that thing that's start of the array that's laid out in memory。

 So it's not the actual value。 It's just the memory address。

 So if we take that memory address and we we plus one， it'll go to the next index， next one。

 next one， next one， right。嗯。That's what we're doing here。 So we already did this in the last。

 we already did this here， where we。Or is it this part， We just， we just advance further。

 So a advances essentially plus an entire block size。 So we advance the。

 we just advance plus whatever this value is to a。 So it's going to。

It's just going to increase that much whatever we set that to and then this is going to increase。

 but it's going to have that n stride right so the trailing dimension in B is n。

 so it's like K by N and so's going to it's going to wrap right it's going to wrap and it's just going to find sort of the next the next one in in B right and that's that's really all we're doing there。

So then we go to this next part。 This is where actually a lot of magic happens。

 and I'll do my best to explain this， but that this part's like kind of intuitively heart。

So we have multiple foreips in here。We have this dot I D X that we iterate over B K with。

 We have this float。 We have this， the specific float。This， this， this， sorry， this。

 this temp temporary variable。And then we have an inner loop here。

 so I'll try to explain this as best as possible。We jump back to here。We notice how like initially。

 we have these two matrices that we're trying to multiply together。This is this is a and this is B。

 right we have these this tile intersection， as we did on the whiteboard there。

 And so really the magic happens is like in these loops， right。

 we've already taken in this outer one。 We've already actually taken the blocked tiles。

 We already have these in shared memory。 and that we have to do fast operations with them。

 So we go down to here where we actually have these in shared memory， right。

 This is a tall and the not very wide。 This is wide and a little bit taller， right。

 So it's it kind of matches up。😊，And then inside of here， what we do is we。

Notice how we do we iterate over dot IDX and then here we iterate through through this this TM right So we have this dot IDX and then res IDX over TM。

 So if we actually pop back to here， essentially what's happening is this at the lowest level in the innermost loop。

Res IX is going through like we have this jump here， which I'll explain that indexing in a second。

 like how we actually arrive there。 But Res IDX is going through these。

 It's advancing vertically downward and it's multiplying with whatever value this is。

 So that little top left corner and B that top left corner value and B is going to say the same。

 And res IX is just going to multiply with that value is going to go。

And it's going to compute a partial dot product along this column。Right now。Now， when we do。

 when we iterate over dot IDx， what's going to happen is dot IDx is going to。

 it's going to go forward this way and it's going to go down this way， right。

 So notice how these these arrows are colored very similarly。' they're actually the same color。

 So that means we're going to。Dot I D X is going to evolve downwards in B。

 and dot I D X is going to evolve to the right in a， so。Whenever we evolve like one。

 it's going to essentially residX is going to take this value。

 It's going to and then we're going to evolve one forward。

 and then re Ix is going to reset and then it's going to do a dot partial dot product for the next column It's going to do a partial dot product for the next column and it's going to do this all the way until it is finished inside of inside of this this entire section。

 And then when these evolve inwards， right So when this is when this is going forwards and like just not even considering residx just like think about like sure these ones are all filled in this one too。

 but when this goes forward when this goes forward and multiplies with this and they are both inching in one at a time as dot this is what's happening ast dot IDx is moving up these are actually acting as little like essentially little tiles and so you end up computing this specific you end up computing the full dot product of。

So when when this one moves like here， it's like one fourth of it is done， right。

 one fourth of it is done。And then it moves up， half is done， half is done，75，75。

 and then it's fully done。 Once that evolves all four steps。

 this entire index right here is computed。 And so we notice that when we do resid X and we go through all of these。

 we end up completing the entire row。 So when we go through this way and this goes forward。

 we complete one column at a time， right， one column at a time is completed per thread。

And so when we， when we have other threads acting like thread column and the thread row。

 which is acting as these little blocks that are shifting downwards instead of like little individual 1 D columns。

You actually end up computing the entire thing， so thread column is laid out this way through like it's like essentially all the column indices in in the be tile。

And then you have the thread rows， which are here。 And so this is going to compute all of the all of the columns in C。

 It's going to， it's going to cover all of them in the tiling aspect。

 And then this is also going to cover all of them。 So what you actually end up with is you complete the entire tile by giving a thread of more operations to do。

So when we actually jump into this。嗯。We can see。 So， first of all， we have this temp B， right。

 So this is coming from the B shared memory。 This is， so we just say dot I X dot dot I x is 0。

 This is the first iteration。 It hasn't or the0 with iteration。 It hasn't changed yet。 So this is 0。

 and it's going to。It's going to evolve you know across Bn0 number of times right。

 so0 times that is0， and then plus the thread column， if that is also if that is also zero。

 then it's just going to be here， right， it's literally just going to be there。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_15.png)

And when dot I D X moves up， then it's going to。Like this isn't it's not going to move this way that this offset here is from the thread itself。

 the thread index itself。But we're actually going to traverse downward。 right， That's。

 that's the dot idea exercise I was explain before。 And then you have the。This res IDX。

 the result IDX， and this goes through TM right so this is this little block that we have here。And。

When we actually look at how this is accumulating， remember the size this is the size of TM。

 we're going to iterate through TM with this red IDX or res IDX。

 that's going to be the amount through TM which we've iterated through。

We're setting that index to a place in shared memory in this exact place。

Is going to be So the thread row times T M plus res Id X， right？ So thread row in this case。

Threadtter in this case， is whichever one of these it falls at， right。

 So that's a specific row that it falls at considering that we evolve at like in T M blocks， right。

 that's that's that's the amount that we evolve。We progress each time and then this res ID X part。

Res IX is how much are we vertically offset。 So we， we advance like 4 or like 8 or4 or 8 downwards。

 And then we have this additional offset residx。 But we have to make sure that we actually arrive at that specific piece because it it's going to be laid out in memory like this。

 right， So we have to make sure that we evolve straight downwards and that we get to that certain re Ix position。

Now， we multiply this by the K dimension， which makes this a lot easier for us。

 right that essentially solves that problem。 So however， many we want to go down this， this thread。

 whichever thread row we're talking about， times TM， which is you know， that that block space。嗯。

Plus res I X， which is that offset。 And then times that all of that times B K， right， this。

 this K dimension here。 And that's just going to times it's going to go22，2，2。

22 right where we need to be。Then we just add the dot IDX offset， which， as I highlighted before。

Is literally just going to progress that way。 So it's going to iterate all the way to the starting position。

 And then dot Idx is going to tell us how much has it gone to the right。 And so you have this dot Ix。

Here， that traverses downwards， and here it traverses to the right。Now if we go back。

Or multiplying this。By this one。We're multiplying it by the temporary v value。Keep in mind， this is。

The only thing controlling this is the dot ID X， which we already highlighted。

 This is going to make it go downwards and then the thread column。 So thread column。

 as I mentioned before， again， we're kind of just going like starting with the a visual example and then going into the code and then connecting that to our visual example。

So thread column is that that horizontal offset and that that like each thread is just going to get a different horizontal offset。

 right， So it depends on which thread we're at。And then we go back to here。嗯。

And we have this thread row right So that's just going to depend on which block were。

 So in this case， we're not at block。 we're not at sorry we're not at thread row 0。

 We're at thread row 1。 So it's going to traverse Tm layers down。

 which in this case is like maybe 4 or8 or whatever whatever number we pick right And then it's going to end up there。

 And then the rest of the math is going to ensure that we get to the correct position with respect to res IDx and dot IDx。

Some other things you want to pay attention to here are how these actually are coalesced in memory。

 right， so in memory。Keep in mind when we're loading these columns in。

 when we're loading these little column bits in memory。

We're loading them as if they're like adjacent next to each other， right。

 So this like thread 0 is going to be adjacent to to thread thread column 1。

 thread column 0 is adjacent to thread column 1。 They next next to each other。 thread column 2，3，4，5。

 right？ So when we actually load this on the level of threads。

 That memory access is going to be coes。 It's going to be combined。 We're not going to have to。

 you know， consider this stride。 And then like， oh。

 we need to get two memory accesses to get both of these。 It's like， no， you can actually fit。

 like a bunch， like， however many as you need into one。 right。So technically。

 what you're going to have here is you're going to have。Since Bn is 64。The N is 64。 So this。

 this whole length here， it's going to have two wars。

 So it's going to literally going to be like two memory aes that we need to do because。

That like an entire warp that can actually make memory aes really efficient when we have two。

 that's that's effectively just two memory aes that we have to worry about。

 So it's really awesome that we have these that we have these coal as right。 I mean， this itself。

 this other one isn't going be coales， but that's fine because we。😊，You know。

 we're still using shared memory。 What we do care about though。

 is that these are coales right the column accesses are coales and that's going to make things really。

 really fast。 So to iterate we essentially iterate over and we complete。

 We let the threads complete the columns like partially and they advance over and and the dot products are going the dot IDxs are going to evolve and they're going to close inwards and then they're going to complete that slowly right and these individual threads are going to complete the columns right So they're going to move through the res IDX。

And then the dot I Xs are going to evolve this way。

 So you end up just completing a whole column because these line up and this one lines up。

 And so you get， you get a bunch of these。And that is one of these， right？

So then we sync up the threads。 We make sure that they're all caught up so that we can actually write out the results safely。

 right， this is for a specific block tile。 So when we have like a bunch of them in the entire thing。

 we have a bunch of block tiles we're worrying about。

 we want to make sure that we've synced them up for this current block tile just for safety purposes right we don't want to mess anything up。

 So we're just doing we're going to be safe there。 And then when we actually write out the results。

 it's going to be very similar to what we actually did up here right So we iterate through this TM term again。

And we're going to have thread row times Dm plus red res ID X， and then times n， right。

 So n is in the bigger picture of that whole that whole C matrix。

And then plus the actual thread column itself， which is going to be that offset。

And that's the actual index that we write out and we're going to iterate over TM or8 indices every single thread。

 so each thread is going to write out eight elements right instead of just one writing out eight elements。

嗯。And thenre we're just going to keep in mind you know this thread results we're just essentially each time we write out it's just going to populate that index。

 So it's like a very easy way of just keeping track of of like which ones we write out at the lowest level of hardware like SM and registers So it's just going make our drops easier on that level So we could literally just store them one by one like an array of eight elements and then we write out that array of eight elements。

 We don't have to worry about strides or any of that stuff right。

We multiply alpha by that for each for each one， right， for each index。

 And then we do the same with beta。 So beta is another term。 and we have C， which， I mean， C is just。

We're essentially just element where we are point wise is multiplying beta so it's like whatever beta is。

 maybe like 0。5 or 3 or whatever it is， where it is multiplying each one。

And so we consider the strides and the offset as well for that。Okay， awesome。

 So now we can actually generate or we can actually see how this performs。

 So remember how bad our initial kernel was。 I'm going to go ahead and run SGm 0，0。

 just to show Kublas。 It's going iterate up。 And we're going get about 11。411。

5 teroflops for performance。😊，And then if we go ahead and run the blockedho one。 So kernel number 4。

You go ahead and run this。We' couldn't get like actually quite a bit faster than the previous。

 which was 03。And this one。Give it a second。This one gave us about  1600 gigaplops。

 This one is about a 3x speed up of what we previously had， which is really good。

 so that pretty much just shows that the memory access patterns we use so that that coalescing of memory access was really。

 really useful and even more useful was using a single thread to do multiple computations to compute eight elements instead of just one so that really。

 really sped up or throughput and performance there。😊，So now if。I actually wrote a like off camera。

 I wrote a separate I wrote a separate function here or not function file。

 may not see you inside of the kernels folder so we can easily like compile it what I pretty much did is I just imported this。

 so essentially the blocktailling kernel， the header for that right here。

I included the macro which we had in the previous file， I initialized some matrices， so 1024， 1024。

 1024， and then our previous like 64， 64，8 and 8， and then I just populated these。

Could a Malic manage just use like this this unified memory。

 which is like going just reduce a bunch of boilerplate and make things a little bit sped up for us。

 but you're going to see the main thing that we're looking for in a second。

 I initialize everything properly and then I call this kernel and we're just trying to see like what does the actual code look like under the hood here。

So。If， if I go up to this command that I ran recently， NBCC dash P T X。

 that means parallel thread execution。 parallel thread execution is what Kuta compiles down to。

 It's the assembly language for parallel processors。

And then you have just the file that we're compiling， and then we output kernel。pttx， right？

Or I have to get out of this。And then go into S R C slash kernels and then go and run that。

This is going to give us this kernel dot Px file， which I'll just open here。 We bring this up。

We go into。Clonnal dots， P， T， X。We notice there are a lot of lines in this。 There are 308 lines。And。

It doesn't tell us anything super specific， right， Like we can see like， for example， like an ad。

 an ad operation or like a fuse multiply ad with a， with a floating point 32 number。It's like。

 I think， output and then like multiply these and then add this  one。

 I can't remember the exact order。 but like these multiply addd right。

 Like you can find all these instructions in here。Multiply， right。Yeah。We have the。

 the load instruction。 So LD。 So that's going to load a floating point number into shared。

Into the asRAM。And then we leave this， if I can exit Vm。I have a separate one that I also output it。

 This is the shader assembly。 So initially， NVCC is going to compile everything down to P T X。

And then PTx is going to further compile into shader assembly， which is then actually run on the GPU。

 Shar assembly is what to executes。 So if we compile you know， Ka binary， right。

 it's actually the actual binary that we run， and then and then we compose this back up into the shader assembly language that is actually executing and then we output that in the the couda binary format。

We can。嗯。R one， I mean。Let me check real quick。 We go。 Yes， so we've compiled it into this。

 and now we， we we look at it again through the special command。

 So Kuda object dump dump shader assembly， and then just open， essentially open that。

And it's going to give us the exact assembly code or what we just compiled， right。

 that entire script。So。If we look very carefully or like load instructions， right。

 So if we look for LD。Which I know is from the from here。

 So PT T X compile to shade assembly the S share memory loads from。From B shared are vectorized。

 right， B shared was the one where we had these individual columns。 Right。

 So when that was in shared memory， the S me loads from shared are vectorized。 Remember。

 when we had the threads that were adjacent to each other， those are what we're looking for。

 So if we look for LD S。So we have LDS U 128， right？LDS U 32。 All right， we have all these LDSs here。

嗯。And this is when they're not coalesced。 So this， this LDS， when we have the 32， that means it's。

 it's， it's not， it's not coalesced together， right， these these。

When it's not accessing like4 in a row， if you do a 32 bit floating point number，32 B times 4 is 128。

 So when we're accessing4 in a row， it's going to be a 128 B load in shader assembly。

 So this is what it actually looks like when we get those coalesc memory access is going。

 And this is what it looks like when we're not right So we end up having to you know。

 maybe load more。 So we have like two loads here But anyways， this is the entire point here。

 just to show you what the actual loads look like in binary format。 this is what they look like。

 And we're going further optimize these kernels to perform better。

 right I think this is FFM is like fuse multiply ad floating point fuse multiply a。

 I can't remember we can actually search that up。呃。To F FMA in Shar assembly。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_17.png)

So。Yeah。Fed， fused multiply addd。 There's probably a manual somewhere。

 which I'm not going to look through right now。 You can do that。

 but these are the shader assembly instructions that we're working with。嗯。

Now we move on to 2D block tiling， which builds on what we've already done。

 but makes it even more efficient and makes it even more performance。Okay。

 absolutely get yourself a pat in the back if you made it this far。 This has been quite challenging。

 so you know， feel free to take take a coffee break or whatever， get some tea。

I have some tea with me right here。 So you know， it's， it， it is a grind。

 But if we step back to just this blog post here， we go to kernel number 5。

 So increasing arithmetic intensity with 2D block howling。 Before we were just calculating columns。

 right， We're just calculating columns。 And now this one is going to calculate an entire blocks。

 It's going to calculate like on the mini block inside of the big block tile， right， That's the idea。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_19.png)

So before we just had this dot IDX in the B tile， this was going to go downwards and we just had a single thing that was iterating down and calculating you know a column so got this。

You would just kind of intersect and you get this column filled out。

But now we have this res ID X N component， right， So that's just。

 that's just going to go and make this essentially cover like like a square。

Or like a row and a column right with the intersect is's going to fill up like a square area。

So we have this， we have this term， which we're going iterate over。

 and then we have this new T N term。 So TM is literally just。

This component and then TM is this component underneath， right？So now like stepping into this。

This is kind of just what it looks like under the hood when we sort of visualize how this is how this is being calculated。

 So we look at we look at our a tile and we look at our B tile。

 and it's literally just we're storing a column in reg M。

 So that's like an actual register memory in this kernel， we're actually using register memory。

 So we're occupying a little bit more where as you can see we literally populate it。

 So Regg M is going be of that size and then Regg N is T N size， right。嗯。

And the total results is going to be the surface area of that total area there。

And we just we essentially just store a column in a row and those those will do product through this entire thing and they will intersect and you'll get a little square right here。

And we can see how that evolves at each step， right？怎你好。Wheres my marker。

Let's actually step into this kernel。So we go back to here。And we see， run SGM 2D blockmailing。

 right？So we have this we have a we have the same Bk term right So Bk is just going to be8 in this case and we have TM。

 which is also the same。 and then we have this new TN term right so we're essentially just going to calculate like this area that we fill out is going to contain 64 elements。

 It's going to be8 by 8。 that's going to fill that entire thing up and we're going to have 64 in there。

Now we have this little hackey situation for handling like the very， very low。

 like the smaller matrices that are going to be tested when we do a benchmark。

 So this is why we have this little outstate here。So in case we， you know， decide to use。

In case we decide to use like a very small matrix， this is able to deal with that effectively。

 but normally we're just we're just going to pay attention to this first if statement for now。

 So if these are bigger than bigger than or equal to 128， right。嗯。Yeah， so in here。

Pay attention to this。 We have。A grid dim， which is going to have an X component， right。

And then a Y component， right， So that that's going that's going to say the same。

And then this block dimension， the number of threads within a block， writes like the block itself。

 the dimension of that， the x component， there's just going to be one value here。

And that's going to be essentially the total number of elements in the output tile。

 so you know we of this Bn and this Bn and then you sort of just get this this filled out area of C。

 the C tile that is going to be this of this size right and then we divide that by the total surface area covered by。

By just what a thread calculates。 So a thread is going to go through those 64 elements Its going to be 8 by 8。

 It's going to go through those and going to calculate a small little mini grid for us like per thread。

 right， And so if we we divide the total number of output results by the by the space covered by a thread we actually get the number of threads right because each little piece here is a thread。

 And so if we divide this by this， we actually get the total number of threads within that entire C tile So if we do this math here。

We're going to get to 128。times。我童以。And then， divide this by。8 by8。And this simplifies to， well。

128 is 2 to the 7， right， becauseuse remember， like if you， if you know， like in 8 precision， it's。

 it's like， it's like an image， essentially， like a number of number of like RGB values in a single like。

The single pixel。So you have like RGB and each of those is like 0 to 255。

 so that's like how you can go down to what like 128 is2 to the 7 because it's like in7 and7 and8 that's how I made that disso。

 but have the this two to the 7。Andw through the 7。body by。2 to the three times，2 to the three。

And what you end up with。Is2 to the4 king。一拜 by。Two to the thick。And we do our exponent laws。

 and we get to 8， right， So 14-6 is 8。 so we choose the8。That means we have 256。

My worker works properly。256 threads， right？嗯。256 threads， my writing is messy。 ignore that。Awesome。

 so we know the number of threads that we're calculating。 Now。

 this is going to help us when we actually jump into this kernel here。 So， you know。

 we have our our BM or B，M， B， K， T， M and T， N， right。😊，There's a lot happening here。

 Let's break this down。So to start， we have our row。

 which is going to be the typical y component we've already went over this。

The total results in a block tile are， as we already said in the in the runner file， this is just。

Actually the whole C matrix。 So you have the M dimension， and then you have the n dimension。

 you multiply those， and you get total area， right that's the number of results that we're going to calculate。

And then we get the number of threads。Per。That entire thing。

 So how many individual squares are there that if the threat is occupying， right。

And so that the square surface area is this， which we already calculated。

 And so this number of threads per block tile should equal 256， right？

And then we just assert that down here。 So I want to make sure that 256 value is equal to what we just calculated。

 which is going to hold true， of course， and then it won't it'll actually continue with executing。

 right。嗯。Let we go down a little bit further。嗯。Don't worry about these right now。

 we're going to get into those in a second。So。We do the， the classical， just allocate shared memory。

 We advance the block tiles based on， you know where they're supposed to be at in the。

In the current block， right？Or I guess， in the current thread。

This is where a lot of the magic happens right here。 So this。

 this part is crucial to pay attention to。 Let's first go over the easy stuff。

 So thread results is just like how big is that， that little square that thread is going to calculate。

 That's just going to be it's just going to be 8 by 8， right。We have this Reg M term。

 which we saw in the blog post。Sir ragm is this， and Reg N is that。Tm。And T N， right。

 that's just going to be the the little， the， I guess the， the iterations of the dot product。

 So at each dot at each iteration of dot I X。It's going to store those in registers and it's going to calculate them really really fast right。

's be like it's going to be like8 it's going to be like8 by one and then a one by8。

 and it's just going to evolve that way。Now we look up at these。So。In a row A。

 so we just essentially have the thread index and we divide that by Bk， right？In a row。

 same idea about we use the mod operator。Then we have this new term called a stride， right。

 And now we're actually going to do the math that we're going to do the math for stride here。

So Friday。嗯。嗯。Striide a。Is going to be number of threads per block tile， which is 256。嗯。Divided by。B。

 K， which in this case is a。So here， if you did buy this out， you end up getting 32。

So our strideide A is going to be 32。My mark is a little weird。 pay attention to that term。嗯。

And then we have this otherscribe down here。Striide B is the same thing。

 but instead of dividing by B K， we divide by B， N。 So B N is actually 128。 So if we divide 156。

 right。啊，我同你。The answer is， too。Now， these are going to be important。

 These are going to be very important as we sort of step through this。

 So let's jump down to this actual loop here now。 So inside of a sheridan。Look at how we index this。

 starts starts here and ends there。 We have this first thing in the brackets， which is inner row a。

 So it's going to be a certain row that we're looking at。 plus a load offset， right。

So the load offset is going to iterate up to BM， which in this case is 128。

So you can think of it as us having this。This is the A tile。Right。And so。也是一。嗯。It's going to be BM。

And that can be B K， right。Inside of here。We're going to iterate up to BM in strides of strideide A。

 Now， strideide A is size 32， right。Dr a is 32。 So if we actually look at how many times it's going to strive through this until it reaches the end。

 it's going to start at 0。 and then it's going to go down to 32。大。对。

And then it's going to go down to 64。And then it's going to go down to， I believe， 96。嗯。

And then it's going to stop， right， It's going to it's not going to actually hit this。

 It's going to stop there。 So we're going to have this this initial offset of 0。

 and then it's going to bump up to 32 in the next iteration。 and it's going to jump to 64 in the 96。

So notice。The actual area that we have to fill in here。 right。

 Not the actual area we have to fill in。 So this area。Is。Very cute。And then this Bk。

 we already know is8， right？And it's going to be the same for this and same for that and same for that。

So this is actually where some really cool stuff comes in now this。This inner row A here。

This in row A is calculated as the thread IX。Divided by Bk， right？To this value。

 if we do the math here。Bd Ivy X is the maxes out at 256。My marker， I need to get in market。

256 divided by Bk， which is8， right？Now， this number。Is going to max out of 32。

 and that's going to be our row。 right， remember this looking 32。This number， this inner row。

 which is based off of the thread itself， is going to max out of 32。Now， this inner column。

 on the other hand， is going to do modbyquet， right？So let me do this。It's essentially going to。

 it's going to go like 0，1，2，3 all the way up to 8。 And then once it hits 8 again。

 it's going to jump back to 0， and it's going to reset。

 So it's going to be like 0 through 8 and then reset 0 through 8 and reset， right。

 And then we're going to have these these rows， the row index that goes from 0 to 32， right。

 So every time we hit the next8， it's going to it's going to bump up 1， right。

And so this actually makes a lot of sense， so inside of here。We have this load offset。

 which is going to be strideed by it as much as 32 here。And then we add whatever this row offset is。

 So when we have the row offset， plus whatever that number is。

 we can effectively populate this entire area here。 So it's like the0 or the or say， it's like。

 I don't know，64。 And then plus whichever row it's at from the thread index itself。

 which we which we calculate up here。It's going to be that times the K dimension。

 So that's why it's going to strive over as many roses as it needs to。

 And it's going to end up at some certain index。And then once we multiply that。

 we know where it's at vertically。 And then we simply add the inner column index to that。

 So the inner column index， like I said before， is going to cap out at 8， right。

 So it's going to cap out at 8。 and it's going land somewhere here。 So by doing this。

 we only actually iterate over this four times。 And each thread。Spanning， you know，32 times 8。

 because if you actually do 32 times 8， that's like。Through the5。Two to the five is 32 and then。

Two to the three is eight。5 plus 3 with our exponent laws。 That's 2 to the8。

 which is int8 next to 256， right， So that's how I kind of make the associations。

 You don't have to follow along， but 8 times 32 is 2，56。Look how awesome that is。

Each thread is going to occupy an individual spot in here。So we're going to load this chunk in。

 Each thread is going to take a little spot in there，32 times 8。 And then we load in the next one。

 Each thread takes its own spot。 So it's like one operation。For every single iteration， right。

 so we don't have to go sequentially through it。 Each thread is just boom done。It's one instruction。

Same for this， same for this， same for this。And then we just index accordingly。

 we just kind of adjust it So instead of Bk being the being the stride over， you know we do times K。

 so it's able to stride over the entire thing when we're actually loading from the GPU V Ram because it's actually bigger is these matrices are much bigger when we' when they aren't tiles yet。

 So we have to stride like the whole K distance instead of just the tile K and distance。

And then same idea applies to B S， right， the not B， be share。来。No。Bike it up for a second。

When we look at what BF looks like， it's literally this。Let me actually get a different marker。

Arible。It simply be like this let me go down。It's where。That's what B。

 that's what B S is going to look like。Now， if we look at。If we look at these values inside。

 we have this load offset， which is going to iterate up up to up to Bk， right and Bk。Is this。

Remember， it's not， it's not this part anymore。 It， it's the size。 And then this part is the N。

 because it's K by N as the B matrix。So。When we， when we iterate in these strides。

 it's actually going to end up being。Well， the N in this case is 128， so it's going to be。

This this stride value is going to be stride B， sorry， is going to be 256 divided by 128， which is 2。

 right， as we calculated down here。So it's actually going to stride。I's actually going to stride。

It's going to strike2， right， and two times。The length of this is actually a quarter， right？

 So if you have eight values that you have8 different，8 different rows。You split it once。

Nigh year and half。 And there's poorros here in Guro there。 Now， you split it in half again。

Then you have2 and 2 and 2 and 2。 all that that up adds up to 8。 So when we actually stride。

 We're just going a quarter of the way down。 same thing in here。

 We go a quarter of the way quarter quarter， right， same idea applies here。

 So whatever this stride value is， it's going to start at 0 and it's going to go up to 6 because it's going to。

 it's going to cap out at。It's going to cap up at whatever BK is in this case is eight。

And it's just going to stop， so it's going to go zero， zero，2， four， six， and it's going to stop。

 right？Then we have this innerro B。Which is from here。 And this is just the same idea。

 So inside of this， we have the thread Id X in this case。It's just going to max out at 256。

And we divide that number。We divide that number by Bn， which in this case is 128。

And the column is the same idea。 It's going to go。0 all the way up to 1，28。 And it's going to reset。

 right， So it's not just going to iterate every time we strive 1，28。 it's going to。

 it's going to go up。 It's going to essentially。One model 128 is one。127 128 is 127， right。

 so that that's literally all' want to do here。嗯。In case you have't notice already。

 this is the same idea as here， except for're just dealing with kind of like a more like very stretched out thing instead of instead of like these nice to look at eye candy looking blocks。

 right？ So the idea here is that we just go， however much we need to in because this。

 this total thing is like 128 and 128。 that totals up to 256。

So it's essentially each thread gets its own little space in there， one thread， two thread。

 three thread，4 thread。Right， they all get their own little piece in there。

 and they're able to load in quarters downwards， right。 that's。

 that's essentially how we're loading into shared memory。So just given this new context。

 we're just loading you know。We're just being clever about how we load them。

So given that we understand how everything is loaded to share memory。

 we've going to jump into the next part here and this part is like where things get a little。

 it's a little funny。 it's not actually as intuitivetuitive and bad as this part。

 but it is still a little bit weird with the indexing part so。If we jump into this， it's。

We iterate over this dot IDX right and the dot IDx going back to this is literally just it's going to evolve right。

 so dot IDx index 0，1，2， and 3， right they're going， they're going in words like this。

 one thread is in charge of this little block at the center and the each thread is is responsible for loading in a column and right one thread takes care of that。

Now， if we look inside here。We load into the registers， right。

 so the registers are the extremely fast pieces of storage that are literally right next to the core in the GPU。

And so we have this reg M， right， which is going to load that column in。So how do we lead this？

We have to look at this thread row， right and。To understand everything else。

 let's go look at the row here。 So where is this thread row sets the thread I D X dot X。

 so this could be a maximum of。You know， 256。And then we divide that by Bn divided by Tn， right。

 So Bn is 128 and Tn is 8， so that you divide 128 by 8， and that's 16。So we have。2，56， divided earth。

0 to 255。 and then whichever one of those it is divide at by 16， right？So。Inside of this， we end up。

Having 16 different numbers that could we could be through， right。

 So if we look at this original8 half here， there are 16 different。

There are 16 different rows we could be at， right， And these are just offsets。 Keep in mind。

 We're loading in columns that are 8 elements long。 So when we have like 161616 all the way down。

 we have this eight times。And。Each of these， or no， sorry，16 times each each。

 each little column here， this is the like color name area you could say。That is going to be8 long。

 right？ So we essentially are loading in like。We go eight。

 but that's like that's like a single that is a single column。And then whichever one comes next。

 it's like this is another 8。 and we go all the way down 16 times。

 And that multiplies up to the the length of M。Which is 128。 So the math is mapping。

The same thing applies to thread a column right I mean are these are square matrices。

 so it's not actually too bad to deal with this。 So same idea here and we end up with some range between 0 and 15 right So if we go back down。

Thread row times T M。 So T M is。T m is。Which like TM is essentially 8， right。

 So it's going to be whichever thread row we're at。 So which， whichever one of these out of。

 out of out of 16 are we at。And then times。Times T m。Plus。

 I and I is going to be that little iterator here that goes up to TM right TM is like that the length of that column or the yeah。

 you could say the height or the length of that column。It's going to entererate up to I。

 and it's going to put that into the register M。 right。

 We multiply this whole thing by Bk so that we get this offset going because we have to go through this K thing and reset every single time。

 We want to get a new column。 You can't just go directly down。

 You have to stride one entire length over to get to the next one。And then we add dot IDX to this。

 so this actually becomes very intuitive when we look at it from a glance。So。

Hopefully hopefully this is sort of making sense in your head。

But this dot I D X is just going to evolve us。 It's going to be that that horizontal offset。

 And then this is the vertical offset。 right， this whole portion here， that's the vertical offset。嗯。

And then we apply the same concept to loading into register N right so register n isn't as bad because we're actually loading we're actually loading horizontally。

 So it's going to be the dot IDx， which by the way， dot IDX is going downwards now。

 So dot IDx times Bn Bn is the length of it right， So you're going to go down whichever dot IDx you're at。

嗯。You're going to go down that many layers。And then you're going to do whichever。

 whichever thread column you're at。 So each thread is going to have its own。

 it's going to have its own little section of that。 right。

 It's going to have its own job because the thread is like loading a specific。

 a specific square in that tile。So right here， right here， right here， thread here it's like。Yeah。

Each thread has its own thing。 So we're just worrying about a single thread。嗯。Thread thread is like。

 you know， thread 1。 it's like here。 and then thread 255 is or thread 0 is here。

 And then thread 255 is here because it goes to like the very edge and then the very edge。

 And then they intersect at 256， right， that's how that's， I'm sort of visualizing this。Now。

 we have this extra eye term， which is literally just the horizontal offset。

 So when you when you've looped around how many whatever amount of dot IDxs you need。

 then you have that additional I， which is going to be the offset。

 you're going to load in the first first element in the road and the second and the third and the fourth。

 And then the same applies for this column up here， which we already did。 It's just going to do 1，2。

3，4 all the way down to 8， right And it's going to store this in like a register memory like a line。

And this allows us to easily do product that， right？So when we drop down to here。

 this is the entire loop， yellow to yellow。 we start off with the。The M component， right。

 So thread M is this part， and then thread n is this part。

 So this this end component is actually inside of it。Now。

 the thread result is calculated as Res IDXM， so whichever， however much it is through a TM， right？

AtThat times TN， which is the horizontal stride that you need to do to get to the next row， right？

And then you have this T N as well。 So TN is how far along you are so it's。Or sorry。

 rez ID X is how far along you are。 So this is going to be your your vertical stride。

 and then this is going to be the horizontal offset right So that's that's we're storing it in linear memory。

 but this is how we're going to index into it right。And then we do whatever that is。嗯。And this。

 keep in mind， this is an individual individual grid， right。

 says you're you're looking at a point within that grid。 you're doing essentially。

A do product across those， so you have to iterate through you know， 8 and then8 against。

 it's 64 iterations you have to go through filling up that entire tile。And then you just use。

 you know， as you would expect that that value， whatever it is。

 So you're just essentially just crossing you're finding where they intersect and then you're setting whatever this is in that。

 So and just becoming this entire matrix light out。 It's like。Instead of being loaded like this。

 you just take this row and you attach it to the end， and then this。Attach it to there。

 And then this one， it's even further， right？That's all we're doing there。So it's like literally。

 as you would imagine， in your head。 This is how it's working。 It's just。

 it's just important to actually highlight like what the indexing is actually doing。

 instead of just trusting that it works， it's really important to actually dig deep into what this is doing under the hood。

So I encourage you， if this doesn't entirely make sense， it's very intuitive。

 I encourage you to test it with your own examples。 So even just like get a piece of paper。

 write that on a whiteboard， whatever you need to do and just sort of write this out and try to visualize it through each step right So you can even set。

 for example， TM to an TN to 4 right and you can make it much easier on yourself。

 You don't have to go to the full extent that we're using with you know our parameters like 8 and2 128 here。

 You don't have to even go that far。 You can be very simple about how you exercise that。But yeah。

 so this is actually how we calculate the the individual thread tile。 So this thread tile。

 this little 2D thing inside of the bigger block tile。 And we calculate one of those per thread。

 right， So 256 threads are laid out。So it's， it's like zero to 16， zero to， I think， 240。

And then over here， it's 256 that it might be like shifted based on how you're seeing that the picture and my hand waving。

 But that's the idea。 is you go from， from 0 to。256， right。

 let me just make sure everything is synced up。 You know， we make sure that all these are done。

 you know， as we're iterating through all these， all of these block tiles， right。

 we have to go like on the on the bigger matrices A and B。

 we actually have to take these tiles and we have to move them closer together right。

 this is what this whole loop is doing， we want to make sure everything is synced up both after the shared memory。

Population up we populate those， we want to sync everything and then once we've written once we've written all the results here。

 we also want to sync everything up， make sure all the threads are caught up before we evolve to the next one and mess with stuff。

So then we have this right out and this isn't actually too bad。 This parts pretty good。So。

Inside of here。We iterate over the same things that we did here when we were actually calculating when we were multiplying those thread rows and columns。

 those little thread tiles。And。If we just step through this。

 this is actually going to seem a little bit weird at first。 But if we scroll up。

 remember that we advance everything to the starting position， given this threat， right。

 or given this block rather。 So we have these initial terms， which are the blocks。

 These are which tiles which tile we actually care about within C。 And this is already stored here。

 So we already know which tile we actually want to worry about。

 And the memory address has gone through， it's skipped a bunch of spaces。就是。

Just like integer operations， it's been multiplied and added up to the point where it's where we want it。

And then we just do everything from there。 So we can， if we stride like an entire length K。

 it'll go here and then the remainder of it， and it'll end up back to where it is。 But just like one。

1 element lower， right， So that that's really all we're working with here。 Now。

 if we scroll back down， it's literally just like this n term， that's， that's like the N term。

 that that's the， that's the horizontal part， right。

 that's the part that we're actually striding over。 So if we have， we're looking at the C matrix。

We have thread row。Times threat M， right or。Or TM， which is8。Plus， the res index。

 remember we it's the same same idea as as as what we did up there。And so。When we are。

It's essentially the same as this， except we're doing I instead。 So， you know， I as。

You could think of I as like up to， you know， TM。 like the same idea。

 Where just iterating through that。 That's going to be the offset inside of that tile， right。

 So like relative to。Relative to the actual CTt that we're working on。

 this is going to be like the relative offset， right， So that's going to be downwards。Times n， right。

 that's going to give us our downwards。Our downwards movement。 And then to progress sideways。

We have the thread column times T N， right， so an individual thread。Individual thread times。

Times that that T and length of8， right， So essentially we're going to have a bunch of a bunch of threads occupying like a square。

And those threads are going to。嗯。We no not not the threads occupying a square。

 but they're going to occupy the whole thing。 And then the threads are each side ist going to iterate through that TM and T N right。

 And so we have this this vertical offset。 We have the horizontal offset。

 and then plus that additional little kick to the right， We're going to iterate。

 This is how much we need to actually like stride over like how big steps we we take。

And then the initial just like inside of that， inside of like one of these depths。

 it's like how much do you actually go forward， right， how much do you do you add to it？

And then we just use it what we've already computed， so thread results， same indexing scheme here。

 this should be fairly intuitive， and we just multiply this element wise for each iteration in the loop。

And then we have our beta times， you element wise， this。

 which is literally the same same indexing scheme that we use here so。

Hopefully the block panel kernel made sense。Now we're going to jump into actually before we actually jump into the vectorized kernel。

 I want to run this。So we go。SGm， we go SG is 04， right， this is block time normal。

This is regular 1D block only， right？Then if we step the up number 5， look at this。

4800 Gflps on 4096， right。Decent。But if we step it up to 5。We double it。So we Python， we go。91，62。

The快的快。48。73。We get about 1。9 x feet up， right， which is really good。 Now we compare to。

The results here。嗯。So。About about this times 1。9 roughly is it's pretty close to 70， right， So。

 I mean， we're essentially getting the same results here。 So everything is working out。

 We just doubled the speed by using 2 D block piling instead of 1 D。

 And now we're already about two thirds of the way to Kubloss performance。 We're actually really。

 really high up there， so。Now let's go ahead and continue with vectorized memory access。

 which is going to give us an additional little performance boost。ok啊信。

So now we have this new acur to worry about number 6 on vectorizing the shared memory loads。

So if we look inside of here。啊。Essentially we do this， everything in here remains the same。Except。

We have this new float 4 type， so notice that we have this this float where I just highlight that and see where it shows up it shows up here。

When we're loading into。When when we are loading into shared memory， right， so A shared and B shared。

 right， this is where it comes up。As well as when we're writing out the results。

 So when we're going in from global V Ram into shared memory， we use float 4 loads。

And then when we're writing out from registers。We load we load with float forward as well。

 right this is what's happening here。Now before diving in right into this。

 I want to go over and review just like what the heck this flowboard does there's a lot of terms like reinterpret cast and this all this weird symbols and stuff。

 so let's just click go ahead and clarify what this all means。

I wrote a separate file here called floatatboard let's CU you can write the same thing。

 but I'm just going to go over this kind of step by step So we have an array length n， right， 1，0。

 three，4 all floats。we have a host input， host output。 We initialized device input and output。

We could those with n time size of float。We could em copy that from host to device。Post a device。

When you launch this with a grid size of one， there's a single block and within that block。

 there's a single thread， so there's just one thread that's actually being used here。Now。

 we run this， and then we copy back and then we display these based on their indices。

 Right It says 0，1，2，3， and then 0，1，2，3， the inputs and the outputs。

 And now what actually happens inside of here is what we want to pay attention to。 So we pass this。

 this device input and the device output put in。 right， These are pointers to array。

output'll as well。 Now we have this I D X， which threaded index in just case is going to be 0。 right。

 We， it goes from like 0 up to whatever the length is -1。And so this is just going to be zero。

 So when we actually look at this。This I D X pay attention。' don't worry about this yet。

This ID X is going to be times 4， so0 times 4。0 times 4，0 times 4，0 times 4。 it's just going to be0。

1，2， and  three， right？It is going to be our X， Y， Z， and W components。

Now let's actually look at what's happening here。 So this new float4 type is part of the is part of the coupa runtime。

 It's part of the， what's not part of the couda runtime。 If we actually look at this。

 it's part of X86， right vector types。 We have those float4。

 We have a bunch of different other vector types that are device built in。 so we can't actually。

We cannot actually see what these are under the hood。

 they just kind of work for us because if I try to click on these， right， it's just like。

That's really all it is。There's park in here。 A lot of this is built in hell by the compiler。

 et cetera。And so。When we break down what's happening here， we notice that we have a few parts。

 so we have this reinterpret cast。 and literally all this means is that we're going to reinterpret as this in in the actual instructions。

 right， So this isn't going to manipulate memory or do any data transformations。

 It's literally just going to reinterpret as a float for。

 that's what it's going to tell like compiler what to do， right。

And this is going to be a pointer to float for， right？Sore we're transforming this essentially。

 So this is a memory address。 This amperserson is a memory address to whichever index we're looking at。

 So in this case。It's going to be， you know， ID X times 4 in this case， this is just going to be。

This is just going to be like I D X is 0。 So it's going to be00 times 4。

 That's just the beginning element， right， That's literally all all this is is just。

We're doing input at index0 and then we're up。We're getting the memory address for that。

 So it's the memory address to the first element in that entire array。

 And then there's the following memory addresses with the， for the extra ones。And then we。We， we， we。

We reinterpret this as a float4 pointer。 So we got the pointer， the memory address here。

 and we're reinterpreting this as a float4 pointer。

 So we're just going from pointer as a float to pointer as a float4 and the float4 is just going to contain essentially the starting index plus an additional three afterwards。

 right。And then we just have this stored as as index0 for the specific data type we don't want to be you know we're doneant and take up extra space。

 So we're just going to index 0 and then the compilers are going going to know what to do with that later on and it's just literally just going to be the dot X component is going to be index0 dot Y is going to be index 1 set is2 and then W is 3 right so that's that's literally how we have it laid it out how we have this thing laid out here。

And that's literally all the， all the flip for data types is。

 So hope that that kind of makes sense to you， you know， when you read complex。

When you read kind of like complicated expressions like this。

 it's good to just break it down step by step， Right， So you have this like。

 you have this thing with its open and it's closed。

 and then you have this thing with its open and it's closed。

 and this thing with its open and its closed。 you just kind of see like。

 you do like your order of operations or simplifyimplified however you want。 But yeah。

 hopefully that makes sense。 And if we can， Im actuallyre going to。嗯。嗯。SGM。

 see into source slash kernels。 And then if we go。And compile that into F 4。

 We notice that we get everything as expected， right， So 1，2，3，4， that is the host input。

 So that's how we initialized it here。And then the host output。

 which is exactly how we want everything to be stored， that is all checking out。Now。

 this next kernel is really fun。 It， it plays around with some things that are usually played around with and toyed around with when you write really。

 really performance， optimal cur kernels， right， So the idea here is like。

 remember how when I showed you before those。😊，Let me go back to here。And。I'm going step out。

And go to S RRC slash kernels。 And then we did the。We did this one， and we saw。We go up。

 We saw these like this load this load instruction， the load dot E。

 and then there was like some load 128， So like load 32s and then load 128， right。

 So that that's like the whole that's the whole deal here is we're going to try to make more of these load 128。



![](img/0f9ea5e8bacc4cc914094ea7b918190a_21.png)

A single floating point number is 32 B。 And so if we， if we， if we make this like a vector type。

 meaning。You know。We just put multiple numbers with each other in the same type。

 Then we can have more， and we can load more things。So。

Let's go ahead and actually jump back to this part here and let's explain like what the heck we're doing。

So。

![](img/0f9ea5e8bacc4cc914094ea7b918190a_23.png)

In this one。We are essentially， we're essentially taking the a tile。 So it's like normally vertical。

 So it would be like。Tiltted das like the bottom would go here。

 and then this part would go right there。We're just transposing it， right？

And this transposing is going to let us cheat a little bit。

 We still get the same amount of memory in that shared block， except we index it differently。

 and this will allow us to coesce memory accesses， right so。Normally， we would， if we go back up。

We would be taking these and we would be advancing to the right here， but notice how。For example。

 like when we're actually loading this in， our threads are going to be loading in from like top to bottom right。

 So we're going have like like threads essentially organized and in different pieces。

 and we're going to be iterating downwards to populate this， right。

 If you remember how we populated it before， these aes were not coalesced。But the B， the B tile。

 the B shared tile was coalesced。Because our threads were loading horizontally。

 So in our thread we moved like thread 1， thread 2， thread 3， thread4。

 those are all next to each other。 So Kutuda is going to go ahead and load those in as a like if you have four of them adjacent to each other。

 It's going to load all those in as a single load operation instead of four separate ones。

So that's what we're aiming for here。And the idea here is instead of advancing instead of having this vertical tile and then taking this and advancing to the and like having IDx iterate to the right。

 it's going to be flipped and we're going to iterate downward。

 So our threads are going to be paired like this next to each other and it's going to iterate downward right that that's the whole idea there。

 But what's even more important isn't even how they iterate downward。

 That's just what the graphic looks like。What it's more so about is how we actually are able to load from global into shared。

 right， So how do we take the a how do we take the a tile on its own and then load that into shared and then populate it like this。

 right。So。We pop back to here。We notice a few things。 So first of all， this is the same。

 This is the same。 This is the same。 but these and these are different， right。So if we pop down here。

 just pay attention to the inner rows and columns for now。

So notice here how that this this is actually very familiar。

 but notice how we don't actually have that loop。 So if we go back to block tiling， for example。

 this 2D block tiling。We were loading in four loops。 So we had B M was  a28 long。

 and then this load offset would increase in increments of 32。

And it would do four different iterations of the for loops。

 totaling eight different iterations per thread。 So each thread was doing eight different instructions。

 or， I guess， at the high level， eight different instructions for moving data around。

And that's like kind of a bottleneck a little bit。 so we can actually speed that up and notice here how we don't actually have any loops。

 it's literally just we store this temp variable。 this is doing this is done once per thread。

 by the way， so this is like once per thread， but we essentially we go into we go into a。

 we get this inner row and we essentially just we essentially just find where exactly where exactly this is at and we're going to load this into shared memory as if it's transposed。

 right？So， for example。I have this thing written on the board here。 This is the a tile。

 and I drew a little section at the bottom with 1，2，3， and 4。

 These are four different values that we're going to count as a float floor， All right。

So when we actually transpose this when we do a tile， then you say t。

 you might not be able to see all those and there just don't worry about it。We transpose this。

 And essentially， were like flipping over。Over this， this dotted line here。

 So these are going to flip over。 They're going to go from this to。This， right？ is is going to flip。

Across that line。And they're going to end up like that。You what you're going to have is。

You're going to have when these when you flip over， they're going to be ordered。12。Or sorry， Bob。5。1。

2，3，4。Now。Don't worry too much about how these are in how these are in like a column format。

 What we do care about is just that we're loading these in a coesced manner， right。

So notice how I've kind of taken like half of this tile here。

 and I've actually done this for a reason。So if we。

 if we go ahead and look back at what these inner rows are and all this stuff is saying。

It's essentially the same as what we had over here in 2D block tiling。

 except instead of just BN or Bk， it's that and then divide by4 right？ So I mean。

 it's it's4 for a reason。 it's literally because we're just we're just we're using the float4 type。

So if we're going to do thread I D X， which in this case， is going to max out at 200 and。

It's going max out thatts。Say 255。And then B， K is 8。 So it's going to be 8 divided by4。

Which is 255 divided by 2， which gives us the indices 0 to 127。Now this one， on the other hand。

Is going to be same idea except we're doing the mod， right？ So 2，55 mod 2。

 that means every two times it's going to reset at 0 again。 We're just going to have the two numbers。

0 and 1。Essentially， this indexing allows us to treat this as a group of four。 So when we divide。

 that means it shrinking to a fourth of its length。

 And then when we go down here and multiply by4 again。

 which you'll kind of see the intuition for in a second。 And when we multiply by4 again。

 it's just going to stress that back out to what it normally used to be。

 So this is just considering this little float4 indexing scheme we have。Now。

 if we pop down to this here， we can see that this。

 I'm actually purposely making this mash R a tile here。So notice how we have this inner row a， right。

 and inner row a is between 0 and 1，27。 So the row for this tile is between 0。Let me put this here。

0ero。And 127， right， So you might not be able to see that。 but 0，1，27， This is very long。

 This is like the longer side。 And then we have 0 to one。 So two values for the for the column。

 right， column A。So，0 to one。Or。Or one rather。And all this allows us to do is just sort things more easily。

 So notice how we have like a。We have this thing that's normally of size 1，28。I ate。And 128 by 8。

 if we actually do the multiplication for that。That's 1024， right？So 1024。

And then reduce this number， we divide this one by four。

That actually reduces the whole thing from 1024 to 256。Guess how many threads we have。256。

 It works out perfectly， so。Each thread is essentially taking its own little。One of these。

so this is going， this is span down 127，0 to 127， and then this is going 01。

 and just switch just split in half， right， So you have it， you have like one，2， three，4，5，6，7。

 right。8。And we're just like splitting this in half。 and then it's spanning the length。

 it's spanning the height downwards， right？And all we have to do is just store this as a float。

 This is what we do here。 we literally take the inner row。 We do that times case。 We need to。

 know stride around and get back to the same the same to the same column again。

And then we do plus the inner column a offset。 This is all in context of like this a tile being advanced where it needs to be。

 So we're literally just adding K， considering that we're in this bigger matrix， right。

 That's all we need K for。 Everything else is it， it just works because we're in the。

 we're just dealing relative to this specific tile as a part of the whole bigger matrix。Now。

 inner column。We're actually going to stretch this out back to4 again， because。

Because we purposely shrunk it， right， So we just need to expand that back again。

And this is just going to index in the old fashioned style， right where we find the vertical offsets。

Meaning， meaning here。And then we add that。 So a vertical offset， and then we plus。To the so like。

 we find which row we want。 We multiply by the， by the K term。And then we get where we want to get。

 And then we plus for the horizontal offset， right And we。

 we have to multiply by 4 to like to actually span that entire length， Right。

 So if you wanted to go to the very end of the matrix。嗯。

If you want to go to the very end of the matrix here， you'd actually have to take this two term。

 whatever that is times 4， and it would it would get you all the way to the end， right， That's。

 that's the whole idea there。But if we go into this。Look at the way we store these， right。

 This isn't actually too bad。So in a shared， we have these four different。

 they have these four different stores， which is each four different component of the float 4 variable。

 So we have this X， Y set and W term。 This is the first one， index 0， and then index 1。Index 2。

 et cea， right。So all we're doing there。As we're looking at the inner column。

Whichever column that us， keep in mind， we have this new tile of this shape。

 So we're doing it relative to this because how we this is how we're storing everything。

So we're going to go the inner column。Whichever that is。 So in this case， the， the column。

We have to keep in context how we stored column for this one。

The column in this case is which one of these。 But since we。嗯。Since we transposed it。

 we have to consider the column in the context of here， right。

 So it's actually a little bit different。So instead of having row as this。

 it's actually column because we interpreted column from this originally。

 that that's kind of what's going on there。 Hopefully that's hopefully that's easy to understand。

And then we have this times 4， which is obviously we're going to stretch it out as we need it to。

And then whichever index we need to plus， right， we're storing this。As like， as like these。

 these vertical valuess。 right， So instead of horizontally laying them out。

 we're storing them vertically。 And this is why you have this extra index here。 This one。

 This is going to be like the the， the column offset， you could say。Like which which sorry， which。

 Yeah， like which row are you at rather。 And then the the BM term。That is just this。

Then we move it over here。 So it's going to stride across as many times as it needs to。

 and then we can add the just inner row a part right。

 so those of the row originally came from this part and now we're just flipping it over to the side So we get the actual offset there。

 And that's literally that's literally how we store it。 It's like literally that easy。So。

Then we go further and we look at B。 B shouldn't actually be too hard。

 I'm not even going to explain this。 It's literally like B。

We're just explicitly adding memory coalescing here， like if I go back to this。What's it called。

Shouldn't the compiler just be able to pull us the second version and generate 128 B loads And then the reason is that the compiler has no way to verify that the float B pointer is passed to the kernel as as 128 B aligned。

 right， which would be a requirement for this。 So essentially。

 we're just saying like like in in the previous example where I showed all those shader assembly。

 There might have been some instances where it did not actually know that it's okay to store as a 128 B。

 as that like a float fort like an implicitly 128 B aligned type。But in this case。

 we're explicitly passing reinterpret cast and we're explicitly setting it to float for or 128 bit。

And that's promising the compiler that this is aligned。 right， This is telling the compiler you can。

 you can do it what you need to with this。 We've set this up properly。 work your magic。

And we're just helping out the compiler that way。 So that's what's happening here。

 Sam like it literally this identical indexing scheme， not really much to talk about here。

 But after this is all done， keep in mind， this is done once per thread right we do we store and then we write。

 right， right， right， and it's just super fast， right so。

Don't don't worry about the don't worry about how we're writing this。

 we don't actually have to make the rights coales， so that the rights don't have to be you know adjacent like this。

 they can be separated like by rows。And then as long as the reads are cooles， that's fine。

 So the reads。Coming from here。 And then we're just。

We're just flipping it over and it's landing there， which is perfect。

And then we move on to actually calculating the results of that little of that little thread block。

 essentially the thread mini tile within the bigger one。And。We iterate through with normal dot I D X。

 right similar scheme to what we had before， except the indexing scheme is a little bit different。

 We remember how we， we have V as like this， this rectangle where it's like this is short and this is。

 this is long。 right？ A is the same way now， now that we have transposed it， A is also like this。

 So instead of a being like this。 It's now flipped over like this， right。

And so all we have to do is just change up how we index it and that it'll work。

 So I'm not even going to go over B B like very obvious I understand， but going over a， right。

 how do we iterate through this。So dot IDX， right？When we look at this， we go。So whichever。

 whichever dot index we're at， we'll just disregard that for now。 We'll just say that's 0， maybe。

And then this， since this is multiplying by 0， that's going to simplify to 0。 So it's going to be。A0。

Plus， and then we'll say， maybe the。Whichever thread row it's at。

Whichever thread row it's at is going is going to multiply by TM， which is 8。

 So it's going to stride however much it needs to， right？嗯。And then we simply add I to that。 right。

 So thread row instead of being here， thread row is actually here because it was previously， right。

 you can see how that translation works。 This was thread row。 This is long。 This is thread row。 Now。

 Now this is long， right， So's， it's the same idea。's we're just。

 we're just making the naming a little bit confusing there。 that's really all it is。

 We're just staying consistent with whatever this term means because we have to transpose it， right。

嗯。And then we just iterate through I as we need to，This should be intuitive。

 I don't really think I need to explain that too much。

 It's just like mainly paying attention to the the naming convention。

 So thread row versus thread column。 Like， why are those different， That's because you。

You' transposing。And then you do the typical write outs， so if we go back to this。up。

This is all it's doing， right， so。Revolving thoughtt IDX downwards。All of these。

 all of these threads are sort of next to each other in memory。 That's why we're str T M， right。

 T M is that。Yeah。This is TM， so whichever thread row we are at。

 we're going to stride Tm because each thread is going to take care of multiple of those values。嗯。

And yeah， we end up we end up just just sort of looking at this a bit differently。And then。yeah。

 just， just some more visual examples instead of having it as like here and then these these like inch is like。

Inch forward。It's。Right， but this is actually switched over。

 So it's just kind of the transposing spatial reasoning you have to have to get through。

 And then this all like is pretty straightforward。But yeah。

 now we can actually pop over to the the right out section。 Awesome， So we're actually almost done。

 We just have to write out the results now， and we have to make sure that these our。

 these are also in this float float prototype。 So also coalesced into the。😊，Global theor Ram， right。

 So we have the the normal iterate over TM and iterate over T N。

 except we change the iterators a bit differently。 So in T M， though the rows， we're iterating over。

 we're we're doing we're iterating up one each time。 So it's going to go1，1，1，1 on， right。

And then for T N， we're going plus4 each time。 So we have eight values here。And we have。

 we have two values here， right？ So when you have this total 8 by 8 thing。

 you would normally have to do 64 values。 But because we're doing float 4。

 we're storing four of those times 16 total right。 So you can kind of do the math。

 It's like four values， times 16 different rights。So it's going to do four values each right for 16 of them and we're going to pop full that full 64 thing across the TM and T N tile。

 right？Um， so we。We set this temporary variable。As the current C， the current C value， right。

 So this whatever whatever the current C is that we care about relative to how we've indexed through these right。

 And this is all keeping in mind to where we are actually at in the entire in the entire C matrix。

 the entire C matrix， right， So the thread row offset times this plus the res IDx M offset。

 and then all that times n， which is the strat of that。 And then plus our our columns times T n。

 and then our residX on end this should all make sense。

 This indexing should be like pretty much crystal clear we've done very similar to this already。

And a lot of the syntax is also similar to this float for we did here。

 So if something doesn't make sense， just look back at this and break things down again。

 that's the easiest way to do it。 But in here we have this， we have this temp type， right。

 and now temp。Keep in mind， this is what C originally was。

 so we can actually store things from the existing TM or the temp variable inside of it Again。

 We can actually do more to it and then write back inside of it because we don't care about the old C result。

 We just want to calculate the new one， right。So we have this this dot x part， which is the index0。

 so we're not going to add anything and then index1 and then  two and then three。

 and these are all X， Y， Z W respectively。So we have this alpha term。The thread results。

 which is with with respect to the thread results variable in the register。

 So it's going to be the res index M。 So which which row are you at， right？And then the。And then T N。

 which is， which is how that spans。 So you're going to stride over and get to whichever row you want。

 then you're going to offset offset by this。 And then based on which which index you're at within the float 4 array within that specific the float 4 window。

 right。You're going to add these to the actual memory addresses or the or the index themselves。

 right， sort as like kind of an effect type。So。This way。

 we can actually get the the value that we want。 And then we simply just add that to the beta Scalar and then multiply that by the existing C value as we got from up here。

 right， So that should be very straightforward。Luckily。

 this is only in register so the indexing isn't too complicated。

And then we simply just write back right so using the same idea that we did back here。

 the same indexing scheme， and we simply write write out C。On the level of threats。

That's vector memory coescing。Okay， awesome。 So now we can actually just print out how well these do。

 right， So we just finished up the vector， the vector co coalesced memory access。😊。

With vectorization， kernelon， let's go ahead and print that out。 How well does that do。

 So the last one was2D blocktyling， kernel number 5。

 We wouldnt print this out and we get a peak of about。9000。 So about about 9100 gig flops。

 and this one。About 10800 gigapopps， which is quite a big increase from before。

 So that's about what roughly。1 thousand0 and 600 more gigaflops than before， which is pretty solid。

 right It's like a 15%，16， whatever percent increase in performance。

So now let's actually go ahead and print like some more， right？I know the auto tuning one was good。

 so we go print 09。This one did about 11000。 So relative to this one， it did， you know。

 moderately better。 And then we can print out the last one， which was coubloss。

 So Coubloss was supposed to be the fastest。We can actually see that this 11496。

Is very close to the auto tune kernel。 Right？ So we actually look back to what we previously did。

 which was number 6。 We are very close to co loss。 So 10000 we'll just do 1800 divided by。嗯。

10800 divided by 1111000。496。So we get about 94% Kub loss performance just using the vectorized。呃。

I like the float for loading， right， So that's ridiculously good。

And we can still optimize further with these ones， right。

 So consider that if we were to optimize these further and maybe use some。

 some additional tricks that you'd find in like research papers， like this could actually get really。

 really fast， right so。That's a。It's pretty cool that we can do that just on our own hardware and we can actually see it from start to finish and understand it intuitively。

 the reason I'm not going to go over anymore is because it's just more and more complexity to dig through as you go through each one and I want to save some time for the last final project in the course。

 which we're going to do shortly but yeah， I'm not going to cover all of these I just kind of cover the main ones。

 So coes memory access from global just like a bump up from naive and then all the different tiling variants and then how we can how we can vectorize memory access。

 right？So given that， let's actually go ahead and print out the ad。

The assembly instructions for this specific kernel。 So if I pop out of here。

And go into source slash kernels。To NBCC。P T x。Then， we go。Number 6。Out， and you can just go。

Number  six， not P T X。Okay， so instead of that， I just remember that we had this main file here。

 which we can reference。 So if I just go ahead and save this， if I like take the the title of this。

And I replace， I replace that in here。And then we go ahead and compile。

 we're going to get our actual PTx instructions here so。It seems like we got some errors。

 which is because。I actually go in here。 We have to copy this， copy it back。Were getting them。And。

So pretty much what happened there was I had it imported properly。

 but we just weren't including the TN at the end here。

 so I just added that and now it's successfully compiled so we get kernel law PTx。

 we open this and we can go ahead and see let's see if we can find a E the 148s armed in here so I actually have to go in。

And， and change this to shader assembly。We can go ahead and do。And PCCC dash will do arch is S M。

Of arch equals S M underscore score 86。 And then we'll do Q binary。Main dots C you。And then out。

 and we'll do it main dot。Through a binary。And then we'll go ahead and to object， object dumb。

And we'll do main dots， keep binary just like that。 And we go ahead and move this up。

And we can see that if we look for the specific LDG dot E instruction。LB，G dot E。128， 128， 128。1，28。

1，28，128，1，28。And so on and so forth。 So how cool is that， We can actually verify that all of these。

Maybe we can find like a 32 in here somewhere。Oh， that's just gonna be in。That's a register。

That's a register as well。 That's a register。So we actually do not have any 32 B loads。

 any 32 B transfers at all。 Everything is perfectly。嗯。Everything is great。How wonderful。

So now that that kind of makes sense that we are able to literally see what the instructions are looking like when we provide optimizations。

嗯。You know， we can， we can actually。We actually feel a lot more confident in our ability。

 It's not just like me telling you that this works and trusting it。

 It's like you can actually see it。 This is what is being。

 this is what's being run on the GPUs controllers， the little migrant controllers inside that issue the instructions。

 right。And so if we pop back to here， there's one little thing I wanted to cover as an extra optimization。

 which is using tensor cores so。We go to programming Tensor course。You literally just search。

 it's on the NviIDdia blog programming Tensor cores in Kuda 9。 So Kuda 9， I mean。

 we already actually have。

![](img/0f9ea5e8bacc4cc914094ea7b918190a_25.png)

Are you here。Nvidia， SM I， we're on Kupa 12。5。 So that's fine。

 We don't have to worry about incompatibility issues。But essentially。

This gives the whole instruction sets。On how to use tensor cores， right， so。

Cooter 9 provides these new features， these tensor cores will essentially like for example。

 the on the Volta architecture， you can do this where it's like you multiply these two FP16 matrices and then you add another one right the fuse multiply and add operation we saw previously。

Except on the level of four by four tensors。And these were supported in the Kubloss Library。

So two tensor， two kuda libraries that use sensorsor cores are Kublos and QDNN。

 right the ones we covered earlier， Kubloss uses Tensor cores to speed up gem matrix multiply operations。

 and CoUDNN uses it to speed up convolutions and RNNs。So。That's cool。

 But what if we want to write our own， What if we want to write our own code that isn't dependent on Kublos right。

 because Kublos， we could just call like a separate function。

 but it might not be as slow or we can't like fuse the actual tensor core instructions with a specific kernel that we want to do Like。

 for example， flash attention， right， if we wanted to write that。

 Kublos might not let us do that because it's sort of independent。

 and we can't include those calls inside of kernels。

So if I wanted to actually look at how to use that。Where did it go。Roll down a little bit。

 cancer course and QD and N。And then programmatic access to tensor course。 And that's where Cota 9。

0 comes in。 So we're good。Essential， there's this new thing called a。The complete namespace is N V。

 and then N C plus plus， it's like the the W the WMMA。嗯。This means warp matrix multiply accumulate。

 which I'm not going to go over like exactly what that means。

 nor do I entirely know what's happening under the hood there， but。

That's that is the Tensorco operations that we can call right， So there's a bunch of examples here。

 I'm not going to go over this part， but this is just kind of like a nice little you know doc for understanding how the heck to use Tensor core operations。

And you might you might even want to implement those inside of the blocktling kernel。 right。

 So the ones that we just wrote， you might want to say， take like a single thread and。

Have like a thread or a piece of it and try to like block these actual tensor core operations and make these really。

 really fast。 So that way it's not just so that way it's not iterating through 8 and then iterating through 8 more and having 64 total operations to do。

 but rather just having one So these are literally going to be organized in a 3D structure inside of the tensor cores on the GPU And it's literally just like a 3D thing or a 2D thing depending on how big dimensions you're using because you can do like batch by time by channel if you're using transformers or you can do。

嗯。Yeah， just。There there is， there is a lot going on in the hardware， but you can actually。

 you can't capitalize on those。 So anyways， I'm not going to ramble on this is， this is Tensor core。

 You have permission to have fun with this。I encourage you to do so I might add some more to this course later on in the Gitthub repo that'll you know sort of talk more about denseor course。

 but this is。