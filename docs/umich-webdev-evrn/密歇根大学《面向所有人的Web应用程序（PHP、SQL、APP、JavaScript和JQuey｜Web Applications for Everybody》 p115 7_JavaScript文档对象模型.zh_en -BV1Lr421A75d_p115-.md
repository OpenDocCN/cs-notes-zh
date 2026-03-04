# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p115 7_JavaScript文档对象模型.zh_en -BV1Lr421A75d_p115-

![](img/55468c3a5087f345acdc23ad4864c413_0.png)

![](img/55468c3a5087f345acdc23ad4864c413_1.png)

Now we're going to talk a little bit about how we manipulate the document object model from JavaScript。

And so here we are in our happy little request response cycle， and so the document object model。

 of course， is how we out here in the real world we view web pages， right that's what we're seeing。

So what we're going to see now is and we're gonna have a request response cycle that's going to write jascript in it。

 but that's no big deal。 You'll notice that all these files I'm playing with now are HM files。

 So there're static files they're not even running on the server at all。

 but inside them they have some ja。 and now we're going to look at how jascript can both look at things from the document object model。

 Look them up and pull them out and then put stuff back in document object model。

 we've already saw how you can use document right to append to the document object model and we see these things。

 And so this is the core essence of interactivity that does not require a request response cycles when we can manipulate the document object model interactively in jascript now in the next few lectures。

 we're going to come up with all kinds of ways or jascript is going to talk to the server and then update the document object model but for now we're really just going to focus on this bit of code right here where ja is manipulating the document object model and not worry about the other cool things that jascript can do。



![](img/55468c3a5087f345acdc23ad4864c413_3.png)

Okay， so the document object model has been around since the beginning of time。😡。

And when jascript was created， document logic model existed。 The problem is， in 1995。

 all these browsers kind evolved independently。 They all had sort of an internal data structure for how they would represent H T M once they parsed it。

 but they weren't the same。And so there's because the inconsistency is the document object model and because they knew that they could never get JavaScript out if they said every document object model has to be the same。

They didn't force the document object model shape the structure of what's a child of what inside the document object model。

 They never force that to be the same。 Okay， And so there's other ways that we have to go look things up。

 You can always look things up， but there's not， It's not as portable。So like I said。

 not all browsers represent their page the exact same way and in the old days。



![](img/55468c3a5087f345acdc23ad4864c413_5.png)

We would write jascript code and then we get at bug that said on i。e 7。3。1， you just blew up。

 but everything else works and Firefox works。 and this works。 and that works。

 That's less of a problem these days， but we will see。

 And so we would end up with bugs that are just like this thing works on everything but Internet Explorer blows up and no options display。

 And this would be an example where your writing code as a developer and you test it and test it on Firefox。

 But then you put it in production in someone used Internet Explorer。 that happens all the time。

 And it's very， very， very frustrating。But。It's still important to be able to do basic simple things to the document object model。



![](img/55468c3a5087f345acdc23ad4864c413_7.png)

And so what they did is because the shapes weren't the same。 And so what I mean by shape is。

 you know， this comes here， the document and the forms are down here and the iframes are over here and what comes underneath these things。

 And there was a hierarchy that you could go like document dot X dot Y do Z sub4。

 and that might be the fourth form or something， right。But the sequence of these things is different。

 So the shapes of an I。e， Internet Explorer or Chrome or whatever have different document object models because that was sort of treated as just a thing that the browser was allowed to do。

 The developers of the browser were allowed to architect their own document object model based on what they thought was the coolest thing to do。

 And so the idea was， is that。In the early days of JavaScript。

 they said we are not going to standardize the document model。

 but what we want to do is we want to be able to find something deep in the document object model。

Independent of。We don't know what the shape is， but if we can mark this little one with I D equals bo。

Then I want to be able to grab this little thing， not knowing where it fits in the tree。

 but if we put an ID tag on it， and that is a function that was built into all the document object models called get element by ID。

 So instead of going starting a document and working your way down， you just say， look。

 I don't care you go find the one that has ID equals Bob。And so that's called get element by ID。

So what we do is we use this ID tag and you know we've seen this in CSS。

 we've used this in CSS as well， but we also can use this in JavaScript as a way to distinguish a particular tag Now there's the class equals and the ID equals you can only have one tag an entire document that has the same ID so ID equals person there can only be one tag that has an ID of person。

So we are marking somehow this text chuck。Okay， and saying so this by the span tag is just a tag that does nothing。

 all we're doing here by putting an ID on is giving us a handle for that text。

And so now what we can do is we can come into our JavaScript and we can say document。

ge elementement by ID person。And that says go through your whole document object model wherever that thing's at。

And find me this tag。So this bit right here。That bit right there is what you get。

 You get the tag span I D equals is not the tax。 It's not chuck。

 And if you want to go down and you want to go deeper to get just this bit。

Then you say dot interhtml。 So that pulls this stuff out。

 And so that's where it says string equals chuck down here。 So it's actually pulled the actual text。

 You go find the tag and then dive into the tag。 And sometimes the tag itself has children in it。

 And so sometimes it's actually quite complicated。 But in this case。

 I just had a span tag with some inter Htl And away you go， okay。And then。😊。

It doesn't have to be that we just this is basically looking something up from the document object model。

And then I can console log it at console。 Dur that just shows us this and it's really nice because then you can expand this and you can see all the little details that are in that tag and that's a good way of debugging and then writing code and then I can actually change it so I go document objectmal El and ID inter HTML so this actually is a handle to this Chuck text。

 whatever is between those span tags and then actually rewrites the document object model and puts Joseph in there instead。

 So if you were to see that you'd see Joseph。On the screen。



![](img/55468c3a5087f345acdc23ad4864c413_9.png)

And so that's what you see afterwards， right？And if you can expand that document dot du。

 this is what's quite nice about this is the console do Dur。

 I think consolet log is roughly the same thing， if you like。

 it gives you this and you can look down through things and scan。

 and that's how you can find things like you know inter HTMLtl or whatever because you can see all these things and child nodes。

 for example， is if our span tag， which is in the document object model somewhere。

 This is our span tag。That's our span tag， it can have child nodes that go within it so thatd be span within something。



![](img/55468c3a5087f345acdc23ad4864c413_11.png)

And so here's a little bit of code that is jascript that's running an on clickick where and again。

 when you start doing jascript in the browser， you want to mess with the dom。

 you tend to add Is on tags to give yourself handles to various pieces so you can change them delete them。

 put new stuff in them。 And so here's this span on this string stuff this string stuff right here。

 I've got a handle I stuff。 So I can grab this tag document I This is an on clickick for this back button。

 this back is an onclick that runs this jascript as soon as I click on back It's going run this code and it's go grab that tag and then take the in HTMLtl of tag and stick back in so that basically puts。

B A K。 So if I press back。This dom， without going to the server， this dom just changes to back。

 And if I click forth。Click this fourth， which is this fourth。

 Then that goes and grabs this same thing。 And then the inter HTMLtml is changed to fourth。

 So that wipes that out fourth。And it looks like that。 so you can go back forth， back forth。

 back forth， back forth， and this stuff is just changing。

 and this is just really simple basic browser interactivity。

Here's a little bit of code that's a little more complex that's manipulating the document object model。

 And so what we're going to do is we're going to have this little more tag， more tag。

 and we're going to have onclick method the Hf means that's a way that we say don't load anything it's not really a link to anywhere。

 it's an interactive thing that's going to make something happen inside this document。

 And so whenever we click on that， we're going to call the add function in JavaScript and then return false to avoid going to some page。

 right。And so now what we're going to do is this is all just HTML at this point， HTML， HTML HTML。

 and we're going to make a UL tag。And we're going to put an LI tag in there first item。

 so if you first look at this page， you'll see that and nothing else。

And then we're going to have some JavaScript。So in this JavaScript。

 we're going to set a very global variable called counter to be 1。

We're going to do a console log just for ys， and then we'll create this function called add and this function called add is going to be run every time we click on that。

 So it's going to click， run add， return false， click， run add， return false。

 So every time we click on this。 what it's going to do is it's going to do a document。

 create element。 So what that does is it creates an L tag。Slash l。Slash a lie that has nothing in it。

 but it's not connected anywhere to the document object model。We can give it a class。

 x is this thing， we can put a class equals on it。Okay， we put a class equals on it。

 That's what this does。 and we can set the inter HTML to be the counter。

And then whatever this variable is， counter and then add one to it。 Well。

 then what we're going to do is we're going to graft it in。 So we're going to grab。This L I tag。

 a U L tag， which is this tag right here。 And we're going to add a new child。

 So the way think about this is the U L。Is the parent and the L I is the child。 Now， we're doing it。

 adding another child to it。 another L I tag。 So this was the L I tag we kind of made out here。

 And then we connect that L I tag to this U L tag。And then then we add one to the counter。

 So if counter equals one。 And then we would do this again。 Every time we click this。

 it's going to run this over and over again。 So a new L tag gets added every time we do this。

 And there's no request response cycles going on。 right， We're just， we're just we have the dom。

 we have jascript and it's just changing the dom。 And as soon as the dom changes， you see this。

 If there was stuff down here， it will get reformated and move down。 And so that change the dom。

 it reformats， it rejustifies。 it does all the kinds of things that it's going to do。

And so this is an example of generating dynamically。Some H that we can see by manipulating the dom。

And doing various things。Now。That's how we did it in the old days。 That's 1995 to 2005，2006。

 for 10 years， we wrote code like that。And the problem was is it wasn't portable and it was kind of。

Just long lot of little details。 that you can do it。 but it was so clunky。

 And there's so many things。 And as we wanted to build cool interactivity。

 it got the amount of code you'd had to write just got bigger and bigger and bigger。

 So a series of libraries in the mid 200s，2004，2005。

2006 came out that tried to make jascript in the Dom a more functional way to write code and a number of them came out motos。

 prototype。But the one that everyone one loves now over 10 years later is called JQu。

 And so what JQury did is it solved two problems。 It made messing with the dom really easy and portable。

 So Jquery knows all the browsers and all the quirks of all the browsers。 And you'd say， and Jquery。

 do this。 go find this tag and do this to that tag。

 And if there was something you had to do for a particular version of a browser。

 JQury would worry about that。And so JQury solve the portability problems。 The dom。

 they solve the dom differences， the underlying functions， things like how wide is the window。

 it used to be you'd have an if statement and this much code to figure how wide the window was。

 whereas in jquery go like how wide is the window。 And it has the if statement in it。

 So it's really amazing。 And we really at this point。

 it's rather rare to do anything other than the simplest kind of manipulation in the dom without using Jquery。

 So many people just assume that jquery'ries always was there。 But it wasn't always there。

 It wasn't there for the first 10 years。 And it was so painful in effort 1 years that things like JQury had to be built。

 And so when we start talking about Jquery。 Well， I'm not going to do much more in dom manipulation and until we start doing that with Jquery。

So this is a。Quick run through jascript， how we kind of write code。

 what the basic syntax of the language is all the way up through manipulating the document object model using the kind of early version。

 the first 10 years of ja， and you still do that Sometimes you want to keep your page really small and you only want to do a tiny little thing so you kind of revert back to get element by ID and that kind of activity。

 especially as old browsers go away， the portability issues are less and less of a problem。

 but as we really start playing with the document object model will play using libraries like jquery。



![](img/55468c3a5087f345acdc23ad4864c413_13.png)