# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p24 24 - Dynamic Memory Allocation_ Advanced -BV17jcReyETC_p24-

看下。

![](img/410f0b7d50dc9c64e6c0b83c352944a0_1.png)

这还较。这样。

![](img/410f0b7d50dc9c64e6c0b83c352944a0_3.png)

I had to like carry it around that。And I would like to go it in。Okay。

 so why are we going get started too much late， I apologize for that。

So today is the second of the two lectures on dynamic memory allocation。

If you remember from the last lecture we're talking about a piece of system software that sits between the application。

And and， and he。Okay。😊，Programs。呃。Make requests to either acquire or free virtual memory at runtime。

And memory gets allocated off part of the virtual memory called the Heap。Okay。

 which runs distraction。And is demarcated by this pointer called this BK。

so you get some initial size of BK when you start up， and then if you run out of heap space。

 this pointer will get bumped up。We spent pretty much the entire class talking about one way of keeping track of the blocks that are available。

 the free blocks， and that was called alicit list where we use the length to link the blocks and we discussed the number of implementation strategies and optimization for that。

We also mentioned that there were three other methods。

Explit lists I to free list and sorting the blocks by size。

And today we're going to spend most of our time on the second one， explicitly。

Which is also the one that you're。First part of your Mai cl feels free。

Just to summarize what we learned about implicit list what we talked about last time。Is that the。

Implementation is simple， the allocation cost is linear time in the worst case， why is that？

The numbersumb yes。You're just walking through all the blocks until you find one that is available and fits。

On the other hand， freeing is constant time worst case， even if you're coalescing。

 which is the act of taking if you're free of a block that happens to be next to one that's already free。

 you want to coalesce those into a bigger block。Of those two。The memory usage。

 how effectively are you using the memory that you have allocated in the heap？

That depends on the placement policy we talked about first fit。

Whi is sort of you go along and you find the first one that fits。

 next fit is similar except when you start the next time you instead of going back from the beginning。

 you start from where you left off and best fit is somehow you go through and find out of all the possible ones that are open。

 which is the best fit， which is the closest to the amount that you actually want to allocate。

This linear time worst case allocation costs is why this particular strategy isn't used in practice。

 but in sort of sophisticated settings， but in many special purpose applications。

 where maybe there's code constraints or something you prefer simplicity and small code footprints over over improving the allocation costs。

 this is one that still gets used。And moreover， the concepts we talked about。

 these things like splitting and boundaryty tags and coalescing and so forth will come up again。

And when we look at other options。Okay， so as I mentioned。

 we're going to talk about explicit freeless。And that's this picture here。

 so basically what we do in this picture is we have pointers that will。

Point from we'll sort of link in one big link list。

 all the free blocks right so here to here and the next free one and so forth。All right。

 so when we look at how we're going to implement this for the allocated blocks， there's going to be。

 you know we still need this size field， right， because remember when we go to free something。

We're not given the size， so the only way we know the size is by squirreing it away in the heap so we can get it we have this bit that indicates whether the thing is allocated or not。

 we have our payload， we have our padding。In this example， to keep it simple， we'll have the footer。

 with also the size and the allocation。But as we observed in last class。

 there are optimizations for removing that。But what's changed is what happens here on the free side。

Where now we have a pointer to the next thing in the linked list。

 but also a pointer to the previous thing in the link list。

 so it's going to be this doubly linked list。Mechanism。Okay。All right， so logically， as I mentioned。

 it's a doubleubling linked list， yes。他唯一是8月1。啊。That was this strategy here。Okay。こやては。Yeah。

 we didn't really dwell on that at all， but basically you're exactly right。

 you can have a balanced tree and that can help you find。Best fit kinds of things， good。All right。

 so logically it's this doubleub linked list， but it's a free list that's being created dynamically as the poetry goes on。

 so sure enough it's soon spaghetti right in terms of how it actually looks laid out in the virtual memory。

Okay， so what this's showing here is。You know that this block A。

 B points to B using green arrow when B is way over here。

 and that points to C using its forward link and that points to the start of the C， right？

And going backwards， you know C points to B and B points to A and so forth。Okay。

So it's not that we keep these things sorted。I mean， that's an option。

 but typically that's not how it's typically done。Okay， so let's look at what happens。

 so if we have this picture before。All right， so this is our W link list and of course。

 things come in here， here and so forth。Here you here。

And we're just focusing in on this middle block， and we're saying in the double Nick list。

 it has a predecessor， preve and a nexted。The one was previous next。Okay。

 so if we decide to allocate。This block here， then we do， well， if we allocate the entire block。

Then we do the usual thing you'd imagine， which is just splic this guy out of the linked list。😡。

And this could be go to this good， but as we've seen。

 oftentimes you there's not a perfect fit between the size you're trying to allocate and the size you have available。

 and so you do what's known as splitting， we talked about last time。In this case。

 what that means is that you have this region that's maled。Okay。

 and you have the region that's still available and that's what you like in its place， okay？

So instead of having this， these pointers always point to the start of the free region。

So now the start of that region is here， so that's why the green pointers moved over。Okay。

 and similarly， these pointers are stored。From the perspective of this block they're stored towards the head and so now that this is the free block。

 you need to put the pointers here at the head。谁？Any questions on that？

So this is sort of the case without worrying about any coalescing。嗯。Okay， so。All right。

 so so that was an allocation now let's suppose you do it free。Okay， so if you do it free。

 then you have a new thing to add to that。So you have all these questions about how to make this efficient。

 whatever the choices are， and all the society is saying is that。You know in general。

 when you're thinking about writing your malic routines。

 you want to sort of get the high level decisions first right what kind of you know explicit lists I'm using and so forth or implicit or what am I doing segregated。

 you want to get the high levell choices to make the most sense for the metrics you're trying to optimize for you know in the real world or in the lab。

 so you know you don't want to go drilling down on the nuia before you get the high level picture right？

But if we were to drill down the minutia， then what we would see is that if we keep these things unordered。

All right， which is the previous example I just mentioned。

 then you can imagine that you either insert a free block at the end of the current free list or at the beginning okay。

 so it's either last in first out or first in first out。

And the advantage of that is you have this pointer to the start of the free list。

And it says doubleub it linked， and so how much time it' its going to take you to actually do the insertion？

不。If I have a pointer to the head of a list and I want to insert something and also it's doubly link。

 so I also point to the tail list， and I want to insert something in either the front or the tail of the list。

 how long does it take？Cost of time， right， so that's the good news。Okay。

There is some studies that suggest that the fragmentation may be worse。Then the following mechanism。

 which is to try to keep them ordered。Okay， address ordered policy says that you always try to keep this。

Collection of pointers that hook up all your free list blocks in a dress order。

 so it hops through the virtual memory in a dress order。Okay。

How long could that take to do an insert？ItCould be linear time right so that's the con you've got to do search。

 maybe you put some search structure over to make it maybe logy of time but still requiress a search。

 it's not going to be a constant time。But on the other hand， if fragmentation is important to you。

 very important to you of higher importance， than insertion time。

 then you might want to go and dress work。O。But let's go with the first of those two choices。

 where we don't worry about a dress order， and now we want to， let's say。

 do a last and first out policy。So if you remember from the previous lecture。

 we had these four different cases when we went to freeupuff that informed the coalescing。

 the first case which I'm showing here is where the two blocks on either side of the thing that you're frameing are also allocated。

Okay and in the pictures we had in the last class， these were sort of stacked towards eyely。

 do you remember？Okay， so you'd have the allocated。Andbo。

 the thing we're trying to free in the middle， but for this lecture。

 because we're showing these pointers it's more convenient to laid about horizontally。

 so that's the same picture just laid out horizontally and it corresponds to virtual memory which we've laid out horizontally as pictures。

Okay。So we have this route ahead of our free list， and it's pointing here。Okay。

 and this little symbol just means that the pre pointer is null that's nothing previous in this case。

And now we want to free this block here。And the fact that these are both allocated means that there's no coalescing to be done and so we just want to insert the free block at the root of the list and so it's the obvious thing you can imagine right you just you point the root pointer to here and whatever the root pointer pointing to here becomes the next of this guy and the pre gets pointed back。

Okay。And actually， this would probably。So correctness point to the start of this。Okay。

 you want all your points to。Poins it。Actually， actually。NoI stay incorrect on that basically。

Because we're using the footer。Tag method， the information that previous always in foot。

 so if we weren't using that footer tag method， then。Then you would point to this story。All right。

 good。So that's case one， that's the easiest case what about this case so here again you have to think about the two different views of this world。

 one is the linked list view of the free blocks and one is the layout in memory。

So the layout in memory shows that I'm freeing something that's adjacent。

Tohoose something that's already free。Okay and because this is the unordered policy。

 there's no reason to think that this has any relationship to how it falls in the link list。

 so we're just conceptually drawing this next successor block as being somewhere in the linked list。

 it has some predecesor， some predecessor， some successor and so forth then of course。

 you know these things go on。喂。Okay。And the root points to some other place。

 there's no reason in general that the root is going to point to any of these three blocks。All right。

 so what we do， we slicelice out， we want to combine， coalesce these two， okay。

 so we want to create this new block。That's the union of both the freedom and the world。Okay。

 and because we're doing a lifeful policy， that new block we're going to put in the front of the loop。

Okay so the root will point to that just as did before and its next will point to what the root used to point to and so forth。

 so that part looks just like the picture room before the only difference is that we actually yanked this part out of the list。

Okay， so this guy points way over here and this guy points back to here。All right。

 so we've removed this part that was here before from the W leak list。

Created this larger block and put that larger block at the funding list。你快写上来。嗯。

We're using a memory that's in like below the kind of rate。

That break back down because if all the like memories like scam。大だ。That知道。So。

It's rare to move it back down， can be done， you have to make sure that everything you move past is not being used at that point in time。

 that's the hard part。But， yeah， but it's legal， legal to do it。对。

Any other questions on this case yes，No， if you notice this block wasn't at the root to start with。

 it was just a free block that was in the middle of this list， again， this is where。

You have to get used to these pictures。 This picture is showing you， you've got。Well this。Sorry。

 this was an allocated block， so it wasn't in the free list at all。

 and your program is telling you to free this。😔，It's adjacent to something that somewhere in the middle of this long double in neck list that eventually the root gets to。

可以。But this is perfectly general， the thing you're freeing has no relationship with the root。

 the thing you' it's adjacentd to has no relationship to the root。你举中。

The only relationship for root is that we're going to put this nearly free block because we're using the life of policy as the first thing。

 so that we'll point to it out to you done。は。Good。All right。

 so case three is the flip where it's the predecessor that's free。So again。

 the pictures you've got this block here and again。

 this predecessor block is somewhere in this massive of doubleub linked list。And so。Youre due。

Similar thing， you're going to splic this part out entirely from this it's placed in the doubleub link list。

 so that's what this intended to mean， this green arrow ducks under here and this red one goes in here showing that this first block has been completely spiceliced out of where it was before。

Then you combine it with what you just free to make a larger block。

 and then that block by life of policy gets put at the root。Okay。Does pictures make sense？

They take a little bit of use to it， and I think they're actually recently。Good pictures。

And the final case is where it's free on both sides。Right。And so now it's kind of what you'd expect。

 right you've got each half of these each side of this is in its own place somewhere in the middle of this massive W link list。

😔，And you want to splice out on both sides。And then you want to create this one big block。Okay。

 and put that at the room。Any questions on that？And all the stuff about like， okay， I need to。

 I want to compute the new length of this and things like that to get。You know。

 the the headers and footers of this right just follow the exact same strategies that we use when we talked about implicitly right you sum up the different sizes of these three and that's how you get the。

The totals。Size。All right， so here's yes。Just in practice， how。Determine which case。

What do you know like if you're going to free your discipline memory， how do you know that？別に。フ。Well。

 the programmer doesn't know， the program is all hidden to the programmer， but the memory allocator。

呃。The memory allocator has track of this， right， so it knows that you're trying to free this flock。

 okay？So well let's start with this one， you're trying to free this block。

 so what it does is it looks at the very next。Sell and virtual memory。

 very next word in virtual memory， and it's going to find a header there。

 okay because absolutely that we're not showing the headers there。

 but it's going to find a header there。And the headers has this little a bit。

 which tells you whether it's allocated or not。And so if it's allocated。

 then you know you're not in this case， if it's unallocated。

 then you know this is free and so you're in this case。Okay， and similarly， from here。

 you go back one， you see the footer。Okay， and the footer also has the allocated bid， if that's set。

 you know you're not in this case， if it's odd， you know you're in this case。

And you do the thing so it's kind of why we walked through all that in last lecture。

Because like we said， sort of the mechanisms are very similar。

Mechanisms for knowing which of the four cases you are are actually pretty much the same as they were。

In the last lecture， so I chose not to review that， but maybe I should。

The only difference between a person and。Fless。Exquisite isub doubling。

Well implicit didn't really have any links at all right it was just based on the sizes。

 so I get to a block and I saw it was size6， then I would hop ahead six and I would get to the next block and I saw a size four。

 hop ahead four and get to the next block it was all based on arithmetic to to do these things。

And plus it went through， and accordingly， it had to go through both allocated and free blocks。

To get there， right， this one， we have the advantage that our linked lists only involve three blocks。

 which。Not a big deal， maybe early on， but as your memory gets more and more full。

 you may even to jump over lots of things。Lots of things。Alle， good questions。哎， so看到。

So here's an implementation trick that you may find handy， okay。

 so we said a double link list but suppose we make them both circular。Dublin linked list， okay。

 so they both wrap around。Then this single data structure can support multiple approaches。

 so for instance， for first fit。If you're looking for the first fit block。Then remember。

 you always start from the beginning， so you can always just start from here， okay。

 that's the first one。Okay， but with the same data structure。

 if you've mared say to D and you're stopped and now you want to start again， then you just。

Move that pointer over here okay and you're just going to next it's going to wrap around when it runs out and so forth so having these links that actually wrap around makes the implementation simple。

 you just keep you following this list and first fit will always start here next with that pointer will move around。

Okay， so that's kind of nice and also if you want to if you're if you're doing like either lifeF or fiIO you could do it with this structure so for instance。

 if the pointer is here and you're doing。LO。Then you want to put it here like we've done before。

 right？If you want to do FiIFO。Then just put it here。Okay。So with sort of a single data structure。

 you can be experimenting with a lot of different policies to see which is getting you better performance。

O快洗上来。Okay， so compared to imp， explicitists。呃。Alloccate。So the things you're searching。

 you search over the free blocks instead of all the blocks that we just talked about much faster than most of the memory is full。

It's slightly more complicated to allocate free because of this splicing business。

And you need there that extra space for the links you get to need to both。I mean。

 not just the size that we had before， but now you need the size and the next and the pre。😔，Okay。

 so this is two extra words。Needed for each block。And the question here is。

 does that lead to internal fragmentation or external fragmentation？

Remember the difference between those two？Intern， right。

It's based on the overheads of structure itself。Okay。So much more common。

 our nice common strategy is what's called segregated free lists。

 where you have not just a single list of all the free blocks of all the different sizes mixed together。

 but you have multiple linked lists of different size classes。Okay， and we'll cover that now。Okay。

 so here's the example。 I mean， the choice of what size classes you have。

Its up to the system allocator， so as a person working on MaFab， it's up to you。

And when you get down to the nuts and bolts of trying to come up with the most performanceant scheme you can。

You're going to want to think about things like what are the size positive？So in this toy example。

 we have a size class that covers both allocations of one and two。A separate one just for three。

 a separate one just for four， and then you know one that covers five， eight。

 and then one that covers all the rest。Okay。Arbitrary choice may be based on whatever request sequence。

That particular allocator was being used to support， this made the most sense。Okay。嗯。

But as a general rule of thumb， you often have separate classes for each of some of the small sizes。

Okay， because you know there's a lot of fragmentation in small sizes， right if you end up padding。

Like if you have a really big block and you have to pa a little bit。

 that's not much fragmentation compared to having a really tiny block。

 you have to pad or add in these headers and foot too。

So there's a real advantage to trying to avoid as much fragmentation can in smaller sizes。

And for larger sizes， a common thing to do is by powers of two。Okay。

 so not just have a five to eight， which covers all allocations between five and eight。

 but have a nine to 16 and a 17 to 32。33 to 64 and so forth。可以。😊，嗯。So now if you have a request。

 then the first thing you do is you figure out which of those segregated lists it belongs to。

 and then you go into that list and you march along until you find something that fits， right？

Because remember， like things like this， anything between five and eight could be available on this list and maybe you're coming in with eight。

 so you're only happy with the ones that are eight。嗯。嗯。

Now it's possible that you can make it all the way through this five through eight and there's actually no8s and so you're stuck in which case you do the obvious thing is you just go on to the next bigger size okay so here you know the first one you find is going to fit right if you find anything in the nine to infinite list。

 it's going to pull eight。Alright。But that is the failback， right， that says if no blocks found。

Try the next larger class。O。Now I said， if you find something will fit， but of course if you。

If powers a two and you go to this next larger one and there's nothing there， right。

 then you have to go up to the next one and so forth， so you repeat until black is spent。Okay。

 but that's really the uncommon case right that you would just keep scanning up these classes。

 typically you're going to find it in the first class the class' intended for and if not maybe then almost surely the next one。

All right， and then the extreme worst case is when you go through the entire all your free list and you don't find space for it。

Okay， that's when you have to call this S break。Fun which is going to bump that pointer up and create more he space okay and there's usually a policy within the system for how much that jumps up right maybe it jumps up by 50% maybe doubles whatever so you're going to get a lot more memory because you don't want to be moving that very often so you're going to get a lot more memory。

And so within this huge new block of memory， you have space now for your。

Request that youre trying to find， okay， plus a lot of other new space。All right。

 and then the remainder you put is the largest size class， yes。Inesting to sort preemp when you are。

靠SV看来说。More everyday needs that。ろは。Yeah that's so I guess it wasn't being clear so that's what I was suggesting that that's the typical thing to do is that you have some you need to allocate more memory。

 you're not going to just allocate for this particular request you're going to do some big jump of this pointer right so maybe it's like 50% you know if it's this much you're going to do like another 50% on top of that right so you have a lot of more space be freed up and then just allocate within it for exactly the reason you mentioned。

Yeah， that's the common way to。Yeah。Slaade out， actually did。Because so if you have to。で啊。

It sucks to you， and it was for all the size four。系转。All exercise。そ田先生。啊。

It's up to you Ty there's no need to right the this is just pointer spaghetti。

 right it's just these these things are be Yeah， they could be literally leak。Okay， yeah。

 and this is only showing the single link because obviously these are all double linked classes。嗯。

All right， and as before， if you' do free， you want to pay attention to the coalescing opportunities。

When you coalescce， something it may。Sor of bump up which of the lists it's going to be in right so if you coalesce two things that are of size of four then you create something with size8 so you want to put the new thing in the size8 list。

嗯。O。So the advances are。呃。As opposed to so linear searches。

 you're kind of getting logarithmic time searches because there's only a loggged in number of classes we get the power of two approach for with the smallest list。

The memory utilization can be good because。You know， first fit search of a segregated free list。

 approximately a best fit search in the entire case， right？So， right。

If you come in with allocation of size three。Can you do a first fit？In this here。

 you've actually done a best for it。Right。Similarly for four and so forth。

 so why we say only approximate is because for cases like this five to eight。

 you're going to come in with something between five and eight and your first fit may return you。

Something slightly bigger， right， so maybe your request is five， it returns you7 or something。

All right， but it's a way of avoiding this sort of binary search tree kind of thing。Of best fit。呃。

Of the entire heat by doing the segment of freeless。Okay。

 and then this is just pointing out that the extreme case of that is instead of doing this power two trick。

 you actually had a segreg list for each individual sizes， you know。

 I had its own 1 I+ one had its own  I+ two that of course it would be equivalent to best fit。

 but then you' you know that's a lot of lists and there's overheads for that。

So you typically don't want to do that。All right， so this is a classic problem that we're talking about。

 you know， Kucea 73 art computer programming。Textbook series you know talks about this kind of stuff and there's other references here。

 these references available at the CSAP student site if you're interested。And so let's do a quiz。

All right， so it seems like people are doing pretty well on this good。

So we're going to keep throwing GDP questions at you until you。

Pro they really understand GDPB because we really want you to。Yeah。

 so watchCom is a know you watch a particular address location。挑取的呃。有。

Is activated whenever that address is modified？嗯。Yes。

 this is internal fragmentation because it's giving you a payload that's much larger than what you requested。

It's good。And。Okay， so this one is a little trick here， but you still most people got it right。嗯。

So best fit。Is。The one that would minimize internal fragmentation。

Because you're always getting the best fit， so segregated free list is a good approximation for that。

 but it's not going to improve utilization。It's going to， for things like with the power of two gaps。

 you're going to still have some internal fragmentation enhance hence some memory utilization decline。

 not a whole lot maybe but a little bit。K关事3奶。Yeah。

 so earlier you mentioned that if we're doing explicit。We want to sort。Avoid。

I said that was an option why is that an option？嗯。Yeah， so it's not intuitive at all。

 that's why it says sort of studies have shown。Right对。That。For whatever reason it tends to be better。

 right yeah。I don't know the nutritionition。All right， good。

 so now I want to talk about garbage collection， we touched on that very briefly at the last lecture。

 mostly of you to point out that a language like Java will do garbage collection for you so you don't have to free things。

Whereas。

![](img/410f0b7d50dc9c64e6c0b83c352944a0_5.png)

C， it's a lot more challenging。

![](img/410f0b7d50dc9c64e6c0b83c352944a0_7.png)

And you have some constraints like you can't move things around。



![](img/410f0b7d50dc9c64e6c0b83c352944a0_9.png)

But let's cover that a little bit more detail。Okay so。Now， to mind you。

 it's automatic recclamation of something that's been allocated on the heap and now is no longer mut。

So here's an example where。You've allocated a region。

And then your return from your function service this pointer。

The scope of this pointer is only within this function and therefore once you return。

 that pointer is not within scope anymore， and so that means you can't get to this entire block of data。

Through sort of。You know， legal means。Okay， and so now that you can be safe to free that region。嗯。

Now， there are。Conservative garbage collectors for languages like CN andC++ I'm going to talk about those。

没是。So the main thing that garbage collect has to figure out is what's garbage？Okay， if the program。

Programr has it told you that I'm done with this particular thing， free at this garbage。啊。

You know the。How do you know。So。So in some cases。It could be that we're talking about compilers a number of lectures ago and。

One of the types of analysis the compilers will do is sort of what's called a my variable analysis Ill try to figure out which of the。

Sort of variables that you've defined are effectively dead。

 they're not going to be used anywhere else in the program。

But that's particularly with pointer structures that's really iffy for compilers and they're not able to do a very good job on that part of the issue is you know a listing of pointers but also just all the conditions like what path through the program you take maybe some path through the program。

 you use that pointer again， some path through the program you don't。

OkaySo what you do instead in trying to figure out whether a pointer is going to be actually used to reference particular member or not is you actually say。

 well。😔，If I have a pointer that's within scope， then there's just this potential that I could use it。

 and so therefore it's not garbagech。😔，Okay。So conversely， if I have a block。

Of memory that's been allocated under the heap。And the program no longer has any pointers to it anywhere in that block。

Or to that block， then there's no way the program to get to it by legal means and therefore it's garbage。

Okay。嗯。So the assumptions you need to make to get to work is that you can distinguish pointers from non pointers。

That all pointers point to the start of the block。And you cannot hide a pointer。

 say by coercing to in and then back again。Okay， so this is。呃。

The sort of the classical setting like what you be doing for Java and things like that。啊。

And there's a whole series of albums starting in the 1960s here in 1960。嗯。And market sweep。

Its one we're going to cover for a few slides。There's Ra County that you may have heard of。

That's you keep track of how many pointers you have your particular。

count of how many things point a particular block and when that count drops zero， then you say， okay。

 I don't have anything to point to anymore。That's reference counting。嗯。

Copy collectors will in the process of figuring out what garbage actually try to move data and coalesce it so to get rid of some of this fragmentation that's spreading out of the data so that maybe you're actually using a lesser chunk of the heap。

Generational collectors， which is a little more recent phenomenon。

 but still been around for a long time。嗯。Looks at the fact that if you've kept something for a while you're likely to keep it for a while longer。

 so the things that are most likely to be garbage are the things that you most recently allocated。

Okay， so you want to focus your garbage collection on things that have been recently allocated。

It's okay to do the other stuff， the older stuff， but the odds are if it hasn't become garbage。

After this long， then it's probably not going to become garbage anytime soon。Okay。嗯。Yeah。

 and there's entire。Book漢s。Okay。So we're going to talk about the market suite value。But in general。

 the way these garbage detectors work。Is that you view memory as a directed graph。

Where each block becomes a node in this graph。Okay and each pointer each pointer becomes an edge in the graph。

 so if I have a pointer to this block here and on a heap， that pointer becomes this edge here。

All right， now the root nodes is an important concept。

 the root notes capture the things that sort of the handles or the pointers or whatever you want to call them into the heap that are actually available to the program at this time。

Okay， so。You know， these are locations， they're not themselves in the heap。

 but they contain pointers in the heap， right， like you put a pointer into register。

It's on something in a stack where it's stuck into a global variable。可以。

So from these root nodes is the way you make your first step into the heap。

And then you subsequently you chase these different pointers to get to other places in the heat。

And what this diagram is showing is that there are some。Reaches the heap， some blocks。

 even that have pointers to them。That aren't reachable by the program because you can't get to them from one of the root node。

And again， the root node are the only sort of windows you have。

 the only access availability you have into the heap。And so that's why these are garbage。

 they're just not reachable anymore， obviously at some point they were reachable that's how you constructed them。

 but they're not reach anymore， the pointer went out of scope for instance。Okay。

 any questions so far？Okayけ good。So Marcus Street， which again is just。

 I guess maybe one of the first collectors that were invented， still popular。嗯。Works as follows。

 you have this extra data structure that you're going to use as you join the garbage collecting。

 and it's called a mark pit。You you stick it somewhere at the head of each block。

And what you do is you start at these routes。Okay， you started the route。

 so let's say you started this route。And you just follow this pointer。 and then you mark this guy。

And then you follow its pointers and you mark their guys and so forth。

 and then go here and you mark this guy。 And you can see if you do that。Then in the end。

 all the green guys have we marked and the。Whatever color that is， pink guys won't be marked。Okay。嗯。

So here's another way。Ficuring that。So you've got the heap and you've got some root that allows you to point here。

And again， just so we're clear here， this is highlighting the fact that。

These pointers are no longer maintaining freeless pointers Okay。

' we're not talking about that right now， right now we're talking about garbage collection and so these are actual。

Pointers in the he， right so this is you're saying this location， the heap。

 there is a pointer that points here。Okay。So。So based on this， chasing these pointers。

You mark the bits of the regions you're to reach。Okay。

And then the second thing is called market sweep， the second thing is this sweep。

 you can just literally sweep through this heap from one end to the other。

 and whenever you see something that wasn't marked， like this region here was not marked。

And this region here was not marked。Then that's garbageing to free。这关的。Is it clear？对。日語理由。かて。嗯。

So you're going to see the， yeah， you have to do this in conjunction with the memory allocator。

 you're going to see the sort of the headers。Right of these things。

so you can look at this header and you say， okay， I know beside size it。Okay， good subtle question。

 Li。Yeah。like a situation where someone might use like make another。No later。

process and then connect it to something that would be garbage。But it gotbleed by the garbage。

 it got freed by the garbage collector。 Yeah， that's a good question。

 the the point being is that let's go back to。This picture。The point being。

 I can always create another root note。Okay。But I have no way of assigning this written note to any of these garbage guys because there's。

There's no hand on， there's no references， there's no way to get to it。Good。questionsions。Okay。

 so let's just look at a simple limitation of market sweep。We're going to have a。呃。

So of a new turns pointed into a new block with all locations cleared， the read and the right。

Of a block。We're going to have a header word by convention。

 we're going to say that for block B that the negative ones。

 the position right before the start of the block， willll have the header word。And。

The garbage collector will be defined in terms of the following functions。

We have some function is pointer that just takes a address and determines whether that is a pointer or not a point。

We have a length。That returns the length of block B。Okay。

 that sort of gets that question and then we have a get roots command which can return all the roots。

Okay， so given those functions， the market sweep is going to look like this follows， okay。

 so you have this mark。Folum Mark， can you give it initial pointer？Okay以。

And what we're said here is if its your user is pointer， sorry， you， you give it a location。

If it turns out that's not a pointer。Then you're done。Okay。

 if it turns out the thing is already marked。Mark Bi set for that。Blocked then you're done。Otherwise。

 it's the first time you visited this block and say you want to mark it， so you set it mark it。😔。

And then you run down the lengths of the block。All right。

 and you recursively call Mark on that particular word in the block。Okay。So then。Right， so。

I mean it's basically just the code。To do this。Terveral， right？You started you pass it to a route。

 it's going to look at the structure and do a cursive call on each of these guys。

And Mark those things accordingly。And then the sweep。

You start at the beginning of the heap and you say， while you haven't reached the end of the heap。嗯。

If the markbit is set。Then this is not garbage， okay， but you go ahead and initialize。

The garbage collecting for the next round， which will occur sometime in the future by clearing the mark bit right because you always want the garbage collector to have all all mark bits cleared before it begins to do its market suite。

 So this is sort of setting you up for。A subsequent call to the garbage scor。Okay， otherwise。

 it's not marked。And so let's see if it's allocate。Okay。嗯。If it's allocated， if it's not allocated。

 that's fine。 It's it's already。In the free list and so forth， so we don't need any garbage like it。

 we're worried about are these ones that have been allocated， but no one can read them anymore。

So if it's。If it's allocated。Then we'll go ahead and free it。Okay。It's garbage， so we free。

And we go to the next block， right， jump。Jump ahead the next。かしくな。So what about C programs all right。

 so C programs？Have all sorts of fun things about them。啊。But among the things is that， you know。

 so maybe Alex， let's say this was an array I allocated right， so I allocate this array。

And I've been marching my way through this array， so we're using a pointer。

 and so at this point in time I have this pointer that's kind of in the middle of array。

 not to the head at all。And so， but to run the sort of the mark and sweep and stuff like that。

 I really want to get to the header of the ring。So。And the assumption I'm going to make is that。

You know if from a root， I can get to a pointer。Anywhere in this block。

That means that I'm still able to access anything in the block， okay， so it's not that I say， oh。

 the only thing that's not garbage is this guy because that's what I'm pointing to。😔，I say no。

 the whole thing， the whole array is not garbage， okay？

Because the programmer can do all sorts of point arithmetic in here and march up and down this array so the whole thing is not garbagetri。

But I am going to assume that you're not walking off the end of a race。

 and that's sort of what I wasuding to before about sort of legal。

 whatever safe programs and things like that， right？

So what we seeing is going to foil my garbage collector， this conserved garbage collector。

 is if you use this pointer and you just keep incrementing it and you march off to something that's otherwise completely unreachable。

😔，Because that's going to be converted soon to be garbage and free。Okay。

So the correctness of this conservative garbage collector is only for the realm of programs for which the pointers。

That return formadic region stay within that region。If you have bad pointer behavior。

And you actually managed to read some other block。Through that point， it wasn't intended to reach。

 then this garbage collector will be problematic。Okay。

 but assuming that your programs don't do those stupid things or aren't hacked to do those stupid things。

hen this will work just fine and you saw this problem that you need to find the beginning of the block。

 so one approach would be to use a have sort of this balanced binary tree where the key is to start of the block。

And the header sort of builds up the trees， so I come in， I have this pointer。

 I come into my tree and I say， oh， is this less than or greater than and so forth and eventually I'm going to come to the block for which。

This pointer falls in the middle of， right？It does based， I'm going to eventually find this guy。Okay。

 because its address here is between this address and the address of the next hitter right and so binary research I will find mention。

Okay questions on that。All right， so that's garbage collection。

Now I want to conclude this lecture with a bunch of points about memory related perils and pitfalls。

In particular， we're going to talk about these is at seven。Pitfalls that are common。

 and you can see a lot of them are tied to things like malicin free。

 which is kind of one of the reasons we bring them up now。Because they may bite you in your own code。

 for instance。So just as a review， this is a chart out of the book， a little bit updated。

About sorry out of the Car and Richie book， so these are the precedents showing the precedes of operators or at highest precedes lower precedence。

And then within a pres class， the sosociivity， left to right， right to left and so forth。Okay。

 and if you look at that。For a minute， there is。Well problematic， right？

Because you see the same symbol appearing in more than one place。Okay， any guesses to。

Why does chart still make sense？Like a plus plus appearss a couple places and the atmosphere appearss in a couple of places。

even plus。Exactly， okay， our binary unit gives sort of the choices。Okay。

So a post fixed plus minus minus has the highest priority。

 but a prefix plus plus or minus minus is a lower priority， a unary。

 that's taking the address of something that has higher priority， the binary and operation。呃。

Has lower product。Okay。对。Okay， and so you know， we've done these kind of tests yourselves before。

 but you're going to want to brush up on things like this right， so this again is a point to an inch。

This is a。An array of 13 pointers ins。Not to be confused of this thing。

 which is I mean sorry which is the exact same thing。

 the parentheses here didn't matter and so forth point or to a point or two an in and so forth。

 so you want to I'll leave these to。Your own offline for you to think about these again， but again。

 you want to be able to understand。How to unrule these declarations in the correct way。可以。嗯。

So the first of our seven。Bad cases is just。Is dereencing a bad pointer？

So this is a classic example where you do a scanF。And。

So you're reading something and you're meant to read into this value。

 but you really needed the point of here。So it's not going to come out like you want， right？

The second one reading on a disized memory。So I mallic this large region。And then I'm doing this。

You know， operation where I'm running through and I'm you know doing a multi and accumulating these in theWs。

And all would be fine and good， except for the fact that I forgot to initialize all these AIJs。はい。

Maalck does not do the ination for you， and so the intention of the。Sorry， initialize all these y。

 the tension of this was you accumulate in this y array starting from zero。

 but you didn't actually zero it out。You can avoid this by using cac。

 which is guaranteed to zero out。The region。可以。😊，Is that clear？

' justI'm using y I've maled this array of y's， I'm using them to accumulate the sum。

 and I forgot that the y's never got in slice of zero。And so。

I'm actually the first time I touched this on reading uninized movement。All right， overriding memory。

So what I'm doing here is I'm malliking。嗯。Region。And then I'm using that the array。

It's a array of pointers and for each of the pointers， I'm doing a mallic。

Of a different size reaching。Okay， so what's wrong with this？Sniipet code。Yes。

 this is a size of paint， which should have size of n pointer and sizeic pointer。Exactly。

 right so this is going to give you， this is a bunch of pointers right。

 you're storing a bunch of pointers in something you've only allocated in for。Okay。

 so you should have allocated the size of a pointer。Good。

Another way you can overwrite memory is off by one ears。

So I'm sure you're familiar with this in your own code。

 trying to figure out in any loop body whether you should stop when it's less than or less than equal to。

 if you go one past， that's a problem。Another class example we've talked about in class is the Sterland。

So why is this a problem？I allocated a place for something that's the size of the string。

 and then I copy that old string into the new string。So why is that a problem。The k null at the end。

 right， didn't allocate a space for the null needed a plus one。嗯。

This one we've covered in Peter's classes right， you allocate a buffer that's not big enough。

 and so you just keep writing past a memory。呃。Misunderstanding porn arithmetic。

You do a plus equals on the size of an int。Now realizing that it kind of does that for you already。

 take seven count the sizes of things when you do the increment。嗯。

So here's one that goes back to our sociativity table， right？You've got the snippet of code。

And what is it doing？You're kind of pulling off the first。嗯。First thing in this heap structure。And。

As a packet， sorry， you take the header of this of this。嗯。You know， already。

 and you say that's the packet。And then I want to have everything but the pack so I assign to what's left over but now I realize that I've decreased the size of this thing by one。

 and so that's what I do here okay。But the problem is that the president order to wrong。All right。

 you really needed to have parentes here。哎。You see why， because it's's you want to。

You want this pointer。You pass it as a pointer because you wanted to survive this function call and so what you want is that sort of the thing that this size points to to be the thing that gets decorated。

 not the pointer itself。😔，Questions that。We're referencing nonexistent variables。

Forgetting local variables disappear when a function returns。Okay。That a big classic example。

Frame blocks multiple times okay so here you had all the best attention in the world。

 you allocated X， you did a whole bunch of stuff with X， and then you free X， you allocated Y。

 you did a whole bunch of stuff with Y， and you meant to free Y， and everybody would even happy。

 but you freed X。Okay。So you've createdd the same block multiple times and you havet fruit black。谁。

So here's a similar kind of thing， you've had this X you've allocated。

 you manipulated you free as before， you have this Y you allocated and you're happy here but。

Maybe you meant to put a Y there or something I don't know。

But you certainly didn't mean good x because you've already3 x。failingai to free altogether。You know。

 some people elect their default。They don't want to think too hard about making mistakes about what they free。

 so they just don't free anything。😔，You know， for little。Short little codes。

 that's probably not a bad program or productivity strategy。

But if you're writing code that anybody's going to use。あい。This memory leak is going to kill you。嗯。

So here's one you may have stumbled on in the past yourself。

 so what I've done is you've got this list。😔，List data structure， you've created this entire list。

 you've got some linked list here。And then you say， well， I'm done with it， and so what should I do。

 I should just free the head of the list。And in your head， you're thinking， oh。

 that means I've free the entire list， but you're have because all these individual list items。

Haven't been freed in the eoscopy free。この呢？人。All right， so these kind of memory bugs。

 which we all fall into。You know，Unfortunately we have some tools， GDP。Can。

It's good for finding some things， but not so much others。The one that's become， this just came out。

啊。About 2004， it's a really nice tool called Valride。That provides a lot more of for。嗯。

correctectness checking kinds of tools。Then then say GDP。

You can plug in separate tools to check for different kinds of mistakes。Okay， there's a。

So you sort of customize the run of it to based on whatever tools you want it does it by the neat thing about is it doesn't even need the it's all a binary translator。

 it doesn't need source code， it just takes the binaries a particular binary and it basically patches it up it rewrites the binary to do make all the calls。

 the stuff is interested in and then track all the stuff and flag the ears。

 things like that so that's nice。For so that's again a general purpose tool。

 specific data structures well often you can write checkers right we encourage you for some of the things you do to write checkers like a He checker or whatever to make sure that things are consistent as you hope there would be。

嗯。So these you can find are in this class erect your own。嗯。

And then the Gliby malik containss some check and code as well。

 you can try out setting environment Malic check three and see what kind of help you get in that sense as well。

Any questions？All right， that's it for today。Good luck， making good progress in your Maet Las。C one注。

な问。

![](img/410f0b7d50dc9c64e6c0b83c352944a0_11.png)