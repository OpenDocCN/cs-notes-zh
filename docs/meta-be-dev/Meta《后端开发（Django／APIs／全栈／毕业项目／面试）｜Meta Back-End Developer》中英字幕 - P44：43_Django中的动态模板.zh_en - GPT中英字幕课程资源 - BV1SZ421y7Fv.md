# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P44：43_Django中的动态模板.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

In this video， you will learn how to use templates to return a web page with dynamic data to display a menu for a little lemon。

You will explore how to create templates and use them to get data from a dictionary and display it on a web page you will also learn to display data using a for loop with a dictionary inside a template。



![](img/41d984d2170fa4e70894eec97ec9e2d6_1.png)

First， I open my apps View that P file。Next， I create a view function that takes the request object as a parameter。

I create a dictionary inside the function by adding open and closed curly braces。

Then I define name as the key and give it the value of Greek salad。

I now need to assign the dictionary to a variable， which I'll call menu item。Okay。

 so the code for the dictionary is complete， but this time， instead of returning an HTTP response。

 I will use the render function。So inside the parentheses of the render function。

 I pass three parameters， first the request object and then the name of the HTML file。

 and finally the variable that holds the dictionary。

It's helpful to think that a Python dictionary is similar to a JSO object commonly used in web development。

So my code is set up to work with the Temp file menu。htm， so I need to create this now。

Back in the project directory， I create a new folder called templateemps and inside it create a new file called menu。

html。I open this file and now I want to write the code to dynamically display the dictionary object to do this I start by creating double curly braces and inside them I pass the key of the dictionary。

 which in this example is name。I then save the file。To ensure that Djago finds the menu HTML file。

 I need to open the settings file and add the name of the templates folder inside the templates list。

I also need to make sure that I have registered the app in the installed apps list。

The final step I need to perform is to open the URLs。pi file and inside the URL patterns list。

 I add the path function。I then pass the URL I want to map to。

 so I type menu forward slash and then the name of the view function to be called， and this is views。

 menu。Okay， so I'm happy with my code， let me run the server and open the URL in the browser。



![](img/41d984d2170fa4e70894eec97ec9e2d6_3.png)

I navigate to the menu page and notice that the value stored in the dictionary is displayed in the browser。

It's important to know that the values held in the dictionary are the content that will display on the web page。

 and this is the logic I create in the code by passing the dictionary key in the HTML template。

 And this is an example of returning dynamic content to a web page。

 If the value in the dictionary updates， so will the value displayed on the web page。

 and I can add as many key value pairs inside the dictionary as I want to。

I can even wrap this content inside HTML tags and you'll learn more about this soon By now。

 you know that injango developers can use templates to make a static page dynamic。

The layout of the page can be structured with HTML。

 and the dynamic data is then placed inside the double curly braces。

The double curly braces imply the dynamic content and it's something that is called Djago's template language。



![](img/41d984d2170fa4e70894eec97ec9e2d6_5.png)

Let me expand on this concept a little more now back in the views。 P file。

 I will replace the dictionary with an object containing some more values。

This is a little more complex notice that mains is the key and then a list of dictionaries is the value。

Insight each dictionary are two key value pairs with name and price as the keys。

Notice that I have assigned this to a variable called New menu。

 which is passed inside the render function。So to display this in the browser。

 I will have to update the code and logic in the menu HTML file。Inside menu。htm。

 I remove the existing code。Next， inside a set of single curly braces with a double percentage symbols。

 I need to loop over each item in the dictionary using a for loop。

 so I type four and then item in mains， which is the dictionary's name。

Next inside a set of double curly braces， I type item。t name and then add item dot price。Finally。

 I need to close the fort loop。Okay， so my code looks good。

 I save the file and then open the browser and refresh the page。



![](img/41d984d2170fa4e70894eec97ec9e2d6_7.png)

Notice that the items from the dictionary are displayed while the code works。

 I want each menu item to be displayed on a new line to do this， I can add some HTML。

 so back in menu HTML I pay some HTML table tags with inline styling applied。



![](img/41d984d2170fa4e70894eec97ec9e2d6_9.png)

Now when I refresh the page， notice that the menu displays inside a table。



![](img/41d984d2170fa4e70894eec97ec9e2d6_11.png)

So now I should be able to add another dictionary and the content will update on the web page。



![](img/41d984d2170fa4e70894eec97ec9e2d6_13.png)

Back in the views。 pie file， I add another item hummus with a price of five。



![](img/41d984d2170fa4e70894eec97ec9e2d6_15.png)

I save the file and refresh the page。Notice that the values are updated dynamically on the web page。

This is how you can create programming logic and apply it to templates to render dynamic data on a web page using Django In these examples I demonstrated the rendering of dynamic data using a dictionary as the data source。

It's important to know that this data source can be other things like a database or an API。

 and you'll learn how to do that soon。

![](img/41d984d2170fa4e70894eec97ec9e2d6_17.png)

In this video， you learned how to return a web page with dynamic data using templates。



![](img/41d984d2170fa4e70894eec97ec9e2d6_19.png)