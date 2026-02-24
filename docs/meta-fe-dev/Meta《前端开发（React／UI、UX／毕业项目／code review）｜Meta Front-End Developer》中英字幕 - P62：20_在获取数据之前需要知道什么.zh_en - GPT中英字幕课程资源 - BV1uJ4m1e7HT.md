# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P62：20_在获取数据之前需要知道什么.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

The fetch function is a very useful tool， but there are some important things that you need to understand before you start using them。

Initially， it's good to get an overview of how JavaScript delegates duties so that you can gain insight into how the fetch function contributes to this process。

In this video you will learn how the fetch function works to retrieve data from the web and how to provide an example in plain JavaScript of the process。

Ftch is used to make a server request to retrieve some Json data from it。

 Fetch API is a set of functionalities that we have at our disposal to use in jascript to make such a server request。

 It's a bit like a clerk at the post office。 Sa you're bringing a package to the post office。

 and you are the first in the queue。 The clerk on the other side of the service desk is jascript。

 Since they can only do one thing at a time。 they go through the process of getting your details。

 measuring the weight of the package， Paing stamps onto the package。

 charging you for the service and going into the back office and carrying the package there。

 then taking time to find the correct place for the package before it gets shipped。

The problem with this approach is that the next step cannot start before the previous one is finished。

 that's what's known as single threaded execution。Since JavaScript is not at all equipped to multitask。

 a way to go around this issue is as follows。 First， JavaScript gets your details。 At the same time。

 it calls a clerk to measure the weight of the package。

 Then JavaScript calls yet another clerk to paste some stamps onto the package。

Javascript calls yet another clerk to charge you for the service。

 and yet another clerk is called to carry the package to the back office。

 allowing JavaScript to take care of the next customer。



![](img/01369cef5660368937b8832ee49c1849_1.png)

Essentially this delegation of duties is what's referred to as asynchronous JavaScript In this metaphor。

 you can think of the browser as the post office， JavaScript as one clerk in the post office。

 and all these other clerks can be referred to as browser APIs or web APIs。

Now let's explore a practical example of how this delegation of duties works in JavaScript。

 so I have a local HTML file， the most important part of this file is the script tag。

 which is getting some JavaScript code from the file named script。

 JS located in the same folder as this HTML file。I'm serving these files locally using the live Ser VS code extension。

 so let me inspect this HTML file in the browser。

![](img/01369cef5660368937b8832ee49c1849_3.png)

Okay， so currently it only shows a H1 heading that reads fetching data。

Now let me take a step back and let's say that JavaScript， the post office worker。

 needs to get some user data from the computer database。

Here is the JavaScript code inside the linked to script。jS file。



![](img/01369cef5660368937b8832ee49c1849_5.png)

What do you expect the output of this code will be since JavaScript can only do one single thing at any given time？

Well， let's explore what the code is doing step by step On line one。

 it performs a console log for the words another customer approaching。 Then it contacts the Fech API。

 which is a browser API that is external and separate from jascript。

Rather than waiting for the Fech API to return the information。

 it keeps on executing the code that comes after it。

 outputting the text that begins our valued customer In the meantime the Fech API requests some user data from a third party web based API available at the randomuser。

me website。The fetchch function is what's known as a facade function。

 meaning it's a function that looks like it's part of JavaScript。

 but actually it is just a way for me to call a browser API from JavaScript。In other words。

 it's a way for me to access a piece of browser functionality that's outside of JavaScript。

You can think of it as the JavaScript post Office clerk。

 calling the records Department of the post office to get some data about a customer when the other clerk gets back with the information and hands it over to the post office clerk。

 then they will get a JSON representation and finally will log that data to the console。

That means that the sequence of console logs from the code will be as follows。

An initial console log that outputs another customer approaching a second console log that outputs our valued customer。

 please wait a moment while I get some information back from the records department and a final console log that outputs the data。

I'll now execute this code to confirm the described behavior。 Everything is already saved。

 so all I need to have this code executed is to go back to the browser。

 right click on the page and press the reload command to refresh it。



![](img/01369cef5660368937b8832ee49c1849_7.png)

You can achieve the same result by pressing the F5 key on your keyboard。

So now I first get another customer approaching， then the hour valued customer。

 and finally the result of the call to the third party API。



![](img/01369cef5660368937b8832ee49c1849_9.png)

This is how JavaScript， although being single threaded， can perform asynchronous operations。

In this video， you learned how the fetchch function works to retrieve data from the web and how to provide an example in plain JavaScript of the process。

You should be familiar with this concept before fetching data in Re， which I'll explore soon。

