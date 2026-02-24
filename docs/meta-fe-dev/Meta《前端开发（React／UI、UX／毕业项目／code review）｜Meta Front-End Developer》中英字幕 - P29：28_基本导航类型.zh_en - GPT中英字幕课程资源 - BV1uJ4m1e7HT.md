# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P29：28_基本导航类型.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In the early days of the web， there were no true standards for design。

 which meant that developers were often very experimental。There were various designs and experiments。

 but ultimately the web development community settled on a few best practices and today the web is a mature medium in this video you'll learn about the basic types of navigation on websites and how the navigation process works in react Now if you think about the history of web layouts and web navigation。

 it's likely development of other great inventions throughout history。



![](img/56f0b118fcbc97abec7313ee7b729c9f_1.png)

For example， after the Wright Brothers flew the first plane in 1903 in Kitty Hawk， North Carolina。

 there was a period of a few decades where engineers were experimenting with different designs。

Planes with two or three sets of wings were the order of the day。Finally。

 after this initial exploration stage， airplane design settled down and the rules and best practices of building airplanes were established。

 like the development of rules of airplane construction。

 after the experimental years of the early web， the web design and development community settled on a few accepted and expected designs。



![](img/56f0b118fcbc97abec7313ee7b729c9f_3.png)

![](img/56f0b118fcbc97abec7313ee7b729c9f_4.png)

The focus in modern website navigation user interfaces is on utility。

Stephen Krgg's famous book on user experience， don't make me think。

 sums up the rule that developers are following today。

It's your duty as a web developer and designer to follow the best practices that have already been established。

 for example， a steering wheel does not belong on a washing machine or an old style phone dial does not belong in a car in the same way you wouldn't want to confuse your website visitors by giving them navigation that might look and feel smart but that's completely different from what they used to。



![](img/56f0b118fcbc97abec7313ee7b729c9f_6.png)

So you might be wondering what is accepted modern website navigation and how does it work in react？

Website navigation is the part of any website that allows you to browse through various pages or links on that website from a single component there are several practical implementations of this user interface pattern。

Let's explore each briefly now the most common navigation component are a horizontal navigation bar。

 a vertical navigation menu， a menu hiding behind a button and a footer navigation menu。

 the horizontal navigation bar is often referred to as a nav bar and the vertical navigation bar is also known as a sidebar navigation。



![](img/56f0b118fcbc97abec7313ee7b729c9f_8.png)

The menu hiding behind a button is usually represented by an icon that has three horizontal lines and is thus referred to as the burger icon or the burger menu an alternative to this is the drop down navigation menu known as the mega menu This menu is usually also hiding behind a button and is usually used as a sub or large menu on Ecommerce sites and other sites that require many links。



![](img/56f0b118fcbc97abec7313ee7b729c9f_10.png)

![](img/56f0b118fcbc97abec7313ee7b729c9f_11.png)

The footer navigation menu is usually displayed as several visual columns containing links。

 all these mentioned menu patterns can often be used simultaneously in different parts of the same page。



![](img/56f0b118fcbc97abec7313ee7b729c9f_13.png)

Additionally， a more complex navigation UI can include multiple navigation approaches in a single component you may for example。

 have a horizontal navigation bar or nav bar with drop down menu items if you're using a smaller resolution the navigation bar displays as a burger menu icon。



![](img/56f0b118fcbc97abec7313ee7b729c9f_15.png)

When you click on the Bur menu icon， a mobile sidebar or a vertical menu appears。😡。



![](img/56f0b118fcbc97abec7313ee7b729c9f_17.png)

Okay， so now you're familiar with some of the navigation types that are available in your react apps。

 let's explore how they are implemented to load to different pages。

If you compare the navigation of websites built with reacts against HTML and CSS。

 you'll likely find no visual difference。While visually everything looks the same， in the code。

 reactact deals with navigation between pages differently。



![](img/56f0b118fcbc97abec7313ee7b729c9f_19.png)

This is because the entire app is loaded inside a single div so you're not actually visiting different pages like you would with hyperperlinks and HTML files instead the content of that single div is controlled by react and it's based on changes to the virtual Dom it either updates the existing view or loads a completely new view。

 giving the user the impression of visiting a completely different URL。Recall that with HTML。

 developers can use a list to make a navigation menu。

 each list item contains a hyperlink to an HTML file， then some CSS to style the menu。

 like the display inline property to make the list display horizontally。

To help illustrate how navigation between pages works with react。

 think about how the buttons on the inside of an elevator work。

Pressing the button will take you to the selected floor。Similarly。

 each link on a website takes you to a different page if you click on it。

 if however you're in a react elevator， it's as if the elevator never moves。😊，Instead。

 when you press a button in this react elevator， the entire construction of that given floor is injected into a single floor of this impossible building。

 that means that react by itself only takes care of the visuals of a single page but has no notion about navigation between pages however this functionality is not available to developers from the react library itself in order to achieve this illusion of a multi-page website you need to add the react route to library to your react projects。

Once again， you add this using the import statement and you'll learn more about how to do this soon。



![](img/56f0b118fcbc97abec7313ee7b729c9f_21.png)

Well done。In this video， you learned about the basic types of navigation on websites and how the navigation process works in Re。

😊。