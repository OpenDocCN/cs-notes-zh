# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P33：32_什么是资源,它位于何处.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now you should be familiar with creating react components and adding text to them。

 but text will only go so far in an app and users expect things like images。

 video or audio for a more complete experience Fortunatelyly you're here to learn about assets and how to use them to liven up your app By the end of this video you'll know what asset are and how developers keep them organized in react you'll also learn some of the common ways to import asset files to be used in your react apps。



![](img/46c773d961d87fcf817d1e87493e4870_1.png)

![](img/46c773d961d87fcf817d1e87493e4870_2.png)

Let's begin by making sure you fully understand what developers mean when they mention the term assets。

In React assets can be things like images， style sheets， fonts， media files。

 or basically any file that's needed by your app at runtime in other words assets are all the files that your react app needs to have access to in order to work as intended。



![](img/46c773d961d87fcf817d1e87493e4870_4.png)

![](img/46c773d961d87fcf817d1e87493e4870_5.png)

For example， you might code your app to display specific images or use certain fonts。



![](img/46c773d961d87fcf817d1e87493e4870_7.png)

But if you run your app without these being available。

 it might exhibit unexpected behavior such as displaying a placeholder or using a default font that's why it's important to keep assets easily and readily available to your components a common way to do this is to add an assets folder inside of the source folder and keep all your app's assets there。



![](img/46c773d961d87fcf817d1e87493e4870_9.png)

![](img/46c773d961d87fcf817d1e87493e4870_10.png)

![](img/46c773d961d87fcf817d1e87493e4870_11.png)

Some assets can also be placed inside the public folder for example。

 in the default react installation， you'll find that some images such as Favicon and logogo 512 are stored there by default The general rule for asset storage is that if your app can compile without it you can keep it in the public folder。



![](img/46c773d961d87fcf817d1e87493e4870_13.png)

![](img/46c773d961d87fcf817d1e87493e4870_14.png)

![](img/46c773d961d87fcf817d1e87493e4870_15.png)

For instance， Fbicon is in the public folder because no component depends on it In other words。

 React doesn't need to use the Fbicon file to compile all the components into an app that will get served in your local browser while you're building your app。



![](img/46c773d961d87fcf817d1e87493e4870_17.png)

![](img/46c773d961d87fcf817d1e87493e4870_18.png)

However， suppose you have an image that needs to be imported into one of the app components。

 then it's best stored in the assets folder Now you're familiar with the concept of assets in react let's explore how to use assets。



![](img/46c773d961d87fcf817d1e87493e4870_20.png)

![](img/46c773d961d87fcf817d1e87493e4870_21.png)

Suppose you're a developer working on an app that helps people adopt animals in their local area。

 you have built most of the app' components， but you are waiting on the adoption centre to send you pictures of the animals that are looking for a new home In preparation for this you create the assets folder in the reactact application。



![](img/46c773d961d87fcf817d1e87493e4870_23.png)

![](img/46c773d961d87fcf817d1e87493e4870_24.png)

![](img/46c773d961d87fcf817d1e87493e4870_25.png)

The pictures arrive and you place them inside the assets folder so they can be added to your components。

To add an asset file to a component， you first need to import it。

 this can be done with an import statement。

![](img/46c773d961d87fcf817d1e87493e4870_27.png)

For example， suppose this component will display a picture of a cat you type the keyword import followed by the name you want to give your asset you can call this almost anything you like but it's best to stick to something descriptive that describes your asset for example cat then you type the keyword from followed by the path to your assets In this case it's a file named Cat do JPEG located in the asset folder The next step is to create the function and write a return statement inside the return statement you use the image tag and then set the source attribute to reference the asset name which is cat in curly braces。



![](img/46c773d961d87fcf817d1e87493e4870_29.png)

![](img/46c773d961d87fcf817d1e87493e4870_30.png)

![](img/46c773d961d87fcf817d1e87493e4870_31.png)

Alternatively， instead of the asset name， you can reference the pass to the assets folder relative to the component。

😊，You can do this with the require keyword， as well as curly braces that encase the JSX expression and act as delimiters。



![](img/46c773d961d87fcf817d1e87493e4870_33.png)

![](img/46c773d961d87fcf817d1e87493e4870_34.png)

It's important to know that with this method you no longer need the import statement This is because you're using the required syntax right inside the JSX expression that's assigned to the SRC JSX attribute。



![](img/46c773d961d87fcf817d1e87493e4870_36.png)

In this video， you've learned what assets are in react and the best practices for storing them in your project folders。

You've also learned some of the most common ways of importing and using image assets in your react apps。

