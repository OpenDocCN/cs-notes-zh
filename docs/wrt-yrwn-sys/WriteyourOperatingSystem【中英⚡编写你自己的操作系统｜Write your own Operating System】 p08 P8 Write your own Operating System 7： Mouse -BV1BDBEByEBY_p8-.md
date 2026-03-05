# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p08 P8 Write your own Operating System 7： Mouse -BV1BDBEByEBY_p8-

![](img/3e7b57a65ebc69688a6a55c003bd59af_0.png)

Hello and welcome back to the seventh tutorial on writingt your own operating system。

 Now before we start with the mouse， let me show you around a little bit so last time I only had the case for an A for reading the letter A from the keyboard。

And in the meantime， I。嗯。Yeah， I edit a lot of other cases。Right， so。And I also edit this。

Ass a static boolean shift。Okay， so for example， if。

The shift key is pressed and I present A then I'll write it capital A and otherwise。Noncap A。

 lower case A。And。Yes， some other stuff。These cases here， case 2 x0 x 2 a and 0 x  36。

 These are the left and right shift keys right， So and if you press one of them。

 this boolean is set to true。And these are the release codes。 if you release these keys。

 then shift is set back to false。And also， I have， I have moved。Here's this test。 if the key is。

There's a release key into the default state， right。

 so because otherwise we would never get the release codes for the shift key and that is not really what we want。

 right？So。

![](img/3e7b57a65ebc69688a6a55c003bd59af_2.png)

So one thing。If we。If we say make run， we will。 because of this。

 we will get a lot of these warnings here and。I'm a bit。

I'mnerved by this as I'm a bit annoyed by this。 So I'll just copy this W of right strings。



![](img/3e7b57a65ebc69688a6a55c003bd59af_4.png)

And paste it in the。Make file as an additional。Parameter to Gcc， but。W， no bright strings。



![](img/3e7b57a65ebc69688a6a55c003bd59af_6.png)

Okay。So。If I make clean and make run again， now all these warnings are just gone。Now， now actually。

 I can do。Hello。YouTube do。Come。

![](img/3e7b57a65ebc69688a6a55c003bd59af_8.png)

Okay， so。That's what I did for between the last video and this one。嗯。Now in this video。

 we will talk about the mouse。And yeah， after we have done the keyboard already。

 the mouse is really easy because it's almost the same what we have to do。 just one thing。

In the communication with a mouse， you will。If if something happens。Then。I mean， if。

 if you move the mouse， if you press a key on the mouse， a button。

You will get three different ps from the mouse。And you need all of them。 So what I have done is。

 I have。I will put an area with three bytes in there。And have an offset。Running over this area。

 And when you get a bite， it will write。The received bite to the offset and then move the offset to the next step。

 And when。When you are through， So if， if the transmission is complete。

 then it looks at this whole by these three bytes and and calls and x。On that。In a way， okay。嗯。

One problem that I。That I ran into multiple times actually already is。

That this offset doesn't start at 0。嗯。And。I honestly don't know why。And it's。

 it's also not the case that it must start at one， or it must start at 2。

 I'm actually not sure where it must start。 Just what I can tell you is if your mouse doesn't behave correctly。

You probably have to change the offset。 It just has to be a number between 0，1 and 2。



![](img/3e7b57a65ebc69688a6a55c003bd59af_10.png)

And if the mouse behaves odd。The first thing you should try is change the offset between these three values I really don't know why this is the case。

 maybe when we turn on the mouse maybe we should reset it in some way to tell it to start at zero again but I don't know so the quick and dirty hackckish solution is just fiddle with the initial value。

For this offset。So。

![](img/3e7b57a65ebc69688a6a55c003bd59af_12.png)

So what I will do now is I told you this。嗯。Since the mouse is so similar to the to the keyboard。

 I'll just copy and paste the keyboard files。Especially for the header file。嗯。Okay。Now。

 before I forget that， I'll put this also。Here。And in the corner。Okay， like this。😔。

So we again have an8 bit data port command port。Then。Have this3 byte buffer。

And this will always store the last state of the buttons。



![](img/3e7b57a65ebc69688a6a55c003bd59af_14.png)

Because the transmission from the mouse will always give us the current state and to， to see if。



![](img/3e7b57a65ebc69688a6a55c003bd59af_16.png)

ABut has been pressed， we have to compare the current state to the last state and then update the last state。

Okay， this is all we have to do for our that H。Okay， the stuff can。Go away。Okay。

 so the interrupt handleler。Works on。The interrupt 0 x to C。But also。

 but uses the same data port and command port。So we can leave it like this。嗯。Like this。

 we activate the mouse commands。 Then we again， we get the current state of the pick。嗯。

And we set the second bit to true。Like this。And write it back again， like this。Okay。嗯。Okay。

And we initialize。Maybe like this， maybe not， we will see。Okay。嗯。Then in the handle， interrupt。 Yeah。

 we read。The status from the command port。And we test， whether the。Whether there actually is data。

For us， so。So only if the state only if the sixth bit of the status is one， only then。

Only then there is actually data to read， Okay then。We will read that into the buffer。

Ats the current offset。And then。Then we move the offset。Pay， like this。No。

If the transmission is complete， this is a case when we are through， you know。

 if this third byte has been written。Then。AndThis is the case when the offset is 0 now。 Okay。

 so the next transmission would start at the at the beginning again， so。So if the offset is0 now。

 then。嗯。Yeah， then we can look at the buffer。And。Yeah， but but a one。Is the。

Is the movement on the X axis and buffer 2 is the movement on the Y axis， but。嗯。

In the opposite direction， then we would。We would think， so。Let you。Through the following。

So I could do something like。

![](img/3e7b57a65ebc69688a6a55c003bd59af_18.png)

Static U and8 T， X and Y。😔。

![](img/3e7b57a65ebc69688a6a55c003bd59af_20.png)

Like this。 And then here we would do something like。X。plus。他是。1。And why。Minus。



![](img/3e7b57a65ebc69688a6a55c003bd59af_22.png)

我错了。2。So this would so， so now x and y would basically quickly be something like a cursor。

 So the position of the mouse。 Okay， so when you move the mouse， then you。

 you get the the change so the。No。The movement。 And you have to。

To add this to the current position to get the new current position， okay。嗯。

So one thing I want to do now。You know， the video memory， right？ So we had that that it is at 0 X。

 B80，0，0， right。And。

![](img/3e7b57a65ebc69688a6a55c003bd59af_24.png)

The first we， we， we had。Separated this into an array of。Of you in 16s， right， So I'll copy this。

This here。And I went'。To。To display the cursor on the screen now， so。I'll take the same address here。

And。After I have moved the cursor。

![](img/3e7b57a65ebc69688a6a55c003bd59af_26.png)

At the new position， I want the cursa to switch the。The colors around from the character that is now。

You knowSo if this is a video memory。Right， so。嗯。We had this separation into 16 hit integers。

And the first。嗯。Byite of every of these characters， so here is their character。

In the second bite of this power。 and the first character is。There's a pair， again， of one of。呃。

It is one B， and the first four bits are for the foreground and the last four bits are for the background color。

 And if we want to change to， to flip the the color， we will just take the low four bits。

Of this bite and copy them here and take the low the higher four bits and copy them here。Okay。



![](img/3e7b57a65ebc69688a6a55c003bd59af_28.png)

So。That effectively flips the color of the position where the mouse is。Okay， so。And actually。

 I will initialize。呃。The mouse in the center of the screen at 4012。嗯。So what I will do now is。

Video memory。80 times y plus x。As we did before。嗯。So let's first take the high。Forbits。Like this。

And shift them to the right four bits。 So they are now the the low bits。Ofson you。But。

Then we'll take the low bits。And shift them to the left。For bits。And。The last two。

The last eight bits will stay the same like this。Okay。Now， this is。

What happens after we've moved the curor， so。What is the case before we have moved the cursor the。

The old position of x and Y。Is already flipped， and we want to flip that back。

 So before we set the new cursor。 So we'll just have。The same thing here。Hm。😔，And。Yeah。

 I would also put the same。Here in the constructor。嗯。Like this。So。AndNow， the initial。So。

 so at the start， I will flip the。The character in the center of the screen。

Because that's the initial position of the cursa。Okay， one more thing。



![](img/3e7b57a65ebc69688a6a55c003bd59af_30.png)

We don't want the the mouse to run out of the screen， right， or if， if we move the mouse。

Out of the screen。On the right， we don't want it to appear on the left one line below， right， so。

We don't want to have that， so。I'll just say if x is less than 0。



![](img/3e7b57a65ebc69688a6a55c003bd59af_32.png)

Then we put it back to0 so that it cannot run out of the left。And if it's。If it runs out of。

On the right， then we capture it back。Like this。And the same thing for Y。Only was 25。Before here。

Okay。

![](img/3e7b57a65ebc69688a6a55c003bd59af_34.png)

So， let's see。

![](img/3e7b57a65ebc69688a6a55c003bd59af_36.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_37.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_38.png)

Just ignore this message。 It tells you that you don't have。Pass through for the mouse。

 modern operating systems have that。 So they are more designed to work inside a virtual machine。 So。

On a modern and operating system， you could just click on the screen and the。And Vitrobox would。

Would pass this into the。Operating system。Here， we cannot。 We can't have that， so。

When we click into it， then Vibox catches。The mouse and。嗯。

It will keep the mouse captured until we press the right control button。So。Now。

 the now battery box has。Has this captured？😔，And， of course， it didn't work。



![](img/3e7b57a65ebc69688a6a55c003bd59af_40.png)

Why should it。Okay， I found point mistake take。And。So we didn't have the interrupt set。

For the most interrupts。So the handle interrupt request like this。😔。



![](img/3e7b57a65ebc69688a6a55c003bd59af_42.png)

Okay， now it's， yeah， it's okay。 so the mouse is running relatively faster。

 I don't like that so much。 but yeah， it that' what it's supposed to。

So I'm actually happy about this now。

![](img/3e7b57a65ebc69688a6a55c003bd59af_44.png)

So。Okay。嗯。Now， let's see。 I want to。I want to look now， if the。If a button has been pressed。 Okay。

 so as I said， the buttons member will store the old state of the buttons。And。

Now we will compare the old state to the new states， okay。So when we are finished。

 we will just copy buffer 0。And。Here is。So here we move。So， so this， this code actually moves the。

A bit， it， it gives us an。Well。A single， a single bitete with the。With a a one at the ice position。

 And we compare that to the content of buffera 0。Okay。嗯。And if that is different。From the old state。

Soう。Different from。Buttons and。0 x，0，1。Shifted by eye。Yeah， then。Here。

 you can do whatever you do when the eyes button is。I pressed。So， yeah， maybe， maybe just。Why not。

Invert the color again so that we can see something。



![](img/3e7b57a65ebc69688a6a55c003bd59af_46.png)

Yeah。So when I press a button now， then。The cursor disappears and when I release a button。

 it reappears。

![](img/3e7b57a65ebc69688a6a55c003bd59af_48.png)

Okay。So yeah。So this is how you read the movement and the button presses。 of course。

 what I'm doing right now is really really bad design， right mean。I mean。

 directly accessing the video memory in the。In the handle interrupt of a driver。

 that's really a bad idea， right so。A more decent idea would be to have another class。

 like keyboard handler or mouse handler， which just has。A method。

 a virtual method on key pressed on key released on mouse moved on mouse button pressed in all these things。

 And then you would， you would store。A pointer to one of these instances in the driver and then you would put this stupid I mean this nice interesting behavior。

 but you could move this out of the driver because it doesn't belong in the driver really， so。So。

But I think you can do that on your own， and。Yeah， I think this is sufficient for today。嗯。Yeah。

We really went far already， didn't we， So I think。

![](img/3e7b57a65ebc69688a6a55c003bd59af_50.png)

This isn't actually too bad what we have reached now， so。I mean。We can move。 we。

 we can boot our operating system。 We can write to the screen。 We can。we can receive interrupts。

 we set up the global descriptor table， we receive keyboard buttons and mouse movements and everything so。

I think in the next video， I think I will。Tidy up the project a bit so that it is ready for becoming bigger。

 you know， I will。I would have a。I would create a more。Yeah。A more tidy structure， you know its。

It's not exactly a good structure to。

![](img/3e7b57a65ebc69688a6a55c003bd59af_52.png)

To have all the files here in one directory， you know， the object files。

 the CPP files and the head of files。

![](img/3e7b57a65ebc69688a6a55c003bd59af_54.png)

So I will make a。A better directory structure， and。And also， I will put the。

Put all the classes in namespaces and so that everything becomes more tidy and。

Because this is getting a bit cluttered right now。 And I think this is a good point to do this before we start with the。

Was a really。Crazy stuff， like network communication and。

Graphics mode and desktop and GuI framework and other stuff。So。So yeah， so that's enough for today。

 as I said next time， maybe you just skip the next video， as I said。

 I will just tidy up a little bit and。The video after that， we will start looking at the peripheral。

component interface， a PCI。Through which you， for example。

 access your network chip and your graphics chip。Yeah， so this is what we will do next time。

We will make a foundation for really network communication and graphics mode and。

Having a desktop and all the stuff。So。Yeah， tune in next time。



![](img/3e7b57a65ebc69688a6a55c003bd59af_56.png)

Don't forget to subscribe so that you don't miss the next videos。Andll see you next time。

