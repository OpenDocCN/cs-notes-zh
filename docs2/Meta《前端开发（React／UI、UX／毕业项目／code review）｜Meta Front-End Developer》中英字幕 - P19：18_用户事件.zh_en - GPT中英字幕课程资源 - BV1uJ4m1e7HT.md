# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P19：18_用户事件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In this video， I'm going to demonstrate how to toggle the value of a Boolean state variable using user triggered events and how to handle multiple events on a single JSX element。

In the example that you'll explore next， the code consists of another example of a component than what you've been used to so far in the course。

The Amos demonstrates how all the event handling concepts work together with state。

 styling and the use of  ternary expressions。Let's say that you have a component that uses states to keep a Booleing value of dark mode on。

Based on whether the value of this variable is true or false。

 your component will render an H1 heading with some in it。

 either as a dark theme or as a light theme。Additionally。

 it's possible to switch the theme with a button click Now let's continue with an in depth demonstration of event handling。



![](img/3774e3ffda4bc0b32b5d058fe16f81e6_1.png)

I'm going to demonstrate event handling with an example so that you can gain practical insight into the use of events to provide additional functionality to an app。

I'm going to build a component and I'll name it Mo toggddler。So in the Explorer sidebar in VS code。

 I right click the source folder and click the new file command。

 I name the file mode toggddler and for now it's an empty function declaration with a default export。

I press C S or command us on a Mac to save my updates。Back in the app component。

 I update its return statements to render this new mode toggr component。

I also need to import it on line one of the app component and save the changes to app JS I now return some JSX code from my Mo toddler component and add a return statement。

In this statement， a JSX expression wraps the turnernary which checks if the value of dark mode on is true or false。

If it's true， it will return whatever is stored in the dark mode value， and if it's false。

 it will return whatever is stored in the light mode value。However。

 I don't have the values I'm evaluating yet， so if I save this code now， it throws an error。😊。

Instead， I define these values by declaring three variables above the return statements these are dark mode on。

 which holds a value of true。Dark mode， which holds the text。

 dark mode is on in an H1 header and light mode， which holds the text light mode is on in an H1 header。

😡，I save my changes and I get the sentence dark mode is on in the browser。

Let me explain what happened here。The dark mode on variable is set to true。😡，Just to do a quick test。

 I can change the variable name of dark mode on in the ternary to the value of true。

Since this value is true， the value that's stored in dark mode will be rendered。

If I change the value of true to false， the value that's stored in light mode will be displayed。

 I have replaced the test word false with our cont dark mode on。

 and now I'll save it and test it again。Now I get the light mode is on displayed on the screen。

I add a button with the onclick events to handle this toggle of the value of the dark mode onbearable from true to false。

So under this  turnary statement， I'll add a button with an on clickick event handler。

 I'll also define the handle click function。

![](img/3774e3ffda4bc0b32b5d058fe16f81e6_3.png)

I start my function by taking the value of dark mode on and change it to the opposite Boolean value using the exclamation mark that is the not operator。

I then assign this value as the new value of the dark mode on variable to explain this a bit more。

 if the value of dark mode on was， for example， true。

 then the not dark mode on will be evaluated to not true。

This not true will be assigned to the dark mode on variable， thus becoming false。

I now add to the rest of the code for the handle click function， which is an if statement。

The logic states that if the dark mode on is set to true， then console log dark mode is on。

 otherwise console log light mode is on。I could have perhaps written this code a bit differently。

 but I wrote it in a way that makes it obvious what is happening here。

This is always good practice for a developer of any skill level so that they and others can easily examine the code at a later stage。

😊，I save and once my app recompiled， if I click the click me button。

 I get the appropriate string output in the console。😡，This brings me to an interesting conclusion。

 although the console log is updating， there are no changes to the actual heading one on the screen。

Of course I can update it manually by changing false to true。

 then saving the app and waiting for a rerender to confirm that my changes have indeed happened because the Priga's heading of light mode is on has now become the heading that Res dark mode is on。

But as soon as I click the button， the console log changes， however。

 the heading in the web app doesn't reflect this change。Why is this the case？To understand this。

 you'll need to go deeper into dataflow and react and observe how it moves between components Fortunatelyly。

 you'll be learning that soon。Great job。You should now be able to demonstrate how to toggle the value of a Boolean state variable using user triggered events and how to handle multiple events on a single JSX element。

