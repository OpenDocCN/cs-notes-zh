# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P117：34_制作原型并测试.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

You're ready to prepare the application for testing through an interactive prototype on FGma。

 You can create the prototype and share a link with users when you are ready for testing。

 Let's cover the prototype。

![](img/11d2f7f2c788651566f98d29129f7a9a_1.png)

First， I open my figma file。 Now， I can scroll the category buttons horizontally and the dishes vertically。

I can also toggle the categories on and off。Be mindful that it's beyond the scope of this prototype to make these dynamically filter the content。

 But it's a great starting point to facilitate a rich user experience for the test participants。

 Let's create both of those effects in Figma。😊。

![](img/11d2f7f2c788651566f98d29129f7a9a_3.png)

![](img/11d2f7f2c788651566f98d29129f7a9a_4.png)

To replicate this， I need to delete the current set of category buttons on the home screen。

On the right hand side of the layers panel。

![](img/11d2f7f2c788651566f98d29129f7a9a_6.png)

I go to the local components page， which I've created to store my components。

Let's create the category button's toggle interactive component。To do this。

 I create an auto layout button and convert it into a component。

 Then click the component button and name it Master button。I hit enter。

 Now I right click this component， go to main component， and then add variant。

 This is where I'll put in the variation。 In this case。

 what happens when the user toggles or clicks it。A perforated outline appears。

Now I want to style the variant to do that， I select it。 and in the label in the design panel。

 I type selected。Then， I hitd enter。Now I customize its appearance。

 select the button and change the fill to a darker color。Next。

 I double click into the text and then change the fill of the text to a lighter color。

Now I want to prototype what happens between the two states。 click the prototype tab on the right。

Double click on the first instance。Drag the prototype icon to the second one and the Pro tab appears。

You'll see on click， change to the selected icon。 Now I want to double click and drag the second property up to reverse the process。

So when this one is clicked， it will go to the selected version。

This is how to toggle between two states。Let's get this onto our prototype and see how it works。

 I'm going to go to page 1 on the left hand panel。

![](img/11d2f7f2c788651566f98d29129f7a9a_8.png)

I go to the assetsets tab beside it and type in Master button。The button shows up。

I drag this onto the auto layout under order for delivery。



![](img/11d2f7f2c788651566f98d29129f7a9a_10.png)

Let's test it now。I click the present prototype button。And the button changes when I click it。

Perfect。

![](img/11d2f7f2c788651566f98d29129f7a9a_12.png)

Let's make some more category buttons。I select the button and duplicate an instance of the button component by pressing Cl or command D。

The button duplicates， but they are stacking one on top of each other。

 This is happening because the parent auto layout frame is set to stack vertically。

I'm going to select both buttons and make these an auto layout frame。

Then in the auto layouty propertiesperties panel on the right， I can change their direction。

I can duplicate as many of these category buttons as I want。

I type into each one to give them unique titles。I gave each one a new label。Next。

 I want to make a horizontal scroll。 I double click the frame。I can see it's called frame 5。

I am going to rename it to dish category。I want to limit the amount that these buttons can scroll within the screen。

To do this， I double click to get into the frame and convert it into a component。

Then I right click and choose frame selection。I scale it from the right hand side to snap to the edge of the device window。

 This creates the overflow edge。I select the prototype tab and click on Overflow scrolling。

Then I click on horizontal scrolling。

![](img/11d2f7f2c788651566f98d29129f7a9a_14.png)

Let's check it。

![](img/11d2f7f2c788651566f98d29129f7a9a_16.png)

Now， the category buttons toggle on and off， and I can scroll left and right。

I repeat the process to scroll the dishes vertically。



![](img/11d2f7f2c788651566f98d29129f7a9a_18.png)

To share my prototype， click the Share button， copy the link。

 and share it with the test participants。

![](img/11d2f7f2c788651566f98d29129f7a9a_20.png)