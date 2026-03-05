# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p09 P9 Write your own Operating System 8： Abstractions for Drivers -BV1BDBEByEBY_p9-

Hello and welcome back to the tutorial onriting Your own operating system。Now， in this eighth video。

 we are going to clean up the whole project a bit because if you look at this project。

 it's getting more and more cluttered。 I mean， it's not very bad right now。

 but it's over time it will become more and more cluttered and confusing so I think we should really tidy up early on so that we don't get into a situation where we cannot unravel this anymore。

So what I'm going to do is。I'm going。To create three subdirecties， one for source files。

One for head of files。And one for the generated object files。And this is really common practice。

But I'm going to do this later in the video。 First。

 I'm going to to do some abstraction for the drivers。 You know。

 right now we have a keyboard driver and a mouse driver。And yeah， they are very。

 They stand on their own。 You know， I want to。Have a little abstraction。

 have a common base class driver and then have a class for driver management。

 which will basically be an array of driver objects and then we can put the keyboard driver in there。

 we can put the mouse driver and any other drivers that we will write data。Okay。

So this is what I'm going to do first。Because this is really the more interesting thing and the stuff with these sub directories。

 this is kind of boring。And。So when I create these subdirecties。

 I will also put name spaces around the classes which correspond to the directory names and then we have to change these。

These， the security。Lines here is， if not defined then defined stuff。

 I want this to correspond to the directory names also。So that they are definitely unique。嗯。Yeah。

 this is what we are going to do now so。Yeah， let's， let's start with that。Yeah。

So I'm going to create。😔，Two new files。😔，Driver do age。And。How about CPP。いそ。So for drivers。

 I'm going to have。We have only a few methods for the base class。1 being。Avoid， activate。You know。

 it was a。So here I want to put this。This code for the。For the activation of the hardware。嗯。

One method reset。Because what you usually do is when you start your operating system。

 you will enumerate the hardware。And。I mean， you don't really know the state that the devices are in。

 So you just reset them， and you need to wait about 50 milliseconds after that。And then。

Then these devices are ready to run and you know the state that they are in。

 so this is really for your security， so I mean it could happen it's theoretically possible that。

You start an operating system， and you。嗯。You shut down that operating system。

 and maybe it goes back into the boot loader and the boot loader。

Then somehow decides to run your operating system。You know， the Linux kernel。

I think it's capable of doing something like that。By now， it's。

So you can do kernel updates without rebooting your computer and this would be a scenario for that。

So。So then yeah， maybe what if the operating system that ran before you didn't clean up everything。

 So， so maybe the hardware isn't in the states that you expect。

 So then you just reset the hardware and then everything is fine。



![](img/92dddb41e74c356cbdf24295a45e4617_1.png)

![](img/92dddb41e74c356cbdf24295a45e4617_2.png)

And by the way， I'm going to have。The reset， return and end。

Which is going to tell us how long we should wait until we proceed with as a good sequence。Okay。So。

 this is。😔，lesss interesting part here。But we will also have a driver manager。

And since we don't have dynamic memory management yet。I'm just going to do this。

I'll just have a fixed length array of drivers。Or pointin us to drive us to be precise。 Let's say。

 maybe。265。 It's always a good number。嗯。O。い。嗯。Yeah。Okay， so this looks good。😔，嗯后。

Now we can put this in the make file。😔，I think it should be relatively far in the front， so。

I it here。And included in the。Okay， now we at the。Keyboard to the driver manager。Yeah。Okay。Now。

 in order for this to work， we need to。To say that mouse drivers are drivers， okay。Yeah。Okay。

So now I put this。😔，Into that activate method。Okay， so this looks good now。嗯。Yeah。

 so the kernel is going to call to tell the driver manager that the driver manager is supposed to activate the driver's now。

Okay， now maybe we want some。嗯。Some status message in here。 So let's have。Something like。

I lying for here and then。Stage one。😔，Stage two and stage3。😔，I think if you remember back in the day。

 I think Windows 95 or something around the time had similar。Stus messages here。In the put sequence。



![](img/92dddb41e74c356cbdf24295a45e4617_4.png)

Okay， let's see if this runs。Okay， as you can see， we are going through the stages and obviously the hardware is initialized because I can use the mouse here。

The keyboardboard interrupt 45 is not ignored again， whatever。😔。



![](img/92dddb41e74c356cbdf24295a45e4617_6.png)

Not so important。The important thing is that the initialization of the hardware is now a little bit more abstract。

 So we now have an array of drivers and mouse and keyboard are just derived from this driver class。

 and so。We can just later put different。We can just put more drivers into this array。

 and this will really take care of most of the stuff for us。So。This was one thing I wanted to do。

Another thing， yeah， now。嗯。You see we had this printing of hexadeadeimal values here and we also had this in the interrupt manager yeah。

 and I really want to take that out of there and put it to the other。Print F method。So。

I'll just copy this。😔，And have。The method for printing。A single bite in exadeimmal。Yeah。Okay。

 this is is going to become a bit ugly。嗯。I mean， if it is。Whatever， I'll just do it the ugly way。

Okay， so now in the keyboard， we can just replace this。With。Yeah。So， then we have to put。

The forward declaration also here。And also in the。Interrupts。Okay。

 and what I've also talked about already is this whole thing is really very messy right now because。

I mean， it it's really not a good idea to have the keyboard driver print the keyet you pressed directly to the screen。

 I mean， what if， what if we put。A graphics mode in between and want to have some desktop or something。

 then this isn't going to help you in any way because。Yeah。

 then then the keys are in a part of the memory where you don't see them。So。

So the object oriented way of handling with the situation is just having。A new class。

Like keyboard event handler。こいく。And then this is just going to have methods。

 virtual methods for on key down， on key up， you know the usual stuff that you see in object oriented frameworks like Java F X and Q and dotnet and everywhere you see these this design nowadays。

Let's have this。Here， also。And then the keyboard driver is just going to have a keyboard event handler。

Okay， and we'll pass this event handler to the keyboard driver through the constructor。嗯。

OhAnd these need to be virtual， of course。Okay，s a keyboard。うん。嗯。

So an interesting question would now be， what are the parameters for key down and one key up？嗯。

I think it would be a good idea to have some internal enumeration for all the different keys。

And pass。Yeah， one of these enumeration values over there， but。Yeah。

 that that would be a little bit overkill for this small project。 So I'm just going to have。

A single character here。Okay， and the default implementation will just ignore these events。嗯。Yeah。

Yeah。Okay， so now we have start handl。😔，Okay， if we don't have an event handler。Then we can just。

And we can just return。Okay， so the in the remainder of the method。

 we can assume that a handler is there。 then we can just replace this print F with。嗯。Okay。

 and I'm going to。Replace all the print of calls here。So I'm going to replace print F with。And love。

放皮。Don。O。So from now on， if we press a key， it's just going to be ignored for now。

 if we want to have it recognized again， then we will have。To do something like this。

 we'll just extend this keyboard event handlock class。

And here I will just put the code right in there with the class definition。でのほ。Okay。

 let's see on key down。😔。

![](img/92dddb41e74c356cbdf24295a45e4617_8.png)

Okay， let's see if this works。😔。

![](img/92dddb41e74c356cbdf24295a45e4617_10.png)

![](img/92dddb41e74c356cbdf24295a45e4617_11.png)

![](img/92dddb41e74c356cbdf24295a45e4617_12.png)

Okay， so。So this works now so the keyboard driver now now doesn't print its keys directly to the screen anymore。

 and this is really a good thing because now we can change this behavior however we want， you know。

 well just if we want the keyboard to do anything else we just。

We just derive a different class from the keyboard Even handler and then just do something else whenever a key is pressed。

And this will be， for example， very useful when we have a graphics mode and we want to pass the key strikes to。

To any applications instead of printing them to the screen。Okay。

 and now we will really do the same thing just for the mouse。And for the movement。Okay。

 and then we would。Now， what are we doing？I know we already have X and Y down here， so。Okay， so this。

lookss kind of okay。You know what I'll just put another method in here。For unactivate。Yeah。Yeah。Okay。

 and now we will just move this。All this explicit stuff where we access the screen directly。

 we will move that again into the kernel CPP。Okay， so this in the handle， interrupt。嗯。

What are we doing here？然后。Okay， again， if we don't have a handler， then we will just return here。

Okay， here is on mouse move。Ced。Okay， I'll extend the onmost move to have。2。Yeah。

 parameters for the old values of x and the new values of x。And why。Okay。Come to think of it。

 I think it's not really a good idea to store values for x and Y in the keyboard driver。

 I think this really should be stored in the。In the event handler。So， I move。This up here。😔。

And these aren't needed anymore。😔，Okay。And these aren't actually necessary in it。😔。

Generally mouse event and I'll put them in here。So then these will just be offsets。Okay change。

 switch the old values。Okay。Okay， so the mouse event handler should not worry about whether the offset is positive or negative。

 so we will。Just enforce it to be given in the right way。Like this buffer  one and minus buffer 2。😔。

嗯。嗯。嗯。Okay。Okay， so then we would have。😔，This。See。Yeah。Okay， so this looks good， so。

If a button is released， we go to the event handler。😔，Okay okay没。



![](img/92dddb41e74c356cbdf24295a45e4617_14.png)

Let's see。

![](img/92dddb41e74c356cbdf24295a45e4617_16.png)

I don't work。

![](img/92dddb41e74c356cbdf24295a45e4617_18.png)

Okay， I found the problem， I think so the data port read was skipped if there was no。

 but this cannot be the problem。😔。

![](img/92dddb41e74c356cbdf24295a45e4617_20.png)

![](img/92dddb41e74c356cbdf24295a45e4617_21.png)

Okay。Yeah。

![](img/92dddb41e74c356cbdf24295a45e4617_23.png)

![](img/92dddb41e74c356cbdf24295a45e4617_24.png)

Okay， I found the problem。This is really ridiculous， I instantiateated the wrong class。Okay。



![](img/92dddb41e74c356cbdf24295a45e4617_26.png)

![](img/92dddb41e74c356cbdf24295a45e4617_27.png)

Okay， so everything works as expected again now。Okay。

 so this took a little bit longer than I expected。Well。

 I'll just do this stuff with the directories and namespaces and everything just in the next video。

 Okay， so because I think this is really enough for one video now。 So yeah， see you next time。

 and sorry about the delay。嗯。Yeah， watch the next video so then we will really have the whole system cleaned up。

And yeah， don't forget to subscribe so that you don't miss any of the next videos。



![](img/92dddb41e74c356cbdf24295a45e4617_29.png)

See you next time。