# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p54 -55-COMP6080 - ReactJS 💥 useEffect hook.zh_en -BV17RXGYuEaM_p54-

Hi， welcome to a lecture on reacts userpha talk。

![](img/7948c9f77b621fec8379dcca8ff91e64_1.png)

You might remember a couple of weeks ago， we created a basic react application。

 and it we displayed the date and time in local format when we loaded the page。

It's not the most useful program in the world。 Today， we'll update it。 By the end of the lecture。

 we'll have created a stopwatch application that allows us to count the minutes and seconds that have elapsed since the page loaded。



![](img/7948c9f77b621fec8379dcca8ff91e64_3.png)

Theoretically， we've already got everything we need。 We've got components。

 We've got interval functions， which allow us to run things on the timer。

 So this should be fairly easy。 Let's make a first attempt。



![](img/7948c9f77b621fec8379dcca8ff91e64_5.png)

Okay， so I have an example app here。 There's no data in it yet。

 but let's try defining an interval outside the function， as well as a reset function。

 And then we'll add some JS X。So I'm setting the interval here for a timer of every second。

And it will increment the seconds by one。 I should define the seconds。

And let's give myself a reset function as well that will set the second。Back to 0。There we go。Okay。

 I have the logic。All I need to do is display it。So I'll render the seconds in a div。

And I'll add a reset button for good measure。ok。So we have the seconds eapsed here。

 but nothing seems to be happening。The seconds aren't incrementing and I'm not sure the reset is doing anything because the seconds are already at zero。

We can try changing the way we store our seconds to use the use state hook。

 which you should be familiar with from a previous lecture。So let's get rid of that。

So we'll put our seconds in a use state hook。And now let's try setting our interval。

So I'm incrementing the seconds in an interval。And I'll redefine my reset function， as well。奥什。Okay。

 so the seconds are elapsing。 fine。 I can reset。But have a look at what's happening to the second。

The more I race at。The cr the numbers go。As a short explanation。

What's happening here is that the set interval call。

It's being called again every single time I have reset。

 which means it's trying to increment the seconds a bunch of times every second。

Let's try with a use effect call。So in this， we actually set the interval inside the use effect function。

We incremented by one。Don't worry if you don't understand the syntax right now。

 we'll be going through it after this demo。I've made a mistake here， as well。There we go， okay。

Seconds are relapsing， okay， so far。And it's looking good。 Let's try the reset button。

And we're still good。

![](img/7948c9f77b621fec8379dcca8ff91e64_7.png)

So I just tried a bunch of methods， and they didn't really work very well。

 defininging the counter outside of the function component meant that react couldn't actually see when something got incremented。

Using the used state hook was a little better， not much better。 It incremented the seconds perfectly。

 But when I clicked reset， it redefined the interval again and made it very confusing。

When I threw that out and I used an effect hook， everything worked perfectly。



![](img/7948c9f77b621fec8379dcca8ff91e64_9.png)

It's clear use effect is useful， but we don't understand why or how。 What even is it。Well。

 use effect is a react hook。 you've already used Use state paired with Use effect。

 these two hooks are fundamental。 You basically can't do anything meaningful without them。In short。

 user effect allows us to pass in custom code that will be triggered under certain conditions in the component。

It gives us the ability to run any logic we want， and it makes sure that it's triggered at the right time in the component life cycle。

So Use effect is a really powerful hook。But the trade off is that the syntax is a little confusing and there are a lot of edge cases that you have to deal with。



![](img/7948c9f77b621fec8379dcca8ff91e64_11.png)

Because the syntax is like that， we'll build up to it gradually。On the right hand side of the slide。

 you can see a user of effect declaration。Use effect is a function。

 and it takes in either one or two parameters。The first parameter of use effect is the function that you want to be triggered。

 in this case， we're setting an interval so that it will run every second give or take。

Hooks are really powerful because you can compose them together。 So in this example。

 we're using a state hook to store the number of seconds that have passed。 and inside the interval。

 we incremented by one using the set seconds callback。



![](img/7948c9f77b621fec8379dcca8ff91e64_13.png)

Let's take a look at what happens using our half built hook。



![](img/7948c9f77b621fec8379dcca8ff91e64_15.png)

你呀。I'm pretty sure time does not move that fast。So clearly， we're still missing something。



![](img/7948c9f77b621fec8379dcca8ff91e64_17.png)

This is where the second parameter of user effect comes into play。

We call this parameter the dependency array。 And in this array。

 we provide a list of props or state objects。I mentioned earlier that there were a set of conditions that would determine if the function you provide to the effect is run。

So if any of the references defined in your dependency array change in any way。

 then the function inside use effect will be triggered。If the component renders。

 but the props and state in the array haven't changed， then the function won't trigger。

If you don't provide a dependency array， then the function will run after every single render of the component。

This is usually not desirable。 It can lead to infinite loops， performance problems。

 and the use cases for it are very slim。You can see here that I'm providing an empty array。

 what that means is that the effect will run when the component first renders。

 but it will never be run again because it doesn't depend on any props or state。

It's important to make the distinction between an empty array and no parameter at all。

 No parameter means there's no dependency array， but an empty array means it doesn't depend on anything。

So at this point， we've got a working use effect function。

It calls set interval to set seconds to increment every second。However。

 what happens if the component is removed from the tree or if it's not rendered。

Will the interval still run？The answer is yes， the interval will always run。

 Now it's been set because it's bound to the window object。

We need a way to make sure that when the component isn't on the tree when it's removed。

 we can clean up the interval。 That's what a cleanup function is for。

Use effect allows us to return a callback function， and we call that the cleanup function。

In this case， we're using it to clear the interval that we sat previously。

The cleanup function is triggered in two scenarios when the component is removed from the tree and also immediately prior to the next run of use effect。

One of the most common use cases for his effect is to set up subscriptions。 In this case。

 were subscribing to a time interval。Canup allows us to unsubscribe when the subscription is no longer relevant。



![](img/7948c9f77b621fec8379dcca8ff91e64_19.png)

That was a lot to take in。 So let's have a look at our user effect call from before。

You can see here I'm defining a use effect function。 The first parameter is a function。

 and the second is an empty array， meaning that the function will be triggered only after the first render of the component。

Inside the function， we're setting an interval to increment our store every second。

 we also return a cleanup function to clear that interval that we previously defined。

 The cleanup function will run whenever the component is removed from the tree or if the effect function runs again。

 which it won't do， because we added an empty dependency array。

And all of that leads to saying that the interval is set when the component is rendered and it's cleared when the component is gone。



![](img/7948c9f77b621fec8379dcca8ff91e64_21.png)

Okay， we now have an application that counts the number of seconds that have passed。

 We can build on this by also storing the number of minutes that have passed to do this。

 we'll use a used state hook to store our minutes。

![](img/7948c9f77b621fec8379dcca8ff91e64_23.png)

You can see here I've made some changes we're using to use state hook。

 The reset call sets minutes to zero， and we're rendering both the minutes and seconds。

 We still need to use a fact hook。So we'll add it below our current news effect hook。

 What we've done is we've passed in a function that says that if we have over 60 seconds。

 we set the seconds back down to zero and we increment the minutes by one。

You can see here that we actually have something in our dependency array Second。

 every time that second mutates， this effect will be triggered。

 What that means is that when the interval is called every second。

 it will increment the seconds variable， which will automatically trigger the next effect。

If you're defining multiple effects that all run at once。

 the order of Dec is also the order in which they'll be triggered。



![](img/7948c9f77b621fec8379dcca8ff91e64_25.png)

Let's take a look。Okay， so first things first， I store my minutes in a use state hook。

Then I'll update the race at Colback。To set the minutes to 0， as well as the second。Now。

 my effect hook。So we race set the seconds at 60 and we increment the in。

We also need to make sure that the effect hook is triggered at the right time。

 so we add the dependency array and we put seconds in there。

We know now that whenever seconds changes， that effect will trigger。There we go。😊。

You can see now that the seconds are ellappssing。And when we hit a minute。

The minutes should increment。

![](img/7948c9f77b621fec8379dcca8ff91e64_27.png)

And that's it。 We've successfully created a stopwatch。

 We'll leave any other details as an exercise for you to do at home， if you like。😊，In the meantime。

 we're going to jump into more detail about how user effect works and how it's triggered。



![](img/7948c9f77b621fec8379dcca8ff91e64_29.png)

First， let's recap when does rendering occur in a react component？Well。

A react component will rerender if its props change， if its internal state changes。

 or if a component above it in the tree is re rendered。

The user effects callback will be called if one of the dependencies in its array is mutated or if you don't provide an array after every single render。

 the function itself is always called directly after the render。

People criticize use effect for being unnecessarily complicated。

 but it's actually really important because it helps keep our functions pure。

 What I mean by that is that given identical props in state。

 the component should always return the same JS X。 If we don't have that。

 That means we have things like side effects， which make it really hard to keep our code correct and maintainable。

 using use effect allows us to sandbox our custom code。We also refer to this as determinism。

 and it's the same reason that all of our state needs to be tracked by react。

 If it needed to track variables outside of components。

 then we could never really guarantee that our function components are deterministic or pure because those variables are outside of them and might change at any time。

That's why we have used state to store variables inside the react loop so they can be tracked。

 Similarlyly， user effect is the same， but instead of storing state。

 it allows us to sandbox and execute custom code。And this allows us to do a lot of things。

 We can fetch data from a remote source is a very common use case for use effect。

 managing subscriptions， setting up timers like we did with the stopwatch and performing native dom manipulations when needed。



![](img/7948c9f77b621fec8379dcca8ff91e64_31.png)

Let's take a look at fetching data from a remote source。



![](img/7948c9f77b621fec8379dcca8ff91e64_33.png)

Okay， I found a free API on the Internet that can give you random facts about cats。 And I love cats。

 So that's a win for me。 I'm storing my loading state and also the cat fact in different use state hooks。

😊，Use a effect as an asynchronous function。 The first thing it does is set our loading state to loading。

And then it does the fetch logic。We fetch it， we get the Json， we get the number of cut facts。

 and we extract a random cut fact from it。Then at the end。

 we set the cat fact and we set the loading state to success。Now， if I refresh。

You can see you get a random cat fact every single time。Notice as well in the JSX。

 I'm actually rendering something different depending on the loading state。

 This is a really common pattern in react。

![](img/7948c9f77b621fec8379dcca8ff91e64_35.png)

And that's the last demo for Use effect。Before we go。

 I just want to alert you to a couple of edge cases around Use effect that might trip you up。

When you define the dependency array in use of effect， E。

 S L will automatically add any state or prop that you use。 and you don't really have a say。

That means we need to be careful about what state we read in effect。In the first example here。

 technically I'm reading the seconds variable， so it will be added to the dependency array。

 but I'm also setting it in the effect， so if I set seconds in the effect and it's also part of my dependencies。

 then the effect will trigger itself over and over in an infinite loop。

That's why I pass a function into set seconds。Additionally。

 always remember that the effect function is only called after render。

 so the first time that your component renders， it won't have had any effects triggered。

 and this can bite you if you're expecting your function to be called before your component renders。

Use layout effect is the solution to this。 It's the same hookers use effect。

 but it triggers just before render。Please note， though。

It's not recommended to use the Use layout effect where you can， you should use the user effect tool。

Great work。Thanks for getting through this lecture。

 I really recommend you go and have a play around with Use effect in your spare time。

 There's nothing quite like using a hook when you're trying to learn how to use it。

 And Use effect is one of the more complicated hooks and react。😊，Until next time， see your letter。



![](img/7948c9f77b621fec8379dcca8ff91e64_37.png)