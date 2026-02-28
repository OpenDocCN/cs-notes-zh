# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P20：20_02_02_方法.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Okay， so now you know about variables， but you also need to know how to do things like look at particular pixels and change their colors。

 How could you do these things， The answer is that you can call some methods that are built into simple image which already have the code to perform these operations。

 In general， methods let you perform some operation， possibly one that is quite complex on an object。

😊，Here is an example of calling two methods， get width and get height to get the width and height of an image respectively。

Let's break down the syntax。First is the name of the object。 We want to invoke the methadone。

 which simple image height do we want to get。Whatever simple image we name here。Next is a dot。

 the dot operator means inside of。We want the Git height method inside of FG image。

Next is the name of the method that we want to call， in this case it is gett height。Finally。

 there are parentheses， parentheses after a name indicate that it is a method or a function。

 which is similar。If the method took any parameters， you would specify them inside the parentheses。

Now that you have seen the syntax of a method call。

 let us see the semantics before we step through the behavior， we'll describe the semantics。First。

 execution goes into the method。You stop executing statements where you were。

 go inside the code for the method and then do whatever code is there。

You do that code by following all the normal rules for executing code。It has the same semantics。

 whether it is inside a method or not。At some point。

 the method will figure out what answer it wants to give back， which is calledRe its answer。

The method call， which is actually an expression， evaluates to whatever value the body returned。

Then you continue executing code after the method call。Let's see those rules in action。

The first one we have seen before。It makes an image and initializes FG image to refer to it。

Next is a call to fgimage。getwis。The code Forge with is in the Duke Learn a program library。

 we don't actually know what the code is， but that is fine as long as we know what it does。

The computer would then go into that code and start executing it。

That code would figure out what the width of FG image is that it's 480 pixels and decide that 480 is its answer。

Since this method's answer is 480， the call FGimage。getH evaluates to 480。

 Another way to think of that is that it's like a mathematical operation with the result 480。Now。

 execution comes back to where it was， which is halfway through this assignment statement。

We finished the assignment statement by making a box for W and putting 480 in it。

Now a similar process happens for the call to fgimage。getHight。

 the computer executes the code inside the Duke Learn to program library。

 figures out that the answer is 270 and returns that value to where the method was called。

Execution then returns to where the method was called。And the assignment statement finishes as usual。

So how do you know what a method does， Well， if you have the code。

 you could see what it does stepping through it line by line following the semantics of the code。

But what if you don't have the code as in this case？You should read the documentation。

 a written description of what a method does。For simple image。

 you can find documentation about it on Dukeleartoprogram。com。

If you were to go to the DukeLearnedtoprogram。com website， you would see a link for documentation。

If you clicked on it and looked at the left， you would find a list of the topics that are documented。

One of these is simple image。If you click on that， you would get to a page that lists the various methods in simple image。

 including getHight。If you were to look at this entry。

 you would see that it describes the behavior of the method。

It gives you the height of the image in pixels。We have said that methods are invoked on an object。

 but what exactly does that mean？Well， if you are asking for the height of an image。

 which images height do you want？The answer is whichever image you invoke the Me on to see this in action。

 let us look at this example which has two images。Our first line of code makes one image called FG imageage。

And our second line of code makes the other image called。D image。Now we are about to do fgimage。

get width。Since we are evoking the gett width method on FG image。

 it's going to work with the image referred to by FG image and give us its height。

Execution jumps into the Gettwi method in the Duke Learn toprogram。

com library and does whatever the code there says to。

Notice that the method looked at FG image and found its width coming up with an answer of 480。

The method call evaluates to 480 and the assignment executes， as you have learned。

Now the next line is D imageage。get width。Since this method is being invoked on D image。

 the method will operate on the image that it refers to。Again。

 the execution jumps into the Duke learn toprogram。

com librariess code and does whatever the code there says to do。However， this time。

 it is working with a different image， so it comes up with a different answer， 140。

 which is what this method call evaluates to。Finally。

 we return to the method call and finish the assignment statement。Some methods have parameters。

 for example， if you wanted to call get Pixel on an image which gives you a particular pixel。

 it might look like this。Notice that we have zero， comma 0 in the parentheses。What do these mean？😮。

These are the parameters to the method。 They give the method more specific information about what it's supposed to do。

In the particular case of git Pixel， the parameter specify which pixel it should get from the image by giving the desired pixels X and Y coordinates。

The particular meaning of the parameters is specific to each method。

But should be described in the documentation。Methods combine together multiple。

 potentially complex steps that operate on a specific object。

There's a similar concept which does not work on an object called a function。

 which we will discuss next， thank you。