# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p12 P12 Write your own Operating System 11： Base Address Registers -BV1BDBEByEBY_p12-

Hello， welcome to the 11th part of the tutorial on Wting Your ownwn operating System。

In this tutorial， we will discuss base address registers。 But before we start with that， I have。

A few little corrections。嗯。Last time I told you about the LSPCI command in。In Linux。

 and I made a little mistake。The LSPC I。Needs a parameter dash N。And now it。

Now it also shows you the vendor ID and the device ID here。

And another thing you can do is you can say LSPC dash X。

And then it will show you the whole PCI configuration space for all the devices that you have。Okay。

 so。In here， you will see the device Ids and。And the vendor IDs， but with the bys flipped， okay。Okay。

 so that's one thing I wanted to。

![](img/af7ddacc287129bb555c29a156bc9d0d_1.png)

Show you。 And another thing is。Here in the enumeration of the。PCI devices。Yeah， once if we encounter。

A function that isn't present。 And Ive wrote a break here， but in the meantime。

 I've learned that that there can actually be gaps between functions。

 So you can have function 1 and then function 5， maybe， but no function 2 and 3。

 And this break would prevent us from finding。The functions that are further behind after this gap。

So， we have to。Make this a continue instead。

![](img/af7ddacc287129bb555c29a156bc9d0d_3.png)

ok。So let's talk about base address register us。What are they for。So。I mean。

 before we had a device driver for a keyboard and for a mouse， and they had fixed， hard coded。

Values for the port number， and。And further interrupt。 And that kind of made sense， because。

You will usually not have multiple。Keyboards on your machine。And if you had。

 you still have only one focus point， so。So what would you do if you press an A there or an A on the other keyboard。

It would still go to the same。To the same process and to the same window。So。

 it doesn't really make sense to。To do this really differently。 And also。

 it's relatively normal for a computer to have a keyboard。So it made sense to hard code this。

And have fixed values for this in a relatively standardized way。嗯。

But if we are talking about PCI devices， well， maybe you have multiple graphics cardss because maybe you have multiple monitors。

And。Maybe you have multiple network cards。So嗯。So this approach wouldn't work for。For this PCI。Re。

 because if you have multiple monitors， then you cannot have a fixed。A fixed interrupt。

 and you cannot have a fixed part to communicate with that。嗯。Because if you send data to the port。

 which of the。Screens， is it going to？It doesn't make sense。

 right so the solution for this is to use base address registers。



![](img/af7ddacc287129bb555c29a156bc9d0d_5.png)

And these are just registers in the PCI configuration space。I think it's on。呃。Yeah， it's an offset。

0 X， E， so。So，0 X E。There is。嗯。One of the base address register I've selected here。



![](img/af7ddacc287129bb555c29a156bc9d0d_7.png)

嗯。And what does these space register for so。They are for communication with the devices and telling them。

 hey， if something happens。Then please raise an interrupt number。42。

Okay so we could write a 42 to the base address register and then we will get an interrupt 42 whenever something happens。

我。We could say， maybe。诶。We could set another base address register to 23。

 and then we can communicate through port 23。 I think I'm not sure。I haven't done that really。

I've just left things the away they are。From Grub and just reading these things。

 And I'm not sure if they have some default values or if Grub has set these values。

 but it works in what I've written。So and that's really what the only thing I'm really interested in。

So。So you can read these phase address registers。嗯。And。Well they are four bites long。😔。

And the lowest bit。Is telling you the type of。Of the base address registerta。

 So there are two different types。one hour。I owe base address registers。

 this this is for communication with devices that communicate in a。In a classical way。

 the way we also communicated with the keyboard and the mouse。You know， where we have a port and。

We just sent every byte individually to that port， and we read every byte individually from that port。

嗯。So this is the case if this type。It is one。And then the next bit is just reserved， so。We're just。

Leave it the way it is。And then this is just the port number。O。And the port number must be。

A multiple of four。Because the less twos。I just not used。 You know， this is somehow。

You see this design， often when you deal with hardware that。That they just say， hey， the last。

 I don't know how many bits you cannot use them， we use them for something else。嗯。And。

 and then you get problems that。Maybe the maybe an address that you give it needs to be a multiple of 16。

I really don't like this design。 You know， I think it's really a bad design。

 at least from a programmer's perspective， because it makes it quite hard to to communicate with。

呃 with these devices。I mean， I'm sure it makes kind of sense to a hardware guy。呃。

To maybe to save some money or whatever。 But from a programme's perspective。

 it's really difficult dealing with this stuff。Okay。So this this are the IO memory。Oh boss。

And the other type that you can have are the memory mapping。So in case of memory mapping。

 there for devices that use memory mapping， the communication is different。

 you don't send bytes individually and receive bytes individually。Instead， in the memory mapping。

 you tell the device， hey， take this memory location。I don't know maybe these two kilobytes。

And I'll just write data there。And you just take your data from there。O。And。If you send data to me。

 just write it to this memory address and。Yeah， so。

Then I can read it from there and I don't need to read every bit and every bit individually。O。

So this is really。Helps you。Because I mean， this is really good for your running time because the hardware does something in the background while the processor is free to do other things。

 Okay， so this is really good for the performance。Okay， so in the memory mapping。

 the first bit is just0 instead of one。好。Then， we have。Two more bits。Which I'll talk about。Next。嗯不。

The fourth bit is a perfeable bit。

![](img/af7ddacc287129bb555c29a156bc9d0d_9.png)

So。Yeah， for example， a keyboard is not prefetable。 You cannot read。

A key strike before it has occurred。But。For example， a hard drive is prefetable。 You know， So the。

 the operating system might decide， hey， I'll read some data from the。From the hard drive in advance。

 because I because I estimate that your program will need that data later。

 So then I will already have that。To give it to your program。So， but， as I said， in case of。

A keyboard， for example， a keyboard is not prefetable。So that's the fourth bit and。

These two bits in between。They can be either 0，0，01 or 10。And that just means if we have 0， zero。

 it means we have a 32 bit。Memory bar。But by the way， its short for base address register。

If we have01， it's a 20 bit。And in case 10， it's a 64 bit。Memory吧。Okay， so。Yeah， this is。

A bit on the theory of this base address， which is。嗯。In these videos。

 we will really only be using the I O。嗯。address registers。

 So I'm going to show you how to program that。If you're interested in the memory mapping version。

There's some good source code， and I'm going to explain it to you later on low level dot Eu。But yeah。

 let us first write the code for。This title。Please address registerta。如。



![](img/af7ddacc287129bb555c29a156bc9d0d_11.png)

Okay， so。First thing， I'm gonna。Make an enumeration。With the values， memory mapping and input output。

So this will we will use for the last bit of the base address register to distinguish if we have a memory mapping on input output。

でそ。Okay。Then， let's have a class。Pace address for that。Okay， one bulloleion for that。

It was the fourth bit， which we will only be using in the memory mapping。系。分。Yeah。O。Okay。

 and then down here。😔，In the controller method。We will add a methods。

That will give us an instance of this space address register class。あの。It gets， again。

 a bus device function。And。Also。The number of the base address register。嗯。Okay。

One more thing that we will need later。I will add。A reference here to the parameters of select drivers。

嗯。な。T twice。Mi S。Aware communication。Interrupt manager。Okay。Okay。

 and we need this include here for the interrupt that age。So this is what we do under the PC dot H。嗯。

Now in the PC I do CP。What will we do here？😔，So select drivers method。😔，Gets another parameter。

And inside this loop。We will now it the base address registers。哦。う。お。Okay。

 here we will now call this gi。😔，Face。At rest forta。This us。Devicise。反正。

And the base address was which a number。So， if we have。So。

This get based address register will will not set or it will set this address to 0 in case it。

For example， if。Yeah， in case， for example， we don't have actually have the function。Okay。

 if we don't have some function， then we aren't there anyway， but whatever。 So only if。嗯。红你服业。

We really have only if this address is really set。Only then we。We proceed。

So if we have an input output， base address， register and。And the address is set。Then， we will。

And we will set this。The port base value from the device descriptor。Yeah， to just。This address。Okay。

 so as I've said， I'm only going into the input output。Version。

 because I really want to proceed with the next topic。Which is the graphics mode。

 which is far more interesting。Okay。And then what we will do here is。嗯。

We will call the get driver method。 Have we written that yet。😔，I don't think so。 Okay。

 we will write a method get driver。For the device。And have it connected to the interrupt manager。

And if we actually get a driver， then we will。We will add the driver to the driver manager。I axis。

Okay， in the PC I dot H。😔，We will also add。The method that gives us a driver。😔。

Based on our device toto。And it also needs the interrupt manager。Like this。う。Yeah。Yeah。Okay。

Now here we will just return zero for now。Oh， before I forget it in the kernel。

 we call select drivers。😔，But we have added。The interrupt manager。As a parameter。

 so we need to do this here。We also need to put that。O。嗯。Now， what we need is。

The get base address register is。Effort。The。Yeah。Yeah。O。We'll have a result。

 and in the end we return that result。😔，Okay from yeah， as I've told you。

 we are reading the offset 0 x0 E。嗯。And we are only interested in。The first。7 bits of this。Okay。嗯。

Now in case， I mean we itd the base address register number from zero to six or to five。

And in case of the 64 bit。Please address registers。 There aren't actually six of them。

There are only two， so。は。好吧。没。So then this is， then we only have two。And。

If we have requested a base address register， which is behind this maximum。

Then we just returned the results。Which has not been set to anything legal yet。

 So the address is not in this point。And then the loop in the other function will just。

We just do nothing。O。Yeah。Okay。O， now we read the。Opppset。0 x。10。Plus， four times。

Now's this bar numbered？Okay， because the。The base address register does have a size of four。

This is a。This here is a offset。Of the birth。Please address your。Now we have0 x 10 here。

 and then the first base address register is this or second base address register is this。😔。

The third assist and the pro assist and so on。This is what we are doing here。嗯。So。Here。

We examine the last bit。O。So as I've said， the last bit is for the type。

And it tells us if it's an input output。Or a memory mapping is address register。So if it is one。Then。

 it's。Input output。 and otherwise， it's memory mapping。Okay， in this case。In case of。Input output。嗯。

We will set the address。To。嗯。Here to the bar value。But we cancel the last。2 bits。Okay。

 so in this case， we take the bar value。And we， we do a bit twice and。

With the number that has just two zeros here。 So this just removes these two bits from the value。

 and that is taught stored into the address， which is in。Later copied here to the port base。

 And that is the port that we will use for communication， okay。Okay， and in this case。

The they are not prefettriate。Okay， and in case of the memory mapping。

This is the case that I don't really want to go into too much。Here we would。Look at this bar value。

 shifted by。1。And then the binary end with 0 x。3。

![](img/af7ddacc287129bb555c29a156bc9d0d_13.png)

So in this is in the memory mapping case， we shifted by one， so we remove this last bit。



![](img/af7ddacc287129bb555c29a156bc9d0d_15.png)

And then， we take the。嗯。a bitwise and with 0 x3， so this really gives us the last two bits and then we have to look is it a zero a one or a2。

So， case 0。There is a 32 bit。Not。Okay， so one is。20 bit。Not。And case 2 is 64。Its mode。



![](img/af7ddacc287129bb555c29a156bc9d0d_17.png)

嗯。

![](img/af7ddacc287129bb555c29a156bc9d0d_19.png)

Yeah， so。I don't want to go too deep into this。 So if you look into this。



![](img/af7ddacc287129bb555c29a156bc9d0d_21.png)

Article on low level dot E U。嗯。Then。Down here， you have some code。

And it iterates the bars just like we did。 Then it looks at the last。The last bit。

 So whether it's an I O or a memory mapping one。So they have the memory as the IO down here。

And if it's zero。Right if it's zero， then it's memory， it's memory mapping。

 and then they do the same thing。They read the。嗯。As I reads it。The base address register。

 if it's zero then it's a memory mapping and then here they do the same thing。

 they shift the value by one， take a binary and with0 x3 and then have the cases0。1 and2。And。Yeah。

 as I've said， I don't want to go too much into detail。But what they do there。Its the following。

 they copy。嗯。Or once。So。What they do is they write one to everything here。O。And then。After that。

 they read the value back。And after that， they reset it to the value it has been it had been before。

 So they they store the value that was there in a temp。Then they write all once。

 then they read the value again， and then they put the temp back。And why do they do that？ I mean。

 it sounds stupid， right？So。So basically， if this is your base address register。

 they copy that to a attempt。Then they overwrite everything was once， then they read this again。

Why it should be all once， right， after we wrote all once， it should all be once。

 And after they read it， when they just copy this back。In there。 So。

 so it it has the value it had before。So why did they do that。嗯。Because as I've said。

 it doesn't seem to make sense。 But the point is。The device will not accept。Writing all these to one。

 if you set all to one， it has the effect that the device will cancel some of them。

 maybe the first five。And have zeros instead。And maybe。Maybe some zeros in the front also。嗯。

So this tells you which of these bits are actually writeriable。So。So you write all once。

 and then you read it back and where you have a0， then there you cannot write anything。

 So this basically gives you a mask for。Where you can write。

 and this is really an interesting and important information because， well， the zeros up here。

 they determine a limit on how big this memory mapping。

How big the area for the memory mapping is allowed to be。You know it'。Let's say， if。

The first 16 bits are all 0。Then it means that you cannot have more than 64 kiloB large area for memory mapping。

RightBecause then you have only 16 bits left and with 16 bits， you can only。

Address 65536 different memory locations。And。On the other side， the zero is down here。嗯。

They tell you， yeah， as I've said。Because the the the manufacturers of devices often use these。

these sps for something else。嗯。These zeros tell you， well。

 the memory location that I'm using for the memory mapping must start at an offset that is a multiple of 16 or 32 or whatever。

Okay。So that's why they do that and。Yeah。Oh。Not a great design from the hardware， as I've said。

 but okay， this is the way it is。So。Yeah， let's write a little step for the get device already。

So this is as far as I'm going into this， if you are interested in this stuff， as I've said。

 go to the low level。Forum。嗯。And here in the get driver， we would do something like switch。やます。And这。

嗯ん。Class ID。So and here we would have a case， for examples。😔，Case，0 x。1022。So this is。

ThisThis is supposed to give us an driver for the A。诶。7，9。C，9，7。3。So， these are inter devices。I mean。

 in reality， of course， you would have some version of。If you have access to the hard drives。

 then you would just read from the hard drive a file which should have a name that corresponds to these values。

But we don't have access to the hard drive yet。 So what we will do is we will hard code。嗯。

So we will hardcoat the drive into the kernel。That's what we are doing here。😔，If we don't find。😔。

A driver that is fitted for the particular device。Then。We might go into the generic devices。

So if we have a class ID of three， it's a graphics device。And then we look at the subclass Id。

And this is for VGA graphics devices。

![](img/af7ddacc287129bb555c29a156bc9d0d_23.png)

Okay， so this does nothing right now。 It will still just return 0， but we can use that later。

For the instantiation of the。Devices。Okay， so that's enough for now， yeah。As I've said。

 for the memory mapping， we won't be using this。 So if you are interested。

 go to the low level website and yeah everything else。系。I haven't compiled this yet。嗯。



![](img/af7ddacc287129bb555c29a156bc9d0d_25.png)

Works。

![](img/af7ddacc287129bb555c29a156bc9d0d_27.png)

And its still works。😔。

![](img/af7ddacc287129bb555c29a156bc9d0d_29.png)

So maybe maybe have some。Some output here。

![](img/af7ddacc287129bb555c29a156bc9d0d_31.png)

![](img/af7ddacc287129bb555c29a156bc9d0d_32.png)

Okay， here we have some。系啊。Here we have found VGA， the VGA device。

 and here we have found the networks card。Okay， so yeah。



![](img/af7ddacc287129bb555c29a156bc9d0d_34.png)

As I've said so much for today， and。Yeah tune in next time。I think next time will be really。

 really interesting because I want to go into this VGA graphics。Not too deep， but。

I think it will really get you started。So yeah， this。

I think we we are really at a point now where where the the abstraction layer is thick enough so that we can really start working on a more abstract。

Level， which I personally like the most。嗯。You know， to work on a more abstract level。

 not really communicating directly with hardware， but telling the back ends， hey。

 I want to do this and it's a backends job to know how to do this on this or that had hardware。Okay。

So okay， yeah， tune in next time。Don't forget to subscribe。 And yeah， see you next time。

