# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P9：Chapter 8 (Triton).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/4d8567e259dcd64e302123211680bc64_0.png)

Okay， so we can finally take a breather now。 matrix multiplication is pretty much finished。

 there's there's a little bit more that we'll do later on， but for now。

 you can consider matrix multiplication finished for the next section or two。Now we go into Triton。

 which essentially takes the previous takes the previous chapter and says。

 let's abstract that and make it easier to use。 So so taking you know。

 major multiplication or like tiled optimizations。 where you'retying things into blocks and then you know。

 multiplying them together more efficiently， we can actually take that and do it in Python with much simpler syntax。

 So this is Triton。Triton is a bit different than Kuda， right。

Before I actually go into the the whole design here and what Triton is about。

I want you to pay engine something。 So if I go hip install， torch。

You'll see that we get all of these， all these all this nvidia stuff， which we've seen before。

 and then we get this Triton Triton 3。0， right。And Triton is used by pytorrch under the hood or accelerating and making things faster with Python syntax。

 right， Triton is also fast， just like kuda。 And so there there are some differences between them。

 which I thought I should highlight。So if we pop over to the。呃。Pop over to the Triton website。

 search up Triton Docs or Triton website or whatever， this will come up。

They also have a Github as well。 So the Github has， you know， a lot of。You know， useful stuff。嗯。Yeah。

 just playing around with it， setting up， configuring， try and doing custom things。

 but you can just pi install tri and like that and then it'll work the same way。

But if you do look at at the Triton website。You'll see a bunch of sections so like how do you install it tutorials on how to use triton。

 so there's like a bunch here， which I don't necessarily cover in this course。

 but you can you can go over more of these if you want to。嗯。

And then there's the important ones that we care about。 So Triton， what are like the Triton docs。

 there's like Jit， auto tune， heuristics， all that just going through。Going through functions。

And then we get into Triton language， which is the most important part of all。

We have a bunch of different operations here with Trident。

 and I'll go into the whole design of Trident in a second here。

 But this it just like makes it really easy to see that all of the operations are right here， so。

Like the programming model operations to know creation ops。

So if you have like if you have an X tensor and you want to make a y。

 but you don't want to populate it with anything or you just want to make it zeros。

 you can say zeros like right as a creation shape manipulation， layer algebra， so dot product。

Pointer ops， memory pointer ops， a bunch of things， math， there's a lot of math ops。

 reduction ops so like maximum where you have an array and you're trying to find the maximum of it and youre reduce it to just returning a single value。

Scan and sword operations， atomics like we went on previously。

 random number generation and etc cetera， right there's there's a lot here even even debugging and printing too。

 So try and this is this is where all of the operations are that you're going to find。

 which makes us really easy to go through。But if we go through。Where is it introduction， Yes。

 So the whole idea here。 And if I go to Triton。Yes， this one。So I'll look at this in a second here。

 but this is essentially what Triton was inspired by is this this paper here for tiled neural net computations like we went on in the previous chapter right and and this is the whole idea here I you have scalar couta has a scalar program and block threads versus Triton。

 which has a block program and scalar threads。 It's like， okay， what does this mean。

 This is super weird。 there's a lot of like geometry happening here。

 So like how do we actually break this down。Now。To clarify the reason why Ka is a scalar program with block threads is because you write a kernel to operate at the level of threads or scalrs in this case。

 So that's why it's a scalar program， each individual kernel runs on a thread。

 but you need to be aware you need to be implicitly aware that those kernels also operate on the level of groups too。

 So when you have， like， for example， shared memory。

 like that's something you need to worry about right。Kuta has。

Cut has blocked threads of scalar program。 It's like the actual kernel that you write and then block threads with the idea of when you actually write the the kernel itself。

 which runs on the thread， it has to be aware of all the other threads too that's kind of what I'm getting at there。

 And then Triton is abstracted up to thread blocks so。This。

 this essentially means compiler takes care of all these thread level operations for us。

 So when you write something at Triton， instead of having it run on each individual thread and have them communicate and be aware of that。

 it's going to write on the level of blocks。 And all of those like thread level instructions and optimizations are going to be handled by the compiler for you。

 So you don't have actually worry about those。And then when we talk about。When we talk about。

When we talk about scalar threads， it means you don't have to be as worried about them talking inter like interconnected with each other。

 You don't have to be aware because Kupa actually handles that part。

 So since you're writing on the level of blocks。 you don't actually have to worry about interthread communications。

 you just have to worry about what exactly the block is doing。

 write the operations out clearly for that。 And then train will actually handle that under the hood。

 So you saw how there's。There's very little operations in the Tri and dot language section。

 this is because the compiler is able to handle a lot of the additional operations that allow for performance increases。

 right？So idea behind that's the whole idea behind Triton and that whole blocked versusar blocked versus blocked in scalar threads philosophy。

So。Why can't we just skip Kuta and go straight to train。 Why can't we do this。Well。

Ttton is an abstraction on top of Kuda， so you have lower level stuff that offers optimizations and that you can be explicit about to the NviDdia compiler。

 the NBCC and Triton takes advantage of those and bumps it up a few layers to something that you can sort of understand easily and write less boilerplate code for so we still need to understand how Kuda works to ensure that we're applying the right optimizations。

 You can't naively write Triton code without knowing what's going on on a low level。

 It just helps you prevent boilerplate。You also may want to optimize your own kernels in Kuta。

 right So going back to what I said before， you kind of need to know the low level operations in order to make sure that everything is working as intended。

 right And if you want to build on top of Triton or build things like it or abstract above Kutuda。

 which is trying。 you need to learn Kuda， you need to understand what is kuda doing so that you can build on top of it so you can leverage what it contains already right。



![](img/4d8567e259dcd64e302123211680bc64_2.png)

And so if we go to the tritton paper here。Intermediate La compiler for tile neuralNe computations。

This is is essentially just。It。It does everything that Kublos and Couddi and N does。

 but does it roughly as fast。 And without a ton of boilerplate。

 So that that's like the whole idea is you have these tile computations that you have to do in Kublos and Coudd and N。

 and it takes care of those。 So I'm not going to go through this。

 There's is like this is a separate course going through all of Triton。

But we're going to go over like how do the basics work right so that you understand how triton can be applied and maybe it'll give you some ideas as to what to do later on。

Okay， so now we actually go into an example of a vector addition kernel intne。 All right。

 so I'm going to try to break this down as kind of as efficiently as possible。

 This stuff isn't too hard。 It's supposed to be kind of a break from doing things like matrix multiplication So you'll probably find this you'll probably find this is a end up end up being you'll probably find this end up being a breeze。

 So we start off you know we import torch So Triton is very closely linked with torch So we end up using that to to handle some other stuff like initialize arrays and matrices and stuff。

We import Triton， the Triton language， and then shorthand version of that。

 and then we go down further。We initialize a seed so that the results are reproducible when we。

 when we randomly initialize stuff to ensure that， you know we don't get errors or whatever。

 it's a good practice。And then we have a size of 2 to the 25。 So if we go into here， we go on。

This is 33 million elements long， right， So we go this。33。5 million elements long。

And then we just initialize our X and Y the two that we're going to add on device that are randomly randomly initialized and then we just have some benchmarking stuff down here。

 don't worry about this， this is just for testing and seeing how they perform which which we'll see in a second here but going up when we're actually adding them together this is when when you do when you're actually adding them you're going to add X and y which are tensors and then you're going to return a tensor right so it's just x plus y return output that's it very simple。

This is essentially an easier way of doing kudamalic， so instead of kudamalik and C or kutta CC++。

 you're going to go tor shot empty like， so it's going to have the same shape as x。

 but it's going to be populated with zeros。We do an assert。

 so we make sure all of our tensors are on the device。

We set numb elements to literally just numb elements of the output。 So how many。

What is like the length of this array？And then we have this weird configuration of of like how we how we actually launch a kernel and how we define like the dim3 and then the grid size and all of that stuff。

 So we have a Lada function here。 Don't worry about this too much， by the way。

 you would care about performance， not not like understanding how the syntax works under the hood。

But this is a just a lambda function and inside of here all like all you have to worry about is that we're doing a ceiling division of n elements。

 So let's say n elements is like 1024 you have an array 1024 elements and you want to add them together in blocks and your block size is 256 So what you would do is you would par that 1024 over four different blocks of size 256 right but if you have。

Say 1025 elements， then you want to make sure that you give it an extra block so that it doesn't miss that element right or else you're not going to get the right answer so you have to actually do a ceiling div so that it rounds up to five blocks instead of just rounding back down to4 because then you'll end up missing that extra one so that's all we're doing here and then just to launch the kernel I know it's weird you do like this function and then you index with this grid term and then you pass in your variables after it's like that's weird but don't worry about this too much So。

We just pass in the grid as like that like those like alligator symbols。 that's all this is。

That's your kernel launch configuration。 And then you have the actual parameters themselves instead of going。

We just go。嗯。We just do that very， so it's like a syntactical thing， right？嗯。Anyways。

 that's that shouldn't be too much of a question。 I'm not going over this because we care about performance as opposed to like what the heck。

 what the heck all these what the heck this syntax is， but yeah。

 so going up to the actual mechanics of a kernel enttriton and comparing that sort of side by side with with Kuta。

We have， we have X。we have to actually I forgot to say we add this Trident Jit decorator at the top to say that we want it to be Jit compiled by Trident。

 just like be aware of that because if you don't add this you're going to get errors but for all the different variables you have your x and y。

 your output， your non elements and then the block size， which you pass into here， x。

 Y output output elements and elements block size。Now， we have these as pointers because in memory。

 it's going to be， it's going to be laid out as the the first element in that array is going to or essentially this。

 this pointer is going to be the first element in that array。 So you want to start from the。

 you want to base it off of the start of that entire tensor or array。

 You want to continue from there。 right， So that's how Triton is going to interpret that。

 And then you do the same for。Why the output pointer， and then we just continue on。

So jumping down a little bit， we see a PID and so PID essentially says which which block are we at in the grid。

 right Now we have to be careful about this。So。A good way to think about which blockout we are in the grid is to actually go down to here and see how does this apply right so when we're actually in this array。

 let's say block size is 64 and we have 256 elements in this array。

You don't want to just say0 or one or two because those are going to be individual elements right。

 when we're looking at the actual data because remember， this is how we're actually indexing data。

 we want to make sure that we're keeping this block length in mind because block size is big right？

 So we're going to advance。um。Block size times the number of blocks。

And then the offsets are actually what's important。 So it's like。Whatever that number is。

 And then we're going to arrange an additional thing of02 block size。 So for like， say， 64 to 128。

 you're going to start the block start is going to be 64。

 And then we're going to arrange a bunch of different indices between 64' essentially just going to be an array of 64 up to1 up to 128 right。

 And that's going that's how we're going to index our data。

 So we do triton language which ought range0 to block size。 And that's what that is。

 And then we just add whatever block start is to that。

 And so hopefully that kind of like make sense in your head。 Now jumping back to Pd here。

You might want to pay attention to this term。 So in here we have access and builder。

 Don't worry about this。 Just worry about access。 So access is like block I X dot X， right。嗯。

Block block like X is the same as axis 0。Block ID D X Y is the same as axis 1， and Z is equal to 3。

 right so。We have to keep this in mind when we're writing more like you know 2D you know 3D spatial kernels then we have to keep in mind this access terms。

 So luckily right now this is very simple， but this is something we're going to want to keep in mind if if would do end up writing this is something you're want to keep in mind if you end up writing more you know 2D3D stuff。

好。Now， going down a little bit， we have this mask term， so mask equals offsets。

Baask equals whatever the Boolean， I guess the Boolean output of whatever if offsets is less than numb elements。

What this essentially does is。We have these offsets。

 which are the indices in the actual arrays itself。 So the input and the output point， input。

 sorry the x and y pointers， whichever indices at in those。

 we want to make sure that those do not surpass。 We don't。

 We want to make sure those do not equal to or pass nu elements。 right。

 It's going to be 0 up to nu elements and -1。 So we want to make sure that we mask everything off。

 That is numb elements or pass that point right。 And that's what this is。

 So mask is just going to be essentially an array。 It's going to do like。Is essentially going to say。

 you know， we have all these offices。 We have this giant like array in memory。

 And we're going to see。If。Like we have a， you know，64，65，67，122， whatever。

 We want to make sure that those numbers are less than a nu elements， right。

 So we want to essentially just making sure that we're not accessing something that's outside of our data structure in memory。

 We have this whole space。 we want to keep it masked to this one section。 right？

 That's what this does。And so we get a new array， which is mass。

 and that's just a bunch of essentially just a bunch of ones and zeros。

 and this behaves the same way that this if statement does。Inside of an addition。

 a vector edition kernel in coa， right， same idea。U。Now， going down further。

 we actually load these efficiently into a shared memory， so don't。Don't worry about how it actually。

 how it right and handles data， how， how it， you know， transfers data。 That's a。

 that's an optimization that's taken care of for you。

 So just assume that these are going to load in like starting from the like the beginning of X up to。

Up to the end。 So it's going to essentially just each each point， each point in memory。

 it's going to each data point in memory， it's going to load those in。 And it's going to do a mask。

 And it's going to say， do we want to actually compute these values or not。

 That's what this is doing。 So whichever point it starts at。

 all the way up to all the different offsets。 So it's like this point。

 And then it's copied and then all the different offsets。

And then you have a mask applied to those as well to say which ones do we want to compute。

 So if these ones are like extra just like compute this section。

 that's what that's what this load is going to do and it's going to efficiently load this into shared memory so the fast memory on the GPU the one on the actual streaming multiprocessors that's what this is taken care of for you。

And then we do the exact same thing for why。Now。Try and implements these block wise operations very efficiently。

 so you don't actually need to do any advanced stuff。 You literally just have these loaded onto SRAM。

 and it'll do a element wise addition， so itll it'll go through each one。

And just add together and notice how this is blue instead of red。

 That means like it's taken care of by trying for us。 So that's。

 that's literally how you compute the output。And then we just store this back again with another with another data transfer operation in Fright。

And so that's just going to be the same idea as here。

 So the starting placing memory plus you know the offset all the offset indices for that block。嗯。

The output itself。 So we're going to store the output。嗯。And then have this mask。As we did here。

 And that's how your in works， so。Hopefully this makes sense。

 Feel free to rewatch some parts that in entirely， you know click in your head。

 but now we're actually going to jump into the softm Trident function。Okay。

 so now we jump into Softmax and instead of just jumping right into code。

 I'm going to do a manual like hand example with this。So。Yeah mean。Delete that real quick。

Essentially what we're doing here， I have a C file。

 we're just doing this in C to understand what it's doing intuitively。嗯。We have an array of floats。

1 to three。 So it literally just looks like this。X。X is that。

 And so we're going to calculate the soft max of x。嗯。

So how this typically goes is if we search this up on Google。Softmax activation function。

It looks like this， right？ So you have this exponentiate， this input。

 So you have an input vector and this this， this symbol is the softmax function。

 and you go over each one。And then you essentially see how much each exp value contributes to the total sum of all the exp values。

 right？If we do， if we open here up。If I just open i Python。If we import math and go。

 say we go math dot E XP of 1。0。We're going to get 2。71 because that's what E is， right。

 So's going to be E to the one。 So our first value。Is going to be。2。71。And then， the second one。

It's going to be two， so7 point say 7。39。And then a third one， number3 is going to be 20。1， roughly。

Now we sum these all together。So。I's trying to autocomplete for me，2。71 plus。7 point。39 plus 20。10。

 and we get 30。2， right。Now in order to get the actual softmax output， we see how much each of these。

 each of these expiated values contributes to the expiated sum of all of them。

 well not expentiated sum， but when you expentiate all of them。

 you take the sum of those which is 32。2 or 30。2 and then you see how much each contributes。2。71。

 divided by。30。2。 So that's about 9 per roughly。 So we're going to go。0。09。嗯。And then we go， step。

39 is 0。24。And then the last one is going to be 0。67， if we go and do it。If you round up， it's 0。67。

 So you have that， right。 And then if we add these all these numbers together， 0。09 plus 0。24 plus 0。

67， you get 1。0， right。And these are all rounded， of course。 But， but， but the point here is。

 this is the softm。 Notice how we had this， this initial distribution here。

 And then we went to a new one， which kind of just made everything add up to one and gave it a bit of。

Gave it a bit of extra weight to the three， right， So notice how like a like three is three times that of 1。

0。The 6。67 is way more than 3 times 0。09。 So you can have that extra weighting for the bigger values。

 right， And that's what the softmax does。 So it's going to like essentially find like the biggest number and and put a lot of weight on it or highlight it the most。

But there is a flaw with this approach and。I'm going to explain this right now。Essentially。

 the flaw here is if you have， say， if you have X。As say one。1000。0。And。u。Negative 100， right。

 So sum of these， the sum of these is 0， right， have， you have a problem with that。 And。

 and that essentially means。This is going to。This is going to contribute a big chunk of this。

Or at least it's supposed to， it's supposed to contribute all of it。

 but it's not going to because you cannot contribute like it just doesn't make sense。

 How can you contribute like what percentage does1000 contribute to0。 It's like infinity， right。

So if you end up doing softftmax on this。Like even if you try to math dot E XP。Of 1000。

' going get math。 I would overflow error math range error because it's just too big of a number。

 right， so。What you can actually do is you can subtract by the max of， of all of these， right？

 So we can see。What is the maximum what is the maximum number here。

 So the biggest one is 1 thousand00。And so what we can do is we can subtract each number by that value。

So we go， we can say x。 We'll just say like x 2 equals。嗯。0。And then。0，-1000 is。Negative 1000。

 then 10001000 is 2000， right。 And so if we go。嗯。We go。Math thoughtt E X P of 0。Notice we get one。

Math or EXP of negative 1000。It's going to give us well pretty close to 0。

 It's not quite going to be 0， but it's going to be very， very， it's going to be a very small number。

 right， and then。Of course， the same thing with 200 is just going to be the same， right。

 It's going to be very small。 And so you notice how if we， if we originally just。

If we just did this one normally using these big numbers would have actually given us errorss。

So we can subtract by the max。We can， we can， you know pointwise subtract by the max number。

 and then we get something that makes more sense。 So you know zero contributes to all of it because that's what that's what the sum is。

啊。And so this is how we actually fall through in the softm function in C。

 so we have three separate for loops here。First one finds the max value in the array。

 so we just set the initial max value to be the first number and then we iterate through this starting at the next number。

 wet want to start it this first we don't want to start at the first one。

 but we start the one after it because we already know what this one is and we essentially compare if the new one is bigger than the max we set the max to that one。

And we end up with this， this max term， which， you know， same as we did up here。 and then。

We have this。 We have the accumulation sum， so we iterate through the length of the array。

And we do that index minus the maximum。 And then we， we add that total to the sum， right， we。

 we add whatever this was to the sum so that we can， you know， accumulate all of it。

 And then we just write out。We just write out the same value。

 we essentially just take the input and then replace it one by one。

 and we set it to whatever that expentd value is。Minus。啊。Or sorry， not minus， but we。

 we have that exponential exp value。 We' defy that by the sum。 Very simple。

 I probably could have explained that in a bit shorter time。

 but I just want you to like again the intuition for that。

 You've probably already written the softm and pi torch and nu pie I get that。

 But just to kind of provide that review as to how it works under the hood and this you know。

 numerical stability add on we have。So now。I have an example in Kuta as well。

 So I'm not going to go over this。But the idea here is in Kuta。 I mean， yes， you could just。

 you could do you could go over， you know the length of one single array。 But in deep learning。

 you're not actually trying to do that。 You're typically going to have a batch size and this batch size is going to have like a bunch of these that it's gonna to be a batch of arrays that you're gonna softm。

 right， and you're going do the softm on them row wise。 So you're going to do here， here， here。

 right， instead of just like to each element。 So it's going to go through the rows。

 And this is where we can actually get a speed of from Kuda。

 because we can give each each of the threads。 we know， we have batch size， many threads。

 And we give each of them。 we give each of them a softmax drop， right， So we see and here。How。

We see in here how we actually give one to each。 we give each。

We give each thread a separate softm drop that's going to go。 It's going to span 1024 iterations。

 or it goes up to the length of n， right， as we can see in these。 So like theoretically。

 it's going to take three n iterations because that's to go three different four loops。's。

 that's kind of how that works there。 So we want to， we want to pay attention to batch sizes， right。

 But there's， there's an example in coupa here， which you can look over on your own and get an intuition for the batch softm。

 but。It's very similar to the one we didn't see。No。We dumb into the one in Triton。Okay。

 so now we actually go into the softm tri and kernel itself。

 a little bit more advanced vector addition， but we're going to go through it step by step so。

We obviously import at the top。 I'm going to go sort of from the bottom here。

 explain what's happening and then what we're going as we're calculating the output。

 So we set our annual see， We make a random normally。Normally， distributed random tensor of floats。

 So mean 0 invari 1。So it's a normal distribution and all of the essentially the shape is batch size by n。

 so B by n batch size is 256 N is 2024 elements long。

 we're just going to softm those 1024 element rows。And we're going to do this on Kuta。

Now we're going to calculate and make sure that torch and try and now put the same thing。

 So typically you would do torch dot softmax or F dot softmax or whatever。

 And then you would go Dem equals1 right， And then we want to do that same thing for Triton and then make sure that you know the max value isn't too ridiculous。

 We're going to print that out。 and then we're going to make sure that this is all close with torch all all close。

 right。So we do the Triton softm， we go here。And in here we have rows and columns。

 So when we print out， understand。Print out input shape。 So we go here。Input shape is。As we want。

 right？Output， we're just going to do a mallic essentially right there。

 And then instead of doing some weird like meta parametera like doing like the whole like lambda function calculating。

 we're just going to do triton and the next power of two。

 So what this says is it returns the smallest power of two greater than or equal to n。

 So similar to what we were doing before but just a little simpler And thenre we're going set block size equal to the minimum of 1024 and this right So you can kind of see how we you can kind of see why why we would do that。

Now， we set our grid to N rows because。In our grid， we want a block for each row。

 right when we're processing in parallel， we want we can't we can't split a single row amongst multiple or at least naively。

 we can't split it across multiple threads。 So we'd want to do it for each block。

 So each different each different row would get its own block essentially。

 And that's how we launch the grid here。 And then you could assume that you know why we have this why we have this trailing is just that the trailing dimensions。

 You can just assume our one。 right， And so that's how like pytorch shapes work if you do like batch sized comma。

 it'll be like B by one。 And so it'll just be like a column vector sort of you could think of it that way。

 And then the softmax kernel。 We do this we call this the same way as we did vector add。

 except we add two more things in So we added in this X dot stride。

 this is just an input parameter to what's going be upstairs here。 So we got X dot stride， which is。

The？Essentially the stride of the row。 So we when we when we go across。

 it's like it's stacked in memory it's like row1 row2， row3， row4 right。

 but the stride is like how hard do you have to go to wrap around to a new one So when we say we want to go to row 4 you actually have to go okay well what is the what is the stride right how long do you have to go across to get to the next one It's like essentially the length and that's。

You know， we could say n columns， but we're just going to use the you know objective attribute x stride。

嗯。Passant and columns and then block size， right？ So we go up， and we see that。

We get the where did it go。Output x。Striide， stride and columns， and then block sides。Output， input。

Strides， strideide and columns block size。Now we do the same we do the same like program ID and the start pointers the same way。

We calculate this normally。 So which block are we at， right？

 And then we have to advance a number of indices forward in memory。 So it's like we， we essentially。

 we take the initial input pointer。 So where does it start at。

 Where does where does a starting place in memory and then。You can add that to。

We we take that and then we plus。Row I D X， So which row is it times the length of the row， right。

 so then we can get which row， What， Where is the starting row within that batch， right？

 So which row do we want to go to。 And then this whole thing is actually in the bigger picture。

 which is the whole memory， right， That's， that's what we're doing there。

 And then same idea for the output start pointer。 So we're essentially just finding the place in memory where we start based on。

Based on these three。And then we load in so you know we do the typical load so。Pointer。

 and then we want to load in all of the indices。 so similar to how we were doing it before。

 And then our mask is we're just going to make sure that this is smaller than N columns， right。

 making sure that we don't go out of bounds。And then this important term other is a bit critical as well。

So。This other term means that if you have， for example。

If you have 1000 elements in a row and the block size is 1024。 So it's going to be a bit longer。

 then that means you're going to process some additional elements。

 It's going to think that there's 24 extra ones at the end。 So what you can do。 I mean。

 that this is not this is not going to happen in our case because were very objective about how we define things。

 but in some cases， this will be important to pay attention to where。

You actually want to explicitly set the edge so that it doesn't mess up everything else， right。

 If that was like one， for example， then in our whole softm calculation。

 that would contribute to it quite significantly because it's， you know， it's。

 it's not just like massive sparse integers， It's like a like decimal places that are around 0。

 right？ So it's important to do this when， when we exponentiate when you do on。

If we go into Python here。Import， import math。We go。Look it can just say x。X equals negative float。

 and then IF。And then we go math's got EXP。X， you notice that we get 0， right。

 or if we repeated math of the X P of one。 You would get， we would get this number。

So we just want to make sure that that is not contributing anything at all。

 that that's all we're doing there。嗯。So all the other additional values， if they happen。

 we don't want those to contribute at all， just kind of the safety thing。

 It's good to look out for this。嗯。And then we just do the normal softm calculation。

 which is actually only takes four lines， so we calculate the max across across that row。

And then we get the numerator， which is， remember， we we subtract the max from that。

 We exponentiate this。 So we exponentiate whatever that， whatever that result is。

And then we get the denominator， which is a sum across。Each individual， each individual one。

 So there there's going to be some sum number。 and then we're going to do essentially this array。

 It's going to be an array of elements。 and we're going to divide this by a scalar value。

 So it's going to just like take this and it's going to divide， divide， divide divide， divide right。

 And it's that's how we get our softm output。 And then we'll see that we store this。

Similar to how we actually loaded things in initially， So instead of the row starting pointer。

 it's the out row starting pointer， same idea， we want to store a value， which is the softm output。

 which is what we calculated here， so that's the actual value inside of it。

And then our mask is same as as we did up here。 So we。

 we want to make sure that we're not doing reads and write out of bounds， right， And that's。

 that's pretty much the entire Soex calculation in Triton。 So， you know， I encourage you to。

 you know， play around with this。 You can do， you can actually do。You can actually go。TL do print。

And then we can go。Like P I D。 And then just put like row I D X you could do。R I Xs like this。

And we can actually print that out。So you know maximum difference between Pych and triton results is very small。

 results are close is true， and then we can see each each individual one of these。Like P ideas。

 you know。2，55， this is an X dimension， right。 So if you had like a， if you had like a。嗯。

This is axis， So we do access equals0， same thing with access of one。 then， you know。

 this would be on this on this spot instead instead of x， right？So， yeah。

 we print out whatever that value is and we get we can print stuff out in the terminal if I do like normal。

 just like save。