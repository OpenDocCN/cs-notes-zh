# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P12：12_01_02_CSS基础.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/c8a935bec75a1af873df64b602e8708f_0.png)

Now you're going to learn a bit more about CSS。Last time you learned why you would want to use CSS to separate the style of a web page from the content。

 which touched on some major themes in computer science。



![](img/c8a935bec75a1af873df64b602e8708f_2.png)

One of those themes was reusability。 You can describe a style once in CSS and reuse it across multiple elements or even multiple web pages。

Another of those themes was maintainability， being able to efficiently change your web page in response to changing design requirements。

Now that you have learned a bit about why CSS is important。

 we are going to build on that and delve into how you can write your own CSS to style a web page。

Before you learn what to write for CSS， we are going to teach you where to write it。In Code pin。

 you've been writing HTML in the left pane to the right is the CSS pane。

Which I have highlighted with a blue square here。You can identify it by the fact that it says。

CSS in the top left corner of that pane。 Also， don't worry about the slightly fancy CSsS in this window。

 It makes a nice looking table， but you only need to learn the basics。

If you were writing a web page from scratch without a tool like code pinned。

 you could include CSS by either using the style tag and writing the CSS inside it or by using the link tag to link to a style sheet。

 Either of these tags go in the head portion of your HTML。

We will start with a small example web page shown above， which describes some delicious foods。

On the left， you can see the web page with no CsS。 notice as how the header drawn by the H1 tag is in black text and left aligned。

 Now， suppose that you wanted to make that header blue and center like the one on the right。

This page on the right has the same HTML， but we have used CS to change the formatting of the H1 tag。

Here is the CSS we use to style the H1 tag to be blue and centered。

 Let's look at it in detail so you can write your own CSS to style the pages however you want。

The first thing you need to write is the selector。 the name of the element that you want to style。

In this case， we wanted to style H1 tags， so we write H1 here。

Next you write curly braces which surround the style information you want to apply to the H1 tag。

When you write an open curly brace and code pin， it will automatically put a closed curly brace after it and put your cursor between them。

 This behavior can be helpful， as you do not have to remember to write the clothes curly brace after you finish writing the style you want。

😊，On each line inside the curly braces， you first write the property。

 what aspect of the styling you want to change。Here we want to change the text alignment。

 which has the property name， text align。After the property name， you write a colon。

Followed by the value you want to give that property。In this case。

 we want to set textex align to center。At the end of the line， you write a semicolon。

 you can then write more lines with the same syntax。 For example， we have color， colon， blue。

 semicolon to set the color property to blue。There are many properties you can set in CSS。

 We won't go into all of them here， but rather suggest you might read more about them online as you need them。

 as with many things you should not try to memorize them， rather look them up as you need them。

If you end up writing a lot of CSS， you will become familiar with the properties that you use often。

In your NVIo quiz， you just thought about how this CSS styles list items to be green。However。

 this CSS makes all list items in your entire webp page screen。

What if you wanted to make some of them green and style some of them a different way？

We're going to show you three approaches to styling only some of a particular element。

The first way you might do this is to use a class， a named style。To use the CSS class。

 you need to change your HTML by writing class equals and the name of the class you want in the tags you want to style。

Now in your CSS， instead of running the name of an HTML tag at a selector。

 write a dot followed by the name of the class。The dot specifies that you are naming a class。

Immediately after the dot， you should write the name you want to give the class。

 This name can be pretty much anything you want。It has to follow some rules like you can't put braces or spaces in the name。

 but you can't pick anywhere word you want for a name。 However， you should make the name descriptive。

In this example， we picked food LI， since we're using the class to style list items that describe food。

Would Dot Green be a good name for this class？Even though that describes how it styles the list items right now。

 Naming it dot green is not a great choice。 If we later decided we wanted to style our food list items to be purple。

 our style name would be misleading。 Instead， we're better off naming it based on the meaning of the parts of our page。

 and we want to style food list items。If you look back at the HTML， now that you've seen the CSS。

 you can see where the name we picked came from， it matches up with the class name we picked in our CSS。

Another way to sell only some of a particular element type is to use an ID。

 an ID names one particular element， notice the difference between a class which can be applied to many elements and an ID which can only be applied to one element。

In this example， the webpage has a picture of a cake， which we want to style in a particular way。

 we have specified ID equals cake IMG inside the IMG tag。Now in the CSS。

 we can describe the styling for cake IMG， notice how the selector for an ID starts with a pound sign。

The final way that we will mention， but not go into depthon is called combbininators。

 These let you specify relationships between tags。 You might specify that you want to style Ls that are inside of U Ls in a particular way。

 which you could do by writing U L， L I as the selector。

There are more advanced relationships such as siblings。 Cominators are a more advanced topic。

 which you do not need to know， but we mention it for those of you who want to explore a bit more。

Classes and IDs both let you name a way to style and element。

Naming a style lets you reuse that style as needed。In the case of a class。

 you can style many elements on a page in the same way。For both names and classes。

 you can reuse a style across multiple pages。For example。

 if you have a logo that you want to display in the corner of every page on your site。

 you can write a style for it once and reuse that style on every page。

Naming and reusing is a common theme in computer science as you delve deeper into programming。

 you will find that it is often useful to name things， constants。

 algorithms or data so that you can reuse them。Now you have seen the basics of CSS。

 you've learned where to write CSS and CodeP， the basic syntax of CSS。

 and how to make classes and IDs to name and reuse styles。

