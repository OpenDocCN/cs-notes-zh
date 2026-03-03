# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p10 10_03_03_WA4E-HTML超文本标记语言第一部分.zh_en -BV1Kt421V7EE_p10-

![](img/3deeec150e85d6fb90707cad1bf23ece_0.png)

Hello and welcome to our lecture on H， the hyperpertext Markup language。

 So we're going to place this in the context of our request response cycle and sort of hears us in the request response cycle and our browser and what we're seeing。

 We make a click。 It goes across the network to the web server， runs some code。

 maybe talks to a database， formats up some new stuff。

 and we get the response then HTML comes out and then that's parsed to make the Dom and what we see is the document object model。

 and we're going to ignore most of that in this lecture。 We are really only going to talk about。

 this part here and that is what this response is。 it's HTML。

 and it is parsed and it's read through and it's used to construct the document object model。

 which then shows what we see。

![](img/3deeec150e85d6fb90707cad1bf23ece_2.png)

And so HTML is just a technique of using some special characters less than in greater than to add tags to indicate what we want to see like the paragraph tag。

 the paragraph tag， that's a paragraph tag， strong tag makes things bold emphasize tag in a paragraph tag。

 and so we have these tags and we just mark up we' communicating meaning。

 if you're old enough to remember word processors used to have ways to look at the actual codes that were being stored in the word processor file。



![](img/3deeec150e85d6fb90707cad1bf23ece_4.png)

So the web is the HTML and hypertext transportport protocolcol and all that stuff is a relatively recent invention and we're doing so many cool things with it。

 it's continuously evolving and really were less than in a 20 years old and so but we're doing so much with it it's continuously evolving So HTML and CSS are really kind of at the edge looking back in the early days if we take a look at what HTML was really intended to do。

 it worked on a next computer in the early 1990s and so this is the next browser which came from CEN and it had everything in a new window。

 images were not shown in line and then there was the NCSA Mosaic browser which was the first browser that was universally available on UniX Windows and Macintosh and you see things like gray background and blue links and highlighted links that you visited in purple。



![](img/3deeec150e85d6fb90707cad1bf23ece_6.png)

![](img/3deeec150e85d6fb90707cad1bf23ece_7.png)

In the early days it was nothing like what we see today you know in the early days we were just amazed and happy that we could see a link and you'd click a link and something would happen。

 but today money is to be made based on making stuff super beautiful on the number of pixels and how things line up and how things are shoved over and how navigation looks and so today we need to create beautiful web pages whereas in the old days we are just amazed to have web pages that worked in the first place。

And of course， computers have gotten much faster capable handling video and images back in the old days images were costly。

 both for network bandwidth and for the time it took your computer to display them。

 And so that just affected how we did it。 and it's kind of fun to use the way back machine otherwise known as the Internet Arch to go back and look at some of these older web pages and realize that it's still amazing that a lot of them pretty much work。



![](img/3deeec150e85d6fb90707cad1bf23ece_9.png)

And in the good old days， Hm was kind of a wild West。

 The browsers did not want to show broken H is broken H。 And so they compensated for it。

 And so in the old days。 We had things like tags that could be uppercase。

 We would have a paragraph tag that didn't finish。 we would have L tags that didn't finish。

 we would have attributes that didn't even have double quotes in them。

 So there was all kinds of stuff。 And literally， you can take this bad page。

 And you could put it into a web browser and it will still display。 So， so H。

 while it technically is a very precise language and you can make syntax errors。

 browsers are extremely flexible in terms of parsing it。 Now。

 you're not going to get predictable results。 like browsers can go into what's called quirks mode。



![](img/3deeec150e85d6fb90707cad1bf23ece_11.png)

And so in order to create the standards environment that we have today， Timberners Lee。

 one of the original founders of the World W Web， helped found an organization called the Worldwideide Web Consortium where the W3C。

 and it really decided that instead of just letting people write a browser and having HTML be be defined by the browser。

 instead they would write a spec for what HTML was。

 and then multiple vendors could produce the browsers and took a while for this to become successful。

 but there was a need for every vendor to build a web browser and so they worked with the World Web consortium and like the mid and late 90s。

 9596 94 through 98，99 where web consortium created a lot of wonderful standards around the World wide Web。



![](img/3deeec150e85d6fb90707cad1bf23ece_13.png)

Now， once we started having rules， then we tend to want to follow those rules。

 And so tags need to be lowercase attributes like this image source equals。

 if have to have double quotes around them， you have to have open tags and close tags。

 open tags and close tags。 And so theres there's a set of rules。

 and now we are much more precise about our HTML and we try to write it as precise as we can。

 so that we get the best performance and the best sort of rendering out of the browsers that we can possibly get。

 because if you don't write precise HTML， then the browsers are going to make decisions as to how to render things。

 whereas if you write precise HTML， then you really are in control of how the browser lays things out。

So up next we're going to talk about HTML itself， look at some HTML documents and take a look at the syntax of HTML。



![](img/3deeec150e85d6fb90707cad1bf23ece_15.png)