# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P30：29_导航栏.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By the end of this video， you will know how to install the react router library on your machine。

 which gives you more tools for setting up navigation in your apps。

 You also practice using this library to create a basic navigation for a web page。

 Let's examine a starter app that I've already prepared。

 It has two components which are named home page and about me。



![](img/236c0f33aca94f6cf84e8aae61a0a8c8_1.png)

Currently， homeage is written to display the header text。 Welcome to my site on the page。

 The about me component displays the header text about me。

Both components are children of the app components。

Notice that home page and about me are both imported into the app component and referenced using An tags。

However， with the default react library， these anchor tags won't work as expected。

 This is because react can't imitate multi pageage websites。 However。

 I can make this possible with the help of another library known as react router。

 As you may have guessed from the name。 react router gives you more control over the routing of components。

 I'll install it using the MPM command NP PM I react dash router， dash Dom addem 6。



![](img/236c0f33aca94f6cf84e8aae61a0a8c8_3.png)

![](img/236c0f33aca94f6cf84e8aae61a0a8c8_4.png)

To confirm that it's available， I inspect package that J and find the new entry in the dependencies。

 which is react routetter Dam 6。3。0。Now that react router is installed。

 I'm ready to make my broken links work First I'll access the index AJS file and enter a statement to import browser router from reactact router Dom。

Once I've imported it， I need to wrap the app JSX element inside browserer router by placing it between the browser router tags。

With that done， let's return to Abda JS here I need to import routes and route from reactr or Dam。

I also need to replace the child JS X elements with some different code Home page becomes route path equals and then forward slash between double codes。

 This is followed by element equals， and then the home page JSX element inside of curly braces。

 Note that the route tag is self closing and has no children inside。For about me。

 I add a similar line， but I'll add about dashash me after the forward slash。

These lines will also be encased between route tags。

If I go to my browser and type the exact link on one of the routes， for example， slash about me。

 I'll get only the About me component showing under the navigation。However。

 if I remove the about me from the URL， in other words。

 if I open the route route that is represented with a forward slash。

 then itll show the text from the home page component under the navigation bar。

 noticeice that I'm grouping all the routes by wrapping them inside the routes JSX element。Also。

 note that the nav tags are outside of the route tag， meaning that navigation is outside the routes。

 Finally， I need to replace the anchor tags with react router links。

 This allows the correct component to be loaded when the link is clicked rather than simply refreshing the page。

 So on the app component， the anchor tag for home page becomes link to equals and then forward slash between double quotes。

 This is followed by class name equals and then naav dash item and double quotes。For about me。

 the change is similar， except that about dash me appears after the forward slash。

I also need to import link from react router Dam and save my changes。

Now when I click on either of the NvAR links， the correct content loads in the browser。



![](img/236c0f33aca94f6cf84e8aae61a0a8c8_6.png)

In this video， you learn how to install the react router library and utilize some of the key functionalities to create a appv bar。

 Now you're ready to learn about more efficient ways for users to navigate your apps。



![](img/236c0f33aca94f6cf84e8aae61a0a8c8_8.png)