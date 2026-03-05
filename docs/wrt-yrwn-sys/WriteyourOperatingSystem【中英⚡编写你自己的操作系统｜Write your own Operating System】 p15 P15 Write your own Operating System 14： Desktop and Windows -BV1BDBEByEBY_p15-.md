# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p15 P15 Write your own Operating System 14： Desktop and Windows -BV1BDBEByEBY_p15-

Hello and welcome to the 14th part of the tutorial on Writing Your own operatinging System。Yeah。

 in the last video， we didn't finish the G framework。 So we。

We didn't implement the desktop and the window class。Yeah， we will do this now。And yeah。

 a funny thing。In the last video， at the end of the last video。

 I compiled the code and it compiled fine， so I was happy。And then later， I realized， wait a minute。

 Why did it compile， I didn't implement the contains coordinate method for the。For the widt class。

 So it shouldn't have compiled。 And then I realized， okay。Here in the， in the make file， I didn't。P。

The objects for。For the desktop， widget and window class there are。

 So that's the reason why these codes weren't even compiled into the binary。Yeah。

 so not much to talk about。Beforehand， everything has been discussed already in the last video so we can just jump right back in。

Yeah。Okay， so I will。These。Object files， also here。O。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_1.png)

Now， when we compile， we will get。Less good X results。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_3.png)

So here we get  errorss now。啊。Specifically， we didn't write the contains coordinated method， so。

I will do with that。😔，But the first thing。The first error it reports is。This here in the。

Common graphics context。Now this is the wrong way around。Okay， and now let's implement the。

It contains coordinate method。I mean we we will do this in a quite simple way。 We'll just check if。

This x and Y R。Larger than the x and y coordinates of the。嗯。あ。Of the wret。 and smaller than。

The coordinates plus width height respectively。Okay， yeah， it's important to notice， I mean。

This X and this Y。AndThey are relative coordinates。嗯。But this still works。Because。

Down here in the composite widret。How。Here we。We turn the coordinates that we get into。

Into relative coordinates， also。Okay。So the things that we pass down here are also relative coordinates。

Okay。One thing I thought about。This code here is a bit ugly。Because。Yeah， we only call on mouse move。

Either once or twice， depending， but depending on whether the。The first and the second one。

Its the same。I think a more elegant way would be to。To check if they are the same。

And if they are the same， you will call on Mar move。And otherwise。

 you call something like on mouse leaf on the first widget and on mouse enter on the second widget。

 so。Yeah， I mean， that's common practice in。Guee frameworks。But I'm going to leave it like this。

 You can figure that out for yourself， if you want to。Hello。Okay， one thing。That， I have noticed。

Is in the mouse driver。晚啊。Here when， when we。When we sent this on mouse move。嗯。It。

 it kind of baffles me because。With the mouse cursor in the text mode， this worked。

But when I went through the code beforehand， I noticed that this doesn't work strangely。嗯。

For the desktop。 So I will just cast this to。And。Before passing these to the。To the event handler。

Okay。Now， the next thing， I think it would be a good idea。F负一。

Would derive the wt class from keyboard event handle， you know， so that we don't have to。

To write these on key down and on key up explicitly， we can just inherit them from keyboard driver。

 and then we can just attach a widget directly to the keyboard Okay and we will we will actually attach the desktop directly to the keyboard。

So we can just remove this。And then， we have。Include the header of course。Okay。Likece。s see。Yes。Okay。

 so the keyboard event handler， on key down and on key up， just get a character。嗯。So down here。

 I mean， x and Y was nonsense anyway。Okay， and I also want to derive composite widgets from。

Mouse event handlers。Actually， no， I'm not going to derive composite widge it from that。

 I'm going to derive the desktop from it。The mouse down here。And pass up。

 I will give them an additional parameter。 They will get also。Yeah。

 the button that has been pressed some。Wait， I haven't implemented。 I haven't declared the。

Method contains coordinate。Okay， and we can remove these methods because we we inherit them from the keyboard event handler。

😔，But the one down here。😔，嗯。Yes， for the composite widget。

 we override them so that a composite widget like the desktop can pass the key strike to the focused child。

Okay， and the。Composite widget also needs something like。Yeah， a method to add a child。

Because the children are private， and。You shouldn't access it from outside anyways。😔，Yeah。

I'll make that wood instead sp。So， if。We already have as many children as we can。

Then we will just return false。AndWhat was the。Lims 100。Okay， so this isn't exactly threat safe。

 but whatever。Right now， everything is synchronous still anyways。😔，Okay， now let's see。嗯。

If this compiles。Ds account。Graphics context is in the namespace common。 So that makes sense。快什。嗯。

Okay， the one mouse down and on mouse up。I gave them this additional button parameter。Of course。

 I also have to do that in the CPP file。And in the derived class。Yes。可。P construct。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_5.png)

Okay， now it compares again。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_7.png)

Okay， before I continue， I will add a few more colors to the VGA driver。And also with this。

 these commas were brown。😔，So color one is blue。😔，Color 0 is black。可虫。Sreen。K of far is red。

And color 3 F。It is white。Okay， so now let's start writing the desktop and window classes。嗯。

So the desktop， of course， is a composite widget because it has windows on it。

And the desktop will also be derived from mouse eventhand。O。So， the desktop will。Basically， just。

Just work like the composite widget， so we don't actually have to do much here。But。

We will have to overrite the methods from the mouse event handler to translate the mouse movements because from the mouse we only get relative movements。

 and so the desktop will。Will turn these relative movements into absolute positions of the mouse。嗯。

So， the desktop will get。Mouse coordinates， although I have read that it's apparently not a good idea to hard code a mouse into the desktop。

 for example， because of tablets， you know， tablet doesn't have a mouse cur up so。But anyways。

 I will do this。This way now。So for the desktop， we only need a widthid。Right right。Actually。

 Whitland height could also be unsigned inte， but whatever。And it will also get a color。

So the desktop will be responsible for drawing the mouse。 So we have to overwride the。

Drawing of some desktop。And as I've said。The events for the。Moice一。一般很早。O。Okay。

 so the desktop constructor will go to the base constructor。Like this。

So I'm assuming here that there's only a top level desktop。 Okay， so the。

So it will not have a parent， so this is zero。It will have。

X and y coordinate 0 because it's supposed to start in the upper left corner。嗯。I mean。Yeah， you。

You could do this actually。 you could。Do it so that you can pass other parameters here， because。

I think using a desktop as。嗯。As a child for maybe a window， for example。

 would be probably a good idea。If you wanted to do something like a multi document interface。

 the MDI form parent。That you possibly know from Windows you know where you can have a window which has child windows in them。

Okay， so then it would make sense to， to have a desktop which has a parent and something else then。呃。

0 for x and Y coordinateds， but。I will do it like this here。And I will initialize。X with。Yeah。

 actually with just the width of the screen divided by two so that it's centered。Okay。

 so the initial mouse position is the center of the screen。Okay the on mouse down and on mouse move。

And on mouse up are also relatively simple。So mouse down and mouse up。

 basically just call the event handler for the other。嗯。So I mean。

 this is a mouse event handlo on mouse down， right， it just has a button。As parameter。

 this is what the mouse calls。So if the mouse does something， this is called。

And this translates it to the widget。Form where you get。

Where you get the mouse position and the button。But this is really simple。 We just have to pass the。

嗯。The current mouse position， mouse X and mouse Y， together with the button to the other handler。

So this is all we have to do for a milestone。T mouse。Up。

Then the mouse move is a bit more complicated。嗯。Because we need to make sure that the mouse stays inside the。

The screen。So， but that's not hard。嗯。嗯。嗯。Yeah。你进楚。く。Yeah。ん。Yeah。Yeah。Yeah。Yeah。Yeah。嗯。嗯。Okay。

 and then。When we call the event handle。The Wit event enter。

And then with saw0 new values back in the coordinates。は。And here at the beginning。

 I will just divide the。The relative movement， by far， because it's。Relatively fast。Okay。

So how do we draw the desktop now， Well， most of what we need is already implemented in the composite widget。

So， we look just。Called the parents Vo draw home。And。After this is drawn。

 so after the screen has been drawn， we put the mouse cursor。And。

And I will make the mouse cursor a little white cross， okay。嗯。嗯。嗯。嗯。Okay。

 but now we have a little problem。I'll just show you a problem。嗯。So。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_9.png)

So now I've instantiateated the desktop。 I think that's kind of funnyni。

 Don't you think it's talking about， I instantiate the desktop， but okay。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_11.png)

That's what I'm doing here， so。嗯。Another strange。Way of saying something is， if you comment this out。

 I think it's also a bit hilarious to say。I've commented out the desktop。

It'sSomething that I've said someday and I was really， I found that quite funny。Okay， yes， I'm a nut。

Oh。So let's see if this compiles。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_13.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_14.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_15.png)

Okay， wait right now。 Okay， we have the desktop now。

 you see we have a mouse cursor right now the it doesn't react to the mouse because。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_17.png)

Yeah， we haven't attached the desktop to the mouse。Yet。

So I would just instantiate the desktop up here。Okay， now I have attached the。

The mouse to the desktop。And while we are at， we can also attach the。The keyboard to the desktop。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_19.png)

Okay， let's see。 This should come。Yes。Okay， so now the mouse is connected to the desktop。

 but if I move the mouse， the cursor still doesn't move。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_21.png)

嗯。The reason for this is。We just draw the desktop once down here。And we don't update it。

So I will just put this into this loop here。😔，Although I want you。When we go to the multitasking。

When we start the multitasking， this loop will never。Be executed anymore once we start tasks。

 So this isn't a really good idea to put it here。 but for now it will work。嗯。And also， we should。嗯。

Yeah， we should activate the interrupts， really。Activating the interrupts should really be the last thing we do。

And that's also why we shouldn't do it like this， because。Yeah。

 this is after we activated the interrupts。So it's really not a good idea to redraw the desktop inside this loop。

 but we'll keep it like this for now。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_23.png)

Now you see that screen is flickering a bit， I think that's okay。And now I can move the mouse。😔。

And yeah， the mouse is now really gone， so it's。If you look closely。

 I don't know if you can see it in the video， but it's flickering。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_25.png)

Of here。😔，Whatever so。A problem that we have。Is that。We are calling the put pixel method for the VGA。

And the put picks。Is really。It doesn't care， whether you。Whether the coordinates are legal right now。

 And so far， we have only passed legal coordinates。 But when we move the mouse。

 we cannot be sure that the coordinates where you move them are legal。For example。嗯。

If this is the screen and you move the mouse here to the right of the screen， then。We are。

 we tried to draw the cross， and it's over it goes beyond the screen。

And that's not really what we want。Because then。These pixels will just be drawn in the。

In the next line。So we will just put some。Some security here。う。あ。Okay， these are unsigned integers。

 so x smaller than 0 is impossible。Why are they unsigned， actually。😔，I mean， it might be a bad idea。

 So this could。Potentially， be。Cause。Problems when we cast。Unsign to。

When we cast signed integer just to unsigned。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_27.png)

Okay， now this makes sure the coordinates are legal。😔。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_29.png)

Okay， I still get this strange error that I've talked about。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_31.png)

嗯。嗯嗯。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_33.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_34.png)

O， so。What have I done。Casted this to int8 T now， so。Yeah， strange behavior， whatever。

 So you see the screen is flickering a bit， but now I can move some mouse。

And this is already something I find quite cool。😔，So， let's do the window。Class now。嗯。Okay。

 so I'm not going to do a lot with a window。 I will just。嗯。

Make it able to be dragged around the screen， okay？

And I will do this in a quite simple way I will just overwrite the on mouse down and on mouse up to set a flag。

 which tells us if the window is currently dragged。嗯。And if it is set， then in the on mouse move。

 I will just change the X and y coordinates of server window。一。嗯。Yeah。嗯。嗯。嗯。Yeah。Yeah。Okay， so。Yeah。

 initially。we need to call the base constructor。😔，So initially， we will set this。Flalect to false。

When the mouse is released， it will also be set to false。Un mouse down will set it to true。

 But only if we are clicking with the left mouse button。So dragging set two。😔，Button equallips 1。

And in the un mouse move。I will look if it is being corrected。

Then we will just change the X and y coordinateds。Yeah。Yeah。Come to think of it。

 we should call the base methods for this， of course。Because， otherwise。

The widgets that the windows contained would never be notified。They are being called。Okay， this X。嗯。

If we move it to the right and the new coordinate minus all coordinates。Positive。

 and then we add that to solve。Okay， this is。All， I think。So let's go to the kernel。😔，Now。

 let's make two windows。Attach them to the desktop。Let's say。At coordinate 10，10， and with width。

And height 20。And let's give it color red。And a second window。And let's。

That right next to the other one， but maybe a little bit。downown。So， this is going to 30。So let。40。

And 15。And let's make it a bit bigger like this， but。This one， I make green。Okay， and the desktop。

Needs to be notified。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_36.png)

Okay， I don't know how good you can see this。So the screen is flickering a lot here。😔。

But I'll just move to the mouse over here。😔，It's a bit unresponsive。😔，Okay。

 I will click now and move it。Down here， yes， you can see I can move the window now。😔，O。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_38.png)

Okay， so。Okay， so yeah， this is really all I wanted to do for the graphics mode。

I think this is quite nice now。 We have we have a desktop。 We can have windows and composite objects。

 I mean， I think you can imagine now how to create further widgets， like buttons and。

Text boxes and radio buttons and check boxes and all these。Yeah， so。

So I don't want to go any further into this topic。嗯。But yeah。

 I think it really sucks that the screen flickers so much。I mean。

 the these drawing methods are relatively slow。 I mean， every pixel is set。For its own。

I think graphics cards should have。Methods to tell the graphics card to draw a rectangle on its own。

 so then you would just need to overwrite the fill rectangle with something that calls this method of the graphics card。

啊。So， then。This rendering would not be so slow anymore。But on the right side of this。

Of this class hierarchy here， everything can stay the same。You know， this is really great， I think。

 because widgets， composite widget's desktop window， they were all written in a very。

In a very abstract way。So yeah， you can have a better graphics card driver。If you want to。And。Yeah。

 so a better graphics card driver will give you better resolutions， maybe and。

Better performance when you draw， but。But everything here， everything in the Gui。

And directory can stay the same， so if you want better graphics， better resolutions， faster graphics。

 you just have to change the driver for the graphics card。And， but I'm not going into that。

 And everything here can stay the same。 And that's really nice， I think。So。Yeah， what else？

It might be a good idea to， to have methods， which notify。

Object widgets when they are focused or unfocused。嗯。And。有稳呃。One other thing。I mean。This whole idea。

 the way we did this is actually quite bad， I think。This whole redrawing the screen all the time's。

It's really not a good idea， I think a better idea would be to draw the screen once。

And don't redraw it at all。Hello。So every widget draws itself。 it is so it is there for。

For the time being。But。A a program or any graphical object should have a method which says invalidate this area of the screen。

 Okay， so the。So here's the screen you draw it。With a windows and you don't redraw it all the time。

 You just leave it like this。 And only when something happens like you move a mouse and you。

Maybe you have moved the window now。Over here。 So it's now should be。Like this。

Then you could just mem copy these pixels over here。And invalidate this。

These two areas of the screen。And invalid would mean that you put。Yeah。

 rececttangle objects in a list of invalid。Areas， and then you only redraw these invalid areas。

 You know， the the moved window is just mem copied。 The pixels are just me copied。

 and the area that that we have uncovered is invalidated， and then。In this loop。

At the end of the kernel or later in a task， in an id task， you would just look。

 do I have invalid regions if so， then I say。I want to this I want to redraw this region。O。And。

When you do it like this。It's probably also a better idea not to draw from the back to the front。

You know， drawing the desktop and the window that's there and so on。

 it's a better idea to to draw from the front to the back。

 but that's really a lot of geometry and rectangle intersections and。Whatever。

 So that's really a lot of math behind that。系。But， yeah， I think。I mean。

 drawing from front to back is a lot of math。 But I think if you move the。

The window like this and invalidate the screen。 And if you redraw the screen only by。

By drawing from back to front。And all the widgets react to so the drum method would also need a rectangle object。

And the wts would just say， okay。If I don't have any intersection with this rectangle。

 I just don't have to draw anything I can return immediately。

 and otherwise I will draw into this rectangle， the part that belongs to me so。

So then you can draw from the， from the back to the front and。This should give you。Yeah。

 not a great performance， but a better performance than the flickering garbage that we have right now。

But， yeah。So this is really all I wanted to do for the graphics mode。嗯。Yeah。

 one last thing I want to mention。You probably want to be able draw to render text to write something on the screen。

And。In the last video， I've showed you this。This file。



![](img/ea253ac465ac5a1fbfb1430ecea87b67_40.png)

was a graphic mode。No， it wasn't the last video， it was the video 12。In this file。

And I really have to say this Chris Giezza， big thanks to him。 that's really a great file。

 and it's great that it's public domain。We are not violating any。

Any copyrights or anything if we do this。 So big thanks to him。So down here。

 you will find this bitmap fund。8ight by8， so。So， here you。This is an。诶。A bit met font with8 by8。

Pixel。Characters。And so。When you want to draw an A， A is what is it 54。

 you just go to the 54th row in there， so  eight times 54。啊。I the。The by there is the last line。Of。

Of this spm font。 So the bitete at this index in this array。嗯。Yeah， the。

 the bits of this bitete are just。There's a pixel that down here。And then the next one。

It's a pixel in the next line at first I thought that this would be the first line and then this would be the second line and so on。

 but then I then I had the characters mirrored so yeah it's from bottom to top。So， yeah。

 this really should give you everything that you need to write your own desktop and windows and。

Buttons and text box and so on。 Your text box can get key strikes。嗯。You can have the。

The mouse events and the mouse。Clicking and moving and all the good stuff， so。

So I guess this is all for the graphics mode。啊。I hope this helps you a lot。As I've said。

And even just going into graphics mode。You just don't find any。嗯。Any good tutorials on the Internet。

 except this one that I've shown you。 It's the only correct one that I've found and。嗯。

I remember when I went to the VGA programming for the first time。

 I was really about to quit when I found this one good tutorial。So yeah， there you have it。

 have fun with this。Tune in next time。I think next time will be also very awesome because next time。

We will be doing multitasking。Yeah， next time we will look into how to。

How to have multiple things run in parallel。嗯。But for the sake of that。嗯。I will basically just uncom。

Everything that we did now。So that the desktop and the VGA and the drawing and everything。

 I will put this。诶。In an area that I protect with。With a pre processor directive like this。Yeah。

That's this I'm commenting out。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_42.png)

And so on。 Okay， so， so then you can just。Enable the graphics mode by uncommenting the the define in the beginning and disable it for this。

 because the stuff that we are doing next。Isn't very graphical。 So we'll be dealing with bites again。

 And I think that。That really requires you to be working in text mode again。

 so that's why I'm doing this now。Okay， so see you next time。

 Don't forget to Don't forget to subscribe so that you don't miss the next awesome video on。

Multiitasking。Hit like if you liked the video and see you next time。

