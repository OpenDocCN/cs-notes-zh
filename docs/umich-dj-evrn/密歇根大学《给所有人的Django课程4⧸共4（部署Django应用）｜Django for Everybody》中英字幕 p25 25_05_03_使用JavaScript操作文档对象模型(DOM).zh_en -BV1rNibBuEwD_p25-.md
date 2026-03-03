# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p25 25_05_03_使用JavaScript操作文档对象模型(DOM).zh_en -BV1rNibBuEwD_p25-

I mentioned that JavaScript owns the document object model。

 the document object model is what we see when we're looking at the browser。

 Well browser parse the HTML sometimes our JavaScript writes it and then creates this object。

 we call the document object model， which is then displayed to the user through a window。

 a window is the subset of the document object model。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_1.png)

In whatever JavaScript we write， we can read， manipulate， and update the Dom。

 and as soon as the Dom is updated， the user sees the updates through the window。

And we can also just go into the debugger and directly manipulate the document object model。

 So if we go back to the 01 No script， there's no JavaScript in here。

 so you just go it shows you a header and a paragraph and that's a document object model。

 but you'll note that if you go into In element and then go into that paragraph tag。

 you can change and add the wordCo。

![](img/09e2e7a8a05dd9491cf5c68bc907669c_3.png)

In a sense that the bugger is JavaScript right and you can actually type JavaScript commands into the bugger if you do the right thing。

But the owner， the debugger is。Owning the document object model as well。

 And so you simply can change the document object model。 And literally it changes the Ui。

 but truly the document object model changes。 So you can take a you can even change the kind of a tag you're dealing with。

 You could turn this into an anchor tag。 You could add some h。

 You can change the document object model。 You're displayed。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_5.png)

It just， you change it and you see it。Now I mentioned this thing called the window。

 there are two sort of foundational objects in JavaScript in the browser， there's the Dom。

 and the Dom is an abstraction， it is a structured hierarchy of tags， column elements。

The window is how we see it。So you can think of this picture that I've been showing you。

 parsing the response， running some JavaScript， and tweaking the document object model and showing it to the user。

And if you change the document object model， let's immediately update it。On the left。

 that's a kind of an oversimplification because the way we actually view the document object model is through the window。

 The window is what's on your screen and and probably most。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_7.png)

Easy way to demonstrate this is to understand that the document object model could be very large。

 and the window could be very small， and the document object model doesn't change。

 and you can resize the window back and forth。 So sometimes you see scroll bars。

 The scroll bar is not a notion in the document object model。 It's a notion in the window。

 The window has a certain height。 The document object model may or may not completely fit in the window。

 and that has to do with the window height。 and so scroll bars。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_9.png)

![](img/09e2e7a8a05dd9491cf5c68bc907669c_10.png)

And so， for example。If you look at 06height。html， all it does is puts out the header。

 puts out the paragraph and then prints out window height and window width， window。inhe and window。

in width。These are the height of the window， not the document object model。

 but the window through which we're viewing it。 and so if you show this page with the debugger turned on with a really tiny window。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_12.png)

It says that the height is 116。 If you make the window bigger and hit reload。

 it says the heights 256。 So in JavaScript， we can ask questions about the window and we can do things to the window。

 One thing we could do is we could scroll it up and down and that's actually a common thing to do in JavaScript。

 If you have a big document object model and you got a scroll window and you want to show the user a particular thing like go to bottom。

 JavaScript can scroll the window down to the bottom。Or up。Our don。

 I don't get those right very well。We can control the window。

 in this case we're simply asking it how tall you are and how wide you are。

 but we can also control it。

![](img/09e2e7a8a05dd9491cf5c68bc907669c_14.png)

And so if we take a look now and we make 07 scrollroll。htM。

 we can see that we have nine paragraphs in a header， that is the actual content。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_16.png)

Okay， and if we have a tall window， we can see the whole document， but if we make the window smaller。

 then we can only see a subset of the document object model and so the window height changes。

And if you look， you now have a scroll bar and what does the scroll bar do Well。

 it just takes and moves the document object model up and down。 Well。

 it moves the part of the document object our view of the document object model up and down。

 but if you're doing an inspect element in some browsers。

 you will see that it's telling us with little kind of annotations that the body is being scrolled right now and up through paragraph 4 is overflowed off the screen up and paragraph 78 and9 have overflowed and they've gone off the screen below now if you play with this and you resize it and refresh it and resize it refresh it。

 you'll see this whole I mean you don't on the left the whole thing shows and so body is not indicated as the scrollable element。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_18.png)

And the headers not overflow， et cetera， so you can play with this。

 but play with it with different sizes， refresh it and then inspect element and watch how the scroll。

 the overflow and the scroll bar， and in this case I'm not printing out height but you would be seeing that the height would actually change。



![](img/09e2e7a8a05dd9491cf5c68bc907669c_20.png)

So one of the things that we're going to do next is we're going to modify the document object。

Model in JavaScript。