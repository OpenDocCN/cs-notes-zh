# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p24 024_03_04_兔子跳跃过程.zh_en -BV1QrB6BcEWW_p24-

![](img/96fd6d778ede3e2550f7d653d8f4d100_0.png)

In this demonstration， we're going to create our own instruction or procedure。

The specific instruction we're going to create is to have the bunny hop。

The storyboard we sketched illustrates the hop procedure。 It has three scenes。

Scene one shows the bunny standing on the ground。Scene2 shows the start of the hop。

 the bunny will move up and forward at the same time。

Notice the arrow indicating that the bunny is simultaneously moving up and forward。

Scene three shows the end of the hop， the bunny will move down and forward at the same time。

 and we can see with the arrow。Let's implement the H。In this world， we see a bunny， a mango tree。

 and a mango。Make sure you are in coding mode where there's a big empty window labeled my first method。

Above the Procedure tab on the left side of the screen。

 you can click on the triangle on the right and select the bunny， technically this bunny。

We'd like to have the bununny hop。To hop towards the mango。 first。

 the bunny needs to turn towards the juicy mango， yum。Then there's two parts to the hop。

In the first part， the bunny moves up and forward at the same time。In the second part。

 the bunny simultaneously moved forward and back down to the ground。Let's implement this story。

Because these three steps will occur in order， we first drag a do in order instruction into my first method。

Do an order goes into my first method Yes， animations in Alice run in order by default。

It's always good to be explicit about what we want。

The first step is to have the bunny turn to face the mango。

Let's drag a turn to face instruction into the do order we just added。Funny。Turn to face。The mango。

Next， we need to simultaneously have the bunny move up and forwards。

We're going to need to first drag a do together instruction into our code。

Place the doing together immediately after the turn to face。

We'll have the bunny move up half a unit and also have the bunny move forward half a unit。

Drag the move instruction。Specifying up。Half a unit。And we also ask have the bunny。Move。Forward。

Half a unit。Now we just need to finish off the hop。Let's use another do together。

 and then inside the do together， we can add the instructions to move the bunny back down the half unit and for the bunny to move forward a half unit。

First， we drag in the two together。Then we have the bunny。Move down a half unit。At the same time。

 we asked the bunny to move forward。Half a unit。One last thing。

It's a good idea to add a comment to our code so that later we'll remember the details of what we did。

 Let's drag a comment immediately before the first do together to describe the hop。😊。

We'll have the comments state that the bunny does a triangular hop。

Now let's click on the run to see our animation run。Bunny turns and then hops towards a mango。

 awesome。😊，But we have a bit of a problem。One hop doesn't get the bunny close enough to eat the mango。

So we'll need to have the money hop again。Oh， there's a lot more dragging and dropping to get the bunny to hop again。

There has to be a better way。Well， in Alice， there is。

Instead of all these do an order and do together and move instructions。

 we can just use a bunny hop instruction instead。Let's comment out the two do together instructions by right mouse clicking on the do Together。

We right mouse click on the do together and we deselect the is anable tab。 We'll do that for both。

Do together instructions。You'll see that there are now gray lines running through the instructions。

That means that Alice will not execute these instructions when we run the world。

 Let's instead use a hop instruction。If you scroll up and down along the instructions or procedures the bunny knows how to do。

 you'll notice there is no instruction for the bunny to hop。I grow up。And that。

There is no hop instruction。We need to create it。To create our own procedure。

 we find the yellow hexagon at the center top of the screen and click on the little triangle to the right of the yellow hexagon。

A drop down list appears containing all of the objects。Technically。

 the classes where we have been selected instances of the class in our world。

 if we mouse down to the bunny。Another drop down list appears， and we can select add Bunny procedure。

Now we are asked to name our new procedure， let's name it hop。

Alice does not care whether you use capital or lower case letters。Conventionally。

 we tend to name our procedures starting with a lower case letter。As we have done with H。

After clicking on OK。The entire screen changes。 The vast majority of the screen is empty。

 providing room for us to drag and drop the instructions that will make a bunny hop。

The good news is that we already know how to have a bunny hop。😊，In order， let's drag a do in order。

We first simultaneously have the bunny move up and forward， let's do it。We drag in and do together。

And we ask the bunny to move。U。Half a unit。At the same time， we asked the bunny to move。Forward。

 half a unit。Then we simultaneously move the bunny down and forward。One more do together。

And in this due together， we simultaneously asked the bunny to move。down。Half a unit。

And we asked the bunny to move。Forward。Another half unit。Finally and stylistically。

 we add a comment describing what we did。We can state that。The bununny。Hops in a triangular。Fashion。

Great， now let's run our world。Butunny turned and。One minute。The bunny doesn't hop at all。

 something is wrong。While we wrote the instruction procedure to teach a bunny how to hop。

 we never invoked or called our instruction from my first method。To do so。

 we click back on the My first method tab at the top of the screen。Next。

 we click on the triangle to the right of the word this on the left hand side of the screen and select this dot bunny。

Finally， we select the bunny's Edable procedureced hop and drag it in to my first method。Now。

 when we click on the Run button。The bunny hops once towards the mango。Hllold on just a minute。

How is this any better than our first approach？This is where the magic comes in。

 If we'd like to have the bunny hop twice， all we need to do is to drop the bunny hop instruction into my first method a second time。

😊，And now when we run the world， the bunny turns to face the mango and hops twice towards the mango。



![](img/96fd6d778ede3e2550f7d653d8f4d100_2.png)

We have unleashed the power of procedures。