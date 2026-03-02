# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p137 137_08_04_配对游戏演示.zh_en -BV1QrB6BcEWW_p137-

![](img/31770ddea0304fb5768882ca3b1ca4a7_0.png)

In this Alice project， we are only going to need to write the event handler for the processing of mouse clicks on the cards。

 The rest of the game has already been set up。Let's go ahead and start by running the project。

We see 12 cards appear， and the alienen briefly describes what the player must do。

Let's go ahead and close the run window。And let's take a quick look at the code that has already been written。

So let's take a look first at my first method and we'll see their calls to two procedures。

 set up scene and set card colors， and then of course we have the alien instruction。

So let's start by clicking on this。And clicking on setup scene。

As we look through the code as set scenene loads， we see that there's a lot of positioning of the 12 cards。

 the cards have initially been set in pairs of matching colors and they all get moved into that nice4 by three grid。

if we notice also， the cards are actually billboards in the shapes of square cards。

We see that there are going to be 1000 calls to the swap procedure。Initially。

And you can check if you're interested in this， the cards are in order。 the first two cards are gray。

 the next two cards are blue， etc ce。 Let's go ahead to edit swap to take a look at how swap works。

As we notice， we generate two different random numbers between0 and 11。

Then we swap the colors of the two cards in the array using a temp。

 This is quite similar to what we did for the memory game。

Let's next go ahead and click on the scene tab。If we scroll down to the bottom。

We notice that there are two scene variables or seen properties that have been created。

 The first is an array of the 12 cards named cards。

 and a billboard is we see it's an array of the billboards。

 which is card 1 card 2 all the way up to card 12。 We also see that we have created one more card a billboard。

 which has been initialized to null card。 In addition to the 12 cards， We created a 13th card。

 which we named null card and placed it below the ground。

When we need to indicate that the first card is not set to any of the 12 cards。

 we'll set it to be null card， indicating that none of the 12 cards is set to first card。

 The first card variable will be used exactly as we have described previously。

Since the game has already been set up， all we need to do is to create the event handler for the mouse clicks。

Let's go ahead and click on event initialized event listener。And let's go ahead and。Add a mouse。

 click on object， listener。Let's start by clicking on the Add detail button。

 selecting set of visuals and selecting that the only types of mouse clicks we are interested in are mouse clicks on elements of the card array。

This limits Alice to only processing mouse clicks on the 12 cards。

 I wouldn't know what to do if the user clicks on the alien or on the ground。

The code for this event handler is going to be rather long and involved。

 So instead of writing all of the code here， let's just go ahead and create a scene procedure。

What couldn on scene。And add a scene procedure。And we'll name our scene procedure process。Clicked。

Cart。觉得 ok。And for this scene procedure， let's go ahead and add a single parameter。Which will be？

What。😮，Got。Clicked。And because in Alices， the thing that gets clicked is an S thing。

 we will specify its type to be S thing。We'll click on OK。And we'll click on， okay。

Let's immediately go back to the initialized event listeners tab and add the call to our procedure。

 So our process clicked card will put right under mouse clicked。

And what got clicked will initially pick， I don't know。 This ground is a placeholder。

 and we can then drag the model at mouse location over top of what got clicked。

Now we can go back to process clicked card to write in the code。As we noted earlier。

 there are three things that we're going to need to do。

 so let's start by dragging in a do in order tile。The first thing we need to do is to figure out which billboard or which card got clicked since we don't really want to process S things。

So let's go ahead and start by adding a comment here。And we'll make the comments say。

 determine which。Card got。Quect。Okay and。Make it a little bit easier to read。

 let's create a billboard variable， so we'll drag in a variable。We'll name our variable， click card。

And will specify its type。To be a billboard。And click on， okay。

And now let's initialize the click card to be the null card。

 and then we'll figure out which one got clicked in just a second。Next。

 we drag in a for each in the tile to iterate through the cards。

And so we'll specify a type to be billboards。We can give the name card iterator。

And we'll set it to be the array， this do car。Inside the iterator loop。

 we're going to drag an if statement because we need to figure out which card what got clicked is。

So we'll just specify true， and then we'll change the true to a relational S thing。

 and we'll test equality。 And we want to test if。Card iterator is equal to what got clicked。

And if the particular card iterator is equal to what got clicked， what can we do here。

 We will simply drag in an assignment statement and will set clicked card to be。The card iterator。

This completes the first step。For the second step， let's start with another comment。

Put it right in here and we'll say。Process。Clicked。Cart。

We need an if statement to see if first card is no card in which case we're going to be processing a first card。

So let's go ahead and drag in an if statement right in here。And it will change true。

And they'll change the true to a relational S thing。 and it'll test equality and check if。First card。

Happens to be。No card。 and a first card is no card。 We're going to be processing a first card。

 and we have only two things that we're going to need to do in this case。

 and we're going to go ahead and do them in order。 So we'll drag in a do in order tile。

The first thing we need to do is we need to assign first card to be clicked card。

So let's go ahead and assign。First card to B， clicked card。The second thing。

 we want to flip the card over。This is going to be a two step process。

So we'll click on alien and actually turn the alien over and then change alien to first carp。

So we'll go ahead and have the alien turn left。Half of a revolution。

We'll make the duration be pretty quick。 So let's go ahead and make it a quarter second。

 And then finally， we'll change this alien to first card and flip the card over。

That covers the second step for the third and last step。

 we're going to be processing the second card。We need to first check in this case that the player hasn't clicked on the same card twice。

Let's go ahead and start with an if statement。Mmm。We're processing the second card。

And we need to make sure that the clicked card is not first card。

 so let's go ahead and change this relational S thing。

 and in this case we're going to select not equals to and make sure that first card is not equal to the clicked card that in fact the gameplay is selected a different card。

If this hold， we're going to have to do five things in order。So let's drag in a doing order tile。

First， we need to go ahead and turn the clicked card over。 and again。

 we'll do the exact same thing we did before as a two step process with the alien。 First。

 we'll have the alien turn left。Half of a revolution。We'll make the duration be a quarter second。

 and then we'll change the alien to be the clicked car to flick the second card over。

As a second step， we need to check to see if the paint of the clicked card matches the paint of the first card。

So as a second step， we'll drag an if statement here， we'll select true。

's scroll down just a little bit and change。 we want to test the paint。And we want to be equality。

And here we're going to have to do this as a couple step process。

 So we'll just test whether black is equal to blue。It is kind of a little bit of a silly thing to do。

 but let's do this and we want to test if the paint of the first card and so again we can't directly test first card so we'll click on the aliens paint。

 so we'll click on the aliens function and choose the aliens get paint。

And this should not be the aliens get paint， but is the first cards paint equal to the clicked cards paint。

 So， again， we'll choose the aliens。Get paint and change the alien into clicked card。Now。

 if there is a match， we wish to at the same time make the two cards invisible。

So let's go ahead and drag in a do together in case the paints match。

 and we'll again do this as a two step first with the alien。 So we'll click on the alien。

And scroll down and drag its opacity。And we'll set the alien's opacity to zero。

And change the aliens opacity to first card。And then again。

 we'll do the same thing again as a two step to set opacity， drag in the setting the opacity to0。And。

Change the second one to click card， the first card and the click card match。

 So we're going to set them to 0。 And let's go ahead and make the duration be a quarter second just so it happens rather quickly。

And in case there's a match， we'll make the two cards invisible。For the third step。

 we need to flip the cards back over， regardless of whether or not there was a match。😡。

So in order to flip the cards over， let's go ahead and drag in a do together。

 And we're going to put this as a little bit hard in here to put it here。 We'll scroll down。

 So first step is to flip the card over。 Second step is to test if the there's a match。

 And the third step is going to be to flip the cards back。 And so again， we can have the alien。Turn。

left。Half the revolution。And we'll change the alien to first part。And we'll have the alien。

Turn left half revolution。 and again， we'll change the alien to the clicked card。

 And let's go ahead and make this happen super quickly。

 So let's make the duration just be maybe a 10th of a second。 So make it 0。1 seconds。

And we'll make the duration of the second instruction also be really quick to be 0。1 seconds。



![](img/31770ddea0304fb5768882ca3b1ca4a7_2.png)

For the fourth step， we need to reset first card to be null card。

 So let's just drag in an assignment statement all the way down here at the bottom。The fourth step。

And we'll set first card to be no card。Finally， as a fifth step。

 we need to check to see if the player has won。So let's drag again one last if statement。

Which we'll put right here as a fifth step and will' select true as a placeholder。Right here。

Now we have previously written a scene function， all cards have been matched。

Let's go ahead and click on this。Click on this。And functions and all cards have been matched。

 I'll put this over top of the true。Now， if you're interested。

 we can take a real quick look at this function that we've previously written。

 so we'll click on the edit。As we can see， this function checks each of the cards in the cards array as soon as it finds one that is still visible。

 it immediately returns false as the game is not over。

If none of the cards are visible and we iterate through all of the cards in the array。

 None are visible， then all have them matched。 So the function returns true。

 Let's get back to our process， clicked card procedure。So we'll scroll down to the bottom。

 If all of the cards have been matched， let's have the alien。So we'll click on this alien。

And we can click on the aliens procedures and we can have the alien say， oh， I don't know。

 we can have the alien say nice。Job， a couple exclamation points。

And perhaps we can make the duration。Be a couple of seconds。Great， let's go ahead and play the game。



![](img/31770ddea0304fb5768882ca3b1ca4a7_4.png)

OkayClick on the card to find matches。That's blue。And red， those didn't match。Oh there's red and red。

 we've got a match。Green。In purple。And yellow。AndGi。And gray， and there is the gray。And purple。

Was that the purple， there's the purple？And blue。And blue。And yellow。And yellow。And green。And green。

We found all the matches and the alien says，Nice job。Fan。



![](img/31770ddea0304fb5768882ca3b1ca4a7_6.png)