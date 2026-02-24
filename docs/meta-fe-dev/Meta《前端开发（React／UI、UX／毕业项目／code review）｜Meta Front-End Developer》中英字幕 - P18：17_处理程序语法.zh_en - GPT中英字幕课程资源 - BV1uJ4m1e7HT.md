# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P18：17_处理程序语法.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Every time you click or tap a button， scroll down a page or can a boring notification。

 you're producing events in the browser and as you learned earlier。

 in order for these events to have any effect you need to use event handlers that will then execute an action for example。

 suppose you use a button to open a menu clicking the button is the event the event handler is on click and the action that follows the event is opening the menu。

 there are a few approaches to adding event handlers to your react code that have different advantages so you'll become familiar with each of them。



![](img/bb207d03122096d8eaf328c4f782c9d4_1.png)

![](img/bb207d03122096d8eaf328c4f782c9d4_2.png)

By the end of this video， you'll be able to describe the syntax differences for using event handlers in HTML and React。

You will also know how to explain HTML function call and react component inclusion and discuss the advantage of the component level of control suppose you're a developer working on a react app and you need to create a button that will trigger an event when a user clicks on it with that scenario in mind let's examine some code that accomplishes this in plain HTML。



![](img/bb207d03122096d8eaf328c4f782c9d4_4.png)

You might open a tag called button with the ID JSBTN。

You then assign the oncl event handling attribute and set it equal to the click handler function。

Next， you can add click me as a button text and finish with a closing tag The code has an ID HTML attribute with a value JS button along with the event handling attribute oncl while the HTML coding the example seems pretty straightforward It's recommended to use jascript for scenarios like these instead Why is that Well you'll find out later。

 but for now you should understand that the equivalent coding jascript consists of two primary steps First you should use jascript to plug into the specific HTML element on which you'd like to listen to for an event In the previous example the HTML element is JS button which signals that it's a target element for allowing jascript to take control of the HTML structure Second once you've got an access to an HTML element with jascript you can then use the built-in add event listener method on the document object to attach a specific event listener。



![](img/bb207d03122096d8eaf328c4f782c9d4_6.png)

![](img/bb207d03122096d8eaf328c4f782c9d4_7.png)

When you apply this method to the previous example， HTML is removed from the equation。

 but the code on the other hand is a bit more complicated。Specifically。

 you need to first declare a constant called JS button and assign the value from the Dom。

 then you need to add the click listener event and the function to run the code。



![](img/bb207d03122096d8eaf328c4f782c9d4_9.png)

Going back to react， the biggest difference in syntax involves the use of the add event listener method。

😊。

![](img/bb207d03122096d8eaf328c4f782c9d4_11.png)

In react， the rule is to avoid manipulating the dom directly as much as possible。

 you should set everything up declarly， meaning that you describe updates to react and let it figure out the rest。



![](img/bb207d03122096d8eaf328c4f782c9d4_13.png)

![](img/bb207d03122096d8eaf328c4f782c9d4_14.png)

![](img/bb207d03122096d8eaf328c4f782c9d4_15.png)

This is best done using event attributes and fortunate one to one mapping between HTML event attributes and JSX event attributes means it's easier to learn Even handling and Re is overall quite similar to HTML but note that there is no function invocation syntax in event handling attributes in react In other words。

 while in plain JavaScriptscript you would need to pass an invocation to an event handling function as a value to the onclick event in Re you should not invoke a function instead you just pass a reference to the event handling function without invoking it。



![](img/bb207d03122096d8eaf328c4f782c9d4_17.png)

![](img/bb207d03122096d8eaf328c4f782c9d4_18.png)

To illustrate that point， let's compare the syntax of an HTML click handler event and its react JSX equivalent。

In HTML， you provide the event handling attribute starting with on and you append the name of the event。

All lowercase after the equal sign， you use a pair of double quotes。

 and inside of the double quote delimiters， you invoke the function that will run。

Contrary to HTML in React， you provide the event handling attribute starting with on and you append the name of the event with each words first letter capitalized。

After the equal sign you use the JSX expression delimiters that is the opening and closing curly braces and inside of the curly brace delimiters you add the name of the function to be run make sure not to invoke it Finally one more feature only use and react is the passing of function declarations as props。



![](img/bb207d03122096d8eaf328c4f782c9d4_20.png)

For example， in an app component， let's say you'd like to render a child component named counter。

You can pass some data from the app component to the counter component using a Pro in this case let's use an onclick Pro that passes in the data that you want the counter componentonent to receive and there you have it so the next time you're clicking buttons on a web page closing notifications or simply browsing through you'll understand that those events are supported by some form of event handling。



![](img/bb207d03122096d8eaf328c4f782c9d4_22.png)

In this video， you learned how to distinguish the syntax for event handling in HTML and JavaScript。

