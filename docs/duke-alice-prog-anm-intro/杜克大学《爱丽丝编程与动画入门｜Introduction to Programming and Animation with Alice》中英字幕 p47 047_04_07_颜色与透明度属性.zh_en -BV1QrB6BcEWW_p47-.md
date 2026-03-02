# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p47 047_04_07_颜色与透明度属性.zh_en -BV1QrB6BcEWW_p47-

![](img/8a6bcbb78e65ddae364d4709383ae657_0.png)

![](img/8a6bcbb78e65ddae364d4709383ae657_1.png)

In this demo， we will implement a story that uses all the things we have learned in this lesson。

 several objects， properties circling around an object and getting exact measurements with built in functions。

 A hungry wolf is looking for a bunny。 A bunny appears and moves around。

 disappearing some and finally hops on a car and drives off。😊。

Here is the story board for the story we will build。 The objects in the world are a big， bad wolf。

 a bunny and a hatchback car。 I'm starting with scene 0， which is about setting up the scene。

 I'll place some objects and then move them or make them disappear。

 I'll paint the bunny yellow and make it turn invisible。 I'll move the hatchback backward 10 units。😊。

Seen one is where the animation will start with just the big。

 bad wolf shown facing the camera and saying。Nothing much happening today。And scene， too。

 the bunny will appear and jump up and down。In scene 3， the big。

 bad wolf will turn to face the bunny and look down at it。 The bunny will change its color to red。

 and turn invisible。And seen4， the bunny will reappear on the other side of the wolf。

 still facing the camera。 The bunny jumps up and down。In scene 5。

 the wolf turns around to face the bunny。In scene 6， together。

 the bunny does a half circle around the wolf while the wolf turns in place。

 keeping its eye on the bunny。😊，In scene 7， the hatchback moves forward 10 units。

 stopping behind both animals。In scene 8， at the same time。

 the bunny moves up the height of the hatchback and the wolf looks up。 Then at the same time。

 the bunny moves forward to the top of the hatchback。

 and the wolf turns towards the direction of the bunny。😊，In scene 9。

 the bunny faces the same forward direction as the hatchback。 Then at the same time。

 the hatchback moves forward off screen， taking the bunny with it。

 And the wolf turns towards the direction。 The car is going。 Lastly， the wolf says， rats。

Let's build this world。 We have already put in the three objects， the big bad wolf。

 the bunny and the hatchback。We also have already written a jump instruction for the bununny。

 Let's look at that。Under Bunny。Here's the jump instruction。So you can see here。

That we have a the bunny moves up and down。And that we have a parameter called how high for how high the bunny is to jump。

And we also have both of the instructions happen very quickly in 0。25 seconds。Let's finish the setup。

Will go back to my first method。Now， we have several commands we want to do to continue the setup。

 We want the hatch pack moved off screen。 We want the bunny painted yellow and made invisible。

We could do that in scene set up by doing a one shot to move the car back。

 and we could set the bunny paint property。To yellow and the bununny opaci property to zero。

But there's another way。 Alice has a special procedure called perform custom set。

 where you can put commands that run before the animation is shown。😊，Let's do that。

To find this special procedure， click on the scene tab。And then you'll see procedures。

 and the first one is called performform custom setup。 So click on that。

That pops up in a new tab where we can put instructions that we want to happen right away。

 Let's have the hatchback move backward 10。Select Haback。And move。Backward。10。

Then let's have the bunny。said it's paint property。To yellow。

We'll need to scroll down to find the set paint。Will set that to yellow。

And then drag over the set opacity and set it to zero to make the bunny invisible。Play your world。

And you'll see。That you only see the Wolf。 Now we are ready to write code。 Now。

 be sure to click on the My first method tab。This is where we want to put our code。

 you don't want to put any more code in the performform custom setup。In fact。

 you can just click on Perform custom setup and click on the X to get rid of it and then click on my first method。

Let's start in my first method by adding a due in order for all the code。Next。

 we might want to include information about the setup we just did。 Let's include a comment。

It'll say several initializations。Are done in the。Perform custom setup procedure。Now。

 let's write code。Let's add another comment。To say。Bunny appears and gets Wolf's attention。Whatops。

There we go。Now， let's have the big bad Wolf speak。Or rather， say。We'll have it say nothing。Much。😔。

Happening today。Let's make that。 Two seconds。So it'll stay up longer。 So duration。Qu。😔。

Then let's make the bunny appear。So select the bununny。

And then you'll have to scroll down to the set opacity。And set it to one。Next。

 we'll have the bunny jump some amount。You'll need to scroll up and drag over the jump。

I'm gonna have my bunny jump， say， 1。5。Let's see what that does。 Well click run。

Nothing much happening today， the bunny jumps。That's it。 Now， I'm gonna make my。

Window bigger so you can see it better。 You can scroll。And make it bigger like this。



![](img/8a6bcbb78e65ddae364d4709383ae657_3.png)

We want to add in a few more instructions。Let's have the wolf turn to face the bunny。

Do also like the wof。Turned face。😔，The bunny。And then we want the wolf to just turn and look down at the bunny。

 so let's select the big bad Wolf's neck。So select big bad Wolf and then look for the neck part。

If you don't see it right away， let's see。 it's all the way up here。 There it is getne。

Now we want the neck to turn forward。Just a little bit。 So turn forward， maybe just。

I'm going to type in。0。1。Then the last thing we're going to do is set the bunny's paint property to red。

 so again， pick the bunny。Scroll to the bottom and drag over set paint。To red。Let's play that。

Nothing much happening today that bununny appears at jumps。The wolf turns and looks at it。

 and the bunny turns red。Perfect。Next， let's add a comment。For the next part of our story。

 we're going to have the bunny disappears。Moves to the other side of the wolf。

And reappears facing the camera。Now， let's make the bunny disappear。We can drag over the ce opacity。

And set it to 0。Let's use duration 2。 so it happens in two seconds， a little slower。2 seconds。Now。

 we want to move the bunny to the other side of the wolf and facing the camera。

 So one way to do that would be to have the bunny circle halfway around the wolf。

If the bunny does that， it's facing the wrong direction。

 so then we would need to have it turn around and face the camera， so let's do that now。

Have the bunny turn。Now the wolf is to its left， so we're going to have the bunny turn left。

Halfway around 0。5。Willll do that as seen by。The big， bad wolf。And since the body is invisible。

 we can set the duration to zero so this happens instantly。Duration。Willll have to type the0。Now。

 the bunny needs to turn to face the camera。So we'll drag the turn to face over。To the camera。

And we can also make that duration0。The last thing is to make the bunny reappear。So， drag over。

Copacity。And said it。To one。Now， play your world。The bunny jumps。Return red。He disappears。

He reappears on the other side of the wh。Perfect， let's add another comment。Bunny moves around a lot。

And what we're going to do is have the bunny jump。Again。So。And again， any amount you want。

 I'm going have my bunny jump。Say 1。2。Then the big， bad wolf should turn to face the bunny。

So we'll use turn to face。Bunny。Now we're going to drag in a do together。

And we're going to have the bunny move and the wolf turning and following the bunny as it moves。

So first， let's have the bunny turn to its right in half a circle。So， the bunny。Turn。😔。

To its's right。Half a circle。Again， as seen by the big bad wolf。And at the same time。

 we're going to have the big bad Wolf turn in place。So， turn。To its。Right。And0。5。Haifwei。

Play the world。Now the bunny disappears。 It's on the other side of the wolf。

 the wolf turns and looks at it， and they both turn at the same time。Now。

 let's add the final part where the bunny escapes with the car。So let's drag in a comment first。

Bunny escapes in car。Then we'll have the hatchback move forward10 to appear back in the scene where it was originally。

So we' pick the hatch pack。Move。😔，Forward。10 this is where it's important to put that command。

In the performform custom setup， so you can go back and look and see how far the hatchback moved backward and then have it moved forward the same amount。

Then next， we're going to add in a do together。We're going to have the bunny move up。

We want it to actually move up the height of the hatchback， but we don't know that number yet。

 so we'll just have it move up any amount。Bunny。Move。up。siwan。

Now we need to find the height of the hatchback。We can click on the Haback and functions tab。

And then we can look for the height of the hatchback and drag that over the number。Now。

 as the bunny moves up， we want the wolf's head to follow it。 So also in the dew together。

 we need to have the big bad Wolf's neck turned backwards， just a little 0。1。

Since we already turn the neck earlier， we can copy。That command to the clipboard。



![](img/8a6bcbb78e65ddae364d4709383ae657_5.png)

And then drag it in to the do together。And change the forward to backward。Next。

 we want the bunny to move over to the top of the hatchback。What's Dr gonna do together。

We don't know how far forward the bunny should move。So we'll just have the bunny。

Move forward Any amount。So， move。Forward。😔，siwen。Now， we can use a function again。

 So click on the functions tab and look for。Distance to， get distance to。

And drag that over the one and then say the distance to the hatchback。

Now the same time the bud's moving forward， we want the wolf to kind of follow it。

 so we're going to have the wolf turn a little bit here in the dow together。

Pick on select procedures。And we'll have the wolf turn to its right。Maybe。0。25。All right。

 let's go ahead and play that and see what that looks like。now the bunny is going to disappear。

It reappears。😔，And now the car comes， the bunny moves up and onto the car。

Now it looks like I need the bunny to turn to face the car before it moves forward。

 so let me do that。I'm gonna have the bunny。Turn to face the car。

Will do it over here right after the hatchback moves forward。Bunny turned to face the hatchback。

Let's see if that looks better。The bunny disappears。Reappears。

Now that the bunny is on top of the hatchback， we want the bunny's vehicle property to be set to the hatchback。

So drag over the bunny's vehicle property。Seet vehicle。

And set the bunny's vehicle to be the hatchback。 We also want the bunny to turn the same direction as a hatchback so we can use the Orient to command。

So what's。Scroll up a little bit until we see Orient2。Let's drag that over。Orient to。😔，The hatchback。

Now we're going to add in one more do together。We're going to have the car drive off with the bunny。

So， we'll have the hatchback。Move forward。Let's say， 10 units。And then at the same time。

 we're going to have the big bad Wolf turn a little bit more to its right。So the big bad Wolf。Turn。

Right，25。And then the final thing is we'll have the big bad Wolf。Sai。😔，After the do together。Rats。

And here's the code for that last part。Okay， let's play the world。Nothing much happening today。

There's the bunny jumping up and down。The bunny disappears。Reappears。They move together。

 The car comes in。The bunny jumps on the car and turns the face the same direction。Oops。

I think we messed up。That certainly didn't look right。We want the big， bad wolf to turn to its right。

 not forward。Okay， let's try that again。 That's the great thing about Alice is when you make a mistake。

 sometimes it's very obvious that you made a mistake。 All right， let's play the world。😊，We see。

The bunny appear。Then it disappears。And it moves the other side。 And then the car comes in。

 and the bunny jumps on the car， turns and faces the same direction， moves off。

 and the wolf turned with it。Now， building that animation was fun。

Enjoy using properties and functions。