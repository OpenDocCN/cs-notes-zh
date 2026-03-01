# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P24：24_02_08_For循环.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Now that you've seen some of the basics of JavaScript and have seen the Duke learn a program environment。

 you still have a few pieces to learn in order to be able to implement the green screen algorithm。

One of those pieces is repeating some steps of the algorithm， doing them once for each pixel。

Repeating steps is incredibly common in algorithms。 As you program more。

 you will find that most algorithms you write have some form of repetition。

So how do you write repetition down in JavaScript？You use a loop。 in this case。

 you would use a for loop， which will repeat some steps for each pixel。

 You can see an example of a for loop here， although the steps inside of it are not the ones for green for the green screen algorithm。

 You still have a few things left to learn before you can do that。

Let's start by breaking down the syntax of this loop。First， you have the keyword 4。

 which says you are writing a for loop。Next， you have information about how to do the repetition inside of the parentheses。

The first part of this information is the variable declaration here Var Pel。

 which makes a new variable to refer to the current item。

The loop will automatically update this variable each time it repeats。

 setting its value to the next piece of data。 In the case of this loop。

 each pace of data will be a pixel。Next is the keyword of。

 which says that you are about to say what pieces of data to iterate over。

Then you have the expression that evaluates the data you want to iterate over。 In this case。

 we have image dot values。 The dot values method inside of simple image gives back all of its pixels to access each one in turn within the loop body via the variable pixel。

Finally， you have the body of the loop inside of curly braces。

 The body of the loop is the set of statements that should be repeated for each piece of data。Okay。

 great， now that you have the basics of the for loop syntax， let's look at the semantics。

Here we are about to begin execution of the for loop。

 We are assuming that the variable IMG was previously declared and initialized to refer to this two by two image。

We've drawn a light blue box around the image and made the arrow in IMG's box match this color to help make it clear what the arrow is referring to once we start drawing other arrows。

IMG's arrow refers to the image as a whole。The first part of the for loop creates a new variable named Pixel。

 so we are going to create a box for that variable。

The second part says that we are going to do a loop over each pixel in the image。

 so we will start with the pixel variable， referring to the first pixel in the image。

 Notice that the arrow is pointing at one particular pixel。

 It is also important to note that we are referring to an existing pixel inside of the image。

 not making the new pixel。 Why does this matter。 In a moment。

 we are going to change the color of the pixel and the change will show up in the image。

 Since var pixel is the actual pixel inside that image。

This box on the right lets you peak inside of the pixel's numerical data。

 The pixel has X and Y coordinates and red， green and blue component values。

 These are not separate data， but we write them here so that they are clear as we manipulate the pixel since they don't show up directly in the conceptual colored squares picture。

Now， we go inside the body of the loop and begin executing statements there。

 The first statement declares a variable called new G and initializes it to 255 minus pixel dot get green。

If you look at the numerical data for this pixel， you will see that its green value is0。

 so new G will be initialized to 255。Next， you are going to do pixel dot set green to new G。

 Since new G is 255。 this will set the pixel's green value to 255。

 changing its color from magenta to white。Now， the next thing in the code is the closed curly braces。

 which ends the body of the for loop。 When you reach the end of the for loops body。

 you go back to the top of the loop and move to the next piece of data。 In the case of this loop。

 that means updating the pixel variable to the next pixel in the image like this。

Now you are going to do the steps in the for loop again with the next piece of data。

 or as a programmer would say， you are ready to do the next iteration of the loop。

We start by going inside the body of the loop and executing the statements there again。 Again。

 we declare and initialize new G to be 2，55， and then do pixel dot set green to 255。

 And that changes the second pixel from blue to can。Again， we are at the end of the loop。

 so it is time to go back up to the start of the loop and update the pixel to refer to the next pixel in the image。

Again， we go into the body of the loop and declare and initialize new G This time， however。

 since the green value is 255， the value of new G is 0。We do pixel dot set green to zero。

 which will change this pixel from green to black。We once again find ourselves at the end of the loop。

 Can you guess what happens next。We go back to the top of the loop。

 updating the pixel to refer to the last pixel in the image。We go into the loop body。

 declare and initialize new G， and then do Pixel dot set green to0。

 which changes this last pixel from white to magenta。And once again， we are at the end of the loop。

Now， there is not another pixel。 So when we go back to the top of the loop， there is no pixel left。

 At this point， the loop has nothing else to iterate over。

 So we jump down past the end of the loop body and continue executing whatever code might be there。

