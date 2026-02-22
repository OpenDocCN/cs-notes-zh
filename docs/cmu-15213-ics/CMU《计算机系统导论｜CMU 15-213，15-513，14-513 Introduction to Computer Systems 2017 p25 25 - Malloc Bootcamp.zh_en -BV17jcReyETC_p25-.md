# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p25 25 - Malloc Bootcamp.zh_en -BV17jcReyETC_p25-

![](img/a37b95b59973c2e797175f42d0cb3a81_0.png)

Okay， we're ready to go All right Hey everyone thanks for coming we'll be going over Mallala today hopefully you guys have already started and have a good understanding of it and we'll skip over some of the basics because we expect you to have read lectures。

 was selects and be familiar with it。😊。

![](img/a37b95b59973c2e797175f42d0cb3a81_2.png)

So this agenda for today will be going over some conceptual stuff。 afterwards。

 we'll be going over some hints about what you can do to improve your score and GDP。 Of course。

 Dbugy will be a huge part of this assignment。 So it's critical that you guys know how to use GDP。

Yeah， so dynamic memory。Oh， okay。So dynamic memory。

 so that's what Malik I is all about When do we use it， when we don't know a compile time。

 how much memory we need， and then he's going to be dealing with Malik， Calc， reallocate free。😊。

And so you should all know what that means and what those function calls do。

 those are the ones that you're going to be implementing in MalloL and then we have M break。

 a payload， what fragmentation is， and then we're going to talk about splitting and coalescing a bit。

So in it， if you've looked at MMm baseline。That's the first function that you see M a minute it。

 so we have a prologue footer and epilogue header at the first。

And then so a couple things to keep in mind， your payload has to be 16 by the line。But it doesn't so。

So the block size total block has to be 16 by a aligned。

 but your payload doesn't have to be a multiple of 16。So you can have a payload of like。

 I don't know， 20 if you like。呃。So things are maled in between the prologue and the epilogue right so after you extend your heap you should have a data structure that looks something like this with a prologue footter。

 your heap， and then the epilogue header。Cool。So assuming an implicit list implementation。

 which you guys talked about in lecture in detail， there's one implemented in MM baseline。

when we need more memory， when we're out if our heap is full， or we can't fit in a huge size block。

 then we need to extend our heap。So MAma brake is the function that we're going to use as brake will allocate space for the number of bitetes you specify and then return the pointer to the first bitete。

So。Extend heap if you look into the code that we give you there's a chunk size that we initialize to like some constant and you can play with that chunk size however you like so here you want to consider what is the chunk size right How much do you want to extend your he by so remember that S break is a decently expensive operation so you don't want to get like I don't know 20 bytes of extend heap and like keep calling that again again。

So there are some trade offs that you have to make here。

 can anyone list something that they think should be important？No。

So can you extend as much as you want， Let's say， hey， the user is going to use up that data anyway。

 can I extend3 gigytes worth of heat。他一。一。So no， you need to get a good ratio of the space available。

You say down what1 feet2 plus the maximum。Exactly， so this is a risk that you're taking right So everything that you use should eventually end up everything that you allocate should eventually end up to the user in a perfect allocator。

 But if you ask for a lot more memory than you actually end up giving out， well。

 then your utility score is going to be very， very low。So how do you determine this number？

Is there any mathematical way to determine this？Okay。Who says yes。

 there is some set formula that you can use。Well， then does that mean everyone else's no？Yeah。

 pretty much if you find a formula， please tell me， but other than that just try random numbers。

 see whatll gets you your best score and then submit with that。

And everyone won't have the same random numbers， so don't try to take a random number from your friend and expect the same increase or same score。

Yeah， but it's not that hard to play with， though， it's like do what makes sense。So。

Let's talk about explicit list， which is what you guys should be implementing for the checkpoint。

So instead of maintaining a list of all blocks like we do in an implicit list， we're going to。

Maintain a list of free blocks。So。So we need some way of storing like forward and backward pointers next in preve。

 so we're going to implement this as like a doubly linked to list and like figure out what's the next free block that I can now allocate。

So。What's like the obvious advantage of using this implementation？Instead of storing all blocks。

 if I just store free blocks， what's automatically， what does that give me？Yeah。

You have to skip over looking at all blocks the all the。I。Yeah。

 so like the point is you have a much better throughput right。

 I don't have to go through pointless allocated blocks， I say on that time。So。

You still need to store your size with header and footer like we do in implicit list。

 it's just now that I have a next and brief， I don't need to look at a block and say oh。

 that's allocated so I have to move on。Right， so。Now that we have an explicit list and we need to allocate something right。

 what if whats we need to care about like the size of our allocation right so。

When do we split a block versus when do we just allocate the entire block？

The answer is kind of on the slide。Yeah。就是。Good for it。

So we would split unless the space wouldn't be large to create another block which Yeah。

 exactly So if you have enough space to actually allocate a new block then you can split your block and then leave the rest for as a three block right。

 but if this face is smaller than my minimum block size。

 then I can't make anything out of that memory I'm going to just allocate the charging。

Does that make sense？Cool， I see someone nodding。 That's good。Okay， so。

Coolescing with explicit lists so keep in mind coalescing more or less works the same way in explicit list as it does and implicit。

 but keep in mind to look at the actual physical blocks before and after your free block。

So you don't want to look at next in pre because next and pre are not physically adjacent right Next can point to like five blocks ahead or five blocks behind even in physical memory so you still have four cases if okay so my so looking here that's my blocks three。

 I can have both allocated one allocated one free， vice versa and then both three。In all cases。

 you can choose to coalesce。At the moment or you can defer coalescing， which some people do。

 but that's up to you So coalescing looking at if if you are in the first case， right。

 you don't need to coalesce anything because the block before you is allocated block after you is allocated。

 you can't really do anything。So now you're in the case where。

One of the blocks before you is free and one of the ones after you is allocated。

So you can just combine the two blocks by transferring。

By changing your size right so here in your header instead of M1。

 I would have n plus M1 and then in my footer I would have the same size and they're both three now with indicated by the zero bit。

Cool questions here。Okay。So。And that's all you need to do with when you have two free blocks， both。

Right above and right below， then you can combine all three blocks into one giant free block and now you have n plus M plus M1 plus M2 as your size and your header and footer。

 you set your allocation bits to say free， so zero in this case。

And you change your next in previous pointers。 So remember to like。Change it accordingly。

 so in this case。You want to look at what the next pointer for that block is and then set that to be your next。

Next pointer here， and then for the previous pointer。

 you're going to look at the previous pointer of the first block and then set that to previous here。

Because if I choose this next， then I'm going to go here， which is。

Getting me know where in the same block。O。Yeah， so make sure to coalesce looking at the block right above and right below。

 not next in brief。Okay， design considerations。So。Oh， sure I can talk about it。

So how do you find a free block right even if we have next so now we have an explicit list with just pointers right so we can still use our three fit policies we can talk about first fit。

 next fit versus best fit versus something that we call like a good enough fit so。So okay。

 first of all。What's the advantage of like using first bit in terms of U tool and through boot？Yeah。

It's fast， right， I just picked the first one and that's I don't have to look at anymore。

 So that improves it throughput。 But what does it not do， yeah。Yeah。

 so you're going to have more fragmentation right， because the first fit may not be the block that's that fits perfectly。

 right so。So that's the opposite is exactly best fit， right。

 you keep looking until you get the one that fits perfectly。

 but that means that you have to look through the entire free blocklist。

So somewhere in between like first and best is what we call good enough。

And so this is also something that you're going to have to tweak， try a number， submit。

 and see what score you get。Because so here for a good enough fit， you can try like， oh， you know。

 a mixed version of a first and a best fit。Because it's neither super bad for throughput nor super bad for utilization。

 It's somewhere in the middle。 and that's what we're looking for。嗯。裤。😔，So yeah。

 and then you can consider your free block ordering。 So if I create a new fully block。

 do I want to where do I want to insert it So you have live0，54 dress ordered。

Orderings that we talk about in lecture slides。 Also， you can take a look at that if you're confused。

 basically， you want to decide。Where am I going to insert my new free block。

 Is it going to be at the front of the list， Is it going to be at the end and so on and so forth。

 Yeah， question next。え。对对对。That's why I answer to you。Empirically。

 you may have different results depending on the allocations that happen。

 I don't think I've really seen anyone implement the next bit。The good enough is really good。

 correct？You might get lucky， I think that's all can happen。Other questions。 Okay， so yeah。

 free block ordering and then one more where can talk more about the。啊，是so。So。

 so you know what first fit is and you know what best fit is， right？

 So we're looking for like a good enough fit where you can。😊，Do some something in the middle。

 So neither look at the first block nor look at the best block。

 but maybe look at the best block after certain number of searches。

So that number you can customize depending on your score。Other questions。Yeah。都是 the。そこは。谁。

Virtual memory， I think and dynamic allocations that's chapter8。

 Yeah basically all the sections listed next to the lectures。

TheThe lecture slides should have like the chapter over there。Be careful about the code though。

 because the textbook contains code that's different from what we give you in MMM baseline。

 so if you're looking for just code， that suggest you look at the baseline code that we give you first。

Other questions？Okay。Yeah， when to Coce， so this is also kind of a decision that you can make。

 whether to coalesce automatically when you're free or while you're searching。

I haven't actually seen many implementations with the searching。

 but you may find an optimization there， if you'd like。呃。And then how much memory to request right。

 so we talked about this at the very beginning， what your chunk sizes might change。

 how much throughput or utility you get。Okay。Other questions。Yeah。So。Allright。

 so so that was a lot of hints right and there's a lot of design decisions that you have to make for Macl。

 basically for the checkpoint， we don't expect you to make too many of those design decisions yet。

 So what I should tell you is that when you're looking at the implementing your checkpoint。

 We aren't expecting you to do too many complex advanced features。 In fact， there's a very。

Strict subset of these features that we are talking about here that we are looking for for the checkpoint。

 However， for the final final submission， something that you want to keep in mind as you write your code is that you do want to increase your utilization a lot more and maintain the same high level of throughput that you had on the checkpoint。

 So the jump in utilization on the final checkpoint is very large。

 the jump in throughput like the how much higher the bar gets raised is not as much as the increase in utilization。

 So the final submission is much more focused on improving your utilization。

 the checkpoint is like just mostly improving the throughput of the baseline that we give you。

 although you do have to improve utilization somewhat as well。😊。

When you are reducing the external fragmentation， right？

You are going to need to do something that's better than just first fit， right。

 Because first fit is pretty bad for utilization。 So as we just discussed。

 what you're probably going to end up doing is close to best fit。 But again。

 best fits probably not what you're going want to do you're going to want to combine that better fit algorithm。

 on the other hand， with something that lets you run a more complicated algorithm。

 So using this like what's it called good enough fit is probably fine， right。

 like in terms of fit algorithm， you're going to find a good balance But one of the nice things about having a algorithm that you can tweak in terms of trading off performance and utilization。

 is that if you improve your data structure in some way that lets you。😊。

Traverse your like lists faster in some way we can talk about in a second。

 Then that means that you can increase the number of locks that you look at in your like good enough fit。

 And then all of a sudden， you actually got better utilization。

 You managed to trade off some of that throughput for utilization。

 And that's the kind of thing that we're looking for。

 That's the kind of empirical testing you're gonna to have to do for the final submission。

 as well as the checkpoint， in some sense。On the other hand。

 when you want it another way to reduce that fragmentation and increase utilization is by reducing internal fragmentation and to do that。

 you're going to need to reduce the actual data structure overhead itself。 In other words。

 the free blocks which are the primary data structure in Malcl because we want to try and reduce that as much as we can。

 they are going to need to be as small as you can make them and that kind of seems hard at first until we take a look at some other things that we can take advantage of inside Maclo。

 so we're going to discuss that now。😊，The first optimization the more advanced optimization that we want to talk about is segregated lists。

What a segregated list is。Is basically a generalization of what explicit list to us。

So what was an explicit list， you track all of your free blocks in a list。

That seems pretty straightforward， right， And so like all throughout your heap。

 all of those free blocks that are currently existing inside your heap are part of this free list。

However。That sort of leads rise to this issue where if you wanted to allocate something of size。

 I don't know，1024。 but all of the free blocks in your heap were like size 8。

 And then like after 100 of those size 8 blocks， you finally had a block up that's big enough to fit 1024。

 When you wanted to allocate that big block， you had to traverse all the little tiny blocks until you get to the big block。

 right。What we could do is instead， we say， how about we have more than one linked list。

 How about we have like。Some like N linked lists where like N is some number that you get to decide。

 So here's another one of those things you get to pick for yourself。

 where like the first linked list is every all blocks between size 0 and 32。

 And then the next one is size 32 to 64。 And then the next one is 64 to 256。 Again。

 these are numbers you get to pick。 right， But you can start to get the idea of each linked list containing a different class of block sizes。

😊，And then when you have a block of a certain size， let's say you want a block of size 1024。

 Then you only look in the linked list that could possibly contain blocks of size 1024。

 So you're not going to look at the linked lists of smaller size。On the other hand。

 you actually might want to look at the link list of bigger size， right。

 Like if you don't have something in the list， that's a size class that happens to be like 512 to 2048。

 then you might look at the link list with the size 2048 and above。Right。

 so these are just example numbers。 I'm just making them up of the spot。

 So you're gonna have to come up with these numbers yourself based on the empirical testing。

 You probably want to start with powers of two because it's kind of nice。

 You probably want to come up with like a reasonable number of size class。

 you only have 128 bys of not sorry not stack space of a globally available space to keep these pointers to to these linked lists。

 But other than that， like the implementation wise， These are just linked lists。

 You just have more than one of them。 you have several of them。 Yes question you。😊，嗯。In some sense。

 there is an unavoidable amount of wasting that has to happen。 If I ask you for a mallic of size 23。

 that's not going to be a multiple。 23 is clearly not a multiple 16。

 So I have no choice but to waste like some part of that block there。

But there are things we can do to make it so that we waste less space。

 and that's the next thing we're going to talk about。A key question though， is。

 is this going to help you reduce the amount of space you waste inside of a block？No。

 I see some headhi。 No， And this is definitely not going to affect the internal fragmentation。 right。

 This does not change in any sort of in any way， the， the like internal contents of a block。

 This is just changing how you keep track of these three blocks。And as a result。

 what we expect here is maybe your utilization goes up by some amount。

 although we can argue about how much it is， it probably not me that much if you think about if you think about how this works。

 you might see why， but on the other hand， your throughput may go up quite a lot once you implement segregated lists。

 Yes question。Probably not。 So you probably will not need this on the checkpoint， right so。Yeah。

 don't worry about it for now， but it is something you want to keep in mind for later so the number of。

Can I have a lot input， I just why is that going to call。Yeah， so like you could have a lot of them。

 but the question is you need to like for linked lists， right。

 you need to track where the beginning of the linked list is right in general。

 The problem is if you don't know where， if you， if you have too many of these。

 you need to keep track of a lot of like the heads of the linked list。

But you only have 128 bytes of global variables。So， yes， you could have a lot of them。

 but you might overrun that。 Now， there is a solution to that。

 Like if you want to have a ridiculous number of segregated lists。

 What you could do is you could say， like at the very beginning of my heap。

 I just use some of that space to store all of my segregated list pointers。

But maybe that's not a great idea and the fact that we only give you this much global variable space should be a hint that we're not looking for that many segregated lists。

Okay。So a brief break to talk about some。More high level concerns that aren't actually exactly related to Mount Club。

嗯。😊，For when you want to go ahead and implement segregate list or even when you want to go ahead and implement these explicit lists。

 and this is， in some sense， a special case of segregated list。

You need to implement these list operations， right。

 You're going to need to be able to insert things into lists。

 You're going to need to be able to remove things from lists。Later on。

 when you have more than one list， you need to be able to decide which size class of some block of arbitrary size needs to go into。

It would be very， very painful to copy and paste code more than once just to implement like for every single one of these linked lists。

 you copy and paste some functions， or maybe like you like have more than one place in your code where you need to insert something。

 And so it would be kind of weird to have to like copy and paste like 10 or 15 lines of linked list manipulation code like into these into these functions that have to insert things into these list or remove things from the list。

So this is like a great case where you might want to write a function for inserting something into a linked list and writing that function early on。

 And by early on， I mean， like now for the checkpoint。

 even though you don't need more than one list right now， it's still a good idea， right。

 because you're going to eventually have to have more than one list anyway。

 So generalizing your function so that they can be used later。😊，Is not such a hard thing to do。

 but it will save you a lot of time later。 Another thing to think about is like deciding these。

 these these size classes， like a very common solution we see is like 14 if statements all after another。

 Like， if the size is less than this， return this， if the size is less than something little bigger than the last one。

 Re this。 And like， okay， so like that that's like gets really， you know， annoying really。

 really quickly， right。😊，A better solution might be to put like a bunch of constants in your global。

 as a global variable or something。 And by the way， if they're constants。

 we don't care about how many constants you have。 So you can actually have this like constant array of sizes。

 and we won't count it towards your global variable limit。And then you just loop through this array。

 right， Like you say you know it for each size in the array。

 iss it less than the size And if it is then you return that index or something along those lines。

 right， So you can probably imagine how that code would look。 Don't write the 14 of statements。

 Just don't do it， please okay。a0 a modularity。 Yeah， you'll just get a zero。 Like no， like。

 actually， you'll just get a zero modularity。 That's the end of the line。 like， don't do it。

One last thing。Beyond just like linked list operations。

 there are many cases inside Mallila and inside future labs where you might be tempted to just copy and paste your code。

 right， because it's like， oh， like， I need to do this thing here。 and I need to do this thing here。

 I'll just copy and paste it。Whenever you get the urge to copy and paste code。

Cut and paste the code into a function and then implement the function that does it and then call the function。

 It's not that much harder。 Right Like， okay， you spend like maybe two minutes like writing the function。

 and then you put the function calls in the right place。 But then later on。

 when you come back and look at this code and this gets into the next slide。

 You come back and look at this code six hours later or maybe six days later or something like that？

 And you just are staring at it And you're like， why in the world do I do this here。

 And like maybe I'd made a small tweak here， I change like a variable name。

 Why does it even like why， what's going on here。 You'll be very confused， It's kind of painful。

 Like you waste some time， Maybe there's a like subtle bug in one of the cases that isn't in the other one。

 So you fix one of them。 But then there's another bug like， it just gets out of hand really quickly。

 So don't do that。😊，What you should focus on is making your code modular from the beginning。

 This is a mistake that we see， like all the time。 Like if you write your code in a way that is not modular in the beginning。

 you can't just like magically add modularity in later without spending hours and hours。

 basically restructuring your entire program。The modularity from the start lets you have abstractions from the start。

 which means that your like mental workload is a lot lower。

 and it lets you spend more time thinking about the actual problems at hand。

 the problems that we want you to think about for Malla and for future labs。

I want to put this copy out there now。 Labs in this course really are not meant to be done in one sitting。

 You should not like put it off to the last minute。

 I hope most people in this room have learned that by now。 but like we cannot stress this enough。

 We see this too often like we we want to really make sure everybody's aware that you should take the time and spread it out throughout the course of the week。

 at the end of the day， you might still end up spending the same amount of time on it。

 But the amount of stress that it causes you will be far lower if you give yourself time to take breaks between sitting down and working on this lab。

 We know Malick lab has a reputation。 We know it's like apparently the hardest lab in 213， right。

 but like。It doesn't have to be this way。 Like you can you can make it so that it's easier for you to work on it。

 make it easier so that it's for you know your brain to comprehend what's going on here。

 It makes it easier for you to learn what's actually going on underneath the hood。

 And that's really what's important here， Right， So leave that time for rest， leave that time know。

 your brain is sort of like have an aha moment。 And then like， you know。

 you're doing something completely unrelated。 But then you realize， oh， that that's how you do that。

 That's how I like insert things into my explicit list。

 That's how I do this coalescing in this weird case。😊，Okay。Enough preaching about modularity。

 Let's go back to actual malla stuff。So。If we have this new idea of segregated lists。

 we now have to be a little more careful about what happens when you coalesce two blocks。

So what happens is when you coalesce two blocks is that you change the size of the resulting block。

 right so you had two small blocks and you put them together and now they're a big block。

The coalesced block will therefore probably not be in the same size class。

 It might be in the same size class as the people that you removed， but maybe not。

So in order to maintain this whole invariant about your segregated lists。

That they contain size sizes of the， you know， or blocks of the right size， something like that。

 You will need to be able to remove those old blocks from those old lists and insert them into the new lists as appropriate。

And again， you have this whole question of like insertion policy， right？So again。

 you have these four cases， like maybe sometimes those two free blocks on either side， when you。

 you know， mush them together like into a bigger block。

 then now you need to remove those free blocks from their appropriate list and add them correctly。

So just be careful， this is one of those like easy places to get tripped up。

 but it's something that hopefully you'll be able to catch thanks to some devvogging techniques that we'll talk about in a second。

Okay， one last optimization。 So this is another class of optimizations separate from segregate list and explicit list like we've been talking about。

 So this next one is called。The footerless optimization。

And what happens is you take an allocated block and you say， actually。

 I don't really need footers and allocated blocks。So you just don't have one。Free blocks。

 on the other hand， still have footers。Why do we need footers in the first place， Well。

 when we are coalescing blocks， let's， I'm going go back to this slide for a second。

 If I am coalescing the block。Here。I have to have some way to know how big this block is right and the heap right before me。

 and the way I do this， if you look at the baseline code， it actually does this。

It looks at the footer of this block and says， oh， actually， that's how big that block was。

 So I can just go back and say that's the beginning of the block。

 and I can coalesce it and be on my merry way。If you are， if the block before you isn't free。

 do you need that size information about how big the previous block was。No， I see some note。's。

 that's exactly correct。 You do not need to know how big the block is before you if the block before you is allocated。

 because you're never going to coalesce with it if it's allocated。So， with that in mind。

We want you to think about for a second。How could you have a way of knowing whether or not the previous block is allocated without having a footer available to look at。

 which contains the information about the previous block being allocated？Right。

So hit on the side of how you might want to do this， yes。食べて在。Exactly， so let's say we're coalescing。

 I guess this is a bad example。 But imagine we were coalescing this block and it was free。😊。

Because this block before it is free。 we would have an extra bit in the header of this block that we're looking at right now that tells us。

 hey， the one before you is free so therefore you can go and get its size from the footer。

 On the other hand， if we go it over here and it tells us， hey， the block before you is allocated。

 Then that tells us we should not go and look at its footer。 In fact， we should。

 we don't need to look at its footer because we don't need to coalesce with it in the first place。😊。

So that's at the heart of the flless optimization。What it lets you do is it gives you an extra 8 by in the payload。

 And that doesn't sound like very much， right， okay，8 like， okay。

 I'm mallacing things that are size 256。 What's an extra 8 bys gonna give me。

But if you are imagining like you are malacing like link list nodes and each one is only 8 bys。

 then another 8 byte on top of the 8 Bte that you are allocating is a lot， right。

 It actually reduces your utilization by 50% or more， right。

 depending on how many more things you have to have inside each each block。

 So this is actually a pretty significant optimization。

 It's not something you'll need to do for for checkpoint。 Yeah， no。

 I don't think you'll need to do this for checkpoint。 if you have time great。

 you can get started on it。 But again， like it's something that you will definitely need to do for the final submission if you are looking to get that utilization score up。

 which is what the final final submission is all about。😊，Okay。So again。

 we're gonna talk about coalescing。 Basically， footer list complicates your coalescent code， right。

 You're going to need to check more， like have more conditions in there about like， you know。

 when do I coalesce the block before me， Thankly， the block after you doesn't actually change。

 So that's kind of nice。😊，So if it's footer less， then you're going to obtain info from the footer of。

I sorry， if it's footerless and the block before you is free。

 you're gonna obtain different from that footer。 I guess we don't have any extra cases there。

 but if it's allocated， you just don't look at the footer because you don't need to coalesce it。

You are going to need to maintain that information about whether or not the previous block of a current block is allocated or not somewhere in your code。

 If you think about when the state of a block changes from free to allocated and back from allocated down to free。

You can probably think about how you might maintain that invariant in some sense。

 and those locations will be very crucial in implementing your foot list。O。Alright。

 so decreasing the minimum block size。 This is the sort of last optimization that we are going to talk about here。

 right， I think， and then it's probably the last optimization you're going to do。So。

In order to reduce the internal fragmentation even more。What we could say is we're like our。

 our minimum block size right now is 32 B。 But if I ask for like a mallic of like 2 or 4。

 I still need to give people blocks of 32 B。 And that's really bad for my utilization。 Right。

 In fact， you'll see some of the traces。 They ask you for。

They ask you to mallic nodes that are like such small amounts that your utilization score。

 whatever you try to do for like， you know， finding the best fit and doing whatever。

 It's still going to be really， really low just because you have to waste a lot of space per block。

 right， That's this internal fragmentation that we're talking about。So。

If we want to reduce the size of our blocks， the minimum block size。

 that means we have to sacrifice some of this payload space inside of our free blocks， right？

What we were using this payload space inside our free blocks for was to source some like linkedless pointers。

 right， So if we go back and look at what a free block looks like over here。

 there's like a next in the previous here。 And you can imagine if I made this even smaller， Like。

 I couldn't fit the next in the previous pointer anymore。 And so I'm kind of out of luck。😊。

But if I'm very clever about how I track these like smaller blocks。

 then I can actually completely get rid of some of the fields inside of these smaller blocks。

 you can think about which fields might be nice to get rid of。

 If we get rid of one of the pointer fields， then we have this problem of like O of N removals。

 right， Like as you probably know， like， if you have a linked list and it's only singly linked。

 you can't remove things without traversing the whole linked list， right， So。😊。

If you get rid of maybe like the header a footer， on the other hand。

 then maybe that's something that you can safely get rid of without sacrificing any throughput in any sense。

 Or you might find， oh， actually， the O of N， like on the， the small case is actually not that bad。

 Like， I can sacrifice some throughput。 And I just， you know， have a nice case。

 So that's a design consideration。 That's something you might want to think about。Okay。

 so that's all I have。 Nikil will now talk about debugging your code。

 which you will probably spend a lot of time doing， unfortunately。So whenever you write a program。

 you never expect that it works on the first time， right。

 I don't think I've ever met anyone who's gone through this entire assignment without a single sful。

So you'll be doing a lot of work to figure out where you went from。Well。

 what's your go to way of debugging？For a lot of people， it's printing。

If you print out every single thing you do， maybe you'll catch something that's wrong。

 something that you shouldn't be doing。Except when you have， let's say， 20，000 allocations。

 you can't really do that。And thing with memory errors is if you do something wrong。

 it may work the first time。 it may work the second time。

 it may even work for another 200 allocations。And then on the 21st time。

 when you're doing something completely unrelated， like freeing a block， look' at a Seg fault。

And it's not necessarily you're free。 That's wrong。

 It's everything that came up to it could be broken。So， GDP。So at the end of last year。

 I got feedback saying I pushed GDP B too hard。 I'm not going to learn from that。

 I'm going to push it even harder this year。So GDP is your one stop solution to figuring out where your problems are。

So you can use GDPB on MDriver and you can use all the commands you were using before。

 You can use step next。To execute your code line by line。

And the another cool thing about GDP is you can run any C instruction。 So for example。

 let's save a function that prints your heap and shows you a nicely formatted way of what your data looks like。

Well， you can call that function exclusively in GDP。

 so you don't have call during the main operation of your program。

 so it's not cluttering up your your terminal every single time it prints out。

But you can reserve it solely for GDP。 So if you have a seg fault， you print out entire heap。

 And then you can see， O， clearly here， this pointer is incorrect。

 Let's see what's wrong with that pointer。And using X。

 you can examine individual memory locations and you can see if some value isn't holding the data that you expected to。

So when you have a Se fault， what's the first thing you do？Well。

 you use back trace to see what were you doing when the second fault happened。

And backts will list a nice table of all the functions that you are in。So here main called run tests。

 which called evaluation， which called Dmalic。And then your malic called F fit。

 and we set forth it in fine fit。Well。Now we know where to start。But what if something before it？

Caused the problem。So then we can go up a frame so we can say， okay。

 pretend we're actually in MM M Malic。 And if you do frame 1。

 you can switch to Malick stack frame and print out any variables that you have there。

So you can examine the entire state of your program。Just by using GDP。

And another cool feature of G GDP is you can set breakpoint and watch points。So。

 break points are essentially。A command or some instruction to G to say before you execute this instruction。

 stop and let me know。So let's say you want to see what value X holds before you run this instruction。

 Well， you set a break point on that line or on that instruction， and you print out the value of x。

You can also say conditional， So only stop here if x is 10。That way you don't stop every single time。

 but if you know， okay， when x is 10， I have a problem。

 it'll stop only when x has that problematic value。You can also use watchPs。😡。

So watch pointss are break pointss， but for data。So let's say you want to see what value X holds during the course of the program。

Well， you can say watch X。 and we'll say， okay， at this point， this old value of x was 5。

 And after this line of code， x is now 10。 And you can see， okay， should X be changing on this line。

 Did I do something wrong where the wrong data is changing。You can also watch memory addresses。

 So let's say you have some particular block that gets garbled or messed up。Well。

 let's watch that address of the block。 And any time we do point arithmetic on it。

 anytime we return it to the user we'll be notified so we can say， okay， this is an allocated block。

 Why am I treating it like it's a free block， Why am I writing and using the next and previous pointers。

And you can put watch pointss on those to find out what's wrong。But the biggest。

Helpful future is the heat checker。So I know many people throw on the heatap checker at the end。

 so you say， okay， let me write up my malic implementationmentation and just to satisfy the Ts for my points。

 I'm going to write some really simple heatap checker。We really discourage that。

So I think if you use a heap checker， you save on average three to five hours。

So what should your heat checker do， Well， your heatap tracker should be exhaustive。

And should check every single invari that your program has。So this isn't meant to be fast。😡。

If he checker could take， let's say 30 seconds to run。 That's perfectly okay。

 It's purely for debugging。 So you know exactly what's going on in your program。

So write this function early and update it as you change your implementation。

Every single implementation doesn't have the same invariance。

And every single invariant is not maintained at all times。 And that's okay。

But you do need to know when to use a heatap checker and what to check in your heat check。

So let's go over some invariance。So if we're looking at the block level of your malic implementation。

 what are some things that should be true all the time？Yeah， exactly alignment， right。

 so we have some alignment requirements for our block。What else？姐。The not exceed the remains space。

What was thatload Exactly， So the start and the end of your payload should be within the bounds of your heap。

And also we have the header and footer matching， right。

 So we have some metadata inside and that metadata should be always correct。And for coalescing， well。

 then we make sure everything is coalesced。 If we're going through our heap and we see two free blocks in a row。

 Well， then we have a problem， right。And if you have this check built in。

 you will know exactly when your coalescing breaks down。 So rather than trying to see， O。

 after running 20 times， I have four free blocks in a row， What went wrong。 Well。

 if you call this before and after every function， then you'll know exactly which function broke this in buried。

Now， if we look at the entire list。 so what are some things we want to consider when looking at the list。

Yeahep。The next element and previous element pointes line up each other。 Exly。 So our linked list。

 So for our next and previous pointers， they aren't pointing to completely different things。

 So if I go from block A to B using the next pointer， Well。

 I should get back to a using the previous pointer of B。😊，What else？Yeah。

Running through the late list visits or the free blocks。 exactlyly。

 So if I my free list says I have 10 blocks。 But then if I go through my main heap and I see， oh。

 there are 12 free blocks。 what does that mean。Well， at some point。

 that means you have lost a free block。What's the problem with this？If you lose a free block for。

 your explicit list or whatever free list you have， can you ever give that to the user？

So it's just dead space， right， so it'll really harm your u requirement。And similarly。

 if you have a segregated list， well， that every block inside there should be at the right size class。

If blocks are in the different size class and you're searching there and if you're searching it。

 let's say you're searching for four byte blocks or 40 byte blocks。

And all your 45 blocks ended up in the 256 size class。

Will you ever find those blocks when you need them？No， so more dead space。

And now if we look at the heap on the hole， what are some things we need to consider？别。

So we've got like the headers and then the length of all the blocksps and all together that should add up to the full size of the heat。

Yeah， that's a good check so if I add up all the sizes of all the blocks have allocated well then I should get the size that I've requested from S break so far。

 what this prevents is header information being incorrect because if you have one header that's really really big and it's saying your block size is two gigabytes well。

 that doesn't sound right。Anything else？Yeah。What about the prologan up？I again at the beginning。

Exactly， right。 So what's the purpose of our prolonggan epilogue。 Well， it needs to bound our heap。

 We know all our blocks are within the prolong the epilogue。 So， well。

 the prologan epilogue better be at the start at the end of our heap。

So will all these invariants apply to every single implementation？😡，No， right。 So for example。

 if you get rid of the prologue and epilogue block， we can't reasonably expect you check it， right。

 So as long as your invariance match your implementation， you're good。So now how do you ask for help？

Be specific。 So if you tell me my program Se faults， I really don't know what to do with that， right。

 I'm just going to say that's unfortunate。 What else can I do for you。

Some good things to tell me are， okay， I ran M driver， and when I take this particular pointer。

 I'm Seg vaulting。How how do I find out what's wrong， How do I go from there。

 And then we can help you out and say， okay， have you tried the watch point。

 Have you tried setting break points here and there。

One thing I want to stress is we really can't sit there and debug every single line of code with you。

So as you've known before， there are maybe 20 TAs and 400 students and office hours can get busy。

And don't expect that to change for meick。So get there early。

 have precise questions that you can ask us and then we can answer。And start early。

Another good thing to say is， okay， by heat checker， which I have thoroughly written。

 catches this issue。What may be wrong and how can I go about approaching to solve that problem。

And when you come to office hours， we will expect you to have a thorough heatap check function。

 and if you don't， we'll just move on to the next person in the queue。And use a rubber duck， right。

 So many times when you're looking at the same code over and over again。

 it's easy to skip over mistakes because everything looks rightright。

But when you start explaining it to someone else， you think， oh， why am I doing this here。

 This is completely wrong， And it's the process of you talking about your code that causes you to find it。

Staying at the same code will be tedious。 And at first。

 talking about it will sound awkward and tedious also。 But trust me。

 it really helps because most of the time， if you do that and you find your bug， Well。

 then you have more time on the cue to ask about something else。😊，So if you get stuck。

 please read the write up and watch lectures and our usual stuff。 and good luck with Malick。

So we do have an appendix， we won't be going over this for the sake of time。

 but feel free to look at it on your own time。About more optimizations and things you can do。Thanks。

 everyone。Good luck。

![](img/a37b95b59973c2e797175f42d0cb3a81_4.png)

First ever。