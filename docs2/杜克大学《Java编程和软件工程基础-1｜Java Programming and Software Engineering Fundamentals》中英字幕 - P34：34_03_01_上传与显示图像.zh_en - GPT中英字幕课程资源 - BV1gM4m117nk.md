# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P34：34_03_01_上传与显示图像.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/c23209ebfc002bd1851e006728e41cfb_0.png)

In this lesson， we'll go over a few concepts that will allow you to upload image files and display them in an HTML Can。

We'll need some new programming concepts and JavaScript tools as we move towards creating an interactive web page for the green screen algorithm。

You'll be able to create more web pages using these new concepts and tools as we move from a very simple page towards the more complex and creative green screen and mini project pages。

We'll start with a prototype， a web page that's a model of what we want。

 but is simpler to understand。We'll need a new type of input element to upload our image files。

 but we'll start with a simple idea in this first prototype so we can concentrate on the idea rather than the details of the new HTML element。

A simpler input type would be text input， which will display a text box like the one you see here that allows the user to type text。

We'll test and understand the concepts with the prototype reviewing the JavaScript for processing this and any other HTML element。

Then we'll change the input type to file and we'll introduce concepts needed to upload an image file and display it in an HTML canvas。

Let's look at this prototype to understand the web page and the JavaScript。

 The HTML text input element allows the user to enter any text。As you can see in this simple page。

 the user has entered Lion。 JpeEg and is about to click the button。

Here we'll use a button to process an event。 It's possible to process text when the user presses the enter key。

 but we'll use a button since they're familiar。As usual。

 when the user clicks the button to generate an event， We'll write jascript to handle that event。

 Here's that， using the on clickicked event handler。

Here's the JavaScript to process what the user entered。

We use familiar JavaScript to access the value of the text input element and display that result in an alert box。

 So when the user clicks upload， the alert box pops up。Remember， this is an example of text input。

 The input element doesn't care if we enter a file name。 We could have entered any text。

 When we change to the input type to file， we will be guaranteed that the value we get represents an actual file。

 though， as we'll see soon， we will need to do some work to ensure that that file is an image。

Let's look at some new concepts。We'll use the last pen as a model and extend that prototype to a web page that allows the user to choose an image file。

 upload it， and display it in the web page。We'll replace the two inputs of type text and button with a single input of type file。

We'll create an image from the file chosen by the user and uploaded This will be a simple image from the Duke Learn to Program library that you've worked with before。

You'll create the web page by extending the functionality we saw in the prototype。

Starting with something familiar helps with understanding the new concepts。 in this case。

 the file input and a library of JavaScript code。Starting with something familiar also helps with debugging since we start with a working web page and working JavaScript。

Let's look at how HTML and JavaScript combine to allow you to upload and display an image。

Here's the HTML for specifying an input element that allows the user to choose a file and upload it to a website。

You'll use file rather than button or color as a type of the input。

You'll make sure the user only uploads one file， not several by using the multiple attribute and making it false。

 signifying that multiple files cannot be chosen。You'll only allow the user to select image files。

 not text files， and not audio files， for example。You do this by specifying a value for x。

 the except attribute。 The value is image slash star， as shown here， star meaning all image types。

 not just Jpegs， for example。As usual， you will provide an input to make it possible to find this element within your JavaScript code。

You'll use on change for the event handler。 This event is triggered when the user chooses a file by clicking the button displayed on the input element。

Note， you do not need to add the button element。 it's included with the file input type。

Here is what the user sees when she clicks on Choose files。

A file selector appears this one only allows image files；

 yours may look different since different browsers handle this restriction differently。

And once the image Lionon Jpeg is selected， the file input is changed to contain the file。

This triggers the on change event handler。 So let's see what the upload function should look like in order to achieve our goal of displaying the image in our canvas element。

The upload function gets the canvasvas element and the file input element each by its ID specified in the HTML。

Then you'll create a simple image variable from the HTML file input itself。Wait。

 simple image is not a standard JavaScript。 It's a library of JavaScript code created for this course and hosted at Dukeleearerprogramcom。

The code is automatically included when you use our custom JavaScript environment。

But for web pages you create， you need to specify the source of this library。

Let's see where to do that in CodeP。In your editing view for the CodeP page。

 the source for JavaScript goes in the HTML panel， not the JavaScript panel。

 enclosed in open and closedsed script tags with the attribute SRC for source。

You can see the last part of the URL is simpleimage。js。

 because that is the library we want the page to be able to use。Outside of Code Pen。

 you would also use the script tag Here is the code that includes the simple image JS library from our Duke Learn program site。

Now that we know how to tell a web page， where to find our JavaScript code。

 let's finish putting an image in the canvas。We have just created a new simple image from the file input HTML element。

The last step is to use the draw to method， a method included in a simple image library。

We will call image。raw to and use the canvasvas element as the parameter to indicate the simple image should be drawn on a specific canvas of our choosing。

As always， you should try not to memorize all of these methods。

 You can consult the documentation at any time， like this documentation from Dukeleerprogram com。

Now let's see the upload function in action。As you can see。

 when Lion do Jpeg is selected as file input， the file selector is changed and the on change event handler is triggered for this event。

 that is the upload function， which displays the selected image on a web page by drawing it to an HTML canvas。

Now you can create web pages that allow users to upload images too。

