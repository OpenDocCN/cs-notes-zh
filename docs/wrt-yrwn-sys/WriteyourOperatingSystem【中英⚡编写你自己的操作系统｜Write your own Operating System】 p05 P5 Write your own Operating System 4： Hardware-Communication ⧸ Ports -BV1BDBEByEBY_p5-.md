# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p05 P5 Write your own Operating System 4： Hardware-Communication ⧸ Ports -BV1BDBEByEBY_p5-

Hello and welcome to the fourth part of the tutorial on writingrit your own operating system。

So in the last video， we have started。Going towards communicating with the hardware， right， so。

Of course， the first thing we want to do is we want to talk to the keyboard。

 So this is your keyboard。 Okay。Drawn a little bit bad。And here's your CPU。Okay。

 now when you press the key on the keyboard。There will go。 There will be a signal， which will go to。

The programmable interrupt controller。Pick。And well。

 the the thing is the programme of will interrupt controller will just ignore that。Okay。And。

If we want to receive this key strike， we have to tell the p to， to not ignore it。

And so we have to send some data there。So before we really start with。

With the back and forth communication between the CPU and the hardware， we really have to。

To to have a method of talking to the hardware。 right。

 so we need a way to send data out and to receive data。

And then the interrupts that we will deal with in the next video。

 they will tell us when there is data to receive。So。Technically。

The CPU has a multiplexia and a de multixa。嗯。Which is connected to different。A different hardwares。

So you don't really need to know that in order to understand what we are doing here。

 this multiplex and D multiplex are they are really。If you know a little bit about。

About all the hardware design， right then。This just means that you can put a number in here。

 and then。The multixa or de multiplexia will will send data to。

 to the portd with that number or receive data from the po with that number， okay。So the pick。

 for example， has the number， I think 32， So 0 x 20。So we would have to send data to part 0 x20。Okay。

And well， in asseemmbbls， there was a simple instruction， which just just called it。Outbeep。

And L B would get two parameters， the port number。And。YeahSo data that you want to send there。

But this this is Asceba， and we are not programming this in asemba， right？So。

Yeah when you read source codes on the internet， you will often see relatively simple methods of doing that。

Like， they， they will just wrap this code， this assembr code， basically。Like this。

Has a direct call to asmbler， and then just。Have a global function for this， also called outbeat。

Okay， so the problem with that is， in my opinion， this isn't really an object oriented way of doing it。

 right， because in order to use this part， now you need to know the part number and you need to know the bandwidth of the part。

 You know， you have different。嗯。Different partss with different bandwidth。 So without B。

 you send a single by。 and here you get a single byte。

 And then there's also W for 16 B integers and out A for 32 B integers。And。On the outside， when。

 when you talk to the port， you're not really interested in the bandwidth， right？

 So you don't want to know that。 But if you want to talk to a port like this， you'll have to know it。

 And I don't think that's good design。So the object oriented design。To have some object。APo object。

Which knows its bandwidth， which knows its port number。 And then you just have two methods read。And。

Right。Okay， and then。Well，8 bit pos will have a right method， which takes。You andt。8 T， right。

16 bits will have you into 16。 So if you， if you really send。

If you try to send an8 bit integer to a 16 bit port。

 that's no problem because the compiler will then say， okay， this is8 bit。

 but I cannot there is no version with 8 bit on a 16 bit port。

 but there's a 16 bit port so I will just turn this 8 bit integer into a 16 bit integer。

 So it's not your problem at this point anymore right whether it's 8 bit or 16 bit you can get one problem if you try to send 16 bit integer to an 8 bit port。

 but。This， at least。Will not。 I mean， this will not really cause a problem。

 only the compiler will will tell you， hey， this is not legal。 You are doing something wrong。 Okay。

 so the compiler will not even let you do。This in the wrong way， okay。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_1.png)

So。Yeah。So let's program this。I admit this， this is a bit boring。

 so I'll try to do this fast so you don't get too bored。嗯。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_3.png)

So we'll create。😔，Two more files。Partt at H， and。Partt dot CPP。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_5.png)

It usual protection。Yeah， we need子。Types again， of course， okay。So now we will have。Clas for。

Basically， a base class for ports。Which。Kns its， its own port number。

 and the port number is always a 16 bit integer， so。This needs to be protected。

And the constructor will also be protected so that we cannot instantiate this。

Because it's a purely virtual。Bace class。Okay。嗯。Then we will have an8 bit pot。

Construct up what a bit。Destruct down。And then we will have a right method。Okay。

I'll just have two copies of this and to save some time。 I will just search replace。

The number 8 with the number 16。And down here， I will replace the number 8 with the number 32。Okay。

 and I will also make another part version， which is also 8 Bs， but it's a bit slower than。

The other 8 bit parts。 So this will need its own bright version。By the way， Ill make。

I'll make these methods all about sure。So， the other8 bit port。Going to be 8 bit slow。And it。

It extends the8 bit part。It will inherit the read method， so we don't have to overwrite that。嗯。Okay。

This。O。So now let's go into the port CPP。And implement all these things。

So the constructor of the base class will just store。The part number。The constructor of the E port。

 we just。F back on the。Bace construct now。Okay， so the right method。Well just use the asem code。好的。

This。And the reach were。Have some Ram for the result。Which it returns in the end， and in between。

Okay， so this looks good。So I'll just copy this。😔，And search replace the number8 with the number 16 again。

And here the number 8 is the number 32。Okay， and then we just have to replace the asem。嗯。

Cas without W。NW。Open。H。And then have。Also the version for。Slow a。嗯。

So the read for the slow8 bit port is inherited。 So we only overrite the bright version。And。

By just adding。To garbage instructions behind to make the。

To make the program wait a little until the pot is done， writing the data。So。Okay。

 so this should be it。Then put it also in the make fire。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_7.png)

Now， let's see。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_9.png)

好。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_11.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_12.png)

Okay， so this seems to work。Now， this was relatively easy and it didn't take much time。

 So I think we have some time left。So， that。We can。Do two more little things。嗯。In the make file。

 I will。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_14.png)

I would put another make target。The clean target， this is。呃。

This is really a standard target you sees this in make files all the time。This simply。

Delettes the generated object files。And also， the。My corner bin， and my corner。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_16.png)

Do answer。So when you call make clean now。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_18.png)

It simply deletes all the object files and all the generated files and only leaves the source files。

 you the things that you've really written。嗯。So。And then you can just say make run again。

 and of course， it generates everything。Again， so this is really something handy to have and as I said。

 this is really common practice you see this in make files all the time。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_20.png)

嗯。Another thing that I think we have the time。For now is the print F。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_22.png)

Because this print is actually pretty stupid right now， because if you。If you called it twice。Well。

 what happens you will still get the same text only once and that's not really what you want right if you call print F twice。

 you want to have the text twice and the reason for this is because every time we call print F well it starts writing to the first location of the video memory again right？



![](img/255810a0e158f70dcd8fb72cf29aa6ac_24.png)

And。So。Let's use。Yeah， basically something like a cursor。And it makes these aesthetic。And then。

 we just。Yeah， we， we don't write to the I memory location， but to the memory location of the cursor。

 and then we move the cursor after that， okay。So how do we compute。

The location of the cursor in the memory， Well the screen is 80。Characters wide and 25 high。

 And if you remember the oldE days of dust programming。

 then this 80 times 25 is probably very familiar， right？So， to compute the。Memory location。

 we just have to say 80 times y。Plus， x。80 times y plus。X。Then， we increase x。And if。X。Is now。

Behind the right border of the screen， then。We。Do a line feed by。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_26.png)

Increasing y and setting x to 0。And then， yeah， what happens if the screen is full if we have reached。

Bottom of the screen。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_28.png)

Then， okay， this isn't really a good idea， but we will just clear the screen and start from the top again。

 okay。So。Okay， so now we overrite。So I we go through the whole screen and reset everything to。嗯。

To dress an empty。Space character。Right。あ。Okay。So。One more thing I want to do is。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_30.png)

Right now， we don't。 we don't use line feed， for example。 So a back slash and so。

If the I character in the string is a back slash and then we really want to make a line feed because this isn't。

Really， exactly。Pretty， so。And you really want to have that when you call a print F right。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_32.png)

So。Yeah， let's do this like this。So let's have this just as a default case。

To actually put the thing on the screen。And in case it's a back slash n。嗯。Yeah。

 we do the same thing we do here。So we set x to 0 and increase y。Okay， so now we。

 we only really print the real characters。嗯。And the back slash and will just cause a line feed。

 And if this line feed goes beyond the border of the screen， then we will still be。

And we will still clean the screen。 And because the。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_34.png)

The case down here will then apply。Okay， now we have the output twice。



![](img/255810a0e158f70dcd8fb72cf29aa6ac_36.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_37.png)

And now we have it in two different roles。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_39.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_40.png)

So I think this is， I mean， of course， this isn't a really exactly great print F。

But at least it now behaves a little bit more like we would expect it， right？

So this should be enough for now tune next time， next time we will really start talking to the pick and。

Then we will actually receive data from the hardware。Through the interrupts。嗯。So tune in next time。

And don't forget to subscribe so that you don't miss the next video。See you next time。

