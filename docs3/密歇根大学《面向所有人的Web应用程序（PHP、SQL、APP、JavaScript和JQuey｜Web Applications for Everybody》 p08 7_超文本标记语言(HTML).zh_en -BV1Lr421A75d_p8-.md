# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p08 7_超文本标记语言(HTML).zh_en -BV1Lr421A75d_p8-

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_0.png)

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_1.png)

Welcome to our lecture on HTML my goal in this lecture is not to make you the world's greatest web designer or a front end expert。

 I just want to teach you enough HTML so that you can sort of do the rest of this class because this rest of this class is like here's some HTML and now we're going to come up with cool ways to make more HTML and that really is the theme of this class。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_3.png)

I never tire of this particular picture， but you might get tired because I always want to place everything we're doing in the right context。

 right， And because there's really three major pieces of software and two network connections that sort of govern everything we do in Web applications。

 This is you out here。Okay， so you're sitting there， you're sitting in a browser， you got a keyboard。

 you got a mouse， you got whatever right， and you have a piece of software running on your laptop。

 So this is your laptop。 Then that talks to over the network to a web server and we're gonna run PhP and all kinds of things in there。

 the Apache web server。 This is like Chrome。This is Apache， and then we have MySQL。

 which is often on a third piece of hardware and a network connection。

 even though when you're doing your own development for this class。

 these two computers will be the same， but they still talk to each other over a virtual loop back network。

And so here we are， the document object model is the thing that effectively is the view and HTML。

Is when you make a request and somehow runs in the server。

 maybe reads some data in a database and it comes back， and then the request comes back HTML。

Is the format of that request and then it gets parsed by your browser。

 it reads right through those things， looking for less than and greater thans and all those things that lead to sort of a set of pixels on the screen in the little image that you see and so this is HTML and so HTML HP is the protocol we use to retrieve these documents and HTML is the format of those documents when they're retrieved and so HTML is very much a browser thing。

 it tells us how we create， look and feel in the browser。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_5.png)

And the ID of HTML， it's a way to mark up text。If you're old enough。

 you remember things like word processors with reveal codes now way that really reveals how old you really are but the notion of saying this is bold and this is italics and this is normal text that's just something that you need to do in any kind of word processing and so one thing that's cool about HTML is they came up with a format that you can actually look at and so if you dig deep into Microsoft word you might find in a doc file it's some weird thing you can't look at but HTML it's internal format。

 it's an internal way of representing the markup that talks about the look and feel of a document except you can look at it and I as a programmer。

 I just love to look at stuff because then I can write a Python program to generate HTML or another program generate jascript because you just know what it is because it's really just text but then we have text that has meaning and so the tagging is meaning so less than P greater than P says start a paragraph less than strong grade instead start bold。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_7.png)

slash strong says stopt Vol。 so again we tag them and less than in greater than and slash our special characters Now we have ways to represent those and we'll talk about that in a second。

 but the idea is is this is a user viewable markup format There are many markup formats where documents are a markup format。

 although there's doc X， which is XML， so it's easier for for you to see what's in XML。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_9.png)

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_10.png)

And so the web started out in the early 1990s， it became popular in 1994 and so we're over 20 years past this。

 and it kind of helps to understand where we're at and understand why HTML is the way it is is it started out in a really small effort and so a group of two people。

 Timbererss Lee and Robert Kayu invented sort of the first round of the web in the 1990s and they weren't a gigantic company。

 they were just two people and so they had to build simple things。

 and so we are in their debt because they were engineers that engineered something easy and so now we get this richness of what we can do with the web。

 but at the core level it's kind of easy and beautiful。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_12.png)

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_13.png)

Now， it's important if you watch that video of Robert Kayu that the web。

 when it was invented in 1990， was not exactly the web that we have today。

 The web was really very much for serious documentations， Ser kinds of things。

 It wasn't really intended to be sort of fun and frivolous and entertaining and to watch movies and to。

Consume information that all came later。And so HTML was a sort of just it was a workhorse。

 it was designed to get some stuff done to show pictures of design documents and you know images opened in a new window and it seemed like it made a ton of sense to do that and I have a video of what it was like actually to surf the web using one of the early mosaic a piece of software circa in 1994 that I。

Regurgitated， I found some old source code， and I made it work on a Mac。

 and I'll show you a video of all that。 But even sort of from 1994，95。

 then the web evolved a great deal after that。

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_15.png)

People were just amazed that there was a place on the screen that you could click。

And you would go somewhere else。That was enough。 We were excited。

 And so you see all these blue links that are underlined that really are saying click me， click me。

 click me， click， please。I am a page full of useful information。 Please click me。 Now。

 this is functional。 And I recall in 1996， when I would see this， I'm like， oh， so beautiful。

 This is the future。 Well， this sort of was the future in 96。 But then what happens is， is that。😊。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_17.png)

As people that are not like me use the web。It had to be prettier and so it's evolved a lot and the good news is is sitting here in 2017 or later so much good stuff is done that we're not even going to teach you the bad stuff I'll show you a couple of bad things sort of these old thing。

 but we're at the point now where web pagess are powerful engines of commerce and money and they do things in Yahoo where they count the number of pixels in this little white bar and they will add one and subtract one and decide if people like the page better based on the number of pixels and all they're doing is they're figuring out what is pleasing to us and they're optimizing to make very pleasing user interfaces and compare and contrast that obsession with beauty with hey。

 the click works， that's amazing know and CSS is a big part of this which we'll talk about in an upcoming lecture。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_19.png)

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_20.png)

And so in the good old days HTML was really tolerant， you know， it just didn't matter。

 you could have tags that didn't finish， you could have all kinds of things。

 you could have uppercase tags， you could have attributes that didn't have double quotes on it。

 you didn't have to like put a slash LI at the end of this thing， all these uppercase tags。

In the old days they just wanted the browsers wanted to be friendly。

 they didn't want to show broken right you know they didn't want to like oh bad page。

 don't look at said page right and so the browsers were really tolerant。

 they let us a lot of HTML built by hand and you know people were just make would make mistakes and the browsers wanted to fix those mistakes and show us you know relatively simple code。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_22.png)

Now， in 1994，9596， the idea it was very， very clear that this HTML in the web was an engine of commerce and productivity。

 et cea， et cetera， etc ceter， and so it became very important for us to build standards around that。

 And so Tim Bernners Lee， one of the other initial creators of the World Web moved from CN to MIT。

 Massachusetts Institute of Technology。 CEern of course， is in Switzerland， it's a physics lab。

 It's not a computer science place。 MIT is more of a technical computer science place。

 And so the home of the standards for the World W Web is an organization called the Worldwide Web consortium or the W3C that comes out of MIT。

 And so HTML moved from a thing that a couple of engineers put together at CEN to solve a problem they had to solve to something that became the foundational technology for the future of industry。

 So HTML started getting revised， more professional， more clear。 So we got HTML 1。 we have HTML。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_24.png)

![](img/d2124ab3ba94b2998e9c58d7cda1cf05_25.png)

2，3，4， three didn't last very long， four lasted a long time and now HTMLt5 is what we're using today。

 and so this has been something that the World Web consortium has been guiding and the whole idea and if you。

 if you look at my internet history， technology and security class， you will see that this。

Whole thing was actually fraught with peril right in the World Web consortium was the good guys and bad guys and Microsoft was good guys in that particular line。

 but I'm not gonna to this is not history class。 it's a little bit of a history class。

 I can't help myself。 And so but the World Web consortium was founded and underpins all the things that we do on the web today and really enables all the beauty that we see on the web and yet it still simple enough to understand part of the problem was in the interim years like 2000 through 2008。

 it was just kind of a mess and then finally it got cleaned up about four or five years ago。

 So there's just some rules now。 And so the World Web consortium said this is what HTML should look like。

 and things like tags have to be lowercase。 all tags have to start and stop if you have an attribute。

 It's got to double quote around it。 and browsers will still tolerate all kinds of mistakes。

 here's a paragraph tag beginning paragraph and paragraph list tag list。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_27.png)

etc so now because of the sort of maturation maturing of this whole thing。

 we now have rules that we follow and that in the old days we used to do sort of all kinds of irresponsible things when it came to the web。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_29.png)

So up next， we're going to talk a little bit about how HTML documents are put together in a little more detail on HTML。



![](img/d2124ab3ba94b2998e9c58d7cda1cf05_31.png)