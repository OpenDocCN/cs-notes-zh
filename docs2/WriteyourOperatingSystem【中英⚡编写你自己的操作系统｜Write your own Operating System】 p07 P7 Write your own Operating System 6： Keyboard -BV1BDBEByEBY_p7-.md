# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p07 P7 Write your own Operating System 6： Keyboard -BV1BDBEByEBY_p7-

Hello and welcome back to the sixth part of the tutorial on writingri your own operating system。

So where were we in the last video？So if this is your process up。

And here's your programmable interrupt controller。嗯。And this is connected to， for example， keyboard。

Also， the mouse。And。Also， the。Hardware clock。So what we did last time is we established a connection between the CPU and programmable interrupt controller。

 and we actually received the first interrupt from the clock。So。This is a good thing。

 so this means that we actually have a connection now。嗯。But it， we had a problem that。

After we got this interrupt， the system just stopped。 And that's not what it is supposed to do。

 You know， it's actually supposed to get the next time I interrupt。 the next time I interrupt and。

Yeah， we， we have a problem that we didn't answer the interrupt。

 So we didn't tell the programmable interrupt controller。 Okay， done。 I have， I have received this。

 and it's okay。 You can continue with whatever you were doing before。嗯。

And we will do this in this video now。And then we can actually， really start the。

To get a decent communication with a keyboard， okay。So the problem that we have now is。

If this is your C plus plus world。So here we have our current main。

And we build this object with the global descriptor table and the interrupt manager。

 and we connect these in our object in a way。And now an interrupter occurs and the interrupt kicks us out of this C++ world into into something like an asemmbler world。

 right。So that's why we wrote the assembly code， which。Which did all this。

All this hard stuff just to get back into the C plus plus world， but。So far。

 we only went into the into a static。Into a static function， right， so。

And that's not really what we want， right。 And， I mean。

 we are writing this in C plus plus because we want to have the power of object orientation， so。

We really want to get back from the static function back into the into this object， into this。

Object oriented construct， right， so。And actually， to answer the interrupt to the p。

 we have to send data back through the command and data pos。And。Yeah。The。

 the command ports and data ports， they are actually members of this。Interrupt manager， right。

So these are members of the interrupt manager， so we actually have to get from this static。啊。

Function into a method of the inter manager just to have access to the。To the connection to the pick。

 okay。And I'm actually not a big fan of this。 So what we'll do is we will have a static pointer。

To the interrupt manager。嗯。I mean， I'm， I'm not a big fan of having static pointers to。To things。

 And， but I think really， we don't have much of an option right now because。

We are in a static environment at this point and in a static environment we only have access to the static object。

 so we need to have a pointer to the interrupt manager in a static variable。As I said。

 not a really great design， but。

![](img/97221e766c222cd97bf1e14d0769de1c_1.png)

I don't think we have much of an option。So。So what Ill do now is。嗯。In here， in interrupt that age。

 I will put。A pointer to the current。Interrupt manager。 So we only have， we only can have。one。

Active interrupt manager。Okay。So now then we have this。😔，Our hand will interrupt function。

Will then called the nons static。嗯。Method do handle， interrupt。Of that。

Of that interrupt manager object here。Okay。So in interrupt dot CPP。Yeah， we need to have， I mean。

 this is a static object。 So we we must put。Intualization here。Initialized with 0。

 And then here in the activate method。嗯。We will just set this。Two of is pointer。

 but I mean in theory， we could have multiple interrupt line address。

But that doesn't actually make sense， right， because。The processor has only one。

 one interrupt descriptor table， and。So there can only one。

 There can be only one active interrupt manager at a time， so。But。I'll put this here。

 if the interrupt manager。Has already been set then。We was。Theact。

The old one and then set the new one。Okay。And deact。So if， if we are calling deactivate on。嗯。

I'm the active interrupt manager， then it is supposed to。Deactiv it。 And if we are calling it on an。

On a different。Object， then it is already inactive。 So then we don't have to do anything。So。嗯。ok so。

Yes。O。嗯。Now， in the handle， interrupt， we can now。Oops。We can now use this pointer， and。

Call do handle， interrupt on it。And the do handle interrupt will basically be the same thing just on an object。

 so。So well just pass the。The parameters and return。What we get back from that object。Yeah。

And otherwise， we have just。Return the。Origin to ESP。Okay。So now let's have this。Do handle。

Interrup method。And so here we put the stuff that we really do now。See。



![](img/97221e766c222cd97bf1e14d0769de1c_3.png)

So this should behave the same way and behave before。😔。



![](img/97221e766c222cd97bf1e14d0769de1c_5.png)

![](img/97221e766c222cd97bf1e14d0769de1c_6.png)

![](img/97221e766c222cd97bf1e14d0769de1c_7.png)

![](img/97221e766c222cd97bf1e14d0769de1c_8.png)

Okay， so。

![](img/97221e766c222cd97bf1e14d0769de1c_10.png)

What we've seen now is， yeah， I mean， the operating system does the same thing as before now， but。

But in a different way。What we did now is we jumped from this static function。

Back into the interrupt manager object and there we have access to the pick connection。Okay。嗯。So。

Yeah， what we can do now is。At this point in this do handle interrupt method。We can now actually。

 we can actually。Sent the answer to the interrupt。 and then。系啊。Then the program。

 the operating system will not hold here。

![](img/97221e766c222cd97bf1e14d0769de1c_12.png)

So。Let's see。So in this。Method。So。We only have to send answers to the hardware interrupts。We have to。

 I mean， which other hardware interrupts。We have remapped the hardware interrupts from the pick to 0 x 20 to 0 x 30。

 so。So in this case， we have to。To send an answer。So this is the answers at the pick once。And。

If we are also。So， so this is the answer for the master pick and。嗯。

Maybe we also have to send an answer to the slave， but not always。So the same answer。

 But only if this was actually a。An interrupt that came from the slave。 So only if。嗯。

The interrupt number。Has been between。0 x 28 and 0 x 30。



![](img/97221e766c222cd97bf1e14d0769de1c_14.png)

Okay， now let's see what happens now。

![](img/97221e766c222cd97bf1e14d0769de1c_16.png)

And you see now we get lots of interrupts。 So this is really a good thing。 So let's stop this。嗯。Yeah。

 I'm I'm really happy right now。 So， so this。Works kind of already， and。I mean。

 we don't want to have this output every time we get a time I interrupt， right。So， I would say that。

This output should only be there， if。If we are not， if the interrupt is not。The time I interrupt。

And the time I interrupt is I interrupt 20 so。

![](img/97221e766c222cd97bf1e14d0769de1c_18.png)

So if we run this now， then we don't get this output because here the the。嗯。

We still get the interrupts， but we don't print them on the screen all the time because they are really not that interesting。

 right。

![](img/97221e766c222cd97bf1e14d0769de1c_20.png)

So。

![](img/97221e766c222cd97bf1e14d0769de1c_22.png)

Yeah。So now we get all the interrupts， what do we do next？I mean。

 we are programming this in C plus plus， right， So we want to。

 to use object orientation and the object oriented way of proceeding now would be to。To have。

Objects for the different interrupts， right， so。And then so for example， for interrupt。0 x 21。

 which is a hard a keyboard interrupt。 We would want something like a keyboard driver or something which handles that interrupt。

 right， So so we need to define some interface for。For these keyboard drivers。

 mouse drivers and so on， which the interrupt manager can， then use。Okay。



![](img/97221e766c222cd97bf1e14d0769de1c_24.png)

So。So what I'll do now is I'll have another base class。Called interrupt Tler。

And this will so the base class will basically just know its own interrupt number。嗯。

And the pointer to the interrupt manager that it is connected to。Okay， and。Yeah， I want to make the。

The construct and de are protected so that you cannot instantuate this。You know， on。We don't have。

Purely virtual functions。 And so we cannot have abstract classes， so。

I'll just handle it in the way that。嗯。By making the constructor protect it。So。Okay。So。

This should work。系啊。And we will also make this new class a friend of the Interop penettra。Yeah。Okay。

And now we will have basically something like the interrupt is crypor table， but on a higher level。

 So here we will have。An area of interrupt hand plus。Ex。O。So。Now， we have to implement these。

Re methods。Okay， so the。The constructor will just store the the values you give it。

And then it will put itself into this area of the interrupt manager。And in the disruptor， it will。

Un restate。Okay， like this。And the standard behavior for handle interrupt is just。

Returning ESP again。嗯。Okay， now in the constructor of the interrupt manager。

We also have to set the handus to0。Like this。And then。Down here， we can proceed and say。Handless。

If we have a handler for it。嗯。Then we then we。Call its handle interrupt method。

Giving it the stick pointer。Okay。嗯。Okay， and then。We can print this message about an interrupt that we couldn't。

Do anything with。Only in the Earth case here。 So if， if we have an interrupt handler。

 then we use that， Otherwise， we print this message。So this will also tell us the number of the。

Interrupt that dwig didn't handle it。

![](img/97221e766c222cd97bf1e14d0769de1c_26.png)

Okay， this looks good。

![](img/97221e766c222cd97bf1e14d0769de1c_28.png)

![](img/97221e766c222cd97bf1e14d0769de1c_29.png)

![](img/97221e766c222cd97bf1e14d0769de1c_30.png)

Okay。So some object file wasn't just wasn't updated and so just make clean and make run。

 fix the error so。

![](img/97221e766c222cd97bf1e14d0769de1c_32.png)

![](img/97221e766c222cd97bf1e14d0769de1c_33.png)

Okay， so。

![](img/97221e766c222cd97bf1e14d0769de1c_35.png)

Okay， so now the。Some now the。The interrupts work as we want them to Now the next thing we can do is we can write a driver for the keyboard。

And。Because if， I mean， if， if we just activated the keyboard。And you press a key。

 Then the p will send the interrupt。 The CPU will tell the p。 Okay， I'm done with the interrupt。

 The problem is the。

![](img/97221e766c222cd97bf1e14d0769de1c_37.png)

The kernel would still stop。 It would not continue running because the pick would not accept the answer from the CPU。

嗯。The reason is， if you get a keyboard input。Then the P demands that the CPU fetches that input before it tells the p okay。

 I'm done so。So that's what we will do next。 We will make a driver class for the keyboard。

 It will be derived from。From the interrupt handler。And it will have its own parts。

And then we will just activate it。 And if the interrupt comes， it will read from the data port and。嗯。

Then。We will have an actual。An actual hardware response， okay。So let's do this。😔，Okay。

 keyboard dot H， the usual stuff。Okay， so this class needs two partss。

 and this is really relatively normal design， which we will see very often in the future。

We will have just。Two partss。A data port and a command port。Wait did I do this。哦，再试。So。Okay。So。

In this keyboard CP。We'll have to do a little bit in。In the constructor。So the interrupt handler is。

Right does that。First， so the interrupt T is for the interrupt 0 x 21。 that's the keyboard interrupt。

And we just pass the manager object to the base constructor。Then we construct the data port。

Which is port0 x60。😔，And the command port。Which is part 0， x 64。Okay。So down here。

If if we know there is a key strike， then we have to fetch it。Like this。And I'll just copy this。转音。

Okay， so this will print the key。 and we need to。Have the forward declaration for printf。

So that it accepts calling printf。O。Now。In the constructor。



![](img/97221e766c222cd97bf1e14d0769de1c_39.png)

So this。When we start communication with the hardware， we will just。Wait for。I mean， I mean， if。

 if you start your operating system and you hold down some key， whatever。

 this will just wait for you to。To stop pressing that key and。然后。



![](img/97221e766c222cd97bf1e14d0769de1c_41.png)

It will just remove all the。All the key strikes that have that might have been there before。So。So。

 this command tells the。Tells the pick to start sending。Keyboard interrupts， I think。

Or maybe it tells a keyboard to communicate using。Interrupt， I not。这你说。After that。

We send it the command 20， which means give us your current state。And then we read that。Then。

 we set the。The leftmost bit to one， because this will be the new state。



![](img/97221e766c222cd97bf1e14d0769de1c_43.png)

![](img/97221e766c222cd97bf1e14d0769de1c_44.png)

And we will also clear the fifth bit。😔，Like this。可呀。So then we。Right command 60， which。

Tells the pick or the， the keyboard to change the current state。So you see we set command。0 x20。

 which gives us the current state。 Then we change to the current state and write it back。

And I think this。Finally， really activates the keyboard。Oh， I almost forgot we need to put this。

 of course， also here。And in the kernel， we have to。Include the header。

And instantiate the object and notice this， we instantiateated between the instantiation of the interrupt manager and the activation of the interrupt manager。

And it gets。Appointed to the interrupt manager。Because this。



![](img/97221e766c222cd97bf1e14d0769de1c_46.png)

Okay， so this should work now。Okay。It didn't do anything。



![](img/97221e766c222cd97bf1e14d0769de1c_48.png)

![](img/97221e766c222cd97bf1e14d0769de1c_49.png)

Okay， so now we have an interrupt from the keyboard。0 X， F A， I think this basically says， okay。

 I'm fine with。I'm done doing whatever I need to do。 so I'm ready now。

 I think this is what that means。嗯。Now。When you press keys。The first times you。

 So the first times you press a key， you will get this。This keyboard key code 0 x 45 and 0 x C5。

En true。I think that's the key code for the nu lock。 And I think this is what virtual box does to。

To tell the virtual machine the state of the numbl。So I think we can really ignore them。And yeah。

 I think this FAA is really a status interrupt。 so we could ignore that also。



![](img/97221e766c222cd97bf1e14d0769de1c_51.png)

啊。So， we could put。Somes， some。Some， if。Statements here， which say， okay， for 0 x 45 and 0 X C 5。

 we don't do this。好的。In a better way， let's say。Switch the key。😔。

And this is just the default behavior。And for 0 x 45。We just do nothing。And also for this0 XFA。



![](img/97221e766c222cd97bf1e14d0769de1c_53.png)

Okay， now， now when you press a key。I just pressed the a key。And you see， we get two interrupts。

 So the first one， when I press it， and if I keep holding it。

 I get the same interrupt over and over again。 And when I。Stop pressing。

 Then I get basically the same interrupt。 But the first。Yeah other。

The first bit of this8 bit integralteger is just one for key release and0 for key press Okay so so you will get the same key code twice you know one when you press the key and again when you release the key just with with a different first bit。



![](img/97221e766c222cd97bf1e14d0769de1c_55.png)

So。So， maybe we'll just。Ignore。嗯。Keys key coats。嗯。So yeah。So， everything。😔。

Everything after 0 x 80 are the key release。Interrupt， and we are at this point。

 we are not that much interested in it。

![](img/97221e766c222cd97bf1e14d0769de1c_57.png)

嗯。So I press A， B， C， D。

![](img/97221e766c222cd97bf1e14d0769de1c_59.png)

And you will realize the， the key codes that you get。They are terrible。 I tell you they are terrible。

 They are all over the place。 So you will not really have an option。 You will just have to。



![](img/97221e766c222cd97bf1e14d0769de1c_61.png)

To take a sheet of paper and press every single key。

And see which key code do you get and write that down， and then for every single key。



![](img/97221e766c222cd97bf1e14d0769de1c_63.png)

You will have to make your own case here。 And that's really， that's really crazy。 I tell you this。So。

嗯。

![](img/97221e766c222cd97bf1e14d0769de1c_65.png)

But let's see。 I'll， just， as an example， I'll just put case。嗯。0 x。完毕。AndIn that case， our print F。

The letter a。Because that's a key code on this keyboard。



![](img/97221e766c222cd97bf1e14d0769de1c_67.png)

WellThe thing of this the worst part of this is on different keyboards。

 the same key codes will have different meanings so。



![](img/97221e766c222cd97bf1e14d0769de1c_69.png)

So here， if I press Z， I get a 0 x15 and on American keyboards， 0 x15 is a y。



![](img/97221e766c222cd97bf1e14d0769de1c_71.png)

And this is stuff that you probably remember from back in the days when you remember the Do programming。

 this is stuff you had to deal with back in these days， right？



![](img/97221e766c222cd97bf1e14d0769de1c_73.png)

But。So。

![](img/97221e766c222cd97bf1e14d0769de1c_75.png)

![](img/97221e766c222cd97bf1e14d0769de1c_76.png)

So I。Compare this again， executed it again。 And now I press a， and you get an a。Great， isn't it so。

So now we finally get real data from。

![](img/97221e766c222cd97bf1e14d0769de1c_78.png)

From the hardware， you know， if I press a again， I get more A's。

And then what you would do next now is just fill in all the cases with all the other keyboard key coats。

And。Yeah， maybe you just copy and paste those things from my zip file。嗯。But whatever。

 So this is really a bit tedious。 And I'm not going to put this in this video now， so。So， this。

This should be enough for today。I think we have really achieved something a really a milestone now because now we really get data from the hardware we press a key。

 the key A and we put an A on the screen and this is really a great feeling。

 I think one thing I want to tell you。At this point， you。At least I when I went。

 when I came to this point for the first time。I thought， hey， this is great。

 I want to run this on the actual hardware， and I said make install and reboot it。

 and I pressed the key， and nothing happened。And that was really frustrating for me。

And it took me quite a while to figure out what the problem was。 So the problem was。

This is a USB connection。So on the， I mean， virtual box。

 we communicate with your operating system and pretend there is a pick， but on your actual hardware。

AUSB keyboard isn't actually connected to a pick。 Okay， I think it is connected to a p。

 but not like this。 This would be， I think the P S。2。Connections。Would be directly connected。

 But now you have。On actual hardware， you have your USB。Thoughts， and， then you have。要 mouse子。

There and your keyboard there。And with with this scenario， you cannot。

So this scenario you cannot handle it right now。But my computer at home had。Luckily。

 it had a buy setting。 I think it was called legacy operating support or something like that。

 And when I enabled this setting， the motherboard really did all the USB stuff and then emulated the behavior with the p and the。

Keyboard and mouse like this。 And when I enabled this by setting。

 then I could actually press keys and get them on the screen。 So if you have a setup like this。

Then I you have to stick with。With virtual through the box for now。

 Or maybe you have such a setting like this。 And otherwise， we。You will。

Get to run your stuff on actual hardware only when。

 when we are at the point where we can communicate with USB。Okay， so this should be enough for today。

Kune in next time。 next time， we will。

![](img/97221e766c222cd97bf1e14d0769de1c_80.png)

We will talk about the mouse but let me tell you now that we have all the stuff where they interact and the global descriptor table and everything。

 the mouse is really easy so。The mouse is really quite similar the to the keyboard。Hello。And。

 and you've seen once we had all the interrupt stuff running， we when we。

We came to the point where we could actually use the keyboard relatively quickly。

 and we'll get to the point where we can use the mouse relatively quickly now。 also。

 because the really tedious stuff， the interrupt descriptor table， the。All the assemblymb code。

 the boot manager the boot loader stuff， the global descriptor table。

 all this hard stuff is now over。 we are now finally at a point where we can really do stuff right all this necessary but TD is fundamental stuff is over now and now we can really get going and do stuff okay so yeah see you next time and don't forget to subscribe to so that you don't miss the next video。

See you next time。