# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p134 134_08_04_逻辑游戏演示.zh_en -BV1QrB6BcEWW_p134-

![](img/f85b526dfaaf36a9ac522f93e4f75ab4_0.png)

We have partially set up this game。We have placed three bells in front of three ancient pillars。

 We've also added a tortoise。Who will be used to provide instructions about the game。

If we click on run， let's do that now。We are asked if we want instructions。

If we enter why the turtle's going to tell us how to play the game。

You want to guess a secret code that is the position of the bells。From left to right is each bell。

 up or down。You will click on the bells to move the bells up or down to put them in position。

But if we click on a bell， let's try it。Nothing happens。Let's close the run window。

Let's click on the scene tab。We're going to scroll to the bottom。

We see at the bottom that there is an array of bells， aptly called bells。

And an array of text strings， called code。Let's go ahead and do each of the three tasks we described earlier。

The first task is to create a secret code。Let's create a scene procedure。And will name it。

 generate secret code。And click， O。What we'll need to do is to go through each of the elements of the code array。

 setting each element to up or down randomly。We cannot use an iterator as Alice doesn't let us assign to the elements of the array being iterated。

Instead， we can use a counted loop。Let's start with a do and order tile。

We start by creating a whole number variable。Let's drag that up。Its type is going to be whole number。

 and it's a variable。Its name is gonna be index。And we'll initialize it to zero。And click， Ok。Next。

 we drag in a count loop into the do an order right after our variable index。

And we'll go up to this code dot link。Now， 50% of the time。

 we want to set the next element of our array to up。

And 50% of the time we want to set the next element of our code array to down。

We add an if statement into our counted loop。And select true as a placeholder。

We then change the true。😔，To next， randombuyion。Next。

 we drag an assign instruction into the then case。There's our sign。We select。This do code。Now。

 the code with the square brackets， which is the array。And then we select index。And we select。

Custom text string。We enter up。We do the same thing for the else case， but we select down。

 so let's drag in the assign。We select this code that's the array。

We select the index and custom text string this time we type down。And click， O。Finally。

 we need to increment the index by one。 We drag in and assign。Stment。And we put it inside the loop。

 but after the else statement。Index is going to equal。Index。And then we'll use math。To add one to it。

Index plus。Wan。That's it。It would be best to see that we are generating different random codes。

 We'll later need to write a function that converts the secret code from an array of strings into a single string。

Let's just write that function now。Which we can then call to see what secret code is generated。

So let's create a scene function。Xin。😔，And function。And let's name it G secret code。

Which is going to return a text string， so set the return type to text string。And then， click， O。

We start by creating a texturing variable named the code。So we're going to call it the code。

Its value type is a text string， so let's change this to text string。

And it's going to be initialized as an empty string。So just select custom text string and hit enter。

And then click， O。We then add a for each in to iterate through the code， so let's drag that in。

And for the item type， it's going to be text string for each item。The name of it will be one code。

And the array will'll use the code array， the code。Click， Ok。

Our loop will append each of the codes in the code array to the end of our the code variable。

Inside this iterated loop， we assign the code to be the code。So let's do that now。So。

 we'll pick the code。To be。😔，The code。And then what we'll do is we will。

Pick the drop down menu beside the second， the code。And will be the code plus something。

And what we're going to add to it is one code。Finally， after the loop is over。

 we can just return the code。So let's use that return。The code。To test this out。

 let's go into my first method。Immediately after the comment。

 we can call this dot generate secret code。So we go to procedures。And drag over。

 generate secret code。And as a last line， we can have the turtle say。Let's get the turtle。To say。

This is after the F。We'll have them say the secret code is。Blank， and then click， O。

And then let's click on where it says the secret code is。And let's append。Just hello。

Then we can go to the tortoise。Functions， os， not there。Let's go to the scene。

Functions and get secret code we can drag over where it saysHo。Now。

 let's run the project and see what happens。We don't need to see the instructions。The coat is down。

 down up。 Let's run it again。The code is up， down up， that's different。 let's run it again。

The coat is down up， down。 So that looks good。Finally。

Let's comment out the line of code where the tortoise tells us what the secret code is。

 because it would be no fun to play the game if we knew what the code was。

So let's just comment out this code。呃。Now we're ready to move on to the second step。

Here we want to process the game player clicking on the bells。 We go to initialize event listeners。

And add a mouse click on object listener。Mouse， add mouse， click on object listener。

We specify the set of visuals to be the bells。Right here， this dot bells。As we only want to process。

 mouse clicks on the bells。Inside the procedure we'll need to eventually do two things in order。

First， we'll move the bell。 and then as part of step 3。

 we'll check to see if the game player has won the game。So let's drag in a do an order。Now。

 we just want to move the clicked on bell up if it was in the down position and down if it was in the up position。

 So drag and if。And select true。We'd like to build the expression if the model at mouse location is above the bar。

We start by clicking on the bell。Here's the bell。And select its I above function。

To scroll down to see that。We'll drag that into the true。And select the bar， the stop bar。

Now we want to click on get model at mouse location and drag that over the bell so it reads。

If Gi model at mouse location is above this dot bar。Well。If the bell was above the bar。

 we want to move down 1。5 units。 Again， this is a two step process。

 We click on the bell's procedures and drag over。The move。Dao。1。5。And again。

 we have to drag the git model at mouse location over the word this dobell。Now， for the else case。

 we can do pretty much the same thing except move the bell up and set it down。So。

 let's actually just copy this。To the clipboard。And we'll drag it in。

And will'll change the down to up。Let's now test our program by running it and clicking on bells。

So if we click run。don't need instructions and let's click on a bell。And it moves up。

We click on it again and it moves down， let's just test another bell。Oh， this is great。

 we click on them and they move。Let's close the run window。

The last step is to write a function that checks if the position of the bells matches the secret code。

We'll create a scene function。Seen and function this time。And will call it。 check for match。

And the return type is going to be abuan， which will be true or false。Click， O。

This function needs to do two things。 First， it has to build the correct string from the current position of the belts。

Let's start by creating a text string variable namedG。So it's a variable， it'll be of type。

 text string， we'll call it guess。And we'll initialize it to an empty string。

 So just pick custom text string and hit enter。And then click， O。Next。

 we can iterate through the bells array， so drag in the for each in loop。

We'll have to select the type。As Bell in the gallery class。Okay。We're going give the name to be。

Bell iterator。And for the array， we'll select that and you'll see this dot bells。Click， Ok。

Let's drag in an if statement。Into the loop。And just select true is a placeholder。For each bell。

 we need to check if it is above the bar。 Again， this will be a two step process。First。

 we drag in the bell function is above， so pick on the bell。

And then look for the functions and search for is above， there it is。Is the bell above the bar。

And then replace bell， this that bell with bell iterator by dragging bell iterator on top of。

This dot bell。 So it should read if the bell iterator is above this dot bar。For the thin case。

 we wish to assign guests。So let's drag it up。And we'll assign guests to be guess。

And then we'll go to the little down arrow beside it， and we'll add something。

 we'll add a custom text string and type the word up。Because the bells in the up position。

For the else case， we assign guests to be guests again。So let's drag in the assign。Guests will be。

Guess。And then again， we'll click on the down arrow。And。😔，Will'll add to it， a custom text string。

That is the word down。Because if the bells aren't up， they're in the down position。After the loop。

 guess is a string that represents the current position of the bells。So second。

 we wish to check if gas is equal to the secret code。We're going to add an if statement。

 right after the loop。And select true as a placeholder。

We then change the true to be a text string comparison。

We're going to check if two strings are equals using contents equals。

And the two strings we want to check are guests。And just pick hello for the second one。

We're going replace， hello。By let's go over to find the function， get secret code。

And let's drag that over top of the hello。So our if statement now should say if guess content equals。

This dot get secret code。So if that is true。Then that means the bells are in the positions to match the code。

So。😔，We want to return true。Let's dragon return true。For the elseS case， we should return faults。

The bells do not match the coat。

![](img/f85b526dfaaf36a9ac522f93e4f75ab4_2.png)

Let's click back on initialized event， listeners。After moving the bell up or down。

 let's add an if statement。Right here and select true。

We drag the check for match over top of the troop。Check for match right there。

 So if check for match is true。What do we want to do。

 We want the touristtoise to say something like nice job。So let's find the tortoise and procedures。

And have the tortoise say。Custom text string。Nice job。

Then we can also have the tortoise say what the secret code was。So let's have the tortoise say。

This is still in the then part of the F。Custom text string。The secret。Code is。And click， OK。And then。

Let's add to that。Plus， hello。And then， let's go to the this。

And find the Gets code function and drag that over the hello。There we go。We are now done。

 Let's play the game。Welcome to the Logic game， We don't need instructions。All right。

 let's click some bells。We go up。We go up。We go up。Let's bring this one down。Bring this one down。Oh。

 we got it。The secret code was up， down down。It worked。We hope you have fun playing this game。

