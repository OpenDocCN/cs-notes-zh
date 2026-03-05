# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p14 P14 Write your own Operating System 13： GUI Framework Basics -BV1BDBEByEBY_p14-

Thenear welcome to the certainth part of writing your own operating system。Yeah， in the last video。

 we went into the graphics mode， which is really a big step。So we had a very big milestone。

But we don't want to stop there， I mean now we have a graphics mode。

 but what good is a graphics mode if you don't do anything with it。

So the next thing I want to talk about is。Yeah， really a graphical user interface。

 a Gui framework and。Yeah， the go frameworks are usually quite similar。If you know。嗯。

Object oriented Gui frameworks。 They are all relatively similar。 in know， cute or。嗯。

C++ builder or dotnet or Java swing， Java FX， and so on Moif。

They are all relatively similar in their design。And yeah， we will write our own GuI framework now。

But I'm a bit undecided on how deep I want to go into this。Because， I mean， this is a bottomless。

えなるく。You can go very， very deep with。With tap order， you know。 So when when you press the tab key。

 then you pass the focus around inside your window and stuff。

You can have enter on mouse leaf events for your graphical objects and so on。嗯。

So it's really endless what you can do。嗯。But I think I'm not sure how。

How we will get around with the time。 You know， I don't want to。Go to spend too much time on this。

 because。This whole thing isn't actually， if you ask me， it's not really。

Part of the operating system itself， you know。I mean。

 the desktop and the stuff is in actual operating systems。

 they are separate processes that the kernel loads from the hard drive and runs。

So they are not really part of the kernel themselves。

But I think they are so important parts of an operating system that you should at least have some understanding of how they work。

And okay， our operating system right now still works very， very。In a very synchronous way。I mean。

 in a total synchronous way。诶。So。Yeah， whatever so。If you've seen any object oriented framework。嗯。

This you will probably have somewhat of an idea how this works。Yeah， by the way。

 I don't even know if I will find the time to write any actual code for this because。

We can have really a lot of stuff going on。Hello。But at least in theory， I want to go through this。

So we had this VGA。Class， right？And in practice， you would put a base class above that。

So that it is derived from something like a graphics context。

You know in the graphics context would define something like put pixel and draw a rectangle。

 draw a line for example， I'm not going into the draw a line method if you want to know how to draw a line in a good way it sounds simple but。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_1.png)

If you want to do it in a good way， look up the Raszenham algorithm。

That is the best algorithm for writing lines to my knowledge。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_3.png)

Okay， so the graphics context would define something like the put pixel。And also， fill rectangle。

And the usual stuff like。Like， draw a line and。Draw circle or whatever。嗯。

But the important part is these other methods like fill rectangle should。

Should have a default implementation which relied just on this put pixel method so that in your actual graphics contexts。

You only need to have this put pixel。Methd， and then everything else should should。

You should be able to do everything else just by overriding this putp method。

So all the methods in here should。Should fall back on this split pixel method。嗯。Yeah。

 in the last video， I used this。I had this parameters RGBA， RGB。Forlor red。

 green and blue channels of a color。But in practice， you would have another class。好看了。And then， have。

When have a。An instance of this color is parameter。

Here for us put pixel and field rectangle and so on。O。And then。Yeah， the GuUI framework itself。

Would start at something like widget。In the windows， I think it's called gadget or whatever。然。

So that would be the base class。And the space class should basically just have a draw method。So。

 a method。That gets a graphics context。And so that the widget draws itself on this graphics context using these putps。

 fill rectangle， and so on methods。And your widgets。

 if you have something like a background color or something。

 then this would be an instance of this color and not。Three separate lights for RGB。But， yeah。

 a widget itself doesn't。Necessarily have a background color。 So I'm not putting。

The color instance in the base class here。嗯。Okay， yeah。

 a widget will usually have something like X and Y coordinateds relative to some parent。

Which is itself a pointer to a widget。And then when you want to draw the widget。嗯。When， yeah。

 these coordinates are relative coordinates， but you want to draw it on a graphics context which works with absolute coordinates。

 So you would need a way to。To get the absolute coordinates on the graphics context for。

For this widget。 So you would need a method like。Vid mother to screen。Yeah， with this x and Y S。

Called by reference。And and x， and。W and then inside this model to screen。Yeah。

 you would basically call the model to screen of the parent。And。

So if you have your object here and there's its parent and there's its parent。

Maybe this has coordinates 1010。And this has coordinates。20，20。And this has coordinates 5，5。

 Then what you want in the end is。So， this。Will be the root。The desktop， wt。系啊。So in the end。

 you meet the absolute coordinates 35，35， right， So you call the screen to the model to screen method of the parent。

And it's just supposed to add its own X and Y coordinates to these。Values it got by value。

 that by reference。Okay。Then。You would usually also have something like a width and a height。啊。And。

Something like。A Boolean method， which tells you if。If this widget contains a certain coordinate。So。

 it contains。Coordinate。Which would just answers a question of whether it contains a coordinate XY。嗯。

And it would just。Look into the question， is this X？Larger than this x and smaller than x plus w。

And is this y also larger than this y and smaller than y plus H。If so。

 then this widget contains this coordinate。O。And this is really。

Necessary for a lot of stuff with the mouse。Have been。ま。Okay。あの。Okay。What else， so the witcht？Yeah。

 I think it's a really good idea to make these widgets have something like。And one mouse down。

One mouse up， one mouse move。But maybe not。So I think widget should not really be derived from。

From mouse handler and also not from keyboard handler。 So with on key down。And one key up。嗯。

So I want these methods， but I don't want to derive widget from mouse handler and keyboard handler。

Because the mouse， for example， only gives us relative。Relative movements in the Mo method。

 it doesn't give us coordinates where we have clicked。So。In my opinion， it would be a good idea to。

To have the desktop。Talk to the。To the mouse and keyboard。Install something like the mouse position。

And then call the un mouse down， on mouse up， on mouse move。Methods。With this。

 with these start positions of the mouse。And also， on mouse down， would also get。The coordinate。

 the current coordinates of the mouse also for the。One mouse up。

 and the mouse move would do something like X， Y。 So the old x and y。And x plus the x offset。

And y plus the y offset。So that you can react to these things。Because for example。

 the other one very important subclass is going to be something like a composite object。

 a composite widget。Which has an array。然。Of childhood wrets。And yeah， in in this un mouse down。

 on mouse up， un mouse move on key down on key up。The composite widget。嗯。

Would basically call all these methods， it would overwrite these methods。

With methods that invoke the corresponding methods on the children。

 So the draw method of the composite wge， for example， would， well。

 it would draw some background color。系啊。Inside this rectangle。And then call the draw method。

Of the children。In reverse order。 and also the。The widgets， which are further behind。

A lower in the Z orura。So they are further to the back of the screen。So they need to be drawn first。

 and then we draw the。Widgets， which might be in front of the other ones so that they overlay the widgets。

 which are further behind。Okay。So for example， this would。Do the draw。嗯。Yeah。

 if you have something like on mouse down。In the composite widt。

 you would just iterate through the children and ask， hey， hey， my child。

 do you contain this coordinate that has been clicked？If so， then I invoke your un mousedown method。

 and otherwise I'll proceed with iteration of the children。Okay， and the。I think， so。

It's a good idea that the default implementation of on mouse down does something like get focus。

What parameters as this？Which and in this get focus method calls the get focus method on the parent and the parent and the parent so that it goes upward in in the widget tree。

嗯。Until you hit。呃， window。The window class， which overwrs this get focused method with storing the。

The parameter in。A focusedcus widget。 So we would have something like。Widdget pointer。😔。

Focus Richard。And here we would override。Here we would overwrite this get focus method here。

With something that doesn't pass pass as a。The quality to the parent but。With something that stores。

The thing that you have passed here in this focused widget， because。In the on key down， I mean。

I mean， in the un mouse down， it makes sense， you know， the un mouse down for a composite object。

 it looks through its children and asks hey， is this for you， Yes， okay， then take it。

But what's with keys， I mean， a key doesn't have a coordinate， so。嗯。So you don't necessarily。

So you don't know which child to send this key strike to。O。So。So a window just has a focused widget。

And the on key down。Which then cause a。One key down of the focused widget。Right。Okay。

 so if you click on a widget， it tells its parent hey， give me the focus。And when you。Pss a key。系啊。

When this focused object gets the key。O。Okay， another class that you would derive from composite widget is a desktop。

And I know it sounds。Its somewhat funny that the desktop is derived from something。

 so the desktop is a widget。In a way， but it makes sense because。I mean， windows are also widgets。

 so the desktop can use。This area to。To store its。The window set in mail。

And the desktop would also have something like a focused widget。 I would call it。Wichard。Active。

Window or something。So this get focus after storing the focused widget would call its own get focus method。

 but。With。But it wouldn't pass。嗯。The value that it has gotten。Through the parameter。

 but it would send itself。Up to the desktop and then the desktop would do basically the same。

 It would then store the active window here and do a very similar thing。 So if you have a key down。

嗯ello。You pass that key down to the active window。And。And un mouse down。嗯。Yeah。

If the un mouseed down goes into a different desk into a different window than the active window。

 then you would change， then you would。Yeah， change the active window。And all then。

You focus a different window。You know，So the the get focus method of the desktop。What's。

Would take this。This newly focused window out of this array and move it to the front。 And also then。

跟。This window is activated， it's put into the front of the Z order。O。Yeah， okay。 I think this is。

Yeah， I think this really gives you a good idea what。What such a degree framework would look like。So。

 yeah， I haven't spent so much time on explaining it so。😔，I think we can just program some of this。

Oh。嗯。So let's see， I think I will make a new。Dirrectory here。狗用。And great。は。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_5.png)

から。

![](img/bdb1077a8ca4413ce5db853e8f3b755b_7.png)

ok。Wres。好。Okay。It。你。嗯。嗯。Yeah。う。Okay。And yeah Ill。To prevent writing。A color here。嗯。Yeah。

 I will just hard code something like。And。ち。1。嗯。Yeah。Yeah。嗯。然后。嗯。嗯。Yeah。Okay。Okay。

 this graphics context dot H is not defined yet。诶。I will basically just fake this。😔，一人看多。Yeah。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_9.png)

Okay。不错。不不不。Yeah。Okay。嗯。Yeah。Yeah。で。So in here I will just。Just to save some time。

 I will just type de。Graphics context。As。S so。VGA driver。嗯。Okay so I've just faked this now。

 so the class graphics context doesn't actually exist， it's just this VGA class that we had before。

Okay。Let's also have a constructor。Okay。一般。嗯。Okay。き？う。

So the get focus in the default implementation just passes on to the parent。Widt。

 unless there isn't any， so。If the parent is not。Zero。When。We pass。The quality was the parent。好。Okay。

は。Okay。哦。Yes色。嗯。3。So to get the。The absolute coordinates。Yeah， we just。Yeah， we just get the offset。

嗯。From the parent and then add our own offset to this。O。In the default implementation。

 I think I will do something like graphics context。是。Rectangle。好。For the。

We need the absolute coordinates at this point。Actually， we set these to zero because。

The model to screen also adds our own X and Y to this。So。Then we proceed with third rectangle。😔。

With x and Y， width and height， and our colors。Okay。Our un mouse down。嗯。Just as。Get focus。This。嗯。

Yeah， this。We might have。 We might put something like a Boolean value。 Like。

 is the widget focusable at all。 And if it isn't， then we don't call this， so。

So we would have something like。我这不啊。Really focus ofably。😔，Yeah。

 but I will just set this to true all the time。😔，O。So the default implementations of。

These methods will just ignore them。O。Okay， okay， okay， yeah， we are using this fill rectangle here。

啊。I think I will。Yeah， this should。In the VGA。嗯。没有。Okay。

 and this should basically just be a copy of this。This here。O。Okay， like this。嗯。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_11.png)

Okay， let's see if this compiles。

![](img/bdb1077a8ca4413ce5db853e8f3b755b_13.png)

好。哈滨。

![](img/bdb1077a8ca4413ce5db853e8f3b755b_15.png)

![](img/bdb1077a8ca4413ce5db853e8f3b755b_16.png)

Okay， so this still works。😔，Yeah，あ。Yeah， inside this same widt dot H， I will also put a class。不。

Composite wt。😔，Which will overwride most of these methods。一。Yeah。Yeah。う。Okay。

 so the mother to screen。😔，We don't have to override。😔，嗯。On keep down。 on keep up。

You do have to overriteide。One mouse down up， move。Let's see。What makes sense。嗯。Okay。

 so the main difference will be this get focus。😔，不非法。そ。死的事。

So the focused child is now the widget and。嗯。お。あも。O。Then， one main thing。

It's going to be this on key down and on key up。Wait， why is this。嗯。Okay。

I think you see now here what we are doing with this composite objects。😔。

The draw method of the composite widgets。We first。Draw its own background。So like this。😔。

So this draws a background。Yeah。嗯。嗯。系。Okay， so this draws the children。O。Yeah， so。

Here we will iterate through the children。😔，Again， in this mouse down， mouse up and mouse move。嗯。

And pass。知啊。And pass the event to the child that contains the coordinate。好吧。So I'm almost mouse down。

😔，I passed to a child， which contains so coordinate。But here。

Here we actually need to go from zero to9 children。

AndBecause the children with a smaller index are further in front of the other ones。

 So if you have two children and one。Is in front of the other than this。 The front child is。

Encountter first。嗯ello。And then， this。Should stop the iteration， because。

The other child is hidden behind the front child， and then only the front child is supposed to get this。

Event。Okay， like this。 we haven't written this contains calledord yet， but。Whatever的吧。

The same thing with on mouse up。And with the un mouseuse move。然后。We will do this twice once for the。

For the object that contains the old coordinate。And once for the object that contains the new coordinateor。

好。Okay， so I'm subtracting the。Always is this x and this y turns the coordinates into relative coordinates。

Okay， so if the mouse move leaves the one。呃。If the mouse leaves one element。

 then that element gets only the first。One mouse move， and。If。The mouse move enters a child。

 Then that child gets another on mouse move。 and if。You move the mouse。Within one child。

 it gets the same。ButIt gets the call twice。2。そそさ。Okay， so。Let's say。Okay， so like this we。We send。

So， so if we move the mouse within the same widget， it doesn't get the same。Event twice like this。

Okay， I think this makes sense。Yes。没。Okay。Yeah。Okay， what I want to do。

As I want to instantiate a desktop object。And have that take over this fill rectangle。😔，う。Okay。Yeah。

Yeah， but I think。

![](img/bdb1077a8ca4413ce5db853e8f3b755b_18.png)

Let's see if this still compiles。Okay， it's compiled。



![](img/bdb1077a8ca4413ce5db853e8f3b755b_20.png)

So。Yeah， I think。This is already a lot that we did now。

So I think this should be enough for this video。😔。

![](img/bdb1077a8ca4413ce5db853e8f3b755b_22.png)

So I think in the next video， I will write the the desktop and base class for Windows。

And then you have something like the window have a reaction on the mouse down and mouse up and the mouse moves so that you can click a window and move it around。

Okay。Okay， but。Yeah， so this， I think should be enough for today。Yeah。Yeah， so tune in next time。

Don't forget to subscribe and hit like if you liked the video。And yeah， see you next time， bye。

