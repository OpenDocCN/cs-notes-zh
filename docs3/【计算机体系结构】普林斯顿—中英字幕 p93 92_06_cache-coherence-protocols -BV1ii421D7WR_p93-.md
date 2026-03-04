# 【计算机体系结构】普林斯顿—中英字幕 p93 92_06_cache-coherence-protocols -BV1ii421D7WR_p93-

So we're to introduce this notion of snoopy cash coherence。Or a snoopy cash。

 And this is work by Jim Goodman and one of his students who's now， I think。

 a U C Irvine faculty member。 And they had this idea that have the cash。Watch。

Or what they'll call is snoop。Either DMA transfers or later it was extended to transactions from other processors。

 other caches。And then。Do the right thing。 Now， what do we mean by do the right thing。Well。

 I'm purposely being a little bit vague there because there' are sort of two or two classes of ideas that you can。

 you can do for doing the right thing。 But the most basic do the right thing is if a cache sees a memory transaction go by for an address it has inside the cache。

 it needs to take some action。Now， what is that action could be， Well。

 maybe the most basic thing it could do is if it sees that transaction go by and it knows that it has an address which is going across the bus and someone's trying to do a memory transaction for an address。

 which it's caching。It might need to at least tell the other entity that something is going on。

 that it has a the more up to date copy somehow。 And we're gonna to look at in today's class。

 two different protocols。Or two different classes of protocols to handle this problem。Now。

If we go look at this， the， the implementation of this， we have a processor。And we have a cache。

 And what do we have in a cache。 Well， we have the data rate， which actually has the data。

And then you also have a。Tag and state array。 So the tags have the， the tag match logic。

 and it also has the actual tags， the upper bits， if you will， of the address。

And the state array has whether the data is dirty and whether it's valid and usually sort of least recently used or most recently used information。

And the insight that the s Snoopy cashshwork had was that instead of having only one port into the tag array。

The tag in state array。 Instead， you add a second port。So， the second port here。

Is attached to the memory bus。And this second port has to watch。All transactions on the bus。

 And it sees a transaction which has an address that is。 it has in its cache already。

It has to somehow signal that theres a case where there's gonna be sta data and something needs to be done。

So that might include removing the data from its own cache。

 That might include it sending the data across the bus and telling the other entity。

 the other processor will say or D agent that is trying to read the data to wait a little bit。

 And we're gonna look at that over the next few slides of what different things can be done there。

 But what's the downside to something like this snooping protocol。 Well， every entity。

 every processor or every cache that sits on the shared bus has to watch。All memory transactions。

 So they have to watch everything。And。The problem with this is the processor here wants to be able to access this cache。

 So it wants to be able to do operations concurrently while there's stuff happening on the bus。

 which is not related to it。 So this requires our snoopy cache tags to be dual ports。

 So there's two ports to these tags， which makes this bigger and， you know， potentially waste power。

 etc。Okay， so let's take a look at our shared。Memory multi processor。

 now that we are thinking about having。Snooping caches。Or snoopy caches。 So in this picture here。

 we now have。A shared memory bus in the middle。 We have three processors on the left。

 and we have three snoopy caches。So now， whenever， let's say processor 3 tries to do a transaction。

 it needs to。Let's say broadcast onto the bus that it's trying to read a certain address。

 The other caches need to be notified of that。 And they to check their own tags and then do the right thing。

So what does do the right thing mean？So let's take a look at that。

And we're going to broadly put snoopy cache coherence protocols。Into two different categories here。

The first one we're going to call is update protocols。

 and the second one is going to be invalidation protocols。So what's， what's the difference。Well。

 we're trying to maintain the data to be consistent amongst all the caches。

 So we're trying to get rid of the stale data。The first thing you can do is we can try and do a write update or what sometimes people will call broadcast based protocols。

 So the basic idea is whenever you do a right。To your cash。You also write that onto the bus。

And everyone is listening on the bus。 Everyone snooping on the bus。And if you。

 let's say processor 1 does a right to address 5。If processor 2 has addressed 5 in its cache。

 it's going to see the right。And it's going to take the updated data， and update itself。

So this is going to， this is sort of the moral equivalent of the right through case we saw before。

 But now on the bus， when someone does a write， everyone updates their local caches by listening on the bus for the particular address and listening for the new updated data。

 So it's a broadcast。 So every right you do that。Transitions or every right you do sort of through a memory transaction is going to update all of the other caches in the system。

 Now， why is this good？ Well， it guarantees that when another processor tries to do a read of。

 let's say that address 5。It no longer has a sta value。

 It has now the most up to date value because we broadcast it and we updated in place。

 And we'll talk about that in a little more detail， in a second。

Second thing you can do is what is actually more commonplace today is called a invalidation protocol or a write invalidate protocol。

And in a write and validate protocol， whenever you do a right。You。

Invalidate all other copies of a piece of data。 And by invalidating all other copies。

 you've effectively or all the cache copies， you've effectively removed the possibility that you could have stale data。

 so。Let's look at these two protocols in more detail here。So first of all。

 we'll look at a right update based protocol or a broadcast based protocol。

 And we're gonna look at two cases a。Write， miss to the cache。 and a read。Miss to the cache。Okay。

 first of all， a right miss。So you go to a right miss。 Well。

 if you miss in your cache and you're doing a right。

 you tell everyone else in the system that you are doing the right and all other processors。

 which are listening， listening to the bus update their copies in place。So you broadcast in the bus。

 I'm running to address 5。 Someone else has address 5 in their cache。

 They update their copy internally。Okay。That， that sounds。Not， not， not， not so。Not so bad。

 but there's a lot of bandwidth there。 You're basically broadcasting rights to everybody。

Let's look at the read side。On the， the read miss case here。You know that main memory。

Is always up to date。Because you've。Are forced to basically write through to main to main memory。

 So you just go to main memory on a readmiss。And you don't have to even sort of check other caches on's look gonna read hit。

read hit in your cache。 You know that the data is in your cache， and you know the data is up to date。

So you don't have to worry。Okay， so let's say in update。Protocol。

 let's take a look at a write invalidate protocol。 What happens on a write miss and and a read miss。

 So on a right miss in a invalidation based protocol， you're going to actually invalidate。

All of the other caches， which have that address in them。Before you are allowed to do the right。Now。

 how does this work， Well， on that shared multi droprop bus， you scream。

 Im going to do a right to address 5 and everyone else， because they have a snoopy cash is listening。

 and they hear someone is doing a right to address 5。And what they do is they invalidate their data。

 They remove it from their cache。 And by virtue of them， remove it from their cache。

 you can no longer have a sta value in the， their cache。 Now， I will want to point out here， though。

 that one of the things you might have to do is when you go to do the invalidate。

 you might actually have to write back that data to main memory somehow。Because if you have a。

 let's say， a write back cache and a different processor has a dirty piece of data。

 let's say for address 5。 and then processor  one tries to write that data。 Well， at some point。

 you need to sort merge the data in a cache line。Processor 2 might have to go and invalidate。

 but at least it knows that it has to do this invalid validation。

 and it has to do that validation before Proor 1 does the right。But we can do this all on our snoopy。

Shared bus。O， what happens on a read miss。Well。If no one else has the copy， this is easy。

 You said you scream on the bus。 you scream in the room saying， does anyone have address 5 and then。

If it's an empty， empty room， no one， no one yells back and no other caches have that data。

 But conversely， if someone has a dirty copy of that data。They need to write it back to main memory。

And you need to read that most up to date copy。So they need to flush the data and potentially invalidate the data。

 depending on the cash coherence protocol。 And we're to look at a couple different cases of that。

So before I move off this， I also wanted to sort of point out when write and validate protocols versus write update or broadcast protocols are good and vice versa。

 so。Most processors you'll see today use some sort of invalidation protocol。 And generally。

 those are actually are going work better because there's gonna be less bandwidth across your bus because you only need to communicate across the bus when you take a cash miss for a write or。

 or a read。Conversely， update protocols， you basically have to broadcast all， all your updates。

 But the， the， the cases where an update based protocol actually wins is if you have many readers and one writer。

So let's say you have five processors which are reading the output of one processor via memory。

 So you have some sort of producer consumer relationship。In an update based protocol。

 you can have that one processor just write， and it will broadcast and push the data to the five processors that are trying to do the read。

In the invalidation protocol， what's going to happen is you're basically going to have to have invalidates bouncing the data back and forth and back and forth every time you do a read or write。

 So there actually could be more bus communication in the validation protocol for one reader one writer multiread cases。

But for the rest of today， we're going to focus on invalidation。Or invalid protocols on a snoopy bus。

Okay， so let's。Take a look at。The extra information you need to add into a cache in order to go implement something like a right invalid protocol。

And。We're gonna look at a base case here， which is called a MS I protocol。

 This is one of the more the basic ones that you'll see。

 And there's some extra bits that are added here。 So let's look at the tag information。

 So we have a tag for your processor。 and typically， you have a valid bit。

 We had talk about having valid bits or dirty bits。

 valid and dirty bits and something like a processor。Some something like a cash， Ex me so。

Each cache line has this information on a per cache line basis。And instead of having， let's say。

 one valid bit and one。Dirty bit。 We're going to use these two bits to encode a state in a state machine。

And we're going to add。So， so we have two bits so we can code four things。

 We can definitely encode three things in two Bs。So we're gonna actually look at a protocol here that we're going to call the MI protocol for this that's named for the state names。

 So we have M， which is modified S， which is shared and I， which is invalid。

And we're gonna say that invalid is basically whether the data is valid or not。

 If you're in the invalid state， it is， It is invalid。 If you are in any of the other states here。

 the data is valid in your cache。But now， instead of having just a dirty bit。

 which tells you whether the data is dirty or not in your cache instead。

We're going to have two other states here， modified and shared。

And what we're gonna to see is by adding these states。We can。Guarantee some level of cash coherence。

 we're going implement a cash coherence protocol on top of this。And。

We're going to remove some of the communication across the bus by remembering whether the data is。

Widely shared or whether we have the sole copy。So what are these three states？Eyes invalid。

It's pretty self inspiratory there。 The data in your cache is invalid。 You're not allowed to read it。

 If you try to access something has an invalid bit set in your state bits。

 you are going to take a cash miss。And that has to transition to one of these other two states。M。

Is modified。So modified means that the data in the cache has been modified relative to what is in main。

 main memory。So this is。Dirty data。And then we're gonna have this other state here called shared or S for shared。

 Well， what is， what is shared well。S or shared state here is going to mean that you have a read only copy of the data。

And someone else may also have a read only copy of the data。 hence the term shared。

 So it's shared amongst multiple people。 But we're gonna say that when you're in the shared state。

You're not allowed to do it right。And one of the things I wanted to point out about this is that each。

Cash line。In each cache has this state machine there。 So different caches。

Have their own copies of this state information。 And the state information only relates to that particular cache or that particular processor。

 And the state diagram to build up here is only in relationship to processor 1。

And we'll see that because it's a snoopy cache， you might be in a state。

And then you might see a transaction go across the bus。

 and you might have to take some action to keep memory coherent。

So let's walk through this basic state diagram here。 We'll see that when we're done。

 we'll actually have the data be coherent when we go to implement something like this。

So what's our first arc here？Let's say we have a read miss。We are in the invalid state。

And we do a read。Mis。And this a here is basically from invalid or it is from invalid。

 I just didn't draw it looping around because otherwise， the the diagram gets too complex。

 So you do a readmiss。You shout onto the to the bus。 I want to read some address。

 or Proor one here Shos onto the bus and says， I want to read an address。Okay， so。

Something happens on the bus， the other。Processors might have to do transitions， but ultimately。

 you're gonna get the data or get the cache line from main memory。

And you're gonna bring it into the shared state。 So you now have a read only copy。

 You can read this from your cache as much as you want。

 And you don't have to communicate on the bus anymore， then。Because you have just do a cash hit。Now。

 if you have to do it right， though， things get a little more complex。So， so this is。Let's。

 let's take a look at the case here。That。You have the data in shared state， but some other processor。

Tries to do a read。 So they shout onto the bus。 I want to do a read of the address that is in the shared state。

Well， if we go look at the state diagram here。That's O。 Its shared。 We can have a read only copy。

 and someone else can also have a read only copy at the same time。So we just transition from S to S。

 We stay in the S state。We don't have to do anything when someone else reads some other processor reads the data。

Now， let's say we're in the shared state in other， some other processor yells out onto the。

 the bus saying， I have an intent to do a right。 I want to do it right。

To address that you have in your cash in the shared state。

 Your processor  one has in the cash in the shared state。Well， we said that。Style data causes the。

Incoherence of， of the data。 And that's what we were trying to prevent。

 So if you see some other processor trying to do a right。You just drop the data from your cache。Now。

 because you only have a readname link copy， you don't have to write this back。

 You don't even have to tell anybody about this。You just have to guarantee when they say I want to do a right that you transition from S to I。

Now， what this means， though， is， if Proor  one wants to go read that data in the future。

 it's gonna have to get a copy of it again because the copy it had is now invalid。Okay。

 let's say you have the data in the shared state。 but now you want to do a right to that data。

Can you do a right to it while it's in the shared state。No。Why。

 cause someone else may have a copy of it。You're in the shared state。That means it's shared。

 and someone else could have a stale copy of that data。So you go to do a right。

 What you have to do before you transition your state is you need to broadcast your intent to write to that line。

 or Proor  one has to broadcast onto the snoopy bus that it wants to write to that line。Okay。

 so it says， I want to do right。 I I to do it right。 And before it transitions。

 it needs to wait or give all the other processors time to invalidate and potentially write back the data。

And different processors implement this in different ways。

 Some processors just wait a certain amount of time as a waiting period。 So you。

 you broadcast saying I have an intent to write， but I'm not gonna。

Do the right until some period of time in the future。 like a waiting period。

 that gives enough time for the other processors to snoop the transaction invalid the data and write it back to main memory if they have copy or。

Let's say everyone else only has read only copies of the data。They needed transition from S to I。

So I wanted to point out here that， you know， all different the different caches in the system don't have to have the data in the same state at the same time。

 This is a per cache state。 So when you have an intent to write。

 you broadcast this information and everyone else has to invalidate it from their cache。

 So whether they have an S or I， they need to somehow S or M， they need to transition to I。

And only then。Can you transition to M and actually do the right？ Now。

 I said there's other ways that you can go about doing this besides having a waiting period。

 One potential thing that people do is they'll actually。Broadcast their intent to write。

 But instead of actually doing the right， instead of having a waiting period。

 they wait for an acknowledgement from all the other caches somehow。That。

 that's functionally the same。 You can either wait and sort of have a proof knowing that you've waited long enough or you can wait until everyone is responded back saying。

 yep， I'm， I'm done。Okay， so what's this modified state， What does this give you， Well。

 if you're in the modified state， you can write the data and you can read the data。

So let's say processor 1 does a read or a write。 Well you just stay in the modified state。

 and you can do as many reads and writes as you want。 And you never have to communicate on the bus。

 You have the sole copy。 You have the， the， the token， if you will。 You can， you can read it。

 You can write it。 No， you guarantee that no one else has a copy。Okay。

 so let's say you're in the M state and some other processor broadcasts their intent to write。Hm。

You're in the modified state。You have dirty data。 You've done a right to this data。

 Mainin memory is out of date。So the most basic thing you can do is。Invalidate your copy。

And give that copy back to main memory or write back to that data to main memory。

 And then the other processor will go and read that data from main memory and pull it in in their modified state。

 So you will transition from M to I， and they will transition， let's say， from I to M。Okay。

One more arc in this diagram here。 What happens if you're in the modified state and some other processor tries to do a read or or broadcast an intent to read across the bus。

Well。What's nice here is you don't actually have to transition to the invalidation。State。

 and the reason is you have the most up to date copy of the data。

They need to see the most up to date copy of the data so they don't get any stale data and you don't have any stale data。

 but。You don't have to transition down to the invalidation state。 You， you。

 you potentially could try to go down to this state。

 but it's gonna require you to actually go pull the data back in if you want to read in the future。

 So instead。In the MSI protocol， if another processor tries to do a read。You do the right back first。

After you've done the right back， you transition to the shared state and they pull it in in a read only copy。

 and you have a read only copy。 So you both will transition to the shared state or the S state here。

Okay， so let's。Look at this。In a little bit more detail here。 Yes， sorry， There's one。

 one more arc that I missed。Rightness。 So if you're in。The modified state。Or sorry。

 you're in the invalid state。And。You want to do a right to align。We didn't draw this arc。

 but there's an arc that goes from invalid all the way around to here。And on this right miss。

You broadcast your intent to write。 You have to wait for everyone to do their invalids out to main memory。

 And in the base case， you pull that data in from main memory and you。

 you enter into the modified state。Okay， so let's take a look at a basic two processor example here。

 Walk through a set of reads and a set of writes and watch everything that happens here。

 So we're gonna have processor one in the top， processor 2 in the bottom。 and we're gonna walk。

Through different arcs here， as Proor one does reads and Proor2 does reads。

 and Proor one does writes and Proor two does rights。So。

Let's say the first thing that happens is processor 1。Does a read。

 And this is all to the same address。Or all to the same cache line or all addresses within a cache line。

 So Proor 1 does a read。We're gonna assume that all the data starts out invalid in all the caches。

 So usually when you reset your computer system， everyone's caches are invalid。

 How could they not be。So you're gonna do a read miss。 It's gonna go out to main memory。

And you're gonna bring the data in to the shared state in processor 1。

Prosor 2 is going to leave this data invalid for right now。Okay， now processor 1 does it right。Well。

 it broadcasts intent to write Pro 2 doesn't have this data。

 and no one else in the system has the data。 So no one， no one screams back。

 I have the data on the bus。 Please wait。 So instead。

 processor  one just goes ahead and transitions into the modify state and。In this case here。

 it even has the most up to date data。 so it won't even have to go out to main memory， potentially。

Okay， then processoror one does， let's say， processoror  one can do reads and writes past this point。

 Now， processor 2 does a read。Well， processor 2 doesn't read。

 Now we're gonna have two different state transitions happening。

 We're gonna see processor  one do a state transition and processor 2 do a state transition。

 So processor。2 is in the invalid state right now。It's going to transition to the shared state on the read miss。

At the same time， because。Processor one has it in the modified state。

 It's going to have to in write back the data and transition。To the shared state。

 So both of these processes are now in the shared state。 So they both have re and copies。

 and the most up to date copy has been up to date copy that the data has been pushed out to main memory or written back to main memory。

Okay， so now let's say Pro 2 does a right。It has it in the shared state。

 This has it in the shared state。 Well， when you go to do this right。The we're going to see。

An intent to write coming out of processor，2。And this is actually going to cause processor one here to transition from shared to invalid。

So。Yeah， this is kind of odd here。 Proor 2 is doing something but it's causing processoror  ones state machine to transition。

And it's because they're on this shared bus that Prosor 2 shouts， I'm going to do a right soon。

Processor 1 sees this。And it transitions。Once you know that processor  one has finished this transition。

 processor 2 now。Can transition to the modified state。 and actually。

continueinue to do reads or writes to that line。Okay。

 so let's say processor 1 wants to do a read to this line。

 This line is getting a lot of traffic to it。 Processor 2 just wrote it。

 and it's in the modified state。Procesor ones in the invalid state。 All of a sudden。

 what's gonna happen is it's gonna want to try to transition to the shared state。

 But this modified state is gonna cause a problem。 So we're gonna have to wait for。

We're gonna have to wait for the。Right back to occur here。From modified to shared。

 So it's going invalidate that data。 And then finally。

 Proor  one is going be able to bring it into the shared state。Okay。

 so let's say processor1 now does a read。 So it's in the shared state。This is in the shared state。

We see the intent to write coming out of Proor 1。So Pro 2 is going to transition from shared to invalid。

 And only then are you allowed to transition from shared。To modify。

And then as we get close to the end here， let's say that processoror true 2 tries to do a right to round everything out here。

 So we have processoror  one in the mod state。 Procesor 2 is in invalid。

 and it's going to try to go this way or the a will probably come like this。 at the same time。

Processor  one is going have to invalidate this data somehow， so。We see the， the right try to happen。

 And what's going to happen is when it sees the intent to write。

Processor ones if to transition from modified to invalidate and write back that data。

 And only then can the right miss occur and processor 2 bring it into the right state。

Or the modified state， excuse me。And finally， processor one can try to do a right。Now。

 why why are we doing this。It's to get this last arc in here because we want to transition over all the arcs in this diagram。

 So Proor 1 tries to do a right to this address。 It has it invalid。 Proster 2 has it in modified。

 and you'll see that it。Well， broadcasters intend to write。 And while it's doing this broadcast。

 it needs to move from modified to invalidate write back the data。 and then processor 1。🤧嗯。

Bringings in the background data and can do it right to that line。Okay。

 so a little bit of observation here。 So we've gone through the basic。MSsI protocol。But。

One of the big ideas here is that。If a line is in the modified state， in one cache。

There can only be one copy of that data。And this is the important invariant that allows the M S I Snoopy based invalidation protocol to work。

 So this allows the memory to stay coherent， because。There's only one copy of writeriable data。

Anywhere。And if you sort of work through this。 And I recommend you do work through this this case a little bit more carefully。

 you'll see that you might have multiple people in the shared state or multiple processors or multiple processor caches that can share data。

But thoses our only read link copies。 So they can read it。 They can read it。 They can read it。

 But when someone tries to do it right， you invalidate all of the shares。First。

Then you can do the right。 And if someone else tries to go read the data。

You need to transition from modified to shared。 Now， why do we do that。

 Why can't we leave someone in modified and someone else in shared？ Well。

 it's because by virtue of being in the modified state。

 that processor can continue to do further rights。So if you continue to do further rights。The cache。

 which brought it in and， let's say， the shared state， the read state。

 wouldn't be able to see those updates。 So we guarantee the invariant for this whole system is that if a line is in the modified state。

 then no other cache has a copy of the data。Or no other entity in the system has a copy of the data。

That's really important。Okay， so let's。Try to enhance this MI protocol。

Why do we want to enhance the M I protocol？ Well， as you might imagine。The MSI protocol， actually。

 you have to communicate across the bus relatively often。

 And we're gonna look at a couple different schemes that reduce the communication traffic across the bus。

 So you can either have a a bus that clocks at a slower speed or you could have more processors on this bus as you think about better ways to actually implement invalid based protocols。

😊，And the first one we're going to look at is called Mezzi and。

Sometimes people call this the Illinois protocol because this comes from University of Illinois and Jane Patel。

 his research group。 And this dates back to to 1984。 and there's actually。4 states。

 So instead of having three states in the， as we saw in the M I protocol。

 the insight here was if we're using two state bits to implement。Three states well。

We have a fourth state we could use， you know，2 to the two is 4。

 So we could do four states instead of three states for the same number of bits。Now， the question is。

 what states do you want to add， You know， just because you have four states doesn't mean your protocol is going to be better well。

We're going to have。An invalid state， a shared state。 Okay， those look similar as what we had before。

And now， we're going to have。A new state called the exclusive。State or exclusive， but unmodified。

And this is very similar to the modified。An exclusive state of the M state。 And， in fact。

 the insight here is we're going to take the state diagram from。M S I。And take the modified state。

 and split it。Into two states。M。And E or modified and exclusive。Now， why do we want to do this？ Well。

 what we're gonna see is that we're going to be able to reduce the communication on the bus In the case where a processor reads。

A piece of data。And no one else。Reads or writes that data。

 And then that same processor later goes to write that data。So if you look at MSI。

 when you go to do a read。You always brought it into the shared state。In Mezzi or MESI protocol。

 when you go to do a read， but no one else has a copy。

You're going to bring it into the exclusive state。 And this allows。You to， you。

 you're not allowed to do it right when it's in the exclusive state。

 but you can upgrade from exclusive to modified。Without having to communicate across the bus。

And this is an important difference than in the M I protocol， because here。In the M S I protocol。

 if you had something in the shared state and you want to go to a right to it。

 you need to broadcast your intent to write。 and everyone needs to have a snoop transaction occur on this。

But in the M E S I protocol， you don't need that extra work there。

 You know that you have the exclusive read and copy of the data。 So when you go to do a write。

 you can， you can just go do the right。 And we're gonna walk through this the state diagram now。

 And it's gonna look pretty similar to the M S I protocol。

 And all of the arcs in this diagram of are in relationship to processor 1。And like I said before。

 different processors can have the same cache line in different states。Okay。

 so let's take a look at this。 step 1。You ever read this？And's a readmiss。But note， I have。A little。

Word next to here。 So this is going from invalid on a readmiss。

 And we're gonna see that there's gonna be two arcs coming out of invalid on a readmiss。

 One that goes into the shared state。And one that's actually even going to the exclusive state。Now。

 what does this mean， Well， on a readmiss。Processor one here is going to shout out onto the bus。

 I want to do a read。On the bus， if someone responds back saying。I have a read。

Or I have a shared copy of that data。 Or I have a copy of that data， which is read only。

What's gonna happen is you're gonna transition to the shared state here because you don't want to invalidate the other cache's data。

And this is actually going be in contrast to if you try to do a read miss。

 but no one else has a copy right now。Because if no one else has a copy。

 we're actually going to transition straight to this exclusive state。But we'll get there in a second。

 So let's say some other processor tries to do a read。And you have it in the shared state。Well。

You just stay in the shared state。But you might need to respond back。Saying that， yes， you。

 you have a copy of that， that data。This is this is important so that the other processor knows whether to enter into the shared state or the exclusive state when they go to do a re this。

Okay， let's say。You're in the shared state， and you want to do a right to the， to this piece of data。

 Well， this looks the similar， exact same thing as what happens in the M I protocol。

You try to do the right。 You have to broadcast your intent to write。

 You have to give everyone a chance to either respond to say that they have a copy and they have to invalidate their copies and write it back to main memory。

 And then after that， you transition to the modified state。 and you now you can do your right。

And just like as before， if you're in the modified state。

 you can do a read or write to the line and you stay in the modified state。Okay， so finally。

 now we come to this interesting case that。You're going to do go do a readmiss。But。

Instead of the data being already shared in other caches or already being in somebody else's cache。

You do a readmiss， you're in invalid， you come into here， but the data is not shared anywhere。

 So the data is not shared。What does this mean， Well。

 you do the readmiss here and you can come into the exclusive state。The wise is good。 Well。

 you have the only readable copy in the system。And why this is useful is if you try to do a right。

 you don't have to go communicate on the bus anymore。 So you're in the exclusive state。

 Let's say processor  one tries to do a read。That's fine。 You stay here。Now。As before， sort of the。

 the exclusive state functionally looks very similar to the shared state。 You only have a read copy。

 readable copy of this data。 If you try to do it right， you need to do something。But。

This is the big difference here。When you go to do this right？You don't have to tell anybody about it。

As far as everyone else is concerned， you had an exclusive copy。 and now you have a modified copy。

 you just transition your state diagram。 You transition the state bits here to being in the modified state and do the right。

So you transition and then do the right。Now， I is good。 As I said。

 you don't have to communicate on the bus to do this transition versus if you're in the M I protocol where you only have shared。

 you need to first broadcast your intent to write， which takes bus bandwidth。 It also takes time。

 And then you can do the transition。 So this， this is trying to save us in this one case here。Okay。

 let's fill in the rest of the arcs here。 The rest of the arcs look somewhat similar。

 except when we sort of come out of the exclusive state。 And you'll see why。

The right mis case from invalid。This looks the same as MSI。 You take a right miss here。

 You're going to broadcast your intent to write， way for everyone to write back all their data and invalidate。

 And then you enter into the modified state。🤧。Now， here's the little bit more interesting arc here。

Let's say processoror 1 has the data in the exclusive state。

And then some other processor wants to do a read。Well。Prosctoror 1 needs to say， I。

 I have a copy of that。So the other processor can't enter into the exclusive state when it tries to do a read。

 Instead， it's going come in on this arc here with some shared data into the shared state。

 But at the same time。Prossor 1 needs to transition from being in the exclusive state to being in the shared state。

 And why is this， well。If someone other processor has it in the shared state and you were to stay in the exclusive state。

 you could potentially try to do a right to that data while the other person has a read only copy of that data and you'll get the data out of sync and you'll have stale values。

So you need， need to somehow fix that。 And how we fix that is when someone else tries to do a write。

 or excuse me， when else tries to do a read to the data， another processor tries to do a read。

 we transition from exclusive to shared and the other processor brings the data in as shared into their cache。

Okay， let's flush out the rest of the the arcs here。 This is similar to what we see before here。

 If you're in the shared state， some you see in other processors intend to write。

 go across the bus for the line that you have。You just have to invalidate it。 Thankly。

 you don't have to write anything back here because you are only have a re link copy。

Similar sort of thing here for the exclusive state。 You're in the exclusive state。

 You only have a re and copy。 You know， you will have the only copy in the system， though。

 But if some other processor tries to do it right， you need to do and validate。Okay。

 let' see we anything else。 Yes， we got a few more arcs。Modified。

 this looks similar to what we saw before。 If you're in the modified state。

 another processor tries to do a read。You transition to the shared state。Now。

 and you have to write back the data。 But what you'll notice here is you can't transition to the exclusive state in this case。

And， in fact， the only entry point into the exclusive state。

Is this readmiss case here when the data is not shared or in another cache already。So， when。

Another processor tries to do a read。 You have to write back the data。

 You transition to the shared state， But this is the same as what we did in the M I protocol。

A couple other things here。 Other processor tries to do a write。

 You'll see their broadcast of their intent to write。 If you're in the modified state。

 you need to clearly do it invalidate because only one cache can have dirty data。And so you see it。

 you write back in transition to the validation state。 And that's， that's， that's the。

 the sum of this protocol here now。What invariance do we have。

Well we said in the M S I protocol that you can only have。1。

Cash or one cache line for or one line only in the modified state in one cache at a time。

For a particular cache line。So is there something similar here。Well， yes。

 but it's a little bit different because we took the modified state and we split it into two。

Similar sort of invariant here， except now we say that only a given cache line can only be in either modified or exclusive in one cache at any given time。

 And this guarantees that we never have stale data。

 and guarantees that we have a useful cash coherence protocol。Okay。Next class， we're going to。

Expand this and talk about a few other cash coherence protocols。

One thing we're going to talk about is what they use in the original A M D Opron processors where they actually had more states。

 They added another state here called the O state。 and they went from Mezzi to Mo Ei。

And this own state is a optimization， which allows you to do cash to cash transfers and effectively track who has the most。

Up to date， written data versus having to always write everything out to main memory and do memory based out to main memory transfers。

 And we'll also talk a little bit about Meif， which is something look they use in some of the Intel processors where they will also split the shared state into another state beyond Mei。

So let's stop here for today。

![](img/46281c8e11173a46b15cf75f26c829e3_1.png)

![](img/46281c8e11173a46b15cf75f26c829e3_2.png)