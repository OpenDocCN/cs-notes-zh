# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p128 128_08_04_场景切换演示.zh_en -BV1QrB6BcEWW_p128-

![](img/688d93a6d32dae8bc413d6e998a0a2f4_0.png)

Let's take a look at the partially built project We see all of the objects in the scene。

If we go into the setup scene mode。We can have the camera move to the camera marker。

Let's click on camera markers。And let's say let's look at the island。

Here we can see that everything is set up for the island， except the changing of the ground color。

We can do likewise for the turtles in the desert。And the scene with the queen。

We could also look at the top view。If we go here。And from here， we can drag around。Or actually。

 move up further。We can also drag the ground around and we can see there is the scene with a tiger。

Over here is the scene with the island。And there's the turtles and if we scroll down a little bit。

There's the queen and the other Alice characters。Let's go back to the camera starting position。

Let's also move the camera back to the camera starting position。

And now let's click on Edit code so that we can look at some of the prebuilt code。

If we click on initialize event listeners。We can see several events already created。

 I'm going to scroll to the top。The key press event is already codeed to allow the dog to move。

When the game player presses the left arrow key， the dog moves left。The right arrow key。

 the dog moves right and the up arrow key， the dog moves forward。We also have an event。Here。

Where the dog collides with each of the gates or with the tiger。However。

If we click on process left gate collision， let's try and find that。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_2.png)

Over here。 oh so actually it's right here。 process left gate collision。

 if we click on the edit for that。We'll see that no code is yet written for this procedure。

 We'll need to write all of these procedures， along with my first method。But before we start coding。

 we still need to add the black rectangle， which will blacken the scene when we need to change scenes。

 So let's go back up into setup scene。And we're going to add a billboard。

 so look for the Shapes text tab。And then let's drag in a billboard。

We're going to set the back paint to black。And we're going to name it。Camera。😔，Blocker。

And then click， O。Next。Let's issue a one shot to move and orient the camera blocker to the camera。

So one shot procedure。Move and orient2。The camera。Oh， there it goes。 It flew right past us。

Let's issue additional one shot instructions to move the camera blocker forward by half a unit。Move。

We're going to try move forward。Half a unit。Now， we can see it。Next。

 we're going to have it move down half a unit。Move。😔，down。😔，Half a unit。Now， all we can see is black。

 That is perfect， but we're going to issue one last one shot to move the camera blocker up out of the way。

 so let's move it up two units。Move。😔，up。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_4.png)

Two units。Finally， let's change the camera blocker's vehicle to be the camera。

So the camera blocker will move when the camera moves。Lgu。😔，To camera。

Now we're ready to start coding we're going to click on Edit code。Let's start with my first method。

 so I'm going to have to click on my first method。All we need to do here is to initialize the initial scene。

 Let's first put in a do order。Let's do several instructions together。

We need to make the Adelaide bust invisible as the Adelaide bust becoming visible is the prize when the player wins。

Let's go ahead and do that。 We have to find the Adelaide bust， so it's a prop。And then here it is。

Now， we need to。Find the opacity。 Here it is。So， let's。Drag this in。To hear。And set it to zero。

 Now this is going to be one of several commands that are going to become invisible。

 so let's add in a do together。So that all of these will happen at the same time。

So set the Adelaide bus to0， the opacity to0。Let's set the duration。Of this， also。To0。

 so it happens instantly。Maao。We also need to make the ruby。

 the Coke bottle and the armbone also invisible， as the player has yet to successfully win those prizes。

We can copy this instruction to the clipboard。And then， drag it in。

And now we can pick one of those prizes。Let's see。 the ruby。And now the ruby's set invisible。

 Let's keep doing this。Copy the clipboard。Now we'll change the ruby。To the cola bottle。

Let's do it one more time。And we'll drag over。😔，And change the cola bottle。To the armbone。Finally。

 we should do the same for the back button as this button will be used to get the game player back to the initial scene。

And the player starts in the initial scene。The back button is actually a sphere whose opacity has been set to 0。

7 to make it possible to see into the sphere， along with a 3D text that says back。Thus。

 we need to set both the sphere and the 3D text named back text to having opacity zero。

So let's again copy this to the clipboard。And drag it over。And this time， will set it the arm bone 2。

The sphere。And then let's copy that。And drag one more over。And let's change this sphere。

To the bag text。Now we have everything that we need set to invisible when the game starts。

After we've made everything invisible， let's have the tiger say that the player needs to bring the tiger a bottle of cola and a bone。

So， find the tiger。Have the tiger say。This is after the do together。Please bring me a bottle of cola。

 and a bone。To win。The price。Okay。That's kind of long。 So let's make that duration two seconds。

And last， let's have the Dalmatian tell the gameplay how to move and interact with the objects in the game。

Let's find the Dalmatian。And drag over a say。Now it could say something like this。

Use the arrow keys to move me。If you move me to the gate。I go through it。Move me to collide。

Into things。 and some of them。We'll speak to you。That's also kind of long。

 so let's change the duration of that。Also， to2 seconds。

Let's run the project to see that everything gets set up。So if we click Run。Oh。😮。

Lots of things are invisible。And the tiger speaks and the Dalmatian speaks， that looks great。

Let's close the world。We're going to require that the player first get the ruby before getting the bottle of Coa。

The left gate will be how the player gets the cola。

The centergate will be how the player gets the arm bone and the right gate will be how the player gets the ruby。

Let's start by coding the procedure to process the collision with the left gate。We click on this。

And then edit， process left gate collision。I actually already happened to have it up。

So if we click on it， there it is。All we'll need to do here is to get the camera and dog to the island。

The actual gameplay where the Dalmatian will get the cola bottle upon colliding with the monkey will occur via the events。

We'll need to do several things in order， so let's go ahead and drag in a do an order。First。

 let's start by having the camera blocker move down two units。So， we can pick。The camera blocker。

 it's right here。And we're going to have it move down。Two units。

Now this is so it will make everything dark。Now， let's have the camera move and orient to viewing Island。

So let's drag over， move and orient2。And let's select the viewing island right here。

 so that will change。The view。And then we also need to have the dog move and orient to the dog on the island marker。

 so let's change this to the dog。And have the dog。Move and orient2。😔，The dog。😔，On the island。

 there it is right there。We also need to make the back button visible so that the game player can now click on it to get back to the initial scene after they get the Collobo。

So let's add code to set the opacity of the spear to be 0。7。Let's find the sphere。There it is。

And let's change its opacity。Next to be 07。And then let's click on the back text。Which is。

Right up here。And let's change its opacity， it should be one。So let's change the back tax。

 which is behind the sphere， we want it to be all the way on， so let's change that to one。Finally。

 let's move the camera blocker back up to units， I'm just going to copy this command。

And drag it down over here。And let's have the camera blocker move back up out of the way。Okay。

Let's run the project to try it out。Okay， we see the instructions。

And now let's steer the Dalmatian over into the left gate。OhOh， oh， no。

We didn't change to the island scene。 we have a problem， okay， let's go look at our code。

So let's see what happens。The camera didn't move over to the island scene。hI see。

 So we have the camera blocker moved down and then we're supposed to have the camera move in orient to the viewing island。

 but I didn't change that to the camera。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_6.png)

So let's change this second line to have the camera move orient to。That's a big error。 All right。

 let's run the world again。Okay， we here see the instructions。

And now we have to steer the Dalmatian into the left gate。Okay。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_8.png)

Oh， this is taking too long。A oh。So we got to the island。But it's not water。 It's grass。

We can fix that。All right， let's close the world。So the first problem was it took a long time for the scene to be black。

We can fix that。Let's put all the move and orient to commands into a single do together。

So they all happen at the same time。 So first， the kmber blocker comes down。

 And then while it's dark， we change everything。And then the camera blocker moves back up。

But the more serious problem is the ground isn't blue when we change to the island。

So into the do together， we need to change the ground。So find the grounds。

And you can see there's a set paint， drag that into the dew together。

And let's change it to the ocean。Okay， let's run the project again。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_10.png)

We see the instructions。And now we steer the Dalmatian。Into the gate。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_12.png)

That didn't take as long。 and we have the ocean there。 That looks much better。Let's close the window。

We still need to add the event processing for this part of the adventure。

We're just going to add a collision between the dog and the monkey。

If the ruby is visible and the dog has completed the task to get the ruby。

 the monkey will give the dog the bottle of cola by making its opacity 1。If not。

 the monkey will tell the dog that the dog first needs to get the ruby。

Let's click on initialized event listeners。And add a new collision， start listener。

So it'll be under position orientation。And then select add Col Start listener。

You'll see that we have to also select a custom array for set A。And a custom array for set B。

The first set will consist of just the Dalmatation， so let's add in the Dalmatation。And click OK。

And then the second customer array will be just the golden monkey。 So add the golden monkey。

 There it is。And click， O。For the code， we only need an if statement。

So let's drag that in and select true。We're going to replace the true first。

 actually let's scroll up when it gets down to the bottom， we can see it better here。

Now click on the true and we're going to pick the relational decimbel number。And we're going to do。

 we're going。We're going to compare equals。And we're going to select one twice。1 and one。

Now we're going to click on props and find the Ruy。Let's see。 There's the ruby。

And now we want to look at the ruby's opacity， so we're going to click on functions and drag over the opacity。

And we're asking if the ruby's opacity is equal to one， which means it's visible。

So if the ruby is visible， we can do two things in order。First， we have the golden monkey say。

 here is a cola bottle。So find the golden monkey。There it is。And we'll have it say。

Here is a cola bottle。Next， we can just make the collobo visible。So find under props。

There's the cola bottle whoops。There's the cola bottle。And。Will'll drag over the。Change the opacity。

Tun。For the else case， let's have the golden monkey tell the dog that the ruby is needed first。

I'm going to drag this down a little bit。And we're going to have to drag over another golden monkey。

 say。And custom text string。You need to get the ruby。Before you can。Get the cola bottle。From me。Okay。

 that looks good。 Let's set the duration to2 seconds。And now， let's run the project。Okay。

 so we're going to steer the Dalmatian in the left gate。

And now we're going to steer the Dalmatian into the gold monkey。 And he says。

 you need to get the ruby first。 Okay， that's great。😊，Let's close that。

And now let's next process the synergate。Since the code is going to be similar to the left gate。

Let's first go back to process Left gate collision。

And let's click and copy all of the code the whole do in order。So， copy the clipboard。

And now we can go to， let's go to scene。Or rather， to this。Here。And then， let's open up。

The process center gate Col procedure by clicking on the editit button。

And now let's go to the clipboard and drag all that code in。We need to make some changes。

We need to have the camera move and orient to a different place。

 How about the viewing turtles and desert？And then we need to change the Dalmatian to move to。

The dog。In the desert。And what else do we need to do， We need to change the paint。

 So the paint should change to desert， which is up here。At this stage。

 you might be wondering why don't we just have one procedure with three parameters？

1 for where to move the camera， one for where to move the dog and one for the pain of the ground。

 The reason why is that if this were a real multi scene game。

 there would likely be a lot of additional and customized setup up that would be needed。

We'll soon see why。When we wish to have the players successfully play a different game in each of the three scenes。

 there will be specialized customized setup required for each game。Anyway。

 this should complete the processing of the setup for the middle gate。

 We also need to add an event for the dog colliding with either of the turtles。

Let's go to initialize event， listeners。And at another collision event。So down here。Again。

 position orientation， and then select Add Col Start listener。Again。

 we're going to have a custom array for set A and a custom array for set B。This time。

 the Dalmatian is in set A， so add the Dalmatian。And click， Ok。

And both of the turtles will be in set B。 So add in the desert tortoise and also add in。

The desert towardtoise， too。And then you can click， okay。

If there's a collision between the Dalmatian and one of the tortoises， we'll do two things。First。

 we'll have the appropriate turtle say， here is a bone。So we need an if statement。

Sragon and if statement。And select true。And we'll drag this back up。

We compare for S things to test equality。So we'll click on the true。

And we're going to compare relational S thing， we want to know if two objects are equal。

And then we're just going to pick the ground for the first one。That's all the way at the top。

There it is。And for the second one， we can select the desert tortoise。Therest tortoise。 there it is。

We then are going to drag the event get S thing from set B that set B is where the turtles are。

 so we're going to drag that over the first part， which says the ground。

So now it says if the thing we clicked on from set B is the desert tortoise。

That's what we want it to say。Now， if we collide on the desert tortoise。

Then we want the desert tortoise to say something。So let's click on the desertert tortoise and drag over a say。

And he's going to say， here is a b。Here is a bone。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_14.png)

And now to have desert towardto us to issue a say for the elses case。

 we can just copy the a code to the clipboard。Let's copy it。And drag it in。

And we'll just change desert tortoise to desert tortoise too。After the if statement has completed。

 we need to set the opacity of the bone to be visible。So find the bone， this would be under。Props。

There's the arm bone。Let's look for the opacity set opacity procedure here it is。

And this goes after the if statement。And we're going set it to one。We can't see it。

 but let's make sure it's there。Now we can see it comes after the of statement if the arm bones opacity is set to one。

Finally， we need to write the code for process right gate collision。

We'll start by copying the code from process left gate collision to the clipboard。

So click on process left gate Col。Let's make a copy of the whole do in order。Copy the clipboard。

Then let's go to this。The scene。And open up。Process， right gate collision。There it is。

And then let's drag in all the code。Andto here。Now we have to make some changes again。

Let's have the camera move and orient to。Viewing Alice characters， that's worth the queen。

Let's have the dog change to be the dog in Alice。That's the object marker in that scene。

And then the last thing is we need to change the paint。So let's change the ocean。To the forest floor。

Let's add another collision event。This time， we only want to process the Dalmatian colliding with the pumpkin head。

So， select。A。Position orientation， and then add Col， start listener。Again。

 we have to pick both the set A custom array and set B custom array。So for the first one。

 we're going to have the Dalmatian at it。There it is。

And click OK and for set B will add just the pumpkin head。Who is somewhere in here。 There it is。

And click， OK。Now， when the Dalmatian collides with a pumpkin head。

We want two things to happen in order。 First， we'll have the pumpkin head say， I grant you a ruby。So。

 find the pumpkin head。And drag it a say。And have him say。I grant you a ruby。Next。

 we're go want to make the ruby appear， so select prop。Down here， and there's the ruby。

And then look for set opacity。And make the ruby appear。1。0Again。

 I'm going to drag it down so you can see all of the code for this collision event。

Let's test our game。Okay， let's steer the Dalmatian into the centergate when he stops talking。

 there we go。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_16.png)

Okay。Okay， so now we can choose to steer the dalmatation into either turtle。

 He says here's a bone and the bone appears。 So now let's click on the back button。O0。

Nothing happens。Oh， we forgot to put the code for processing the back button。 Let's do that now。

So let's get out of this。Let's again start by clicking on process left gate collision。

 that procedure and copy all the code the whole do an order。Copy the clipboard。

And then let's go to scene。And look， we have a procedure called process click on back。

Click on the edit beside that and it will appear。And now， let's drag all the code。

Into this procedure。When we click on the back button。

 we want to go back to the original starting scene。

So we're going to have to change a couple of things in here。The camera should now move an orient。

 too。The camera starting position。 There it is。And the Dalmatian should now move an orient to the dog starting position。

We also have to change the sphere and the back text because we want them invisible in the original scene。

 so let's set both of these to0。Said opacity to 0。 And then finally， we have the ground。

 Let's change the ocean。To grass， there it is。We also have to do one more thing because we're moving the dog back to the original scene。

 it may be the case that moving the dog back to its starting position will cause it to collide with the tiger。

To avoid this from happening immediately after lowering the camera blocker。

 we're going to add an instruction for the tiger to move down 10 units。So let's find the tiger。

And have it move。down。10 units。😔，And we're going to make this happen really fast like instantly。

 so let's set the duration to zero。Nowao。Immediately before raising the camera blocker。

 we need to move the tiger back up 10 units again with duration0。

 so I'm just going to copy the move down to the clipboard。

And then I'm going to drag it here right after the do together。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_18.png)

And we'll have the tiger move right back up instantly。

This will effectively avoid an accidental collision between the Dalmatian and the tiger。

 because if they collide， the tiger might say something。 and we don't want that to happen。

Let's try this out by running the project。Okay， so we need to go find some things。

 so let's go straight。Okay， so we're going to collide with a turtle， he says here's a bone。

We click the back button。 there it goes。Now we have a bone， let's go over here。And here。

We collide with the monkey。He says， oh， you need to get a ruby first。Do we click on the back button。

And we have to come to the third gate over here。And now。If you notice what we clide with a queen。

 nothing happens， let's try another character。We tried the pumpkin head， and he says。

 I grant your ruby， awesome。😊，Let's go back。Now we have a ruby so we can come back over here。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_20.png)

And now， if we ask or just collide with the monkey， he says， here's a cola bottle。

 so now we have all three of the items。Let's go back。Great， we can pick up all three the items。😊。

We still have some code to do。The last thing we need to do is process a collision with the tiger。

We can edit the same procedure， process tiger collision， so let's in this。And， let's click on。This。

And here we have a procedure called process tiger Col， so click on the edit button beside it。

We need to build an if statement to check if the coloboal opacity is one and the arm bones opacity is one。

 which means you've collected both of the items you need to。So let's add in a do an order。

And then let's add in an if statement。Inside， do an order。So。If。Will select true first。

If we have both the cola bottle and the arm bone。How do we say that。

 so we're going to first have both true and true because we have to check two things。

For the first one， we want to know if we have， let's say the arm bone。

 So let's do relational decimal number。And let's compare if two things are equal。

 and let's just pick one and one。And since we're going to do the same thing for the second one。

 I'm going to go ahead and do that too。So let's go ahead and do again relational decimal number。

 compare if two things are equal and just select1 and1。Nao。Let's。Fine the coke bottle。

Where's the coat it's under props。There's the Coke bottle。Let's check its opacity。

We need to look at its function to check it。Here is the Coke bottle gitopacity。

So we'll see if the Coke bottle's opacity is equal to one。

And then let's just drag it over again into the second comparison。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_22.png)

Over here。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_24.png)

Right there。We put in the wrong place。That happens sometimes in Alice， changed us back to one。

Let's try and drag it over again as Coke bundle opacity into this third item here， this one here。



![](img/688d93a6d32dae8bc413d6e998a0a2f4_26.png)

![](img/688d93a6d32dae8bc413d6e998a0a2f4_27.png)

And we want to change the Coke bottle into the。Bone or the arm bone right there。

 So now we're asking if the colabos opacity is one and the arm bone opacity is one。

Then we want to do a couple of things。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_29.png)

We're going to first add in a do together。We want the tiger to disappear。

 and we want the Adelaide bust to appear because that's the price。So， let's find the tiger。

And click on Pro。And look for setting the opacity right here。

And drag that in for the tiger and make the tiger invisible， so set it to zero。

Then just drag it in again。And this time， set it to one。And change the tiger in the second one，2。

The Adelaide bus， which is all the way near the bottom。Okay。

 so if we have the two items we're supposed to have。The tiger becomes invisible。

 and the Adelaide bust becomes visible。Now we have to do one more thing。

 let's have the Adelaide bust， let's find it。Under props。Let's have it say， you win。

This would be right after the do together。Yuwen。😔，And click， Ok。For the else case。

 we should have the tiger say， you must bring me a bone in a coke bottle。So drag over the say。

 and this time this goes in the alts。And say。You must bring me a。Bone and a cola bottle。Click， O。

And I actually need to make the Adelaide bus change that into the tiger。

So the tiger says you must bring me a bone and a cola bottle。I think that's it。

 so let's play the game one more time。Okay， we have instructions。All right。

 we're going to go this way first。 as should we just go into the tiger。 And he says。

 you must bring me a bone in a cola bottle。 Good。 so let's go over here。

And we're going to go into here。We go into the pumpkin head。He says， I grant you a ruby。

 we have a ruby。Let's go back。Now we can come over here。And we can see the monkey。He says。

 here's a coo bottle。We still need a bone。So let's go back。Now we go in this gate。

And now let's go to the other turtle this time。He says here's a bone。 so they both both turtles work。

And now we click on the back button。

![](img/688d93a6d32dae8bc413d6e998a0a2f4_31.png)

And now this time we go to the tiger。And he says， oh， he disappears。 and the bus says you win。

 That's exciting。 You can now play your first really big game。 Isn't that exciting。😊。

