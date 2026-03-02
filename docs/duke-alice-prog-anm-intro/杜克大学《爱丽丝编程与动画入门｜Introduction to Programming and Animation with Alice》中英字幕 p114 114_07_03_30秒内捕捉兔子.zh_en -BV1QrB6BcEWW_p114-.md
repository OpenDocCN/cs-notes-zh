# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p114 114_07_03_30秒内捕捉兔子.zh_en -BV1QrB6BcEWW_p114-

![](img/6230a34f6921a5c43e49564e7be9b32e_0.png)

![](img/6230a34f6921a5c43e49564e7be9b32e_1.png)

In the next few lessons， we'll be experimenting with creating variations to our bunny colliding game。

Our plan will be to review the changes we'd like to make。

 describe how we'll go about making those changes， and then build the modified game。In this lesson。

 we'll describe the first variation。Let's try to allow the player to have 30 seconds in which to collide with the bunnies。

To create this variation will require us to make five changes to the game。We'll need to add a timer。

 we'll need to create one new event and make a slight change to one of the existing events。

 and we'll need to make two minor changes to the main driver loop in my first method。

Let's describe each of these changes in a bit more detail。The first step will be to add a timer。

 You can save a bit of time by saving out the timer we created last week and adding it back here。

Alternatively， we can just go ahead and add a new timer， which is really a 3D text object。

We'll of course， need to add a variable to keep track of the time left and also create a decreased procedure。

 which will do that double bookkeeping trick to decrease the variable and update the display。

We also have one other subtle problem。In this game。

 the ghost is going to move and the camera will move with the ghost as the camera's vehicle has been set to be the ghost。

😊，Having a timer on screen will be a problem， as the time left will no longer appear on screen once the ghost starts to move。

We can fix this problem by setting the timer's vehicle to be the ghost so that the timer always moves with the ghost。

 staying in the lower left corner of the screen。We'll need to make two changes to the events。

 The first is that we need to add an event that runs every second。As long as there is time left。

 we can call the decreased procedure to decrease the time left by one second。

We should also change the key press procedure。 We only want the left arrow。

 right arrow and up arrow keys to work。If there is time left。Thus。

 we'll be able to put a singleal outer if statement around the entire procedure to only process the keys being pressed if there is time left。

We'll also need to make two changes to the overall gameplay driver loop in my first method。Currently。

 the bunny's hop， well at least one of them hasn't been collided with。

We'll need to change the buoant condition of the game to only have the bunnies hop while there is time left。

And finally， we cannot always compliment the game player。

 It may be the case that the player was not able to successfully collide with all 10 bunnies within 30 seconds。

😊，In that case， we'll have to have the ghosts tell the player that he or she was not successful。

Much of the difficulty in building cool games is in the understanding of the game flow。

 What I mean by this is that it takes a bit of time to understand where in our project the changes will need to be made。

Make sure you are comfortable in understanding exactly why each of these changes will be necessary to make。

 as well as developing a good intuition about why we'll be changing the events we are and the main driver loop。

Then let's go ahead to the next lesson and make those changes。



![](img/6230a34f6921a5c43e49564e7be9b32e_3.png)