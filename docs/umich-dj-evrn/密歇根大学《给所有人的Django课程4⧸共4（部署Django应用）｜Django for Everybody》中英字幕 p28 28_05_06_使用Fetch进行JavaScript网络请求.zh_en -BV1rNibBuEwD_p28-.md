# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p28 28_05_06_使用Fetch进行JavaScript网络请求.zh_en -BV1rNibBuEwD_p28-

So the last kind of events that we're going to talk about are network events that is code that runs as your JavaScript is talking to the network。

So we can do network operations in JavaScript， we can do the entire request response cycle in JavaScript。

 the problem is that this has to be an asynchronous process because we can't pause our code。

 we can't say stop and read from the server because otherwise the browser would lock up。



![](img/24350a1647945fcaae64a9405cb4c5db_1.png)

So we have to kind of use events and we kind of chain these events together we have a start the request and then。

Give me an event when the request is and then as the date is being retrieved when date is all retrieved。

 then you process the request。 And so there's a multi step process and you do one step and then initiate the second step and so that that means that we're never in our jascript waiting for anything are responding to an event and then triggering another event and then responding to an event and triggering another event。

 but never doing anything that waits in our code。 This particular code is 14 fetchch。 Htm。

 Now fetchch is a function that's available and its parameter is a URL。

 So I've got this URL called secret。 Txt。 Now fetchch returns what's called a promise。



![](img/24350a1647945fcaae64a9405cb4c5db_3.png)

A promise is something that hasn't happened yet but will happen。

And then you say dot then and the then code。

![](img/24350a1647945fcaae64a9405cb4c5db_5.png)

Runs。When the fetch has started。And so in this case。

And I'm using this sort of short syntax because this inside the parentheses of the then。

 you see a function that takes a single parameters or the variable response。

 that's my choice is a variable name。

![](img/24350a1647945fcaae64a9405cb4c5db_7.png)

I console log and then I return responseponse dot text。

 Now that what that really is saying is now go retrieve that text， which will take some time。

 so respond dot text itself。

![](img/24350a1647945fcaae64a9405cb4c5db_9.png)

Is another promise。 And so the return value of the first then is itself a promise。

 And that's why you see the second then。

![](img/24350a1647945fcaae64a9405cb4c5db_11.png)

Now， the second then happens when the response text has been retrieved and now we're being handed that as a text string。

And then it says let's run code and console log that text string， so fetch。

 starts and returns a promise， then says when that promise completes， run this code。

And then return another promise， and then the second then takes is runs after the second after the promise is retrieved。

 and then we're done。 So you see there's three little steps。

 and each of those steps is instantaneous or as fast as we can do it。

 and there's no waiting and each time we have to register a function to respond to the request。



![](img/24350a1647945fcaae64a9405cb4c5db_13.png)

So Java script calls us back， okay？And so you can kind of see this happen， right， the fetch starts。

 the first promise resolves。And we see what the response is now you'll if you look carefully。

 you see that the response is a 200， which means it looks like we're doing well， right？

And it has a readable stream。But we have not yet used the body。 Okay。

 so when it says body used equals falses。That means that we've sort of started the request and it looks like it's going to go well and now we're given a chance to see what we're going once this request is started now by calling response。

t text， that's a method inside this response object that then says， oh。



![](img/24350a1647945fcaae64a9405cb4c5db_15.png)

Go back， make a new promise， and that promise will be fulfilled when we've actually retrieved the text。

 so at this moment where it says consoles log response， the text hasn't been retrieved yet。

 and so we're returning a promise to be fulfilled after the text is received。



![](img/24350a1647945fcaae64a9405cb4c5db_17.png)

Then when that text receiving is finished， which might take， you know， two seconds or something。

 And it's like， oh， I've got some text， so I'm going to call you back。

 resolve that promise and pass the actual re text string back into us。

 And so that's the that's the only moment that the what the server has given for secret dot Txt。

 which the secret of course is 42 is the text。 that's when we can actually printed out。

 We can make this a little bit more succinct and then watch it as it happens。 So this is 15 fetch。



![](img/24350a1647945fcaae64a9405cb4c5db_19.png)

![](img/24350a1647945fcaae64a9405cb4c5db_20.png)

So we're going to do something with this text instead of just printing it。

 and we're going to use kind of the more succinct contraction style of this function code。

And not put so many console logs in。Jo was putting console log so you could see the steps that happened。

So this is a more typical way of doing something， so we're going to fetch secret。t Txt。

 which is you're on the server。

![](img/24350a1647945fcaae64a9405cb4c5db_22.png)

When that fetch has successfully started， we resolve the first promise and then we say， okay。

And the first response arrow response text response is the parameter to the function。

 and response dot text is calling the text method in that。

Which is the return value to this first promise， which is another promise。

But that'll be it when that promise resolves， it resolve to a text string。

 And that's why the second then says， take a variable。 Again， I could call text string X。

 It's just a variable in a function call。 It's just a parameter of function call。 So call me back。



![](img/24350a1647945fcaae64a9405cb4c5db_24.png)

Call mother's function I'm making text string and then get doc in that code is document get elementement ID by ID Zap。

 which is that P tag and I set its inner text to be the text string that I retrieve from the server and so you can kind of see that。



![](img/24350a1647945fcaae64a9405cb4c5db_26.png)

We can do things， we can get data from the server， and then we can move it into our document object model and I try to do this in the simplest and smallest version we will cover this in a lot more detail when we actually have something more important to retrieve like JSO。

 for example， JavaScript object notation， which is the the next section。

 This has been quite a busy ro through how things work in the browser。

 we talked about the document object model， we talked about the browser window。

 which is like that part that we're seeing。UI event handlers。

 whether we register them within a click or with a Ed event handler。

 DOm event handlers like the DO loaded window event handlers like the Resize， we can change a tag。

 we can add a new tag， we can change the CSS， and we can even make network requests from JavaScript。



![](img/24350a1647945fcaae64a9405cb4c5db_28.png)