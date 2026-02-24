# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P8：7_导入组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

One of the advantages of components based architecture is that your app is split up into individual self contained components。

And as you have already learned， these components can be used to build powerful UIs based on reusable components of code in order to create a fully functioning react app。

 you need to create a collection of components but with the app broken into several different components you might be wondering how do you locate and integrate them all into your app in this video you'll learn about the concept of modules and how to manage your react components by placing them in a components folder。



![](img/bd259ac3e61591a752569a723af96f70_1.png)

Finally you'd explore the structure of the import and export statement As a developer you often need a way to use and reuse components that may have been defined elsewhere or created by someone else for example do you recall the concept of modules in JavaScript modules are standalone units of code that you can reuse again and again being standalone means that you can add them to your programs。

 remove them and replace them with other modules and everything will still work well in reactact you can make use of this JavaScript feature to separate your components by placing them in their own file then you can use the import and export statements to make the files communicate with each other。



![](img/bd259ac3e61591a752569a723af96f70_3.png)

![](img/bd259ac3e61591a752569a723af96f70_4.png)

The export statement is used to make a module available to another module。

 it helps to think of every JavaScript file as a module。

Then in order to make the functions and variables available to other files。

 you need to export them which makes them available by the import statement in JavaScript there are two types of exports default export and named exports the default export is used when the function name as the same as the file name and named exports are used when you want the function name to be different from the file name at this point you may be wondering what is the difference between modules and component since they are both essentially just JavaScript files and you're right。

 while they have similarities it can help to think of a component as a single part or small piece of functionality like a button then you can think of a module as something that's larger than just one component like a series of components。



![](img/bd259ac3e61591a752569a723af96f70_6.png)

![](img/bd259ac3e61591a752569a723af96f70_7.png)

This technique of splitting your code into several modules is known as modular programming and it complements the component based architecture of react。

To help you understand this better， let's explore the following scenario。😊。

Suppose you're a developer currently in the process of building an application with reactact。

 and there are several components that need to be included in the app。

Some of the required components have already been created by your fellow developers。

 so you need a way to import them into your app。To do this。

 you need to use the operation known as importing。And in react。

 you import components into your application using the import statements。



![](img/bd259ac3e61591a752569a723af96f70_9.png)

You may have already noticed the import statement in the default index dojS file where the app component is rendered。



![](img/bd259ac3e61591a752569a723af96f70_11.png)

In react to import a component， you use the keyword import。

 followed by the component name you want to import。

Then you use the keyword from to specify the location of where the component is located。

You need to use a file name sequence such as a dot forward slash before the file name。

 but the file name extension is not required Okay， so now you know about the syntax of the import and export statement。



![](img/bd259ac3e61591a752569a723af96f70_13.png)

Let's explore how you can structure your component in react。

Remember that a component is essentially just a JavaScript file reactact doesn't have strict rules on how you put files into folders。

 however， there are a few common approaches you may want to consider one approach is to place all components in a folder named components。

This allows you to structure your project by grouping similar files together for example。

 suppose you are building a payment page for an ecommercecommerce app。

 the page contains three sections that will each be represented by a component in react first a header section using a component called header then a payment section using a component called main。

And finally， a sidebar using a component called sidebar each component will be called and habits contents returned to the root component of our application。

 which is app。 JS In this video， you explore the concept of modules and the structure of the import and export statement。



![](img/bd259ac3e61591a752569a723af96f70_15.png)

![](img/bd259ac3e61591a752569a723af96f70_16.png)

You also learned how to manage your react components by placing them in a components folder。

