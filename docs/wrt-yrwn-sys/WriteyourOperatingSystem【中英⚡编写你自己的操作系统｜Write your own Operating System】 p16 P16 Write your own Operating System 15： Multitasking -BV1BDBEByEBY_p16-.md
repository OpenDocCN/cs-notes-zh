# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p16 P16 Write your own Operating System 15： Multitasking -BV1BDBEByEBY_p16-

Hello and welcome to the 15th part of the tutorial on Writing Your own operating system。Now。

 in this 15th part， we will be going to。Yet to multitasking。诶。I'm really excited about doing this。

 This is something that I very recently have gone into。

So this is something that my own operating system that you find on my website cannot even do。

 So I've written this for。For our common operating system， and。I'm going to show you this today。

How I did this。So I'm coding it again with you watching。Okay， so what is the idea of multitasking。So。

Here's Hill Ram。Okay， and。Let's say here is the interrupt handler for the time I interrupt。啊。

For general interrupts， maybe even so the interrupt steps do S。

Say here's a code that the processor is currently executing。So it is jumping around here and。

Somewhere in the rem， there is a stack。Okay。So here's the stack。It's growing to the left。Okay， so嗯。

The processor is executing the code here and pushing stuff， popping stuff， and so on。

And now a time I interrupt occurs。What now happens is the processor pushes some data on。The stick。

Some registers。It's save some registers， for example， the instruction pointer so the pointer。诶。

Where he has been。Before。Before the。Interrupt occurred。

 and then it goes into our interrupt step start age。Where we push some oil。Registers。Okay。

And then we go into the handleler method， it can push some stuff inside the methods and overrite register in the processor when we come out of this again。

Then this is already。Okay， so these values are put back into the processor。

 and then it jumps back into。Yeah， into the。To the address where he has been before the interrupter occurred。

Okay， so somewhere in here， there's the instruction point up。Okay。

 and this is actually really necessary to store these values and store these values that we store manually because。

Yeah， you never know inside this handler methods。We don't know what happens。

 The registers could be overwritten。And if we didn't install them， we would just jump back in here。

 then this would probably just break everything。嗯。So the task that has been running here may really be broken if we didn't restart the values from before。

Okay， so this is how things happen right now。And what do we have to change to do multi threading？

Okay， so let's say yeah。So what we do is we just take。Another。Portion of the。R。

And we will just make another stack there。 Okay， so this has been our kernel stack。And here。

 we will put。Yeah， really for every task that we have， we will have our own stack。So。

So this is the memory that we reserve for this stack。And what we do now is。Yeah。

 we just put values for the processor know phony。Values。For this。We push that on the stack。Actually。

 we don't push。 we write them。Explicitly。Okay。嗯。So when we create a task， we create this。

 we get this。MemoryMemory region and we just put values for the processor in here like for example。

 A X， B X c X and so on will just be initialized with0 and in particular the instruction pointer down here will just be the。

We will put that to the entry point of the task。Okay， so。Yeah， if you have programmed with projects。

 threats， then you probably know this P thread create function and it gets a function pointer。

Yeah to the function that is supposed to be run in a separate thread。And yeah。

 this is really what this P3 create method does。 It takes this function pointer and puts it there。

If somewhere。😔，In this， in the memory， you have the code for。For the task。

 So this is a code of the task。And here's the entry point， usually it's just the first。Yeah。

 I don't really know it。😔，There could be a header in front of it， but。

It doesnn't matter so this is just set to the entry point。Of this code， of the function that is。

Supposed to be run in a separate task。And。Okay， so what we did。Here。You know in the interrupt steps。

 we pushed these values and then we pushed the instruction point。Not the instruction pointer。

 we pushed the stack pointer。So， and this was really a parameter to the handle。

Interrupt function in the interrupt dot。CPP file。 Okay， so。The handle interrupt function。

Gets the pointer to this stack here。As a parameter。

And what we do after we return from this handle interrupt。 So the handle interrupt returns。

Another value for the， for the stack pointer。And。This is actually。

When we return from the handle interrupt， this is written into so the return value of handle interrupt is written to ESP。

So， normally， we。Oh。We pushed the stack pointer。Then handle interrupt。

 did something and handle interrupt just returned this EP that we pushed before， and then。

This was copied。 So actually， nothing really happened because this has been。The same like before， so。

So we didn't really change anything ESP has。Has pointed here anyways。

 but we have overwritten it anyways。 So what we do now instead is。嗯。

The return value for the handle interrupt method。Well， just instead。

Return a pointer here to the top of this stack。 Okay， so then the。Interrupt steps。ButS。

We'll copy this here。And to ESP。Instead。Okay， this point， we should store somewhere else。

So that we can continue running this task。Again， later。

And so the pointer to this deck is returned here。And now what happens the。

The interrupt steps thatt S and also the current the CPU。嗯。Copy these values back into the processor。

And， in particular。This pointer down here is written to the instruction pointer。Okay。

 so what happens now is。After we did this， the processor is not going to jump back here and execute this。

 it's going to jump down here and execute this， and this is how the task switching works。O。So。

 I think this should。Really explain what we are doing。So let's quote this。Yeah， as I've told you。

Put all the stuff with a graphics mode in this， if defined graphics mode here。Okay。

 so all the graphics mode stuff is gone。Now let's see。

 I will put this actually in the top level here。😔。

![](img/1a155ef902e8069c9e3686ee180cda77_1.png)

![](img/1a155ef902e8069c9e3686ee180cda77_2.png)

Yes。So I will put a class for tasks。 class task。And the class。Task managertro。Okay， so the task。Yeah。

 the task manager might have to work inside the。The private values of the task， so make it different。

Okay， so here I just。I just allocate some stack。Yeah。I'll just use 4 kiloby for now。



![](img/1a155ef902e8069c9e3686ee180cda77_4.png)

And also， I will have a pointer to the。Yeah， to the hat。 Yeah to the。To the top element of the stack。

嗯。But I would put a data structure over this over these areas， you know。

 with CPU pushed and user pushed data。 So， and I'm going to call this CPU state。



![](img/1a155ef902e8069c9e3686ee180cda77_6.png)

![](img/1a155ef902e8069c9e3686ee180cda77_7.png)

So the pointer to the top is actually a pointer to a CPU state because。Yeah。

 the data that you find there is。It's the state of the CPU。



![](img/1a155ef902e8069c9e3686ee180cda77_9.png)

Okay， so the task will need to in the。In the constructor。

 the task will have to talk to the global descriptor table。

And it needs a function pointer to the function that is supposed to be executed。Like this。

Okay and the task manager will basically have an array of these tasks。

The number of tasks in this area。And the index of the currently active task because。



![](img/1a155ef902e8069c9e3686ee180cda77_11.png)

That is where you will store。We push this ESP。And the pointer to this is。

Over Britain after the handle interrupt is finished。 So we need to。



![](img/1a155ef902e8069c9e3686ee180cda77_13.png)

We need to store that somewhere。 So because otherwise we couldn't。

Go back to the to executing that task， ever。見やげま。Okay。

 and that's what this current task is needed for。And here we will have a method。



![](img/1a155ef902e8069c9e3686ee180cda77_15.png)

Wwhichch does the scheduling， we will just use round robin scheduling。

 so we will just have this linear array of task pointers。



![](img/1a155ef902e8069c9e3686ee180cda77_17.png)

And then。Every time one task is executing and we go into this time I interrupt。

 we will just go to the next task， next task， next task。And start over at the beginning。

That scheduling strategy is called ground Robin。Yeah。Okay， and yeah。

 I haven't defined what the CPU state is now。う。O。What is in there？

So we have the registers accumulator， base register， count register data register。Stick index。

 data index。And stick base point on。😔，我分。When。One integer for an error code。

 I will go into what that is for。So here's the instruction point。😔，Stick point。And stick segment。😔。

Yeah。うそ。And also， this。Elements that we have been pushing so far already， so。G S， F S。E， S and D， S。

てます。Okay。There are some missing。😔，So we have the instruction point as a code segment。😔，Flaex。

Stick pointer and stick segment。Okay， and the values down here are the ones that are being pushed by the processor and everything up here。

Is what we push。In the interrupt steps。O。Okay， so the constructor of the task manager just sets no tasks。

😔，To zero， because we have no tasks。In the beginning。And the current task。To minus1。😔。

Because it's not set to anything legal inside array。Okay， at task。So if we already have 256。😔。

Tasks in there。 Then the array is full。So then we just returned false。And otherwise， we put the task。

😔，嗯。The next free spot。And return true。Okay。Yeah。好。O。然后。So the CPU state here。

Its supposed to be a pointer to the start of this block here and for a new task。

 this is just all the way to the right。So。U。So we will set this。😔，Just to。

Just as a pointer to the stack。So the pointer office。Your starts as stack plus。The size of the stack。

But minus the size of。Of the CPU state。Okay。So start of stack plus size of stack。

 minus size of the entry。Okay， and now we'll just set phony entries here。Yeah。This is。

 I comment this out because this only has to do with。If we。

If we are dealing with user space and different security levels and we are not doing that for now。

Now the instruction pointer is set to the entry point。The state segment is also not used。😔。

When we are not dealing with different。系ello。😔，With different security levels。These flags are set to。

0 x2，0，2。Okay， and I will also， what do we have？😔，What do we have。Yeah， the error is popped anyway。

 so we don't need to。Go at that。I'm not sure this is really a good idea。😔，I mean， this is the。

In the data segment。I'll just comment that out。Okay， I'll just remove all this stuff with the GS F。

 S， E， S and DS， S。Okay。Okay， wait， I almost made the biggest mistake。😔。

Here's a CS in the tutorial that I've read， they just set this to eight。

And I did that and I got a lot of general projections， which is the equivalent of a blue screen。

 and then I set this to 0 x 10， so from 8 to 16， and then it worked。嗯。But。

I don't think it's a good idea to have a magic number here， because it's。

Because the value that you put there must really be the code segment selector from the global descriptor tablever。

The offset of the code segment。I mean， you can hardco this。

 but I really don't think it's a good idea。So taking this from the global descriptor table is。

 I think a much better idea。O。し。Now， what do we do in the schedule method。So if the。

If we are not having， if we don't have any task yet。We just returned the OH CPU state。

So we don't switch the task then。So if the current task is。😔，So if。

 if we are already doing the scheduling， then we。We store the O CPU state。Okay。

 so we store the old value。 We， we put the task back into the list of tasks。

And here we just do the round Robin。嗯。So if current task exceeds the size of the array。

 then we start over at the beginning。And then， we return the。The new current tasks。A task。Okay。Okay。

 so this is all we need to do in this file。嗯。

![](img/1a155ef902e8069c9e3686ee180cda77_19.png)

So notice this。If we go in there。So if we really do have tasks。嗯。The first time we run into this。嗯。

When current task is -1。

![](img/1a155ef902e8069c9e3686ee180cda77_21.png)

Then we， we don't store it away。 And this happens with the kernel stack here。

But this only happens after we started the interrupts and that is a reason why in the kernel。

 the interrupts activate should be the last thing you do because after that。



![](img/1a155ef902e8069c9e3686ee180cda77_23.png)

You just don't know when the processor jumps out of the kernelel's deck and into the tasks。

 and it never goes back to the kernelels deck， so everything after this interrupts activate。

Then isnt might not be executed anymore， so that's why this really should be the last thing here。



![](img/1a155ef902e8069c9e3686ee180cda77_25.png)

And that is why this desktop draw here will break when we go into multitasking。

And then you should just have a different task for the redrawing here。Okay， so in the corner。

I will just make two functions for tasks。Okay， like this。Right。O。And then。You' right after。

The global descriptor table， I will instantiate the task manager。Yeah。Then two tasks。Okay。

 the reason why I instantiateated it up there。Thiss because the interrupt handler will need to talk to the task manager to do the scheduling。

Okay， so。Now， we need to go back into the。The interrupt stuff。And the interrupt manager will have。

Apointer to the。Task management。And this is。So we'll get that。From here。Yeah。Okay， here。Okay。

 so now the interrupt manager knows the task manager。哦。O。This is getting a bit out of hand。😔，Okay。

 here in this do handle interrupt。啱。Yeah， it's actually nonsense to do this in here with a setting ESP again so we could actually remove that from the interrupt handlers。

 but I'll leave it there right now。So if we have a time， I interrupt。Then。嗯。Yeah， then I'll set ESP。

😔，2 task manager scheduled。O。You could。You could fix the data types here now so that the U end 32 becomes a CPU state。

 Instead， I think that would be a little bit more clean。あ。Okay。Okay。

 I think this should be all we have to do in the interrupt CPP。

 but this is really a lot to do we really have a lot to do here。😔，哎。

So we also have to go into the interrupt steps。Okay。

 I'll put this here so we can see what we are doing in the interrupt steps。😔，嗯。Yeah。O， up here。嗯。

In the handle interrupt request， we need to。Just push something like a zero。

 because this is for this error。嗯。So otherwise， we would have。Just in the interrupt request the。

Thing would get confused。So for an exception， the CPU pushes this value。And for an interrupt request。

 it doesn't push anything。 So we have to push something ourselves so that this structure works。Okay。

Now。Down here， we push the pointer。😔，And the interrupt number call this。😔。

I don't know why this is still here， it makes no sense to have it there。😔，O。Oh。Okay， so for this。

For this value that we've just pushed up there， we need to add4。To ESP。 so here we pop that again。

Okay。Okay， so I have commented out。These registers here。So I'll remove them here also。😔。

And this push A and P A， I will I will comment them out also。Because I want more control over。

Which register goes well。So here we just push these values manually here and everything down here is pushed by the processor or by ourselves up there。

So。一批。一的哎呀。对。So notice up here， we push them in the in the other order。 So EBP first， E D， I， E， S I。

E，D X，EC C， X， E。EX and EA X。And down here we push them we pop them in the opposite order。错。Okay。

Okay， okay， okay。 I think this should be all。

![](img/1a155ef902e8069c9e3686ee180cda77_27.png)

I really hate going into。

![](img/1a155ef902e8069c9e3686ee180cda77_29.png)

Into the as code because it's so easy to break something。So when I prepared for this。This was really。

This gave me nightmares。 I got all sorts of exceptions all the time。Okay， where is it。Okay。

 let's see line 1。2。😔。

![](img/1a155ef902e8069c9e3686ee180cda77_31.png)

Yeah。

![](img/1a155ef902e8069c9e3686ee180cda77_33.png)

Yeah。

![](img/1a155ef902e8069c9e3686ee180cda77_35.png)

Okay， it compiles。Yes， it works。😔，So。Let me。T， so here you have A's。Now you have bees。😔。

Pa the execution or the time B。

![](img/1a155ef902e8069c9e3686ee180cda77_37.png)

Ace， yeah。So this seems to work。O。う。Okay， this is all I wanted to do with multitasking。

So now you know how to run different tasks， but right now everything is in kernel mode。

 so everything has all the rights to do anything you want。



![](img/1a155ef902e8069c9e3686ee180cda77_39.png)

So this wouldn't be a good idea to do this with programs that are supposed to run in user space。嗯。

Yeah， I'm not sure if we will have the time to talk about user space。 if we don't。

 there's a quite good。Article on low level E U。So if we don't find the time to， to go into that。

 then。

![](img/1a155ef902e8069c9e3686ee180cda77_41.png)

You can look it up yourself。Yeah， so that's all for today。嗯。What will we do next time。

I think we should do memory management next。😔，Because we'll need that for networking。

 maybe we'll have time for talking about hard drives， I hope。So yeah。

Don't forget to subscribe so that you don't miss the next videos。NoAnyways。

 no matter what the next topic will be， I haven't decided yet。So if you like this video。

 don't forget to hit like。I think this is really cool to have multitasking now。

I think this is one of the biggest milestones you can have in the development of your operating system。

Yeah， have fun with this。And yeah， see you next time， bye。



![](img/1a155ef902e8069c9e3686ee180cda77_43.png)