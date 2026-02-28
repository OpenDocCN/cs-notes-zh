# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P35：35_03_03_图像转灰度.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/333205ce1cecae90629cff130fcd4b6c_0.png)

Hi， let's look at changing a simple image programmatically using the same concepts you used in the previous module。

In the foundational programming lessons， you modified pixels in an image， for example。

 you change different parts of an image to create stripes so that part of the image was red。

 part was blue， and more。You also saw how to modify all pixels of an image as part of creating a new image that was a green screen composite of two images。

We'll use these same concepts of modifying pixels to create interactive web pages that use this simple image library。

Let's look at creating a grayscale version of an image。 Gscale is a common filter。

 We'll start with a code pen web page that already has functionality to upload an image。

 We'll fork it and we'll add a button to create the grayscale web page that takes an image like the waterfall on the left and converts it into a grayscale version as shown on the right。

Extending a working web page continues what we did earlier with the prototype web page before we introduce the HTML file input type。

The button that we create will'll call a JavaScript function namedMakeGray。

 using the standard oncl event handler will'll need to access the uploaded image in this function makeGray。

This will require a new programming concept， global variables。

A global variable can be accessed in all functions because it's defined outside of any of these。

 that's what makes it global。We'll see that a global variable for an uploaded image can be accessed in the function upload and also in the function make gray。

The global variable is set or assigned to value and upload and then access or modified in make gray to create the grayscale version of the image。

The first four steps in writing a program are to devise an algorithm。

We know that what makes a color a shade of gray is that each of the red， green。

 and blue values is equal to the others。And we'd like for our grayscale image to retain variations in brightness of the original image。

 so it won't just be black and white。One way to do this is to average the RGB values and to set the new RGB values to this average。

Let's look at the first step， working an example by hand with some sample pixels。

To do any math on this green pixel， we need to know the RGB values for green， that's0 red。

255 green and zero blue。Averaging these values means performing the operation 0 plus 255 plus 0。

 all divided by3， which is 85。That means the new grayscale pixel will have R and G and B values each of 85。

Which looks like this。Try this for magenta。We can see the RGB values。Did you get 170？

A gray that looks like this。If you'd like more practice by hand。

 try the gray scale algorithm on Maroon， Sky blue， and orange with these RGB values。

Did you get these answers？Now， we've done steps 1 and 2， working an example by hand。

 You wrote down what you did。 We can now generalize these steps。 Start with the image we want。

 And then for each pixel in the image。Obtain the R and G and B values。Calculate the average value。

And then set each of the RGB values to this average。Finally， display the final image。

Using the Duke learned a program environment， you wrote code to process all pixels in an image to change their color。

 We'll use that same idea of looping over pixels to create a gray scale version of an image in our interactive web page。

 Let's look at translating this algorithm into code。Recall that we're adding a button。

 make grayscale。

![](img/333205ce1cecae90629cff130fcd4b6c_2.png)

Whose on clickick event handler is the function make gray。Let's look closely at this function。

 make gray。Here's the JavaScript source code for the make gray function。

 We'll look at each line and see how the code works to convert an image to grayscale。

Let's assume that the first step of the algorithm is already complete。

 The variable image was previously defined。To do steps 2 of the algorithm。

 we loop over all pixels in an image by creating a variable to represent each pixel and then using the image method dot values to access all the pixels。

We calculate the average of the RGB values by accessing each of them。

 adding them together and calculating the average。Then we set the pixel's red value to the average。

 then the green。And then the blue to the same average。Finally。

 to perform the third step of the algorithm to display the grayscale image。

 we access the HTML canvas element by calling document do get element by ID with the I of the canvas here。

 that's C AN or can。 We use this canvas by passing it to the images draw to method。

 So the image draws itself in the canvas and we see it on the web page。We do need to address。

The first step of the algorithm， Let's take a look。We need to start with the image we want。

 where is it？In our version of the web page that only uploaded a file。

Changing the file selector by clicking on it， call the function Up。

Where we created an image by calling new simple image。But now we need this image in the function。

 make gray。 How does make gray access a variable initialized in another function？

Let's solve this problem。Since upload is where the variable image is defined with the Var VAR keyword。

😡，That means a function like make gray。Cannot see variables defined inside the function upload。

And image dot values will not work。We need global variables for this so that many functions can access the same variable。

We can still use the variable image in the upload function， but without the word var。

 the keyword VAR。A global variable can be accessed in all functions。

 Let's see how to use global variables in code。A global variable is defined outside of all the functions。

 using the same JavaScript keyword VR var to create the variable。

The global variable can be used in each function without using Var。

 Remember that using Var creates a new variable Here。

 the variable image is assigned the value of calling new simple image。

 It's assigned that inside the function， upload。Here。

 the variable image is accessed in the function make gray to loop over all pixels in the image。

Note that the variable pixel is defined with VAR， but the variable image is not。And here。

 image is used again， so it can be displayed in the canvas by calling the image do drawaw2 method。

Be careful when using global variables。 If you had defined the variable image using VAR inside the function upload。

 you wouldn't be assigning to the global variable， but to one defined for the first time in upload。

 this is a hard bug to find sometimes。It's possible to have more than one global variable。

 For example， suppose we want to display the original image without the gray scale alteration。

Without uploading the image again。We could create a new image in function make gray。

 rather than modifying the uploaded image。 We could store both the regular image and the grayscale version in two different global variables。

You'll have the opportunity to try out this alternative where you don't alter the original image。

Try to minimize the use of global variables， relying on too many can make it hard to understand the code you're developing and how the functions interact with each other。

Happy coding。