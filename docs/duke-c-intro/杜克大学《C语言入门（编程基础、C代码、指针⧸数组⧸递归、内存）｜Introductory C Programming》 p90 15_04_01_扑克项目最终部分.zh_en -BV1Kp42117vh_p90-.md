# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p90 15_04_01_扑克项目最终部分.zh_en -BV1Kp42117vh_p90-

As we wrap up this course in specialization， it's time for you to finish your poker project。

 You've written a lot of code in courses 2 and 3， and now it's time to handle reading input and unknown cards and bring it together by writing the main function。

 which will do the Monte Carlo simulation。One of these parts may seem a bit tricky。

 How do you handle unknown cards。 It turns out that we can do this with concepts you have learned。

 pointers， arrays and reality。 Here is a small input with two hands。 The first has。

 the king of cards and two unknown cards。 The second has the ace of spades and two unknown cards。

 Both hands share question mark 0。 So we have to make sure our implementation can ensure that both hands end up with the same value。

 Of course， real hands need at least five cards， but we are just going to draw a smaller example here to show you how this works。

Will'll make a structure to track unknown cards Since we already have decks as a representation for sets of pointers to cards。

 We'll reuse that type here。 Our unknown card structure will have an array of decks。

 Each deck will correspond to one particular variable。

 So question mark 0 will correspond to one deck。 Que mark  one to another and so on。

Unlike normal decks， each of these decks will point at placeholders in the hands to show where to fill in later。

 Let's see this in action。 Our first card is the king of hearts。

 We will allocate space for hand one And for this card。 Our second card is question mark 0。

 We don't know its values yet。 so we could send them to invalid values。 That way。

 if we ever mess up and don't change them。 It will be easier to catch the mistake。

Since this card is unknown， we are going to update our unknown card structure。

 we'll allocate a deck to correspond to question mark0 and make a one element array whose value is a pointer to the card we just created。

The next card is also unknown， so we will proceed similarly。

 we will make a deck for question mark1 and make its one element point at this placeholder card。Now。

 we start on hand2。 The first card is the ace of spades。 The second is question mark 0。

 so it is unknown。 So we will want to add an element to the deck for question mark 0。

 which points at this newly created placeholder card。The last card is also unknown。

 so we make a placeholder。Since it is question mark2。

 we will need to make a new deck and point its one element at this placeholder cardt。

Now we need to be able to use this structure to assign random values to our placeholder cards。 First。

 we need to know how many random cards to draw。In this case， we need three。

 but how do we know that in general？So let us suppose we shuffle our deck and look at the top three cards and find they are the four of clubs。

 the queen of hearts and the seven of clubs。 How do we set the cards in the hands to these values。

 While everything that needs to be set to the four of clubs can be found from the pointers in the deck for question mark 0。

 so we can iterate through that array and use these pointers。

That we find there to refer to the cards whose values we want to set to the four of clubs。

 Once we set these to the four of clubs， we want to repeat the process for the other unknown cards。

 For question mark 1， we would use the pointers in its deck to find the cards to change the queen of hearts。

 And then the same thing for question mark 2 and the7 of clubs。

 If we wanted to repeat the process for another set of random cards we could。

 We just shuffle the deck and iterate through the unknown card structure again。 With that。

 I think you are ready to dive in and finish a project。



![](img/f00920417259f5ac118d8190be84df5c_1.png)

![](img/f00920417259f5ac118d8190be84df5c_2.png)