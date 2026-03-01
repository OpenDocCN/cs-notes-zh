# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p20 020_02_04_故事板实现.zh_en -BV1QrB6BcEWW_p20-

![](img/ba24090510c801175fc7707712faa671_0.png)

Let's implement the story of Amy the astronaut， who sees an alien on the moon。First。

 let's set up the scene。Start a new Alice project and select the moon for the ground。And click， O。

We will need to add several objects to the world。Click on setup up scene。And then click onBped Class。

We will need to make the astronaut with the character builder。Click on female adult。

Scroll down the outfits。You'll need to go all the way down to the bottom。

There you will see the space suit。Note， not all the characters have a spacesuit。

 Only male and female adults have the spacesuit。 I guess kids are not allowed to go to the moon yet。

When you click， O。Give your astronaut a name。I'm giving mine the name， Amy。

Push Amy back a little and put her on the left side。Then scroll over。

 and you should see an alien with a green face。 Actually， I see the alien there。

 Click and drag the alien onto the right side and push the alien back a little。

Let's add in a spaceship。Click on all classes。And then click on the transportport Class folder。

And then select aircraftcraft classes。Add in a UfoO。Are renamed mine spacecraft。Click， O。

It's really big， click on it and push it back far。Not too far。

Now we need a rock for the alien to hide behind， click on the search gallery tab。And type in rock。

Add in the rocky outcrop， small。This one。Click， O。It's actually pretty big。

 so you could resize it just a little bit。 Click on the resize button。

And pull it down just a little bit， not very much。Then make sure you click on the default button。

Push the rock back。Let's do a one shot to have the alien turn to face Amy。Select the alien。One shot。

Turn the face。😔，Ay。Then move the alien behind the rock。

Maybe with just a sliver of its green face showing。

I'm going to adjust the camera just a little bit with the leftmost set of purple arrows。

I'll click a few times on the up arrow。That just makes the camera look down on all the objects。

 You will learn more about camera control in another lesson。We are ready to implement the storyboard。

Click on editit code to go to the code editor。First。

 let's drag up a do an order from the bottom of the window。

All of our code will go in this do an order。Why do this by putting all the code into a do an order。

 it will be easier to copy and paste all the code together if we want to move the code somewhere else。

It is also easier to disable all the code if we wanted to。

It also makes it clear about our intentions that all the code will be done one instruction after the other。

We will talk more about cutting and pasting code and disabling code in later lessons。

Let's add in a comment。An alien appears。And gets Amy's attention。

Let's have the alien move and speak at the same time。Drag in a do together。

We want the alien to move out from behind the rock。The alien is facing the rock。

 so have it move to its left。2 units。Put the move in the do together。Move left。Cu。

Then let's have the alien say something。Who knows what aliens would say？Drg in the say。

Select custom text string。 I'll have mine say。Sliy。😔，Tove。Okay。Click on Run to see what happens。Yeah。

 that looks good。 Let's make the run window bigger。



![](img/ba24090510c801175fc7707712faa671_2.png)

I'll drag it up here and then grab the corner and make it a lot bigger。



![](img/ba24090510c801175fc7707712faa671_4.png)

Be sure to close the run window after you have watched it。

If you go back to the code editor without closing the run window。

 you will not be able to do anything in Alice。Now let's have Amy turn to face the alien。

This should happen after the do together。Select Amy。Drag in the turn to face into the do in order。

 but below the do together。The alien。Let's add in another comment。Right after the turn to face。

It should say。Amy is。Terrified。And returns to the ship。Now have Amy say something。Like。😔，Oh。あ。

And then have Amy turn to face the spacecraft using the turn to face instruction。

Click on run to see what happens。The alien comes out， she turns and faces it， she says， ah。

And faces the spacecraft。Perfect。Close the run window。Now， we need several things to happen at once。

 As Amy moves to the ship， let's have the door open and the alien turn the same direction。

 Put in a de together。Have Amy moved to the ship using the move to instruction。Amy move to。😔。

Spacecraft。At the same time， we need the door to open。

 change the object to spacecraft and follow the black arrow。

You will see that the spacecraft actually has two doors， a left door， and a right door。

 we can have both of them open。Choose the left door。And have it turned to its left。

We just want it to turn a little bit。 so let's do it。0。05。Click， O。Then select the spacecraft。

The right door。Also， have that turn。To its right。Also， just a little bit。0。05。One more thing。

 The alien is watching Amy as she heads to the ship， so select the alien。

 have it turn to its right a quarter。Select the alien。😔，Turn。😔，To its right， about a quarter。

Click on run。The alien comes out， she turns。She moved to the spaceship just as the doors opened and also noticed the alien turned and watched her move to the ship。

 That looks great。Let's close the window。 Now， close both doors at the same time。

 Put in a do together。Have the left door。Turn right。😔，The same amount as before， which would be 0。05。

Then select the right door。And have it also turn。This time， to its left。

Which is the opposite of what it did before。Also， the same amount，0。05。

Now this spacecraft should rock a little before taking off。Let's have it roll， just a tiny bit。First。

 add in a comment。Spacecraft takes off。Then drag in the spacecraft roll instruction。

 make sure you change this to spacecraft。Have it， roll。😔，Just a tiny bit。

Let's have it roll to the left。02。😔，0。02。Then have it roll the other way back to where it was。

 plus a little more， so roll right。Rong。Right。0。04。Then have it roll back to it upright position。

 so roll left。Roole left。😔，0。02。Click， Ok。To have this spacecraft take off。

 we need it to move up and move forward at the same time， let's add in a do together。

Dragon spacecraft。 Mo up。Let's say five units。5。Then， dragon spacecraft move。Forward。And this time。

 let's pick a big amount。 let's say 20。We also want the alien to watch the spacecraft take off。

 so have the alien turn to its left a quarter。Select the alien。And turn。To its left。😔，A quarter。

Click on run， and let's watch it。She goes to the spaceship， the doors close， Oh。

 that rocking looks good。Oh oh，What happened。The spacecraft took off without Amy。But in fact。

 Alice did exactly what we told it to do。We told it to move the spacecraft。

 We didn't tell Alice to move Amy。Let's also add code to move Amy。Close the run window。In the same。

 do together。Have Amy。😔，Let's find Amy。Let's have her move the same amount。 So have her move up 5。

And have her。Move forward。20。Let's click on Run and see what happens。She moves to the spacecraft。

 the doors close， the rocking looks good， and now the spacecraft takes off。Ah， do you see Amy。

 she's floating in the air？What happened？ Amy moved。

 but she is way out in space behind the spacecraft。Think about it。When Amy moved to the spacecraft。

 she was facing the opposite direction in the spacecraft。

 so her forward direction goes behind the spacecraft。We could fix this several ways。

One way is to have Amy move backward when the space ship moves forward， but that may be confusing。

Another way is to turn Amy around。Let's do that when the doors are closing。Close the run window。

I'm going to scroll my code down a little bit。Find the do together where the two doors close。

Have Amy turn to face the camera then。So turn to face in this same do together when the doors are closing。

Turn to face the camera。Now， click on run and see what happens。All right， she screams。

 she goes to the spaceship。The spaceship rocks。It takes off and I don't see Amy floating anywhere。

That works。It also looks nice when she turns around to look out as the doors close。😊，Now。

 for the very last part。Let's add a comment。First， close the run window。

Let's add a comment at the bottom。

![](img/ba24090510c801175fc7707712faa671_6.png)

Not in the do together。You may have to scroll down to see it。The alien is sad。

Then have the aliens say。Select alien。😔，Sai。😔，Don't you want to play。To make the alien look sad。

 let's have it turn its head down。Click on the alien。And follow the little black arrow。Then。

 look for get head。Select that。Have the alien's head turn forward a little bit。Turn。😔。

So I can't quite get it in there， so I'm going to have to scroll down。There we go。

Have the alien's head turn。😔，Forward。Just a tiny bit。0。125。That should be it for our story。

Click on run。The alien comes out， She turns around。She heads to the spaceship。

The spaceship is taking off。The alien says， don't you want to play， And his head goes down。

 he does look sad。That looks fantastic。 You have learned how to design a story board and turn that story board into code to create an animation in Alice。

😊。