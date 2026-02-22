# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P7：Chapter 6 (CUDA API).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/288c1b6f722131e86fcef560de496a90_0.png)

I hope the last part wasn't too conceptually hard for you。

 that that's typically where people will sort of break down and question a lot of things。

 it was probably hard。 But anyways， I'm glad you made it through。 Feel free to rewatch some parts。

 That is one of the most challenging parts of the course。 There's lots to unpack。

 It's very spatially intuitive。 But this part is supposed to not be very spatially intuitive。

 It is supposed to be just like textbook examples。 This is how you navigate things。

 it's not supposed to be very hard， mathematicalmaticly， spatially anything。 So。😊。

This this chapter is on the Kuda API， so this is chapter 6， Kuda APIs。

 we have a few to go through Kubs， KD NN， etc cea， but I want you to navigate over to Doc。tonvidia。

com/kuuda so。Here we have a lot of resources。 We have a lot of cool things to look at。

And I just kind of want to point this out not that it's specific to the CD API section。

 but because there's lot there's a lot of useful things here。

 so you have your installation guides for like Windows and Linux right like this is just like everything you need to get started。

Programming guide， best practices， all the different you know Maxwell， Pascal Volta， Tring， MP Pier。

 Hopper Eda， Maxwell， all these different compatibility guides and tuning guides for different architectures。

 and then you have like your PTX， which is the assembly instructions for Kuta that's what it compiles down to。

And then just like API references， miscellaneous stuff and tools like NBCC GDPB for KUDa。

 so when we cover GDPB earlier in the C++ review section。

 this is the equivalent for KUA so when you're debugging coDa programs you'd use that and then there's like Ans compute which we use earlier and that's yeah just a lot of very informative tools here。

What we may mostly care about is the co API references。 So in here， we have runtime API。

 driver API and math API。 You can go through those if you want。

 But mainly what I'm going to cover is Coublos and Co DNN， which is over here。

 If you go to Dos video do com s deeplearning s Q D N。 you can find this。

And these are the main ones which I expect to cover in this section。

You can think of these like Kublos and Co D N N as they're not。 you're not actually writing。

 You're not writing things out manually。You're not writing out your own kernels。

 It's the the whole idea here is you have like this。

 this black box function that you call or like a it's binding into a shared object file， like an S。

 O。And。It's opaque。 So they use these， these， this word called an opaquestruct type。

 And what that is is is you're just calling something that is compiled down to to run on the hardware。

 you do not get to see it because it's， you know。And encode code it in some binary format that you can't really read as a human。

 And so you have to refer to these opaquestruct types to be able to call those。

 These are highly optimized。 So like the state of the art algorithms in the world for running。

 you know， deep learning algorithms that these are the fastest ones。

 Sometimes you might get something faster depending on the use case。

 but will generally assume that these the co API provides the fastest functions， generally speaking。

 so。When you're trying to figure out how to get the fastest possible inference to work on your GPU cluster。

呃。You might want to， you know， use something like K to API and then going through。You know。

 just going through and researching and figuring out how to get it done by going to like Google search。

 perplexity， Chad GBT， you know， and maybe anthropic models。

And then keyword searching in the Nvidia docs， like just a control F like that。嗯。

But the coD API is going to give you the fastest stuff， right？嗯。You may have seen this before。

 how we did this these like error checks。 And these essentially just just say like when you call a function and say like coublos。

You're you're going to check if， if that return an error or not。 And if it does。

 you're going to print the error and the line it was at right。

 So these are just custom ways of of printing out errors。 And when things don't go according to plan。

 So I have these both for colas and Q D N N。 So just checks the function。

 Make sure it went through properly。Now。Kublo is short for kuda。

 So the C is for kuda basic linear algebra subroutines or subsystems。 I can't remember which one。

 but it for it's for linear algebra stuff like matrix multiplication， right and S gem。

 which is short for single precision general matrix multiplication。嗯。

And that's that's like pretty much what this whole like readme files about。

 I'm kind of like reciting it as we go down， but you know。

 there are resources on this like proper error checking library samples。If we were to go to this。

 there's like a library samples where you can test out each of these。

But the whole idea with Kubloss and how it's important to deep learning is in something like the transformer or an MLP in the transformer itself。

 you're going to use this algorithm called matrix multiplication。

 And when you want the MLP to run really fast or you want this language model have really。

 really fast inference time。 You want the algorithms to not really have bottlenecks， right。

 You want them to run as fast as possible on the hardware。 And so using the subroutines in Kubloss。

 you can actually get that。 There are other ways where you can combine and mix things together。

 but that's more advanced For now， we're just assume that the fastest algorithms exist in Kubloss and codnN for deep learning purposes。

So we're going to go ahead and start here with Kublass。你好。Basically algebra subprograms。

Bk celebrating AI。I performance applications， like I said before。嗯。

Industry standard blast APIs and gem APIs。 So general matrix application with support perfusions。

 highly optimized for NviPs。 I'll dig into fusions in a second here。 Don't worry about that。

 But what what I've essentially done with each of these is I've laid them out into testing。

 So before I go into actually like printing out what the results are and how well these work and what the differences are。

 It's important to cover what they actually do。 What is the difference between these。 So。

Kublo itself is just the super high it's essentially the easiest one to use and get working。

 It's just like the standard that you typically start with and it's going to support your basic。

 you know， single precision， so FP 32。And FP 16 matrix multiplication， right？

KubloOSs LT is a lightweight extension of Kublos that provides a more flexible API。

 primarily aimed at improving performance for specific workloads。嗯。

Except this is more oriented around larger matrices。 So Kublos L T is optimized a little differently。

 and it can be faster than just regular Kublos in cases， so。When you have。

 when you have something that's a lightweight， ideally， it's going to be lower precision， right。

 you can think of the L as like light or lower precision whatever you want。 And And essentially。

 what this means is， is it's the same as Kubloss， except when you use lower precision like F P 16。

 F P8 and 8， they're going to run way， way faster。 And that's what L T is designed for。So same idea。

 just lower precision， bigger matrices， different kind of workloads。And then you have X T， which is。

 I don't actually recommend this because it's ridiculously slow。But you can。

 you can interconnect multiple GPus and CPUus together to solve a problem。

 So if you have a massive matrix， you have a giant matrix multiplication to do。

 you can actually split this across the CPU and GP。

 and they will talk to each other and get things done。 However， the memory bandwidth bottlenecks。

Really limit the compute。Because you don't just have this super fast。

 like this high memory bandwidth on the GPU that you can just go back and forth。

 like the memory bandwidth between the CPU and GP was really low。

 That's why it takes so long to copy things over。 So you have to worry about that。

 your solving speed actually gets slowed down a lot。 And this is one of the holdbacks with X T。

But you can run multiple GPUus。 It's designed to be threadsafe。

 ideal for large scale computations from， you know in distributedri workloads。

 large scale linear algebra that exceeds GPU memory。

 So if you have like if you have giant matrices that it's like 16384 by 16384 and you multiply that by itself。

 that might not all fit on like an 8 gig car。 You know， if I do I go to Python and I do 16384。

Gquared。That's what？8 minute， that's like 268。 That's like 268 million numbers。

 That's a lot of numbers。 And if you have three of these， if you have an A， B and a C all allocated。

 then that's like 70s。That's like 800 million numbers。 And then if you， you know。

 kick this up to like F P 32， you multiply by the number of you multiply by 4。 That's the。

 that's the size of the。That's the size of a float。 So 4 of 4 B。 And you get ridiculous numbers。

 like 3。2 GB of space。 So if you have a 2 gig card or it's like an embedded system。

 it's not going to fit all that。 Or if you were to bump this up to like， say，00000。

ThatThat's not going to fit right like these type of numbers are so massive that you just need to use external CPUU D Ram in order to actually store them right so you can there's obviously other ways of optimizing that。

 but X T allows you to do this。So。I did a run of these where the size was 163，84。

 And this all actually fit on my card because。I have 8 GB of GP P V Ram， which is。Low， but I。

 in some cases。嗯。Kublo versus Kublo X T， so I did five runs each， about 。59 seconds on average。

 and then this took about 3。5 seconds on average so。The results ended up matching。 So it was。

 they were like pretty much identical。 And then， yeah's，'s。

 it's just like insane how much of a speed up that gets when you just stick with using the GPU right。

 And so。That's like one of the examples why you want to be careful when you use things like Kubss X T Kublo Dx is we're not going to be doing that。

 we're not going to be using that in this course。 but you can look more into it here with this documentation。

 Now， cutless is something I'll I'll cover in the in the extra section a little bit more， but。

Kubloss and itsvariance run on the host。Whenever comes with Kubla Dx。

Isn't well super documented or optimized。And when we're trying to do things like matrix multiplication in a transformer。

 we may not want to rely on something or where the operations are scheduled from the host when。

 when we want to call like a Kublo operation， the C view tells it to do that， right。

 whereasas on GP P， it's just like a kernel that's launch and all the operations are are done there。

 So they're a little bit different in that regard。When we do like matrix multiplication。

 along with like a value activation and then another matrix multiplication and then another value and then like a convolutional layer。

 it's like。You typically don't have that in a single operation， you fuse those together。

 and that's this idea of fusion， which we talked about before。And。When when you。

 when you have something like cutlas， which is a template library that disabled a few things together。

You know you can get a lot higher performance。So。For example， like flash attention。

 it doesn't actually use cut lists， but it's an example of what fused co kernels look like。

 So flash attention was a paper that came out you know I think two， three years ago， something。

 if we just pull this up。It's， you know。It's essentially for the attention mechanism in transformers。

 And it has a whole thing。 And the idea is you have this， this attention layer in the GT。

 It's like matel dropout softm， maskask and another matel。

 And if you fees these together with custom handwritten， highly optimized kernels。

 you can make this really， really fast。 and you can speed this up by like 5 to 10 x on certain hardware。

 And that's the idea of fusion。 So cutlets will allow you to develop， you know。

 faster management multiplication algorithms。And then you would take something like fusion。

 and you would combine what you've maybe written in cutlas。 and you would。

 you would just combine everything so that you don't have to rely on whatever Nvidia provides。

 And you can just do your own thing。 right， that's kind of the reason why we do things like fusion and we use cutlesss。

 So template， template， linear algebra subroutines。But。Don't worry too much about cutlas。

 We're not going to go over cutlas in this coursetz。 There's a lot to cover there。 But anyways。

 that's like the whole idea of。That's the lady of Kublass。No。We dig into these。

I'm going to sort of go through this as best I can to illustrate what's happening。

So we need to import this Kublos V2， right？ So this is， this is a new thing we're going to add。

 We're going to add F F P 16。Inclusions。And then just some matrix sizes， right as macros。

 And then we're going to include these these macros that check for errors。

 So we wrap those around like， for example， here， when we， when we do a kuda mal。

 it's running on kuta。 So we have to make sure that doesn't return an error。

 We just do this consistently for everything to make sure that nothing just breaks everything goes according to plan。

 right。嗯。And so in this example。I'm actually going to go back to a section。

 there was a point I missed。As we saw。In the script。I make these arrays。

And notice how these are small， right？ There's a few thin。

 There's a few other things like this that you want to watch out for when you're comparing things。

Because what we're doing here is we're essentially comparing these speeds and how similar things are together。

 want to we want to compare like the FP 32 with the FP 16， see how they perform。

 make sure they match up in the end。And so there's a lot of things you have to watch out for。

Doing warm up runs is good， because。Kuta might incur some additional overhead when you do like the first few runs。

 so you want to get those done with。And then。Continue with the benchmark runs。

 So make sure that the overhead like just gets like removed。 You want it to like。

 just sort that out on its own for like a few runs。 And then you do like 100 benchmark runs。

 And you take the average time of those。 And that's where you get an accurate measurement of how long it takes to execute a function or internal。

 right。Without doing any marup runs， you might see like the first thing take like 50 milliseconds。

 And then the next one take 2 milliseconds。 And it's like， whoa， what what happened there。 Well。

 that was the overhead that you needed that that kubloss actually took over and required。

 So that's why you do the warmup runs。So。Warm up and benchmark runs。

 You want to verify all of your results。 So in。In here。Where was it。

Maybe we didn't compare results in here， but we do somewhere else。

You want to verify everything so that it all matches up。

And then the last one is when you're testing things from scratch。

 instead of like randomly initializing massive matrices instead of having like 00 by1000 and just like random distribution。

 you want to populate it with values that you can actually calculate on your own。

 like something that you could take to your whiteboard or do it in your head， right？

 So when you have something that's laid out like this， you can go ahead and write out。 Okay， well。

 why did it not work， right， then it's more more easy to break down the problem and understand what went wrong there as opposed to taking apart a nonreproducible 1000 by 1000 matrix you just can't do that。

 But anyways， going back to the point here。Dip， we initialized some matrices， so。3 by 4。

 and then a 4 by 2。 So they should have 12 elements。Right。We scroll back up。 This goes up to 12。

 and then this goes up to 8 as the2 by 4。We initialize these on the CPU， so C on the CPU。

At the single precision Kublo output on the CPU。And then。D。

The C co was output for the half precision。And then we do a CPU Mamal just to test the results just to populate because again。

 the CPU might be the easiest one to actually write out for us if we're transferring this from Python or nupyy。

 we can just write out the CPU Everything will be super easy to compare back to it so we just do that first we have this kublos handle thing。

 which I'm going to go into in a second here， how like all of these are how all these work together。

But you have this kublo handle， which it just gives like a kublos context on like what you're doing。

 you just have to initialize this for safety， We create that with a separate function。嗯。

We do all of our Mals。And then we have this this new function here， which you haven't seen before。

 this is called S gemm so。Single precision general， general with the G E matrix multiplication。

And inside of here， if I。And troll， click on this in V S code。We can see where this comes from。

 We can see where this comes from。 and I can right click on this and see where the root of this actually is。

 right。So we look at in order what all these are。 So we have the。The handle。The operation。

 these operations， I'm actually going to pull these up in a second。 So this makes more sense。

 We have the shape。 So M and K， the alpha term， which will make sense in a second。 We have a。

 the leading dimension of a。 So in this case， itll itll it would be M。B， the leading dimension of B。

 which in this case would be N， because it's an M， N times。N by K。

 And so the first one's going to have leading M and then the second one's going to have leading or sorry leading K。

 I mean， leading K。B is going a the leading dimension is going to be a K。

And then we have this beta and a C， which we element wise multiply by。

 and then leading the dimension of C。 So there's a lot of things you have to add to this。

 And it gets， it gets quite bloated fast。 So I guess to just sort of illustrate what all of those mean。

 There's a lot to unpack here。If we scroll down to。S， Jem。Asked Je。Kubos SGm， awesome。

This is a super important part。嗯。This is exactly what we just saw。And look at this。 So this is。

 this is what the matrix matrix multiplication looks like。 So we have a C。

And we do alpha times an whatever operation， which is going to be like maybe a transpose on a major to multiply that with some operation on B。

 which might be a transpose， and then plus the beta term， which beta is a。

Beta is just going to be a constant float number。 So like in this case。

 you might want to have a as 1。0 and B as 0。0 just so that you're only doing a times B equals C。

 right， but it does it does provide this this abstraction for you so that you can do more with it if you want to like add something on later。

 like maybe like maybe a bias， right。And then we have all these other operations。

 So Kublos Op N Kublo Op T and Kublo Op C， so。We wantna， we want to worry about the N and the T here。

 So the N is like。No operations。The T is a transpose。嗯。And then you have this column major format。

 so。Colum major throws a lot of this off。 So to illustrate this difference of column versus row major as we saw in。

 as we saw here。 So matrices are stored in column major format with these。诶。With these dimensions。

 M M by K， and then K by N and C M by N， all in major versus major is very important so。

It's actually a little harder because it's column major， but we'll make do anyways。The column major。

Major。We'll just have a。Well， actually， we'll make it real major first。 That's a good idea。

Row major a equals。And then call major。A。And then， the memory of layouts。

So notice the difference here。So we have a we have a。A 2 by 4 matrix， right， it goes 1， and 3，4，5，6。

7，8。 And then here we have 1，5，2，6，3，7，4，8， right？ So the whole idea here is we essentially transpose it。

We。The width this row goes from left to right， it is now going from top to bottom。

And now we have to deal with this。 So if we have something that's like， I mean。

 typically when you're going to feed a matrix into a matrix multiplication。

 you expect it to be in row major。And Kublas， Klas S Jem expects it to be any column major。

So there's a way to get around this and notice how this， by the way。

 notice how this is laid out in memory。 This is like a very simple way of looking at it。

 And then this is like， okay， that's， I guess so， but a little interesting because of， you know。

 it's just like 1，5，2，6，1，5，2，6 in that order， but。啊。

There's an interesting article I found on how to how to deal with this。

 So this is why we see our dimensions are a little messed up。On this。

Pay attention to your shaping from stacked overflow。

 I found an answer to this and how to make it actually worked to your favor， so。Where is it。

This guy pretty much said。Kubs interprets matrices as column ordered。 So when you execute this。

 you are correctly transposing because you're doing an opt T， which is going to transpose A。

 and then an opt T is going to transpose B。You correctly transossing each input。

But Kubla does the result in column major order， so you want it to come back in row major order so that you can use it for something else。

So what you end up having to do to avoid this whole column major mess is trick wholos into computing differently。

 And so the way you that way that you call this is you say handle up N Op N。

 then you go N MK instead of MKN。And then you go Alpha。And then your， your B matrix， instead of a。

Because normally you would do A here， but instead you do B。嗯。

And then you do your leading a dimension So remember n N is the leading a dimension now。

And then you have your A and the leading dimension for that is it's going to be K。

I know it's confusing， but just bear with me。 and then you have the beta。

Which is just like that that number you're going to multiply D by and then leading dimension for C is going to be N。

 So there's a lot， there's a lot of different。 There's a lot of weird changes there， but。Essentially。

 thats that's going to avoid the column a issue。 So when we do this in Ds code。

You can see that I call K loss SG with that same idea。 So N， N， and then it go N M K。We put our。

 we put device B matrix。Put N。Dvice a matrix， K， beta， device C matrix then n again。

 So just exactly like copy and paste from that。 And this works。So。This。

 this concept applies to H gem as well， which is what we have below。

 So I've done a single precision and a half precision as well。

 And there's like a little casting operation that you do here。 It's like a float to half function。

 which we initialize these as half precision matrices。

 And then we we do a float to half conversion and store the result in those based on our index，그러면겁이。

Have precision data to the device So the host， right， this is a host。Sorry， a half。And then。

We just copyied that we do the H gem， which is the half precision version of this。

And then we copy back。And then we， we can just print out the results to make sure everything matches up。

 So when I go NBCC。And we have to add this little e like link。

 this is for link and then we put Kublo at the end of it that's what that means because Kubos doesn't come just right out of the but you have to actually manually link it because that has to do that part separately。

They just go ahead and run this。 We can see。Our matrices， so we go up。This is a row major， right，1，2。

3，4，1，2，3，4，56，7，8，91112 and then same one same idea with this one it's， you know。

 it's a four by two。 so it's going to be four high and then two， two wide。And。So the two。

 the two width is1，2，1，2，3，4，5，6，7，8 right everything is lined up as we want it2。

 And when we do a row major matrix multiplication on the CPU we end up with what we're supposed to get。

 So these inner dimensions cancel out and we end up with the three and2 like we were we were practicing before right and we end up with the3 and 2 here。

 these results， these are these are our verification results， 50，60 114，140， etc。

We do the KubOS S gem result， we get the same shape。嗯。Same numbers。And then the H gem result。

 after we cast back to single precision。3 by2， boom， boom， boom， boom。Right。

So that is just a very clear， concise example how unlike the differences between Kublo。

 S gemM and Hm， all the differences is just half single versus half precision and。

The key point of changing how you set this up。 This is the most important part of the entirescript。

 is just what it， what it is， what it does， and then everything in between that we need to pay attention to in order to keep everything in real measure。

So now we might move on to Kublos LT St。If we just pop over to right here， Google+ LT。So。

Kubla L T is the lightweight version， and it's designed to hold much bigger matrices。

 And so I figured little something to do with that out the hard way that I was playing around。

 You cannot have。Marices without multiples of four。 So if you have like a three by four。

 like three is on a multiple of four or two by four。 both of them aren't multiples of four。

 those that does not work。 That will not， that will not return successfully。

 But if you do have like a 4 by 4 or4 by 8 or like a 12 by 16 or something like that'll work fine。

 So if we like right click on this just like I found this in the Kubos documentation。Where did it。

 Where did it go。Let's search this up。Oh， maybe I should copy this part。But yeah， so if you plug。

 if you plug that string into here， you'll see in the Kibloss LT Ma， it's going to be。

Scroll down data ordering。 So4 by the line leading dimension。

 leading dimensions must be multiples of four dimensions。 M and K must be multiples of four， right。

 So it's just universally a good idea。When you're working with big majores， don't do like。

4091 4096 is just kind of like makes logical sense to do that so。

That's that's all I kind of wanted to say for that iss to watch out there。

 But let's go ahead and just dive into like what the actual LT Ma code is doing。

 So we have this new include header or this new include that we have to do。

 So Kubss Lt do H and then we have the regular macros for check and code un checking KubOSs for errors。

We have the CPU implementation to compare against。We have the print matrix。

 so that's just going to like conveniently print things for us so that we can look at them and make sure everything lines up。

And then notice how I make the sizes4，4 and 4 right so nothing less than that square matrix square matrices。

 I do also make sure to make these piece like different elements。 So if these were a clone。

 this was like11 to 16 and then one to 16。 like you might not get the results you want。

 So you want to make them a little bit unique so that you don't run into like any weird cases where you think you have the right answer。

 but you don't So I change this three right here to a4 So it's 4 and then 4。

 And then instead of 13 to 16， I did 17 to 20 just to mix it up a bit。Now， the actual magic， I mean。

 we have a lot of stuff happening here where we。Where we essentially。

Where we essentially make like a like a FP 32 matrix。

 we co a malic and we we populate those and we also have a half。 So this is just the half of a float。

 So it's FP 16 is what this is。And then we just populate those with。We。

 we populate these or we populate it。I think that's。Oh no， we already populated them up here。

I'm being silly。But we go down after we've like KdaM copied everything。

 this is all on the device now。We have this Kublo LT handle。

 So this is this just the handle that we need to create the context。 We go and create that。

 And then we have this new term called a Kublo LT matrix layout type。

 So this is just there's a few types we need to ensure that this goes properly and this is one of them。

 So essentially just the shapes and the data type that we're going to use。 So co to data type。

And then this， this kind of follows the same idea as the whole column major thing。 So if we。

I don't know where exactly this was in the docks， but if we go to Kublo。What was it。

 It was the matrix K+ L T matrix layout to create if we just entered this in。We see it's down here。

 And if we take a look at the rows and columns number and rows and columns in the matrix。

 and then leading dimension， leading dimension of the matrix in column major layout。

 So this is the same idea。 and I'm going to show you how to like get through that。

 it's a little bit easier intuitively to sort of see that how that pans out。 But yes。

 we do need abide by that column major rule there。 So。Pppping back here for FP32。

 we just use real and then 32 F。 So if we actually look at this specific type like where does this come from the coup to data type。

 you can actually see a list of these So we have anywhere from like like real number So R is real C is complex and then this number is the precision So 16 is half and then 32 is single and then 64 is full and then you have like the other smaller types that you can use and then like just normal f is essentially what that difference is is like normal Fp16 will have it'll have a signed bits that's either positive or negative and then it'll have a certain number of exponent bits So how big is like the integer before before the decimal place and then the menteisse of bits which is how precise can it be in the decimal places right So FP16 is gonna to be more precise in decimals and then B F16 or brain flow 16 the reason。

It's called Brain flowlows because it came from Google Brain。

That that is going to have less mantea and more exponent。Exponent bits。

 So that's how that kind of naming scheme goes。 But all we need to worry about in this case is the the real 32 bit floating point and then the real 16 bit floating point。

So we can see that we use those here just for the 32 bit。

 we use that and then when we're ordering this， we want to do so that the first matrix A is going to be of shape n M M by K。

 so we want to flip that So it's going to be K by M。

 and then because we've flipped it we need to put the leading dimension here right so leading dimension is at the end。

嗯。And that's， that's that， so。Matx B， same idea we have is normally K by n。

 so we flip that and then put the new n as the leading dimension and that same idea here as well。

Then we go to the FP 16， which literally just uses real。

 but we replace the 32 with 16 and we do the same exact thing with shapes。

 and then we go down to the mapm description type which we just have to create。

 we just have to create that and essentially we pass in this type that we define the memory address to that。

 the compute type that we're doing and then the data type。

 so we look at this it's going to be the mapm description with the Kublo Lt mapm description type like we had here。

And then the Kubloss compute type， which I'll show you in a second here， and then the data type。

 which we were doing before， which is just going to be FP 32。 So we go to this compute type。

We actually see there's a few of these。 You just do like control click to look at those。

 But there's a few here。 So we have like Kubla compute16 F。

 which is which is what we're going to want for the the next one。 But we're using this one right now。

 You can do like fast。 You can do like fast。 so it'll it'll like。

 I can't remember exactly how it changes those inside。

 but it's something in the realm of like accumulating in this and that。But yeah。

 so these can be it kind of just depends on like what you're doing if you're sticking with Brain Fat 16。

 then you can you could pick that type， you could do like fast up to you， but yeah。

 that's that's the whole idea there。So。If we pop back to this one。

 we notice we're just using the compute 16 floats and then the data type of 16 bit float as well。

And then we're going to we're going to set an attribute。

 and the parts of this attribute that we're going to need are the map description type。

 which we defined earlier。 We're going to need a description attribute， which we which is。

If you can literally go to these。And these are， these are essentially just the。

I can't remember exactly what this is， but it's probably like some transpo like transpose A and then transpose B or whatever that is。

 that's what I'd assume this is。 I haven't looked into this in depth， but。

And then this one is just going to be the kublos operation。 So yeah。

 so essentially just like transposing or not， and then the the size of this kublos operation type。So。

That's just like this essentially so we're taking this this transpo operations and that we're just setting what that that op is so when it does like op and then in brackets a like that's what this is。

And then we go ahead and do the Kuboss LT Mam， which itself takes in a handle the MamL description type。

An alpha a matrix layout， B， matrix layout for B， beta， C， C matrix layout， D and etctera， right？

You can pretty much just directly paste these like there's a lot of these that we don't actually need that we can just set to null and aren't really required。

 So don't worry too much about that。 You just kind of want things to be in the right order。

 And so similar to how we did for regular kub losss， you're going to do the B matrix first。 and then。

And then you're going to do the a matrix after， right？So' that's kind of how that goes。

 and then we just do the checkkuub+ to make sure everything goes properly。

And then then there's an important part that I kind of like messed up here and it was a little silly。

 but I was trying to do this 16 bit floating point， Kuboss LT Mael with with the regular alpha types。

You know， notice how this is like that this is void doesn't specifically say float。

 So I looked I looked at that and I was like maybe maybe like we shouldn't use a 32 B number and multiply that by a 16 bit floating point number。

 Maybe that that's not how it goes。 So it' was like。

 okay and at the time I was getting a bunch of zero output。

 So I figured this might be a good fix and it ended up working。

 So you pretty much just have to typecast this。 So float to half and then you just set you know your alpha is gonna to be one。

 your beta is gonna to be0。 You just want to do a map that's all you care about。

 So that's how you're gonna set them and then just have alpha half and beta half and just set these accordingly and everything will work according to plan so。

That's how it goes。OnceOnce we're done those。We copy the results back to hosts。

 we're not doing any like benchmarks here， we don't worry about that we just want to make sure we have the correct results for both the KubOSs LT single and the half precision。

And so we just we essentially copy these back， we do a CPU Ma to essentially get a verification output so that we can compare it to。

And then we， we do the actual comparison itself。 So we use a standard library。 absolute value。

 We go this minus that。 It's going to get， give us some value。 That's like。You know。

 hopefully less than one times 10 to the power of negative  five。And if that's false or or sorry， if。

 if this is bigger than that number， if， if it's bigger than what it tolerates。

 then it says they don't match and we end up returning。 they don't match。

 So if I go ahead and actually。嗯。Run this， we have to do link Kublo and link Kub+ Lt because remember at the top here。

 we did Kublo LT。 H， so we have to include that。And then， if we just。Run this。

We can see that we get a matrix A。 So row major， matrix B，4，4， and then 17 or 20 as we as we wanted。

 And then we get a C output。 So 106，6，64，106，6，64，106，6，64 for all of these different precisions。

 And we can see that these match with intolerance。 Awesome。

 So that's just like comparing them and making sure that they work the way we want them to so we can like carry that and import it to something else。

 but。😊，Then for actually comparing it for measuring performance， we have a different script here。

 So I essentially did the same thing。 Don't like worry about a bunch of what's happening in here。

 This is， this is just a this is just a。A benchmarking script that I wrote。B。

We're comparing very large matrices， so we do a 4096 by 1024 times a 1024 by 496。

 so the inner dimensions cancel out， the Ks cancel out。

 and then we end up with a 4096 by 4096 matrix。And。And so。

I pretty much do a naive matrix multiply because these are very big。

 The CPU will take forever to do these。 So I wrote a naive matrix multiply that still gives。

 you a verifiably true answer in row major order。And then。You know， we have our our。

Our normal distribution random number generator here。That， you know， ensures everything is is。

Kind of just。goeses as we want such some essentially like when you do torch dot R N。

 it's going to just do that。 It's going to make it like Rand n as it's for normally randomly。

 normally distributed。That that's what this is doing and then verify results。

 same idea it does the relative error match with intolerance。We do a timing。

 so with our previous streams， so we don't actually put the stream in。

 but we just want to record the time and do this eappsse time thing and then just return that to measure it on the actual device itself。

And then we benchmark。And we just have a bunch of other stuff filled in in between here。

 the same as what you saw in the previous script。And then we。

 we just end up printing out the average time afterwards， so。

It'll also return the max error we get as well， consider there is some error with FP 16。

 so we should know about that too。But if I， I just print this out here to compare。We print this out。

Notice so。Okay， so Kublo results match the naive kernel with intolerance， results match。

 results match and results match。 A。 So everything is lined up。

 I did give it some additional tolerance here just because of some of the error。

 But here we notice that this error is not super significantificant。s not this is the maximum error。

 So most of it is going to be very insignificant compared to this。

 This is just like a side edge case， which might pop up a few times very like not often at all。

 So when we actually look at the times。 We can see normal Kub loss gives us Fp 32 average time of 2。

5 milliseconds， Kublo Lt gives us an an average of 2。 about 2。8 milliseconds， which isn't amazing。

And then Kublo L T FP 16 gives us 063 milliseconds， and then L T gives us about4。46 milliseconds。

 which is really fast compared to this naive kernel that we've written before。

 So this took 28 milliseconds to write。 This is about the time that it takes me to ping the Google servers。

 about 28 milliseconds。For it to run the complete naive kernel and the LT took of a 0。

5 milliseconds that is insanely fast。Like， look at the if you just look back at at how we we were。

 we were doing a matrix multiplication of like taking the。A column and do producting it with a row。

 like you have a。It's like size1024。 and it does that。 and it does for every single combination。

's and it does all of that in。Half a millisecond。So that's， that's about 5，1000 of a second。

 But yeah， anyways， that's。That is kubloss L T。 For this point。

 you might be a little upset or frustrated about why I'm just showing you code and then reviewing it and not like writing it from scratch。

 like starting from the very top。 Like， let's define these and then write this and then write this。

 The point is like all of this。 It is a lot。 It is a lot of lines。

 I'm not going to type this all manually。 The course is long enough already as it is。

 I'm not gonna make it 10 times longer by writing everything by hand。 But yeah， you you。

 you kind of get the point。 you， I identify the main。

 the main material that you need to learn the most important stuff。 And I highlight it。

 But I don't need to highlight everything。 Like writing check Kubss is just redundant writing。

I don't know Like writing writing this stuff iss just redundant。 Like you already know what that is。

 So that's that's kind of why I'm sticking away from that side and just trying to kind of trying to make like fast progress here。

 We might write out some things later on just just to kind of help you understand it when it gets more intuitive。

 and， and you're actually like building stuff。 But right now， we don't。

 this is not very conceptually hard。 So we're just kind of flying through it。

 But this next part is on Kublos X T。 So。It's essentially the same thing as what we've just done。

 except it's a bit different。 We still do the handle。 We still create it。

We do this new thing called device select， which remember when I talked about how you can have multiple GPUs and and do computation across multiple GPUs in the host。

 that's what this is。 So we。We essentially just do this little hack and we just device select whatever the main GPU device。

 And that' that's how we do things across。 So this is this is just a little hack when you have one one GPU so that you do this。

Mm。And then we do this X T S gemm， which is the same exact thing as we've been doing before。

 except you have these things that are on the host and then they're managed by this this S gemM function。

 So you don't have to actually move anything to device。

 You just you don't even add I don't have a single coM copy in here。

You just pass in your matrices on the host and it'll manage all of that memory back and forth。

 but at some performance costs， so you'll see that in a second when I compile this。

We don't actually need to link L T， but that's fine。

And so you can see maximum difference between CPU and GP results， right。 And then if we go to say。

And then we just link blue losss。We'll give that second here。 I did。

 I did the exact same thing as as our Kub loss Lt， but for X T instead and made very big matrices。

 So 163，84， you notice the Kub loss run does。You know， like I like I think I highlighted this before。

 but 0。59 seconds or 0。6 seconds on average。 and then the Kubos LT is going to be way longer than that。

So。we'll just give this a second here to finish， but。Yeah， you get my point。 It takes a while。

 You don't want to run this。Maybe you don't want to run this in production。

So we get the average time， everything matches with intolerance and we're good。But yeah。

 that's Kub+ Xt for you go ahead and delete these。I hope you enjoy that section on coub Bs or Kuta basic linear algebra sub programss。

 That was， that was quite a bit。 Hey， we got a second part on coup DNN。 So when you do。

 when you do for example， like hip install torch like this。😊，And you see like where is it coulo。

 Q D NN， right， that's that this is where is where it's kind of coming from， right。

 And you have all the other things like QF F T and Coo randomand number generators and cous solvever and coos Sps and collective communications across multiple nodes。

 profilers， Triton， which we'll go into later。 right， I mean， this is。

 this is why I'm covering this stuff。 so that you can。

 So you can kind of work with it And you understand how pieytorrch works under the hood， right。

 That's one of the main reasons I'm putting this out so。We're going go to Kuddi N。

There's there's actually a lot more nonpack here as compared to Kublos。

 but it's not conceptually hard。 Some of it is a little bit intuitive， but not really so。



![](img/288c1b6f722131e86fcef560de496a90_2.png)

Kianan is not。Entirely for matrix multiplication， it does matrix multiplication in some operations to really speed things up。

 but it's not a performance bottleneck。 You don't actually explicitly do matrix multiplication in Q DNA。

 That's not a thing。 That's what cola handles， right， So in QD。

 you're going to deal with things like convolutions。Poling layers， softm， dropout， right。

 bathroom normal， tensor transformations like reshaping and concatenation， layer norm， all this。

 right？So all these other deep learning operations other than matrix multiplication is what QDNN is going to cover a lot of a lot of the commonly most commonly used ones。

 So this this is kind of why I'm bringing you to the docs here is because this is a super direct interface with everything So they actually have their own thing docsnet video s deep learning coDNN and you go there and it brings you to this page。

 So there's multiple things here。 we have like getting started or installation guide which we don't care about and the other ones the important ones which is backend API and developer guide So we're going to be looking at these two today and doing some examples of coDNN operations and comparing them so。

We go to like back end API overview， we can see it's like。Cudus。

 so it supports the coos drones that we were talking about before。

 It has multiple things that it's kind of like linked to。 So there's like。II don't。

 I wouldn't pay attention to that entirely， but you have these。

 you have essentially have these three parts。 So you have coudon and graph， coudon and oxs。

 coon and CNN N and adversarial， so。Graph is going to that it's， it's not。It's not。

 It doesn't support like a graph operations where you're like dealing with graphs。

 It's more so how do you combine operations together in the form of a graph。

 So when you're doing like like a convolution layer and then you're adding a bias and then you're doing a max pool after it Like that's going to look like a graph right。

 you're going have these nodes essentially where it's like a node is an operation and an edge is a tensor or a matrix。

 And so it could be like convolution 2 D And then there's going to be an edge。

 which is the which is the data flowing from from the output of here to the input of the next node and that next node might be like the bias that adds right。

 and then and then it's going to flow out of the bias into like a max pool layer or an average pool layer。

And then it's going to go from there and so instead of doing these separately where you do a separate function call for convolution bias you do like a manual bias kernel and an Emma manual max fluid kernel you just fuse these all into one and you keep track of all of your all of your data in between and it does that for you so coudion that's what the whole coudion and grafting is it supports you know both forward and backward past so when you're going through calculating the predictions and when you're modifying all the gradients and then back propagating through it' supports both of those right so it's designed for it's designed for kind of just putting something in place instead of having to write all the kernels from scratch is just kind of makes your life easier that way。

So。There are multiple things within a coudion N graph， so。We have these pre compile engines。

 runtime compile engines。I have this pulled up on my second monitor here。

 which I'll probably just bring over。Where did it go。Yes， so the precomped single operation engines。

 I'm going to make this more readable。The pre compileild single operation engines precompiled and optimized for a single specific operation。

 like a convolution， because they're pre compilelid。

 They offer very efficient execution and are inflexible in terms of operations they can perform。

 right， They're compiled down to machine code。 They only do one specific function on something。

 but it goes very fast because of all the optimizations in binary that has， right？ So like。

 for example， major of multiplication engine that is pre compileild and optimized specifically for that operation。

 right， like similar to convolutions。 And then there's generic runtime fusion engines。😊。

Designed to dynamicallyuse multiple multiple operations at run time。

 So offer more flexibility compared to pre compile because they're generic and they can adapt， right。

 These are things that would that would happen during the compilation。

not might not be as highly performance optimized， but they are generic and they act as like a generic fuser of operations together。

 so you will get those performance benefits， but they're not going to be as high。

 so you still get them， but they're not be they're not going to be as high as something customly written for that algorithm。

Then you have a specialized runtime fusion engine， similar to generic runtime fusion engines。

 but they are typically specifically optimized for certain patterns or combinations of operations。

 right。Offering runtime flexibility and leveraging optimizations for particular use cases or operation sequences。

And then for example， an engine optimized for fusing convolutional layers followed by activation functions in neural networks like similar how similar to how I was talking about before you have like convolution and then a bias and then convolution bias and then a max pool layer similar similar to that right it'll recognize your code architecture and it'll find the fuseed patterns where you would get a speed up so it's going to just it's going to be it's going to be smart right it's going to try to be smart when it's compile those down and seeing where you can actually get a speed up from。

嗯。And then you have the specialized precomplied。 So precomplied for specific sequences。

They offer the same high performance as pre compiled single operations of these ones that are really fast。

 but can handle sequences of operations rather than just single ones。So these are actually。

These are actually amazing If you are trying to do a lot of layers。 Like if you have a whole， like。

 say a transformer block in a neural network and you want to do that entire attention block。

 this is an example of what that would be。 So you have a lot of different operations that you're doing in there。

 But if you just have this wrapper that says。😊，Multthead attention。You call that you get everything。

 you put everything in that you need and you get everything out that's useful and then you can continue on and it's going to be highly optimized precompiled into binary specifically for that right so this is kind of how QDNN is structured and this is these are the things you're going to you want to pay attention to and you're trying to optimize when you're looking out for how you can take advantage of underlying QDNN features。

So， you know， there's an example of like runtime fusion right here。

And then if we go back to the graph API， if we go back， I know it's bright， you'll be fine。嗯。

We pop over to this this graph API， I think this sort of was。 Yeah。

 graph API with operation fusion so。Convolution forward。Point wise bias。 point wise value。

 right that's。That's kind of the whole idea。 And if you wanted to use these together。

 you would do like you'd have like essentially some organization you'd have three tensors that you input and that would be like their variable names and then like these two would go through here like your your X and then your your weight kernel。

 the convolution filter itself is your W and that would output something with this arrow and then this one。

 this bias would come in and it would essentially add to the output of that convolution and then you would do a pointwise value。

 which is its just a。It literally just goes one by one，33 each element。嗯。

And then you get your output so that that's the idea of a graph is like you have these。

 which is your data flow， the edges your is your actual data and where it's flowing to。

 and then the points， the nodes themselves are the operations so。Continuing to go through this。

 you know， inputs convolution backwards， So alpha beta， D Y， W and Dx。

 and then you would end up getting。Yeah， you you kind of get the point you put whatever in is required for an operation and you get whatever out is is useful right。

 especially important you pay attention to that in the backward path of things because there's going to be more data you'll have to take care of。

U。But yeah， these， these kind of work the same way all around。 But normalization。

 you have like your mean epsilon and variance。Then your scale。Continuing to go forward。Same ideas。

 generic ramp and fusion engines。You can kind of just scroll through this and get the idea about how everything is architected。

There's， there's quite a bit here。 I don't expect that you'll read all of this。嗯。But。Yeah， that's。

 that's pretty much how the whole fusion engine thing works。 I know it's a kind of a。A silly term。

 but it is you are effectively fusing operations together and you could say that access as like an engine right So if we go back to this VS code here that I've opened the readme file you can actually find these in here So just you know a bunch of bunch of stuff but like the graph API very important。

Matmole。Convolution forward， backward， backward data， point wise。嗯。Yeah。

 just like for pretty much some of the images copy and pasted and then this one was。

 this one was actually support。This one is support for the different compute capabilities。 right？

 So if you have like， for example， if， if I did， can't remember what it was。

 it was like device query。 Remember that when we printed out the compute capability and mine was 8 8。

6， so。I would actually not get the convolution backward filter fusions。

 I would not get this because it's only supported on 9。0 and up right。

 So pay attention to things like that when you're trying to fuse things together for like research production purposes。

 you want to pay attention to what is supported on your hardware or whatever hardware you're working on。

So that you don't like try to do something and have it not work and waste time。

 So it's good to just like double check with this stuff and see this is all in the coud in and docs。

 but。There's still a few more sections we have to cover， so I'm going to dig into those。

 We have the Ops API， which I'll dig into next is very simple if we just go to。Here， we go to Ops。嗯。

Essentially， you have these same opaque str types as you did with kublos。

 except they do different operations， so you can do like like you can like create tensors， pooling。

 filter， dropout， loss， activation， all of this。 So the actual functions here might be hard to read。

 It's very bright。But。Actvation backward activation forward。

 you just have like a massive list of stuff。 I'm not going to go through these one by one。

 but but you get the point， these are all the operations that are supported with KUNYN tokuDNN。

 and we're going to test we're going to test some of them out。So， you know。

 you get a bunch of like descriptions about each， what each of these do。 So it， you know。

 in case you're wondering about something or you're not getting an output as you'd expect。

 you would generally refer to these docs。 So you could whatever type you're working with or whatever function you're trying to call like。

 let's say you're， you know， working with this。Or maybe you're doing， let's see。

Maybe something simple like a。Like activation backward， right？So you have this。

 you copy it F and you you can find these all across So you have the couddnet activation backward and it has all the different types in here that you would use and then you have the this this original one that we highlighted before。

 So that's how you navigate these you just search for whatever is wrong and then kind of just like look at that and see any of the any of the notes on it and see if you missed something that's that's kind of how you're supposed to approach these。

And then going into a CNN API， So this is where stuff might be a little bit interesting。

 It's not like any graph fusion stuff you're doing it's just like raw algorithms。嗯。So you'll have。

 you know， convolution backward bias， like all just all the different convolution stuff there is。

 I mean， there it there is fused ops， so that's where like some of this would come in but。Yeah。

 this is this is where all the convolution stuff's going to be for like image processing and you name it。

 right， So we're going actually use convolutions in a second here。 So I'm I'm going to save this。

 but's you approach it the similar way as you would with with operations。

And then you have the adversarial API。Which is same idea， but， you know other functions。 So like。

 you know， R N Ns， seat CT TC loss， multi head attention。We'll do， yeah。

 see mop ahead attention to weight。 so if I go。Multi head attention。 Mal head attention forward。

 Asome。 How do we use this。Right， there' theres melt ahead。Attention。Forward。

 there's 22 of these in here。21 now。So you kind of get the point we can scroll through these。

There's a lot， cheese。So this is how you would do a multi head attention block forward in the forward pass。

 There's a lot of stuff in here。 but that's that that's kind of how this goes right。

 just the adversarial like extra， the other section， miscellaneous， whatever you want to call it。

 But now we can actually go into some of the。Comparisons。To understand。

How to actually use coDNN in a coa script now we can actually go into some of the code and examples behind coo DNA and how it works under the hood well not how it works under the hood。

 but how we can use things like Pytorrch under the hood to make operations really fast。

So in this example， you know we do the coupa runtime and the coDNN。th。

 I'm just going to do the 10h function for example。

 and in case you haven't seen the 10h function yet。



![](img/288c1b6f722131e86fcef560de496a90_4.png)

go to Google Images。It literally just looks like this10h。Or like this， Maybe this is a better one。

It's like between negative one and one。 It's just a little activation function that you do。

 It's like a nice smooth S curve。 and yeah， so that's。That's all we're really doing here。

 We don't actually need to like do the type of the formula that's already done for us。

 I've actually written out the 10H kernel here and operation is literally just 10 H F for 10h function on device。

So very simple。We want to have a tensor with the shape， what's it called。And by。And by sea。

 by height， by width。That's the format we want to use。 So it's gonna to be like N is batch size。

 channels is channel， C is channels height and then width， right。

 So the whole idea of like channels is if you have like like an image， for example。

 like the image or video you're watching me on right now， This is gonna have three channels。

 It's gonna R GB right， So this is if say you've， you've done some convolutions。

 And now you're now your channel dimension is very big。 So instead of three。

 you've got like 32 elements per pixel that you have to keep track of and and do operations on right。

 So we're making a big tensor here， big tensor。 if I actually going into Python new 256， going go。

 well， four times because 4 of the number of bytes。

 it's going occupy four times 256 times 32 times 2。Times 2，24 squared。We end up getting this number。

 And if we divide this number by 1 million。It's about。1。6 GB。 That's how big this tensor is。

 And we're going to do a 10 H on that。It's so coed in and is going to handle this。

 and we're going to compare that to the9th kernel。And yeah。

Just stepping through this same kudamalic initialized data kamman copy。

 we're going to create some events that we can time stuff on the GPU。

 We're going to do our R warm up and benchmark runs。嗯。

We're going to do some warm print within a na kernel。嗯。We're going to do benchmark for it。

We're going to set up Coion in。 and this is where we're actually going to learn a little bit。

 And then like benchmarks to Coyion N， of course， this is where it mainly takes place， so。

We have this coudon and handle type。We createed that。We have this tensor descriptor type。

 so you actually need to it's like the when you did like a matrix a descriptor or matrix B descriptor。

 it's the same idea， but we do that for tensors because it's you know it's more in the deep learning context there's more deep learning operations and coDNN since it's deep neural network deep neural net。

 right？So。😊，We have creates Tensor descriptor， which is going to just take the memory address of this and actually create the tensor descriptor based on the type。

We're going to set the tenscriptor， so it's going to be。This type， which we， which we did already。

 the tensor format， the data type， and then each of those N C， H， W format， right， So we do this。

 we do this format and you can， you can look this up and there's。It's right here， Tensor format。

 so we can do NC HW， we can do NWC or N NHwC and et cetera， right。

 So that's we just we just pick this one。And then this data float， we look at this。

 we can have like a bunch of different ones fast float for F。FP8。

 So you'd have one sign bit and then five exponent bits and then two mantea bits， right。

 So it's 8 total， right， And then F8， you know， more， more mantea bits and then Boolean。

 we have all these different types。 But we want the float。 There's no like float 32 here。

 We just want a normal float。 No， no half no B F 16 None of that。 just something basic to， to use。

And then we create not only the tensor descriptor because we have the tensor itself。

 and then we have the activation descriptor， which is about what the activation is going to do。

 and we have a custom type for that and you can go here and there's a bunch of difference。

I think it's。I don't know where exactly this is， but I just like to right click on things to learn。

Good luck。We create the activation descriptor with its memory address。

And here we have the activation scriptor type as before， we have the activation mode type。

 so the activation mode is going to be 10h， and then the propagation type is just Nan。

 we're not doing that。嗯。And then the coefficient is going to be 0。 So there's not gonna。

 I don't know what。 what is co F。 I don't know if that is。 But anyways。

 this is just like the template layout we're having。

 And I don't expect you to like go through this and understand every single character that's happening here。

 This is just kind of a more template example to show you like， how we're comparing these。

 how we're running and test。 And you can like take these out and put them into other pieces of code。

 So I don't like feel bad at all if you don't understand this。 It is there is a lot。

 But if we go to like this， for example， we have like sigmoid value 10 H clip value Swwish all this。

 right。So we just want the10H function。Now。We go to activation forward as we saw just like a few minutes ago。

 we have the Cuudion and handle， which we defined before， activation descriptor。

 which we just covered the alpha parameter， the tensor descriptor， which we covered up here。

We have this。We have this void X， so that's just that's just the input， a beta term。

 which we don't need。And then tensor descriptor type for y。

 So in the output itself is just a it it's nothing， it's nothing particularly special。

 it's just a void。 So we don't need any like special types for it。

 It's just like a raw data like array output essentially going to be a bunch of floats right So that's that's that。

 And it's going to be on device。 that's what we have the D there。

We're going to synchronize everything and then do our benchmarks run， benchmarks runs。

 we're going to find the average time we're going to verify against the CPU。Like a CPU10 H。

 for example， it's not not going to take long since it's like like a pointwise operation。

 it's just going to go one by one through it， it's very it's like linear time。So when we actually。

When we actually compile this。10 H， good get。See it knows。We run this。

Actually to be surprised by something。So give this a second to run。

My machine might be liking a little bit， I'm not sure， but。

We're going to let that run for a second here。 Our matrix sizes are， are quite big。 Remember， these。

So。You know， tensor size as we wanted the naive cur kernelnal time。 notice how this is actually。

Baster than the Accuudion and activation time。嗯。They're both correct。 We just compare the results。

 you know point wise。And。This is faster， why。That really made me angry when I， when I saw this。

 I was like， what is the point of having a having a coion an activation， Like。

 what is the point of this， And the point of that is just to。

Give give yourself things like alpha and beta right So when you have alpha and beta。

 these are extra numbers that you have to consider in the operation。 And when it's so simple。

 when it's as simple as just a like exponentiation or like a multiplication。

 and it's like a very simple。 for example， R takes almost no time to complete 10 H is like a very simple operation just on a single number and you just output that to the same index。

 it's very computationally simple。 But when you add in little things， like alpha and beta。

I suspect these are what actually caused the performance difference。

It might be mostly these or some coudy in an overhead。 I mean， again， we don't even know what this。

 what this is doing under the hood。 It's a complete black box opaquestruct。

 We don't know what's happening。 So it's hard to actually know why this happens。

 There's not very many resources on。Why custom kernels might be faster than CoD and N。

 I haven't really found any of that。 So we're just gonna hold the assumption that there's this big opaquestruct black box thing that we don't know。

 And then you also have just the alpha and beta as well that you're you're times and adding things by。

 right。 So that's gonna add some extra compute compute overhead。

 But these are not very big differences And all right。 So you have like 8。523 and then 8。6。

 It's like if this is like nothing。 This won't actually matter in production。 It's like。If you。

 if you take the difference。If you see how much faster。The naive couldfernalized。

It's like literally 1。3 per cent faster， which you're not going ever going to notice in a real environment like that。

 this is unnoticeable。 So it doesn't actually matter that much。 If you care， like， totally just like。

 go okay go ahead go and write your own kernels。 But that that， that's a general idea。

 It doesn't really matter that much。For convolutions， it will matter， though。

And then going down to this I wrote up a pietorrch script to just kind of illustrate things out manually。

 So like how pietorrch handles， how pieytorrch handles the custom10 H。

 like when you write it from scratch on your own。Versus when you just use the built in detorrch。10h。

Re go， yes。Or shot 10。嗯。So just kind of comparing those side by side and seeing how they perform。嗯。

So if we write these out。O， it's taking some time to。Do this。 Yeah， so custom 10 H。

 that's going to take 21 milliseconds。 remember how Coy and N beforehand was taking about point。

I don't know what it was like point。It was it was a very small number。

 The custom like built in 10H is still very fast。So if we go back and we just。And VCC compile this。

 and then。No run， and let's just like look at which what the shapes of our numbers are real quick。嗯。

If I do batch size by， say， or if I do 256 by 32 by 224 by 224。Rand end。

 and we wrap these in brackets here。We we can check this one real quick and see how fast this runs。

And then we will compare the Python script to that directly without like deleting the output。

 so we can't see it just so we understand like how much performance could be gained from， say。

 using using like a custom written ktocurnal。Our custom written coion in function。 So if we go。

Python or compare， it's going to take a second。 Oh yeah， randomno memory， awesome so。嗯。Rand， yeah。

 I know。 that doesn't work。I bumped this down till like 128， in my work。It's not very fast。Yeah。

 so like。Custom custom 10 H is super slow。 and then the built in one，4。3， let's say 4。4 milliseconds。

 right？嗯。And then we go up and we can see that， you know， this is， this is actually。

This is about to double that， right， So if we do 4 point about 4。4 times 2。8。8 right？

 So we go back up。 And it's like this is less than that。 So if we write a naive co kernel。

 like this is just naive。 If you were to optimize this and implement something like a loop un rollinging。

 which will go until later and you optimize this even just something as simple as an activation function。

 You can get this surprisingly faster than ptorrch。 and just like write everything manually。

 you can actually get considerable speed ups。 So that's just to provide some context there。But yeah。

 activation functions， don't worry about too that too much， it's not really going to affect you。



![](img/288c1b6f722131e86fcef560de496a90_6.png)

嗯。And then we go to like convolutions， right， is this is an example of where we're actually using convolutions so。

You know， we。We， we have a lot more things to pay attention to。

 I'm going to dive into this right now。 Now we can jump into convolutions a little bit。

 I've been hacking around with some of these。 And let's just going show you how these。

 how these work。 So we're going to start off with a visualization first。 I'm going to bring over a。

Convolutions， visualize。 just pop over to here。 And this is just what it looks like。 So we can like。

 you have these input sizes， kernelnal size， padding， dilation and stride。 input sizes this。

I can change the input image， the kernel size， the actual weight itself， the weight term。The padding。

 so how much black pixels are put around the input， the dilation of it。Right。嗯。

And then stride as well， so I can make it stride by one each time or stride by2。Um。

And that's that's pretty much just u that that you can mess around with that your own time。



![](img/288c1b6f722131e86fcef560de496a90_8.png)

But I've written two scripts so。1 for piytorrch。 So the piytorrch and this one use the exact same values in the exact same order。

 with the exact same parameters here， they're all the same。

 And I'm just doing a sad side comparison of them so that we can get our desired output， so。

It's essentially。It's essentially like a like a4 by4。 The input is like a4 by four image。 So 1，2，3。

45，6，7，8，9，101112，13，14，15，16。 And then the kernel itself is 1，2，3，4，5，6，7，8，9。

 and it's just going to2222222。Right， let's going do that。

And we put a padding over it so that this is going to end up flooring to one。

 So kernel size is3 and then divide that floor by  two。 So if we go Python， go3。2， we get one。And。

That's just going to be our padding and then torch is going to do that with this functional libraryiv here and we get the output right？

This should be very self explanatory， very easy， we're just reshaping it and then reshaping it here as well。

But when we look at this parse， this is actually where the fun kicks in。

 So we do ourudon and dot H at the top。 I've written a naive co kernel for this for doing 2 D convolutions。

 Take an input， a kernel output the width， height in channels， out channels。

 kernel size and batch size。 So don't， don't worry about how this works internally。 Just。

 it just let it be there as some like template code。 that's going to do what we want。 It's a modular。

 so。And then we have all the same settings as we do in our pytorrs ripped at the top here。

 so we define like how big our inputs， outputs and kernel elements are going to be。

 We print this out， we do our classic just Mals， we have our values organized。아。

More co toM copy stuff， and then we create the QDNN handle。

 So this is all very similar to what we're doing with coDNN in our 10h function。

We created an input and output tensor。Buildiler descriptor for the kernel itself。嗯。

Convolution descriptor for the convolution operation， we create all of these。

 we create the convolution descriptor with that memory address。

 we're going to use the 4D descriptor because it's going to be shape of batch size by channel by height by width。

And then if we look at these， so we have the。We have the tensor descriptor the format。

 so how which what it was like the shape of it， and then the data type。

 which is just a float 32 as we have here。嗯。And then we have the n by C by H by W， right。

 So batch size by channels by height by width。 And we do the same thing for all of these。

 The output is going to be out channels because it's not in。

 It's going to be how many out channels do we get in the end。嗯。

And then the filter descriptor is going to have a different。

 it's going to be organized a different way。 It's going to be out channels by in channels by height by width。

 So out channels， in channels height height by width。Right， for these。For the kernel itself。

 for the convolution filter， you could have use this interchangeably convolution kernel and convolution filter。

 same thing。 And then the actual descriptor itself this is a 2D descriptor so it's going to be a 2D convolution。

Can we just。Dump all these in。 So the padding H， padding W。

U and V and dis just we're not even using dis convolution mode。

 So it's going to be cross correlation and the data type is just float。

 So I don't expect you to know what all like the convolution laws are and everything。

 We're just comparing to pytorrch and making sure that everything lines up。And then。In terms of the。

In terms of the algorithm itself， we have a little thing that searches their stuff here。

 I might change this later。 this doesn't it's not very beautiful to look at。

 but what you can do is actually just like literally this or is it。This algo here。

 when you do the when you give when you give coudyian N。

 like a workspace size to do the operation in， there's this coudian N convolution forward algo type。

 which is right here。Forward algo type。 And there's a bunch of them in here。 So by default。

 what that's supposed to do is cycle through them and find which one is the best。

 but I find that it might be a little bit better to just cycle through these one by one on your own。

 So try out implicit jam， try out precomp jam， try out gem。

 try to direct FF FF tiling Vigra unfused count right So try all of these out and see how they work which which I have in this comparison script we're gonna do later on but yeah don don't don't worry too much about those you can kind of just run the script as is but we're just trying to find the best convolution algorithm for our problem at hand right So when you have a smaller kernel and a small image a certain like maybe an implicit gem might be faster than say an Fft tiling because the overhead right see you have to just consider things like that your problem size。

 all that stuff。The workspace size is just how big。

How big you actually return the minimum size of the workspace to be past the convolution given an algorithm right。

 So you're essentially just saying how much do you get to work with here。

 and this is defined by a bunch of things that it just decides this right so we give it a bunch of descriptions and it's going to use that context to decide what the workspace size should be。

U。Now。Now we can do our benchmark warmup and benchmark runs。

 so we have this you know just skipping alpha beta， we have this convolution forward function。

 which I'll show you in the NviIDdia docs in a second here。

This consists of the handle alpha tensor descriptor for the input， the input itself。

 which is just any just a void pointer， right？And then the filter descriptor。

The kernel convolution kernel。 So that point again， a pointer to to an array。

The convolution descriptor， so actual operation algorithm itself， the algorithm， the workspace。

 which we just in workspace size and bytes， the workspace size and bytes， we pass in this。

 we do this size T， which is like a size type for like storing large values。

 and we put this into here， and then this value changes based on these settings， right。

 So when we put this back in here， it's going to decide when it's actually running this。

 how much do we need and what are the resources requirements， it's predecided， right。

And then we do we just enter the output description and then the output the output device array right and then we do the same thing。

 but with our con futuity except there's like it's less complex to filter through and then we synchronize all of our threads and blocks in the GPU with pseudo device synchronize very simple and we do the same thing for benchmark friends except we just add a time an event recording as well right So fairly simple concepts happening here。

 just timing and benchmarking and mainly just filtering through what the heck of function takes in and what are all these types doing right that's really the mess you have to dig through。

Now if we go down， we can we actually print out the coudin an output and the naive kernel output and then the flattened one as well so that we can compare back to pi torch element by element。

 we just destroy all the context afterwards， same thing with the 10 H。

 same thing with the 10 h kudos scripts。Going， run this。So。Out。01。Just like that。Liinnk could in in。

We we run this。All of these are as expected。 And so it's， it's going to just， yeah。

 it's going to select an algorithm。 These， These are all messed up。 I might change these later， but。

We notice that couddiian N is slower than the naive kernel。

 And that's because it's just really small。 right， It's very small。

 Couddian N probably has more to organize。 It's got these alpha beta terms everywhere that's got to take care of them。

 Yeah， there might just be some extra overhead there。 So it is， it is indeed。You know。Like 3。

 four times slower than this， just just because it's smaller and it's not a big problem size， so。

If we look at the output here， we see 111178，217， and then the end is 274，275，175。 Now。

 if I go and run。But torch compare。It's going to do the exact same thing， notice how we get 111。

 178217， and then 295 or sorry， 27429295175。So go back here，2，74，2，95，1，7，5， perfectf。

 So everything we can look through these， these all line up 1，2，3，4，5，6，7，8，9，1011，1213，14，15。

16 elements。 And this one has， know，16 elements， as we print out。嗯。At the bottom here。

 just the length of that。So I try to be like fairly quick with that， it's very， you know。

Kind of just a bunch of boilerplate code that we， we run through。 But now。

 now that we know that this works and it's outputting what we' wanted to。

 we can actually go take a look at the comparison script。 So the comparison script。



![](img/288c1b6f722131e86fcef560de496a90_10.png)

Actually， real quick， before I go to this comparison script。

 I'm going to bring up the the coudon and docs here just to kind of show you。The呃。Notice CNN。

So we're doing this convolution， coian and convolution forward， right， So we look at this。

And there's a bunch of things in it， so like this thescriptor type。Handle alpha betta。

 So it just describes everything that we need to know， right？

 So if something I said didn't make sense， maybe just look at here。

 And it might make better sense to you that way。 But if we want to say look at something like the forward algo type。

 we go here。 click on it。 And there's a bunch of， there's a bunch of value。

 So implicit gem Expresses as a matrix product without actually explicitly forming the matrix that holds the input tensor it。

 So there's a bunch of descriptions here about like different algorithms you can use。

And just like when you might want to use it。There's also other articles on like which ones are good for different cases。

 convolutions are very very well covered in the whole deep learning space。

 so shouldn't be too hard to navigate。But。These are these are going to be your forward forward pass algorithms。



![](img/288c1b6f722131e86fcef560de496a90_12.png)

Now， if we go back to。We go back to this comparison script。

 I'm essentially doing the exact same thing， except I set the。

I set the algorithms used to implicit gem。 So that's the。That's this one right here。

So I just set that manually。那。Yeah， that's， that's， that's pretty much it。嗯。

Now we we set this to algo and then we just plug an algo in there sos that's like the main difference And then the other one is just how we initialize our data。

 Everything else is the same as this initial like just the the convolution compared like between pi torch。

So we choose it。Yes， so we initialize on the CPU with just a bunch of random values。

 And then we just do an operation with those。 So I make the。

 I make the elements a make this whole thing a lot bigger。 So it's 224 by 2，24 by 11 by 32 by。11。11。

32，64 not， it's not times all of these， but the input is going to be of size width by height。

It's gonna be width， by height， by。By in channels by batch size。 So N HW， as we did before。

It's going to take up a lot of space， but we're just going to benchmark this and see how it goes。

So we're going to run this， get a batch size of four。And we notice co in an average time is 14。

8 milliseconds， and the knife kernel average time is about 82 milliseconds。 So if we do that。

If we do that division there。We notice。That we get a 5。5 x speed up by using coudDNN。

 How awesome is that right， I mean， if you optimized this naive kernel up here and made it like more specific to your your specific use case rather than calculating a bunch of stuff。

 it would be faster， but this is kind of just like for demonstration purposes。

 CoudDNN is still wildly fast and it would take a while to get something that is actually more performant than this。

 like significantly more performant would take a lot to do that。

But that's that's the idea right this is why you use things like coy and and and Pitorrchches because they're they're just like super fast。

 they just it just did a massive convolution operation of like an image with 32 channels of batch size 4 and a kernel size which like 11 by 11。

It's just like insane the amount of operations it does in such a little amount of time。

So that's what we're working with， that's Coy and infor you。Now。

 when you're working with big massive data centers and GPU clusters。

 even if it's your own local rig that's just on the side and you have 8，40。

90s or 39 is connected to it。 This part might come in a little bit of handy， right。

 So larger rigs or data centers。Let me just change that how that looks。

 So you have Klo MP versus NCCL versus mig。 Now these are all different。

 I'm going start with Mig because it's the easiest one to explain。

 essentially think of it as your like your Amazon， your AWS and you have a you have a giant you know GPU inside of your inside of your facility or data center。

 And so typically with this type of GPU， most people aren't going to use the entirety of it。

 just like a small chunk。 They just want the parallel processing aspect for like some some whatever signal processing。

 I don't know。 And so what you can do So you can actually split that node。

You split that node into a bunch of smaller GPs with multiple instances GPU。

 you can have multiple instances connected to the same card and you can split workloads evenly and securely across those and so's what that's what MIG does It's used in data center environments use cases right and then you have NCL。

 So NCL is actually really， really important or distributed cluster computing So this is essentially going to it's exactly how it sounds right it's not going to it's not going to do operations across but it's going to help manage and communicate different things across a cluster。

 So used for distributing information collecting it。

 acting as a general cluster level communicator whereas Kubloss MP up here is going to be doing the grunt work of doing like say giant matrix multiplications across like a note of888100s。

And then NCL is going to is going to like run this in batches。 So remember collective communications。

 these operations within that and and there's more resources on this would be like all reduce。

 broadcast， gather， scatter across right so not like there's no like multiply or like fused operations in here it's it's doing it across a cluster and communicating communicating data right。

So just for reference in Pytorrch， you would use distributed data parallel for this distributed cluster level of computing。

 so distributed data parallel data parallel is at the module level which can run across multiple machines。

 so module would be like say a function in Pytorrch right。

Wwhich can run across multiple machines should multiple processes and create a single data distributed parallel instance per process and there's a bunch of more stuff you can read about this this is used a lot actually in Pytorch it's very simple to set up。

But this is like kind of all of that simplified into one usable thing。嗯。Now， going back， there's。

 I do have more resources on this， too。 I'm not going to cover all of this since I don't actually have a cluster in my house to experiment it on。

 but there are some links and resources that you could， you know。

 you could find yourself going down a rabbit hole with these， which is what might be quite fun。

 but Kublo MP is actually going to。It's literally designed to do distributed basic dense linear algebra。

 So if you're doing like a multi GPUsor tensor operation this。Kublos MP would handle that。

 So if we go back here， and we go to Kublos。Kubos MP P。

 high performance Kud a library for distributed Denling or algebra。嗯。Getting started， for example。

 like code samples。Right。You have these giant like grids and stuff that you handle。How to use it。

Yeah， maybe like how to use it， for example， CAAPI。

And there's a bunch of interesting resources on here as to how you would do things。

Maybe there's like an operation。I don't know this is up for you to navigate it's optional you don't actually have to know Kub LosOSmp because Pytororch does a lot of that for you if you're just working with those workloads。

 but if you're going to be working on like data center infrastructure。

 this is something you want to learn like Kub LosOS MP and NCCL so。

Hopefully that helps to provide some context on like larger larger setups。

