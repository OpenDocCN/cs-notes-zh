# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P74：32_为光标位置创建高阶组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

The little lemon restaurant is receiving a spike in visit to their website during the last month due to customers loving some of the special pizzas the chef presented to the public。

 Despite the success， there are some pizzas that aren't receiving the same level of attention。

 So they have decided to implement some basic analytics to better understand which are the bests sellers and which ones are not being ordered so regularly。

For that， they would like to track the mouse position of the visitors when they are in the pizza section so that they know exactly which pictures are capturing people's attention and which ones are overlooked。

 in this video， I'm going to show you how to implement such functionality by using a higher order component or HOC。

 which will be in charge of encapsulating the logic and state to track the cursor position of the visitors。

Then I'll showcase two different presentational components that will consume that data and present it in different ways。

Are you ready， let's begin。

![](img/f295e6eb68e19fffa44082eb8ac4994d_1.png)

The little application has been created with Cate reactact app so far in the rendering part of the app component。

 there is a header displaying the title of the restaurant and two components。

 panel mouse logger and point mouse logger。They both expect a mouse position prop and will return null if that prop is not provided。

 That's why at the moment， they don't render anything at all。

You could implement the mouse tracking logic in each component。

 but recall that it would incur code repetition and duplication of the same logic in two different places。

That's why the recommended approach is to use one of the techniques that react provides for encapsulating cross cutting concerns。

In this example， I will illustrate how to do this with an HOC。

I will call this HOC with mouse position that with part of the name is a general convention recommended by reactact。

 since it expresses the enhancing nature of the technique。

 like providing a component with something else。Recall that an HOC is essentially a function that takes a component and returns a new component。

Let's complete the initial scaffold and return a component that will render the RA component provided to the function without forgetting to spread the props it receives so that they are passed through。

Great， now to track the position of the cursor， I would need to define a new piece of local state。

 which I'll call mouse position for the data and set mouse position for the state set。

The initial state will be an object with two properties。

 x and Y to define the two dimensional coordinates on the screen， and I will set both to0。

X equals 0 and y equals 0 represents the top left corner of the screen。 Next。

 I would need to set a global listener in the window object for the mouse move event。

 since this is a side effect， I need to perform the subscription and unsubscription logic inside use effect。

Let's go ahead and do that。 I will add a new event listener for mouse movement to the window object for the call back。

 I will name the function。 handle mouse position change That for now doesn't do anything。

It's important to remove any subscription when your component unmounts。

 The way to do that is by returning a function from use effect and then performing any cleanup needed。

 In this case， I would have to use the window dot remove event listener， passing as argument。

 the mousemo event and the same callback function as before to complete the logic and set the state with current mouse position。

 I need to read that information from the browser event object which is passed as an argument to the callback。

 That event object contains two properties that define the coordinates clientient X and client Y。

 so I will assign both of them to the corresponding dimension。And finally。

 the last step to complete the implementation is to set a new prop called mouseuse position in the RA component to pass that information down to all components that are interested in that data。

Great， so now that the implementation of the HOC is finished。

 let's add the last few pieces to display the mouse position on the screen to enhance the two components previously defined panel mouse logger and point mouse logger。

 I will use the HOC to create two new component versions that will be aware of the mouse position data。

 and I'll call them panel mouse tracker and point mouse tracker respectively。Finally。

 I will use the enhanced versions in the rendering part of the app component。



![](img/f295e6eb68e19fffa44082eb8ac4994d_3.png)

Amazing， the requirements are now finalized if I move the cursor around the screen。

 you can see two different trackers that display the same information in different ways。

 one as a panel and the one below as a data point。While that's the end of this video。

 Little Lemon Rau now uses this solution to track their pizza loving customers and have discovered that something was affecting the sales of their pizza Diavla。



![](img/f295e6eb68e19fffa44082eb8ac4994d_5.png)

Guess what after an employee investigated that particular pizza on the app。

 they noticed that one of the photos was a bit blurry thanks to this little tracking application。

 they have now taken action and uploaded new high quality photos so the next time a customers exploring the menu they won't miss the pizza de Avila。



![](img/f295e6eb68e19fffa44082eb8ac4994d_7.png)