# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p105 105_06_05_计时器.zh_en -BV1QrB6BcEWW_p105-

![](img/f8d157d22bf84263a2a4c61ab6322387_0.png)

We're going to want to modify our click a penguin game to challenge the player of the game to click on 10 penguins within 30 seconds。

 The challenge of accomplishing this task will require us to use timers in addition to scores。

In a sense， timers are sort of the opposite of scores， with timers， the value。

 the amount of time left generally decreases， whereas with scoresrs。

 the value the player score generally increases。In Alice。

 we implement timers in exactly the same way as we did scores。

 We add a 3D text model when we add a text model to our Alice project。

 we have to give it a name timer， we also specify its color。

 which we have set to blue and provide an initial value which weve set to 30。

We also need to add a property to our text model。 The reason for this is the same reason as it was for scores。

 namely that what Alice displays on the screen is really a string。

 you cannot subtract one from a string。 You can only subtract one from another number。

 and you can't display a number。 You can only display a string。

 We need to keep track of the amount of time left， so we'll be able to store the time left as a whole number property。

As the amount of time left should generally decrease by one second at a time。

 we tend to prefer whole numbers instead of decimal numbers。In this example。

 we've named our property， time left， and given it an initial value of 30。

We also write a procedure to update the timer， very similar to the process of updating a score。

 the process of updating a timer requires double bookkeeping What I mean to say is there are two things you'll need to do to decrease the amount of time left。

First， you will need to update the value of the property In this example。

 we are decreasing the number time left by one。And the second thing you'll need to do is to tell Alice to update the display to be the new value of the time left property。

In essence， we can catnate an empty string， which turns the number into a string of the number so it can be displayed as a string。

By calling this decreased procedure， we'll be able to have Alice decrease the remaining time by one and show the player the updated time。

The one difference between timers and scores is how they're called。With scoresrs。

 we typically call the increased procedure from an event when the game player has done something good。

 like clicking on the penguin with timers， we typically want to decrease the time left by one every one second。

Alice is a special event called a Time listener that we can choose to get called every one second。

And every second， we wished to call the decreased procedure。After adding the time listener。

 Alice then as a procedure， time elapsed， which gets called every one second。

Coding this time elapsed procedure is quite straightforward。

 As long as the amount of time left is greater than 0。

 we simply call our decreased procedure to decrease the amount of time left by one second。

 Let's see how timers can be used in a game。😊。

![](img/f8d157d22bf84263a2a4c61ab6322387_2.png)