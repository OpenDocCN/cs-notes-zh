# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P60：18_使用 useEffect 钩子.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

To demonstrate how to use the use effect hook within a component。

 let's continue working on the little lemon app。 Sa the owner of the restaurant wants to add a specific way for the user to interact with the app on a button click。

 the owner wants a welcome message displayed and on another button click。

 the owner wants the message hidden。Additionally， the owner wants this change to be reflected on the browser tab where the app is served。

 Up a browser tab is an example of a side effect。In this video。

 I will demonstrate how to do this by using the Use Effect hook to perform side effects and react。

 as well as how to control when the use effect function is run using the dependencies arrayray。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_1.png)

I am going to use an app I built previously using createreate React app to demonstrate how to use the Use effect hook to describe what's happening。

 let's start with a return statement。I have a wrapping， div， and inside of it， an H1。

 a button and a JSX expression that uses the logical and operator to conditionally render an H2。

The button has an on clickick event handling attribute and it triggers the click handler function。

 which I've declared as a function expression starting on line7。On line  five。

 I've destructured the toggle variable from a call to the U state hook to track the state of the toggle variable and make the conditional rendering in the return statement possible。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_3.png)

Now let's inspect my app in the browser as it's currently being served。

Everything is working well when I click the button。

 the sentence welcomel to Little Lemon appears under it if it wasn't shown previously and vice versa。

Although the app is working well， my app currently has no way of updating the text in the browser tab like the restaurant owner wants it to do。

This is an example of a side effect， which is why the correct way to add this functionality is to use the Use effect hook。

 so above the return statement， I'll add a call to the use effect function as follows。

 Re dot use effect。

![](img/0f94c59f9c40d1fe72eccfba9b3959b5_5.png)

I need to pass a function to the use effect call， so I'll add an arrow function without parameters。

 and in the body of the arrow function， I'll add this ternary here。

 which checks if the value of the toggle variable is true or false。If it's true。

 it should return the string that reads We to Little Le。 Otherwise。

 it should return the string that reads using the use effect hook。

 Whatever gets returned is the value I'm assigning to the title property of the document object。

 This property thus dynamically updates the text showing on the tab of the browser where this react app is served。

Let's inspect the updated app in the browser。

![](img/0f94c59f9c40d1fe72eccfba9b3959b5_7.png)

I can confirm that with every click of the button， the title on the tab is updating to one of the two specified strings。

So imagine that the owner has changed his mind and he wants the title on the document to be set on the initial component render。

 After that， he doesn't want it updated。

![](img/0f94c59f9c40d1fe72eccfba9b3959b5_9.png)

This is where the dependency array comes in。 The dependency array determines when the use of effect hook will be invoked for now。

 I'll update my code with an empty dependency array。

 meaning I'm not tracking the state of any state variables。In other words。

 regardless of what is happening in my app， I don't want the Use effectact hook to be invoked。

This means that it'll be invoked only once。 And after that， no matter what happens in my app。

 the use effect hook will no longer be run。Now that I've updated my app。

 let's save the changes and examine how this affects the behavior of my app in the browser。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_11.png)

The Use E hook runs only once， outputs the words using the Use effect hook， and after that。

 regardless of how many times I click on the toggle message button。

 there are no further updates to the tab title。 The dependency array is there to watch for changes to a specific variable。

 and based on that， execute the function that's passed in as the first argument of the use effect function call。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_13.png)

This means that if I want to run the Use effect hook whenever there is an update to the value stored in the toggle variable。

 I need to add the toggle variable to the dependencies array。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_15.png)

After this change back in the browser， the Use effect hook will be run every time the toggle message button is clicked because the click handler updates the value of the toggle state variable by invoking the set toggle function。

This， in turn triggers the use of facting vocation since the dependencies array is set to watch for changes to the toggle variables's value。

And there you go。 I have a way to fulfill any of the restaurant owners' requests that might involve some side effects in my react apps。

 You should now have a better idea of how to use the use effect function to handle side effects and of how to use the dependency array to determine when it will be invoked。



![](img/0f94c59f9c40d1fe72eccfba9b3959b5_17.png)

![](img/0f94c59f9c40d1fe72eccfba9b3959b5_18.png)