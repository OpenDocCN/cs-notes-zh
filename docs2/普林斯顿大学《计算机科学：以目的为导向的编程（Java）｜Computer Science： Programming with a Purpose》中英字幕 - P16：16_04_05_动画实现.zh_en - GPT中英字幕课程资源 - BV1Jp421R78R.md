# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P16：16_04_05_动画实现.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/10713556266d8d107a06a4b57fe1597d_0.png)

Now we're going to take another step with output graphics and add animation。

 which again opens up a whole new world of output that we can provide from our programs。

So the idea from animation is to just make things appear to move with standard draw turns out to be not so difficult to do what we're going to do is just repeat the following steps we have here a ball black ball drawn on a gray background we're going to clear the screen。

 move the object draw the object again at a different position and then display it and just pause briefly。

 it turns out at computer speeds， you don't have to leave it up for very long for the eye to get the appearance that everything is moving。

So as long as the display time is bigger than the time that it takes to clear the screen。

 which it is， we have the illusion of motion and it's very easy to arrange for this within one of your programs using standard draw so we're going to look at the bouncing ball application that's kind of the hello world of animation so ball's got some position Rx and RY and we're going to give it constant velocity Vx and VY that's just the amount that it moves at each time step。

So to move the wall， we just change the position to R x plus Vx and R Y+ VY。

 so that's an easy computation if it hits a vertical wall。

That is one of these walls here then we just change the sign of the velocity and make it move in the other direction and so that's easy and if it hits a horizontal wall。

 then we switch the sign of Y to make it move in the other direction so that's all that we have to implement in our program。

 move the ball， check that whether or not it hits a vertical a horizontal wall and if it does switch the corresponding coordinate。

And then redraw。 So here's the code for this。 again， it fits on the slide， 1015 lines of code。

We're going to start our ball up kind of in the middle of pie。

 and we're going to give it a velocity that looks good in lecture。In its radius is 0。

05 that's the size of the ball that we have there， we're going to make things go from minus1 to plus1 just to make the code simplify the code a little bit and now we're just going to stay in an infinite loop。

 the ball will bounce as long as you keep your computer on。

First thing we do is set the pen color to be light gray and then draw a filled square that fills the whole screen。

Then we're going to check for whether or not we hit one of the walls。

 so if our current position in x plus the velocity in x plus the radius of the ball is bigger than one。

 that means it hits the right wall and so we have to change the velocity in x to go the other direction and then there's a check like that for the y coordinate as well。

So that could be plus or minus1， that's why we chose the scale to be between minus1 and plus1。

Then we update the position， set the pen color to black， draw the ball。

 and then here's where we use show， which says just show that ball for 20 milliseconds。

And that's long enough that the ball， you see the image of the ball and not the image of the clear screen with your eye。

 That's it。 That's a complete program for implementing bouncing ball。 And if we run this。

 there we get。A ball that bounces along on the screen as long as you want。

So now you can not just draw not only just draw things， you can draw things that move。 And again。

 there's many， many cases where you might be modeling something in the real world where you want to see motion of this type。

We have demos later on in this course and in later courses where you have multiple balls that collide in various other phenomenon that we can easily visualize with animation using standard draw。

Just as a warm up pop quiz， what happens if we take the clear of the screen and move it out of the loop？

So we'll take that clear screen code and just move it out of the loop。

 So now what's this program going to do？Well， it's easy easy enough you just try it and what that shows us is the entire path that the ball ever traversed。

And that's interesting to watch as well。And you'll see you'll have many other examples where you'll be able to observe what happens with the bouncing ball。

 we can apply gravity or electric charge or whatever else we want and get an interesting simulation。

And it's just just an example of using even more capabilities of standard draw。

 so one of the things that we can do is instead of a black ball。

 let's show a picture of a tennis ball。And let's make a sound when it hits one of the sides or the top or bottom。

 we'll talk about making sound in the next lecture。

 but it's another library of ours called Standard Aud that will play a sound that's given in a file。

 so here's what happens to this one。And you can hear the little bounce when the ball hits one of the walls。

And you can see you can have endless entertainment with this simple tool。

So that's the summary we've added to Java for your programs。

 for libraries that greatly expand the kinds of programs that you can write。

If you download an intro CSS， you have them or you can get them at the book site rather than just being able to print text output and take text from the command line。

 you can have a standard input stream as well， and you can do standard drawings with all kinds of interesting applications even though there are only a few graphic primitives and next time we'll talk about standard audio where audio where you can write programs that manipulate sound。



![](img/10713556266d8d107a06a4b57fe1597d_2.png)

![](img/10713556266d8d107a06a4b57fe1597d_3.png)