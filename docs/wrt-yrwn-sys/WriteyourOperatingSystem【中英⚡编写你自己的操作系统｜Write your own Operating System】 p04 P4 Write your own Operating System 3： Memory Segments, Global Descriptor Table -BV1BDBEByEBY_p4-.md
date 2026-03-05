# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p04 P4 Write your own Operating System 3： Memory Segments, Global Descriptor Table -BV1BDBEByEBY_p4-

Hello and welcome back to the tutorial on writing your own operating system。Now。

 in the third part of the tutorial， we will look at。

 but we will start with communicating with the hardware。嗯。I mean。

 writing stuff to the screen wasn't hard， right， We just had to set a specific memory location。

 and that was okay。嗯。But when we want to talk to the keyboard， for example。And。I mean。

 sending data to the keyboard isn't really hard， but receiving data， that's pretty hard。

And before we start that， we first need to talk about memory segments。嗯。

And I will explain later why we need to talk about that。So。That' say this is your run。Okay。

 and let's say here is your kernel。So the binary code， the kernel that bin。

And maybe some data that it uses。O。And then maybe there's a program you are executing as user。

 you know。I mean。For Linux users， it's relatively normal to think about。You know。

 administrator mode when you run as route and when you run things。As a normal user。And。

As a normal user， you have less privileges， right？So here's your the code of your。Of your program。

And maybe there's some data of your program。Now， a few years back。

 a common approach of attacking a computer was to make a program load binary code into this memory section。

And then， jump into that。Effectively executing a virus or something。嗯。But today。嗯。Well， what a。

What an operating system does is it tells a processor， well， this here is a data segment。

And you are not allowed to jump into data segments。 Okay， so this really eliminates this。

Security threat。嗯。But there are other things， you know， as I said， so this is。A user space。Thing。

Right， and here your kernel space。非他。嗯。Now， imagine the processor is currently executing。

Theres a coat in here。And now you press a button on your keyboard。What what this does know is。

If here's your processor and here's your keyboard。You press a button， and then。What happens is。Yeah。

 you， there will voltage will go out of the keyboard and into the port and。

And there is a controller in the port， which communicates with a。With the processor。

And this will cause a so called interrupt。So the CPU will then say， okay， I have an interrupt。

 I will stop working here。And we interrupt for for a keyboard press。Might be maybe here。Okay。

 so the CPU is now supposed to jump here。嗯。But as it is currently here， and it's set to。嗯。

To limited access rightss。 And it is only limited to using this memory location right now。

It cannot actually do that right now so。Everything outside of this memory segment is actually invisible to the processor at that point。

So what we will have to do now is。We will have to set up an interrupt descriptor table。I D T。

 which contains the information。Well， if for our keyboard interrupt。We need to jump down。And we will。

 and we also have to switch the。The memory segment。So。

This can be put into the interrupter scripter table， which。Sa ok。If this happens。Then。

Switch the memory segment here and switch the access rights and jump here。So。Doing that is okay。

 It would not be possible to do that in the code here in any way， you know the。

The CPU would just not do that because at that point it's。And。Some protection modes。Now。

 what we have to do now before we start creating the interrupterscriptor table。I。

We need to talk about these segments here， right， because we cannot tell the interrupt descriptor table will jump to this segment or set this as the active segment。

If we haven't defined what a segment is， right。So what we have to do first。

This we need to deal with these segments。And we deal with these segments by creating a global descriptor table。

And maybe I should tell you。This here， and also this， these are called code segments。

So this is where we are allowed to jump into。And this is a data segment。嗯。

So the global descriptor table is now just a table of entries with。With， yeah。

 with with these segments。 So you will have。Basically。A starting point of the segment。And also。

 a length of the segment。 So if this has length。1024， then there will be a 1024 here。Okay。

 and you will also have some flags， you know， like。So in the Fls。

 you would have the information that this is a code segment or a data segment， it's executable。

 What are the access rights you need to jump in there and access that。That's in the flags。Okay。So。

 that doesn't sound。Difficult， right？ I mean， just， just a pointer into the Ramm。

 the size and some flags。 that nothing particularly hard， right。Well。

 it turns out this is really hard because。These entries here。嗯。

They are backwards compatible back to the 386 processor with 16 bit addresses。So。

So one of these so an entry in this table。It's8 bys。Okay。



![](img/5421de862bcd0d53876a8b8ae5152c8a_1.png)

Okay， so it's eight pipes long。And。Well。You have 16 bits for this limit。😔，Then you have 16 bit。

For this pointer。So this is the way it used to be。But then people said， okay， this isn't enough。

 we can only address 64 kilobys like this， so this was expend。So。Yeah。

 and here's another bite for the point on。And here are the excess rights。Now， in this。Pite number 6。

This is subdivided into two。Half pipes。呃。With the low by with four low bits being four more bits for the limit。

O。Then4 bys for the flags。And another by it for the pointer。So this is really terrible， isn't it。

This limit。Is spread throughout these bites here。And here。And this pointer is spread。Here。😔，And here。

So this is really， I mean。From a programmer's perspective， this is really terrible， right， so。

Because you will not be able to tell a compiler to do that right。

 you will have to do this really manually and。That's really a pain I can tell you that。

 so we will be doing that now okay。

![](img/5421de862bcd0d53876a8b8ae5152c8a_3.png)

有。So what I will do now is。😔，I will create more two more files。We be descript table dot H， and。

L bitscriptpor table do CPP。Okay， so and。The GDPT that H， we will put。ButThe protection again。

And this will have a subclass and not really a subclass。😔，The nested class。To be more precise。

For the entries。嗯。This nested class， as I told you， this needs to be bite perfect， so。

That's why we put。嗯。This here。 So this will make sure that。

The class will really be laid out like this， like we wanted to。

So this prevents the compiler from deciding， well， I'll move them these objects around a bit because maybe that will gain us some performance。

But the compiler is not allowed to do that。So。So the limit。No pads。三子。The point。

 the low bites of the pointer。I mean。1 by。Extenion for the point of。Then the excess。fiives。

Or maybe that's called this flex limit high。Ok。And we will have a constructor。😔。

Which will just get regular base and limits as 32 bit integers and then move the stuff around the way we want it to。

Then we will also have methods which return the pointer and the limit。

So it has to compute this spread out stuff back。You insert it to T。Base。And U N 32。T。Limit。Okay。

 now this is a class for the entries。 and now we will just put a few entries in this global descriptor table。

 and I just want them to be。So I'm going to put specific ones in there。

 So I'm not really making this an array or something。I will really use。Explicit。Members here。

So the first one is going to be something like an empty one。嗯。Then one unused， I'm not sure。Why but。

That's what I've read。In the tutorial once。Then。1 code segment and one data segment。Okay。

 so right now we we will have just one code segment and one data segment and they will both spread throughout the whole memory。

 Okay， so this might not be a good idea in terms of security， but I mean， at this point。

 I think we have other concerns than security right？So。Constructor。嗯。Destructor。気持ち。😔，T。

With one code segment。Select。This method is supposed to give us the offset of the code segment descriptor。

嗯。And one for the data segment。嗯。O。Okay， so much for the GDPDT dot H and now have now let's create the GDT dot CP。

然后。So what we will have to do is。Wait。Of course， here we need to include。The types that age。

Because we are using here this。Uent types here。And here we will include。😔，Just the GDT dot H。

And everything we need in GDT dot CPP will be included by GDT dot H。O。So now， let's implement the。

As a constructor。Okay， construct。It will construct the N segment。Select。This parameter has 0，0，0。嗯。

I'm most sick。I should really copy this。Also with zero，0，0。And then， the code segment。Select on。

So this code segment selector will start at index 0。And let's say， we will have。64 MB。

And I don't want to go into details。Right now， if you want to know what these flags are。

You can look this up at low level do Eu。The article about the global descriptor table。And。Okay。

 so this creates the table。嗯。And once we've created it， we will。

Want to tell the processor to use this table， and this is a bit tricky。嗯。

Because the processor expects6。嗯。6 bys in a row， and。Pose this and。We've just。Faucet like this。嗯。

So here we have8 bys。我要都吃。Well the first bite is just the address of the table itself。Like this。And。

The last four bytes are the high bys of the second。Inter job。

So this is the size of the global descriptor table。And we need to shift that to the left。

Because it's supposed to be the high bites。Okay， and now when we have done that。

We need to execute one line of assembly code。To tell the processor to use this。嗯。This table help。

So the are similar instructions that we need is load global descriptor table。Okay。The de。

There's nothing for now。Actually， it it should unload the global descriptor table， but whatever。嗯。

Well， then。Then we want the offset。Of the data segment selector。So this is supposed to give us the。

Offset。And we can do that by taking thee。Address。Of the selector and。Subtracting。The address of the。

 of the table。Okay。Alright， we'll do the same thing。For the code segment。Okay。嗯。Now。

Now comes the hard part。 We need to。To set。These entries。

According to the parameters we get from here。Okay， so。put scriptor table。😔，Sments select。Signment。

 select our constructor view in 32。Pra and end。32。Limit。And you and paint。For the flex。Okay。嗯。

So now we have to distinguish。呃。A few cases。So。So I really tried to make this easier， but well。

It's just such a mess with these bites being spread throughout the structure so。

We will just cast this to an array of bytes and set these bites really explicitly。So。The first case。

 if the limit is small。So if， if it is a 16 bit limit， then we can just。Set the sixth by。To this。

 And this will tell。The process， O， this is a 16。The 16 bit entry。And otherwise。嗯。Well。

We have one problem now。I mean， if you look at this， we have。2 and a half byte only for the limit。

So these are really 20 bits。 And well， nobody can really prevent us from from using， I mean。

 this this will not even work， I mean。If we want to address a whole。RM， or let's say。

 even at least for gigabytes。Then this will not be sufficient。So what they did。I。Well， they。

 they said。The number in here。Must actually be multiplied。With。嗯。Withs 2 to the 12。

So then you have these 20 bits。Plus。Plus， these 12 additional virtual bits， right。

 But this is only allowed if these， if these last bits。Have all been one。So。So what I mean。

 we we get a U in 32 as parameter for the construct， right so。So it looks like this。

 we have four bytes。嗯。And the two and a half， most significant。Ws。

Will be really put into these memory locations and the rest will just be cut off。

 but this is only legal if this is all one。So。What we will do now is if this isn't all one。Then， we。

Okay， we could just set them all to one， but that's。Not really what we want。

 because then this table entry might go beyond a location that we really wanted to have in there。So。

This would be really nasty， because。You might get some overlap with other segments。

 and you really don't want that， Okay， so。So what we have to do now is。If this isn't all。

If these aren't all ones， then we will just decrease this number by one。And then， we can。Actually。

 increase this to all ones legally。 And well， okay， maybe that means。So if， if this would be。

If this is the limit we get。嗯。So， so maybe。The limit we want。Might have gone up to here。

But now we have subtracted one from this。Leading part。Getting us here。And then setting these once。

 these these bits here to once， setting it here。 So the worst thing that can happen is that we have such an empty unused region behind that。

Okay， that's not。That's not exactly great， but it's acceptable， I think。

So what we have to do now is really we have to to shift this stuff around a bit so。If the limit。

Is not。So if the last。12 bits of the limit。And not all ones。Then we will set the limit。To。The limits。

Shifted by 12。And then minus1。Otherwise。We were just shifted by 12。Okay， like this。 Okay。

 so now we have a legal value for the limit。And this is the case if we are not in another 16 bit mode。

 so。Then we have to set the sixth。By to。0 X， C。Zero。Okay。And now， we have to。

To distribute these things。Around， right， so。Target 0。So。So the last。好一下。

I is going to be the least significant bits of the limit。So target 0 equals to limit。And0， X， F F。O。

Target。one。啊，了。Next。8 bits of the limit。Okay， like this。So now we have set。

These two bys off the limit。Maybe I'll mark in。So this is done， this is done。

And now the rest is supposed to go into this half bite over here。So。This is target。6。Now。

 one thing we have set target6 already to something up here， right？So。Now。

 we are only allowed to set the low。4 bits of this。 So we will set。It like this。😔，U。Limit shifted by。

16。And。0， x。Yes。Okay， so。This is now。This， now we have this limit。Put into this entry in a legal way。

Okay， now and we have to encode the point up。So。Target equals。Bs shifted by something。And0， X， FF。

Whatops。0 x， F。K， target 2。3。4our and obviously，7。So the first one doesn't need to be shifted。

 So second one will be shifted by 8。This is shifted by 16， and this is shifted by 24。😔，Okay。

 so now we have distributed。This pointer into the memory through these three。Locationations。

Don当 done done。And we have also set these flags。So this is also done and now we only have to set。

These excess rights。Target。Size。Is set to the flags。O。So， this。

So this really solves this complete mess right it just gives the constructor just a normal 32 bit pointer here。

 just a normal 32 bit length of the segment and it will take care of putting everything where it is supposed to be。

Okay。Now。We have only two things left。That we do。At a few points。

 we might need to look up the pointer from this structure。

 so we actually need to do the same thing we just did backwards。

So we need to just take the corresponding。Bys if we。

 if we request the base and if we request the limit。嗯。The thing with the limit， of course。

 is we may have changed the limit so we cannot just simply store it somewhere else so。

We have to compute it again。Bace and。And the limit。Okay。

So the base isn't that hard because all the4 bys are preserved。嗯。But we'll do it again like this。

Okay， and then。Okay， so first， we take the seventh bite。

And then we successively shift it to the left。Okay like this。 And then。We just returned that。Okay。

 this was the easy。Part。嗯。嗯。So here we first take the low。4 bits of。Of the。Of this chat。B。嗯。And then。

We would basically do the same。You know， we。At。算了。First and zeros。Right。Like we did before。But with。

With this， I mean， we have to， to include these。These 12 pipes， again， so。So， now， we would set。

Result to。Result shift 12。0 X， F， FF。Like this， but。This is only in the case。Where we were in this。嗯。

Case， right， so we haven't shifted them， really if。嗯。If this， if we were in this case so。

This is only necessary， if。Yeah， if target 6 has been set to。To the 0 X C， right so。If。Target。6。And。

0， x， C，0。Equals 0 X， C0。Only then。To with it we， we do with this shifting。O。No。Well， in the kernel。

 we also have to include。The GDT dot H。And then we can。Insentiateiate the global descriptor table。

Like this。

![](img/5421de862bcd0d53876a8b8ae5152c8a_5.png)

![](img/5421de862bcd0d53876a8b8ae5152c8a_6.png)

嗯。Okay， and we also put need to put this in here。 So GDT。Oh。



![](img/5421de862bcd0d53876a8b8ae5152c8a_8.png)

See if this works now。😔，嗯。

![](img/5421de862bcd0d53876a8b8ae5152c8a_10.png)

![](img/5421de862bcd0d53876a8b8ae5152c8a_11.png)

![](img/5421de862bcd0d53876a8b8ae5152c8a_12.png)

![](img/5421de862bcd0d53876a8b8ae5152c8a_13.png)

Okay， so this。Looks good。

![](img/5421de862bcd0d53876a8b8ae5152c8a_15.png)

Okay， so this。It's all we need to do for the global descriptor table。嗯。Tune in next time。

 next time we will create the interrupter scriptor table and once we have that。

 we can really start communicating with the hardware okay。So'll see you next time。

