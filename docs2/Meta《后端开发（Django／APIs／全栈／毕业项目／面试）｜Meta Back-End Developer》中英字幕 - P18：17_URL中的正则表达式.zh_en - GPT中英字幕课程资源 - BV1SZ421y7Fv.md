# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P18：17_URL中的正则表达式.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

By now you should be familiar with the concept of mapping URLs with parameters in Django。

Jiango lets you design URLs however you want， and you do this by using the path function and path converters。

For example， creating a custom URL with dynamic values。😊，For more complex matching requirements。

 you can define your own path converters using something called regular expressions。In this video。

 you will learn how to use regular expressions to define URL patterns in Django。

Suppose you have been tasked to create a menu item page for the little Limon website。

The page displays content for each item on the menu。

Instead of making a specific page for each menu item。

 you can define the dynamic URL structure that would pass the menu item ID to the view function。



![](img/934990f0064baa7a6fcb5c981ab6e81c_1.png)

The content of the page will depend on the menu item value passed to the view function from the URL。

Based on the ID value passed in the URL， the logic in the View function will determine what type of data to display。

 like a menu item name。The advantage for developers is that they only need to create one page。

Instead of creating individual static pages for each menu item。

 developers only need to create one page whose content updates dynamically based on the values passed in the URL。



![](img/934990f0064baa7a6fcb5c981ab6e81c_3.png)

However， to ensure that the URL is structured in the way that the view function requires。

 you need a way to define and verify the values and format of the URL。



![](img/934990f0064baa7a6fcb5c981ab6e81c_5.png)

To verify that the URL values passed to the view function are correct。

 you can use regular expressions。Regular expressions are Regg X are a set of characters that specify a pattern and are used to search for our fine patterns in a string。



![](img/934990f0064baa7a6fcb5c981ab6e81c_7.png)

They are a powerful tool that developers use to perform extraction and validation。

 advanced searching， group searches， and find and replace operations。



![](img/934990f0064baa7a6fcb5c981ab6e81c_9.png)

![](img/934990f0064baa7a6fcb5c981ab6e81c_10.png)

![](img/934990f0064baa7a6fcb5c981ab6e81c_11.png)

In Django， developers use regular expressions to define。

 extract and validate dynamic URL paths before they are sent to the associated view function。



![](img/934990f0064baa7a6fcb5c981ab6e81c_13.png)

This video focuses on using regular expressions in Django URL paths。However。

 it's important to know that regular expressions are not specific to Python or Django。

They have many uses across various areas of computer programming and software development。

Regular expressions and their associated characters are universal。

 meaning they are the same across all programming languages。



![](img/934990f0064baa7a6fcb5c981ab6e81c_15.png)

Let's begin by exploring an example of a URL pattern containing two entries in the URLs。pi file。

The first path is constructed using a regular URL and the second with a regular expression path。

Let's step through the cold line by line。First， you import two functions。

 path and regular expression path from the Django dot URLs module。



![](img/934990f0064baa7a6fcb5c981ab6e81c_17.png)

Regular expression path is used for paths that need to contain a regular expression。



![](img/934990f0064baa7a6fcb5c981ab6e81c_19.png)

Inside the URL Pat sequence， there are two entries。

This example will only explore the first argument passed inside these functions。



![](img/934990f0064baa7a6fcb5c981ab6e81c_21.png)

Notice that the first path contains the URL string of menu item forward slash 10。

This string is static and immutable， which means it has no possible numerical variations。

 even if in the same format。

![](img/934990f0064baa7a6fcb5c981ab6e81c_23.png)

For example， if you enter a URL such as menu item forward slash1。

 it will not match this path and map to the view。As a result。

 a 404 not found error message will be displayed you can accept all URLs in this format using the regular expression path function。

 like in the second entry。

![](img/934990f0064baa7a6fcb5c981ab6e81c_25.png)

![](img/934990f0064baa7a6fcb5c981ab6e81c_26.png)

Notosis the character are at the beginning。This makes a raw string which treats the backslash as symbols as literal characters and not escape characters。



![](img/934990f0064baa7a6fcb5c981ab6e81c_28.png)

Let's explore some of the most common symbols used。

First is the carrot symbol used as the anchor at the start of the string。

It can also be used for negation。Next is the dollar symbol。

 which is used as the anchor for the end of the string。

You use opening and closing square brackets to define a character set that matches any one of the characters present inside。

Next， opening and closing curly brackets are used to specify the exact number of preceding characters。



![](img/934990f0064baa7a6fcb5c981ab6e81c_30.png)

Finally， opening and closing parenthesis are used for grouping parts of the rex。



![](img/934990f0064baa7a6fcb5c981ab6e81c_32.png)

Now that you are familiar with some of the characters， you can use them in regular expressions。

 let's revisit the URL structure from the little lemon menu example。😊。

The URL begins with a string with the word menu item。Then it's followed by a forward slash。

 followed by parenthesis for grouping。Inside the parenthesis exists two occurrences of numbers between  zero to nine。

Outside the parenthesis is another forward slash， followed by the dollar symbol to inch the strain。



![](img/934990f0064baa7a6fcb5c981ab6e81c_34.png)

Acceptable strings for this rex can be menu item forward slash followed by the range 1 to 99。



![](img/934990f0064baa7a6fcb5c981ab6e81c_36.png)

Regular expressions are extremely useful while creating URLs， but at the same time。

 they can often get complex。And this is especially true for regular expressions containing several special characters。

😊，It's common for aspiring developers to feel confused when first learning regular expressions。



![](img/934990f0064baa7a6fcb5c981ab6e81c_38.png)

Sometimes a symbol can be used for one or more purposes。

 or the same symbol can behave differently depending on the case。



![](img/934990f0064baa7a6fcb5c981ab6e81c_40.png)

Getting familiar with their usage requires some practice and a little patience。



![](img/934990f0064baa7a6fcb5c981ab6e81c_42.png)

It's advisable to start with the example in this video and build your knowledge using the remaining readings and exercises in this lesson。



![](img/934990f0064baa7a6fcb5c981ab6e81c_44.png)

In this video you learned about regular expressions and how developers use them to create and validate dynamic URLs in Django If you would like to learn more about regular expressions。

 there is a link in the additional reading at the end of this lesson。

