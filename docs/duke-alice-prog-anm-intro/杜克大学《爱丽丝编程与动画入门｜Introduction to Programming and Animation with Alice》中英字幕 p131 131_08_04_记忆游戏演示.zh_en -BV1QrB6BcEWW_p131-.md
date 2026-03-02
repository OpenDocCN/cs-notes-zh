# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p131 131_08_04_记忆游戏演示.zh_en -BV1QrB6BcEWW_p131-

![](img/c03bea534ea6fec7c12e1a93dfa4f040_0.png)

Let's take a look at what has been set up for us。If we go ahead and click on the scene tab。

We'll see that the only objects in the scene are the seven bunnies。

We see that there has been an array called Bunnies created and that has been filled with the seven bunnies in the order。

 Bunny， Bunny 2， Bunny 3， Bunny4， Bunny 5， Bunny6， and Bunny7。

We also note that there is a whole number variable named index， which has been set to zero。

Other than that， nothing seems to have been done。As noted previously。

 there are going to be three parts to the playing of this game。

Let's start by tackling the first part， namely the mixing up of the array of bunnies。

We can start by creating a scene level swap procedure。So let's go ahead and actually。

 we can just click on the add scene procedure right here。And let's call it， swap。To start。

 we're going to need to do a few things in order， so let's start by dragging in a do in order tile。

We need to generate two different random numbers between0 and 6。

The reason they need to be different is that it does not make sense to swap the bunny located in position 4 of the array with the bunny located in position 4 of the array。

Nothing would happen。Let's create a whole number variable， so we'll drag in the variable。

We'll specify that it's to be a whole number。And we'll go ahead and we'll call it index1。

We'll set it。 We need to give it an initial value， which we can set to be0。

 We actually want it to be a random number， but we have to do this in a two step process。

 So we'll click on the OK。And then we can change from the0。 We can click on random。

 And we'd say we'd like a random number from 0 up to but excluding。 We'd like the size of the array。

 but we can't access this。 So let's put in one as a placeholder。And now finally。

 we can click on the drop down next to the one and change that to this bun's do length。

 which in this case is going to be7， so that this will generate a random number from0 up to。

 but excluding seven， namely a random number from 0 through6。

Choosing this dot bunnies dot length is better than choosing the number 7。

 The reason is that if we later choose to add or remove bunnies from our array。

 this dot bunnies dot length would still contain how many bunnies are in the array。

 whereasas we need to remember to change the number 7 to the number of bunnies in our array once we change the array。

Let's go ahead and create a second random number， whole number。

 so let's go ahead and drag in a random whole number。Again。

 we'll specify that it's going to be a whole number and this one we'll call it index2。

And we'll again set index2 to a random number from0 up to but not including7， so again。

 we'll initially set it to be0。Click on the OK。Then we'll change from the zero to a random number。

 from zero up to， but excluding， and again we'll initially put one as a placeholder。And then finally。

 we'll click on the triangle to the drop down next to one and specify this will be a random number from zero up to。

 but excluding the bunny's length。Now， we need to do one more thing before we swap the two bunnies。

 we need to make sure that index 1 and index 2 are different numbers。Let's use a while loop。

So let's drag in a while loop。It was like true initially。

What we want our Boolean condition to be is let's change this to the relational whole numbers。

And specify not equal to here， and we'll basically say， well not we want them to be not equal。

 So what we'll say instead is while index 1 is equal to index 2。

What do we need to do if they're equal， Well， let's go ahead and assign a new value to index 2。

So we'll assign。Index 2， and again， we'll do the same trick to be initially zero。

And will'll change0 to be a random number from0 up to。

 but excluding n will place one in as a placeholder。

And then we'll go ahead and change this to this bunny's length。

And we are done because while the two numbers are the same。

 we will generate a new random number for index 2 and this process will continue repeatedly until index 2 is a number which is different from index 1。

Now， what we need to do is to swap the bunny at location index1 and the bunny at location index2 of our bunnie's array。

In order to do so， we're going to need to add an extra variable。

 so we'll drag in an extra variable in here。 We'll name our variable temp。

Will specify its type to be a bunny。Click on okay。And we'll initialize and say T B the variable。

 this dot bunnies。At position indexex1。And click one， O。Next。

 we'd like to assign this dot bunnie's index1 to be this dot bunnie's index 2。

So let's go ahead and do an assignment statement。Here。To specify this dot bunnies。

Of index1 should be assigned to be this dot bunnies of hm。I can't specify index 2。

 so let's just place zero here as a placeholder。And they'll click on the drop down for the zero and specify here。

 index2。Looks good so far。Finally， let's go ahead and assign。Here to this dot bunnies of index 2。

To be temp。But we can't specify Ts。 So we'll just put this dot bunny as a placeholder。

And click on the drop down for this dot bunny and select Temp。And we are done。

Let's go ahead and call our swap procedure from my first method。So go to my first method。

And let's go ahead and start by dragging in a do and order tile。And we can call our swap procedure。

Let's go ahead and run the program。And the swap happens。But。

How do we know if the swap happened correctly？Well， we don't。

 so what we're going to need to do is to skip to step two where we turn each of the bunnies in our array purple very briefly。

And let's go ahead and create another scene procedure。Here。Which we can call， show。Colors。佢讲 ok。

This procedure will iterate through each of the bunnies， turning each one purple。

 and then back to white。 We start by dragging in a for each in tile。And we will specify this。

 We want to go through our array of bunnies。 So specify a type of bunny。We can name our iterator。

Bunny。Iterator。And the array， we can specify as this dot bunnies。Perfect。

We're going to need to change each of the bunnies to purple。 so in order to do this。

 let's do it as a two step process。 so we'll click on this dot bunny。And we'll scroll down。

And choose to set this bunny's paint。To be purple。And we can make the duration be half a second。

Great， and we can change this dot bununny now to our Bunny iterator。

And let's go ahead and repeat this process to turn the bunny iterator back white。

So we can set the paint of this bunny。To be white。Willll， again。

 make it happen for a duration of half a second。 And then finally， we can change this dot bunny to。

Bunny iterator。Now let's go back to my first method。And after we've done the call to swap。

 we can go back to this and we can click on。Show colors。Now， when we were going to run the project。

 we're going to get a chance to see the effect of the swap。 So before the swap。

 they would have printed off。 They would have turned purple in order。

 And we're going to see  two out of order。 So 3， then2， then  one， then 4， then 5 then 6， than 7。

 And what this means is bunnies 1 and 3 in position 0 and 2 got swap。

 Let's go ahead and run the project again to see a different pair of bunnies get swap。This time， one。

 then two， then6， then four， then five， then  three， then 7。

 and we notice that bunnies 6 and 3 in positions 2 and five of the array get swapped。

To make things more interesting， let's loop a thousand times calling swap within the loop。

 so we'll close our program。We'll go ahead and loop。A whole number of times specify a thousand times。

And instead of swapping just two bunnies， what once， we'll swap two bunnies a thousand times。

 So let's go ahead and run our program one more time to see the bunnies all mixed up。2 then one。

 then  three， then 6， then。Four then seven then five， theres complete random order， and in fact。

 if we run it one more time， we'll see a completely different arrangement of bunnies in order as a result of the thousand different swaps。

Great， the bunnies appear all mixed up。Next， we need to handle the player clicking on the bunnies。

So let's close up our program from running and go ahead and click on initialize event listeners。

And what we're going to need to add is an event for mouse clicked to an object listener。

We need to check if the bunny that gets clicked on matches the bunny inposition index of the array。

 so let's start by dragging in an if statement。And we'll specify true。

And what we'd like to do is we're going to need to test to match in one case a bunny with the object that got clicked on。

 so let's go ahead and change the true to relational S thing， and we're going to test equality。

And we'd like to say is this dot bunnies of position index equal to。

 and we'll just start with this ground as a placeholder。And then we can drop。

The event get mouse at location over top of the ground to build the equation that is the object that got clicked on the bunny that is initially in position zero of the array。

If it is what we're going to do in case there's a match is let's increment the index by one。

So we can assign。The index。Tobi。The index。And then we'll go ahead， and。Use math。And addd。

1 to the index。 That means we got the bunny in position 0。 And now we want to try。

 and hopefully the user will click on the game player will click on the bunny in position 1。

 They get it in one。 And their next challenge is to click on the bunny in position two of the array。

After we've incremented the index by one， we still need to go ahead and check if the player has won。

So let's do two things in order， so it'll drag in a do in order。First。

 we're going to increment the index， and now we need to check if the player has won。

 so let's add an if statement in here。Now， how do we know if the index if the player has one， well。

 that simply the case at the index has gotten to be7 or the length of the array。

 So we'll go ahead and change true to relational whole number equality。And ask if index is。

 we can't specify this as the length of the array， so we'll just put in one as a placeholder。

And then we can change the one。To go ahead and change this to the bunny's length。

And in case that the index becomes the bunny's length。

 then we can have perhaps one of the bunnies say you win。So we'll go ahead and。

Click on Bunny and we can have the bununny say。Custom text string。You win。

And maybe some nice exclamation point。Now， going back to the outer if statement。

 we need to decide what to do if the player's guess does not match the order of the bunnies in the array。

In this case， we're going to do two things first， so let's go to the outer else and we'll do two things in order。

The first thing we're going to do is we're going to assign to the index variable the value of minus1 because they've lost the game and so they no longer can increment the index and we'll set it to an invalid value of minus1。

And the second thing is let's go ahead and have the bunny。Sai。Something like。That is not the correct。

Order。We still have one small problem with the event processing。Namely。

 we only want to process mouse clicks of the player only if the player has not yet won the game and not yet lost the game。

To determine this， we need to write a Boolean scene function that returns true when the game is continuing。

So let's go ahead and create a scene level function。

 so we'll click on this for scene and create a scene function。Well initially set it to。Game。

 well name it game continuing。And we'll make it a boolean。Fangs。Now。

 the game continuing function should return true。As long as index is at least 0 and less than 7。

 If index becomes -1， we know the game is over because the player is lost。 If index becomes 7。

 the game is over and the player has one。Let's go ahead and figure out how to code it。Now。

 we need an if statement because the if we want to write is if indexes bigger than equal to 0 and indexes less than 7。

 we return true。 Otherwise， we return false。So we'll drag in an if statement into our function。

Well initially specify true， but we need two things to be true。

 index has to be bigger than equal to zero， and index has to be less than7。

 so let's change the true to be both true and true。And we'll change the first true。

 the leftmost true to index bigger than or equal to zero， so let's do relational whole number。

Bigger than equal to， and we'll make sure that index is bigger than or equal to0。For the second case。

 the game is continuing， we need index to be bigger than or equal to zero and index to be less than seven。

So we'll go ahead and change。Relational whole number。And we'll say less than for the first number。

 we'll choose index。 and for the second， we want the length of our array。

 so we'll initially just put one as a placeholder。And then we'll change the one to this bunny's length。

And if the index is bigger than equal to zero and the index is less than7。

 we can go ahead and return true because the game is continuing。Otherwise。

 we'll return false because the game is over。 Either the player has won or they've lost。 Now。

 we go back to the initialized event listeners tab。



![](img/c03bea534ea6fec7c12e1a93dfa4f040_2.png)

We need to modify our mouse click event because we only want to process mouse clicks if the game is continuing。

 So we'll go ahead and drag an if statement right into the beginning of our mouse clicked event。

 We'll click on true。Then we'll click on this as functions and drag game continuing on top of the true。

 and if the game is continuing， now we'll drag all of our code。

And if the game isn't continuing where you don't have to do anything。

Now let's play the game and try to win。Click on the run。It was6 then five。 Then， oh。

 I forgot already what it was， so。I'm going to try it again， I did six。Then 5。And two， oh。

 that's not the correct order， let's try it when the game one more time。



![](img/c03bea534ea6fec7c12e1a93dfa4f040_4.png)

F than six， then one， then three， then seven， then two then five。 let's try that。F。six。Then one。

 then three。And7。Into。And five。Fantastic。Let's go ahead and modify the game just ever so slightly by having some initial instructions。

 So perhaps after the bunny has， we've done the swaps， we can just have the bunny say something。

 so click on this bunny。And procedures。And。Maybe right here right in the beginning。

 we can just have the bununny say。Click on the bunnies in the。Order that they appear in。Purple。

And let's change the duration of the say。To be maybe three seconds。Great， let's run it one last time。

I misspelled Dca， so I'll fix that in a second， one， then two， then five， then four， then three。

 then six。Or seven then six。1 then2。And five， and four， and three。And7 and 6。Fantastic。

 so let's just correct this for one last time， so we'll。

So we'll click on this and change the custom text string， and let's just fix the。



![](img/c03bea534ea6fec7c12e1a93dfa4f040_6.png)

There we go。And now you have a fun memory game to play。

