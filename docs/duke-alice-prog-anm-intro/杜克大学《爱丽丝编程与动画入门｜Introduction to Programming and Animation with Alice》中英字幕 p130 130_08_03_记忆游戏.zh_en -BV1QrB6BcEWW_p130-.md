# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p130 130_08_03_记忆游戏.zh_en -BV1QrB6BcEWW_p130-

![](img/0aa82b10814e24fbaa261a820bdd9adf_0.png)

![](img/0aa82b10814e24fbaa261a820bdd9adf_1.png)

Now that we know how to change scenes in Alice， it's time to design three games or tasks the player must successfully complete。

The first game is going to be a memory game。 We'll start with an array of bunnies。

 We show each bunny's position in the array in the number below each bunny。😊。

Bunny is in position 0 of the bunny's array。 Bunny 2 is in position。 One of the bunny's array。

 Bunny 3 is in position 2 of the bunny's array， et cetera。

 for this game will randomly rearrange the bunnies in the array。 Note， the bunnies have not moved。

 We randomly rearrange them in the array。 And you can see their position in the array。

 Bunnies has changed。The first bunny Bunny is now in position 3 of the array。 The second bunny。

 Bunny 2 is in position one of the array。 The third Bunny， Bunny 3 is now in position 0 of the array。

 In fact， if we could look inside the array， we could see how the ordering has changed。

 On the left is how we created the array。 We put Bunny first， then Bunny 2， et cetera。

 shown on the right is the new ordering of the array。

 After our program randomly rearranges the bunny positions in the array。😊。

You can see the first bununny item in the array is Bunny 3， and then Bunny 2， etc。Now。

 let's get back to our game。After we have rearranged the bunny positions in the array。

We'll iterate through the array， turning each bunny purple。In our example。

 Bunny 3 is landed in position 0 of the bununny's array， so it is turned purple first。

 Bunny 2 is landed in position one of the bunny's array， So it's turned purple  second。

 Bunny 5 is landed inny position 2 of the array， So it's turned purple next。

 Bunny has landed in position 3， So it's turned purple next。 Bunny 7 is landed in position 4。

 Bunny 4 is landed in position 5。 Bunny 6 has landed in position 6。

The idea of the game is that the bunnies are shown turned purple。

 and then the game player must click on the bunnies in the order that they were turned purple。

If the player can remember the ordering of all seven bunnies， the player wins。

They are three challenges to designing this game。 The first is how to randomly swap the positions of two bunnies in a bunny's array。

 generating two random numbers between 0 up to， but not including 7 is easy。

 Suppose we generate a3 and a5。 We'd like the bunnie's array in position 3 to contain the bunny that is presently located in position 5 of the bunnie's array。

 And we'd like the bunny's array position 5 to contain the bunny that is located in position 3 of the bunnie's array。

This is quite challenging to accomplish。 The difficulty can be seen by the following analogy。

 Suppose I have a cup containing orange juice and a cup containing grape juice。

And I'd like to switch the contents of the cups。 I can try a quick。

 jerky motion where I simultaneously throw the contents of each cup straight up into the air and quickly cross my arms before the contents of each cup come down。

😊，This is not likely to work。 Probably nine times out of 10。

 I'm going to wind up with juice all over the floor。

 It would be much easier if I were allowed to bring in a spare cup。

 I can first pour the contents of cup 1 into the spare cup。 Next。

 I can pour the contents of cup 2 into the now empty cup 1。 Finally。

 I pour the contents of the spare cup into cup2。 and I have successfully swap the contents without making a mess。

😡，The code to accomplish this in Alice is exactly the same idea。 I create a variable named Temp。

 First， I placed the bunny in position 3 of the bunny's array into temp。 Next。

 I placed the bunny in position 5 of the bunnie's array into position 3 of the bunnie's array。😊。

Finally， I set the bunnies array position five to be the bunny that's located in Temp。

Now let's see this pictorially。Remember the bunnies never moved。

 Their positions in the array are changing。 You can see the bunnies are standing from left to right in the order。

 Bunny， Bunny 2， Bunny 3， Bunny 4， Bunny 5。 Bunny 6 and bununny 7， below each bunny。

 we show its position number in the array。 Bunny is in position 0 of the array。

 Bunny 2 is in position  one of the array， et cetera。

 Since we're focusing when swapping the bununny's positions in the array or in positions 3 and 5。

 We've added two purple boxes to show which is in position 3， Bunny 4， and which is in position 5。

 Bunny 6。😊，In our first line of code， we add a temp variable of type bunny and set its value to the bunny that is in position 3 of the array。

 which happens to be Bunny 4。 In our second line of code。

 we change the bunny that is in position 3 of our array to be the bunny that is in position 5 of the array for this short moment。

 Bunny 6 is listed twice in the array in position 3 and positions 5。

 And Bunny 4 is no longer in the array。It is a good thing that we have our temp variable containing Bunny4。

In our third line of code， we set the bunny in position five of the array to be the bunny that is in our temp variable。

 Bny4。The second challenge is to show the user the new ordering of the bunnies after we have done several swaps。

 That's quite simple。 All we need to do is to iterate through the array of bunnies for each bunny that is being iterated through。

 just turn its paint to purple and then back to white again。The third challenge is somewhat tricky。

 We need to remember the sequence of bunny that the game player clicks to make sure that it matches the actual order of the bunnies and are now mixed up array。

 The solution to this problem is somewhat subtle。 We create a scene variable index。

 which we initially set to 0。Now， when the user clicks on one of the bunnies。

 we check to see if the bunny that the user clicked on matches the bunny in position0 or position index of the bunnys array。

 If it matches， we increment index by one。 So the next time the user clicks on a bunny will'll check to see if that bunny the user clicked on matches the bunny and position one of the bunny's array。

 etc。😊，However， if the bunny the user clicked on does not match。

 we will immediately set index to be minus-1， indicating that the user has lost。 Thus。

 the game ends when either index becomes-1， meaning the player is lost or index becomes7。

 meaning the player is one as the player successfully remembered the order of the bunnies from position 0 in the bunny's array all the way through the bunny in position6 of the bunny's array。

 let's build this game。😡。

![](img/0aa82b10814e24fbaa261a820bdd9adf_3.png)