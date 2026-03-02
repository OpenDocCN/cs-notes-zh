# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p35 035_03_03_摄像机控制.zh_en -BV1QrB6BcEWW_p35-

![](img/e86e55e48fc8ced7acf8d20208c1debe_0.png)

Sometimes you're watching a scene in a movie。 Maybe the scene is two people talking。 Suddenly。

 there's a loud noise。 likely， the camera will turn towards the direction of the sound and then even move closer so you can see what caused that sound。

😊，Then the camera might move to an up close view of the two people so you can see their reaction to what caused the sound。

The scene the camera is looking at is called a camera viewpoint。In this lesson。

 you will learn how to set up such camera viewpoints so you can move the camera around to different camera viewpoints in an animation。

You will learn about Alice's special built in two dimensional camera viewpoints in the scene setup that you can use while you're setting up a scene to make sure the objects in your world are placed exactly where you want them。

You will learn several different ways to move or turn the camera to look at another location in your world。

 either by one shot which you've used before or by using the camera controls。

Once you have the camera and a location you like， you can save that location with a camera marker。

Then you can move the camera to that save location any time during the setup of the world。

 or when you're running your world。We will look at an example world that has already set up three different camera viewpoints for its animation。

This is the starting camera review for the world。Let us see which animals are in this world。

You can see a panda。 There's an obsceneian cat to the panda's left and a falcon above the panda。Now。

 look at the side view with the camera looking at the panda's right side。

 You can see that there's a bunny hiding behind the panda。

 This is why this side view is so important。 You would not know theres a bunny hiding behind the panda if we did not have this view。

You can also see the obsceian cat is partially obscured。Now， look at a closer view of the falcon。

 The camera is so close that it's the only animal that you can see。

You might want a close up of a character in your story as a special effect if they're doing or saying something important that you want to focus on。

Before learning how to set up these views， we will first look at Alice's 2D built in views。

In the setup scene view， Alice gives you five built in views to help you in positioning the objects in your world。

 You can click on the arrow to switch between the different views。😊，The first view。

 the starting camera view。Is the view you get when you start scene setup and the same view you get before you move into scene setup。

The layout scene view gives you a view from above the camera。 so you can see most of the world。

 but note that we could not see the bunny in either of these two views。

Alison gives you three two dimensional built in views。

 That means that the objects in these 2D views can only move in four directions， not6。

One view is the top view。 Typically in this view。 You'll see the camera。 That is the black object。

 We're looking at it from above。 The top view is stationary。

 but the ground and objects can move together。 We can click on the ground and pull it down to look for the animals。

Now， you can see the camera pointing directly at the animals。

 It's difficult to see the bunny because it is below the falcon。

We can also zoom in or zoom out from the view。Here's a closer view that shows the two dimensional directions that the cat can move。

 The cat can move only in four directions to its left and right and to its forward and backward。

It cannot move to its up or down。This view may help you in moving animals around on the ground to a location that you want。

Here is the two dimensional built in side view of the animals。

 Not as the thin line that is the ground。 With this view。

 you can make sure that the animals are standing on the ground and not slightly above or below it。

This view is stationary。 If you click and drag the background color。

 the animals in the ground move together just as they did in the top view。

If you click on an animal such as the panda， you can see its axis to see how it can move by itself。

It can only move its up and down direction and its front and back direction。

 It cannot move to its left or right。The last two dimensional view is a front view。

 This view is also stationary。 If you click and drag on the background color。

 the ground and the animals move together。The cat is clicked on。 you can see how it can move。

 It can only move to its left and right and to its up and down。 It cannot move forward or backward。

These built in views should help in getting the objects exactly where you want them when your program starts。

One way to move the camera is to use the purple arrow camera controls from the starting camera view。

 you should see all of these arrows。 The straight arrows are used for moving the camera。

 and the curved arrows are used for turning the camera。Look at the leftmost group of arrows。

 Notice that these are all straight arrows。 These arrows are used for moving the camera。

 The up and down arrows move the camera up and down。

 and the left and right arrows move the camera left and right。Look at the middle group of arrows。

 notice that two of them are straight and will be used to move the camera。

 and two of them are curved and will use to turn the camera。

The two straight arrows that point up and down are used to move the camera forward and backward。

 the two curved arrows that are used to turn， not move。The camera to the left and the right。

Look at the right group of arrows。 Notice that both of these errors are curved。

 These errors are used to turn the camera forward and backward。

 and you can use these camera controls to move and turn the camera until you get a camera view that you would like to use in your animation。

There's another way to move the camera。 You can use one shots。

 You have used one shots before to move objects around during setup。

You can use one shot the same way to move or turn the camera shown here are several instructions you can use with a camera such as moveve and turn。

 Now here's a tip。The starting position of the camera is always slightly turned forward before moving or turning the camera。

 make it upright using the orient to upright instruction。 Then if you move the camera forward。

 it will not go into the ground。You might want to use a combination of one shots and camera controls to move the camera to another viewpoint in your world。

Now that you know how to move the camera around in your world。

 you might want to say particular location so you could move the camera to that location when your world is playing。

A camera marker is a special object that can remember a camera location in your world。

 You can create a camera marker by placing the camera in a location you want to save and then dropping a camera marker on that location。

😊，In a scene set after selecting the camera， you will see an option for camera markers and a button to add a camera marker。

Clicking on add camera marker creates a camera marker that looks just like the camera object。

 but it's a different color。You should name the camera marker a meaningful name。

After adding a camera marker， you can see I named it camera start view， and it's the color red。

I'll move the camera to other locations and drop two more camera markers。

Known as they all have different colors and they all have meaningful names。

These markers appear in the scene setup view so you can see where they are。

 but will not appear when you are running a world。In this 2D side view。

 you can see the magenta camera that's looking at a close up of the falcon。 It's right at its face。😊。

You can also see the green camera that is set to give you a side view of the animals。

Camera markers have two control buttons。The left button looks just like the black camera pointing to a colorful camera。

 and it's used for moving the camera to a camera marker。

That will be useful while setting up objects or moving the camera to preset locations during an animation。

The right button looks like a colorful camera pointing to a black camera。

 and it's used for moving the camera marker to the camera。

And it's useful if you decide you need to reset a camera marker to a different location。

To use the camera control buttons， you must first click on the name of the camera marker and then the button。

In this picture， I have clicked on the magenta camera marker called Cam Falcon View。When I do so。

 the colorful camera in the buttons become magenta。

Then I click on the left button and the camera moves to that camera marker。

If I decide I want this camera marker to be moved forward just a little。

 I move the camera forward to a position I like and then click on the right button above and the camera marker will move to that camera and now is reset to this new position。

You can also move the camera to the camera marker using a one shot with the instruction。

 moveve and Orient2 shown here。Then the camera will move to the camera marker and also turn to face the same direction as a camera marker。

Here are a few tips to help you with a camera marker。First。

 you should always drop a camera marker before moving the camera。

 Call it something like camera start view。The location of the starting camera and a new Alice world is special。

 It's representing the center of the Alice world。😊。

It is the location an object will be placed if you click on the object to add it into the world。

You do not want to lose this location。In using the camera buttons， if you click on the wrong button。

 then click on Edit Undo。Undo is your friend。 It undoes the previous command。

Sometimes the camera markers ob an object in a view。

 making it difficult to click on the object and move it。If this happens。

 you can always use a one shot to move the object。It is better to set up all the objects and then then add the camera markers。

Once you have camera markers set up， you can move the camera to them during your animation。

You would use the moveve and Orient to instruction and select the camera marker that you want to move to。

This instruction moves the camera to the camera marker and also orients the camera to face in the same direction as the camera marker。

You can have the camera move slow or fast to its new location by changing the duration。

 A duration of5， for example， would take5 seconds for the camera to move to its new location。😊。

You have learned a lot about the camera， how to move it and how to set up camera markers to say viewpoints。

 You have also learned how to set up a scene by moving objects choosing Alice's 2D views。

Enjoy creating animations with different camera viewpoints。😊。



![](img/e86e55e48fc8ced7acf8d20208c1debe_2.png)