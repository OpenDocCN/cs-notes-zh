# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p136 136_08_03_配对游戏.zh_en -BV1QrB6BcEWW_p136-

![](img/cc191b192eb31f542bbf5de02949d1d2_0.png)

We're going to introduce our third and final game， specifically we are going to play a game where the game player tries to match the cards of light color by clicking on them。

As shown， the player starts with 12 cards that have been turned over， hiding their colors。

Because Alice does not have regular playing cards， we're just using billboards。

 the player clicks on the cards to try and find a match In this example。

 the player clicked on the card in the upper right。

 which is blue the user then clicked on the card in the lower left。

 which is gray they on'll match so they're flipped back over。Now。

 suppose the user clicks on the upper left card and then the card in the upper right。

It turns out both of these cards are blue， so they match and are removed from the game。

The game continues until the player has found all six matches at this point， the player has won。

Part of this game is quite similar to the memory game。

Namely for the memory game we needed to shuffle bunnies here we're shuffling cards。

 or rather the paint color of cards， but there's a significant difference。

The difference depends on the player's click。 When the player is first clicked on a card。

 we simply flip the card over。 But once a card has been flipped over and the player clicks on another card。

 Alice needs to remember what the first card that was flipped over was。

 Then we can compare the color of the two cards to see if they match。

The easiest way to remember a card is with a variable。

 We can start by initializing the variable to a card that is not one of the 12 cards。

 We've added a 13th card， which we have named null card。

 we initially placed null card to the left of the cards that the player will click when searching for pairs of identically colored cards。

 This card is used to keep track of whether the game player is clicking on the first card searching for a pair。

 or the second card。 If first card contains the value null card。

 we know that the player hasn't yet clicked on a card。 When the game player first clicks on a card。

 we assign first card to be the card that was clicked。😊，When the game player clicks on a second card。

 we first check first card， if first card is not null card。

 we know that the player previously clicked on a card and we can compare the two cards。

 first card and the card that was clicked to see if there is a match。

Because we don't actually want the game player clicking on the null card。

 we'll place null card below the ground so the game player cannot see null card and cannot click on null card Let's go through the steps involved in processing a mouse click on a card in a bit more detail We need to do three things First we need to convert the S thing that was clicked on to a card。

😡，Second， we'll need to handle the case where there isn't already an upturn card。

 We'll call this case processing the first card。 And third。

 we need to handle the case where there's an upturn card already。

 We'll call this case processing the second card。Let's first handle the case of converting the S thing that got clicked on to a card。

When we handle mouse clicked events， Alice returns get model at mouse location， which is an S thing。

 As Alice does not know whether the user clicked on an object or just the ground。

 If we store the get model at mouse location into an S thing variable， What got clicked。

 we need to iterate through the list of cards to determine which card matches。 Once we find a match。

 we can store the match card into a local variable， clicked card。😊。

The second step is handling the case where we need to process a first card。 This is the easier case。

 We know that we have a first card if the scene variable first card is set to nu card。

We need to do two things。 First， we store click card into first card， and second。

 we flip the card over。The third step when processing a second card requires five substeps before we get started on the sub steps。

 we need to make sure that the player clicked on a different card if the player clicks on the same card twice。

 we can simply ignore the second click。The first sub step is to flip over the second card so the player can see what they clicked。

 Second， we check to see if the two cards match color， changing their opacity to 0， if they match。

Third， we flip both cards back over again， while it is only technically necessary to flip them back over again。

 if the cards don't match， we flip them back over again all of the time so that if we wanted to play the game a second time。

 all of the cards would be oriented in the same direction。Fourth。

 we reset the first card variable back to being null card。

 the reason we need to reset first card back to being null card is so that when the next time the player clicks on a card。

 we want to have Alice processing the card as a first card。And fifth。

 we check to see if all of the cards have been matched， congratulating the player if they have won。

The completed code can be seen here。I think it will make the most sense if we go ahead and build this program now to see just exactly how it works。



![](img/cc191b192eb31f542bbf5de02949d1d2_2.png)