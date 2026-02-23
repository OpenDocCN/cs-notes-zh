# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P39：38_范例-构建计算器应用程序.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

I'll now demonstrate how you can use React to build a simple calculator app that is able to perform addition。

 subtraction， multiplication and division operations。😊。



![](img/b3749c4914ec110d0e9ad80cd0cf0396_1.png)

I have some code for this app already written， however， because it's incomplete。

 it encounters problems when it compiles。😊，The first problem is that use RefF is not defined。

 so I'll import Use RefF to fix that issue and then press C S to recompile。

The second problem is that the use state hook is not defined， so let's import that as well。

And when I recompile once more， the problems should be resolved。😡。

So the structure of the app is there， but currently it can only perform addition。

 so I need to add the other functionalities。Let's start by examining what I have with the plus function。

It runs the Pre default function on the receiveive event object。

 and then it invokes a function for updating the state variable。

I can use this as a template for the other functions I will write。

 so I will copy and paste this code into the functions I've started。In the minus function。

 I update result plus number to result minus number so that it subtracts whatever is in the input。

In the times function I update the same snippet to result asterisk number and finally for the divide function。

 I use the divide operator or forward slash to make it result slash number。

Now I also have two functions called reset input， which sets the input value to zero and reset results。

 which sets the result value to zero as well。Reset input needs to run Pres default。

 and I follow this with input Ref dot current dot value equals zero。For reset results。

 I use a different approach。I have it run prevent default。

 but then instead of setting the value to zero directly。

 I have it multiplied the previous value by zero。😡。

I type this as set result followed by an arrow function that directs prevV to return prevV times0 Now if I go to the return statement of the app component。

 I find that I need to add the value of the current total as a JSX expression so I type result。

I can condense this code to a single line， so I'll do that。Next。

 I have to add buttons to trigger the functions that I've written。😊。

I paste in five button components that I've written previously。

 each of which is bound to an onclick event。😡，This component is written for the plus function。

 so that is already taken care of。😊，I'll update the other button component by changing the function that is called for each one。

 as well as a text displayed on the button。So the second button calls the minus function。

The third button calls times。The fourth called divide。😡。

The fifth one calls reset input and the final button calls reset result。

Now I press Cr S to save my changes。I'm ready to test that my app so I type two in the input fields and then click on the add button。

😊，The result changes from zero to2， and then adding two again updates it to four。😊，Next。

 if I type one and then click on Subtract， the result becomes three。

If I enter 10 in the input field and click on multiply， I end up with 30 as the new result。

And now if I type6 and click on divide， I get a value of five。😊，Finally。

 I can click reset input to set the value in the input field to zero as well as click reset results to clear the results and bring it back to zero and that's it My code is complete and my app works as per the requirements。



![](img/b3749c4914ec110d0e9ad80cd0cf0396_3.png)