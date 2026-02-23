# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P20：19_父子数据流.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Imagine you are working for an online retailer that discounts prices regularly to keep stock moving。

Sallles are announced at multiple points on the website。

 but what's the best way to keep this information up to date？



![](img/669dc4bfe9cde169990ec243e71eb219_1.png)

For example， updating items individually would be tedious in time consuming。😊，Fortunately。

 it's possible to change information at a single point and have everything else update automatically to match。

😊，This idea illustrates a parent's child relationship。

 and in this video you'll explore this concept as it applies to react。By the end of this video。

 you'll be able to describe the parent child's uni directional flow of data。

 and you'll gain an understanding of the hierarchy of react。

Let's start with an example of two components which will be used in the same app。

First is the promo component， which will return the contents of the promo heading component that you will create later。

To build the promo component， you can declare the function promo and then write a return statement inside of curly braces。

This statement has a div inside of which promo heading is called。

This is then followed by the line exportport default promo to make the component accessible。Next。

 let's write the promo heading component。You can declare function promo heading and in curly braces type return opening parenthesis。

 H1 tag， the text 80% off sale， H1 closing tag and closing parenthesis。Once again。

 don't forget to export the component to make it available。Success。

You've now created the component promo， which calls a function from the component promo heading to return the text 80% off sale。

In this example， the promo component is known as a parent component。

 and the component it renders promo heading is referred to as the child component。

Now let's say that the discount increases to 99% off and you need to update the code to reflect this。

One approach is to update the text inside of the H1 tags in the promo details component。

That's a quick fix because there is only one change to deal with。However。

 let's explore a more complex situation。😊，This time。

 your manager asks you to call the promo heading component in the sidebar and photo component of the web app in addition to the promo component。

They also want two messages displayed， 99% of all items and everything must go。

These new requirements mean that the approach of updating the child component will not work quite as well Why is that Well it means that you now have to update multiple components with the same data。

😡，This is not in line with a general program and principle of Dr or don't repeat yourself。

 which aims to reduce needless code replication。Also。

 consider the following possibilities while entering the same text into several components。

 it's possible you make a typing error， also what if your boss decides to change the discount again？

😊，It means you'll have to change the text in all the connected components once more。😡。



![](img/669dc4bfe9cde169990ec243e71eb219_3.png)

Then instead of writing the same code over and over， you can change your approach。😡。

You can establish a single source of truth that contains the two strings that store the values for the texts。

 99% of all items and everything must go。This will be contained within the parent component so that any data needed can be passed onto the child components using props。



![](img/669dc4bfe9cde169990ec243e71eb219_5.png)

Now let's use this approach to update the promo component。First， you create a single source of truth。

A JavaScript object named data。Data is an object that will contain two properties named heading and call to action。

 both represented as strings。Next， you update the promo component to pass the heading and the call to action values of the data object to the promo heading component。

This is known as passing data from the parent to the child component。

Back inside the PRmo heading component， you update it to accept data from its parent component。

To do this， you'll need to first delete the existing H1 in the return statement and then add a new H1 for Pro dot heading and an H2 for Pro dot call to action。

Now this component accepts a props object， specifically it's two properties heading and call to action。

The values of the props object are determined in the parent component when you add to the specific JSX elements that should be rendered。

This was achieved when you rendered the promo heading inside the promo component here you access the properties on the data object using the regular dot notation syntax of plain JavaScript。

Knowing this， you can now code the sidebar component and the footer component in a similar way to the promo heading component。



![](img/669dc4bfe9cde169990ec243e71eb219_7.png)

Remember that in react， the prop data always flows from the parent to the child's component。😡。



![](img/669dc4bfe9cde169990ec243e71eb219_9.png)

And using props helps you avoid the need to change the data in several places。Instead。

 you make the change at the data source， the parent。

 and the updates will be applied to the child automatically。



![](img/669dc4bfe9cde169990ec243e71eb219_11.png)

In this video， you learned how the parent child relationship can be set up so that data flows from parent to child。

By storing data in the parent component， you can dynamically pass it to the child components without the need to update children individually。

