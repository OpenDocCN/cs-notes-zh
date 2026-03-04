# Victor Gordan【中英⚡OpenGL教程｜OpenGL Tutorial】 p17 P17 Face Culling & FPS Counter -BV1kkvTz8Egh_p17-

![](img/716149bb056029d03e28afd984841bed_0.png)

Today I'll show you what face calling is and how it affects performance We are also going to measure this performance change by making an FPS counter So face calling is a step in the graphics pipeline that decides if a triangle will move on to the fragment shader aka if the triangle will be drawn or not Open gel decides this by seeing which side of the triangle is currently facing the camera generally speaking in most 3D graphics programs it is the front side of a triangle that is sent to the fragment shader and the backside of a triangle that is discarded the way open gel figures out which side is switch is by an index convention which can either be clockwise or counterclockwise in a counterclockwise framework if the order of the indices of a triangle are a counterclockwise when facing us then the side we see is the front side likewise if the order of the indices of a triangle are a clockwise when facing us then the side we see is the back side for a clockwise frame。

Work it's the exact opposite。 Most graphic programs use a counterclockwise standard。

 but don't expect all of them to use this。 Now in order to put all of these into code。

 we just have to enable the face calling using GL enable with gel called face specify which face we want to keep 99% of the time that will be gel front and then specify the standard we want to use again I suggest using the counterclockwise1 since from what I've seen is more common than the clockwise1 Now if we run the program you'll notice that when we get inside an object。

 we won't be able to see its insights since it contains the box of the triangles， which discarded。

 Therefore we only see the background So let's see if this makes any difference in performance for that well need an Fps counter which all display in the title of the window let's start by creating three doubles for the previous time the current time and the difference of this two then we also want an unsigned integer that well act as a counter。

To see how many frames we have in a certain amount of time now FPS is simply the amount of frames you get in a second so that means that in order to get the Fps we can count the number of frames we get in a second a frame being one loop in our main wide loop but that would also mean that our FPS will get updated only once a second instead let's update it every 30 of a second for example to do that we just need to get a current time in seconds using Gfw get time the time difference and increment the counter then if the difference is higher or equal to a 30th of a second we go ahead with a measurement of the Fps the Fps well simply be equal to one divided by the time difference which is just the amount of frames in a second that this time difference gives but the time difference contains multiple frames which are equal to the counter so we also need to multiply it with the counter as well Now we could stop here but it's also useful to know how long a frame take。

In terms of millisecondsTo do that， we simply divide the time difference by the counter which gives us the number of seconds a frame takes and then multiply that by 1000 to transform it into milliseconds then we simply put together the new title and apply it to the window using GFW set window title then we want to set the previous time as the current time in order to get the time difference back to0 and also set the counter to0 Now if you start your program you'll be able to see the amount of frames。



![](img/716149bb056029d03e28afd984841bed_2.png)