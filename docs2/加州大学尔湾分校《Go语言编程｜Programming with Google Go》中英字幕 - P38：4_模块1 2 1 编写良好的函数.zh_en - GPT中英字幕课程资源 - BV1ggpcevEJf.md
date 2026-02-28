# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P38：4_模块1 2 1 编写良好的函数.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 1 functions in Or， topic 2。1 well written functions。



![](img/f3d4a2eb2966d25c4db54cd943a8b3ac_1.png)

So we're going to talk a little bit about。How you， how you should write functions。 Now。

 this isn't actually necessarily specific to go。But this is more a good way to construct your code so that your code is well organized and easy to understand。

 okay。And understandability， I I'm highlighting this idea of understandability。

 It is important to be able to understand your own code for many， many reasons， Okay。

 mostly for debugging， but also maintenance， other people interacting with your code。

 it needs to be understandable and the way you write your functions the way you define your functions really impacts understandability。

😊，So if we look at a block of code， we could roughly say that a block of code is a bunch of functions and a bunch of data。

So a bunch of functions that are the operations that you're going to perform and the data that you're going to perform the operations on Okay so you can see really any block of code。

 any program as a pile of functions and a pile of data somehow organized together。😊，So。😊。

When I say understandability， when I say， oh， this program is understandable。😡，Here's what I mean。

 I mean that if you're asked to find a feature， you can find it quickly。 So as an example。

 where in your function， where's a function that blurs the image。

 say you're writing some graphics program， Where's the function that blurs the image。

 you can locate that。 Now， you might be asking that yourself， because you found a bug。

 Something's not working and you need to find that piece of code or that could be some kind of code review you meeting or you're dealing with other people you're working with and they need to understand how your code works and they ask you this type of question。

 Maybe it's your boss right， your boss is like， look， where is the code that does this。

 and you will look like an idiot， if you can't answer that。 If' your code， you wrote it。

 you should know it， right， So you need to understand the organization of your own code。 Now。

 a lot of this is memorization。 but it's also a matter of organization， if you organize it， Well。

 it is much easier to find things， So know where is the function that does this operation。

 blurring your image or where do you compute the average score， whatever the question is。

 where is the code that does this， Where is the code that does that。

 You need to be able to find that and that's an understandable piece of code。😊。

If you could find that pretty easily and even better if somebody else can find it。

 So if you write the code and you give it to somebody else because you're probably working on a team right and that other person can find where the where the images blurred or where the average score is computer。

 if they can find it quickly。 That's a real measure of understandability right and remember this too。

 I know a lot of students in my class is they underrate how important this is。

 right think a look is my code， know Of course， I not understand my code So believe me。

 if you write a complicated piece of code and you walk away from that code for a month。

 you come back， you will lose track of what the heck that code did。

 will you will not understand your own code so you really want to construct in such a way that it is easy to figure out what the where these features are located inside your code。

Now。Another aspect of understandability is finding where data is used because often you'll get some you'll get some kind of a problem where this data is incorrect。

 okay or this data is not just use I said where data is used。

 Also where data is used and where is defined So this data is incorrect， How did it get incorrect。

 what part of your code actually affected that data。

 know that type of question you want to be able to ask So you want to be able to trace through data。

 people say this data， Where is it used， Where is it defined。

 So where did you modify the record list right， So you got some record list。

 you realize that record list， the contents that list are wrong while you're debugging Where did you modify that。

 you got to find that so you can find where the bug is where did you access the file。

 Maybe this file has the wrong data and you want to know what code that's affecting So where did you access that file。

 Where did you access these different pieces of data。So this is what I mean by understandability。

 you need to be able to find a feature， find the code dedicated to a particular feature。

 find it quickly， Also data that could be wrong， where is that data used and where is it written to。

 so where is it used and where is it modified， you need to be able to find quickly and organization writing your code writing your functions in an organized way really helps you with that。

😡，So very basic debugging principles， and there are a million debugging principles。

 but I'm going to just be really basic now。 So say you run your code， the code crashes。

And it crashes inside some function somewhere， right， So some function you wrote。

 it crashes on line 100， right， some function。So I can broadly say that there are only two ways that this could go wrong。

 two options for any kind of bug， okay？It could be that the function that failed is written incorrectly。

 it just did the wrong thing。 so maybe as an example。

 it's supposed to sort a slice and it sort in the wrong order。 Okay， it did the wrong thing， right。

 So the function could do the wrong thing or maybe the function is written perfectly well。

 But the data that the function uses is incorrect。 So maybe this function is you know it sorts to slice just fine。

 but the slice has wrong data in it， right， so somehow the data that it got was wrong。

 So when it does a sort， of course， this results going to be wrong。

 right because the original data was wrong。 So the function that you're working on。

 it could be messed up or its inputs could be messed up。

 Now its inputs from can come from the parameters， right。

 So it could be arguments that it passed to it， but its inputs don't have to come from there。

 They could come from maybe a file。😊，Or some user input or something like that。

 So you got to think of all these inputs。 So this is just my sort of high level debugging principle。

 And notice how I'm dividing this。 I'm saying， look。

 either the function is written incorrectly or if the data is false。

 So it's the function written wrong or the data is at fault。 Now， of course。

 when you trace that back， you'll see the data is probably incorrect because some function rotd incorrectly。

 But locally， you can say look， either this function is wrong or the data that's working on is wrong。

😊，So in order to support debugging， when you run into a bug like this。

 first thing you got to be able to do is understand your own function so functions need to be understandable so when you look at that function。

 look at the code， you got to be able to look through it and manually say look is this right。

 is it doing what I think it's doing does it's actual behavior does it match what I want desired behavior So your function needs to be written in an understandable way so that you can determine that without too much difficulty。

😡。

![](img/f3d4a2eb2966d25c4db54cd943a8b3ac_3.png)

The next thing though is the data needs to be traceable。

 So what that means is maybe your function is perfectly fine。

 but there's some input data that it got passed that was that somehow it access that was wrong so you need to be able to figure out where do that data come from So you can follow back to where the original fault actually happen Now this could be easy。

 it could be hard。 global variables for one complicate this because see one thing about having no global variables is that the inputs to the function comes straight from the parameters。

 So you know where every piece of data came from， it came from the caller but if you use global variables。

 then they can come from whoever wrote to the global variables。

 And since these variables are global anybody could have written to it。

 So it's much harder to trace back which function is at fault for writing the wrong data to a variable。

 That's exactly why global variables you should be careful about and I'm not going to say never use them。

 people use them and there are reasons I use them sometimes but。

understand that they add this complication they make it hard to debug because you know just because you know this data is incorrect。

 you don't know what the source of that that was and then you've got to do something more complicated to figure that out。

Thank you。