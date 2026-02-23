# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P6：5_创建 React 组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In this video， you will further explore the concepts of components in react and learn how to create a component from scratch。

You'll be introduced to the concept of the export statement and how components can be used to create reusable blocks of code。

 I've launched Vis code here， and I have the creating component folder open in the builtin terminal。

 Now I'll execute the command NPpm in it react app dot the dot character instructs Vs code to run this command in the current folder。

 In other words， I'm using create reactact app to build a new app for me inside the folder。

 I execute this command by pressing the enter key。

![](img/5220520646539e6e642861664fa22486_1.png)

I wait for the app to build and once it's ready， I can start the app by typing NPpm then a space followed by start。

The process of building the react app could take a couple minutes， so just sit tight while it builds。



![](img/5220520646539e6e642861664fa22486_3.png)

Great， my react app has started and loaded in the browser at Localhost 3000。

 which is the local server。 Notice that I have all these files and folders in the left pane of Vs code now such as node modules。

 public， SRC and files like package。 Jasonson。You'll learn more about this later for now。

 the only folder I need to work in is the SRC folder。

 so don't worry about all these other files and folders。Instead。

 I want you to focus on how to build a component in react and to do that， let's have a clean start。

The easiest way to do this is to remove all the code inside the function inside the app。 JS file。

I guess you might say this is the simplest possible component。

 I'm declaring an app function and I'm exporting it as a default module。



![](img/5220520646539e6e642861664fa22486_5.png)

I save my file and notice that my app is just a blank page。

Now let me create another component thatll contain some text that I want to display in the browser to do this。

 I create another function called header， and in the function body I'll just return some greeting text inside an H1 JSX element inside the H1。

 I type Ho world。My code looks good now， but my screen is still white。

 This is because I'm not yet rendering anything from my app function。To do this。

 I need to return to my app function and call the header function from it。

 I use the JSX elements syntax to render a component， which is the name of my function。

So inside the body of the app function， I create the return statement and type the function name of header inside left and right angle brackets。

 not forgetting to add the forward slash before the right angle bracket。

 noticeice that the syntax to render a component is very similar to a self closing tag in Hml press Cr S or command S if you're on Mac to save everything again。

Great， my code is working now， and I notice an HTML heading with a text Ho world displayed in the browser。

Congratulations in this video you learned how to create a functional component。

 This component named app calls another component named header。

 which displays an HTML heading with some text At the moment the header component code exists in the same file as the app component。

To make the header component isolated and reusable， I need to place it in its own file。

 then I can reuse it multiple times in the application anytime I want to display a heading element with some text。

 and you'll learn how to do this very soon。

![](img/5220520646539e6e642861664fa22486_7.png)

In this video， you learn how to create a functional component in react and render it to the root components named Ab JS。



![](img/5220520646539e6e642861664fa22486_9.png)