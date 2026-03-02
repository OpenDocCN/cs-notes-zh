# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p103 103_06_03_计分器.zh_en -BV1QrB6BcEWW_p103-

![](img/7a7116be6b596eb3ca0b28667ccba559_0.png)

![](img/7a7116be6b596eb3ca0b28667ccba559_1.png)

When designing games in Alice， it is often desirable to be able to create representations of the player's score。

 or perhaps how much time there's left in the game。

 We'll explore how scores work here and how timers work a little bit later。😊。

We're going to want to modify or click a penguin game to challenge the player of the game to click on 10 penguins。

But before we modify the gain， we need to learn how scoresrs work。In Alice。

 we implement scores by means of adding a 3D text model。

 A text model is an object in Alice that displays some text。

When we add a text model to our Alice project， we have to give it a name。

 much as we would for any object that we add to Alice。

 We also specify its color and provide an initial value。In the case of this score。

 we set its color to be blue， and we set the initial value to be the string0。

We also need to add a property to our text model。 The reason for this is that what Alice displays on the screen is really a string。

 you cannot add one to a string。 You can only add one to another number and you can't display a number。

 you can only display a string。 We need to keep track of the player's numeric score so we will store that score as a whole number property as scores generally don't include fractions。

 We tend to prefer whole numbers instead of decimal numbers。In this example。

 we've renamed our property score value and given it an initial value of zero。

We also write a procedure to update the score in Alice。

 a bit of what's called double bookkeeping is involved。

 What I mean to say is there are two things you will need to do to update a player's score。 First。

 you'll need to update the value of the property In this example。

 we're increasing the number score value by one。For example， suppose the player score 0。

 If we call increase the player score score value gets updated or set to one。

 And the second thing you need to do is to tell Alice to update the display to be the new value of the score value property。

In essence， we can catnate an empty string， which turns the number into a string of the number。

 so it can be displayed as a string。By calling this increased procedure。

 we'll be able to have Alice update the score by one and show the player the updated score。

How does a score updating actually happen， Let's take a closer look at this example and see how Alice increases a score。

 Initially， the score value is 0， and the text value is the string0。When we call increase。

 the first line of code to get run is the instruction to set the score value to be one plus the current value of score value。

As we can see， Alice first looks up the value of score value and sees that it's 0。

 Alice then places the0 in place of this dot score value and next evaluates the expression 1 plus 0 to be1。

 The value 1 is then written back into the memory associated with the variable score value。

Next is the instruction to set the text to be the empty string concatenated with the value of score value。

 Alice looks up the value of score value and sees that it's one。

 Alice appends the one to the end of the empty string， producing the string 1。Finally。

 Alice writes back the one into the memory location associated with the variable text。

 simultaneously updating the 3D text to show a one。

Let's get started seeing how scores work in practice。



![](img/7a7116be6b596eb3ca0b28667ccba559_3.png)