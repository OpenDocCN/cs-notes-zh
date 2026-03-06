# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p145 p73_02_angular-life-cyle -BV1tAygYoEj5_p145-

H there。In this video， we will learn about angular life cycle。So let's get started。

Understanding the angular life cycle is essential for developing angular applications。

The angular lifecycl consists of a series of pre definedfined stages。

 or you can say hooks that occur during the lifespan of a component。

These hooks allow you to perform specific actions at different points in the component lifecycle。

To help you visualize the angular life cycle， let's imagine a component as a living organism。

Going through different stages from birth to death。

Let us look at the important angular component life cycle。

Stages so first we have creation that is the birth of the component in that we have a constructor。

So this is the first method that is called where a component is created。

It is used to initialize the component and its dependencies。However， at this point。

 the components template and input properties are not available next we have initialization。In this。

 we have Nng on changes。So this hook is called when the components input property changes。

 it provides information about the change properties。Then we have Nng on in it。

So this hook is called once after the first NG on Change called。

It is used for initializing the component， making API calls and performing other set of tasks。

Then we have content projection。In this， we have Nng content in it。

So this hook is called after the content children that is the projected content are initialized。

Then we have view initialization in this we have Nng after content in it。

So this focus is call after the content children are initialized and available in the components view。

And then we have view update。In this， we have Nng after view in it。

So this work is called after the components view and Chil View are initialized。

 it is used for performing additional setup of tasks that require access to the components view。

Then during the run time， we have N do check。This hook is called during every change detection cycle。

It is used to perform custom change detection and react to changes in the component state。

Then the last stage of a component is destroy in this we have Nng on destroy。

 So this hook is called when the component is about to be destroyed。

 it is used to unsubscribe from subscriptions or maybe clear timers and release any resources held by a component。

Let us understand this to an example， so let us go to the VS code I have here a basic angular setup ready and this is the main component file that is add dot component or Ts。



![](img/c361dd7d5dc9d984e38a9831713efa43_1.png)

Here in the template rather than using a path， lets use backt and lets put a template here。

So let's add X2。And let's say life cycle example， something like that。

And let's close the edge2 tag here。Then we can have a P tag and we would be adding some conditions here。

 so let's say。N G F。And if。This particular value， let's say， initialized。This variable is true。

In that case， we want to just render component。Iitialized， that's it。And let's close this p tag。

Similarly， I will have one for another condition and lets say if you can put destroyed if you want and then you can say destroy component。

 whatever。You can put many conditions here。Now let's start adding the。Life cycle。

 you can see stages or life cycle hooks here。So let's say class app component and you can say implements and we want to add。

 let' us say on in it and make sure that you import on in it here。

And then let's also import on destroy。In this case， we can include two variables。

 let us say initialized after the title or we can remove the title as of now。Let's。Say， initialized。

That we have declared here and this would be a Boolean value。And let's make it false， initially。

Then let's also create this destroyed or lets say any other variable that you want to create。

 but let's start with the first hook now that is constructor。

So lets say console dot lock and we can say construct。过い。And let's add one more hook。

 let's say Nng on in it。And lets just focus on in it for now， if you want to add this。

 you can add it so we can say Nng on in it。And here we can say this dot initialized equals to true。

 and then we can say console dot log。Component。Initialized。

So now let's do what it should come on the template as well and it should come on。

The console as well。 So let's click on save。 And what would be the order of these life cycle folks you can say。

 So let's go here to the console。So in this case， it would not be template URL but a normal template。

 So now if I click on save， you will see in the console， first of all。

 we have component initialized here， but in the console you will see the order of。



![](img/c361dd7d5dc9d984e38a9831713efa43_3.png)

How these hooks are called。 So first constructor is called and then component initialized。

 and then if you add， let's say Nng on destroy， then the destroyed would be called at last。

 So on this， lets。

![](img/c361dd7d5dc9d984e38a9831713efa43_5.png)

![](img/c361dd7d5dc9d984e38a9831713efa43_6.png)

Look at how the flow of these components or these hooks work。

So the first would always be the creation phase and then we would have an initialization phase。

 then content projection then view initializations and after that you can update the view and then run time in that case we have N do check and in the last we have destroyed So this is the actual flow of how。

The flow of this life cycle hooks work。It is very important to note that not all hooks are always used in every component。

The life cycle hooks are optional and you can choose to implement only the ones necessary for your components。

 behavior or for use cases。Understanding the angular component life cyclee helps you manage component initializations。

 perform cleanup operations， and optimize performance by utilizing the appropriate hooks at each stage of the life cycle。

This is all for this video in the next video we will understand about angular decorators see you in the next video Thank you。



![](img/c361dd7d5dc9d984e38a9831713efa43_8.png)