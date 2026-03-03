# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p12 12_03_05_WA4E-HTML代码详解.zh_en -BV1Kt421V7EE_p12-

Hello and welcome to Web applications for everybody and this。Scrreeencast。

 we are going to play with some of the sample code and you can either download it and play with it on your own computer or you can look at it in your text editor or if you just want to browse it。

 you can browse it here and take a look at the version that I'm using it's really been intended that you look at this in the developer tools and so you can do things like say In element。



![](img/a11a028d71b34f17dcaea3ade8516f08_1.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_2.png)

And so here we are。 we're going to this will also be a little more valuable even we're doing CSS。

 but you can see the document object model。 Now， the interesting thing here is it shows something I'm always talking about is the difference between the document object model and the source code。



![](img/a11a028d71b34f17dcaea3ade8516f08_4.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_5.png)

So this is the document object model it's kind of stylized。 If you look at the source code。

 you have to say view page source， and so the source code。

 this is literally exactly what's in the file。 and if you go look at this file at a text editor。

 you will see this。

![](img/a11a028d71b34f17dcaea3ade8516f08_7.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_8.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_9.png)

And if you're looking at it here， it doesn't quite look exactly the same。

 And some things have been done a little bit differently。 You know。

 they kind of got this extra stuff。 And this is kind of after the browser has looked at it。

 And we start talking about jascript and changing some of this dynamically。

 you'll see this part is the document and object model， but the source never changes。

 The source is what was originally downloaded when the server sent this back to us。 so。



![](img/a11a028d71b34f17dcaea3ade8516f08_11.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_12.png)

Let's take a basic look at this， I'll hide this unless I need it。

 I'll go back and forth between the source， so we have a basic document。

 HTML with a head tag in a body。

![](img/a11a028d71b34f17dcaea3ade8516f08_14.png)

And then a header。And of course， here's our header。 We're using default styling。

And paragraphs are an important part of things I you know you don't you can squeeze this up as much as you want white space sort of doesn't matter right so this white space kind of doesn't matter here。

 you know the fact that this has got extra space， it doesn't much matter and so you can see an anchor strong tag that leads to a boldness。



![](img/a11a028d71b34f17dcaea3ade8516f08_16.png)

Let's just go ahead and look at it here in the。

![](img/a11a028d71b34f17dcaea3ade8516f08_18.png)

Inspect。We'll go down here we'll find like a strong tag that's the bold。

 we got an emphasize tag and if you look a little farther you'll see there is the anchor tag。

 which is the whole anchor tag is this whole tag from the A to to the slash a list on HM that's where we're going to go if we click on this text right here and so you can see。



![](img/a11a028d71b34f17dcaea3ade8516f08_20.png)

Now this is a relative link and it turns it into an absolute link and that's because the browser knows where we're at。

 and so it sort of prefixes everything up to that to the relative link but that's nice because if we look in folders。

 we will see that these folders are all here here let me go find you that folder。

 it's pretty deep in my。

![](img/a11a028d71b34f17dcaea3ade8516f08_22.png)

Later， this will all make wonderful sense to you。I do a lot of stuff with Web。Code。



![](img/a11a028d71b34f17dcaea3ade8516f08_24.png)

Htm。Okay， so here we have after all that， here we have the files right and so this is index。

htM and indexedhtM is right there and list。htM and so if I click here， I'll go to list。

 HM and that'll pull this other file up and so these guys are all in the same folder together it just means that I can use relative links to go moving between them。



![](img/a11a028d71b34f17dcaea3ade8516f08_26.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_27.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_28.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_29.png)

Tag that's really becomes more important， especially as when we was talking about writing code inside each ti on showing people code is the pre tagag。

 and so the pre tagag and you can just say inspect to hop right down to where the pre tagag is。



![](img/a11a028d71b34f17dcaea3ade8516f08_31.png)

The pre tagag respects spaces， so all these spaces happen， the new lines happen。

 and it also shows that a monospace font you can change all these things once we get to CSS。

 but pretag when we're printing debug out from not in files like this， but when we're running code。

 sometimes it's good to print。Debugging out in。The prets。 So let's go to the next page。

 And so here's a whole series of things we're going to play with。嗯。This is a。



![](img/a11a028d71b34f17dcaea3ade8516f08_33.png)

Unnumbered list， this whole thing is an unnumbered list from top to bottom。 So when I highlight this。

 you see the whole beginning to end of the list， then each item in the list has a start an end LI tag。



![](img/a11a028d71b34f17dcaea3ade8516f08_35.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_36.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_37.png)

Right， down， down， down。So here here's this， we should learn about tables and there's a ARF。

 there's another relative link and so this is sort of my jumping off page to get to all of the all those other things。

 right， learn about tables。et cetera， et cea。 so you can see these we probably use just to take a look at the source code of this page。



![](img/a11a028d71b34f17dcaea3ade8516f08_39.png)

And so that's that's the source code that I typed in。 and you can see the LeI tags， the P tags。

 I'm putting P's inside of lis to get space。 let's see if I can sort of show you that。

 So if you look at this。

![](img/a11a028d71b34f17dcaea3ade8516f08_41.png)

And you look at the L tag， the L tag is that and the paragraph is what actually creates the vertical and horizontal space right。

 so that orange that you're seeing that's paragraph there's space that the paragraph tag has preset so that's how I do that。

Putting paragraphs and Hres， and so that's what this all looks like。



![](img/a11a028d71b34f17dcaea3ade8516f08_43.png)

So let's take a look at special characters。And so this is an interesting thing because it's not really what came out because less than requires ampersand Lt。

 but it's kind of processing that。 So let's take a look at the source code to this one because that'll be more instructive。

 So Ampersand L T， Ampersand G T， Ampersand Am。

![](img/a11a028d71b34f17dcaea3ade8516f08_45.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_46.png)

This is an ampersand in HTML and then just the letters AMP semicolone semicol is not special。

 there are only really three totally special characters less than greater than in ampersand and you can put all kinds of fun stuff。

 clubs， hearts and diamonds。

![](img/a11a028d71b34f17dcaea3ade8516f08_48.png)

And so you got the clubs hearts and diamonds， some arrows， stuff like that。

 What's nice is browsers just have these built in， although they're not necessarily the sexiest or coolest things and I think what happens when I go back on this link is I go back to the list So that's just special characters and you'll notice that the default styling。



![](img/a11a028d71b34f17dcaea3ade8516f08_50.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_51.png)

It says we've seen this one and this is how the web worked a thousand year now。

 back in the 90s is you sort of， oh， it's kind of nice that it's turning purple and you'll notice that Google does this as well when you're doing Google searches。

 it actually lets the links change color after you visited them。So let's take a look about links。

 we look at links。I'll you the source of this guy。Absolute link， AHf。Right。And then slash A。

 this is the clickable text right between the beginning tag and the ending tag。

 the attributes are on the beginning tag。Another attribute that you can add and I do it all the time is target equals blank and that basically is the way we say open this up in a new tab so you'll do this pop up in a new tab and so that's where that one goes when it pops up and so you can decide whether or not you want this to go in the same page。



![](img/a11a028d71b34f17dcaea3ade8516f08_53.png)

Back。Or in a new page， and then I got to close the tab to get back and now I'll go back。



![](img/a11a028d71b34f17dcaea3ade8516f08_55.png)

Because that's just a relative link。To list that HM so I can go back and look at the next thing。



![](img/a11a028d71b34f17dcaea3ade8516f08_57.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_58.png)

Let's take a look at how images are represented。

![](img/a11a028d71b34f17dcaea3ade8516f08_60.png)

So this is just a paragraph that has an image in it。



![](img/a11a028d71b34f17dcaea3ade8516f08_62.png)

So it's a paragraph， but that there's the image， source equals medium dot AG if you look in my folder。



![](img/a11a028d71b34f17dcaea3ade8516f08_64.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_65.png)

If you look in my folder， you see the image right there medium bo dopNG。

 you don't see the suffix because Mac is trying to hide it from me and so that's just you see this space here and here。

 the image doesn't have any space we could add some to CSS later but the paragraph is what's adding that space。



![](img/a11a028d71b34f17dcaea3ade8516f08_67.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_68.png)

Then we have just a regular old paragraph。

![](img/a11a028d71b34f17dcaea3ade8516f08_70.png)

'mNot supposed to use the center tag we'll get to the how to center stuff。

 so that's what that is saying right there and you can have an image that's right in the middle so you see where that image is。

I think of images if they're right in the middle of text。

 they're like a giant character and so that's that's how that works。

 And you can even sort of stick an image as the thing inside of a link。

 So here's the anchor tag it's that bit right there and then the anchor tag body is an image And so if I click on that it's going go back to list HM you'll notice these I'll go back to list HM。

 so I can work on the next thing。

![](img/a11a028d71b34f17dcaea3ade8516f08_72.png)

Right？Tables， again， you're not supposed to use tables for laying out like blocks of text。

 which we used to do。 We used to do things like use tables to draw border around things。

 which you'll see in CSS。 but now that's totally verboan and you're supposed to look at tables in a way that they're you know nice and pretty。



![](img/a11a028d71b34f17dcaea3ade8516f08_74.png)

So let's do a view source here。So let's see there's our table。

 our slash table and a table row now let's take a look at the dom。



![](img/a11a028d71b34f17dcaea3ade8516f08_76.png)

So apparently I didn't put a tea body， we're supposed to put a tea body in there， and I didn't do it。

 but this is the dom， the dom put it in。

![](img/a11a028d71b34f17dcaea3ade8516f08_78.png)

That's put in by the parsing。 And so clearly， I made a little mistake in my H T M L because I didn't put a tea body tag。

 And so that was added by the browser as it was parsing and reading through this。 like， oh。

 he forgot his tea body。 So it just like slapped one in for me。 And I think the mistake is。

 this is my header row。 I think that should be like a T head。 So there I go。 bad H T M L。

 It's the story of my life。

![](img/a11a028d71b34f17dcaea3ade8516f08_80.png)

And now I've got the rows and you'll notice that the Dom is kind of prettier， so sometimes I do this。

 the Dom is indented nicely， so this isn't really the source code。

 This is the data that represents this visual right it is the thing that you're seeing。

 but it is it read this from the file or from the server parsed it and produced the dock of an object model。

 I only say that like a million times。

![](img/a11a028d71b34f17dcaea3ade8516f08_82.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_83.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_84.png)

Okay， so back we go to the list， we're making pretty good time。嗯。So heres some really bad HTML。

I'm going to view source on it。 And again， you'll see sort of the difference between the document object model。

 When you're debugging these things， you will have to sometimes view source。

 Sometimes document object model will be the only way to debug it and sometimes view source。

 So this is the one that's got bad stuff like。

![](img/a11a028d71b34f17dcaea3ade8516f08_86.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_87.png)

H1 is hot uppercase。 This paragraph tag is not terminated。 This U tag is uppercase。

 This L is not terminated。 I don't have double quotes here。

 So there's a series of mistakes that I've made in this H， but it looks pretty good。

 and you'll notice in the document object model， it's fixed all that。 each one is lowercase。

 The P tag is finished。 There are double quotes， meaning the document object model is not just your HTML source code。



![](img/a11a028d71b34f17dcaea3ade8516f08_89.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_90.png)

It's like the sensible parsed pretty version of the HTMLm source code， you know。

 and so you know this UL tag， these L tags are now done， the UL's lowercase， everything's lowercase。

 so it's like I'll take care of your mess， I'll patch up and fix your HTML and then I'll display it for me and make sense of it。

The document object model is not the same。 It is sort of like a。Sweet， awesome， better version of it。



![](img/a11a028d71b34f17dcaea3ade8516f08_92.png)

But this is what changes that， so let me just show you something how I can change the document object model。

 let's see， let me see if we can change this text。

![](img/a11a028d71b34f17dcaea3ade8516f08_94.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_95.png)

I changed the document object model。

![](img/a11a028d71b34f17dcaea3ade8516f08_97.png)

That changes so I'm actually but that doesn't change the source code here。

 the source that it was retrieved to produce it， but I can change the document object model and later in the class we will write code that will actually change the document object model so we'll change this。



![](img/a11a028d71b34f17dcaea3ade8516f08_99.png)

We'll call this be going。To lists。Yet。

![](img/a11a028d71b34f17dcaea3ade8516f08_101.png)

Again。So I can change the document object。Do so you see it changed it。

 So when we change Do object model， what we see in the browser changes。

 but the source doesn't change Did I say that enough times so let's click on this。



![](img/a11a028d71b34f17dcaea3ade8516f08_103.png)

And go back to lists。Okay， so some HTML can be broken so badly so that it doesn't render at all。

Ohoops， that didn't work so well， will I'll do a view source on it。

🎼And then I will let you figure out why this doesn't work。

Why this doesn't show you take a look at the source。



![](img/a11a028d71b34f17dcaea3ade8516f08_105.png)

You figured it out。I hope this has been helpful to you， see you on the net。

