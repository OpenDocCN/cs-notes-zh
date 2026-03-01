# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P45：45_02_07_演示：使用panic停止程序.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/5d2950ec164a09384e67adfbf1e25fa9_0.png)

In languages like JavaScript， you have a throw where you can throw errors， throw exceptions。

 and in Python you can race these exceptions。In languages like Gol and rust。

 you have the ability to call a panic。 A panic is something that will immediately halt execution of a program with their message and it will cause the program to exit early with an optional back tray。

 So we can actually say right here at the very top and we can say。Error of。We are。

We are panicking or we're crashing the program That's fine。

 So now you can see that immediately the text editorator knows that this is not going get executed。

 if I run this yes， unreachable statement right here any code following this expression is unreachable yes we're having a panic you can see here threat main panic that error we're crashing the program perfect so that's good well that's not entirely good we're going to remove these and in this case we are going to be calling loop and panic and we're going to run that and it's going to go through number one2。

3 and4 and as soon as it gets to a negative number it say hey negative number found that's a problem we need we need to do a negative number found error and or call it as an error and but a co panic so that execution gets halted right so if number is less than zero you can see here I。

A minus5 in there in that vector。This is a way of dealing with a situation that you do not want to continue where you want to get the problem to actually crash and stop execution at all cost this is an unreasonable thing to expect we cannot continue So what is the deal here Why would you want to use panic panic is available certainly in Ruam。

 you can see in work here， but it is something that is frowned upon on production great code of Ra programs unless in very specific situations normally you wouldn't be handling an error condition with panic panics are fine for example code those are fine for demos where you want to halt execution I mean you just saw me do something right before the loop and panic right here but it's something like you wouldn't necessarily。

Want to have something like this。 I mean， there are situations where you might want to have a panic and implement panic and say this is 100% forbidden。

 you are going to get into trouble， which is fine but you have to be very careful and do executions。

 So for example， in the vectors and we haven't touched too much on vectors or strings even let's say new new string。

And then that's fine。 And if we say printline new string， but if we say the index 100。

 this is going to probably panic because hellello world is not is not going to work correctly so again use panic sparingly there are certain situations that you must use panic that you can you understand that this is in the program that you're writing this is absolutely inconceivable and you have to panic。

 there's no way and we can see this in definitely many different parts of the rust standard library and that's I mean makes it okay but it is not that the fault most common way to deal with errors you may want to bubble those errors nicely with error types that are available in rust。



![](img/5d2950ec164a09384e67adfbf1e25fa9_2.png)