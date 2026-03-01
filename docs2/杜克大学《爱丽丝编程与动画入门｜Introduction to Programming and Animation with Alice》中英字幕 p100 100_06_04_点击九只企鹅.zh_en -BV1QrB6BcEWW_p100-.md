# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p100 100_06_04_点击九只企鹅.zh_en -BV1QrB6BcEWW_p100-

![](img/2b7e7e2bbbc1fe198a876fdc57f872f6_0.png)

In this project， we are going to play a variant of the Wackammle acade game。

 rather than trying to click as many moles as possible within some time limit。

We are going to design a game where the player has to click each penguin once。

Rather than moving one penguin around， Willin said， place 9 penguins into a3 by three space。

 We'll then move the penguins below ground， and the randomness will involve popping random penguins from the9 up and then back down in place。

😊，In this project， we initially have nine penguins all standing in the same place。

If we click on the scene tab。Which is here。And we'll scroll down。

And we see that we have a penguin array。With 9 penguins in it。It's called penguin list。

And they're located in positions zero through8 of the array。Let's click back to my first method。

We see that my first method contains a single call to set up scene。If we click on this。

Then we can click on the editit besideSe scene。And now we can see the code here。

We see that the camera is moved to a position where it looks down on the ground。

And we see that the nine penguins are all moved into position making up a three by three grid。

They are then moved below the surface of the ground。Let's click back on my first method。

Let's cause the penguins to pop one at a time and randomly out of the ground。

Let's drag a while loop up right below the setup scene。And select true。

This is going to be initially an infinite loop， so we'll leave the true there。

Let's create a seen procedure called popop up Penguin。So scene， create a scene procedure。

 we'll call it pop penguin。This procedure is going to pop the penguin out of the ground。

We're going to pass a single parameter of type penguin。So let's find that in gallery class， penguin。

And we'll name it。 which penguin。We I gonna to do an order tile。Now。

 if the penguin that has been passed is white， we can pop it up in place。

So we drag in an if statement into the do and order。And select true as a placeholder。

Then we change the true to relational paint， and then we're going to compare if two paint colors are equal and we'll just select white and white。

We'd like to ask if which penguins get Pa is white。 So to do this， we'll first pick a penguin。

 I'll just pick penguin 9。And then we'll look for its function git paint。

 and we'll drag that in over the first white。And then， we can。

Drag which penguin over top of penguin 9。 So it says if which penguin get paint is white。

If which penguin's paint is white， then we want it to quickly move up one unit， wait half a second。

 and then quickly move back down below the ground。So let's add in a do an order。

And we'll have penguin  nine。Move up1。Unit。We want to tap in quickly， so we'll add a duration of 。25。

Let's change penguin 9 now to our parameter， which is which penguin。Next。

 we want the penguin to delay half a second， so we have to scroll down。And find the delay。

And then we'll have it delay half a second。And change penguin9 to which penguin。

And then the last step is to have the penguin moved down。Back under the ground。

So we'll drag over the move。down。😔，1， and again， will'll change the duration to025。

And we need to change penguin 9 to which penguin。So now if which penguin's paint matches white。

 it'll move up。It'll delay for half a second and move back down。Let's go back to my first method。

We click on this。And now we can drag over pop penguin。Into the while loop。

And select the penguin list with a placeholder of0。

Now what we want to do is have a random penguin pop up。

 so we'll click on the zero and change that to a random number。Which goes from。Z up to。

 but not including the penguin list length， but that's not a choice， so we'll just pick zero。

And then we'll click on the second zero and change it to the penguin list length What this will do is generate a random number that is one of the positions in the penguin array and pick that penguin to pass to pop penguin。

Let's run the project。And we see random penguins popping up。That's great。We can close that now。

Now let's create an event that turns the penguin red if we click on it。

Let's click on the initialized Even listeners tab。We click on the Add Even listener button and select Mouse。

And add mouse click on objectject listener。Under the Add detail。

 we can select for set of visuals our penguin list array。

We'd like to process clicks on any of the penguins in our penguin list。Now， what should we do？

Just turn the clicked penguin red。 That's all we have to do。

 so we can select penguin 9 or any penguin， really。And then we can look for its set paint procedure。

 which is down here。Let's drag that in。And have it set the paint to red。And then instead of Pguin 9。

 we can drag the git model at mouse location， which is the thing we just clicked on and drag that over。

The penguin night。Nowo。Let's click on Run again and this time let's try to click on the penguins。

So I'm going to run it， there they are。Now they're kind of hard to click on。

 so you know what I'm going to do， I'm going to close this and I'm going to go back to Po Penguin and I'm going to slow it down a little bit。

Where the delay is， which is half a second， I'm going to change that to one second。Okay。

 now click on run。Nowao。Oh yeah， that's much better if I click on it。

 you can see it turning red slowly。There， see， it's just turning red。Now。

 I should be able to click on all nine penguins。Oh yeah， they just keep going。I got him all。

But the game just doesn't end。So we need to do something to make the game end。

Let's close the run window。And go back to my first method。

And the game never ends because we have a wild true loop。

So what we really want now is while at least one of the penguins is white loop。

So we need to create a scene function。Let's do that。A scene function。Addine function。

And we'll call it。At。Least one of the penguins。Is white。And it's going to return a bullion。

 either true or false if this is true。What we need to do in this function。

We need to iterate through the penguins one at a time， if we find just one of them that's white。

 we can return true。If we go through the whole loop and none of the penguins are white。

 then we need to return false。Let's write that。First， let's drag in a do an order。

We want to drag in a for each in tile into the do and order。And this is going to be for penguins。

 so we'll pick gallery class penguin。The name can be penguin iterator。

And our array can just be our penguin list array。And click， O。Now into this loop。

 we're going to drag in an if tile and just select true。

We click on the true now and change this to a relational paint。

Comparison to see if two paints are equal。And then we'll just compare white with white for now。

We'd like to ask if the penguin iterator's paint is white， so this is going to be a two step process。

 First we select to penguin， I'll just pick penguin 9。

Then we're going to drag in its get paint function right here。Over the first white。

And then we're going to change penguin 9 to penguin iterator。

So we're asking if each penguin one at a time if it's white。Now， what should we do if it is white。

 well， just return true， so drag up the return and select true。Because if just one of them is white。

 we need to keep the game going。But if we go through the whole loop and we haven't returned yet。

 that means that none of the pinggus is white， that means the game's over。

 so let's return fault at that point。Return。False。Let's click back on my first method。We then select。

😔，This over here。And we want to drag in our function that we just wrote。

 at least one of the pings white over the true in the while loop right here。



![](img/2b7e7e2bbbc1fe198a876fdc57f872f6_2.png)

So while at least one of the penins is white， we'll have a random penguin pop up。Lao。😔。

The last thing we want to do is when the game is over。

 we'd like to have all of the penguins move up together。So let's do that。We can drag in a。

Each in together tile right here after the while loop。And this is going to be for a penguin。

 so gallery class， penguin。We can name this item name penguin itator。

And our array will be our penguin list。So what do we want each penguin to do。

 we want each penguin to move up one。So for penguin， just pick a penguin， say penguin9。And have it。

 Mo up one。And then change penguin 9 to the variable in our loop， which is penguin iterator。Now。

 let's run the project。There we go Now our pings are going， we click on them one at a time。

 there's two， I've gotten three。F。😔，5。😔，6。seven。😔，诶y。Nan。And they all come up。

That's our click of penguin game with 9 penguins。 In't that fun to play。😊。

