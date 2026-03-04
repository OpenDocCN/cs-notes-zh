# 【计算机体系结构】普林斯顿—中英字幕 p107 106_06_implementation -BV1ii421D7WR_p107-

Okay， so。Now that we've gone through the beginning exercises of what。A directory based。

Distributed shared memory machine looks like。Let's talk about how to actually。

Figure out where the directory is。So you have an address。 and usually these systems。

 you're want to do this on the physical address basis。

 You're not gonna want to do this un virtual addresses。

 You're gonna want to have to run this all And this is because you're sharing data between lots of different systems。

 At this point， you're sort of out at the system bus。 These addresses are no longer virtual。

 You've got， you've gone through the translation look buffer or the M M U。

 and youve figured out what the physical address is。So。To figure out what。

The directory is or what's sometimes called the， the if in a distributed shared memory machine。

 the home node。Or it the， it's a number of。Which one of these directories to go to？

And there's a lot of different ways to do this。 But one of the more common ones is to just use some bits out of the address。

So you take the number of directories in the system。Take the log base two of that。

 And then you take that number of bits to be the home node number。So when you take a cache miss。

And it's not on your cache。 And you need to go figure out and do the load of that data， we'll say。

You send a message and the message I D and the destination of that message will actually be the home node。

And hopefully， your interconnect knows how to route the data to， to that directory。Now。

Taking the higher bits has some benefits。😡，Let's， let's take a look at that。

As we discussed already in， in a non uniform memory axis architecture。

 the O S can control the placement。I can do this， because。Based on these high order bits。

 you can actually determine what， which node in the system or which directory in the system you're going to。

 so you can actually basically allocate memory， allocate your stack， allocate your instruction space。

Based on。The physical address and the O S can manage that because the O S has absolute authority over where physical addresses get doed out to。

Downside。Is a directory or a home node？Can become a hotpot。So let's say all of a sudden。

 all of your processors in your system。Try to access one page of memory。 There's like a hot page。

 which has all the locks in the system。 And you're in some threaded program。

 and you have to go access those locks a lot。Well， if you look at that。

 that's all going to be down here。It's gonna to be sort of low order addresses。

 It might be from sort of here down， whatever your page sizes will say。

 So even if you're not having false sharing。Anything like that。

You typically would try to pack all the data onto a page or structure or something like that。

 And it's pretty hard to interleave it based on the very high order bits of your， of your address。

 And especially considering a program that has effectively no control of the high order bits of a physical address that's managed by the O S。

So if you do this， one node can become a hotspot because these were all alias to the same directory。

 So all， all the messaging traffic goes to one node。 And this almost starts to turn back into a bus。

 Now， we have one directory。All traffic has to go there。

 It's a little bit better because we don't necessarily need to invalidate all other locations。

But the directory and the bandwidth in the directory starts to become critical。Well。

 that's a tough one。The flip side is you can start to try to have。

The low order bits determine where your directory is。Or which home node you're using。

So you still have the， the offset within a cache line。 But then you have。The number。

 the bits of the physical address that determine what home node you're going to be the low order bits。

Well， this ends up being very well load balanced。Because you're going to choose different home nodes。

Effectively at random， depending on which cache line is。 So you， you know， two cache lines will。

 the same cache line will go to the same home node。Or the same directory。If you。

Have slightly different has lines。In which is pretty common because it's pretty hard to contend all on one cache line。

 There's just not that much data in one cache line。You'll spread across the different controllers。

 and you'll effectively have some good distribution。Flip side， though。

 is the O S loses placement ability here。So it's， it's tricky。

 It's a tricky trade off here to think about。 Some people have even built systems where it's configurable。

This gets a little more advanced。 And I touch on this in the last slide of of today's lecture， but。

You could think about having some systems where depending on the actual address and depending what comes out of your page table。

 maybe making different choices of how to do the mapping。But everyone has to agree on the mapping。

 which gets a little bit tricky because the directory has to agree on the mapping。

And all of the caches in the system have to agree on the mapping。Okay。

 so let's take a look at what is inside of a directory。 So we added this new hardware structure。

 And whenever we add a new hardware structure， I like。

 look at all the bits inside of the hardware structure。So we add a new hardware structure。

 and this hardware structure has an entry per cache line in this in that particular memory connected to the directory。

 So if you were look across the entire system， there will actually be an extra piece of data for every single cache line in the system。

And the naive approach for this will have it such that every single cash line the system。

 whether it's。Or not every single cache line every single memory line in the system。

So if you have 10 ter of memory in the system。The naive approach is going to have a directory entry for every single。

Block size， chunk of memory， Ca block size， chunk of memory in the system。

And these are held in big tables。 Typically， they're held in S Ram。

 You might try to put them in D Ram。And what do we have here， well。

The directory needs to know what state。The cache line is in。

 and we're going to look at three different states in our basic protocol here， shared。

 uncached and exclusive。So everything starts out as uncached。 It's out in main memory。

When it gets pulled into a cache is read only。The directory is going to say， okay， that's now shared。

If it gets pulled into a cache。Read， write。The directory is going to note that as exclusive。Now。

 if it's in shared or exclusive， we need to know。What node， of if it's exclusive。

 We need know uniquely what node has that so we can go message it when we need to go and validate it。

And if it's shared， we need to know the list of all possible places that it could be that we're gonna have to send messages to。

And this is better than having to broadcast or send messages to all the nodes in the system。

So we're going to have what's called a sharer list here。Which is a。

In a naive full map directory is going to have 1 B per core in the system or per cache in the system。

 And it's either just gonna to have one or a 0 in it。 So if it's a one， that means that。

Core has a share a redoling copy of the data。 And when some other cache goes to get it in writeriable and its cache。

 it's going to have to invalidate。Let's say this ones or the zero with cores。Cash。Now。If you're。

Exclusive。You're not going to have multiple bits set here。Because this basically means that that。

Core has a writeriable copy， and we can't have， if we want to keep the data coherent。

We won't want multiple writing。 We don't want multiple readable copies in the system。

So as we can see here， it's denoted only one，1 here。 And if it's uncached。

 we don't need to track anything there。 We just get don't cares。There's one other state here that I。

 I have and。It's pending。 And this usually actually turns into a couple substates。

There's different ways to track this at the directory。These transactions take multiple steps。

 You're gonna to send some data and start transitioning。

 Let's say you want to get a data data writeriable。 that the。

 the directory is gonna have to invalidate all the other copies。 It can't do this instantaneously。

 but we want to。Provide the appearance of animity or or that the operations are atomic in some way。

So。Typically， you'll actually have some substates that are share that are stored here。

 which are something like， oh， this cache line is currently transitioning from， I don't know。 U to E。

 Don't allow some other transaction to happen to it right now。It's just kind of a block that。

 Another way to do that。The one way is to store it actually in the directory。As a statepi。

 other way is you have some fully associative structure， a side structure。

 which just has all of the cache。Lines currently in flux。And。

The directory is smart enough to know that if some other request comes in for that line while it's in flux just to knack that request or negative and acknowledge that request and tell the other cash to retry。

So you can do it either way。But it gets pre complicatedated。

 We're gonna to talk about all the details of that。

 But we we'll talk with the high level transitions here assume that they are somehow atomic。So here。

 we're gonna look at how MI。Fits together with this。But you could actually think about doing this。

With Mezzi or some other protocol， It's a little bit simpler。 M I is a little bit simpler。

 So want to look at that。 Also， the benefit of something like a Mezzi protocol is lessened in a directory。

 because if you do。Pull something in in the exclusive state。Which is unmodified at the beginning。

And someone else wants to get a read only copy。 You're basically gonna have to send a message to that core。

 And that was inexpensive on a bus because it could just see the transaction going across and it would just snoop it and would demote from E to shared or some of that E to S。

 But now it actually turns into actual work。 The directory is gonna have to。Generate messages。

 and you have to wait for responses coming back from a cache， which had it in exclusiveusive， so。嗯。

Fu mezzies is a little bit less common when you start to go to these distributed shared memory protocols。

Okay， so this is a slide that we had before。This is MSI， on a bus。Well。

 things change a little bit when we go to。M S I for directory coherence。

 And before we go through this， I wanted to point out that there's actually two different state machines going on here。

There's one state machine， which is happening。Y。The cache controllers。 So actually in the cache。

Of a respective processor。And then there's a different state machine。

 which is happening in the directory。And you'll see they'll have different letters here。 This is S。

 U and E versus M， S and I。And， and we label these differently on purpose just to not。

 not get horribly confused。 And these state machines interact by setting messages between each other。

 And as messages flow between the directory and the cash。They will be。

Both going through different state transitions on this， on these two tables。Okay， so let's。

Let's jump into this。This is the same。Modified， shared and invalid states that we have。

In our bus based Snoopy MI protocol， we didn't change anything here。And the rules。

 the rules are the same。 If you're， you haven't modified。

You can do a right to this and not have to send any messages。If you have it shared。

 you can read the data and not have to contact anybody。

If you have it invalid and you want to do anything with it， you probably need to contact somebody。

Or you， you have to go contact the directory before we would have to send a transaction on the bus。

 Likewise， the transition from S to M and or M to S， we have to to communicate。 That was the same。

 So think about this as the same。State machine。Running。

 except running on a bus where before we would send transactions across the bus。 Now。

 we're gonna take those transactions and turn them into messages that we send to the directory and messages we receive from the directory that we have to respond to。

 So before， when we were snooping traffic across the bus。

 which caused us to transition different locations。 So here， other processor has intent to write。

 and we saw that across the bus。 So we had to transition ourselves to the invalid state。Now。

 we're actually going get a message from the directory controller。So let's， let's walk through this。

 But it's， it's always exactly the same as what we saw before。 So this is the， the cache date。

For particular line， for processor P1。We'll start with the entry points。We start off in invalid。

And let's say we want to get a read。A readable copy of this line。So were going to take a read miss。

So what we're gonna do is processor  one is actually gonna send a read miss message。

To the directory controller。And during that time， it does not have a readable copy。

 It cannot go and access the data。 It's， it's effectively still in the I state。

Sometimes people actually have sort of a pending state here。

 depending on how you go to implement this。 It depends if you have a side structure or something like a mis status handling register or you'll track that in。

 or you can actually track it in the the cache state itself。So you have a read miss？You send。

The read mis message。 And you're waiting。For response。

 And this response is going to have the data that you need。And。

That's going to be a synchronization point saying， okay， you're， you're safe to transition to S。Okay。

 that seems pretty simple。Similar sort of thing here for a right miss。

 If we're in the invalid state and we do a right。We're going to send a right mis request to the directory controller。

It's gonna do something。 And it may， we have to be waiting for a while here because it might have to go and validate all the other lines in the system。

And then it gets a response。 once it gets a response。

 we have the data and we can transition to the modified state。So as we said。

 these arcs are pretty easy。😡，We can read by P1， and nothing changes。

 or we can read or write if we're in the M state by P1。

 and we don't have to communicate with anybody。But now we have a few different messages coming in here。

If we're in the shared state。We have to be responsive to an invalidation message。

Which is a little bit different than a bus snoop。 So before we saw another processor trying to write。

That's what transitioned us to I。 But now the directory controller sends us a message。

Which says invalidate this line。 And that will transition us to I here。Note。

There will probably be a reply。 We will probably have to send a reply。

Because the directory controller wants to know。When all of the cash lines in the system have been invalidated。

 it might take a variable amount time and sending messages。

 So it wants to wait for replies to come back。 So we're gonna have to send a reply。

So this arc here is similar。Except。We need to write back data because we had modified data。

We had writeriable data。 We get an invalid message from the directory controller。

So we need to write back the data and then reply afterwards。Similar similar sort of idea here。Okay。

 said leaves two arcs left here in the middle。We're in shared。

And we want to do a right to that cash line。 So our cash we have in the shared state。

 We want to do a right to it。嗯。Before we can actually do a right， we have to send a message to the。

Directory saying。I'm doing a right miss here。 I want to get this data writeritable。

And we have to wait for a reply before we transition here。

Because we have to wait for the directory controller to go communicate with all the other caches。

So that they don't have read in copies and we can have a writeriable copy。

So it's going to invalidate all the other readable copies in the meantime。And then finally。

 we have an edge coming this way。Which is。From modified down to shared。

And this is a little bit different。 Well， it's the same idea here。

 Another processor is trying to do a read。So we have it in the modified state。

 and another processor tries to do a read。So we receive a read miss message。

We don't need to invalidate the data。But we need to write back the data because we have the most up to date copy because we had it modified。

 So we're going to write back the data。 and that's going to be a response。

 And then we're gonna transition to the shared state。 We can keep a read copy of this， because。

The other core is only having a readable copy of it also。Okay。

 so that's the any questions about that so far。Okay， so。

Two interesting arcs that we're going to add in here。😡，Is。This one。 and this one。

Which we didn't have in our base MSI protocol。And， you know， you may not need these。

But what these correspond to is。If our cache has the data。In it。

And then because of let's say a conflict miss or a capacity miss， it gets bumped out。

It might be a good idea to go update the directory。

And tell the directory that in the future of some other cache wants to go get that data。

 they doesn't need to go contact you again。So if it's in the modified state， we。

 we can write back the data because we have dirty data。 We write back that as the directory。

And then we notified the directory saying， we don't have a copy of this anymore。

 You can transition to having it uncached。Likewise， here， if we have a read only copy。

 we may or may not want to do this。But we， if there's， you know， extra bandwidth on the。

 on the interconnect， we might want to send a message when we do an invalidation here。

And this is not an invalid because of an invalid message， but this is an invalid because。

It just gets bumped out of the cache。We may want to notify the directory saying。

 please remove us from the sharer list。And if the share list is already empty。

 the directory might change the cache line from shared to being uncched completely。嗯。

But I do want to point out these are not strictly necessary。😡。

The reason they're not strictly necessary is。If we build the cache controller system such that if you're in the invalid state for a particular cache line and you get some message coming in that would have been。

 let's say， this message or that message or some other arc。We can just reply back saying， yeah。

 we don't have it anymore。 We're invalid。 You know， we， we don't really care about that。

 that transition。So if you're， youre here， the only message that's going to come really to you is。

And validation message that would just take you to the state anyway。

So we can just ignore the message or just reply the same as we would to the normal invalid message。

Okay， so directory。State transition。Looks a little different here。We have。Uncached。

 shared and exclusive。And as we said， shared means there could be multiple redoling copies in the system。

 Exclusive means there's only one cache in the system with that data。

 What's interesting here is if you were to actually have a。Mme S I protocol running。

That would not change the protocol running in the directory。Because exclusive here。

Is effectively the same， same state。With respect to how the directory sees the line。

 we't have to do anything different。Okay， so let's walk through a few transitions here of the state of the cache line in the directory。

 And this is not in the cache。Let's start off uncached。

And let's say we get a message which is a readmiss from processor P。Well， we should transition to S。

 Now， we should give it a readable copy， and we should reply with the actual data。And。

We should put P on the sharer list。So do we know that if someone else needs to go invalidate that line。

 we need to go contact。P。Now that we're in the shared state。

 let's say there's other read misses from other Ps， other processors here。Well。

 we're going to give it up the data。And we're going to add it to the share list。

 we' would take sharers and add to it。The processor， the share list is just going to grow。嗯。Okay。

 let's， let's start here and go the other way。 We're in un。Uncached， and all of a sudden。

We get a ripeness from processor P。 Well， we give it the data。

 and the sharer list or the owner list is going to get P uniquely onto it。

And we're gonna give it in the exclusive state because we were unced before。

 We don't have to contact anybody else。嗯。Let's look at this arc here before we go to these。

So this is a little bit different， quite bit different than what we had in these slides。

Because the students's been different， but。In this state here， we know， let's say， processor P 0。Has。

The data。Exclusively。But all of a sudden， a different processor。

's say processor 2 goes to access the data。Well， we already have the data in the exclusive state。

So we're to stay in the exclusive state because some other cache is going want to get it exclusive。

 but it's a different cache。So what has to happen here is we need to go and。The data out of P 0。

P0 is going to write back the data。It's going to transition to the invalid state。嗯。

We need to then provide the data to the new processor P2 will say and add that P2 to the share list。

So we can， we can transition into this state。 And then finally。

 let's look at the edges between these two points。 actually， let's go this way first。

If you have data that gets written back。So this is that arc， which I said。

 is similar to the arc here， which is optional。Let's say you have data。It gets written back here。

Actually， this， this arc may not be optional。 Let's think about that for a second。

This arc may not be optional。嗯。No， it's still optional because you can just。

KNnack the message effectively and， and tell it that it's in main memory。 Okay。

 so let's say you're here。 and you see a data right back happening。 So a message gets sent to you。

 which is the equivalent of this arc here。 The data was writeriable。 It was exclusive in some cache。

 And it's no longer writeable。 It's probably a good idea to go contact the directory。

Write back the data and clear the sharer list。So the share list is just empty。

 So it knows that no one has a copy of it at that point。Okay， few other fun edges here。 Okay。

 we're in the shared state。So we have multiple redoling copies， and one cache comes along and says。

 oh， I need to do a rightness message。I need to get it righttable。Well。

 now we actually have to go through a pretty long process。

 We're going walk through the entire sharer list and send messages to all the sharers in the share list saying。

 invalidate this copy and tell me when you're done。

We're going to collect all the responses at the directory。 And once all the responses have come back。

 we know no one else has readable copy。We can give the data value to the。Requester。

And add it to the sharer or owner list。Okay， last dark here is from E to S， is orange dark。

And that happens if we have a particular line as writeriable in one cache。

 and another cache wants to go read it now。We'll send a readmiss。

 The other cache is going to downgrade from E to S， or excuse me， from M to S。In its local cache。

 But the directory is going transition from E to S here。

And we have to go get the most up to date data from the node。

 So we're gonna send a fetch and a fetch request to the node that had it before an exclusive。

Once we get the up to most up to date data， we can forward that to the new reader and everyone。 And。

 and we add that processor to the shareer list。Okay， so questions about that one so far。These。

 do start to get a little complicated because you have multiple state machines interacting。Okay。

 so we're gonna speed up a little bit here。 I included this chart from your book just to give you an example of we went through very quickly here all the different messages。

And this chart here sums up all the different message types。

 And from who they could go from and who they could go to。 And this is， this is in your textbook。

 And sometimes messages need to communicate addresses。 Sometimes they need to communicate data。

Sometimes they need to communicate which node the message is coming from。To add it to the share list。

But I'm not going go through this into great detail。

 One thing I did want to say is these message types here do not include。As and acts。So。

When you go to request something， there's replies that come back。

These replies after that's not drawn in this。Diagram， we， we see data value reply， but that's not。

 that's just actual data。 There's not like a response coming back from the share actinging the。

 the share or actinging the invalidator or something like that。

Another type of message that's pretty common。That is not drawing here is a negative。Acknowledgement。

So it's pretty common that if you have a cache line that is being transitioned。

 there's an app pending state at the directory and get a request coming in。You might need just。

 to tell that cash retry later。 I can't handle this case right now。



![](img/2d2905f0e864c9ab402bd0270fa59892_1.png)

![](img/2d2905f0e864c9ab402bd0270fa59892_2.png)