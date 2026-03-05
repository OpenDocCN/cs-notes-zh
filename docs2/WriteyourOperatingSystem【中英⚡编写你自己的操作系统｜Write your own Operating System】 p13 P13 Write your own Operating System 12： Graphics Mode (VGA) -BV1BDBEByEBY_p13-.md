# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p13 P13 Write your own Operating System 12： Graphics Mode (VGA) -BV1BDBEByEBY_p13-

Hello and welcome to the 12th part of the tutorial on Wri your operating system。And okay。

 today is a big one。 Okay， now in this video， we will go to the graphics mode。 And okay。

 we won't go into a great graphics mode， just some。VGA graphics， you know，320 times 200 pixels。

With 256 colors。 So that's nothing special， but it， it sets。

It gives us at least something that we can work on to build。A desktop and a G framework and stuff。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_1.png)

So。Yes。One problem that we have right now is we still don't have any。Dynamic memory management， so。

That is why in the enumeration of the devices for the peripheral component interconnect。嗯。

We cannot instantiate the driver。Dynaically。But。Yeah， we have one advantage。Namely。

 the the VGA is relatively simple。 It's。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_3.png)

Quite similar to how it works with the text mode。 You know， there's just some certain。

Memory locations。 And you write stuff there， and。Then you， then this is drawn on the screen。

 but you need to set them the graphics card to graphics mode。 So is that it。Actually。

 does that and doesn't look for the text at what was the offset 0 x。What was it B 80，0。

0 or what it was？So it's similar， but we need to change the mode and。

Changing the mode is really hard。Because。When you Google this， I mean， when I went into this。呃。

I Googled for a long time for an an。 I was actually。

I almost quit it because you just don't find anything good， you know， because almost all。

Websites that talk about graphics mode and VGA graphics just say， well， use the interrupt。13 H。

 ex decimal 13。So。YeahM C plus 13 H， I think is basic syntax， I think so。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_5.png)

Interrupt 19 or Exodml 13。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_7.png)

か？Yeah， and almost all tutorials， I don't know。 I've read dozens of tutorials， and they all tell you。

 just call interrupt。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_9.png)

Xod SMl 13 and。It doesn't work。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_11.png)

I mean， this is how you did it in the Dos times and I guess that Windows has some compatibility for this interrupt。

So when you， when you call that interrupt in a Windows program， I guess Windows just。

Emulates the behavior in a way， but。呃。When you are writing your own operating system。

 this doesn't work because。Interrupt Xodimal 13。Is bias interrupt？



![](img/7f8a3436ff0f9f278d70dd3b72567d15_13.png)

Okay， that's not。 I mean， we had situations where the operating system did stuff for us when we are working inside an operating system。

And we cannot use these things when we are outside of the operating system。

 but that's not the problem here。You know。If you remember。

 we had the situation at the boot process of the computer。The firmware is loaded。

 and then the firmware loads the。The boot loader and the boot loader loads the kernel， right？



![](img/7f8a3436ff0f9f278d70dd3b72567d15_15.png)

嗯。So here you have the firmware， the bioos。Then you have some boots。😔，And then you have some it。

And this interrupt。Heexa her team is actually a bias interrupt so。

So this might actually work even if we don't have a Windows kernel or a Linux kernel to rely on。

But the problem is Gr puts us in 32 bit mode。Even before our kernel starts and this v bio extension interrupts like this one。

 they are deactivated in 32 bit mode。嗯。So what you could do is you could go back to a 16 bit mode。

 and then you would have， then you would be able to use that interrupt。

But I don't even know how to go to 64 bit mode and going backwards。I don't。 I don't want to do that。

So。So this isn't what I want to do。So if you don't use the bias， interrupt。To switch the mode。嗯。Well。

 then you need to talk to the graphics card directly and tell it to go into graphics mode directly。嗯。

And I want to point you to。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_17.png)

A source code on O S D dot org。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_19.png)

啊。Here at this address。There's a lot of code here。 and in particular， you have these。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_21.png)

He has these sequences here。For。Text mode，1990 times 60 characters。Graphics mode。

640 times 480 times two colors or two bit。 I don't。 I'm sure。To。Colors。

So here you have different initialization codes。For different。Resolutions and color depths。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_23.png)

然。And that is really just what we have to do。 We just have to to send these codes to the graphics cards to set them out。

Okay。嗯。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_25.png)

Now， one thing， yeah， the design of the VGA graphics is really， really bad。

So when they came up with this stuff。They really weren't thinking too far into the future， so。呃。

Yeah for。For small resolutions， you already。Exceed the capacity of the Ramm。 you know， I told you。

In the text mode， you have this。Particular offset。 And what you write there is put on the screen。

 And with a graphics mode， there is also。A certain offset and the colors that you put there。

Correspond to the pixels on the screen。But yeah， this's。

The size of this memory location is just too small。啊。

I don't know exactly from the top of my head what the size actually is but。😔，嗯嗯。Yeah。

 since it is already too small for a very small。Resolutions and color depth。

 They came up with strange。呃。Strange ways of circumventing the problem with so called bank switching and。

呃。And also。Yeah， so， so they they。They just have different。Multiple different locations for。For the。

For the different resolutions。 So if the resolution is too large， then you have multiple。

Of these memory locations。 And you need to know where to write。Your data now。

And this is quite tedious， as I said， I think this is really bad design。

 they just weren't thinking too much about having higher resolutions back then， but okay。

 so this is the way it is。嗯。Yeah， what I wanted to say is。Yeah， the VGA is very similar。

In the way that these memory locations are fixed。You don't need to really communicate with the PCI controller and。

Stuff to find this out。So because of this， we don't really need dynamic memory management at this point。

Right， we can handle this just the way we handle the。The text mode。嗯。Yeah， we'll just have a driver。

 and we can。We can instantuate it in the kernel CPP。嗯。I mean， it's not really a good design。

 And I think it's a better idea to have a mock up that hides this functionality in the enumeration of the PCI devices。

 but。Whatever， let's just start with。Sending these codes to the。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_27.png)

嗯。To the graphics card， so that we get。Into graphics mode。Okay， include drivers。Okay。

 so the the V G A has a lot of partss。Let's see。11 points。This is madness， but okay。嗯。So。O。Okay。

 we have one part for miscellaneous stuff。One for the cas rate tube controller。Index and data。

Pokrating。快吃不了。嗯。H。By the way。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_29.png)

When you do graphics programming inside Windows or Linux or whatever you have an operating system protecting you from doing bad things。

You know what？But if you send。I mean， you are writing your own operating system。

 There is nothing that protects you from sending wrong data。To the graphics card and a monitor and。

It could potentially really break your hardware when you send the wrong data。嗯。And， I mean。

 VGA is pretty standardized， but。I don't know。 I am not taking any responsibility if anything breaks on your hardware or。

嗯。I mean， it's。In theory， it could even happen that your monitor explodes。

And you might get injured or maybe even die。嗯。I don't think that this is a realistic scenario in times of TFT monitors and stuff。

 I think this is really that was a concern with CRT monitors。But。I I warned you， okay。

 this is you're doing this on your own responsibility。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_31.png)

Sequence index points。Yeah。And tribute control。Inex。おち？

And this is a little bit different than the other parts。 we don't have a data port。 We have。

We don't have index and data。 We have index。Read， write， and reset port。Okay。I struck out。

 he's struck out。Okay， then we will have。A method to。Set the mode。With height and。Ys。

But we'll also have a method which tells us if a certain motor is even supported。😔，Okay。Then。

 we will have a method。Which sends these initialization codes to the。To the。Corresponding parts。

Like this。嗯。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_33.png)

Yeah， then we will have a method， which gives us the location of the。嗯。Of the memory。 look。

 you know this。This frame buffer segments。You know， it's。Yeah。

We need a method that that gives us the correct。Offset for the segment that we want to use。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_35.png)

Lexus。うい？Yeah。And this is needed for。Yeah。嗯。For the method put ps。😔，Yeah， here I will。

I will do this in a。In a more abstract way。 So I will have a method put pixel， which accepts。诶。

A 24 bit color code。Rt。Green。그리고。So this method is supposed to put this color。To。To this coordinate。

 okay？Okay， but yeah， as the VG A， we will be using an 8 bit。Version for now， so。So， actually， we。

We cannot actually set a color like this。So they put ps of it。😔。

Method down here is supposed to get an index。

![](img/7f8a3436ff0f9f278d70dd3b72567d15_37.png)

You know， the8 bit color modes use basically a table of 200。56 entries。Of different colors。

 And then here you just select an index in that table。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_39.png)

Okay。So the put P method actually needs to get this color index for a certain color。嗯。Good。卡了。😔。

Index for。For RGB color。Okay， so the put pixel method down here is supposed to call get color index to get the。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_41.png)

ASa index for this color， I mean。We could give it too many different colors。Here， So。

 so the driver is supposed to hide away the fact that it cannot actually represent this many colors。

 so。So we might have only one light blue。 And if we want to set one light blue or a different light blue。

 they might get。Drawn as the same light blue in the end。

 But this is supposed to be hidden from all this all the things that draw on the screen。 Okay， the。

The objects that that draw on the screen are not supposed to know that you have only 8 bit color depth in behind。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_43.png)

Behind this， okay？So。Yeah。嗯。Yeah。Okay。Okay， now we initialize the different parts。嗯。O。

So as a miscellaneous port， that is port number 0， x，3， C2。😔，Yeah。

The carate tube controller index part 0 x。3D。Soong。Data thought is3D5。Sequencecer index is 3， C4。😔。

Sequence that data port is 3， C 5。Graphics controller is 3 C。😔，And。3 Cf。Attribute controllers is。3。C。

0。And the right part is also 3 c0。3 C1 and 3DA。O。Yeah。Okay， for now。

 we will just implement the mode 320 times 200。And 8 bit color depth， okay so。Okay。

 so this is the only mode that we support right now。嗯。And in the set mode。Yeah。

 here we basically just take this from。From this file here in O SF dot org。嗯。This one here。

So there 320 times 200 times 2。56。Okay。And we just。😔，We just pass this to the。To the right register。

😔，Method。And then we return true。😔，So it should have worked at this point that。We have set the mode。

But if the mode does not support it。So if we try to set the mode to an unsupported mode。

 then we just return false。Like this。Okay。Now， how do we set， I mean。

 what does this right registers method do？It just writes this data to the miscellaneous part。

 this to the sequencer， this to the ca ray tube controller， graphics controller and。

Attribute controller。So。然后。Okay。So we get this pointer to the register。Entries here。

And then we we just write the first one to the miscellaneous port and increase this pointer because the data。

That we had in the miscellaneous we don't need anymore more so we can basically just discard the old pointer and have it now point to the next memory location。

嗯。Then we have five values that we write to the sequence on。And this is quite similar in the next。

In the next for the next part， also， so。嗯。You first write the index to the index port and then the data to the data part。

Sequencecer index part。Right， I。Wait， this is supposed to be8 bit integer。So first， we say。

 where do we want to write the data and then。What do we want to write there to that index？Okay。

So this is for the miscellaneous， this is for the sequence now。😔，嗯。可 for the。

For the catthhoderate tube controller。There we have 25 values which we send。😔，Like this。

Photographics control now。There we have nine values。😔，And the attribute controller。

There we have 21 values。😔，Attribute controller index part。Attribute control。呃。

Here we have a little difference。😔，So we right to the index part， the I and。To the right part。

The data。 But first， we need to reset。The attribute controller before we send data。嗯。

Attribute controller reset port dot read is how we do that。O。Okay， O， okay。Now， one more thing is。

 yeah， we need to do something like some mutual exclusion。So the cassult rate tube controller。

 because this is。I think this has to do with the fact that the cahode rate can blow up if you send the wrong data there。

So。You need to unlock it， send data there， and then lock it again。

I think this I think this is a security feature。C， T C index part。Right。0 x，0，3。

So we will read the Oit value。😔，嗯。Do a bit twice， always。The number 0 x80。And write the。

 So basically， we are just setting the first。bit of this to one。 right， we。

 we get the old value set the first bit to one with this and write it back to。That index。



![](img/7f8a3436ff0f9f278d70dd3b72567d15_45.png)

我。And here。嗯。Yeah， for the 11th。For the 11th index or 17th， actually。We set the first。

 the first bit to 0。Like this， okay。よし？Okay， now if the data that we get， which we send to the CRTC。

嗯。I mean， we are over writing these values again in this loop down here， right， so to。

So this would actually unlock the controller again。哦。No。

 it would lock the controller again if we got wrong data on in this registers here， so。

So in the register that is written to 0， x 0，3， we also。Set the first bit to one。And。

And the register as it is written to0 x11。We set the first bit to 0。

Just to make sure that we don't accidentally overrpe this。Again。Okay。And when we are finished。😔。

Attribute controller。Reset product do read。 So we reset the attribute controller again。And write。

0 x 22。The attribute controller index port。O。Okay， what do we do， What do we have now。

 So the the partss are initialized。We can write the registers。And we can set the mode。Okay。

 and down here。Yeah， this。This put pixel method down here we' just call the other put pixel method。

With the same X and y。😔，But with a get color index。For theRGB value。Okay， for now。

I will just do a little mock up here。If。R is equal to。Zero。Green is equal to 0。And blue is。

Equal to0 x。A8。Just return color。Z x，0，1。So this is just the index。

 I think virtual box has this as a default setting， I think。

Although I've run this on on actual hardware also and it also worked， so it's probably。Standardized。

 I guess。So。嗯呀。So we get the color index and pass it to put pixel。And。Pixs。Works like this。😔。

So it asks this get frame buffer segment where to put the pixel。

So we get the current frame buffer our segment。😔，And that。Yeah。

We haven't stored the width and the height anywhere。 So I will hardcoat this to 320。Times a y plus x。

And at this address。We put the color index。Like this。Okay。Now。

 the last thing we need here is the get frame buffer segment。😔，And this works like this。嗯。

We are looking to the index number six for in the graphics controller。So， the segment。Number。We get。

From the data part。Okay， the code that I have here is a bit ugly。嗯。

I think I will do it a little bit differently。😔，嗯。I'll shifthi this by two。

 So that we are only interested in the。The bits number three and 4。

So we just remove the last two bits。And。Then we takes a bit twist and with。The number3。

 So that all the other。系。All the other bits are killed。Okay。Now， if this is a0。Then。

We need to write our data to。The memory location。Okay， this is a bit odd。Just。Just0， okay。

It's strange， but。Okay， I will also put a default。Here。

 I think the compiler complains if you don't have a default value here。So0 x A，0，0，0，0。嗯。

That's in case 1。0 x b0，0，00 is for case 2， and case 3 is 0 x。B。8ight，0，0，0。Okay。Yes。

 I think this should be it。But you know what， I will just。

I will make this picture with a color index。😔，I will make this public also for now。

It shouldnn't be in the long run， but for now， I will just do this。嗯。O。あ。Okay， and the make file。

 we now need。Object drivers。B A dot O。And in the color。Has a V G A。Yeah。嗯。うい。Okay。

And then have V3 A dot set。😔，Moote。3，20 times 200 times。8 bits。嗯。And then， let's just。Draw a a blue。

Rectangle on the screen。一。嗯。Yeah。Yeah。Yeah。Okay。嗯。嗯。Then as the colors that we set， we only had this。

0， x 0，0，0， x 0，0。0 x。诶。8ight。This was the only colour that we had。Okay， let's see if this works。😔。

Okay。Okay， it looks crappy。 This isn't what we wanted。😔，But at least it does something， you know。

It's not a bad sign。Okay， I mixed up this。The ports here。 So the read port。It's 3 C。玩。

And the right plot is 3 C0。Okay， let's see if this works now。Okay still not okay。Okay。

 so I found them mistakes that I made。😔，嗯。Yeah， it just shows。

That you really need to to be sure how many bytes you use。 Okay。

 so the problem was that I was using U and8 T for Y and x here。And 320。😔，Is outside of the。嗯。

Of the representable numbers for an U and A T， so。Actually。

 the compiler should have told me an error message there， I think， but。So make this。😔，And 32。

Those of them。可啊 here we。We啊。Centuated， set the mode and iterate。

Over the pixels and set them to blue。So make clean， make run。And bam。The screen is blue， yes。Okay。

 now I've installed it on my actual machine。Reporting。My operating system。And you see， yeah。

 we have a blue screen。 Okay， yes， this is not a blue screen we have now put the actual hardware in graphics mode and drawn a blue screen。

😊，On everything。 So， so yeah， this also works on the actual hardware。

 And I think that is really an awesome feeling。 One of the biggest milestones that you will have in。

😊，Writing your own operating system。So yeah， so there you have it。

 you can also run this on your actual hardware。O。So。Yeah， this， this wasn't that hard。 I think。

 I mean， you need to set the mode and。Then you just need to write the pixels in the right positions。

But I think this is sufficient for today。 So next。Next time we will talk about GI frameworks。

So that we can actually build a desktop on top of this graphics mode now。嗯。Yeah， so。Yeah。

 tune in next time。 Don't forget to subscribe and also hit like if you like the video。Yeah。

 so see you next time， by。