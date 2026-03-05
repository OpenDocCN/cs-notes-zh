# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p17 P17 Write your own Operating System 16： Dynamic Memory Management ⧸ Heap -BV1BDBEByEBY_p17-

Hello and welcome to the 16th part of the tutorial and writingriting your own operating system。

In this tutorial， we will talk about the heap and dynamic memory management。Because， yeah， right now。

 we have allocated everything very statically， know， in some functions we。

Just have these objects and they are allocated on the stack。嗯。But， yeah， sometimes。

You just don't know in advance what memory you need。 For example。

 when you iterate through the PCI devices and you find a device that。嗯。

So you find a device and then you need to instantiate a driver or you need to reserve some space for the driver。

And then of course， you need to keep track of the space that you have already assigned to something because you don't want things to overlap and disturb each other。

Okay， so。What I'm going to do is actually quite easy。So if you've had lectures on data structures。

 if you know linked lists， this won't be very surprising for you。嗯。So here's your re。And yeah。

 we've talked about this before。So you have your video memory， the memory for your text then。

The the bio。It's loaded somewhere。 the bio has loaded the boot loader。

The boot loader has loaded the kernel。And the kernel has its stack。And then， after that。

There is a lot of nice free space that we can use so we can， yeah。

 we can assign this and use this any way we want。嗯。

Although I'm not really sure I haven't found a way to find out。😔，诶。

If Grub has put something behind the kernel， you know， it might have written something here。

So for example， the multibu structure， which we will talk about later again。

We don't know where it is。 It might have loaded modules。 they might be behind the kernel。Yeah。

 we really don't know。How much space there is。 And as I've said。

 I haven't found a good way to find that out， so。What I'm going to do is， I will just。

Take the pointer to the。啊。To the stack。And。And then I will just add something like。

 I don't know for megabytes to it。And hopefully， that is enough， so。

So that we don't overwrite anything。And there are so。😔，Yes， this is also actually a method。

That where was it。 I'm not sure if it was on OF or low level Eu。 they really。Said that。

This is the way you should do it。 You should。They advise you to really take a fixed offset and say everything behind that belongs to me。

Yeah， if you ask me， there really should be a better way， Grub should tell us。嗯。

Well it put the less data。 But as I've said， maybe there is some way to find this， but。

I haven't found a way to。To ask for this。And I've really given up on the topic。

 so this is really how I'm going to do it， although I don't like it。啱。Yeah。So how will we do this？😔。

And do I have a better。陈。So how are we going to do this？ Yeah， as I've said。

This is really very similar to a linked list。😔，So we will make a class called Me manager。

And give it this point up。And then， some size。This size， at least we can get from Grub。嗯。呃Yeah， so。

So then we are over here。嗯。And what I'm just going to do is I will write a class。Memory trunk。

Which is supposed to have。Point out to the next memory chunk and the previous memory chunk。

Then a guion。Which tells us if it is allocated。And。The size T for the size。

I think size T we haven't defined yet， but this is really common practice。

 I will just put that into the types dot H。嗯。Yeah， so such a memory trunk really describes。

The memory manager will be responsible for handling the space over here。 Okay。

 so this is the space it's responsible for。 And then we will。Ask the memory manager， hey。

 give me 1024 bytes。Okay and then it's supposed to find some area in the Ram that is large enough and give us a pointer to it。

ok。In these memory trunks。A basically a linked list。Double linked， actually。And okay， this is。

 this won't be a fast implementation， but。For every chunk that we've cropped from the Ram。

 we will have an entry in this list。Which correspond to So this is how we keep track of the data that we have already used and。

The data it is free。嗯。But the question arises， where do we put these values mean。

When you do a linked list in the data structures lecture， yeah， you just say， hey， I want。

 I want to allocate。A new node。Yeah， but how do we can do this here。

 Because here we are currently writing the code for。Give me a new note。Right。We cannot say， hey。

 I want a new memory trunk because we are writing the thing that gives us the response to that。Okay。

 so。So， we need to think。About how to decide where to put these objects。

 So we have to manage that really manually。But the thing is， we have a lot of RamM here。Okay， so。

We will just use the Ram here for this list，And memory， many people。

Preferre to put just some table at the beginning of this。Area。And keep track of things in this table。

I。We'll do it like this。😔，嗯。I will put。These objects just at the beginning of these chunks。Okay。

So if you。If you request。1024 right。嗯。I will actually chop off 1024 plus。Size of。Memory trunk。Okay。

So then we have。The next pointer， the previous pointer。The info， if it's allocated and the size。Okay。

哇。And yeah， as a convention， I will just。Have size。

Be the size of the data that is actually used here。 So if I allocate 1024。

 then there will be a 1024 in here。Although this is more than 1024。 Okay。

 so this size is only telling us。How much data is behind that chunk behind that header。ok。And then。

 I want the。I want these pointers here in a linear order。The next pointer is going to the next entry。

😔，And the previous pointer is going to the previous entry。😔。

So so the next pointer is going to be to the chunk that has the smallest。

Offset larger than these ones， Okay， so these pointers will never cross each other。

We will not have a pointer to a chunk over here and that has a pointer back here or something that will always be in a linear order。

Okay。So。Yeah， this isn't。This isn't hot， I think。One thing that I want to mention， when we free。嗯。

When we freeze the memory again， if we delocate it。嗯。Yeah。Let's say this。This chunk here is free。

This one has been allocated， so there was a one here and says this one is also free。So。

If I just set this allocated to false。This is somehow stupid， because。Say， if I have。10 with 24 here。

10 with 24 here and 10 with 24 here。And now I tried to allocate something like 2000。100 or 2500。

 Then it would come here， see， okay， the size is too small。 This size is too small。 I'll continue。

 This size is too small。 I continue。 This size is too small and continue。

 And that's not really what we want， you know， because。

If this is not allocated and this is not allocated and this is not allocated。Then these together。

Large enough to hold this 2500。So what I want to do is。

I want to prevent the situation that we have more than one chunks。Which are not allocated in a row。

Of course， you can have multiple chunks that are allocated in a row。

 but I want to prevent the situation that we have multiple。Unallocated in a row。 So if I。

If I delocate something that has neighbors to some free space， and I will merge。It， again， was。

The previous one， I mean， if the previous one is。Free。

 then I will merge this and if the next one is free， I will merge this and if both are free。

 then I will merge this first。So， that。We have this situation。2048 plus the size of a memory trunk。

And after that， I merge this chunk with this。 So this really saves us a lot of cases。

If we do it like this， if we merge。This first， and then this。We only need two cases instead of four。

Okay， so yeah， how will the situation be when we start？When we start， nothing is allocated。So I。

If nothing is allocated。嗯。Then I can have only one chunk。Because otherwise， if I had two。

 these would be two consecutive chunks that are both free。And I want didn't want this。

 I didn't want to allow this。So we will start with one chunk with a full size。

So this is the first chunk， so it previous pointer will be set to0， it's also the last chunk。

 so its next pointer will be set to0。It will be not allocated and have the full size that we get from the kernel。

Okay， and when we allocate something。嗯。Then we will try to。Chop off。

 then we will try to split the chunk。And other we will set。This next pointer here。

 this previous pointer here。啱。This will be allocated， then this will not be allocated。

This will be the size。😔，That we have requested， and this will be the size from before minus the size that we have requested。

 Okay， I think that makes sense。嗯。Something。If。There is a chunk after that。

Then his previous pointer is。Still pointing here。 we have to take care of that situation also and。

Move it over here。 So this is really nothing surprising if you know linked lists。

Just a little bit of。Of working。And yeah， but since we really decide the locations of these memory chunk instances。

嗯。Yeah， we have to do some extra fiddling。That you wouldn't have in when you。That linked lists。

Normally， but yeah， it's not that bad so。Let's just program this now。う。So。

I will comment these tasks out。

![](img/78de33d16cf722ce44753100b4fc2326_1.png)

![](img/78de33d16cf722ce44753100b4fc2326_2.png)

![](img/78de33d16cf722ce44753100b4fc2326_3.png)

Yeah。Yeah。そ。Yeah， so on a 32 bit system， the memory addresses are 32 bit。

And that is why we set size t to U 32 here。😔，On a 64 bit system。

 we would set this to you in 64 instead， because then we could de referenceence。嗯。64 bit。Intrus。Okay。

 the memory manager will have。A pointer to the first chunk。😔，But it doesn't have to stall。😔。

The size is because the size is actually stored inside the memory trunk。Okay，m。So， we。

We want to call it the。A location later from functions from and functions aesthetic， so。Yeah。

 like with the interruptop Ttler， we will have something like an。Active。Memory managertra。Mhmm。

Which we were just set to this in the constructor。Yeah。Yeah。Yeah。O。This is how this is going to look。

Ok。So。In the constructor， as I've said， we will set the active memory manager to this。😔，And then。

 we will set the first。Trunk。To。To the address that we get here as first。好了。Yeah。

So the start is the offset where the memory manager is going to。

The data that the memory manager is going to handle。So this is where we put the first memory trunk。嗯。

Yeah， but if the size that we get here。😔，Isn't sufficient。And this。Yeah， it might happen。嗯。

We should really protect ourselves against the situation， because。If the situation arises。

 then we would be writing outside of the。Of the area that we are allowed to write。So。Okay。

 it's not really。It's not really likely that this happens， but to make sure。Yeah。Okay。So。

So the first trunk is not allocated。😔，As I've said， the first next point are0。O。对。Yeah。Okay。Okay。

 when we try to allocate something。We will iterate through this list of chunks。

And look for a chunk that is large enough。So this is really how you iterate through a linked list。So。

When we find a chunk that is free and large enough then。We set this result pointer to that chunk。

And in that case， we can。Also， terminate this loop。Okay， after that， if we haven't found anything。

Then we， then the result are still 0， and then。Yeah， without paging。

 then we are lost and we just have to return zero。Okay。No。No。Here， when we reach this line。

 then we know that the result is set to something。So， we can look。So what I'm doing now is。



![](img/78de33d16cf722ce44753100b4fc2326_5.png)

I want to。 So if I find a large chunk。So， maybe this is。30 mebys， and I only want 10 B。Then。Yeah。

 then I drop off 10 bytes and put the next memory chunk instance here。But。Yeah。

 what happens if the size isn't even。As large as what we've requested plus the size of a new memory chunk。

Well， then we cannot split it then we。Then we would just have。Yeah， some bys left over here。

 so the program that requested。The data will just have a few bytes left over。Waste it。

So we can only split this if the requested size plus the size of a memory chunk is larger than the size that has been here before。

It's less than。 And this plus one that I put there is。If you don't put this plus one。



![](img/78de33d16cf722ce44753100b4fc2326_7.png)

Then you would split the chunk into。😔，The requested data plus only the header for the next chunk。

 but it would have size0 and that wouldn't make sense， right？So if the chunk is too small。

 then I just mark it as allocated。😔，And in the other case， we make a new chunk。And we put that。😔，超。

The position of the result。😔，Yeah。

![](img/78de33d16cf722ce44753100b4fc2326_9.png)

So。

![](img/78de33d16cf722ce44753100b4fc2326_11.png)

So here's the result point。We add the size of memory chunk to get here and then the size that has been requested to get to。

The position for the next chunk。Yes。そ。Saw the result。Later will be。Well get the size。

That we've requested。😔，And。The new chunk that we've cut off at the end will get the size of the old chunk minus what we have requested。

😔，Yeah。Yeah。Okay， and then we have to。And we have to modify all the pointers here。😔，い。Okay。T部。

Next becomes。What was the next before？😔，And if there is something。😔。

Its previous point I must be set to1。😔，Actually， we can just move this down here。😔，人题。Frilips this。

Okay， so if the result is larger than what we need。😔，L enough to split。 then we split it。

 then after that， we。Mark the result as allocated。And then。好。



![](img/78de33d16cf722ce44753100b4fc2326_13.png)

Okay， so。The result pointer points to the start of the memory chunk。😔。

And now I return this address plus size of the memory chunk。

 so this is aer to the beginning of the region that I have allocated。



![](img/78de33d16cf722ce44753100b4fc2326_15.png)

嗯。Okay， so in the free。

![](img/78de33d16cf722ce44753100b4fc2326_17.png)

First， so。We have given the guy who requested the。Memory the pointer here to the beginning of the free region。

 and this is what we get back when he freezes。This region again， so we get the pointer here。

 but we need a pointer to the memory trunk， so we will subtract。Size of memory chunk from it。



![](img/78de33d16cf722ce44753100b4fc2326_19.png)

嗯。Okay， and now we'll do the merging that I've talked about before。Yeah。

So to merge the chunk with the previous one。😔，We set the next pointer of the previous one。😔。

To the next of the chunk。And also。If there is a next one。😔，Yeah。Yeah。

So we've removed it from the forward linked list， we removed it from the backward linked list。😔，And。

And then we just add。😔，The size that we have freed。

 including the memory chunk to the size of the previous chunk。什。And then， we move the。

Then we move this chunk pointer to the previous chunk。



![](img/78de33d16cf722ce44753100b4fc2326_21.png)

And by this， we now have a situation where we know that the region that the chunk on the left of the current chunk is allocated or not existent。

And。So。So what we have done now is。So we have。😔，We have changed this pointer to go over here。😔。

And this pointer to go over here and we've changed the size we've added。😔。

Or this to the size of this chunk。 And now before we had the pointer here。

And we've changed this also， we've set it now here。😔，So it looks。 now it looks like。

Like we have been freeing this whole chunk。😔，And the trunk on the left is。Is allocated。Okay。

So this is allgon now。

![](img/78de33d16cf722ce44753100b4fc2326_23.png)

And this is how the situation looks now。So。So now we know this is allocated all now。

And now we have to look so the pointer is now here。

 so it looks like we have been trying to freeze this。

 but nothing but the space on the left of the pointer is allocated。😔。

So now we just look into the case that the thing on the right is also free。

 and then we have to merge this。This new chunk with the next chunk， also。So。Yeah。

And here we basically do the same thing。没有。So we just increase the size of the chunk。😔，嗯。Okay。

So we swallow the next chunk。😔，Okay。好。Yeah， so。If the new next chunk。Exists， then。

We set its previous pointer to ourselves。😔，O。So this should do everything we need。😔。



![](img/78de33d16cf722ce44753100b4fc2326_25.png)

I mean， it does that in a relatively slow way。 know if we allocate。A million bys， one by one。Then。

The next allocation will take a million iterations to find some free space， but。Yeah。

 I think you will be able to come up with better ways of finding free space。Like。

Keeping track of the free chunks and maybe have larger chunks so that。Oh。Yeah。

 I think really this is what a memory page actually is， it's just a chunk with a certain size。

And when you allocate。Some chunk， then。You allocate the full page， maybe I don't know。

 maybe a megabyte or something。And you assign that to the program that requested it。

 So when it requests more， then you chop off more from that one MBgaby。

 And then then you don't have to jump in these small steps。

 Then you could jump in megaby steps through the Ram。



![](img/78de33d16cf722ce44753100b4fc2326_27.png)

To find a free page。Okay， so let's put this in the make file。😔，Yeah。

So now I'm going to instantteniateiate one。😔，And the question really is， what values do we pass here？

😔，um。I would just hard code。😔，This to start at 10 megabytes。嗯。But yeah， what。

What should we use as the size， I mean， we've given the virtual machine 64 megabytes。

 so we could use just 54 megabytes as size here。But that wouldn't be portable。

 So what I'm going to do instead。I mean， as far as I know， there is a。There is a bias interrupt。

Which will give you the size of the memory， but。I really don't want to go into interrupts inside the C code。

 inside the C+ plus code， so there's actually a better way to get this。So。Yes， the situation is this。

We are getting this pointer to the multiput structure from G， right？And。😔。

So far we haven't done anything with it， but when you look into the multiput dot H from the group project。

 also known as Linux。嗯。Then you will find this structure here。😔，The multi boot in。Okay。

 and there you see how this data is structured。 So you could just copy that multibu dot age and include it。

 and then you could。Could use multibo In pointer instead of Vo pointer。嗯。But for copyright reasons。

 I'm not going to do this here。嗯。Yeah， what I'm going to do is。I'm counting here， so this is4 bytes。

This is4ytes。So after 8 bys， we come to this integer。Mm upper。

 and this really tells us the size of the Ram。In kilobytes。Okay， so。What I'm going to do now is。Yeah。

So I'll take this pointer to the multibo structure， add8 bytes to it。😔，And cast the result to an。

U in 32 pointer。And then here as size， I will just take the content of that pointer。

Multiplily it with 1024 because it is in kilobytes。And I will subtract。😔。

The address where the heap starts， and I will also subtract。嗯。Yeah，10 kB of padding behind this。

Behind the heap， okay？So。Yeah， you know， something that I have tried before to really not hard coat the heap。

I I tried to put。A pointer here behind the kernel stack。And then。Make it global。 And in the kernel。

 I would have Xter C white pointer。Heap。And then you would have to take the address of that heap。

But I don't know， I've had all sorts of problems with that and as I've said。

 I've really given up on the subject， I just hard codings this to 10 megabytes and hopefully we are good for some time。

😔，Okay， so。

![](img/78de33d16cf722ce44753100b4fc2326_29.png)

![](img/78de33d16cf722ce44753100b4fc2326_30.png)

![](img/78de33d16cf722ce44753100b4fc2326_31.png)

![](img/78de33d16cf722ce44753100b4fc2326_32.png)

嗯。AndThis should be appointed to a chunk， of course， not to a memory manager。😔。



![](img/78de33d16cf722ce44753100b4fc2326_34.png)

![](img/78de33d16cf722ce44753100b4fc2326_35.png)

![](img/78de33d16cf722ce44753100b4fc2326_36.png)

Yeah。

![](img/78de33d16cf722ce44753100b4fc2326_38.png)

Okay， and now you see the he starts at。10 megabytes。

 And here we have allocated something that starts at 10 MBbys plus 10。Bs。X aresimmal 10， 16 bytes。

Yeah， that makes sense。Okay， so。This apparently works。As I've said。

I've had so much trouble with this， and I don't even dare say that it does work。I only dare to say。

 it seems to work。

![](img/78de33d16cf722ce44753100b4fc2326_40.png)

So okay。Yeah。So now we can allocate memory。嗯。But。Only if we have this。APoer to this memory manager。

 but we have a static pointer to that。嗯。So what I want to do now。I mean， we on the command line。

 we have deactivated the new， the inclusion of the new operator in。FromFrom the compiled code。So。



![](img/78de33d16cf722ce44753100b4fc2326_42.png)

So we can allocate Ram， but normally we would want to to allocate it more in a。In a way， like。

Not really getting a void pointer， but we want to get， we just want to say， hey。

 I want a new object of this type。I know that's the C+ plus way of doing it。You know。

 this is very C like what we are doing here。嗯。So what I'm going to do now is I'm going to the interrupt thatt H。

And here I'm going to include this memory managementment。 age。😔，Wai。

 I didn't want to do this in the interrupts， I wanted to do this in the PCI。😔，Okay。

 and then in the PC I CPP。😔，Here， I want now to do something like。So here I want to set this driver。

😔，嗯。To something like。义呜。AMD。Something。う。嗯。Okay， so I could do it like this。😔，嗯。No。

 actually I couldn't do it like this because I haven't written this new operator。

So this is what I'm going to do now， and I'm doing this outside of this my O S namespace。

So these are the two。😔，Versions for U。And for delete。O。And I will implement this。Basically。

 by just going to。嗯。😔，By going to this active memory manager。Yes。Okay。Strangely enough。

The other one is just a copy of that。Looks kind of wrong to me， but。Whatever。



![](img/78de33d16cf722ce44753100b4fc2326_44.png)

By the way， this is a point where we now have a delete operator again。

This is a point now from which on you can use virtual distractors again。



![](img/78de33d16cf722ce44753100b4fc2326_46.png)

Okay， so if I do it like this。Then in this PC I dot CPP， I can actually just say driver equals new。

Type and。Give it the parameters to the constructor。



![](img/78de33d16cf722ce44753100b4fc2326_48.png)

But here's a really big problem。あ。So if we don't find any place to put this requested object。

 this requested memory。😔，嗯。Yeah， then the loop terminates and returns null。it just returns zero。

So I'm not true about this， but I think。Moc is apparently supposed to throw an exception if it doesn't find memory。

So normally N C++ when you say new。It calls malloc。

 and Meloc doesn't find anything as an exception as thrownrone。

 but we don't have any exception handling yet so。So we only can return zero instead。

Which is how malllo did it a few years back， if I remember correctly。But the thing is now this。

If Manoc just returns0。Then this new will， since no exception has been thrown。

 then new will just say， okay， I have gotten something， I will use this。And， normally。Yeah。

 since you have gotten zero， this would mean you are dereencing an I pointer and you get an exception。

 an I pointer exception。嗯。That is what would happen in user mode， but we are in currentlyly mode。

And in kernel mode， yeah， you have access to the memory location zero， you know。

 another pointer is just a pointer to the memory location zero。

So if new gets this illegal return value0， it tries to access it and in kernel mode。

 it's allowed to do that。In kernel mode， you are allowed to do reference an eye pointer。So。

So therefore this you cannot really do it like this。😔。



![](img/78de33d16cf722ce44753100b4fc2326_50.png)

So what you would have to do instead。This。We need to make two new。😔，News versions。

Called the placement new。嗯。And in the implementation。😔，They just return。😔。

They just returned this point。😔，So this is called the placement new operator， if you look for this。😔。

This is what you use when you。When you want to call a constructor explicitly on ReM that you have already allocated in any way。

Like this， there is also a placement delete for explicitly calling。The de， but。

So this is how that looks。And then inside the PC ICPP， you can do this。😔，So， you can。

Alllocate the Ramm， explicitly。So。You allocate a memory region of size。

Of the size of the class that you want to give here。

And then you have to check explicitly if this is zero。



![](img/78de33d16cf722ce44753100b4fc2326_52.png)

And only if it's zero， only then you call the constructor explicitly。



![](img/78de33d16cf722ce44753100b4fc2326_54.png)

Like this new。Drive up。AMD。And here you put the。The parameters。 Okay， so this。

 we haven't written this class and we haven't defined。



![](img/78de33d16cf722ce44753100b4fc2326_56.png)

The parameters of the constructor， but that is what we will do next time。



![](img/78de33d16cf722ce44753100b4fc2326_58.png)

So yeah， so this is all we need to do for the memory management。😔，Yeah， as I've said。

 it's not really fast but。It does a job and it's a starting point so。As I've said。

 I think you can come up with better ideas。嗯。You probably should be going into virtual memory fast。

So that you can really work with virtual addresses and then the processor will tell you if a program tries to access。

A page that currently isn't in the memory and then you can do the paging and write some page to the hard drive and different and load the requested page back into the Ramlet。

嗯。Yeah， and my personal experience。I've seen computers really go down on their knees when they start with the paging。

 So my experience is when the。Computer starts paging， you're screwed anyways。

 you're better off rebooting it。So that's why I have never actually written code for paging， but。

Yeah， I mean， for what we are doing with 64 as megabytes is sufficient anyways。So yeah。

 now you have a heap， now you can do dynamic memory management。And。Yeah。

 next time we will use this here in the code for the。

PCI to dynamically instantiate a network car driver， and then we will start。



![](img/78de33d16cf722ce44753100b4fc2326_60.png)

Talking to the network。So yeah， don't forget to subscribe so that you don't miss the next video。

When we start talking to the network。If you liked this video， hit like。And yeah， see you next time。系。



![](img/78de33d16cf722ce44753100b4fc2326_62.png)