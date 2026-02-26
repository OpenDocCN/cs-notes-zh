# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p28 -28-COMP6080 - Javascript WebJS 🦄 Events.zh_en -BV17RXGYuEaM_p28-

Hey everyone， it's Anna here and in this lecture we're going to talk about events。

 so let's just dive in。😊。

![](img/4fc3d622b533537c72273b777841e057_1.png)

First let's take a look at what an event is， so an event is basically a signal that a thing has happened to an element in our do。

😊，If we watch for these signals， then we can run JavaScript code in response to these signals and a signal can be something like a user action。

So basically events are a way that we can incorporate user interaction into our apps。



![](img/4fc3d622b533537c72273b777841e057_3.png)

So when I say a thing has happened to a dom element。

 this could be that the user has interacted with the element in one way or another。😊。

Events come in many forms and some of the most common ones are mouse events and keyboard events so some examples of mouse events are click double click and then there's mouse down and mouse up so mouse down is the start of a click when the mouse is initially pressed and mouse up represents the end of a click so when the mouse is released。

😊，We also have mouse enter and mouse leave， so if I hover on an element。

 mouse enter is fired when my cursor enters the element and mouse sleeve is fired when my cursor leaves that element。

😊，Taking a look at keyboard events we have key down key press and key up so these are useful。

 for example， if you're keeping track of arrow key presses or if you're looking for enter space shift or control keys。

In case you're wondering what the difference between key up key down and key press is so key down is when you first press the key key up is when you release the key and key press represents like a character being tacked so on one key down many key press events may file。

Yeah and there's plenty of other examples of events。

 some of which are only available for specific types of elements I listed a bunch of examples here。😊。

For example， focus happens for an input text box when that text box is focused can play as an event for video elements。

 which is fired when the video is able to be played by the user agent。

And I've included a lot of events on this slides， but there are Hs heaps more and I recommend you take a look at what's available on MDDN。

😊。

![](img/4fc3d622b533537c72273b777841e057_5.png)

Cool， so we know that events are something which raise a signal。

 but how do we actually listen to that signal？So an event listener is a handler function that runs in case of an event。

So basically， handlers are a way to run a JavaScript callback to respond to user interaction。

Now how can we actually add an event handleula？

![](img/4fc3d622b533537c72273b777841e057_7.png)

So there's three main ways of adding an event handler。😊。

The first way is here on this slide and that is to do so using HTML so here I've got a little HTML snippet for an input button and I've added an on click handler which is an attribute。

And I've put the JavaScriptscript that I want to run in quotations， so with this example。

 when this button is clicked。This JavaScript line here will run so and a lot will pop up saying the button is clicked。

The second way to do it is to set the property on the Dom element so when I have an element in JavaScript through get element by ID or another method。

 I can assign a function to element do on click so on click is a property on the Dom object and this syntax here is just an arrow function which I'm assigning to on click which is basically like a simple landout or anonymous function and again this will alert that the button was clicked when we click it。



![](img/4fc3d622b533537c72273b777841e057_9.png)

So a quick quiz I have this function written here called do something and then I'm writing element。

 onclick equals do something what's wrong with this code so feel free to pause here for a second if you want to take a second to think about it。

So the problem with this code is that I've added parentheses after do something。

 which means that I'm executing the function， I'm calling it。

 rather than assigning on click to the do something function。

So the correct answer would be like this just to remove the parentheesis so the onclick。

Call back the onclick。Object on the dom element is a function。



![](img/4fc3d622b533537c72273b777841e057_11.png)

Cool the final way of adding an event listener is via the function called add event listener so this is a function which takes two arguments the first one is the type of event so this could be click or mouse move。

And the second parameter is the listener， which again is a callback function。

 just like the last two examples。So once an event listener is added。

 you can also remove it using Reve event listener so you can see add event listener and Re event listener being used on the last two lines on this slide here。

And add event listener also takes a third optional options parameter。

 so options is just an objects which specify some extra settings for that event listener so some examples of things it takes is。

An option called once， so if you specify once equals true。

 this fully parameter means that listener can only be invoked once。Yes。

 so that means it'll automatically remove the listener once it's been ined。Another option is capture。

 which is another bulloleyanant parameter which indicates that the event should be captured so we'll look into a bit later into what this means。

And the last example is passive， which is also abuolean which went through it means the function we'll never call prevent default and we'll have a look at what prevent default means later in this topic as well。

So you can see all the details about a event listener and all the options except on MDM。😊。



![](img/4fc3d622b533537c72273b777841e057_13.png)

All right， so we've seen how we can set a function or a callback to be an event listener。😊。

Now event listeners actually have an optional parameter so this。This。Handsler。

 this parameter for the handler is an object of type event and this object represents all the details relating to the event that has taken place。

So here we have a small example of an event listen now which is using the event parameter。

 this code adds a mouse move event listener to the document via a event listener which will fire when the mouse is moved anywhere on the document。

And then in the callback， I'm consoles logging event。 clientientX and event。

 clientientY so clientient X and clientY represent the coordinates of that mouse event let me quickly pop into the browser and demo this。



![](img/4fc3d622b533537c72273b777841e057_15.png)

Al right， let's test that mouse move example in the browser。So I'm going to do document。

adeven listener。The event I'm listening for is mousemove。And now in this callback。

 I'm going to console log Client X in clientient Y of the event。All right。

 I've added the event listener now if I try to move my mouse on the document。

You can see here that it's console logging the coordinates of my mouse so if I go all the way to the top left。

 I get00。And。The y increases when I go down and the x increases when I go to the ramp。



![](img/4fc3d622b533537c72273b777841e057_17.png)

So what information does this event interface actually contain？

So as we saw earlier there's many many different types of events and there are some properties which are common to all of these events。

 for example we have current target which is the current element that the handbl is running on。😊。

There's timestamp， which is the time the event was created in milliseconds and then there's event dot type。

 which is the name of the event I click。There are also other properties which are specific to types of elements。

 for example， client X and client Y which we just saw in the last example on mouse events and for example key is something which is on keyboard events only。

 which has the key code of the key that was pressed。Now with our knowledge of events。

 let's code a small events example with using keyboard events。



![](img/4fc3d622b533537c72273b777841e057_19.png)

Allright， let's do an example with keyboard events。

 so the first thing I'm going to do is I'm going to add an event listener to the document for the key down event。

😊，And I'm going to define a handle a function。Yeah。

ICon logging event key just to show you guys what key codes are console logged when I op different keys so running this in the browser on the left if I press the a key I get a console log if I press B DP then if I press numbers it also prints the number if I press a key like an arrow key I get。



![](img/4fc3d622b533537c72273b777841e057_21.png)

Arrow up， arrow left， arrow， right， arrow down or shift。

So basically the key gives us the name of the key which was pressed。Cool， now I've got a HTML。

 a simple HTML page here with a div that I've coloured blue and set to 50 by 50 pixels。😊。

Now what we're going to do is we're going to write a script， which when I press the arrow keys。

 it will move the box around the page in the direction of the arrow key， which I pressed。



![](img/4fc3d622b533537c72273b777841e057_23.png)

So now what I'm going to do is I'm going to retrieve the square from the HTML and I've given an ID square。

 so I'll use gett element by ID。Next thing I'm going to do is I'm going to write a function which accepts a left delta and a top delta and moves the square by that amount。

😊，So I'll call my function move squd。So to move the square's left position I'm going to use the square。

 style。 left property， so first I'm going to retrieve its current position。

 then I'm going to add the provided left delta。So I'm going to set square dot style left to current left plus the provided left delta。

 and then I'm just going to add Px at the end。And now I'm going to do the same thing at the top。

Now just to test this， when I hit any key， what I want to do is move the square just by 50 pixels。

So if I press that second time it moves at 50 more pixels so our move square function is working now what I want to do is I want to check which arrow key was pressed with different left and top values based on the key that was pressed。

😊，So I'm going to do a switch statement on event dockkey。

So in the case that the down arrow was pressed， I want to move。

 I want to increase the top value by one and I want to leave the left value the same。

If I'm moving up， I want to decrease the top value by one。If I'm moving left。

 I want to increase the left value by one and leave the top the same。And if I'm moving right。

 I want to increase the left value by one and leave the top the same。So let's try and run this code。

So I'm pressing my right arrow key now and this's moving right。

 I'm pressing my up arrow key and it's moving up so it looks like this is working let me just quickly increase the amount I'm incrementing by。

😊，So nowm moving five pixels at a time it's moving much faster， so that's our keyboard example done。



![](img/4fc3d622b533537c72273b777841e057_25.png)

So now we're going to talk about the event loop。So JavaScript's concurrency model is based on something called the event loop。

And the event loop is essentially a message queue which lists messages or events that need to be processed。

So when an event gets triggered， it's added to the queue and the page won't run the next event until the current event has reached completion。

So we call this the event loop because it resembles something like this loop here。Basically。

 JavaScript is continuously synchronously waiting for messages while handling any messages which are currently waiting to be handled。

Javascripts event loop uses something we call to a run-to completion model so this means that every message is processed completely before any other message is processed so the benefit of this is that it's a really simple and easy to understand model that we can often take advantage of when we're writing our ja code but the downside of this is that since it's synchronous and we have to wait for messages to be completely processed before any other messages are processed if a single message takes too long to complete this eats up the main browser thread and the browser won't be able to process anything else which means that if the browser thread is really busy we can't even click on elements or scroll on the page because those events aren't being processed。



![](img/4fc3d622b533537c72273b777841e057_27.png)

Cool， so that was the event loop。Now let's take a look at event capturing and bubbling。

 so this is a way of understanding how events are propagated through the do。

So when a standard Dom event happens， the event goes through three phases of propagation。

 so this diagram shows the events flow after clicking on a TD tag inside a table。

 so we've got a table tag， body tag or Tbody tag TR tag and then TD tag。

So the first step is the event capturing phase， so the event starts at the highest level。

 which is the window and goes down through the document HTMLL body all the way through the different tags until it reaches the target element which is the TB tag in this case。

 so that's the capturing phase。The second phase is the target phase。

 which is when the element has actually reached the target element， the TV element。😊。

And then finally， after reaching the target element， this is when it goes through the bubbling phase。

 which is when the event bubbles up from the element all the way back to the window。😊。

So the concept of bubbling is that when an event happens on an element。

 it first runs the handlers on that element and then on its parent and then all the way up its ancestors back to the window。

😊。

![](img/4fc3d622b533537c72273b777841e057_29.png)

Let's do a quick example which demonstrates event capturing and bubbling。



![](img/4fc3d622b533537c72273b777841e057_31.png)

All right， so here I have a sample HTML page where I have three nested divbs。

 so I've got my div first， second and third， and Ive applied some styling so that they appear like inside each other and under each other。

So I've also quickly added some JavaScript so in here I am calling get elementement by ID to get all three squares and then I've added an oncl listener to each of them so let me quickly demonstrate what happens when I run this so if I click first。

I get an alert saying first because I've clicked on the first element。Then if I click second。

 what will happen is the event handler will be called on the second on the target element first which is our second div。

 but then it will bubble to the parent， which is first， so let's try that。😊。

Also it's alerted second and now it's also alerting first。And I'll try the same thing with third。

 so I'll go third then second and first since it's going from the target element to the parent to the parent and all the way up the dom。

So it's doing that。Then second， and F。Now we have a function called stop propagation so what stop propagation does is it stops the event from bubbling up to its parents。

 so let me show an example of doing this so if I add the event object to this listener and do event do stop propagation。

Then when actually click third， it's not going to bubble on two second and first。

So it's alerting third。But then it doesn't go on to its parents so that's all about event bubbling and stop propagation now let's take a look at prevent default so what is prevent default。



![](img/4fc3d622b533537c72273b777841e057_33.png)

Basically some types of DOm elements have default behavior for example。

 when you click on an input checkbox this toggles the checkbox that's browser default images also have default drag and drop behavior to allow you to drag them into another location and key presses in a text input field have default behavior that when you type it enters text into the input field。

So in our event listeners， we can use this function called preventvent default to stop the default behavior happening in the case that we want to stop it right let's do a quick example demonstrating prevent default。



![](img/4fc3d622b533537c72273b777841e057_35.png)

Al right， so I've got this HTML page and what I've put here is an input checkbox field。

 which is just a checkbox and an input text field which lets me type into it。嗯。So like I said before。

 checkboxes have the default behavior that when you ticket it， it gets checkeded。

 text boxes have the default behavior that when you type into them。

 whatever you get type in appears in the text box。So first I'm going to demonstrate prevent default for the checkbox。

 so I'm going to get this checkbox using gett element by ID。

And now I'm going to add the click event listener to the checkbox。Now in here。

 I'm going to do event dot Pre default。If I now run this code。When I try to click the checkbox。

 it's not actually getting checked because I've stopped the default behavior， so if I un this。

Say it's working again。Now let's do a slightly different example for the text box so first let me grab the text box by its ID as well。

😊，And an eventless enough for key press。So if I do prevent default。

 it won't let me type in there at all， so let's just quickly show that。

So I'm typing and it's not doing anything。Now what I want to do is I want to allow typing。

 but I don't want to allow typing of any letters but lowercase characters。

 so if someone tries to type a number or a symbol I don't want to allow that so I'm going to use the Charcode attribute of the event to check if what was pressed was a lowercase letter。

So I'll be in this if statement if the character is less than a lowercase A。

 which means or greater than lowercase Z， which means if it's outside of the lowercase alphabet and in here I'm going to do prevent default and I'll put an alert。

😊，So let's try and run this again， so if I type lowercase letters。

So I fine if I try an upper case letter， I'm getting the alert saying。

 please use lower case letters only。😊，唔家。Cote Ser that's how to use Prevent default。



![](img/4fc3d622b533537c72273b777841e057_37.png)

Okay， finally， we're going to do an example which combines all of our knowledge of events。

 which is a drag and drop。

![](img/4fc3d622b533537c72273b777841e057_39.png)

Basketball game。All right， so let's get started with our basketball drag and drop example。

 so I've got this HTML page which has two images， a basketball and a hoop。😊。

And I've also got this label here which says the score so right now there's no score and I've positioned the hoop absolutely far away from the page so first thing I'm going to do is I'm going to try to make the ball itself drag aable so I'm going to grab this element from the do and to make a drag aable I'm going to use a combination of three events I'm going to use mouse down for when the ball is pressed I mean like to mean picking it up I'm going to use mouse up to mean I've released it I'm letting go of my drag and I'm going to use mouse move event。

We saw earlierR in this video that we can use event client X and client Y to get the position of the mouse。

 so I'm going to use the mouse move event to position the ball where my mouse is。So first。

 let's get the elements from the dom。Now what I'm going to do is I'm going to add a mouse down and mouse up event listener to the bull。

So just now if I try to mouse down on the ball， I get a mouse down console logged， if I mouse up。

 so I release my mouse， then I get mouse up console logged。

Now what I want to do is I want to add a mouse moveve event listener。

 but I only want to listen to mouse moveve if my mouse is currently down so to do this I'm going to add my mouse moveve event listener inside mouse down and remove my mouse move event listener inside mouse up。

I'm just removing the event listener using Remove event listener like we saw before。

Running this again， if I'm moving my mouse on the document。

 nothing is being console locked when I mouse down on the bull。Ands stop。Moving my mouse。

 I get a mouse move event being console logged。Now you'll notice that。

When I pick up this ball I'm getting this kind of weird draggy behavior of the ball。

 but this isn't custom drag and drop， this is actually the default behavior of the browser when you have an image so what we want to do is we want to prevent the default behavior of dragging this image so I'm just going to do event up prevent default。

So let's try that again。Cool so that's no longer happening and you can see mouse movies being console looked cool now what we want to do is we want to change the position of the ball to be the same as the coordinates of the mouse so to do this I'm going to change ball dot styles up left and I'm going to make this equal to the coordinates of the mouse。

And I've done the same with top set it to client way。Let's try this。Cool。

 so now you can see when I mouse down on the ball and move my mouse。

 it's following my cursor and you can see that when Im massed down and I start moving the bull jumps a little bit。

That's because I'm setting the top and left position of the ball to equal my cursor while what I want to do is I want my cursor to stay on the same position within the balls element。

To avoid that jumping when I first pick it up。So to do this。

 I'm going to calculate the offset of my cursor within the ball element。

 so to get the offset of the cursor within the ball。

 I want to get the position of my cursor and from that subtract the top left point of the ball's bounding client rectangle。

And now I'm going to use this offset and set the left and top of my ball to equal the mouse position。

 but subtract this offset。So now let's run this again。

And now you can see it's no longer jumping All right next thing I want to do is I want to make us actually able to score goals in this little game so I want to make such that if I drag this over our little hoop graphic that it will trigger a function which will increment our score so first thing I want to get is I want to get the coordinates of this little red actual hoop bit from within the image this is okay to hard code I grab these values earlier so I'm just going copy them from here so these offsets are equal to the offset of the red hoop from the top left corner of the entire hoop image so let's add some logic to our on mousem to calculate if our current mouse position is going through this hoop so let's just keep track of the score in a local the global variable。

First I want to get the actual position of the hoop。

 so I'm going to also do this using get founding clientient rectangle。I've given the hoop ID hoop。

Al right， so in this if statement I'm checking that event dot client X is within the bounds of this red square which I calculate using the hoop rectangles bounding client box so the top and left position of the hoop rectangle plus these offsets which I've high coded so I'm just in here I'm going to console log。

That goal was scored。There you go， CDC in my console。Goll school is being console logged。

Now what we want to do is we want to update the scoreboard to show our new score。

 so I'm going to get the scoreboard element。😊，Using its ID。

Here I'm going to change school board text content。Okay。Cool。

 so you can see our score is incrementing， but you probably notice a mistake now that it's incrementing too many times so since it's triggering on mouse move as I move over the red portion of the hoop。

 it's incrementing multiple times。😊，So to fix this。

 let's just have a boolean which stores if the score is already incremented in my current movement over the square。

So I only want to increment the score if has scored is false。Just try again。Great。

 so now I can it's only increment one time per movement through the hoop。Cool。

 so that's it for our basketball example。😊，And that's also it for this lecture on events。

 so thanks so much for fall the asleep， I hope you learned something。😊。



![](img/4fc3d622b533537c72273b777841e057_41.png)