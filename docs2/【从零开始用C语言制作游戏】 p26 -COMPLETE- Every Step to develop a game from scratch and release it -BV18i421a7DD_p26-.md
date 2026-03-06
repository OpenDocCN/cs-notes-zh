# 【从零开始用C语言制作游戏】 p26 -COMPLETE- Every Step to develop a game from scratch and release it -BV18i421a7DD_p26-

![](img/04ac20b27193dff2ac4a92a77496c329_0.png)

Hello folks， in the course of 24 live streams， we developed a game from scratch。

 going from having absolutes with nothing。

![](img/04ac20b27193dff2ac4a92a77496c329_2.png)

🎼To having a game released on steam。

![](img/04ac20b27193dff2ac4a92a77496c329_4.png)

🎼In these 24 live streams， a total of 8 to1 hour of development。

 there is a lot of good information for you so I's how to organize it and list the main topics discussed throughout the development。

😊。

![](img/04ac20b27193dff2ac4a92a77496c329_6.png)

![](img/04ac20b27193dff2ac4a92a77496c329_7.png)

🎼Kind of a step by step of what we did to develop the entire game hopefully it can help you in point you in the right direction This is the final result we developed。

😊。

![](img/04ac20b27193dff2ac4a92a77496c329_9.png)

![](img/04ac20b27193dff2ac4a92a77496c329_10.png)

![](img/04ac20b27193dff2ac4a92a77496c329_11.png)

The game starts off as a simple breakout clone with special occasions with the games field。

 animations， particle and such， then we play around with the idea what if other arcade games had to be like breakout？



![](img/04ac20b27193dff2ac4a92a77496c329_13.png)

So you get breakout punk， breakout tets， breakout space eigators。

Be developed entirely on a live stream， you can easily download the source code to learn， modify。

 copy， and make our own games。I divided the tasks accomplished based on each live stream so you can follow that chronologically。

 so let's get started。

![](img/04ac20b27193dff2ac4a92a77496c329_15.png)

![](img/04ac20b27193dff2ac4a92a77496c329_16.png)

Okay， welcome everyone to my first ever live stream on E One。

 I started off by playing the structure of the games code and tested the build by making a hello world program。

 so if I try to run。I have the hello sealer， then we look through the wing 32 documentation to add an entry point for game。

 we opened the window， go the first version of our renderer， processed input and timingies。



![](img/04ac20b27193dff2ac4a92a77496c329_18.png)

O to episode2， hello everyone， welcome to my second live stream right off the bat we started making the gameplay。

 the breakout clone and started to organize the code to spa blocks。



![](img/04ac20b27193dff2ac4a92a77496c329_20.png)

They implemented a simple AABB collision for the player and the ball and implemented the first version of the ball versus block collision。

 a full sweep that stops the ball and the closest block could colled that frame Okay。

 now it makes sense。😊。

![](img/04ac20b27193dff2ac4a92a77496c329_22.png)

![](img/04ac20b27193dff2ac4a92a77496c329_23.png)

Then in episode three， I started to play around with different levels now it's pretty cool， I think。

 starting to look like a real game right， based on what people were suggesting and some ideas of my own。

 we built the structure to allow us to easily add no levels and change completely the game rules at that level。

😊。

![](img/04ac20b27193dff2ac4a92a77496c329_25.png)

![](img/04ac20b27193dff2ac4a92a77496c329_26.png)

On episode4， we finished the structure of the game code and programd several game mechanics that allow us to make interesting levels and we don't。



![](img/04ac20b27193dff2ac4a92a77496c329_28.png)

![](img/04ac20b27193dff2ac4a92a77496c329_29.png)

Eptplode5 was when the game really started to shine。

 I added the levels that corresponded to the original game Z core idea playing several arcaded games as if they were breakout。

 having most of the levels this early allowed us to keep iterating and improving them all the way to the final version。

 and we also implemented a core random number generator in our game engine。



![](img/04ac20b27193dff2ac4a92a77496c329_31.png)

Adro 6 was all about soliding what we built for， so I created a logging system to help debugging our game and made several improvements。

 fixing bugs and making overall more robust。

![](img/04ac20b27193dff2ac4a92a77496c329_33.png)

With the core gameplay done on episode 7 we started to improve the game's field。

 we added small animations to the game， ball trails and overall feedback to the player。

 this is what we wanted。

![](img/04ac20b27193dff2ac4a92a77496c329_35.png)

Then on episode 8， we doubled down on the game field and created a full particle system。

 added more animations， more feedbacks， and improved the controls。

There was also some boat fixing and boat creating too， right？😊。

couldn' couldn't make it in time with the game play on a solid state we shifted our focus with the engine once again on until9 engine programming right the first thing we did in our engine robustness pass was to support drawing rotated rectangles in our software rangeer there was some head scratching with all that now。

 but we put it off in the end。

![](img/04ac20b27193dff2ac4a92a77496c329_37.png)

![](img/04ac20b27193dff2ac4a92a77496c329_38.png)

Oh， victory。

![](img/04ac20b27193dff2ac4a92a77496c329_40.png)

嗯。😊。

![](img/04ac20b27193dff2ac4a92a77496c329_42.png)

In fact that this is the T live stream on Ep 10， we started off by making some temporary program art and displayed pixelo independent Bimps in our software render huh？

😊。

![](img/04ac20b27193dff2ac4a92a77496c329_44.png)

Then I did some better looking trick art and make the player move with something pixelo accuracy。😊。

Making it look and it feels super smooth。Oh， I really like that。 We also added a pretty float system。

 a unique random seat for each run and then awesome force to effect as well as some other improvements perfectfect。

 that is just perfect strong blocks。😊，U crap got strong box。



![](img/04ac20b27193dff2ac4a92a77496c329_46.png)

Aptute 11 was all about audio we implemented a game engine sound system from the ground up。

 you started by implementing direct sound and playing a square wave now I'm going to try。



![](img/04ac20b27193dff2ac4a92a77496c329_48.png)

Listening to this guy here and let's hope I don't die。It's still pretty bad。

And then reading wave files， playing them， mixing them。

 added cool features like penny sound and pitch shifting So yeah。

That was really cool then on episode 12 we fixed some audio bugs and programmed the job system to make Mo threaded possible and easy to use our game engine。



![](img/04ac20b27193dff2ac4a92a77496c329_50.png)

With that in place， we started making some things run asynchronously。



![](img/04ac20b27193dff2ac4a92a77496c329_52.png)

Because we are running asynchcraously， asynchronousism。



![](img/04ac20b27193dff2ac4a92a77496c329_54.png)

And a synchronous way。On E 13， we did some things to make the game more complete。

 implemented the main menu， a safe system， started implementing the sound effects and fixing more bugs。

😊，Yeah。

![](img/04ac20b27193dff2ac4a92a77496c329_56.png)

It's a great stream。Sound effects do make a other thing。

The focus was all along game byagonnetural 14 we added a ton of sound。

 tweak the field and made the necessary improvements to our existing systems like the audio mixer to be able to create what we want。



![](img/04ac20b27193dff2ac4a92a77496c329_58.png)

Then on episode 15 we did some major visual inexperency improvements on the game。

 the main menu now feels a lot nicer that has better visuals， not entirely bad。



![](img/04ac20b27193dff2ac4a92a77496c329_60.png)

🎼But。The game now shows the player a h with useful power up and par down related information and added support to draw text。

I think you've got a nice privacy， look at that。

![](img/04ac20b27193dff2ac4a92a77496c329_62.png)

Aptute 16 was crazy talent we started off by solving some bugs then we started to dive head firsts into optimization first I programmed the profiler to let us know compare understand where the game is running slowly then we discuss some optimization possibilities and optimize the render we got from running the menu at 4K resolution at 66 milliseconds per frame which is 15 frames per second all the way to 16 milliseconds per frame 60 FPS。

😊。

![](img/04ac20b27193dff2ac4a92a77496c329_64.png)

![](img/04ac20b27193dff2ac4a92a77496c329_65.png)

![](img/04ac20b27193dff2ac4a92a77496c329_66.png)

And there was still a lot of room for improvement。🎼Okay。



![](img/04ac20b27193dff2ac4a92a77496c329_68.png)

Okay。😊，We managed。We managed to get that back。

![](img/04ac20b27193dff2ac4a92a77496c329_70.png)

To get that back no， to get like working at all at。16 frames per second。

 so this is the story of today。This is like the thumbnail。 This is like。



![](img/04ac20b27193dff2ac4a92a77496c329_72.png)

The victory that we achieved。So we started out。And yeah， we started out。

With a menu at 66 milliseconds per frame and finish at 12。4 milliseconds per frame。On episode 17。

 we went back to the game itself， solidifying that player's movement and animation。

 especially in regards to its frame independence。We also made a game leap after flipping the frame to give a customs frame rate。

We also improved the sounds， animations， and gameplay overall。



![](img/04ac20b27193dff2ac4a92a77496c329_74.png)

Nice。Absilute 18 was all about the last level， Teris， we designed it。

 improved the existing systems to support what we wanted to do and program and iterate it on that level。

 we from having nothing to pretty much done in this live stream。



![](img/04ac20b27193dff2ac4a92a77496c329_76.png)

On episode on 19， we weed the entire collision system， making it more robust to shift the game with。

We also created a camera system and for the minute screen shape， it really improve the gameplay。



![](img/04ac20b27193dff2ac4a92a77496c329_78.png)

By episode 20 it was time to wrap up the gameplay we did several improvements in fine tune to the games levels。

 in implemented level transitions， they really make the game shine。



![](img/04ac20b27193dff2ac4a92a77496c329_80.png)

![](img/04ac20b27193dff2ac4a92a77496c329_81.png)

On episode 21， we created an asset system for our game， respect the file。

 created the cooker to package the assets， implemented an OGG reader。

 utilize the motorthraing job system to make the OGG decompression running in parallel another cool stuff。

 It was an awesome stream。 Look at those points。 Oh my God， I missed it。😊。



![](img/04ac20b27193dff2ac4a92a77496c329_83.png)

![](img/04ac20b27193dff2ac4a92a77496c329_84.png)

We have the biggest piece of news we had in a wild， which is the game has now a ST page。

Epilence 22 was focused on polishing the gameplay， changing things like the speed and small bugs。



![](img/04ac20b27193dff2ac4a92a77496c329_86.png)

Someone suggesting added a possibility for the player to change the mouse sensitivity。

 sensitivity equals， so we wrote a par to read a confi text file from scratch。



![](img/04ac20b27193dff2ac4a92a77496c329_88.png)

![](img/04ac20b27193dff2ac4a92a77496c329_89.png)

There， the bird can change some options like mouse sensitivity in window mode。😊。

In the very end of this stream， we started a big audio reuring to make it robust to ship with。

Yeah the sound is scratching we have to take a look at that on episode 23 we finished the game we did some assembly debugging and a nice restructure of the auto mixer to make it thread safe。

 We also did some final gameplay tweaks， improvements and polish like adding more particles there are never enough particles。

 right。😊。

![](img/04ac20b27193dff2ac4a92a77496c329_91.png)

![](img/04ac20b27193dff2ac4a92a77496c329_92.png)

And that was it。 The game was done。 We're gonna have a lot stream。 so you can keep eye on that。

 That'll be pretty cool。 And on the very last stream， episode 24， we released the game on steam，6，5。

4，3，2。😊。

![](img/04ac20b27193dff2ac4a92a77496c329_94.png)

ok。I think nothing happened。 Could you hear the sound I pressed button？

I'm going to have to press again。Oh my god， the button is not working。Is this？ok ok说。😊。

When I press the button。Things appear down here。It was a chill stream where we talked a last and I told some stories give away some keys to my other games and celebrate the end of the series。

 my eating cake in the end。I also plan for what's next。

 how to improve the game updated and new projects。😊，This step is often overlooked。

 I didn't do it before my previous game， which took three and a half years to make。



![](img/04ac20b27193dff2ac4a92a77496c329_96.png)

And the bigger the development， the earlier， and more carefully， you should make the plans。

 especially post launch plan， and that was it。

![](img/04ac20b27193dff2ac4a92a77496c329_98.png)

🎼So that's the summary of this series right now you can download the game Menar code on team。

 it's also on GiHub。

![](img/04ac20b27193dff2ac4a92a77496c329_100.png)

🎼So it's called for each individual episode is on each child。



![](img/04ac20b27193dff2ac4a92a77496c329_102.png)

The next step you can take now is jump right in and start watching the development。



![](img/04ac20b27193dff2ac4a92a77496c329_104.png)

Or you can watch the Star called walkthrough， which is a macro view of what we managed to build and release。

Either way， I hope you enjoyed this video and I think if had any questions so let make games。



![](img/04ac20b27193dff2ac4a92a77496c329_106.png)

![](img/04ac20b27193dff2ac4a92a77496c329_107.png)