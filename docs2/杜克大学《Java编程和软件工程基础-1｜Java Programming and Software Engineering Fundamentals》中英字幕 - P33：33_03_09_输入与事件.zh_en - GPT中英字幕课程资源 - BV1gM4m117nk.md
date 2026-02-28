# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P33：33_03_09_输入与事件.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/c09f47bb1558695ceb2f09a1444dd454_0.png)

In this lesson， you're going to learn about new HTML input types and events。

 You've already seen the button input type with the oncl event。

 and now you will learn how to use additional input types of events to make your web pages even more interactive。



![](img/c09f47bb1558695ceb2f09a1444dd454_2.png)

![](img/c09f47bb1558695ceb2f09a1444dd454_3.png)

As you have seen， the HTML input tag is used to create an HTML element like a button that gets input from the user and processes that input with JavaScript code。

You have already used a button to get input from the user。

 but you can also create web pages that ask for text input。

You've likely seen web pages in which you enter a name or a password or a URL。

 You can present the user with a color picker tool， such as this one。

Or a range which gets information from the slider， both of which you'll see in this lesson。

There are many other options you can find in the documentation for the HTML input element。

In the case of a button， the input is the user clicking on the button。The on click event。

 But as you'll see here， there are other events that you can connect to a button or another type of input。

For example， here is an article on the Duke Today website。

 The content highlights when the mouse rolls over it。

The on mouse enter and on mouse leave events are used to have the browser execute any function you connect when the mouse enters or leaves an object。

Changes to a field or input can also be useful events。

Here is an example of a search function executing on the Duke Today website as user input is typed in to look for articles about Duke's Kunshan University。

A color picker or color chooser allows the user to choose colors as part of interacting with the web page。

 The color can be specified by name， by using sliders， or selecting RGB values。Or more。

Note the color was introduced with HTML 5 and new input types that are not supported by older web browsers will behave simply as input text types。

Let's look more closely at how a color picker or chooser works。

Herere is the input tag which you have seen before，The type for a color chooser is color。

And here we have specified a default value of dark blue。

This color picker element has an ID so that we can refer to it in our JavaScript code and represent its input with a variable。

Many inputs require connecting events other than mouse clicks or moves。

 A color chooser uses an on change event。 This may be connected to a mouse。

 but isn't based on clicks just when the color chooser's value changes。

This event is connected to JavaScript through the onchan event handler。Now。

 let's look at the function do color。This function can be named anything。

 but must match the name you specified in the HTML input element。

Accessing the color picker value in the JavaScript code uses functions and concepts that you may recognize。

First， the canvas element is stored in variable D D1， as you have seen before。

Then the color picker element is stored in the color input variable。

 using the same technique to find the element in the document。

As before you can choose any name you want for your variable names。

 but the IDs given in the strings must match those IDs given in the HTML elements。

The value of the color chooser is accessed using the dot value attribute or field of the color Chor HTML element stored in the variable color input。

Next， we use the dot style attribute to set the background color of the canvas to whatever color the color picker is currently set to。

The basics are the same here as they are with a button input。

 connect JavaScript code to an event using the HTML input element and the appropriate event handler。

Let's see the color picker in action。The make line button still works。Now。

 clicking or moving the pressed mouse button over the color options will change the color shown in the color chooser dialog。

 pressing down on the mouse will change the active color in the color chooser and generate an on change event。

This event is also generated if you keep the mouse pressed down and move it over the colored pencils。

When the mouse is down， a color change event can be generated。

What happens if we change the event we are responding to from on change to on click。Now。

 clicking on the color picker with its default of dark blue changes the canvas background。

 whereasas it did not for the on change event， because the element had not been changed。

 In this case， changing the color chooser does not change the canvas color until we click on the color picker element itself。

This is the difference between the on change and on click events for an HTML input element。

Let's look at one more type of HTML input and the events it uses the range or slider input here。

 the slider is horizontal and has a label of text indicating its purpose is to make a square using a slider。

As a slider is moved， a square is drawn with side lengths determined by the value of the slider。

 The square can be made larger or smaller as the user drags a slider， right or left。

The HTML to create this slider has an input type of range with three parameters you specify when creating the HTML element。

 the minimum value of the range here that's 10。The maximum value of the range here that's 100。

And the current value when the slider is first rendered in a web page here That's 10。

 which happens to be the minimum value。 So the slider will be first rendered all the way to the left。

The ID of the input element is important for accessing its value to use in the function do square。

When you click and drag the slider， you generate an on input event that you can use to connect the web page with your JavaScript。

 Let's look more closely at the function do square now。This is the function do square。

 which draws a square with side length given by the range input。As before。

 we store a reference to the canvas in a variable。Then we use the ID for the slider element to create a variable size input representing the slider。

We get the value of the slider element and store it in the variable size。As you have seen before。

 we need to get the context of the canvas in order to draw in it。Finally。

 we use the size input from the slider to draw a yellow rectangle starting at the coordinates 1010。

 whose side lengths are determined by the size variable。Let's see what this code does。H。

 the square can be made larger with a slider， but it doesn't seem to get smaller。

This is because each time the on input event handler calls the do square function。

 it draws another square， one on top of the other， but the old ones are not cleared。Luckily。

 there is an attribute for the context that can clear a previous drawing。

Dot clearre will clear a rectangle given four parameters。

2 for the top left coordinates of the rectangle， and then its width and height for simplicity here。

 we will clear the entire canvas each time do square is called。That's better。 Now。

 the square resizes with the user input from the slider。Now you know how to use new types of input。

 the color chooser and the slider， and you know new types of events to use with them on change and on input。

Have fun as you continue to make interactive web pages。

