# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p18 P18 Write your own Operating System 17： Networking -BV1BDBEByEBY_p18-

Hello and welcome to the 17th part of the tutorial on writinging Your ownwn operating system。

Now in the 17th tutorial， I'm going to show you how to communicate with。With the network car that。

AV box offers。So。Yeah， this is an。A device by a virtualized device by A And D as a chip。A M7，9， C，9。

7，3。然后呃。This is actually a relatively complicated device。I hope this doesn't take forever。😔。

Here in the code that I've prepared。It's。Yeah。It's about7 pages long。

 so I'm a bit afraid that it will take quite some time。 As I said。

 it's a quite complicated device so。There's a lot that we have to do。然后。Yeah。

 I want to show you this。The site here on low level E about the AMD PC net。So， this。

This is where I've got a lot of the stuff that I'm else that I've written here。Actually。

 there there has been an error before。So when I wrote this for the first time。

 it didn't work and it took me hours。I think even more than a day to find the error I had I really had to go into the documentation of the actual chip and。

And compare really every byte that was in the documentation with the code that。I had。 And， yeah。

 then I really found that。There had been a mistake。But don't worry。

 I've reported it that mistake and on the side it's been fixed by now。So。Yeah， so。

I think a lot of the things that。We are going to talk about relatively familiar by now。 I mean we。

We will make a class for this device， which will be derived from driver。嗯。

It's going to also be derived from interrupt Tr， we will get the interrupt number and the part numbers from the PCI。

So this is the first time that we actually do something with the stuff we get from the PCI。Yeah。

I'm not looking forward to this。 So the initialucization of the device is really a lot of code。嗯。

Sending and receiving data。 Yeah， it's not that much。Okay， so。One thing that。

That I want to talk about before we start this。So this device can have multiple send and receive buffers。

And for every of these buffers， you need。An instance of a structure， which。

Mainly has a pointer to that buffer。One problem with this is， yeah， this is one of these。Devices。

 which。Apparently use some of the bits in the addresses for something else。So because of this。

The first。The index of the first by of a buffer needs to be a multiple of 16。So， yes， so。

I haven't found。A solution for this problem that I really like。嗯。

I think there was something along the lines of， you can tell GCC。

That some data structure needs to be aligned like this or like that。I'm not really sure about this。

So the best solution that I've found is to just。To just have。15。Additional bites。Yes。

Then so we will have a buffer of size 2 kilobytes。And actually， we will reserve 2 kB plus 15 B。

 and then we will use the first address plus 15。And kill the last four bits to get somewhere inside that。

Somewhere inside that。2 kB plus 15 B。 we will find。呃。One address that is a multiple of 16， okay。

So yeah， not really a great solution， but。As I've said， it's the best that I've found so far。

So let's start coding， as I've said， it's a lot of code。😔，So。

I want to don't want to talk about it too much。😔，So that we。We get through this。😔，Today。Okay。

So I'm going to include this in the PCciI。t H。お。Yeah。So that in the PC ICPP， we will be able to。

Instantiiate this。嗯。But the。The constructor will get。

This PCI device descriptor and the interrupt manager。As parameters。ます。没有。Okay。

 so this driver is going to be an interrupt tanlum。And it's going to have a lot of partss。 This time。

 it's actually 16 bit partss。Yeah。Yeah。So we have three ports for reading the media access control address。

 the Mac address。あがと。So each of them gives us two。By it's of Mac address。Yeah。我。Okay。

 so these seven ports。Then。嗯。Its also going have an instance of that。

Structure initial civilization block， which I haven't defined yet， I'm going to do that later。Okay。

Yeah， and then I'm gonna have this。The 16 byte aligned。嗯。Bs。8 send buffers，8 receive buffers。嗯。

So8 buffers of size 2 kilobys plus Cs 15 for the alignment。😔，Yeah。Yeah。Okay。

Then I need some memory for these。😔，For these descriptors for the。Of us。

A problem with them is they also need to be 16 byte aligned。So I'm going to just allocate some。

Some Ram here。😔，And for the。Receive buffers。我看定。嗯。And then I will just move a pointer to。

To a buffer descriptor into this memory。う。O。So these perfect descriptors look like this。😔，Actually。

 I'm going to do this as a nested class or structure。😔，Yeah。So that the scope is。Unique。Yeah。嗯。O。

And attributee picked again。Okay。There is so much code。😔，And this initialization block here。

Looks like this。So we have 16 bits for a mode。😔，I think with this， we set it to。32 bit mode later。

Yeah。Oh know， actually， this is for Promiscuous mode。O。Then we have four reserve bits。W。

Then the number of receive buffers and number of send buffers， which。For bits。 And they actually。

Define how many bits。 So we， we will write a three in there。

 but that will mean that we have8 buffers。Okay。Then we will have。😔，Yeah， this。The Me address。

 I think。Okay。But this isn't actually 64 bits， it's treated like a 64 bit number later。

But it's 48 bits。😔，Yeah。Okay， we had the physical address。Here's a logical address。Okay。

I'm not sure this might be for the I P address， but I'm not sure。On this level。

 we shouldn't actually be concerned about the I address。Yeah。Okay。Oh。And a trie packed again。😔，Okay。

お。Then， we need。A number which tells us which of these 8。

Receive and send buffers are currently active。Okay。嗯。Okay， from driver， we will。um。

Inherit these two methods and overwrite them。And from。You interrupt hand now。We were。

Inherit and overrite this handle interrupt method。ふ。Okay， we haven't done anything for。Sending and。

Receiving actually， at least in the。Not in the。But in the interface here。But I want to get into the。

嗯。I want this to at least run at a point and I want to initialize it。う。Okay。Okay。Yeah。Okay。

 so now in the constructor。So we initialize this as an interrupt hand。😔。

So we pass the interrupt manager and the interrupt number that we reserve for ourselves。

Is what we get from the device deor。But this actually needs to be。Yeah， this must be。呃。

Increased by this offset that we used。For the hardware interrupts。好。Yes。IEx this， okay。

And then we initialize these parts。红色。是子。😔，Part base。Is what we get from that PCI。😔，This one。嗯。

Okay so I moved this out of here because I only want one driver for the device and not for every base address register done。

😔，Okay， so the port address as the port base is what we get from there。Yeah。Okay， now a second。Okay。

Offet 0， offset 2， offset 4。😔，I offset 16， except is sum 10 as the the register data part。😔。

Register address part is 18。Reside part is 20。And this is。2。Okay。Okay。Yeah。O。Okay。

 when we want to reset。We just。Ts reset set port。然后。And after that。

 we should wait for 10 milliseconds。 That's what this means。😔，Okay。Yeah， in the initialization。哎。だます。

Yeah。へ。So much code。O啊。So， in the。Constructor。I'm going to read the Mac address。Yeah。好了。好。Okay。

 so we set the device to 32 bit modes。😔，So we write 0 x1，0，2。To the register number 20。Yeah。And。

I don't remember what this was。😔，We set the stop bit。I think。This might have to do with resetting。

We tell it that it's not supposed to be resettinnel， I think。Okay。

 then we set the initialization block。So this means8 buffers because it's 2 to the8。

 so the number of bits we use。Okay。Okay。think a tricky。You correct。Okay， now we do this。😔。

All this garbage with these。嗯。With these buffers and their descriptors。So， we moved the。嗯。

The pointer。15 by to the right and then kill the last bits to to move it to a 16 by aligned。Attress。

いぱ？Okay。And the same for received buffer。😔，太好了。Okay， terrible。No。So now we've moved。

 so we've selected the memory for the descriptors and now we have to set these descriptors。😔，嗯。

And here we basically have to do the same thing again。So with this， we sent the length of the。

Descriptpile。And 7 zeros。Okay， so this tells it that it's a receive buffer and not a send buffer。😔，嗯。

O。So now we have constructed the initialization block and now we move this initialization block into the device。

Yeah。Okay， so this should do the miniurization。😔，Yeah， I told you it's a lot of code。😔。

And we aren't actually even finished。 So this is only in the。Constructor。

Now in the activation method。て。So I think this enables the interrupts。😔，Wait， why does this mean。

Why is this even supposed to work？😔，So we eat。😔，The thought。Patrita， and then we write it back。😔。

But we set the， I don't know， what is it。😔，The 20th or something。I don't know，12， it's late。😔。

I'm a bit exhausted。We set one of the bits to one。O。Okay。Now in the handed interrupt。😔。

I think this is also necessary。I think this is similar to the programmable interrupt controller。

Where we have to read the data that we want to。I mean， if it tells us that there is data。

 we need to fetch it。No。So， now we。Read the rich and number 0。Now。

 we cannot do a switch case statement because multiple of the bids might be set at the same time because you might have different。

Errows at the same time。Yeah。So if we get exit center 8000。😔，This is just。A general isarrow。走吧。

2000 is a collision error。1000 is a missed frame， so。Basically， stuff like。

We get just too much data faster than we can handle it。So if we have missed a frame。

 let's say our out for that。😔，So this is when we get data。And 200 is。

If it has successfully sent data。😔，I'm not sure why this is done here in my code。

 but this says that the initialsization is done。😔，ふ。Okay， so that's what was a lot of code。

 and this is all just the initialization， you know。

 we haven't actually even sent or received anything。😔，Yeah。一。Okay。そ。Okay， let's see if this compiles。



![](img/a5d628cc685cf1eb5c09a79a6b7374e4_1.png)

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_2.png)

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_3.png)

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_4.png)

嗯。

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_6.png)

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_7.png)

Okay。老不。So。The device requires。The PCI。And I try to include the device in the PCI again， so that。嗯。

The class definition was before the definition of peripheral component interconnect device driver by Descriptor。

是。This。Well since this is a mock up， I think it's fair to put it here。 you know， in the end。

 this isn't supposed to be hard coded in it anyway。😔。



![](img/a5d628cc685cf1eb5c09a79a6b7374e4_9.png)

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_10.png)

Okay， so。Nothing has happened now。😔，Yeah， I mean the。The activate method un called， I think。

Because down here， I just instantiate this thing and don't add it to the driver manager。I work。可然啊。

Now I return it。😔，And add it to the driver manager。😔，And then the driver manager， when I go into。

TheDri manager activate all。 It should call the。

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_12.png)

Activate method。 And then we should should get something。Our great crashed。😔。

HeActually it has gone into the。😔。

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_14.png)

I think I know what the problem is。😔，I didn't return anything here。

So then I probably return 0 or something instead， and。Then the stack pointer would be set to0。

 and that would really cause such a problem。😔。

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_16.png)

Let's see if it doesn't work now。😔。

![](img/a5d628cc685cf1eb5c09a79a6b7374e4_18.png)

Okay， we have gotten some interrupt from。Z device。But。Doesn't really say what the interrupt was， but。

I don't care。 You know this。This is really all I wanted to achieve today because this is so much code。

So this at least tells us that we we successfully have initialized the device。 We have activated it。

And， yes。I'm quite happy about that。Even if。I don't really know why it doesn't tell us anything more。

😔，It just says interrupt， but not which one so whatever。😔，I really think this is enough for today。

 a big， big step we are now finally able to communicate with the network device。So yeah。

 in the next video， we will start sending data and receiving data。

And then we will start building our networks back on top of that。Ethernet2 frame。

 address resolution protocol， Internet protocol， Internet control message protocol。

And all the other protocols you know， but that's going to be a lot of code again， too。Although， okay。

呃。IP， ICMP， UDP， ARP， Ethanna 2， they are all relatively simple compared to TCP。 I can tell you that。

We can get through that， but not today， this is enough for today so yeah。

 if you want to see the next video just hit subscribe so you don't miss it。If you like this video。

 hit like。Although I have to admit this was really a lot of tedious code， code， code， code， code。

 because it's just so much code we have to write。Not really much to understand。Hello。Before that。But。

 I mean， it's also， it is a relatively complicated device， you know， so。So what are you going to do。

 this is just the way it is。So， yeah。Have fun with us and see you next time， bye。



![](img/a5d628cc685cf1eb5c09a79a6b7374e4_20.png)