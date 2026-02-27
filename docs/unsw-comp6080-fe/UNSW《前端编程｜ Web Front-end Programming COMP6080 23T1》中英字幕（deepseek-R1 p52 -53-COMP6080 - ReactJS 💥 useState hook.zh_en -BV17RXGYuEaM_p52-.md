# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p52 -53-COMP6080 - ReactJS 💥 useState hook.zh_en -BV17RXGYuEaM_p52-

So we've actually gotten to a really good point now where we understand how we can declare our UI that we want to go on the screen。

And we understand how React can efficiently look at how our UI has changed and figure out how to put the changes into the real Dom and minimize the amount of layout costs that we need to pay。

But there's one final big missing piece of the puzzle in terms of having a framework that really behaves like react。

And that piece is， how do we actually tell react that we're making changes， you know。

 how do we tell it you're going to need to regenerate this component and compare the previous state and the new one。

And the answer is that there is only one way in react to cause an update to happen to the UI。



![](img/c215da2b6362971902c261ca5f5bd507_1.png)

And that one way is cold react state。So React State is a small subystem inside React that allows us to essentially tell React about data that affects the way that the user interface looks。

In this case， we're looking at our standard app functional component。And on the first line。

 we're calling a react function called use state， and we're calling it with a number0。

So zero here is the default value of our state。And use state after we pass it a default value will return us two different things。

 Firstly， it will return us the current value of the state， which we're calling count in this case。

 which will be zero at first。And it also returns us a function called set count。

 which will allow us to change the state。On the second line。

 we have an very basic Lambda that is just a wrapper around set count。Called increment。

 and it's just going to set count to be the count current count plus one。

 so it's just going to increment the count by one。Then we're going to return a button element and on click。

 we're going to call increment。And inside the button element。

 we're going to display the current value of the count state， which will start at zero。



![](img/c215da2b6362971902c261ca5f5bd507_3.png)

So to give you an idea of what's happening internally here is when we click our button。

The count is going to be incremented and the functional component is going to be run again。

The first one and the second run are going to be the two different trees of our virtual dome that we're going to diff against each other。

And we can see that the diff results in the outer button being marked as unchanged and as a result。

 the button isn't going to be deleted from the real dom。

But react can figure out that the contents of the button has changed。

 and as a result it's going to rerender the text content of our button。So in a bit finer detail。

 it's important to understand a couple of things about how set state works。So firstly。

 the big one is that state is updated asynchronously right when you call set state。

 it won't update until the next run of the JavaScript event loop。After the state finishes updating。

 our render function or our functional component is called again。Except this time。

 U state will return us the new value of the state。



![](img/c215da2b6362971902c261ca5f5bd507_5.png)

So。

![](img/c215da2b6362971902c261ca5f5bd507_7.png)

比。嗯。We call our functional component with the new value。

And React uses that as the first and the second state to diF。And then the second state。

 once it figures out the dis that it needs to make。

 that's what it actually propagates to the real UI。



![](img/c215da2b6362971902c261ca5f5bd507_9.png)

So let's have a look at a little bit more of a powerful and interesting example。

 something that you might actually use in a real application。😊。

We've got our standard functional component wrappper on the outside here。

And this time we're using use state， but instead of with a number like count like we did previously。

 instead we're using it with a boolean， so the default value of our state in this case is false。

Where naming our state as drop down visible and set drop down visible。

 So drop down visible is the state and set drop down visible is the function that will update the state。

So from our functional component， we return a rapiditive and inside we have a button。

The button text says open drop down and on click this button calls set dropdown visible with not drop down visible。

 which is essentially a shorthand way of just saying the opposite value。

 so each time we click set drop down visible， it will toggle from true to false to true to false back and forth again。

Then we're using a nice little bit of JavaScript shorthand here as well。

 we're saying drop down visible double ampersand， which basically means that if drop down visible is true。

 it will continue to the right hand side of the expression。

 which in this case is an unaudered list with three list items saying drop down item 1，2 and  three。

And the overall result of this is that we're making something similar to a primitive drop down menu。

 The way that it works is at first， drop down will be false。A drop down visible rather will be false。

 so the shorthand expression will short circuit and won't return our unaudered list。

And when we click our button， drop down visible will be set to true and when drop down visible is true。

 it will continue to the right hand side of that expression out and it will return our drop down contents。

And the great thing about using a declarative framework in this case is that we're never going to end up in a situation where we accidentally forget to remove the dropdown contents from the dom where the state of dropdown visible gets out of sync with the menu being open or closed。

 you know， we can actually guarantee by looking at this that there are only two possible states。



![](img/c215da2b6362971902c261ca5f5bd507_11.png)

And reactor is going to cover all of the transitions between them。

So the best way to understand this extremely simple， flexible and powerful cycle of render。

 change the state， rerender again is to just play around with some simple components yourself there are lots of fun things that you can emulate dropdowns are good timers。

 you know that that type of stuff so just have a play around with some components yourself and make sure you have fun while you do it。

Thanks a lot。

![](img/c215da2b6362971902c261ca5f5bd507_13.png)