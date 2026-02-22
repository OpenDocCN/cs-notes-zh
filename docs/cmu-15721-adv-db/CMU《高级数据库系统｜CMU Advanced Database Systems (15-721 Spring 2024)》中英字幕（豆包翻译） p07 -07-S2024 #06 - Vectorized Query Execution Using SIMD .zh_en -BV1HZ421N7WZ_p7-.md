# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p07 -07-S2024 #06 - Vectorized Query Execution Using SIMD .zh_en -BV1HZ421N7WZ_p7-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/a55ba0e98df074bca24360ded1a60926_1.png)

🎼。All right， so today we're going to talk about。Vectctorize query execution。 Again。

 this has been the thing we've been leading up to the entire semester。 Like， know。

 we've been saying this is， this is one of the ways that like a modern overlapap system is going to get good query performance。

 We'll see why and why， why and why it doesn't always do this。😊。



![](img/a55ba0e98df074bca24360ded1a60926_3.png)

So last class， we talked about how to take a query plan。

 divided up into pipelines and run them in parallel。 And so this is the notion of this。

 this method is called task parallelization。 So how to take a。A query plan。

 break up the tasks and run those in parallel。 We have said haven't said how to schedule them and where to schedule them。

 that'll be in in next week。 But at a high level， we understand we could run things in parallel。

 We could coalesce things with， with exchange operators。

And then we also discuss how we the data system actually would evaluate any kind of expressions and wear clause or a joint clause。

 And we saw this as being a， we sort of preview to query compilation stuff that we'll talk about on。

Or just in time comp completionilation or cogen stuff we'll talk about on， on Wednesday this week。

 And then we also introduce the idea of query adaptivity。

 We didn' we're not gonna to push on this too much just yet。

 But it's the idea that the optimizer spits out a query plan。😊，Then at runtime。

 while the data system is executing that query， it can decide whether that query plan was a good idea or not and can make some changes either to change the ordering that that it checks prediccateates。

 what code path it would use to do certain things。 But then we'll see later in the semester of how to do bigger things like。

Change the actual query plan on the fly while we're running。G。

So or today's class is going to be about vectorization。

And the idea here is that we want to take the scalar algorithms that we discussed in the introduction class where we're going to operate on a single tuple at a time。

 and in some cases， even a single opera at a time， and we're going to convert them into a vectorized form and rely on Cdy instructions that the CPU can provide for us to be able to run our run multiple operations within within an operator or expression。

 whatever we're trying to do at the same time。😊，And so this is to we notion as data parallelization that we're going to have multiple computations occurring at the same time for multiple pieces of data。

 and then CD is going the way that we're going to achieve this。So why does this matter， Well。

 again in the same way that scaling out across multiple threads， processes or nodes。

 it's going to give us additional improvement of performance because we' not be restricted to what a single thread on a single core can do。

In some cases， we can get even bigger speed up because of CD because that also can run parallel across multiple coreds and then the speed it will'll get will be multiplicative so every core we can run have a data parallel algorithm and across all those cores。

 they're all running at the same time。So let's say that I'm on a machine that has 32 cores。

 assuming I can scale out perfectly literally and I can divide my task up into 32 discrete tasks so that's a 32x speed up and then if I can have a portion of that computation。

😊，Knowing how we get tuples in and out for now， that can run on using Cdi and it can do process 4 twos at a time。

 So then it's 32 x times 4 x。 So in theory， for the scenario here。

 we could get up to 1208 x improvement in performance。And that's just on a single note。

 And that's pretty significant。 right， Anything that's you know。

 at least an order of magnitude is is a huge win。 Two orders magnitude is be unheard of。Now。

 we're never going to come close to this because as I was saying。

 there's a bunch of stuff we have to do to get things in and out the registers。

 in and out between operators， copying things from disks and things over the network like this。

 we're never even come close。And in some best cases， a scenario。

 when we look at some vectorized algorithms。We might get 1。4 x speed up if we're lucky。Right。

That doest mean we shouldn't be doing this。 All right， so we covered this。

 I think early in the semester we did I did a quick preview of what Cdy actually is。

 So I don't want to spend too much time in it。 again。

 the idea goes back to this this notion of this classification of what these instructions are actually going be goes back to the 1960s。

 There was this thing called Flynn's Taxonomy where he described what Si instructions are Cdy。

 And I think MImdy as well。 And I think at the time they were all theoretical。

 you you could have these things in the 60s。 But obviously now in the 2020s。

 these things have been around for for quite a while。

 So we can exploit them we use them inside of our database systems。😊。

So SMDA is going to be a class of CPU instructions so it's can allow again a processor to multiple do the same operation on multiple pieces of data at the same time and the way this is going to work is that we're going to rely on these special CMID registers as a way to get things into these instructions and out of these instructions。

And the overall goal as we go through is that we want to keep things out in the C registers for as long as possible。

 do as much processing as we can。And a paper you guys read talked about because AVX 512。

 we can achieve this now better than we used to if you want to keep things out in the CM register as long as possible and only bring it out back to the CPU cache or memory when we're done with whatever it is what we're going to do。

So we're going to focus most of this lecture on ADX 512。

 but this is showing here that every other ISA has their own variance of them。

 and the case of Intel goes back to the 1990s and they first put out these NMX stuff，Ar and breast。

He is that pretty still thing。Question， is power PC still a thing？😊，I mean。

 when do you need still a thing like does it exist， Yes。

 or people paying a lot of money what's the marketker sharere or power PC for databases， I mean。

 pretty small。But there's enough， there's enough legacy software that's running on some really old。

 you know， systems running that need to run the power PC， right？ I mean。

 I Mss is still like the number one， I think。I think I' this is still true。

 I saw some reports saying IBM makes most of its money from I M S more than any other piece of software。

 And they invented that for the Apollo Moon mission in the 60s。

 because there's all these banks that are still running all this stuff。 right Again。

 it's mission critical， you don't want to mess around like， yeah。

 I let me just switch to something else， because it's be major engineering effort。 And if it fails。

 then your business is screwed right。😊，P BC has some other advantages over。

Over X 86 for a variety of things， but I mean。Yeah， if you were look at a brand new starter today。

 would you use Power PC now？I I， I mean， I， you can't get it from， from any of the cloud vendors。

 right， so。Okay。嗯。Right， yes， I mean， so again， this is just saying that these。There's other。

There's other sort of categories， and remember the categories or releases of sending instructions for different platforms。

 ISs， not just the AVX stuff。 But again， we're going focus on this because this is when they Intel put this out。

 they added some additional things that make it better for database systems in a way that we didn't have before where we had to sort of emulate stuff ourselves。

So this is the example that I showed before， we once want to do a simple operation。

 take two matrices x plus y， add them together produces the new matrix Z。So again。

 if you want to write this with scalar code or using6 instructions。

 you just have a for loop that iterates over every element of X and I and then write out to Z。

 So your' literally is scaling or going through each element of the two arrays， one by one。

 running one instruction added together and then one store instruction to put it out into the output buffer the Z。

Right and， you know， compiler can be smart about this。 It can unroll it right to， to。

 to speed things up。 But for now， at the end of the day。

 it's still gonna better execute a single instruction to add two numbers together and to write it out to another register or another write out the memory。

So as simply， what we can do is we can take a a vector of。

 of values assuming here we're doing 32 bit numbers，4 elements。 So it's 120 bit bit register。

 can A V X 5，12 is' gonna be 512 bit registers。 so we can put more things in there。

So now it's going to be one CM instruction to add up the offsets。

 the matching offsets across the two registers and produce a single output。

And then do the same thing for the other one， added together produce the output。

 So what took before8 instructions。 So do 8 additional instructionss。 Now we can do it down to2。

Right。This is why this is going be important， obviously for databases where if we're trying to written through columns and columns of billions of tuples。

 we want to be able to take advantage of this。So there's two type of vectorization we can have in our system in our data system the first is what I just showed or the first would be what is called a horizontal vectorization where the idea is that you're going to have some instruction that's going to take all the elements within a C register and then produce a single scalar output like if I want to get the summation of all the elements within for lane register here。

 there's some instruction that can do that and then produces some scalar output there。呃。

Early CPUs don't support this。 it's mostly found in the newer CPUs that can do on the X86 that can do AVx 2。

 which is the precursor AVx 512。 But this is not gonna be that entirely useful for the self we want do in databases。

 The one we care about is vertical vectorization where the idea again。

 is that we have two registers and they're lined up across lanes。

 assuming the values are all fixed length of the same size and we execute one instruction to do some operation on the combination of the two and then produce produce a new producing new output。

So this is way more common。 This is， this is， this is the technique we're mostly gonna be using in。

 in our database going forward。 But again， you could do this as well。Actually， yeah。

 I think the top one here， I think this shows think of like summation。

 if I want to add up all some of the values in a column。

 you could use horizontal vectorization for that。So this is a table just showing you that， yes。😡。

AcI know very。Is it like using real system？It question， is it using resistance， I think so yes？Yeah。

I think we have an example ofhouse， I think Clhouse is doing this for someation。

rightSo this is is a table showing the history of the different sd extensions that Intels put out over the years and again the one we care about here is the bottom that came out in 2017 AVx 512。

 so the registers are going to be 512 bits it's going to support integers。

 single precision and double precision floating numbers and then the big one iss going to be that you read in the papers that they're going support these permutations or predicate masks that allow us to keep track of or specify which lane should an operation actually apply on and prior to that this coming on AVx 512。

 this is something of the data system we have to do themselves by basically using a separate register to store a bit mask like that。

 whereas now in the case of AVX 512 there's explicit registers to do those things。

So this link here will take you to a great presentation by James Vandeers。 He was an Intel fellow。

s from I 2017 or so， but he gives a good history of all these things and why this matters and what some of the cool things in EVX 512。

 So if you're interested this kind of stuff， you can go check it out。😊，All right so as I said。

 Aix 512 is the one that we care about it's not to say that people weren't doing vectorization in database before this。

 it just makes everything a lot easier And so in addition to having the new instructions to new data conversions and scatter operations。

 which is we'll cover in a second that permutations is the big one to be able to say here's some bit mask that says。

 I want certain operations the operation I'm going to apply to only occur at these different lanes。😊。

Right。And so the downside though， is that unlike in AVX 2 in SSE 234。

 like in these earlier extensions to X86 or Cindi， they were all all or nothing。

 meaning like if I said my CPU supported AVX2， I got all the capabilities and instructions that I would expect to have in AVX2 for whatever reason it's an Intel thing that when AVx 512 came out。

 they broke it up into groups。 So now when you buy a processor。

 you have to go check like the CPU flags to see what instructions you actually support。

And we'll see an example again from Clickhouse， well they'll have if blocks in their code that says。

 am I compiling to ABx 512 or this group or that group versus that group because they' to have different instructions and different capabilities。

So to give you an idea sort of how confusing it is， like this is from Wikipedia。

 this is just showing all the different groups you could have for AviX5 12。

 and then which iterations of the ISA going back to the Xon Phi actually supports these。

 and so you can see not everyone has everything。😊，There's another chart here from。

 I think one of the papers， again that is showing you how these things have been sort added over time。

 but then now within well here's it all stuff in EX 512， but。

There's newer versions that don't have things in the early versions。

 So even though you say you sort8x 512， the system has to go check what actually it has。Again。

 we'll look at a clickhouse I in a second。 They have if clauses in their source code that figures out what CPU capabilities are available。

So， again。The other issues8 X 512 in a second where but I don't wantna spoil it just yeah。

 So even though I'm gonna spend most of time， hey， great， you could do this。 A X 5，12。

 the back of your mind realize， like may not always be able to do this。 In some cases。

 you actually may run slower if you， if you use A X 5，12。 Well Ill explain why in a second。😊。

Al right， so how do we actually want to get。How do you want to actually use this， right？

 there's basic three approaches。 Do I want the compiler to figure out what what it can vectorize。

 Do I want to get hints of the compile that say how to vectorize things or do I want to do the vectorization myself。

And so the way to think about these three approaches that the top one is be the easiest to use because you don't really have to think about in some ways。

 Sometimes you do sometimes you don't， and just hope the compiler can figure out how to compile things and vectorize your algorithm。

And if you design your database system in such a way that you break things up into small enough chunks that are looping over over arrays。

 then the compiler could potentially be able to figure it out， but not always。

Compilr hands says' giving a little nudge to the compiler say， hey， look， you really can back。

 I think you should and hope it tries to figure it out。

 And then the last one is like you write the actual instructions in your code to actually invoke the exact opera C instructions you want。

So let's go through these one by one。So they said automatic vectorization。

 the idea is that the compiler can potentially identify when certain instructions inside of a tight loop could be rewritten as vectorized instructions And so my example I showed in the very beginning that iterating over an array。

 two arrays and adding them together， that's something obviously that the compiler should be able to figure out。

So this is only going to work for simple loops。😊，And in some cases， in the A systems。

 it doesn't always pan out。 This has gotten better then the GCC and Kang and suddenly ICC have gotten a lot better where you can start figuring these things out without hints。

 but maybe five years ago this was an issue And obviously if you don't have Cdy instructions on your CPU that you're compiling on the compiler is not going try to use it。

 So say you compile on your laptop that doesn't have Avix512 you take that binary and p it up on your enterprise grade Zion server even though the Zon server is gonna have 512 it was compiled without it at the time。

 you could compile on your laptop So you got to be mindful of where you're actually compiling and running things。

So this is our template that we had before。Where now were going to pass in pointers to array x。

 Y and z， and we're going to loop over them by some max value and at to get， right？

Can we allowed to vectorize this？She's taking her head yes。Baise hand， if you think yes。Re say no。

Why now？Well， he says need to restrict， but what does that mean， why， why？Yes。

 so he said if the point is ever Latin， then then there's dependency。 So again， think pile time。

 do I know what the pointers of x， Y and z are pointing to。No， right it's a runtime thing。

 So in this case here， the compile is going say， hey。

 X Y Z could actually be pointing to the same thing。

 So I can't vectorize this because let's say that Z is just know one byte more than than the memory address of X。

 So now if I'm ripping through my my code at runtime。

 in the scalar version for one iteration of x or run iteration of the loop。

 I'll overwrite what the next value actually should be And so now the next iteration。

 I'll get a different computation。 but if I vectorize that with Cdy。

 then when I do the computation of the second iteration。

 it won't see the effects of the first iteration。 So it actually produce a different result。

 So the compile is be very， very careful to make sure that if it vectorizes your code。

 it doesn't produce something that generates a different value or different computation then it would have if it a scalar code。

😊，Yes。Comp。Ja。Can't the compiler do loop unrolling， then auto vectorize that？😡，But again。

 you don't know what Z is actually pointing to potentially， right。So it's going be very conservative。

 doesn't want to avoid want to avoid any kind of problems。 So in this case here， it's gonna say I。

 I don't know what x Y and z actually point to。 So I can't vectorize this。So here' sort question。

For us， we actually can't。Well same is for us， you can't do that， yes， we'll get that in a second。

Okay。We're in C+ Law Sea land， okay。All right， so。啊。Right， so， so the， the。The he said Patrick said。

 oh， you could use the sh key word。 And that's an example of a compiler hint。

 So that's it's we as the programmer can tell the compiler something about our code to make it more likely to try to auto vectorize something。

 And so the the key word to see in a second。 That's an example of giving explicit information about memory locations to say these things can't overlap。

 They're not gonna change while this loop is running。 Therefore， you can auto vectorize it。

They a more brute force approach。 You just tell the compiler， hey。

 turn off any checks for dependencies or alienliasing here right， and just vectorize it trust me。

 like you know， driving me without the seatbel， right。So going back to a function before， as he said。

 if you add the restrict keyword， which is in C99， but it's not in the C+ standard。

 but pretty much every C+ compiler supports it。Right， you add this keyword。

 And that's telling you that these arrays are gonna be distinct locations that were the it's for the lifetime of the pointer。

 they're not going to change， at least within this function。 So therefore， it。

 it knows that it's safe to actually vectorize this。

So this approach is widely used like so if you go looking like an inductDB。

 you just search for restrict and then C+ plus it underscore restrict So you see all these functions are set up to do this kind of stuff。

 right。

![](img/a55ba0e98df074bca24360ded1a60926_5.png)

Am。And the goal here is that theduct to B wants the compiler figured out how to auto vectorize this。

 So it's passing that hint hint to it。A point also to here。 You can see sort of two versions of the。

 of doing this check here。 right， There's the is。Is all the the bit maskask I'm getting is everything。

 if everything is not valid， then I have to check my bit mask to see whether it's valid。

 If I know everything is valid， then I can skip that extra check right。

 So that's we saw that sort of technique with。We're checking for nullles with， with vox， right。

 So even though there's a conditional here， know， it's worth it not to do that additional check on。

 on rows。

![](img/a55ba0e98df074bca24360ded1a60926_7.png)

This is a clickhouse。 Clickhouse does the same thing up above。

 So this is to do an aggregate sum computation， which I think would be horizontal vectorization。

 But again， you see this underscore underscore restrict on the pointer。😊。

But then they had this other beast in here， which is they're actually checking again what A V X 5。

12 group the CPU actually has， Then it has different implementation to， to do that computation。 Yes。

 you should if。This question is you should be doing if death this， these are all like macros too。

 yeah。Oh， they're all macros。 Yeah， these are all like crazy macros that get。

You auto generateded the code。I don't about， I think that's probably also a pound deaf。Because well。

 if de， I'd be concerned is our。And it's， I think it's a NftA。Manding up above。

 you have use multit CPU code。It can could still ifll just the compiler will get rid of it。Yeah。

 it would be dead code， yes。Yeah。But， the pun， this is a good example of like， hey， here's you know。

 there's two versions of A V X 5，12。 There's A V X 2， There's SSC 4， which is the precursor A V X 2。

 right， So the main thing I care about is here。 Like it's A X 52。 Oh no， no。

 not really you to check what group you actually have。Right。



![](img/a55ba0e98df074bca24360ded1a60926_9.png)

All right， so restricted probably the most common one an alternative is use these pragmas， IV depth。

 which is basically ignore vector dependencies， vectorization dependencies， openmp。

 the big parallelization framework library， they have like pragma Cd like there's different versions of this this basically says ignore any of your alying checks when you do an auto vectorize this and you would end up the same thing。

 And again， this is up to the data programmer to make sure that this is done correctly because the compiler would do whatever you will likely do whatever you want it to do。

The last alternative is do explicit vectorization。 And for this one。

 we we're to rely on what called intrinsics or CPU intrinsics。

 And you think of it intrinsic as like a like， I want to say virtual function。

 but it's like a fake function in the in your C plus code。 It looks like a function。

 but it has an underscore or double underscore in front of it。

 And it really is translating into the exact Cd instruction that you want the compiler to to omit for that that line of code。

😊，And that's how you call explicitly the SI operation that you want or put things into registers and what registers you want to touch and so forth。

Now the problem with this is that， you know， if you want exact control of your database system。

 this is what you you need to use this。 and talking to friends in industry。

 this is what BigQury does。 This is what this is what Redshift does in some other systems。

 And in that environment because they're hosted database systems， they control the hardware。

 they know what Vms are're running on in the cloud。 So they can they can make that choice。 know。

 they're not trying to run a power PC， for example， But obviously， if you use like an X 86 intrinsic。

 you can't run on arm or some other CPU。Now there are some libraries that can hide some of these Cds in Triss and have ways to step down to to the smaller retro size as's needed based on grouping or extensions you support Google Highway is probably the most common one。

 I don't know of any data system that uses this。 I guess we could just the source code open source ones that figured out lead SD is another one that's why again。

 not sure outside this is Rus has its own SD library。

 but I think it's only turned on for experimental nightly。

 I've never used it the one student that was here before she he says you just use lets alter vectorization handle everything。

 And as you said， because the compiler is in better shape to understand whether are things will collide。

😊，Because there's more explicit control over memory locations。

So if you were the using transsects without one of these libraries。

 it would essentially look like this you had these underscore underscore and then some prefix of what sort of group of Sim exceptions you're using。

 then you say what size the register you want in I means you're storing integer。

 So all we're doing here is casting the integer vectors we were given putting them into the SI registers and then now we can do our loop and do Cdy addition and then store it in and the output vector we want。

 And now you can see here our loop we' we're doing four editions at the same time。

 So we need divide the number of iterations we would have divided by four。😊，Right。

So this is roughly what it looks like。All right， so which one do you think is the best？Explicit。

That's control。For this specific。Like can maybe that， What is the best for performance。

Explsite was the easiest to write。Yes， I said before。 So let's see。

Let's see' see what the performance you get from like explicitly writing vectorized code。

 So this is a paper we did with the Germans a few years ago where we compared against the vector the vectorized approach for doing query processing and then the hyper approach。

 which will cover next class and the student in Germany wrote sort of one system that supported both these techniques and do the bake between the two of them。

 The idea is to strip out all the extra stuff that that differentiates between vectorwise or hyper or other systems get it down to a common substrate to the extent that you can for these two approaches。

 And then that way you have a pure apple apples compare some between the different approaches because there's other things that would come up like the way hyper does numerics would be different than vector wise and for some queries and TPCH that would make actually a big difference。

😊，So it was a single test bed system that did both vectorwise and hyper， which cover next class。

 And we just wanted to measure how well a compiler can can auto vectorize a bunch of the vector Y primitives。

😊，So again， think of like a primitive being a single function that takes an array or a vector of tus of a certain type and runs like。

 know， there's something less than something or something greater than something like how well could it vectorize those sort of small loops of code。

 similar of what I showed before。And so we compared against we used Kang GCC and ICC。

 which is Intel's compiler。 ICC， it's not free。 It's not the source。

 but this is obviously way better at auto vector vectorizing at least a few years ago than than GCC and Kang' Gcc and Kang I've gotten better。

 But at the time， ICC was was much much better。 And again， you pay for that because Intel。

 Intel chose the hardware。 They obviously can write really good compilers to it as well。😊。

So we're going to basically do comparison between hashing a selection and a projection。

 And some other operations that you had to run for the full query。 didnt。

 we didn't vectorize because you can't。All right， so this is running across some select number queries of TPCH and the first bar here is complete auto vectorization。

 let the compiler do everything， the black bar would be just if you do it by hand and then the red bar would be the combination of let the compiler auto vectorize everything。

 then we would go check and see which function didn't get auto vectorized and we go back and do that and manually here。

😊，And what we're measuring here is the reduction of the number of instructions versus like a scalar approach when you don't do any vectorization。

 you don't let the compiler do any vectorsization。Right。So。You know。

 the main takeaway here is that the， higher， in this case， higher is better。

 But there are some cases where the， the。You know， the manual one。For whatever reason。

 like because it just was so complicated actually right。

 we always didn't get a huge improvement in the reduction of number instructions。

 But the combination of letting what the compiler does and then going back as a human and cleaning things up。

啊。was actually the best approach for all of these。Right， that's not actually feasible， right。

 Like you don't know the。So unless we're just specifically optimizing D。So the statement is。

It seems it is like， can you， would this not work in a real system because you don't want thequeries ahead of time。

 Again， we， we're， we're， we're trying to vectorize the primitives。Right。

 and they're not specific to any one query。 Like take a column of integers。

 check to see whether the number is less than than a single value。

 That's what we were auto vectorizing。 And it wasn't hardcoded exactly for， you know， Q1。

 Q6 and so forth， right。So technically， it was still a general pressure system。

 We're just trying to auto vectorize like the actual low level operations are premincent within them。

 yes。Cue6 was worse。Yeah， I forget why that was the case。Again， it's the。Yeah， I， I。

 I think would read the paper。 I， I forget why that was case。Yes。Why is what why， why is Q sick。わ。

Why is Q6 before4 Q3？😀Hper。I had to go look。ReRead the paper why I have to go check。

 It doesn't matter。Yeah。It might be a table。 Maybe， maybe this is really Q3 and this  Q 6。

 but it doesn't matter。 you should Yeah， the main main way of this is that you should do both， yes。

So the audio photo in manualuel， was it more that？You took away some of the manual instructions or you add change it It question is what is auto plus manual so you auto vectorize everything then you actually look at what was actually generated in the assembly。

 figure out what functions for prims were not auto generated auto vectorized。

 then you go back and rewrite them the actual C++ code to put in the intrinsics。

Saying Manuel was not done right。I mean， they're Germans。 So like I I'm assuming he's done right。

 And maybe， again， I have to go look at what exactly this query was。 I think the idea was that the。

Yeah， of course， like。2。In theory， you could also look to see what this thing vectorized to， right。

 and then rightly equivalent intrinsics for that。 But I don't think he did that。

 I think the idea was like， okay， if， if， if， if you bring in a German who like。

 who knows what they're doing， how well can they do implementing themselves。

It might even be that like the overhead of moving。I'm back to register actually。嗯。たデ。Again。

 everyone don't。We can go little the results again。 we can go into more detail in this class。

 The reason why I didn have you guys read this paper is because it's compilation plus vectorization at the same time in one single evaluation。

 So I chair to picked this result out because they just focused on vectorization So I wanted to cover compilation first。

 and then we can talk a little bit as well。 So I can follow up figure out what's actually going on here。

 Everything's open in source online as well So we could check it out what happened。😊，All right。

But now we can check to see what the performance difference actually is。 And so in this case here。

 we're measuring and what's the reduction of time of the system。

 running these queries between the different implementations。

 So it's all relative to the scalar function， scalar implementation。 So if you're above zero。

 it's faster， if you're below zero， it's worse。 And so you can see in some cases here。

 especially for Q6， even though that one code he wrote by hand had more instructions it was actually faster than the one that was the combination of auto vectorization and manual。

Or in the case of here， in case of Q3 going back， right， they reduced the number instructions。

 but it was done in such a way that it was actually slower。 Na is always the best C。

But the point I'm trying to make to write that is heart。So the if you have。

 if you have the capabilities to do it， like if you have a German in house or you can just spend the time doing it。

 the red one's probably what you want。 I forget what percentage of he actually had to go touch up。

Right，But if you spend the time and effort， you can get。

ItBecause it' almost equivalent than writing assembly。And that'll be any compiler。Just。

So manual manual are compiler hints and intrinsic or just like level one。

 essentially the first part manual is literally manual is the last one。

 explicit vectorization called intrinsics。 This is compiler hints。😊，And this is compiler hints。

 And then what doesn't get vectorized， you go and put insics。Yes， I will buffer about Q9 and Q18。

 I you compiled try to it and still somehow perform worse Yes， we'll cover with this one in a second。

 yes。I guess a hint。 you even know why。To。Now。All rightWe'll get to the end。

There's a footnote in the paper you guys read that explains it。We'll get to the end。

Let to make sure It anything on this。Like dashO2 instead of dash。Sa is。

 is it same reason why most compilers do dash or 3 instead of O2。 it2 no。

Because the new version is download。B go， that's it。 So he said。

 it's because the new versions down clock or downcycled the CPU。 So when you call A V X 512。

 they turn down the clock speed。Right，And some compilers were actually not。

I want to vectorize AVx 512， but I always use AVx2 because of this exact reason。

Becauseuse the heating issues， yes。I was asked why they It'， It's heating issues。 my understanding。

 yes。You know， in the early versions of Cdy， like in the 90s M and X stuff。

 there was literally like like you would call scale instructions。

 but when you call it C instructions， it would stop all the SD instructions， Sw over to Sdi mode。

 run that， then switch back Now as superscaleal architecture， we can run these things in parallel。

 But as I said， like I don't know whethers all all AB X 512 instructions。But at least enough of them。

 like， it'll get down clocked。I don't know whether these are。I think all， I think X86 is are the。

The current crop is Intel CPU has all had this issue。And so Intel will cover this at the end。

Intel actually turns off AVX file， they fuse it off on consumer grade CPUs。

Becauseuse they don't want people to get downsy on think the CPU is running slower than it should。

 Yes， do other CPU vendors。Does the one other CPU vendor for X86 that be relevant？Also。

His question is does AMD also do this？I don't think AM D has A X5 12。 They do。 The new ones， okay。

I don't know what they downc。Do you know the reason behind he。Yeah。because you're doing Cindy。

 like doing a lot of stuff you have to talk。あわせく。He says he uses the scientific term。

 is it because they're doing a lot of stuff。Yes， yes， yes。I， this。

 this is not a class about like Intel's design decisions。 like I dont， Ca I don't know the answer。

 I'm only telling you what you can read。 Sorry， yes。D clocking doesn't。I had to double check。

 They might be using A V X 2。 I don't， I't know。 I we， we can cover this in ala。 Okay， again。

 this is not like let's bash on Intel。But again， this is what I said in the beginning。

 just because it's there doesn't mean it's always going to work。And in some cases。

 A V X 2 is gonna be better because they won't have that that down clocking downcycl issue。Alright。

 so now let's go through the primitives that we're gonna use as building blocks that allows to do you can construct and put together。

 So they're doing more complex functionality to actually start running running queries。

 And this would be a combination of what was in the paper you guys read and then some earlier paper that I'll I'll cover a little bit as well of like。

😊，And these are the basic primitives that CinDs can provide for us that we can then put together to start doing the larger database operations or algorithms that we need。

So the big one I said is that AX512 added ignoring the down clocking issue is that they have now all the instructions have these predication variants where you can pass in a bit maskask that says which lane you want to be applied the operation should be applied at again。

 prior to AX 512 you could do this， but you you would have to use as separate。

 use one of the Indian registers that are available to you to actually then apply it。

 So now there's specialized ones are just for the bit maskasks。The number registers。

 I think in the La version is like 32， right， So we're not talking thousands and thousands of registers。

 A X 512 going to 32 is a lot。 I think it used to be。Low20s， So there's more available to us。

 but it's still still not infinite。So the idea is that say I have two vectors here。

 I want to do some operational one。 and if you think of these again。

 the offset have sort of line up across the lanes。 And so say I have this bit mask here set of one。

 So that's going to say whatever my output to be for whether my instructions is gonna be only apply it for the lanes where this thing is actually set to one。

😊，So to say I'm just doing addition， then the output would just be 3 plus 2 and 3 plus2 to produce the output5 here。

 and then for the ones wherere at0， you pass in this merge source register and then that just is being used to fill in where the zeros are to put value there。

RightSo you can put any value in， there's also the variant of zero masking where you don't have to pass this explosive register。

 just puts the zeros where everything is。 right So that's the basic idea。 So with this bit mask。

 which to get in， we say we can generate because in some cases in our our algorithms。

 when we apply filters like the ones in zero is corresponding to what tus of what else set actually satisfy the predicate。

 So thats that's sort of the basic construct we can carry along in our in our operations to determine whether a tu is even valid or not。

All right， so the first thing we want to do is permute and the ID here is that we want to copy values from an input vector specified to some offset to some other destination vector and again。

 in the prop Ax 512， the way you had to do this is take things out of the vectors。

 put it into memory， and then put it back in the vectors into the right order but now again with AVX 512。

 we can do all of this within register directly register and that's way faster and we don't pollute the CPU caches or slow things down。

RightSo the idea here is that here's our input vector here's the index vector that's going to correspond to where we're going to write things to。

 So in this case here for this first value sorry first index value。

 if we're going to this position here， we want the value within the input vector at offset 3 which is D so that gets written here and so it's done this all down the line。

 I don't know why the errors is in line up but if it does this all the way down the line and then。

Populates that。 And that's， again， that's all done。 And is a single instruction。

Even though I'm showing it in different steps on PowerPoint。The next one we have is a selective load。

 And the idea here is we want to take some contents that we have in memory。

 and we want to be able to write them out to， to some input vector。😊，Yeah， wow。

 I don't know why these aren't lining up， That's weird。Whatever， right。so again， we have a mask。

 And so what's going to happen is in this first position here， which's just going skip。

 So it doesn't overwrite whatever's in the vector right now。 So then it's all where the ones are。

 And it's gonna grab the first location that it has because you give it this offset the starting location of the input memory vector input memory buffer or address。

 And so every time he sees it one。 it's going to increment over by one and then write that value up。

 So in this case here， we're going to write you to the second slot。

 We're going to skip skip this one here。 leave that alone and then go the next one we write V to that slot。

😊，Again， all happens within a single structure。Select the stores going the other opposite direction in reverse the top is our target。

 so we want to write out into memory。 So the same thing going across， we skip the0。

 the one gets written to the first position， and then the skip the that zero。

 and then that one's written to the second position。And then we're done。

So this is how we're going to get things in the registers and then out of the registers， but again。

 more than just like blind copies， we can be clever about how we write things。

So then we can use compressed to move things across the different vectors in different ways。

So in this case here we have our target vector is the value vector to the top。

 we have input vector and then this index vector。 So the idea here is that for the the first forever there's a one。

 we're going to write out something up there right So same thing here we write the D to that first position and then everything else is just left as zeros。

😊，So basically compressing down whatever woulds in our input vector to fill in the things in beginning to the end until we'd run out of space or we have number items to put into it。

Expand is the reverse， So we have the one here。 So the the first one will get， sorry。

 the first value within our input vector will get written to that position。

 Sam thing with the next one over there。 and then the rest of all to  zeros。

 So that's taking what was compressed on this side。

 potentially by this operation and then expanding it out back to to its traditional form。So again。

 they're just reverses of each other。so then we can do select a scatter and gather and the idea here is like how do we actually get things specific things we want out of out of our memory into registers or registers back into memory。

 So in this case here， I want to take whatever is this offset specify but index vector。

 jump to my offset memory and then write that out to the first position。

So two would be this position here， and that's written the first position and then so forth for all the other ones there。

So now we basically you're changing the order of how things are written out to memory but lining them up the way you want them inside the vector。

Again， the sector of scatter is the reverse。 Okay， were taking a value vector and then specifying what memory location we want to write things into。

 So again， so in this case here， the index vector wants to write to 2。

 we take the first position at this lane is a and it write to memory position 2。😊，Right。

So I don't know whether they。I don't know whether they， they require the。

 the memory location you're writing to to， to fit within a single cache line。

 There's alignment issues。 I think the hardware takes care of all that， all that for you。

 right because this index vector， this can't be you know， a million elements。

 You're not gonna be writing out to all different locations of memory。

 This thing roughly has to fit into， single cache line。Because L1， you can do。

 I think one or two loads in stores per cycle。So you obviously don't want to spend a lot of cycles just filling out taking things out of the vector and putting putting them in。

So again， these are the basic constructs。 I'm going through them quickly just to say like， okay。

 there's ways to pass in these bitmaasks or these index vectorers to specify where you want things to go to and where you want things to come from when you move things in and out of the vectors and into memory。

So that's about how we actually want to put this in Saturday data system。

So I'm going to go through some basic operations that we can use or built using Sbiium vectorization and in most cases。

 we're almost always going to want in favor of vertical vectorization we're going to have different tuples within the different lanes of our C register so that we can process them the parallel So again。

 horizontal vectorization would be either like I'm trying to sum up all the values within a vector or say I'm trying to string comparison of our long long string and that's breaking up into across different lanes we're going to ignore all of that。

And our goal here is that we want to maximize lane utilization。

 meaning we don't want to have our computations that we're doing。You know。

 in ours instructions to operate on things we know have been eed no have been removed before。

 Like if something does not evaluate to true， you know doesn't make sense to do a bunch more expensive computations for it。

 we want to ideally be able to fill it in with something else that's useful。

 And the paper you read talked about that。 And we'll see other ways to do it as well。

All rightSo we'll first talk about the basic selection scan。

 then we' talk about new vector refill and then I'll talk about two variants of doing hash tables or joins and then this is not the paper you guys read。

 but for part histograms， this one is like really simple idea that I think is pretty clever and again it comes from this paper in Columbia。

😊，So this paper here， this is from 2015， this is from some researchers at Columbia。

I I used to have the students you guys read this， but I don't have it read don't it anymore。

 I read the German one because in this one， they make a bunch of assumptions that aren't real because it was 2015。

 it was for8x512， So they assumed all your values were 32 Bs and that your pointers are always 32 Bs but obviously in the real real workloads。

 the real data says that's not always true。 And then they also assumed that everything' is gonna to fit in L3 cache which obviously does not always always pay out to be true right。

Alright， so let's go back to have new basic scan operation。 So this is the code that I showed before。

 How to do a branch of scan where。We're always going to copy our output into any tu we're given to the output buffer。

 but then we run this check here and if this evaluates to01 after we analyzed them them together。

 that determines whether we move our offset up by one。Right， so there's no if clauses in Cdi。So we。

 we can't run the the version， ifN else version of this code， right。

 we basically always have to run this one。So the way to vectorize it is pretty easy because now instead of getting a single tuple。

 now I'm getting a vector tus， I load the key I want to evaluate on into some Sd vector or SD register。

 not specifying what size doesn't matter。 Then I can run bitwise operations to do the comparison。

 Sorry， I can run the comparison operations on the key that produce bit masks that I can then and together。

 and that's going to determine whether a tuple has been satisfied this predict or not。😊，And。

 I'm not showing you the then the code to make sure we remove things when we come back around the second iteration。

 we can ignore that for now， right。So， again， this is me walking through what I just said。

 skip all this。 So instead of using， again， placeholders like low and high。

 let's actually use real values and some and some real data here。 right， So again。

 think of this as that there's8 tuples here。 And then the key is some single character。

 It could be a dictionary code。 It doesn't matter。 right。

 So it's not a string going across each element。 Each tu is has a single string single character string value。

😊，So to do this in Cindy。Is that you would first do that SMD compare And that's the first step here。

 is something is the value within a given key greater than or equal to a low value。

 And that's a single SMD compare instruction that then can produce a bit mask。

Then I got to run the second half of the comparison and produce another bit mask where the key is less than less than a to。

 less than equal to the high value， the letter U。And that produces another bit mask。

So I have two now bitmasks sitting in CP registers。

And I can then run a Sdy in operation and instruction to just compare those two bit masks。

 It produces a new bit mask。 And that tells me， here's all the people thats actually qualify or satisfied the predicate。

😊，And then if I want to return it back to which offsets in my input vector or actually were set to true。

 I can then pass in a sequence 0 to 7。And any bit that's set to one。

 I just do a CD compress operation to then produce a single CD register that has these values here。

Right。So there's other tricks you can do。 Obviously， there's like。

 if I can run a rank instruction to determine how many ones I actually have in these bitmask。

 if they're all set to 0， then I can bail out and not do the other steps。 Yes， it all offset。

 That's not a。Or is it just like an， all offset Yes， his question。 what。

 what is it's just a register。 Yeah， and there might be。

 I think send instructions that that that can convert this automatically now。

 butm just visually showing it。Right。So again， like。

How do you actually implement this in a real system， Well， again。

 if you take the vectorized approach， which again we'll cover more in the next class。

 you would have explicit function that says。You string。

An input input column of8 elements or some number elements of a certain type run the greater than or equal to comparison operator for a given constant。

 So you， you invoke that function。With the pointer to the column and the constant value。

 and then it just loops through that and compare someone by one。

So then the compiler can then auto vectorize that to do the S instruction to put the data that you're trying to compare against into a CIbi register。

 run the CI compare it and take the output。Yes， the selective store。

 take a bit mask and simply store it in。Why do we have to the compress？His question is。

 doesn't the selected store take a bit max and store it into memory where you want it？嗯。

I'm just showing you how how to how to this， convert this into a position list。あ。Actually。

 he brought up a question earlier。Um。这点。Like how could I generate all the primitiveence for all possible variations of wear clauses？

And this is a good example where maybe auto vectorization isn't going to be as hacky。😊，Sorry。

 exactly what we want because。Again， this thing， the primitive that's going to do this evaluation。

 if it produces this mesh offset， what I really want is the bit mask。

So I could then take the two outputs and run this CbiA myself。

There are going to be variations of the primitives where sometimes you want to just produce this match offset list immediately。

And other times， you actually wanted the bit bit mask out because then feed that into some other operation that take two bit masks and can run them together。

So how to auto vectorize all of this is actually not trivial。Again。

 it has to take a few minutes to come and figure out how to compose these operations together based on what。

 you know， the additional things you need to do in the query。Again。

 we'll cover more of that next class。So we can now go back to that paper we said before from the Germans。

 plus me。I'm Peter Bos， he's Dutch。 but the the the vector wise guy。

 But now we can actually run his version of the， vector wise。

And hes gonna be use A X 512 for everything because this was。

 it's easier to to use the bitm registers to do vertical vectorization。

 So I'm gonna show results for both the。For for three different operations within a scan。

 so the hashing to hash something put into a hash table without putting in the hash table。

 a gather operation and then join probing it。 And then we just see how much the SI stuff helps for over a scalar instructions。

 So I again to strip out the rest of the system to say for actually the core algorithm are doing the scan operations and other things in a query plan。

 how much does C help。And so what you see is that across hashing gathering join， if you vectorize it。

 you get a bigger win for hashing and a bigger win than join over the scale of value right。

 So up to 2。3 x improvement of performance。😊，But again。

 that's just doing the bare minimum you need within that scan operation。

 just doing the hashing or doing the joint probe， right。

When you bring it to the rest of the system and now start worrying about getting data in and out of the registers and materializing results going from one operator to the next。

Then you see the performance difference is not that significant anymore。

So you put it in a full query。The difference between the scalar operations and the vectorized one is actually not that much。

this is the best case scenario of like。T0 written code。 its everything's in memory。

 I forget whether it's what scale factor 1。 Yeah， it's gonna fit in CPU cache It's not that big。

 or most is gonna fit CPU cache。So what is， right？But again， it'。

 what's going on is that it's not just a matter of like， okay， we， it's Amd's law。

 What portion of the query is actually gonna to be the part that could be vectorizing and get the biggest win。

 It's not all of it。 It's， not a sizeable chunk。So you're only going get maybe， you 1010% bump。For。

 for vectorizing the state that one small piece of the code。

It's all the materialization overhead is going to slow us down。 and that you can't vectorize。

So this is somewhat deflating。 Like， again， if it is said， you know。

 spending entire lecture about how great vectorization is and how great， you know。

And how much can help， but it doesn't actually make a big difference when you run a full query。

 that's true for a lot of things in databases。But these， these things are cumative。

 You obviously don't want to， you can build the greatest query optimizer。

 But if your query engine sucks， it's gonna run slow。 But if you have an amazingly fast query engine。

 but you have a bad query plan， it's gonna run slow。 So it's， you know。

 all the lectures put together is what you need to put， you know， get things to run fast。😊。

Get that order magnitude performance difference。Okay。

So one of the problems in the paper you guys read was that they， they spent， I think。

 two chapters on or two sections on was the problem of underut。

 where you have some lanes being containing tus that have been invalidated or or should be discarded。

 but because we don't want to。Always move things in out of the registers。

 you may have to continue processing dead two so to speak， but you're essentially wasting resources。

 right？So the situation would sort be like this。 So if I say have a query。

 select count start from table where age is greater than 20 and so。In my sort of pseudocode of this。

Again， I realize this this is a branching version a branch list。 But for now it's fine。

 right as I'm scanning along the table， I may have a bunch of tus here that would get invalidated。

 and I don't want to include them in my aggregation。 So if it's if it's if it's scalar code。

 no big deal because I've just loop back around and go get the next next batch。

 but it's vectorized code， I may have 8，4 to 8，12 tuples in my vector and some of them might not satisfy this predicate。

 but now they're gonna be strung along in my。😊，In my sorry my vectors。

So you sort to think of like this。Peace right here is the sort of the first pipeline。

 And then the second pipeline is this piece here。 So we're going to avoid having to pass along dead tuos in this。

 right。And so the， the idea that I'm about to show you is basically。Instead of having the。

 the materialization， you， point B at the， at the。If had a pipeline breaker。

 we actually could introduce artificial pipeline breakers。

Our synthetic pipeline breakers where we can materialize from results， go back in our loop。

 get more data and keep filling up this mini buffer， if you will， and then once that's filled up。

 we know all the tus there aren't dead or they're all useful。

 they we can proceed up to the rest of the computation in the pipeline。So this is a paper。

 I think it's citation 16 in in the paper you guys read。

 It's a paper that that we worked on here with my PJ student Prashat。

 who's now building working on the photon vectorized engine at vector Y。

 So this is the ideas that we're gonna decompose pipelines into subts that can operate on vectors of two is just with vectorized processing using CD when possible。

 But then the ideas that we can。😊，You can start storing things in buffers， fill up a semi register。

 and then move on to the next stage again so we don't have waste of computation and wasteted resources。

So the， it's called relaxed operator inussion， because the idea is like you're taking the operator fusion approach from the hypergs and actually relaxing a little bit and introducing these breakpoints。

So they think first thing is that you figure out these are the vectorization candidates。

 clearly I want to filter， I want to vectorize the filter operation and that。

 but before I maybe do the aggregation step， I want to materialize some results。

 make sure that's all gets filled up， and then I can do the aggregation computation using S and vectorize that without worrying about throwing away un results。

Right so the code basically looks like this。 So I'm scanning through as a vector tuple。

 I do my comparison if my buffer is full。😊，Then I can go， go fill， know， if this thing gets full。

 then I can go to the next stage within my pipeline and do the aggregation。 Otherwise。

 I loop back around and you know， get the next batch。

So this buffer is are incrementally getting getting full of value so that it can then fire this off again in a vectorized manner。

So this is the first part here， and then this is the second part here， right？

And then obviously they admit at the end。So one of the tricks that we figured out with this though。

 is that because you have this staging point in this really tight loop。

 you actually can start doing software prefetching。

So there's hardware prefection where the CPU going to try to figure out what pieces of memory you're going to need next and starts bringing that into your CPU cache。

 like if you're scanning along long stride of memory。

 it starts bringing in cache lines ahead of what you actually need。But in X86。

 you actually can pass hints to the CPU and say， hey。

 I'm going to need his memory region pretty soon。It's not required to actually obey your your request。

 it's like a hint。 but in some cases it actually can make a big big difference right And this stage you stop because it's its you know having instead this really long pipeline。

 So you're breaking up to these substages， it's sort of a nice natural boundary for prefeting operations。

So again， this is sort of jumping ahead to do query compilation stuff that we we talked about before。

 But this is showing that if you do holistic query compilation the same way that。That hyper does。

 which will worry about X class。 but then you also introduce these relaxed operator fusion stages。

 you can get a pretty pretty performance。 In this case here。

 software prefetching doesn't help because there's no join there wasn't really a good place to say。

 okay， let me go on prefetch and over here， this does make a big difference because this query 19 can be broken up to these substages。

😊，W I think Q has a high selectivity。Yeah。Yeah point he's correct。 Q1 is a high select。

 So like you're not discarding。 it's basically taking everything。Okay。You let me just。

 let me skip this like I wna get the hashings。 But basically， this is the old peloton system。

 So the interpreter， our interpret engine was total crap。 It was like it was garbage。

 We converted it to compilation。 So you got this， this amount of improvement。

 And thenre playing rack up diffion with Cindy plusffsion Cindy plus prefeting。 right， you get event。

 So again， this will be next week。 But going from this is not really like let me see this。😊。

I don't want get the impression like， oh， you switched a compilation。 You' can make 97 improvement。

 This is like crappy student code to like high end perant code right。

 Who's now databricks like that that I'll get you 97% of the end the day of the week。

 The thing I really care about is， is going down here again。

 that you can still get a pretty significant bump by introducing these。

 these stages and vectorizing as much as possible。😊。

The newer version of hyper and Ubra before this paper come out can actually use CD and vectorization。

 but at the time in 2017 or 2016， they didn't support that because they were doing entire。

 doing nothing the push based execution with complete compilation of the queries。All right。

 so this is one way to go making sure that we're always utilizing all our buffers， but again。

 we did this before ABX 512 and in the paper you guys read they called this a materialization approach。

They also discuss two different algorithms you could use that try to be clever about deciding when to go back and get more tus from the operator below you。

 I think somebody asked a question about this and I said most systems don't do this but this is one way to do it and the challenge course is going to be the bookkeeping to keep track of where do I leave off in the operator below me and where can I write results into and they can do this in AVx512 because there's a lot more registers now so the idea is that while my operator is running。

 if I realize that I have an unutilized lanes， I can just leave leave all that data in that register go then execute another part of the query and have that right to other registers and then once that thing gets full then I can combine the two of them together。

At a high level， that's what they're doing for these real algorithms。

 The question is whether do you go get more tu postss within your own operator by iterating over the loop again。

Or do you jump out of that operator， go below you in the query plan and let the operator below you now start producing twoples off the query plan。

So the buffered one is the one where you stay in the same operator。

And the idea is that you use additional registers to sort of stage results。

 And so that the next iteration doesn't overwrite them， which is writes into another register。

 And then when that gets full， you can then use send instructions to compile them。

 The partial one is where they。Basically spill out all the results within the current operator to a bunch of registers。

 go down below to another operator， have it produce more results up through the query plan。

 pushing it up and then once that's full， then you can combine the two of them together。

So if you think of the top one is more simple becauses just like， okay。

 let me just call it let me call it next on my loop， you know within my same operator。

 but I just make sure that I don't write the same register that I wrote before and I don't need to keep track of where I'm actually writing to。

Other other than like， I don't write where I write before。 And this one。

 you're trying to be clever and like， okay， I know that there's things up above that I could write into。

 but I can't right now because these these links are being occupied。

 So try to like like fill things in at more fine grain level。Again， other than other than Ura。

 I don't think anybody actually actually actually does this。

 I think everyone just naively carries along the unused buffers on on the。

Carries along the dead tus and because it's just easier at the end。Okay。

So so far we covered selection scans vector refs， I want to quickly go through two variations of hash tables and then finish up with partitioning histograms。

😊，So in hashables， the challenge here is that。We have this data structure。

 this hash table that Khan is not really Cindy friendly。Right。

Because it's this long stride of memory。 but then we need to be able to do comparisons within in continuousuous regions of memory and not within you know。

 different lanes at the same time and contain different elements， right。

So the scalealar approach would be， you have some input key。 you hash it with some hash function。

 produce a hash off set。 You jump to that offset set。 And then now you just do again a linear scan。

Looking at all the keys within the hash table so you find your match and then you're done， right？So。

The way to， to use horizontal vectorization to to make this run faster is that。

Use within each offset， within the hash table， we're actually going to store four keys with four corresponding values。

So now when I do a lookup on a single key， I hash it in the modify by the number buckets or slots。

 and then now I land to some memory address now I get four keys。

And now if I want to comparison whether I have a match。

 I just duplicate this key in a single register， make four copies of it。

 and then do the same comparison， and that's going produce a bit mask that says whether I have a match or not。

And then whether or not you know， you do， you do the rank see whether these are all zeros are all one。

 then you do the same thing going down to you loop around。Right。So that's kind of cute。

 That's kind of clever。The problem of this one， though， is， like。呃。哎。That you know， how to say this。

Like， what if， what if it's not keys， these keys， these slots may be empty。

 And so I may be going fetch some location。 And there's like two out of the four4 keys there。

 So I can't guarantee that I'm always doing all my lanes are fully utilized when I do the。

 the comparison。So the alternative is to do vertical vectorization and the idea is now I want to compare four keys at the same time my hash table is just like well4 before I do have multiple elements each slot now it's just again a single key per slot。

😊，So I take my four keys， there's CinD operations or CinD instructions or CinD hash functions。

 you can use Merrmur 2。 I think there's aID version of that that vectorwise used。

 and then now I'm going to boost some hash vector， then I use my Cindy gather to go grab these different memory regions。

 put it into now a CinD vector。Then do my CMD compare to see whether I have any matches。Right。

Of course， now the challenges are going to be some of these tuos are going to match。

 Some of these twos aren't going to match。So then now， in the next iteration， I need to。

 for the ones that don't match， they need to all go down by one in my hash table to figure out whether there's a match。

 But again， I don't want to keep be doing the same computation over over again for two that didn't match。

So I want to go back and get two new keys to fill in the spots that did match before。

 and then now I've run another round and I just need to keep track of which lane as I'm going along what iteration are they at。

 like what location am I hash table do they need to go look at。

So maybe this thing is sort of wasteted computation for the middle guys， but that might be okay。

 that might be enough。Right， so then do the same thing do do the the gather to go bring them in to semi me registers and do the comparison until all all my I satisfy all my my checks。

his question is is vertical clearly better？Most times yes。不在。What's the benefit of the。

It seems like you're just doing it。This question is。

 what is the benefit for the horizontal or what is the benefit for the horizontal one。Again。

 the paper basically for every single core operator in a data system。

 they had a vertical and horizontal variant of them to show that you could do it。

And then the measurements determine， oh yeah， the vertical one is always better。嗯。

There's something else though， that's tricky about this that may not be obvious。And that is the。

There's not always me a guarantee that the， the。TheThe output tuoss are always going to be in the same order every single time。

 you run this algorithm， right。Because the。You're sort of reading the keys。In a different order。

 sorry， the output is going to be in a different order than the keys as they come into to the operator。

And under a relational algebra， that's okay， right， there is no ordering。

But if you're trying to debug this， then sometimes you run the same。

 same query and the same data and you'll produce output in a different order。

 and it's hard to kind of debug things to try to if there's problems you're trying to figure out。Am。

So it's not really a， you know， I would not say that's enough to discourage people not to do this。

 It's just to say like， it's someone to be aware of that， like the。I mean。

 hashing always try to randomize these things， but this takes to a higher degree。

 things even more challenging to work through it because again。

 the way the Cdy stuff is trying to do multiple comparisons at the same time。Alright。

 so I'm gonna skip the。ThisThis is the result from the paper。

 I don't want to spend too much time on it。 but basically。

everything goes once you run out of CPU cache for these different im and this is running on the Xon Phi。

 which is an older Intel accelerator。 think like Intel's version of a GPU in the 2010s。

 they don't exist anymore。 Again seem over here on running on Zons。 Once you run out of cache。

 there is actually no difference。😊，嗯。But， if if your hashable size is actually small enough。

 that's why you always put the small table on the build side， then you might be okay。

And CB cache has gotten way， way better。 I think there's the one AMD chip but like it's like 800 megs for L3。

 It's insane。Right。It's almost a gigabyte L3 cache on a single socket， that's insane。嗯m。So all right。

 let me show one other cool thing I like。 and this is。It's a really simple way to see like， okay。

 how can I parallellyze things with Cindi to do another basic operation in in my data system。

 So how do we build want to build a histogram。And so we if the problem is going to be that if we just do the naive thing。

 say these our input keys and we use Cdy Rax， which we'll cover in a few weeks。

 with basically think of poor man's hash function， You just basically grab the first bit and tells you where something goes。

And so we want to get the radius on this。 We have hash keys。

 and then we're gonna fill out some histogram。 But the the problem is gonna be。

 we're gonna to have two keys map to the same location in our histogram。

 and they're gonna collaborate them they're gonna collaborate each other when I try to， you know。

 put things， sumit together， because I'm gonna try to overwrite to the same position。😊，So。

 to get around this problem， I can just replicate my my hash table where for every single lane in my CM register。

 I'm just going to have another array。And so now I know that know。

 lane 0 is going to write to this column here。 La1 is going to write to this column here。

 So for each column， there's going to be one entry for the key in my my my has in my histogram。

And then I you just use a S ad to put it together across the lanes and then produce the final counts。

Right。Again， there's a bunch of different clever ways you can combine S operations and instructions together to produce results。

 again， keeping everything in CM registers。So this one I like。And this is clearly when。Okay。

 so we've covered this a lot already。😊，Put it out now on the slide。

 So A B X 512 is not always going be faster than A B X 2。 And as I said in the paper you guys read。

 there's this little footnote down here where they， they mentioned that in their experiments。

 they didn't see any down clocking issues with either the Skyl Xon CPU or the nights landing Zon Phi and that they was always running at a stable for4 gigHtz clock speed。

😊，But there's a lot of there's a lot of blog articles out there and a lot of stack stack overflow posts about。

 hey， my， my， my program's running slow， why and I trace it down to my CPU clock getting you know getting downcycled Why is this the case right And the issue has to do with。

In the case of Intel， they identify whether some instructions are either light or heavy。

 and if you run too many heavy instructions， then they dial down the clock speed and your thing actually runs slower。

Think of like if the CPU recognizes that it's getting too hot because you the fan's not running or something。

 it'll down clock itself so it doesn't damage itself。He says it needs to be bigger heating。

 I don't think it's even that。 I think it's like hardwired that it just always down down cycles it。

 I don I don't think it's try to sense sense the temperature。Yes， so I did further the research。

Apparently ontel CPU this isn't as bad， but it still exists AM they do this totally differently。

 They have hardware 2 registers and they use two of them to make the512 instructions work so it's always faster and never but it's not as big of an as so his statement is new versions of Intel they've gotten a little better at this。

 but I for the consumer ones they turn it off default it's actually fused off I don't think you can even turn it back on and that AMD doesn't really do true 512。

 they do two256 registers and put it together and they say that's always faster should be a but forco decos does the bit the key difference terms of databases does have I don't know if it has those capabilities right。

Anyway， and there's I can post on piazza， there's some blog articles from like the Klang people the GCC people were like。

You know， they will always try to use A V X 2 instead of A X 52 to try to avoid these issues。

 right Now you may be carefully say， okay， I'm going to make sure if I'm using intrinsics that I make sure I only use AV X 2 to avoid this down clocking issue。

 but you may link in some library that then gets auto vectorized A V X 512。

 and then your database is running slow because of some third party thing that you didn't weren't expecting。

 right。So。I don't know when， this all get fixed。 Who knows。But， like。

The safe bet is probably going to always be A B X 2。

 but I do know some of the commercial systems do run A V X5 12。

 and maybe they're try to be more careful about when if and when they use it。Okay， so to finish up。

 so vectorization is gonna be obviously super important。 doesn't always going to be the biggest win。

 And ideally， you know， we want to rely on the compiler the auto vector as much as possible。

 But in some cases， we do have to come in。😊，And either using intrinsics。

 which is more common or one of those libraries that can mask the actual details of what what C extension package we're using。

 And again， all the things we talked about so far about doing in queryry parallelism。

 This is all in conjunction to the S stuff。 So every core is going to have its own set of C registers。

 And so we want to use data parallelism within each core as much as possible。And again， well， we'll。

 well cover query compation next class。 but that's another tool we can use to， to。

Control the movement of data within our query plan so that we have precise control of when things are going registers。

 when they come out of registers， and how things are moved through memory or CPU caches？Again。

 so next class will be compilation。So it's going to be a German paper。It's very dense。

 It's a lot of L and IR don't sweat the details of that。

 The main thing I want I want you to get away from it is out of it is this notion of what he calls sort datacentric computation。

 that just really means the push model in his query processing approach and that again。

 how he's going to have fine grade control of what goes in the CP registers as things do with the query plan okay？

And then we talk a little bit about the project status in preparation the status update later this month at the end of this class as well。



![](img/a55ba0e98df074bca24360ded1a60926_11.png)

Any final questions？All guys， see。

![](img/a55ba0e98df074bca24360ded1a60926_13.png)

Stack and six snacks on the table and I'm able to see saying I was on my way。Don sure put the crop。

 you know what got them， I take off the cat but first' tap on the bottom。

 don't about three in the freeze it so about the killer。

 cat for with the bottle baby don't feel it co they nice and says the pain nice way you can't get down with the guy little。

Take back the pack of ths， andvo to some same now for cricket to the ths。

 Billy De and toil teach to tell the weak God， be a man to get a can of same time。

