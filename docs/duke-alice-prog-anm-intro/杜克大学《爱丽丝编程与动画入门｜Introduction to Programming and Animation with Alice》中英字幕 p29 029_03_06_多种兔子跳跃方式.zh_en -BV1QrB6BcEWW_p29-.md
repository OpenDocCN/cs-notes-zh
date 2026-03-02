# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p29 029_03_06_多种兔子跳跃方式.zh_en -BV1QrB6BcEWW_p29-

![](img/bd1dc98fb784a20d7a433c6585524fd7_0.png)

In this demonstration， we are going to create some additional instructions or procedures。

We're going to create two variations of the regular triangular hop we created in the last session。

It will allow us to create a simpler hop that we'll use in later sessions。

 as well as a more realistic， albeit complicated hopping instruction。

 The first new instruction to create is rectangular hop。

Instead of the triangular hop we created for the bunny last session here we'll have the bunny move in a rectangular motion up。

 then forward， then back down。Let's get started。Let's click on the hexagon at the top center of the screen。

Then let's click on Bunny。And select Add Bunny Proc。We'll name this procedure rectangular hop。

When naming instructions， we actually use something called Caml case。

Which means that the first word begins with a lower case letter。

 and subsequent words begin with an upper case letter。Therefore。

 we make the R in rectangular lowercase and the H in hop uppercase note that there is no space between the two words。

Please note that Alice doesn't know anything about camels or camel case。

 It's just a convention that many programmers like to use。

 which will follow The code for rectangular hop is straightforward。 In order。

 the bunny moves up one unit。 then forward half a unit。 then down one unit。

 Let's go ahead and do that。 First， we click on Ok to create rectangular hop。

Now we'll explicitly state that we're going to do this code in order。And first。

We will move the bunny up。One unit。Then we will move the bunny。Forward。Half a unit。And finally。

 we will move the bunny。down。1 unit。To try this out， let's click back on my first method。Presently。

 the code calls the old hot method twice。Let's drag the two hop instructions into the trash can。

Sstructction1。An instruction to。Now， click on the triangle to the right of the word this and select this dot bununny。

Now we can drag the rectangular hop instruction into my first method immediately after the bunny is turned to face this mango。

Now we can test out our rectangular hop instruction by clicking on the Run method。

Note how the bunny now hops differently than it did before。

You might wish to drop a hop instruction after the rectangular hop instruction to illustrate the difference。

They can do that by simply selecting the Hrp instruction。

And running it immediately after the rectangular hop instruction。 And now when we run。

 we'll see the bunny do a rectangular hop。Followed by the old fashioned triangular hop。

Now let's create one more bunny hop， a realistic hop， just as you did before。

 create a new bunny procedure which can be named realisticistic hop。Click on the triangle。

Specified Bonnie。And add bununny procedure， and we will name it realistic。Hop again， using Caml case。

For this hop， it is worthwhile to look at a storyboard。First， the bunny leans forward on its feet。

 kind of like a ski jumper。Then the bunny will hop in the triangular hop fashion before standing back up again。

 So there are going to be four parts to this realistic hop。From the initial scene in scene 0。

 the bunny gets into the ski jumping position in scene1。Then in scene2， the bunny is taken off。

In scene 3， the bunny has landed。 and finally， in scene 4。

 the bunny has returned to its original upright position。

These four steps are going to be done in order。So start your realistic hop instruction with a do in order。

The first part， getting the bunny to turn forward on its feet is the trickiest。

If you ask the whole bunny to turn forward， say an eighth of a revolution。

 the whole bunny turns forward。But what we want is the whole bunny。

 except for its feet to turn forward an eighth of revolution。To accomplish this。

 we can use an animation trick。At the same time， the bunny is turning forward one eighth of a revolution。

 we will have the bunnies two feet， turn backwards， one eighth of a revolution。

This turning backwards， one eighth of a revolution will cancel out the turning forward。

 making it appear as if the entire bunny， except for its feet。

 are turning forward one eighth of a revolution。Let's try it out。First。

 add a do together into the first line of the do in order。Next， within the do together。

 have the Bunny turn forward， one eighth of a revolution。Tur。As the bunny to turn forward。

One eighth of a revolution。To access the bunny's feet。Actually。

 you have to access the bunny's left foot separately from the bunny's right foot。

 Click on the triangle to the right of the word this on the left hand side of the screen。

Note that while you are creating the realistic hop instruction。

 the word this refers to the bunny rather than to the entire scene。Now select the bunny's right foot。

We click on the rest of the joints。And we select。Get right foot。Now。

 when you drag in a turn instruction， it will be the bunny's right foot that is doing the turning and have the right foot turn backwards one/ eighth of a revolution。

Right foot。Can turn。Backwards， one8 of a revolution。 At the same time， the bunny is turning forwards。

 one8 of a revolution。We can do the exact same thing for the bunny's left foot。We select this。

And now we choose to access。The bunnie's left foot。And again。

 we will ask the bunny's left foot to turn。Backwards。One eighth of a revolution。

Before we continue the animation， let's try out what we have done。

Let's click back on my first method。Now， the word this refers to the scene。

 So let's click on the triangle to the right of the word this and select this funny。

We can now drag in realistic hop。After rectangular hop。

And as we don't really need the regular hop instruction。

 we'll just take that one and throw that into the trash。Now we can run the world。

The bunny turns to face the mango。Does a rectangular hop？

And now gets into position to be ready to do the realistic hop。

We do have a slight complication because objects in Alice are egocentric。

 They rely on their own orientation。Now the Bnie has turned forward， one eighth of a revolution。

 this is great news。The reason is that moving the bunny up one half a unit actually moves the bunny forward。

 half a unit as well。Let's try it out。Click back on the Realistic hopop tab。

Now we can drag in a move up half unit instruction。So we select move。U。Half a unit。

Let's run the world again。Butun he first does a regular rectangular hop。

Then it takes off moving up and forward at the same time。Now。

 we can get the bunny back down simply by moving the bunny forward half a unit。 Let's do it。

We simply ask the bunny to move forward after it's moved up。 The bunny can move forward。Half a unit。

Let's run the world again to see if it works。Butdy does the rectangular hop。It goes up。

And forward to get back to the ground。Finally， we just need to get the bunny standing up again。

To do this， we need to do the opposite of the first do together instruction。

Instead of dragging and dropping all of these instructions。

 we can simply right mouse click on the do together and select copy the clipboard。Next。

 we can drag back from the clipboard to the end of the instruction。 We simply drag the code。

 which we've copied。And put it right back。At the end of the instruction。Finally。

 we can change all of the forwards to backwards and all of the backwards to forwards。So。

 we'll turn the bunny。Backward， and we'll turn the feet。Forward so that it's the feet。 don't move。

Let's test this out。But he does a rectangular hop。It lean forward。It's a more realistic hop。

 and it stands back up again。Exactly what we'd like for a more realistic hop to be。Finally。

 we should add a comment or two describing the funny turning of the bunny。

We' going a a comment in the beginning， telling the Bunny。Gets into ski。Jumping position。

And then we can add a comment at the end。To say。Bunny。Gets back。Into its standing up position。

One last modification。Let's make the bunny turning forward to get into position to hop。

 occur a little bit quicker。By default in Alice， all animation instructions require one second to run。

By clicking on the add detail to the right of an instruction and then selecting the duration。

 we can change the animation to Ron rather than in one second in a quarter second。

We can do this for all three of the initial instructions to get the Bunny into ski jumping position by making all of the durations a quarter second。

And we can do the same thing for the three instructions to get the bunny back to standing up again after it's finished its jump。

Simply by changing the duration to be a quarter second。



![](img/bd1dc98fb784a20d7a433c6585524fd7_2.png)

Now when we run the animation。We'll see the bunny doing its rectangular hop and then a more realistic hop。

Great， you have now written your first complicated but realistic instruction for the bunny。

