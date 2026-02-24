# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P12：11_实际样式.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Recall that there are three techniques to include CSS in HTML documents。

 The first is in line by utilizing the style attribute inside the HTML element。

 Next is internal by using the style element in the head section。

 and finally external by linking to an external CSS file using the link element。In this video。

 you'll learn how to take CsS style rules from an external file named index dot CSss and add it inside a component as an internal style。

 These style rules can then be referenced by your code inside the return statement of the component。



![](img/9e485adc78d6fd13b585b12fb057f99c_1.png)

Notice that the components are styled by the external style sheet indexed CSss。 for this video。

 I'll continue working on an app which consists of the components header， main and sidebar。

 This time， the focus will be on using internal styling inside the sidebar component。

To demonstrate this， I don't need to move all the code from the index do CSss file。 Instead。

 I'll just focus on the styles related to the sidebar component。For example。

 I select the CSS code for a site and cut it by pressing controlr X or command X on Mac。

 After saving， notice that this removes the styling from the sidebar component displayed in the browser。

Now let's go to the sidebar。js file where I'll paste the code before the return statement。



![](img/9e485adc78d6fd13b585b12fb057f99c_3.png)

This will not affect my component because I'm pasting CSS code into a JavaScript file。

 so I need to make some changes to turn the CSS rule into a JavaScript object to do this I need to declare a site style as a cons variable and then replace the semicollonons in the code with commass I also need to replace the hyphenated names with CAl case。

It's important to know that because CSS declarations like background are now an object property。

 I need to make their respective values a string by wrapping them inside double quotes。

And I also need to repeat this for the other new style elements as well Finally。

 inside the As tag in the return statement of the component。

 I need to add a style attribute by typing style equals a site style as a JSX expression。

I then choose save all in the file menu to save my changes。

Notice that the sidebar component appears in the browser as before I edited the index。css file。

 so that's an example of using inline CSsS styling directly inside a component。In this video。

 you learn how to take CSS style rules from an external file named index。

 CSss and add it inside a component as an internal style。



![](img/9e485adc78d6fd13b585b12fb057f99c_5.png)