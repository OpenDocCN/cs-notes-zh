# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p11 P11 Write your own Operating System 10： Peripheral Component Interconnect (PCI) -BV1BDBEByEBY_p11-

Hello and welcome to the next video on writing your own operating system。In this tutorial。

 we will look at the peripheral component interconnect or PCI for short。嗯。Well， the thing is。

Before we had drivers for the mouse and for keyboard。And they were relatively。

Relatively simple because， I mean， a keyboard is a keyboard。 You know， it's basically the same thing。

 no matter which keyboard you have。 I mean， there are exceptions， but。It's quite standardized。

 and pretty much every computer has one。 So it made sense to have something like a fixed。

Interrupt for the keyboard and a fixed part for the keyboard。 But if you take just some specific。

Network chip， for example。Not every computer is going to have exactly that keyboard。

 exactly that network chip or a compatible one， right。So。And maybe you， you may。

 you might even have multiple。Network cards with the same network chip。

 So then you would get some really big trouble if you tried to do this like we did it with。

Keyboard and the mouse。Because then you could only access one of them at a time。So。

What people came up with is the peripheral component interconnect， the PCI。And that is really some。

I think some really well designed。Harwell。嗯。So you have your your processor， your。

The programmable to interrupt controller， and。Your PCI controller。

And connect to your PCI controller for example， your graphics card。And your network card。Okay。

 and as I've said， it doesn't really make sense to have a hard coded interrupt and a hard coded pot for these things because you don't know。

Are they even there， are there multiple of the same or multiple different？You know。

 there are just too many different scenarios， so。What they came up with。

 and I think this is really a good design， is。You can talk to the。PCI controller。And ask it， well。

 what。What device is on port number， this， what device is on port number that？嗯。And what。

 what is the interrupt it's going to send to me。And so this really solves a big problem， you know。

 because before we had the situation。嗯。We would have hard coded addresses。

 hard coded interrupt and everything and。Yeah， this this was really a problem。

Because there are just too many different devices， and you can connect them to your computer by putting them in different slots。

You know， all the other stuff， you know， you just don't know exactly the layout of the computer that your kernel is running on。

So this really is a very， very well thought out way to configure your kernel。Automatally。

 so you don't have so the user doesn't have to tell you the interrupts for the different devices。

Okay， so。And anti he doesn't usually have to tell you which driver to use for which device。嗯。So。嗯。

Yeah， let's talk about PCI。嗯。So， you can ask the。As a PCI controller。Well， a PCI controller does。

Has multiple buses， and。嗯。So the PCI controller has up to eight buses。And there's。

 it's not even exactly。 There's some debate what bus even means。

Most people translated with binary unit system， but whatever， I think it's not correct but whatever。

 so you have up to eight buses。O。And then on every bus， you can have up to 32 different devices。嗯。

And yeah。A device can have multiple so called functions。Okay， a function is， for example。For example。

 your sound card。If you look into the。Andto your。Hardware setup up。

 you'll often find the sound card multiple times。 you know。

 once as an audio capture device and ones as。Yeah， a soundcut。So。

So devices can have so called functions。Up to 8 again。Okay， so。So， to。To put this together we have。

8 parts。32 devices each。And 8 functions each。So。So you will need three bits to encode the function。

Three bits to encode the bus。And five bits to encode the device number。Okay。嗯。Okay。

 so I would say let's start with the enumeration of these devices， so we will talk to the PCI。

Controller and ask it。 well， what is the。What is device number3 on bus  one， for example。

 Okay and then it will give us basically2，16 bit integers。So UN and 16 T for the。Vandor IDd。

And UN 16 T。😔，嗯。For the device， I D。So every major vendor。Has its own unique vendor I D。And。Okay。

 you can have there can be at most 65536 different vendors having such a vendor I D。

 I think smaller vendors share Is， I think。But this is really a very useful information when you want to decide which driver he want to instantiate to talk to a certain。

deviceevice。Okay， and every vendor can have up to。65536 different devices。Okay。

 I think there are even vendors who have multiple vendor Is， but。Whatever。

The PCI controller will also tell you。The more general information something called a class ID。

And the subclass I D。So and these are also 160 bit intes。

And these are really useful for some compatibility modes。 You know， if you have。For example。

 there's the class I D for multimedia devices， and then you have a subclass I D for。

For VGA compatible video graphics， array compatible graphics cardss。

 and then you don't actually need to look at the vendor and device ID because if you just want to use VGA graphics。

 then this is sufficient for you and。Then you don't have to drive us for each individual graphics card that there is。

Okay， so but of course， if you want to do something like Harper accelerated 3D graphics。

 then you really need specific drivers for the。Photographics card。

But what we will do in the next over the next videos is。

We will really have a driver for VGA compatible graphics cards。

And to decide that we just need to look at the class I and the subclass ID。Okay。

 so so these are information that we will get from the PCI。 And then based on that， we can。

We can load a driver and put it into our driver array， and then。Yeah， then we can start。

Drawing stuff， okay， and that。That will be a big step， I think。So and actually。

 I think once you have the PCI drive already。I think that's a very big step because when you have that。

Then you have。Basically， everything you need to to really do whatever you want。

 So so then once you have some PCI， you just need to look。

 what are my devices and you just write your drivers for your devices and maybe some。

Maybe some protocols。Implementation， you know， like。Like Ethanana2。IP V4 TCPU。And then， you can。

Communicate and。With networks and stuff and stuff， but。The PCI is really a major step here。

 So once we have that， we are basically in at a point where we can really start doing what we want。

 We just need to。To write the different drivers for the devices。 And， but we have everything to。

To connect these drivers together and load them， so。Yeah。Okay， so let's start with this。



![](img/c5af12040040c953fb8c30fb52c52cf6_1.png)

う。So in the hardware communication， I will create a new file。Pci I dot H。And PC I dot CP。う。ううん。Yeah。

嗯。Yeah。Yeah。聞？Okay。样。Okay， so the PCI controller has yeah。Relatively standard。

 a data port and a command part。In this case， they are 32 bit ports。不。Yeah。いや。Okay。Okay。

 and then of course， one of the first things we want to do is we want to read data and write data。



![](img/c5af12040040c953fb8c30fb52c52cf6_3.png)

And。Yeah we will just have a way of passing the ID for the bus。

 the device and the function along with the read right。



![](img/c5af12040040c953fb8c30fb52c52cf6_5.png)

Comment， so we will have something like。You aim to32 T。😔，ARead methods。嗯。Which gets the bus number。

A device number。And a function number。

![](img/c5af12040040c953fb8c30fb52c52cf6_7.png)

And also。So。嗯。So we will be able to read data from。A certain function。 Okay， and the thing is。

They all have some memory locations。They have some memory， and we。They have a standardized。

Memory space。And。So， we will。We will just have to read certain offsets of that memory。

Where we will find the class ID， the subclass ID， vendor ID， device ID， and so on。So。

What we have to also pass is the offset of。Pro品。Of the data that we want to read。

 you know there's an offset for the class ID is an offset for the subclass ID and so on。So。



![](img/c5af12040040c953fb8c30fb52c52cf6_9.png)

诶。So we also have to to pass。The offset that we want to read。えぱ。And then we'll have a right function。

 which also gets。The bus device number function register offset and also another 32 bit number for the value that we want to write。

O。し。So， in the constructor。嗯。We will set the port number for the data port， and the command port。

Yeah。So the data product 0 x CFC for the PCI controller。And the command port。This number 0 x。C， F 8。

う。Yeah。O。From。

![](img/c5af12040040c953fb8c30fb52c52cf6_11.png)

Okay， so from these three numbers， we will construct。



![](img/c5af12040040c953fb8c30fb52c52cf6_13.png)

Okay， from these numbers， we will construct an identifier that we were sent to the。

To the PCI controller。So the best number is going to be。Shifted by 16 bits。Yeah。So device member。

Will be shifted by 11 bits。Willll be shifted by 8 bits。😔，Then the register offset。嗯。

Isn't shifted at all。😔，Yeah。 and the first bit needs to be set explicitly to one。😔，Okay。

 and we will need to do this both in the read and also in the right。Method。

And then we will write this number to the command port。And after we've done that。

 we can read the result from the data pod。YeahYes。い。But one thing。

You may have noticed the register offset here。We take the bitwise and with the number 0 XFC。

 And that means we are cutting off the last two bits。



![](img/c5af12040040c953fb8c30fb52c52cf6_15.png)

Oice number。So this needs to Yeah， so this is actually。So the numbers are4 byte aligned。

 So this is actually。An address of a byte。But since the bytes are grouped as 32 bit integers。Yeah。

 we would ask for。嗯。For a location of an in。 Okay， so we cannot ask to get the。

Second or third byte from that integer。 We just get the full。嗯。The full integer back， okay。So。

I think I didn't explain that。I think I didn't explain that too。Okay， so。

So here's the data in the device and。Maybe here is fall。Here's8 and so on。

Then when you want to have this buy it。诶。You will have to send the number 4 so that you get this full。

32 bit integer。 And then you just have to extract this bite out of the result， okay。

So you can only ask for a 32 bit inte。

![](img/c5af12040040c953fb8c30fb52c52cf6_17.png)

Yeah， you can ask for number four， you can ask for number eight， but not for number six。

 if you want number six， you have to ask for number four and then just discard。

The bites that you didn't want。So。Then we will do this。😔，あの。我喜欢。Yeah。O。And。Down here。

We basically do the same thing。 We've constructed this identifier that we want to have and。

Then we write that to the command port。But then we don't read from the data port。

 we write to the data port。

![](img/c5af12040040c953fb8c30fb52c52cf6_19.png)

Okay， one very interesting question is。When we enumerate these， all these functions。嗯。I mean。

If there is no device on a certain bus or maybe the device doesn't have multiple functions and it doesn't really make sense to ask for each function individually so。

Because this would make the selection of the drivers quite slow。You know。

So we will need a way to ask a device if it has functions or not。



![](img/c5af12040040c953fb8c30fb52c52cf6_21.png)

Okay。And that's quite simple。嗯。Question of。I'Just implement this。Yeah。So bus number device number1。😔。

InSince we have the read and the write already。This is quite simple then。😔，So。嗯。To find this out。

 we just need to read the。That a bit with the address 0 x 0 E。On function0。The address0， x0， E。

But we only need the seventh sp of that。Okay， so we， we read this。

This address and the seventh bit of that tells us if the device has functions or not。And yeah。

 this will speed up the enumeration of all the devices and the driver selection by a factor of eight。

O。

![](img/c5af12040040c953fb8c30fb52c52cf6_23.png)

So what we want to do in the end is we want to give the driver manager to the PCI controller and have the PCI controller talk to the driver manager and insert the drivers for the devices on which are connected to the PCI controller okay。



![](img/c5af12040040c953fb8c30fb52c52cf6_25.png)

So， we will。Want to have something。Like wait， we don't have drivers yet。Okay嗯。

So we want to have a method select drivers。

![](img/c5af12040040c953fb8c30fb52c52cf6_27.png)

Wwhich will enumerate the buss， the devices and the functions and select the drivers based on the information about class ID。

 subclass ID， vendor ID device ID。And， and it's supposed to。

To put these drivers into the driver manager。

![](img/c5af12040040c953fb8c30fb52c52cf6_29.png)

On its own。こ。Yeah。O。Yeah， and this will look。Relatively clear。嗯。For now， also。

We'll just iterate over the buses。 have a nested loop。

Iterating the devices have another nested loop iterating the functions。Yeah。我。Yeah。Okay。

 and the number of functions。That we have to check will either be zero or。I mean。

A device has at least one function， so。The number of functions is。😔，I will。8 or one。

 depending on the result of this device has function。而钱。Yeah。う。Yeah。Okay。I think it's a good idea。

 although it will be a little bit more to write if。If we add another class here。



![](img/c5af12040040c953fb8c30fb52c52cf6_31.png)

Just to store all the data that we get， you know， the class I， the subclass I， all the stuff。嗯。

And then we will have another method， which will。Which we will call inside the loop， and。Well。

That will give us an instance of this new class。

![](img/c5af12040040c953fb8c30fb52c52cf6_33.png)

Yes。Yeah。So a number for the port that we will use for the communication。 You know。

 this is a number that we will get from the PCI control up。Yeah。One for the interrupt。H到。😔。

So here we were stall at bus。Deivise and function。Ander I D device I D。

Class ID is an eight bit integer， sorry， I was wrong on the whiteboard。う。Yeah。Okay。Yeah。Okay， so。

So I'll add another method。Wtually both a subject descriptal。For a given bus device and function。嗯。O。

Yeah。嗯。で。Okay。Okay， these are just copied over。后。I mean。

 you could pass them to a constructor for the peripheral component interconnect device describedor object but。

Whatever。So。So the vendor ID is on the offset 0，0。The device ID is on offset0 x02。

The class I D is on0 x 0 B。I。Subclass ideas on。00 x，0， a。Yeah。Yeah。O。Okay， so then in this loop。

 we can just call this method here。I like this。嗯。Now。The vendor ID will be either zero or or once。

If if there is no device on that function， okay。If。The vendor ID。Is isza0？😔，It's all once， then。嗯。

Then we can break the loop because then there are no more functions coming after that。嗯。Okay。

 I will just for demonstration purposes， I will put two print fs here。嗯。Yeah。Yeah。嗯。い。Yeah。嗯。Yeah。

Yeah。嗯。嗯。う。Yeah。Yeah。嗯。没异议。Yeah。Okay。Yeah。うん。Yeah。嗯。嗯。对。うう。



![](img/c5af12040040c953fb8c30fb52c52cf6_35.png)

嗯。Okay， so yeah， I'll just。Wait。

![](img/c5af12040040c953fb8c30fb52c52cf6_37.png)

Okay， so now I've included it in the project。And I want。

To be known in the kernel and used in the kernel， of course。嗯。1。嗯。嗯。嗯。这一。嗯。嗯。一个。6。Yeah。Okay。

 so let's see。😔，朋友。Yeah。嗯。Yeah。Okay。Yeah。

![](img/c5af12040040c953fb8c30fb52c52cf6_39.png)

![](img/c5af12040040c953fb8c30fb52c52cf6_40.png)

嗯。Okay， so this is really an interesting output that we have now。嗯。So this really lists。

The devices that we have on our PCI controller。嗯。So。😔。

I think we should come to an end now I think this video is quite long already。

 I think the point that we have reached now is also a good point to make a cut and continue in the next video。

嗯。So the information that you see here is a really， really。嗯。Good information that we have now。

 For example， you see here。This。When多。嗯。1，02，2 device，2，0，0，0。嗯。This is the。Advanced micro devices。

 you know， A And D the the。Manufacturer， which also。Makes。呃，CPUs。That was a quite。

Commonly known for the CPUs。This device was a number to HxA SMMR 2000 that that is the network car installed in。

In this virtual machine， you know， it's the network card with the with a network chip called AM M 7。

9 C。 I write down。So。1022。So this is the。A and D。Network trip。For。A。7，9。C。9ine，7，3。So， if you。

If you write a driver for this chip and you will find quite decent documentation about this chip online。

Then you will be able to send data over the network。 You know， there there's。A quite good。

Tuttorial on that on low level。eu。嗯。And。I mean， okay， will you？Right now。

We have only found an interrupt but we haven't found the memory location that we will use to talk to this chip through memory mapping this is something we will do in the next video。

嗯。But the thing that I want to tell you is。These vendor IDs and device Is are super interesting。

 super relevant data So if you ever have any trouble with a PCI device。

You just look at this vendor ID and device ID and you go for this binary number this hexadationimal number and you will find forums where exactly your problem is discussed in no time and discussed by really competent people so this is really a very。

 very useful information for troubleshooting and the data that you see here is actually。



![](img/c5af12040040c953fb8c30fb52c52cf6_42.png)

The thing that you get if you use the Linux command LS PCI。



![](img/c5af12040040c953fb8c30fb52c52cf6_44.png)

You see here you。You have dis information。It tells you what the。What the devices are。

 you will find quite extensive lists on the Internet， which。Yeah， which。um。Which which vendor I D。

 device I D combination is。嗯。Is which device stands for which device by which vendor know？嗯。

So as I said。😔，This information here is。Very useful。When you are troubleshooting stuff and。

The output that you have here by LSPCI is basically the same output that you get from this list that we've just written。

And you can do。Also， L S USB。Which gives you another barrier。Similar list。

 but not for PC high devices， but for USB devices。 and as I've said， this is really。

 really useful information。When you。When you have any trouble with your hardware and。

When you go on forums on the internet， where people discuss hardware problems。嗯。

The people who help them will usually ask them to send the output of LSPCI or LSUSB as one of the first things they ask for。

And now you really know why and what that does and so on。So。Yeah， that should be enough for today。嗯。

Yeah。So we have a lot of communication with the PCI and the devices right now， and。Yeah。

 in the next video， we will talk about the base address registers of the PCI。Devices。



![](img/c5af12040040c953fb8c30fb52c52cf6_46.png)

They will really tell you。Which memory location the device wants to use for。For memory mapped。

 input and output。And once you have that， you can really。

 you can really communicate with the hardware and send your commands。

 And then you can write the drivers for the devices and have them。Haps the instantiation。😔。

Put the instantiation here in this loop。 So， so then you will。



![](img/c5af12040040c953fb8c30fb52c52cf6_48.png)

Have a really large， a really big leap。For what your operating system can do。Okay， so yeah。

 tune in next time， don't forget to subscribe so that you don't miss the next video。

And see you next time。

![](img/c5af12040040c953fb8c30fb52c52cf6_50.png)