# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P11：10_JSX 简介.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

At this point in the course， you've been introduced to the concept of JSX and how it's used to interact with components。

In this video you'll explore JSX in more detail in the context of component and styling you'll also learn how to mix JavaScript。

 HTML and CSS within a component So what is it that makes JSX so special？



![](img/921471368b50c177dcd90eb8edb48581_1.png)

![](img/921471368b50c177dcd90eb8edb48581_2.png)

![](img/921471368b50c177dcd90eb8edb48581_3.png)

In one word， expressiveness。Developers can express what they want react to render using a very expressive syntax almost identical to HTML or X In other words。

 JSX allows developers to write HTML directly inside JavaScripts code for example。

 you can add a navigation function to a website by creating a nav component。



![](img/921471368b50c177dcd90eb8edb48581_5.png)

![](img/921471368b50c177dcd90eb8edb48581_6.png)

![](img/921471368b50c177dcd90eb8edb48581_7.png)

Then place the HTML semantic nav element and an unored list inside。



![](img/921471368b50c177dcd90eb8edb48581_9.png)

And because this is react， the list values can be made dynamic by passing values as props。



![](img/921471368b50c177dcd90eb8edb48581_11.png)

It's important to know that a regular JavaScript function is used to define how react should render the component。

 wherever it's referenced using the Nv JSX element， and this is what makes JSX so powerful。

 like the fact that you can insert specific JSX expressions such as variables and props。



![](img/921471368b50c177dcd90eb8edb48581_13.png)

![](img/921471368b50c177dcd90eb8edb48581_14.png)

![](img/921471368b50c177dcd90eb8edb48581_15.png)

![](img/921471368b50c177dcd90eb8edb48581_16.png)

The reason why this is so great to work with is because anything that's placed inside the curly braces of your code is essentially regular JavaScript code for example you could calculate a series of simple expressions using the LI or list item tag this means that you can think of the curly braces as being special areas where you can write any kind of JavaScript code you like and you can write the rest of the code inside the return statement。



![](img/921471368b50c177dcd90eb8edb48581_18.png)

![](img/921471368b50c177dcd90eb8edb48581_19.png)

![](img/921471368b50c177dcd90eb8edb48581_20.png)

![](img/921471368b50c177dcd90eb8edb48581_21.png)

![](img/921471368b50c177dcd90eb8edb48581_22.png)

Okay so now that you have learned a little more about JSX expressions。

 let's focus on some JSX rules inside the return statement of the function The return statement can be thought of as the area of expressive syntax so that allows you to write regular HTML code as you'd like to have it in your rendered app but if you need to return HTML code over multiple lines it must be placed inside parentheses This allows developers to alternate between regular HTML tags and dynamic values represented as JSX expressions inside curly braces it's also important to remember that the HTML code must be wrapped in a toplevel element such as a div tag if you do not want to add extra div elements to the dom you can use something called a fragment instead。



![](img/921471368b50c177dcd90eb8edb48581_24.png)

![](img/921471368b50c177dcd90eb8edb48581_25.png)

![](img/921471368b50c177dcd90eb8edb48581_26.png)

![](img/921471368b50c177dcd90eb8edb48581_27.png)

![](img/921471368b50c177dcd90eb8edb48581_28.png)

![](img/921471368b50c177dcd90eb8edb48581_29.png)

![](img/921471368b50c177dcd90eb8edb48581_30.png)

![](img/921471368b50c177dcd90eb8edb48581_31.png)

This is like an HTML open and close tag without the tag name while you can think of the code inside the return statement as regular HTML it's worth remembering you are in a JavaScript file and as a result there are some differences for example you cannot use the keyword class to work with CSS classes in your HTML elements this is because class is a reserved keyword in JavaScript you must use a slightly different keyword called class name instead。



![](img/921471368b50c177dcd90eb8edb48581_33.png)

![](img/921471368b50c177dcd90eb8edb48581_34.png)

![](img/921471368b50c177dcd90eb8edb48581_35.png)

![](img/921471368b50c177dcd90eb8edb48581_36.png)

Also notice that class name is written in Caml case which depicts the separation of words by using a single capitalized letter。

 you can use class name to list any number of CSS classes to style a specific JSX element inside a component。



![](img/921471368b50c177dcd90eb8edb48581_38.png)

![](img/921471368b50c177dcd90eb8edb48581_39.png)

![](img/921471368b50c177dcd90eb8edb48581_40.png)

![](img/921471368b50c177dcd90eb8edb48581_41.png)

This is just like how you use the class attributes in regular HTML and it's only one of the many ways you can star react apps You'll learn more about how to do this later For now just know that this is the closest to what you would do like if you were working with HTML and CSS website layouts there are some other differences and you'll learn about them later but in practical terms you can consider the code to be pretty much just like regular HTML In this lesson you explored further the concept of JSX styling and how it's used in react you have now furthered your understanding of how to use JSX to mix JavaScript HTML and CSS within a component great work。



![](img/921471368b50c177dcd90eb8edb48581_43.png)

![](img/921471368b50c177dcd90eb8edb48581_44.png)