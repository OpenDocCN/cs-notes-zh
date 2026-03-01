# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P31：31_03_04_交互式页面切换.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/23a9522d6948480123971790a4343eca_0.png)

Let's look at how to change a web page interactively using jascript。

 This interactivity will be the basis for programming a green screen algorithm in a web page and for being creative in designing your own web page to change a page。

 you'll need to write jascript code to access elements like H1 tags or div elements or other tagged elements in a page。

 It's possible to access all the elements with an H1 tag， for example。

 or with an li tag or any other HTML tag。 It's also possible to access individual elements by an I or a group of elements by a class。

 We' mostly use IDs to access HTML elements since Is are distinct and every element must have a distinct I In contrast。

 many elements can share the same class In our examples。

 you'll see how to add a CSS class to an HTML element like a div。

 This will allow you to change the background color or the width or the height of an element。

It's also possible to change the text displayed in an element or other features。

 Let's look at a simple example of changing a web page using interactive JavaScript。

 We'll use two CSS classes each specify a different background color for a div。By clicking a button。

 you'll use JavaScript to assign a CSS class to each div。

 making the divs change appearance and go from no background color to different background colors。

 The basic idea is to programmatically access each div using the IDs and change the CSS associated with the div。

We'll explore this at a high level and then look at the details。 Here you saw the divs change color。

You may remember that each div has a different ID， one which displays hello， has the ID D1。

 as you can see here， the other which displays goodbye has the ID D2。😡。

Recall that the oncl event attribute tells the page to create an event handler to execute the jascript code that follows。

 You'll be able to use jascript to access the div or whatever other element you tagged with the I D1。

 that makes it possible to change the features of an element， as we'll see。In this example。

 the JavaScript function is called change color。Let's take a look at that function by looking at the JavaScript。

The JavaScript function change color is shown here。

Remember that it's called when the user clicks on the button that is interacts with the web page。

 the JavaScript function is change color。😡，Remember that it's called when the user interacts with the web page because its function is called or invoked by the onclick event handler。

 which calls the function change color， the JavaScript method get element by ID is used to access an HTML element using its associated ID。

You may remember that a method performs an operation on an object and is preceded by a dot。

 In this case， the method get element by ID uses the HTML document to access its element。

 The label document refers to the entire HTML webp page。

 The get element by ID method has one parameter here it' D1。

 The ID label associated with a particular HTML element。😡。

The get element by ID method returns this HTML element with the ID label that was passed as a parameter。

 that's the div element with the word hellello because the associated ID label is D1。

We need to create a variable to store this returned HTML element here that's shown by Var DD1。

Now that variable can be used to access the element and change its color。

The next line creates a similar variable called DD2。

 This stores the HTML element returned by document。ge element by ID when it's past the parameter D2。

Next， to change the background colors used in this page。

 we need to set the background color for each div。We'll do this by setting the CSS class for the DV。

The line of code DD1。 class name gets blue back is what changes the color of the div with the IDD1。😡。

Remember， this div was stored in the variable DD1。The attribute class name is one of the characteristics of an HTML element that can be accessed in JavaScript。

 As we'll see in later examples， there are many other attributes of HTML elements that you can also change by accessing them with JavaScript。

 These attributes are sometimes called fields。 They're accessed using the dot notation in a JavaScript program。

The code assigns the class nameBback as the class of the div stored in variable DD1。😡。

As you can see in the CSS panel of the code pen page that we've shown here。

 the class blueback has a specific background color。

If other CSS characteristics were part of this class blueback。

 these characteristics would also be part of the div labeled D1 as a result of assigning the class blueback to the variable DD1 in JavaScript。

 the next line similarly assigns the class yellow back to the variable DD2 which is storing the HTML element with ID D2。

 again in action using the on-click event handler to call the JavaScript function change color。

 assigns these CSS classes to the chosen HTML elements， and we see the background change。

It's also possible to change other attributes of HTML elements like the text associated with an element。

 This function change text uses a very similar approach to what we just saw with changed color。

The first two lines create variables to store HTML elements。

 and these are exactly the same lines as we just saw with change color。

Just as before to access or access attributes of an HTML element。

 you'll use the dot syntax and the name of an attribute or field that will be used in JavaScript。😡。

The attribute shown here，in HTML accesses the HTML content within the element。In this case。

 that's everything inside the div， which is text。 This line of code DD1 do inner HTML gets Bnjour。

 changes the text of the HTML element accessed by the variable DD1。😡。

That's the same HTML element whose ID is D1， which used to show the word hello before the code executed。

 and will now show Bnjour after the code runs， it's worth pointing out that while DD1 is an HTML element。

A div specifically in this case。 in general， it's just an object。

 like a CSS style or simple image are objects。 You can always use documentation to find out what methods operate on different objects In actions here you can see what happens when you click on the change text button An unclicked event handler calls change text。

 the JavaScriptscript function we just saw， which accesses the HTML inside the divs and sets it to new text。

 Bnjour and cara。We'll provide some resources to show how you access other attributes using JavaScript as you practice making web pages and changing them interactively。

 Bonjour and Saionara。