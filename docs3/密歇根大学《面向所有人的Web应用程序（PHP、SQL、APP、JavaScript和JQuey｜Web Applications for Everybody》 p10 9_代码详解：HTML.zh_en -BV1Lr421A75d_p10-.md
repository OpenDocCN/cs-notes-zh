# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p10 9_代码详解：HTML.zh_en -BV1Lr421A75d_p10-

Hello and welcome to Web applications for everybody in this。Screencast。

 we are going to play with some of the sample code and you can either download it and play with it on your own computer or you can look at it in your text editor or if you just want to browse it。

 you can browse it here and take a look at the version that I'm using it's really been intended that you look at this in the developer tools and so you can do things like say In element。

And so here we are， we're going this will also be a little more valuable even we're doing CSS。

 but you can see the document object model Now the interesting thing here is it shows something I'mma talking about is the difference between the document object model and the source code。

So this is the document object model it's kind of stylized if you look at the source code。

 you have to say view page source， and so the source code this is literally exactly what's in the file and if you go look at this file at a text editor you will see this。

And if you're looking at it here， it doesn't quite look exactly the same。

 And some things have been done a little bit differently。 You know。

 they kind of got this extra stuff。 And this is kind of after the browser has looked at it。

 And we start talking about jascript and changing some of this dynamically。

 you'll see this part is the document and object model， but the source never changes。

 The source is what was originally downloaded when the server sent this back to us。 So。

Let's take a basic look at this， I'll hide this unless I need it。

 I'll go back and forth between the source， so we have a basic document。

 HTML with a head tag and a body。And then a header。And of course， here's our header。

 we're using default dialing。And paragraphs are an important part of things I you know you don't you can squeeze this up as much as you want white space sort of doesn't matter right so this white space kind of doesn't matter here。

 you know the fact that this has got extra space， it doesn't much matter and so you can see an anchored strong tag that leads to a boldness。

Let's just go ahead and look at it here in the。Inspect。We' go down here we'll find like a strong tag。

 that's the bold， we got an emphasize tag and if you look a little farther you'll see there is the anchor tag which is the whole anchor tag is this whole tag from the a to the slash a list on HTMLM that's where we're going to go if we click on this text right here and so you can see。

Now this is a relative link and it turns it into an absolute link and that's because the browser knows where we're at。

 and so it sort of prefixes everything up to that to the relative link but that's nice because if we look in folders。

 we will see that these folders are all here here let me go find you that folder。

 it's pretty deep in my。Later， this will law make wonderful sense to you。

I do a lot of stuff with Web。Code。Htm。Okay， so here we have after all that。

 here we have the files right and so this is index。

htM and indexedhtM is right there and list htM and so if I click here， I'll go to list。

 HtM and that'll pull this other file up and so these guys are all in the same folder together it just means that I can use relative links to go moving between them。

Tag that's really becomes more important， especially as when we was talking about writing code inside a ti on showing people code is the pre tagag and so the pre tagag and you can just say inspect to hop right down to where the pre tagag is。

The pre tagag respects spaces， so all these spaces happen， the new lines happen。

 and it also shows it a monospace font you can change all these things once we get to CSS。

 but pretag when we're printing debug out from not in files like this， but when running code。

 sometimes it's good to print。Debugging out in。The pret so let's go to the next page and so here's a whole series of things we're going to play with。

嗯。This is a。Unnumbered list， this whole thing is an unnumbered list from top to bottom。

 So when I highlight this， you see the whole beginning to end of the list。

 then each item in the list has a start an end LI tag。Right， down， down， down。So here's this。

We should learn about tables and there's a HR， there's another relative link and so this is sort of my jumping off page to get to all of the all those other things。

 right， learn about tables。et cetera， et cetera。 so you can see these we probably use just to take a look at the source code of this page。

And so that's that's the source code that I typed in。 and you can see the LeI tags， the P tags。

 I'm putting P's inside of lis to get space。 let's see if I can sort of show you that。

 So if you look at this。And you look at the LI tag。

 the LI tag is that and the paragraph is what actually creates the vertical and horizontal space right。

 so that orange that you're seeing that's paragraph there's space that the paragraph tag has preset so that's how I do that putting paragraphs and Hres and so that's what this all looks like。

So let's take a look at special characters。And so this is an interesting thing because it's not really what came out because less than requires ampersand Lt。

 but it's kind of processing that。 So let's take a look at the source code to this one because that'll be more instructive。

 So Ampersand Lt， Ampersand G T， Ampersand Am。This is an ampersand in HTML and then just the letters AMP semione semicons not special。

 there are only really three totally special characters less than greater than in ampersand and you can put all kinds of fun stuff。

 clubs， hearts and diamonds。And so you got the clubs hearts and diamonds， some arrows。

 stuff like that。 What's nice is browsers just have these built in。

 although they're not necessarily the sexiest or coolest things。

 and I think what happens when I go back on this link is I go back to the list So that's just special characters and you'll notice that the default styling。

It says we've seen this one and this is how the web worked  a thousand0 years now。

 back in the 90s is you sort of， oh， it's kind of nice that it's turning purple and you'll notice that Google does this as well when you're doing Google searches。

 it actually lets the links change color after you visited them。

So let's take a look about links look at links。I'll give the source of this guy。Absolute link， A Hf。

Right。And then slash A this is the clickable text right between the beginning tag and the ending tag。

 the attributes are on the beginning tag。Another attribute that you can add and I do it all the time is target equals blank and that basically is the way we say open this up in a new tab so you'll do this pop up in a new tab and so that's where that one goes when it pops up and so you can decide whether or not you want this to go in the same page。

Back。Or in a new page， and then I got to close the tab to get back and now I'll go back。

Because that's just a relative link。To list at HM so I can go back and look at the next thing。

Let's take a look at how images are represented。So this is just a paragraph that has an image in it。

So it's a paragraph， but that there's the image source equals medium。t AG if you look in my folder。

If you look in my folder， you see the image right there， medium bo dopNG。

 you don't see the suffix because Mac is trying to hide it from me and so that's just you see this space here and here。

 the image doesn't have any space we could add some to the CSS later but the paragraph is what's adding that space。

Then we have just a regular old paragraph。'mNot supposed to use the center tag we'll get to the how to center stuff。

 so that's what that is saying right there and you can have an image that's right in the middle so you see where that image is。

I think of images if they're right in the middle of text， they're like a giant character。

 And so that's that's how that works。 And you can even sort of stick an image as the thing inside of a link。

 So here's the anchor tag。 it's that bit right there and then the anchor tag body is an image。

 And so if I click on that， it's going go back to list HM you'll notice these I'll go back to list HM。

 So I can work on the next thing。Right。Tables again。

 you're not supposed to use tables for laying out like blocks of text which we used to do。

 we used to do things like use tables to draw border around things， which we'll see in CSS。

 but now that's totally verboan and you're supposed to look at tables in a way that they're you know nice and pretty。

So let's do a view source here。So let's see there's our table our slash table and a table row now let's take a look at the dom。

So apparently I didn't put a tea body。 we' supposed to put a tea body in there， and I didn't do it。

 but this is the dom， the dom put it in。That's put in by the parsing。 And so clearly。

 I made a little mistake in my H T M L because I didn't put a tea body tag。

 And so that was added by the browser as it was parsing and reading through this。 like， oh。

 he forgot his tea body。 So it just like slapped one in for me。 And I think the mistake is。

 this is my header row。 And I think that should be like a tea head。 So there I go。 bad H T M L。

 It's the story of my life。And now I've got the rows and you'll notice that the Dom is kind of prettier。

 so sometimes I do this， the Dom is indented nicely， so this isn't really the source code。

 this is the data that represents this visual right it is the thing that you're seeing。

 but it is it read this from the file or from the server parsed it and produced the dock of an object model。

 I only say that like a million times。Okay， so back we go to the list， we're making pretty good time。

嗯。So heres some really bad HTML。I'm going to view source on it。 And again。

 you'll see sort of the difference between the document object model。

 When you're debugging these things， you will have to sometimes view source。

 Sometimes document object model will be the only way to debug it and sometimes view source。

 So this is the one that's got bad stuff like。H1 is hot uppercase。

 This paragraph tag is not terminated。 This U L tag is uppercase。 This L is not terminated。

 I don't have double quotes here。 So there's a series of mistakes that I've made in this H。

 but it looks pretty good。 And you'll notice in the document object model。 It's fixed all that。

 each one is lower case。 The P tag is finished。 There are double quotes。

 meaning the document object model is not just your H source code。

It's like the sensible parsed pretty version of the HTML source code， you know， and so you know。

 this UL tag， these L tags are now done， the UL's lowercase， everything's lowercase。

 so it's like I'll take care of your mask， I'll patch up and fix your HTML and then I'll display it for me and make sense of it。

The document object model is not the same。 It is sort of like a。Sweet， awesome， better version of it。

But this is what changes that。 So let me just show you something how I can change the document object model。

 let's see， let me see if we can change this text。I changed the document object model。

That changes so I'm actually but that doesn't change the source code here。

 the source that it was retrieved to produce it， but I can change the document object model and later in the class well write code that will actually change the document object model so we'll change this。

We'll call this be going。To lists。Yet。Again。So I can change the document object。

Do so you see it changed it So when we change Do and object model what we see in the browser changes。

 but the source doesn't change Did I say that enough times， so let's click on this。

And go back to lists。Okay， so some HTML can be broken so badly so that it doesn't render at all。Oops。

 that didn't work so well， I will I'll do a view source on it。

🎼And then I will let you figure out why this doesn't work。

 Why this doesn't show you take a look at the source。 You figured out。

 I hope this has been helpful to you。 See on the net。



![](img/4b52a1316479067705ec34feb5a3c926_1.png)

![](img/4b52a1316479067705ec34feb5a3c926_2.png)