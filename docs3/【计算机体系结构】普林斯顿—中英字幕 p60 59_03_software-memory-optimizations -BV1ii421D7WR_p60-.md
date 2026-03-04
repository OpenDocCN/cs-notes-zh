# 【计算机体系结构】普林斯顿—中英字幕 p60 59_03_software-memory-optimizations -BV1ii421D7WR_p60-

![](img/76d75659875e1b66d4e3c97af8b823da_0.png)

Okay， so now we get to what can software do for my cache and what can software do for my memory system。

🤧。Well， surprisingly a lot。 And compiler people actually。

Do you spend a fair amount of time thinking about this？

So one of the things you'll actually see is you'll see the compiler in many times。

Pad out data structures。 So if you go disassemble a piece of C code that you have。

 you'll actually see the compiler。 many times willll insert extra bytes， which wastes memory。

But it's there to improve performance。And how this improves performance is it'll make the access patterns。

For instance， either not conflicting in our cash or conflict in our cash in a strange way。

 which is beneficial or will somehow。Exploit either temporal or spatial vity。So。

You can do lots of tricks here to either improve spatial or temporal locality。

 One of the things I did want to talk about is sort of a hybrid software hardware solution here that you can actually。

Add instructions to your processor。To give hints。To allow the compiler to give hints to the architecture。

 whether to pull something into the cache。Or not p into the cache。 So many times。

 the compiler will actually know or the programmer will know。I need to use this data。Exactly once。

Now， if you know you only need to use that piece of data once， should you pull it into your cache？No。

 you're never gonna reuse it。 You're're never going to get a cash hit。

 You're gonna take the cash miss。 And then some point later in the future。

 you're just gonna invict it。 And you it's gonna to hurt your mis rate。So， instead。

There's been an introduction actually， sometimes people call this nontempor hints or no allocate bits。

 So one way this actually works out sometimes is certain pages in our memory system are marked as being non-tempor and or won't be cashable。

You can do this on X86， actually there's non cacheable bits in the page tables， for instance。

A finer grain way of doing this is actually having special load instructions or special store instructions which say。

 do not ever bring this into my cache or do not pollute my cache of this data because I never intend to go read this again。

And lots of architectures have started to include this now as an optimization。

Another fun thing you can do is if you know if the compiler or the software system or the programmer knows that you're never going use the data again。

Why let it sit there and rot in your cache？Get out。Get out as quickly as possible。🤧嗯。

A coupleuple different ways to do this。 So one of the。

 the instructions that you can add to the architecture and have a software hardware approach to this is you'll actually add something that。

I think on X86 is actually called flushush and invalidate。So the idea is that you。

 you may still have dirty data in that location and you want to flush it out to main memory or flush it out of my cache and invalidate the data in the cache。

And by giving the compiler or the programmer find great control of this。

 you can effectively kill data that is in the cache。

And make it clean or make it clean and not valid in the cache that line。

 So when you go to bring in new data， you don't have to evict something。 So you're effectively。

It's kind of the in of prefech and software prefetch。 you bring something in early。 Here。

 we push something out early。And that， that can be， a pretty big benefit。

 One of the other things is that。Not。I don't quite have this。 I don't this on the slide here。

 But there's there's a corollary to this。 There's lots of times architectures will have an instruction called。

Basically， it's just like inval instruction。It'll invalidate the data。

And this is the semantics of this are a little bit You have to be a little careful with because this inveil does not flush the backing data out to main memory。

 You're changing architectural state with this instruction。 So if there was dirty data。

 you're effectively deleting that dirty data。Sometimes people will actually use a instruction similar to that。

 instead of flush and invalid。 If you know that you just have scratch pad memory or you don't need the backing data。

 And that's a way to， you don't have to waste the right back bandwidth to your L 2 or your L 3 or your main memory。

 You can just say this data is no is now dead。 I never want to use this again。

So that's typically an inve instruction。And in instructions will lots of times take a cash。

Line number instead of an address。 Sometimes they'll take an address。

 and it will validate the entire cache line。 Unfortunately。

 you need to take the entire cache line or cache block。And throw it out。And the finally。

 the inverse instruction of that instruction， which a couple architectures have。 I know Alpha has， I。

I think X86 has later added it， I don't know what's called an X86。An。Alpha， it's called。呃。

Like something call like right 0，64， I think， is what it's called。 Basically。

 what you can do is if you have some data。And you want to write some data to your cache。

 but you don't want to have to go pull in the backing data。

Because that will just effectively add bandwidth out to your main memory system or out to your higher levels of cache。

 and what you can do is there's a special instruction。

Which will just fill the entire cache line of zeros。Out of nowhere。

And what's nice about this is now that you filled an entire cache line of zeros。

 you can go do rights to those zeros and fill in with useful data。

And never have to have gone and fetched the background data from memory。 So it saves bandwidth。

So these are all different hardware software techniques together that the compiler can use to optimize。

Performance。But yeah， I do just finally one last thing about this improving spatial locality and temporal locality。

 If you ever go disassemble a C program， you'll definitely see structures。

 if you're in the C program with feedback driven。Compilation。

 you'll see that a lot of times they'll actually reorganize the data structure。And languages。 So。

 for instance， if you go look at the careful description of what C says about this。

 some languages allow you to insert padding or reorganize some of the fields in a data structure。

And by doing that， you can get more performance by effectively reorganizing data so you put all of the things that you access in a row right next to each other。

 and that'll get you， for instance， spatial locality。Okay。

 so now we get to go to some of the fun software optimization strategies。😊。

So let's go to the first one here。I'm going to give you guys a second look at this code。Look at。

 look at the top example first or the top piece of code first。We have a loop around a loop。4 J。

Is less than n for I is less than M。Okay。So it's doubleubly indexed array X here。We're effectively。

Striiding through his array。Somehow。And we're multiplying every element in the array by 2。Seems。

 seems basic enough。So one of the questions that comes along here is。In sea。The default layout of x。

It's a doubly indexed array。😡，And we're walking。By the higher index。Is the inner loop here？

So if we look what's happening here， this is a 2D array。X。And。Iy goes that way。And J goes that way。

Now we're going and we're walking through this array。By I。So we're going to walk。downown。I walk down。

In that pattern。By default in C。This array gets laid out such that the。Second index。

Gets wrote laid out contiguously。And the higher order index gets laid out。Non contiguously。

 So this would be addressed， let's say0。 This would be addressed 1。 This would be addressed 2。

 This address 3，4，5， assuming these are all bytes。And me come back over here，6，7，8，9，10。我话明。

Unfortunately， with the way that the top loop is written。We're effectively hitting。

We're fighting spatial locality of the cache lines。嗯。That's not good。Well lo and behold。

If we do the exact same operation and our compiler can easily detect this。

And we just flip the order that we strive through the array。We'll take going。

This way through the array。Instead。We'll go that way through the way。And get。Spatial locality。

Perfectly。So by doing a simple loop interchange， life gets a lot better。

Actually before we move on here， I do want to say。This this brings up a good example of packing of data。

I have something here with saying。Which has6。Bites。In a row。0，1，2，3，4，5。Now。

 one optimization that compilers will times do is they'll actually。Had out this structure。

Let's say out to eight bytes。Because it makes the math a lot easier。

To go stride through the array indices。So that's an example of one of the things that I showed before。

 it'll also sometimes even have better cache performance because you'll pull in an entire line at a time versus straddling different cache lines if you have odd。

 a non naturallyally aligned structure like we had before。

That may not happen in this That may not hurt in this example if you're striv through the entire right。

But other examples， could， could definitely be harmful if you are trying to operate a lot within one row。

Okay， before we move off the loop interchange， that。啊， actually。

What type of locality does this improve。Sppatial， ya， ya， we drove that one。Down pretty well。Okay。

 so let's look at our next piece of code here。For I。Less than n。We multiply。

B of I times C of I and deposit it into A of I。And then， the next loop。something very similar。

We take C of I multiplied by A of I and deposit it into。Divvi。Well。You to say， how does this happen。

 This seems like a brain dead way to write this piece of code。Yes and no。

 Maybe you do something in between here。Between these two four loops。

And it may not be readily apparent to everybody that you can actually。Do anything about this。 like。

 because you have a piece of code here， which goes and reads。I don't know。 all they。For instance。

Well， the compiler can recognize this and actually say， well。We just wrote this entire array。

And now we go back and read this entire array。 And we read C before， also。That's not。

 that's not very， very good because we're effectively， let's say these caches are， assuming。

 these arrays are large。We're going to readency。An element of C， arena element of B， deposit in A。

 And we're basically strive through the cache。 And these all these three arrays are going to kick each other out。

But the time we get back to here。A of zero is definitely not going to be in our cache。😡。

Maybe a of the last element will be in our cache or A of N will be in our cache。

 or A of M1 will be in our cache， but a of 0 is not going be in our cache。So our compiler。

Can think real hard about this and do what's called loop fusion。And pull these statements apart。

Such that you take。B of I times C of I。Put it here and then use that。

 You're probably actually going to do that at temporary very。

 You're probably not going do that through your main memory。

If you have AF I and A of I in statements right next to each other。

 but you still have to write A of I， we'll say for a program correctness。

And you take A of I and C of I， multiply them have each other and put them into D here。

 What's nice about this is you're actually going to bring in。😊，A cache line of B of I。

 We're going to cache line of C of I。Do the multiplication。You're bringing。Well。

 you already have A of I because that's your destination。And you just have that in variable。

And then you can write it over into D ofI and stride through all those cache lines together。

 and effectively， you are not having to go refetch a of zero multiple times。Instead。

 you've fetched it once。 And what's also nice is you't have to go refreshfe。

 Let's say C of I twice or C of 0 twice。It's already there in your cache。Okay， so。

Quion comes up here， what type of locality does this improve？It'sor， yes， because before。

We were bringing something into the cache， kicking it out of the cash。

 bringing it back into the cash。Both these actually exhibit decent spatial locality actually already。

 And we didn't really change the spatial locality of what's going on here。

 They're both striding through rays。Spatly， but temporally。We don't have to kick。

Every we don't have to kick。A and C out of the cache effectively twice。

 or we bringing into the cache twice。So we're able to exploit a bunch of spatial locality here。

Or sorry， It was to explain a lot of temporal locality here。Okay， so now。

 now we get to do something a little bit more sophisticated。Matrix multiply。

Common thing for computers to do。 You want to take at least in dense matrix codes or linear algebra sorts of codes。

 You take matrix A。 You want to multiply by matrix B。

 So this is like traditional matlab kind of code。 You have some matlab。 You have a big array。

 You want to multiply by another array。 And let's take 2D。Marices。

 this applies to higher dimensional matrices also。不。

It's easy to draw two dimensional things on a two dimensional screen。

 It's hard to draw four dimensional things on a two dimensional screen。 So we'll start with that。

Here's our naive。Implementation。We， we had。3，4 loops going on here。

And what we're doing is we're doing the traditional way that you learn how to do matrix multiplication。

You take a row。Multiply by column。And that's that spot。 Take this row multi by that column。

 That's that result。 This row by that column。 It's that spot， this row by that column there。

 And you just work through it。 And youre basically。

 when you let let's step through actually what the multiplication actually is， you take this value。

 multiply by that value， take this value， multiply by that value， and you continue。😊。

Going down and summing each of the multiplication results。

And that's how we ultimately end up with this point here or this value here。

 So this is the input input output。Okay， let's think about what this does。To our cash。Okay， let's。

 let's say our cache line， these elements here are， are bigger。

 They're not just one byte or one word。 There are a couple words or theyre maybe like a long。

 long or something that。 They're a big data structure。 They're big， big value。

And let's say only three values fit in a cache block or a cache line。

So when we go into this multiply， we basically have to bring in two lines。For this one row。And then。

Over here。If cache lines are arranged this way， as we go down。This column。We're bringing in。

Different cache liness。And only using one value out of that cache line。Well， that's not super great。

Make matters worse， let's go look at the output array。

The output array looks relatively similar to the input array。 We're writing here， writing here。

 writing here， writing here， writing here， writing there。

 So we're just kind of streaming through memory here。I don't know if we can do better。

 That's a good question。 At least we're going。At least that way how this code is written。

 We're going from left to right。 So we're actually taking advantage of spatial locality。

We could doing， could be doing worse。But just a recap here。This is pretty poor cache aes。

We're bringing many cache lines。They're all going to fight each other， especially for large arrays。

And over here， we're pulling in。Line after line。Even though one of the interesting things is after we do this multiplication。

 times that。We're going to do this multiplication by the next one。Which sounds good。 You know， this。

 times this， this times this。 we should be getting temporal local Kellyli here， but the downside is。

For very large。Sized matrices。As I said， this can be multiple。Blocks or multiple lines long。

 What's going to end up happening here is this may come in with something else farther down。

If it's a very large cache。In its own array， or you're just increasing the occupancy into the cache。

So we're gonna to talk about blocking， which will actually make it so that we can actually only read。

One block at a time and do the multiplication in multiple steps。Okay。

 so the code gets a little bit more complicated when we go to。Blocking our cash。

Or blocking our memory multiply。Sometimes people call this tiling， instead of blocking。Soer of。

I think tiling is traditionally sort of meant as a matrix。

 multiplication specific term to a more general thing， which we'll call blocking。

Cke gets a little more complicated。But what we're going to do here is we're going to start off by here。

And multiply these three elements by these top three elements and deposit it into the result。Now。

 you might say to yourself。That's not the result that needs to go there。It's not。

 It's only half of the result that needs to go there， in fact。So you need to do something。

 You need to finish this multiplied by that。And。Add what was here before with that new value。

But the nice thing is， addition is communicative。So we can reorder these steps。And in fact。

What we're going to do is we're going to block。Or tile。 and have this block。

Rotated multiply by that block and deposit the results here。And then in our next step here。

 if you see， we're actually going to。Some into the same destination。

So the first step is we're gonna to take this multiply by that。

 And what we're going to see here is we're going to have 1，2，3 cache lines。And over here。

 we're actually going to have one， two， three cache lines， even though we're accessing them this way。

We actually design this algorithm such that we reuse that other portion of the data we pull in here。

And then we're going to do that and sum the partial。Part of the multiplies into these nine locations。

And then we're going to do the second half of that。 We're going to take。

This multiply that and accumulate them into there。As you can see， this actually is going to have。

Some better locality， which we'll talk about in a second。

And we have to bring in fewer cash lines at the same time and still get good performance。Okay。

 so let's look at the， if you want to compute。This part of here， because we're not。 We didn't。

 We talked about， in this example here computing this entire result array。 So how do we compute。

That part over there。It's the same idea。 You're gonna take。This。Allll part that。

Just deposit it there， and then take。This rotate multiply by that and accumulate into there。

So a couple things。So。Recap here， a couple happy things about this really。Able to。

Shrink the working set in our cash。 So our cash capacity is lower。

For what's really going on here or rather， our effective cash load is lower。

 The number of cash lines we need to keep in our cash is quite a bit lower。We also。Can have better。

So， that's。Going to be temporal locality。Because we're basically going to have the data in our cache。

 and we're going to be working on the data in our cache。 Now， we also end up with， you look at the。

Input array here。We're also to have better spatial locality。

Because before we are sort of streaming through all these different cache lines。

 and now we can work on one block at a time。 and especially in our result matrix， because。

This and this， reuse these entries in our result matrix twice。So we can get some benefit out of that。

So， so the answer is you get both temporal and spatial locality improvements here。But it' a fun。

Software optimization you can do。That improve your performance。Okay， so let's go look at。

Compilr memory optimizations and what we can get out of this well。你给他。

Get some different things out of this。If you do the cool tricks where you have non temporal hints。

 to some extent， you can use that to increase your。

 your bandwidth because you're utilizing less bandwidth。Hit time。

 I don't think you're really going to allow software to change the hit time。

You know it's a hardware contraint。 So we're not going to have anything to do about that。Mis penalty。

嗯。We might be able to help out with。So how does the compiler help out with this penalty， Well。

 it can schedule the data so that's in closer。 for instance。

 that blocking algorithm will actually use a smaller cache footprint。Soll fit into a smaller cache。

 So we won't have to go out to the L2。 So a good example of this is。

 let's say you have a matrix multiply in your matrix multiply。 It fits in your L2。

The naive approach fits in L tube， but doesn't fit in the L1。



![](img/76d75659875e1b66d4e3c97af8b823da_2.png)

![](img/76d75659875e1b66d4e3c97af8b823da_3.png)