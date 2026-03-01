# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P36：36_03_05_迁移至CodePen.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/3ae9f22094dbbaa052fefe5814065693_0.png)

Let's look at how to use concepts， tools and programming to create an interactive green screen page。

 we'll use HTML elements like Canvas and inputs for files and buttons to create an interactive green screen page like this one。



![](img/3ae9f22094dbbaa052fefe5814065693_2.png)

You can see two images have been uploaded， I'm about to press the Create compositeos button。

That will combine the two uploaded images into one using green screen code you've seen in the Duke Learn to program environment。

There are several steps you'll need to take to use the code you developed in the Duke Learner program environment and make it work in a web page。

 you'll need to use HTML input elements to allow users to select files。

 Those input elements need event handlers to connect the events to JavaScript code。😡。

You'll need to create functions to load the images and global variables so that all functions can use these images to make the green screen appear。

 you'll use the draw to method instead of print。 Finally。

 we'll show you how to protect your code with checks to make sure that it works without error。

Let's look at the components of this interactive web page。 We'll look at the H elements first。

 and then we'll connect these to jascript。 You can see here that there are two standard canvas elements。

 Each one has a border that's part of the CsS for the canvas。

 There's one canvas where the foreground image will be displayed。

And another canvas for the background image。You'll also see four input elements。

 two are file inputs for the images。And two are buttons that change what you see in the canvases。

 The file inputs are labeled with their purpose on the web page。

Upload a foreground image and a background image。 Two buttons are used。

 One to create the green screen composite and one to clear the canvases。Let's look in the tail。



![](img/3ae9f22094dbbaa052fefe5814065693_4.png)

At the HTML file elements。We have two file inputs， one to upload the foreground image and one for the background image。

Here's the HTML for these labeled images。 We'll review the HTML elements and the concept that you've seen before。

We create a file input to allow the user to upload and display an image file。

 Here's the foreground file input。And there's also a file input button for the background image。

These file input buttons have unique I。 This will allow them to be identified as needed in the jascript code that interacts with the webp page。

 We see FG file for the foreground input and BG file for the background input We connect these input to corresponding jascript to load and display the image in a canvas。

 We use the onchan event handler and call a ja function。 Here， we're calling load foreground image。

 And here， the event handler calls a jascript function named load background image。

 Let's look at the jascript code that's called when the user uploads an image。

Uploading and displaying an image use concepts we've seen before。

Here's the JavaScript function to load the foreground image。

 The background image functions very similar。 So we'll just look at this one。

We'll see that there's a global variable used for each image。

 The foreground image is referenced by the global variable FG image Here。

 you see that FG image is initialized to null。 Iitializing global variables is a good idea。

Using Nll will allow us to determine if an image has been loaded when the user clicks the Create compositeos button。

 for example。Nll is a special value used in JavaScript and other languages to represent nothing。

You'll see this idea again later and with other programming languages。

Here we see that the code that accesses FG image。 notice it doesn't use the word var because the variable FG image is global。

The variable is assigned a new simple image element created from the file input element。

Here we see FG element used again to draw to the canvas element。

That will be displayed on the web page。We will also use many local variables like Vr IMG file。

 it references the file input for the foreground image。

 we use that HTML element because it's passed as a parameter when we create the simple image。

Using local variables with the word var is a really good idea。Here。

 the local variable represents the canvas where the foreground image will be displayed when value is accessed in multiple functions。

 making a global is required。Otherwise， make variables local to avoid losing track when you have hundreds of variables which might happen in the mini project。

Let's look at the JavaScript code to create the green screen composite。

We're going to look at the steps to create the green screen composite。

Willll need some basic ideas from。Image processing that you've seen in the Duke Learn to program environment。

We've adapted these for use in a web page when the user uploads an image and then processes the image。

 For example， we need to check that the user has uploaded two images。Before clicking。

 the create composite button。We accomplish this by checking to be sure that the foreground image is ready to go。

If the global variable FG image is null。The value it's initialized to when it was made global。

 then the user hasn't clicked the upload foreground image button we just saw。

Because that JavaScript creates a non null version。For FG image。

It's also possible that the user has uploaded the image。

 but the image hasn't been completely constructed， large images take time to create。

The method dot complete allows us to determine if the image is completely loaded here。

 it says not complete。 That's the bang or exclamation point。

 And if it's not ready because either it's null or it hasn't finished loading。

 we'll need to let the user know。 We do this by displaying an alert， indicating the code won't work。

We check both the foreground image。And we check the background image。

Before creating the green screen composite。Now let's look more closely at the code to create the composite。



![](img/3ae9f22094dbbaa052fefe5814065693_6.png)

Here's the JavaScript code， adapted from the Duke Learn to program or DLTP environment to create a green screen composite。

The first step is to create a new image with the appropriate width and height。

 It will be the composite of the foreground and background image。

The new image is initially all black。So we need to set each pixel by looping over all the pixels of the foreground image and copying either a foreground pixel or a background pixel。

 depending on how green the pixel we're looping over is。

Here we see that if the pixel's green value is greater than some threshold。

 we use the background pixel in the new image we created。And if it's not greater than the threshold。

 we use the other pixel。We'll also need JavaScript to display the new image in a canvas。

Notice that the threshold variable， green threshold must be global because it's not defined here with the word VAR。

Let's look at the final steps。Well need to display or draw the new composite image to create a canvas element with the image in it。

 We'll use the dot draw to method before。Making sure that the image appears。

 we know it will because we've checked to make sure it's loaded。

And we'll clear the canvas elements before drawing so that we show only one image。

 the green screen composite。Let's take a look。Your working green screen page allows the user to interact by uploading images。

 one for the foreground。And one for the background。

We have to wait for those images to load and be displayed。Then we'll click the Cre compositeos。

And watch the green screen be created。We can see that the button stays clicked。

 it takes some time to create this composite。Then we see it riding dinosaurs， we can also clear them。

 There are no dinosaurs。 Where did they go， We know that combining two people and dinosaurs can be lots of fun。

😊，You will also get to have lots of fun when you use the green screen program to create your own green screen composites。

Have fun with programming。

![](img/3ae9f22094dbbaa052fefe5814065693_8.png)