# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p133 133_08_03_逻辑游戏.zh_en -BV1QrB6BcEWW_p133-

![](img/c6fc64c269dab07fd9e9ecfa2843d218_0.png)

![](img/c6fc64c269dab07fd9e9ecfa2843d218_1.png)

This next game that we're going to build is a logic game。

 The idea for this game is that we need to guess a secret code。

Each of the bells can be in either an up or a down position。 Initially。

 all three bells are in the down position。As the player plays the game， they will click on the bells。

 If the bell that is in the down position gets clicked， it should move to the opposition。

 If the bell was in the opposition， it should move to the down position。In this example。

 we can imagine that the player clicked on the middle bell and in turn。

 the bell has moved into the up position。The goal of playing this game is to guess the secret code。

The secret code might be up， up， down， or it could be down， up， up。 for example。

 we will store the secret code as an array of text strings。 Here。

 the secret code has been initialized to down， down， down。

The game player will repeatedly click on bells until they have correctly guessed the secret code。

There are three parts to this game。 One， we need to be able to set a random code。Two。

 we need to allow the game player to click on the bells to change their positions to up or down。

And three， we need to be able to check to see if a given position of the bells matches the secret code。

Let's explore each of the three。First， we need to set the three random values。

 We'll iterate through each of the three values of the array。It would be nice to use an iterator。

 but Alice does not allow the iterator to be assigned to。 so instead we use a counted loop。

For each index of the array， we use the built in buan function next random buyan。50% of the time。

 this function will return true， and 50% of the time， it will return false。 That's just what we need。

 If the function returns true， we'll set that element of the array to be the string up。

And if the function returns false， we instead set thatelma of the array to the string down。

That's really all we need to do。The second part， processing the player。

 clicking on the bells is actually rather easy due to an animation trick。As seen in the picture。

 we have placed a bar into the middle of the scene。We make it invisible when the game gets play。

In order to determine whether the bell is in the up or the down position。

 we can simply use an if statement to check if the bell that got clicked on is above the bar。

 if it is， we can move the bell down。If it's not above the bar， we instead move the click bell up。

The third part is a bit trickier。 We cannot easily compare the positions of the bells to an array of text strings。

Our solution has two subparts。 The first is to convert an array of text strings into a single text string。

We start with an empty string and in order， append each of the up or down values onto the end of that text string。

For the second sub part， we do nearly the same thing。

We iterate through each of the bells for each bell。 If it's above the bar。

 we add the string up onto the end of the string。If it was below the bar。

 we add the string down to the end of the string。After we've done this。

 we just need to check if the two strings are the same。 If they are。

 the position of the bells matches the secret code， and we return true。Otherwise。

 we return falses as they do not match。Let's go ahead and build this game。



![](img/c6fc64c269dab07fd9e9ecfa2843d218_3.png)