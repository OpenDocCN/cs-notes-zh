# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p40 040_03_04_双足动物的继承跳跃.zh_en -BV1QrB6BcEWW_p40-

![](img/bffcb1a71e60e67117775b2ff59ab325_0.png)

This world contains a bunny and a chshire cat。 The Cheshire cat is standing half a unit in front of the bunny。

 facing in the same direction。We have made the bunny half a unit high and the Cheshire cat。

 one unit tall。We can confirm this as part of the scene setup by looking at the different camera viewpoints。

So let's go ahead and click on scene setup。We can look at the different camera viewpoints that we have created。



![](img/bffcb1a71e60e67117775b2ff59ab325_2.png)

So by scrolling down to the camera markers。We've created three camera markers。

 we can click on the left view and see the view from the left。

Which shows the bunny standing directly behind the Cheshire cat。

 and the bunny looks to be about half the height of the Cheshire cat。

We can also click on the right view。And view from the right。

 And this we're going to see the Cheshire cat standing in front of the bunny。

 And because of a Cheshire cat is taller， the bunny is hidden behind the Cheshire cat。

Let's go back to this start view。And we can click on the editit code to get out of the scene setup mode。

In this world， we included the rectangular hop method created for the bunny。In my first method。

 we can ask the bunny to do a rectangular hop。By clicking on this bununny。

And asking the bunny to do a rectangular hop。We can add another bunny to the world。

 we can call this Bunny Bunny too。Watch what happens if we add another bunny to this world。

So we'll scroll over。And we'll add a second bunny to this world。

Will allow it to be named Bunny too and say okay。Let's set Bunny Tus paint to red。

To differentiate it from the first bunny。We can actually ask Bunny too to hop as well。

So if we click on Bunny2， we can drag in the rectangular hop method for Bunny2。

And if we were to run our world， we can see that Bunny can do a rectangular hop。 And Bunny， too。

 also can do a rectangular hop because all bunnies know how to do a rectangular hop。However。

 we cannot ask the Cheshire cat toho as it is not an instance of the Bunny class。

And if we click on the Cheshire cat， we will see that the Cheshire cat does not have a rectangular hop method。

Let's go ahead and remove the code that we've just added along with Bunny2。

I will remove the two lines of code。And then we'll go ahead and right mouse click on Bunny2 and go ahead and delete it。

The reason is we'd like to code up a version of leapfrog where the bunny and the Cheshire cat repeatedly hop over one another。

We saw that by creating a bunny procedure。 only bunnies can do rectangular hops。

 So let's create a procedure for bipeds instead of bunnies。

 as bunnies are a subclass of the biped superclass。😊，To create a biped level procedure。

 we start exactly as we had done for creating a bunny procedure。

 We click on the hexagon at the top of the screen。But instead of selecting Bunny。

 we select BPD and then add BPD procedure。We can go ahead and name our procedure， leapfrog。Again。

 using Caml case with the F of Frog being capitalized and the L of Le not being capitalized and click on OK。

For leapfrog， however， we will add a parameter how high whose type is decimal number。

So we can add a parameter。Haohai。And it's type。Can be specified as a decimal number。

Then by doing an order。We can add our three instructions before the first instruction。

Ask the Bped to move up。How high many units？We can then ask the BuP to move forward one unit。

And then we can ask the Bped to move back down。How high many units？That's it。

By creating leapfrog as a biped procedure， the bunny can perform a leapfrog。

 and so can the Cheshire can't。The bunny will need to leapfrog moving up one unit。

 while the Cheshire cat will only need to leapfrog moving up half a unit。

Let's go ahead and do that in my first method。So in my first method， we can ask the bununny。

By clicking on this bununny。By clicking on the editable procedure Leapfrog。

 we can ask the bununny to leapfrog1 me。Then we can select the Cheshire cat and ask the Cheshire cat to leapfrog。

Half a meter。In my first method， let's have these two bipeds alternate。

 leaping over one another three times， so we'll have back the bunny。Well， leapfrog。1 m。

Then we'll click on the Cheshire cat。To leap frog。Half a meter。Then we can select the bunny。

To leap frog。1 m。And then finally， we can select the Cheshire cat to leapfrog half a meter。Now。

 when we go ahead and run the world， we can see the animals leapfrogging one another at exactly the right height。

There goes the bunny。And the cat。And the bunny。And the cat。Great。One last modification。

 after the first pair of calls to leapfrog， we can change the camera to move and orient to the left view。

So let's select。This camera。And select after the second leapfrog。

 we can ask it to move and orient to the left view。And after the second pair of calls。

 we can ask the camera to move and orient to the right view。

This gives us three interesting views of the leapfrog animation， and when we run。

 we can see the first leapfrog as we have set up before。

And then the camera is going to change as a view from behind from the left。

As they hop over one another。And then the camera is going to view from the right and see the other direction as the animals leapfrog over one another。

In summary， the level at which you create a procedure is significant。

 creating a procedure at the bunny level allows all bunnies to hop。However。

 creating a procedure at the bipedD level allows all bipeds to leap。

