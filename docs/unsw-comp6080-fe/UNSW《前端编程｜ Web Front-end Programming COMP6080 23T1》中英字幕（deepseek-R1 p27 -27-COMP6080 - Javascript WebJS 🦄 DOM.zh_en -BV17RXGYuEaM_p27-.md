# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p27 -27-COMP6080 - Javascript WebJS 🦄 DOM.zh_en -BV17RXGYuEaM_p27-

Hey everyone， it's Anna here and in this lecture we're going to talk about the Dom。😊。



![](img/809da449ae600ad588d1294a2445252d_1.png)

So we're going to be covering what the dom is， we're going to look at what the dom allows us to do in JavaScript and then we're going to do some live coding examples。



![](img/809da449ae600ad588d1294a2445252d_3.png)

First let's have a little bit of a recap about what makes up our web pages so almost all web pages consist of HTML CSS and JavaScript H is used for defining the markup and structure of the page CSS is used for applying styles to elements in the document and finally JavaScript can be used to dynamically modify content on the page。



![](img/809da449ae600ad588d1294a2445252d_5.png)

Now， what exactly is the dome？The Dom， which stands for document object model is an interface that allows JavaScriptscript to interact with HTML through the browser so you can think of the Dom as a representation of your web page the browser takes into HTML which you write passes it and then turns it into the Dom。



![](img/809da449ae600ad588d1294a2445252d_7.png)

So taking a look back at this diagram， the dom is like an interface which allows JavaScript to access and update the content of your web page。

 such as the content， the structure and the styling。😊。



![](img/809da449ae600ad588d1294a2445252d_9.png)

Here we've got a basic example of some basic HTML and the corresponding dom。

So one of the features of the dom is that it has a treela structure。

In HTML you probably know that HTML tags are structured like a tree where tags can have children。

 so if you take a quick look at this HTML snippet we have the header tag which has a child title and we have the body tag which has a text child and a bold tag child。

😊，So the same thing goes for the dom just by stepping through this dom tree。

 we can see that the fruit of the Dom tree is called the document。

The document is a predefined object that's available to you in client side JavaScript。

 which represents the root of the entire dom。Then you can see the HTML tag。

 which is the outermost tag in our HTML is the first child node of the dormittry。😊。

And just jumping down to the body tag， you can see that the body tag has two children。

 some text and a bold tag， and this is represented as two children nodes in the dormitory。😊。



![](img/809da449ae600ad588d1294a2445252d_11.png)

Now let's take a look at a few dumb data types。

![](img/809da449ae600ad588d1294a2445252d_13.png)

On the previous slide I mentioned the document object， so like I said。

 this document object is the root of the entire Do trait。😊。

So document is the type of this document object， this first type here。Next one here is element。

 so element is the type of all the nodes in the dong treee。

 so this interface is what we can use to manipulate elements on the page and get info about them。😊。

Finally we have node list， which is an array like structure of elements。

 which is returned by methods like queryery selector All， which we'll look at in a moment。😊。

Now I want us to look at a little bit deeper at this middle type here， the element type。😊。



![](img/809da449ae600ad588d1294a2445252d_15.png)

So element is the type of the all the elements in the dom。

 so suppose I have a div on my page in the Dom， this is an element。😊。

But JavaScript gives us more specific types based on what HTML element we have。For example。

 if I have a diviv， this will be a HTML div element。

 if I have an input tag this will be a HTML input element。😊。

A list of six of these specific types here， but there's dozens and dozens of element types。

 and basically element is the base type of all of the types of objects in the Do and types like HTML element are subtypes。

😊，So they have everything the element has plus some extra things based on what type of element it is。

 and we'll look at some more specific examples in a second。😊。



![](img/809da449ae600ad588d1294a2445252d_17.png)

So what does the element interface actually give us？



![](img/809da449ae600ad588d1294a2445252d_19.png)

Their element interface has a bunch of attributes and methods。

 and we can use these to write to the dom and read the dom。😊。

So we can read things such as the size of the element， its position。

 its colour or the text in that element， and we can also write things so we can change to the styling and even add and remove elements。

😊，So I'll give some examples of those attributes， so every HTML element has some attributes such as style。

 the styles like the way of tending the styling and overriding the CSS。😊，Offset left and offset top。

 which is like the position and client width or client height to get the size。😊，And then。

 like I mentioned。Different HTML tab types have different types in the dom which add extra attributes and methods。

 so an HTML image element has all the things that HTML element has it also has things like the alt attribute which stores the images halt in a text and a source attribute for the source of the image and then HTML input element has the focus method which focuses the text box So button and select which selects all the text into the input element and focuses it。

😊。

![](img/809da449ae600ad588d1294a2445252d_21.png)

I want to take a moment to quickly look at the HTML element interface on MDM。😊。



![](img/809da449ae600ad588d1294a2445252d_23.png)

So here's the MCZN page all about HTML element so here we can see it's got a bunch of properties it inherits everything from element and also adds a lot of other properties for example we've got dragable which says whether or not that element is draggable hidden attribute。

😊，We've also got offset height， offset left， offset top， offset width。

 which tell you about like size and positioning。In the title。

And then we've got a bunch of event handlers， which we'll look at in another lecture。

And finally we have a few methods like blur， which removes focus from the element， click。

 which sends a click event and focus， which makes the element in focus。😊。

And if you take a look here on the side panel， we've got all the children types of HTML element。

 which represent all the different HTML tags。So plenty of them over here。

So I just take a look at HTMLML image element。Yeah。

 so here you can say it itherits all the properties from its parent HTML element。

 but it's also got other attributes like the old attribute。😊，And yeah。

 I always find MDN really useful to refer back to to find information about different types。😊。



![](img/809da449ae600ad588d1294a2445252d_25.png)

Okay， so we've seen how when we have a dumb element in JavaScript。

 we can read data from that element and manipulate it。

 but how do we actually get access to these do elements？😊。

So there's a few way of retrieving do elements and on this slide I've listed a few of them essentially when you know the ID the class or the tag type of an element。

 you can use these to retrieve them from the do so first up we have here document。

 get element by ID which uses the ID attribute of an element。😊，And this returns a single node。

 so as you probably know IDs in HTML are unique you can only have one element with a7 ID and get element by ID will get that element for you。

😊，Next up we have document。ge elements by tag name。

 so this will accept a tag name such as div or image and itll return all the elements in the document which have that tag name。

And similar to document doc get elements by class name， so unlike IDs class names is not unique。

 so it does the same thing as get element by ID but returns all of the matches。😊。

The last one we have here is document。queery selector。

 so this returns the first element that matches the provided selector query string and I'll show you some examples of how to use query strings in a moment。

😊。

![](img/809da449ae600ad588d1294a2445252d_27.png)

Alright， so I've made up a little sample HTML page here taking a look at the elements tab in the browser console I can see that we've got a head tagag。

 a few images and two divs， so let's have a look at how we can retrieve these elements from the do。😊。

So first I want to try get elementement by ID and you'll see this image tag here has ID Puppy。

So if I type document。Okay。Y ID and plus in the ID copypy。

You'll see that it's returned this dominate。Nelace tried to get elements by class name。

 so I have two boxes here and both of them have the class name box， so let's try and type that。

And as you can see， it's returned a HTML collection with two elements with both of my boxes。

And let's try I get elements by tagging， so I have three elements with the image taging。😊。

Let give me three。Images now I'm going to show query selector。

Every selector accepts a query based on what I'm querying by I have to use different symbols so if I'm querying by an ID just like in CSS I use a hash and then type the name of the ID which is Py。

😊，And it returns the first match， in this case there's only one match。Now。

 if I want a query selected by class name， I use a dot， so I'll do dot box。

And it's only returning the first match， if I want all the matches， then I use document。

query select all。 so that's how you read elements from the dom。



![](img/809da449ae600ad588d1294a2445252d_29.png)

Cool， so we just saw how to read the Dom now let's take a look at how to write to the dom。

So the first method we have here is document dot create element this is used to create an element as a variable so it doesn't insert it into the do。

 it just creates an element and it accepts the tag name so I can create and div by saying document dot create element div。

😊，We can also create a text node in just the same way， so document do createate a text node。

 pass in the string。😊，We also have methods for adding these nodes into the do。

 so if you have an element， you can do element。 aend childild。😊。

And that will add the new element as a child。嗯。We're also able to set attributes， for example。

 say I have a button， I can easily in JavaScript set an attributes such as adding the disabled attribute or adding another attribute such as an ID。

😊。

![](img/809da449ae600ad588d1294a2445252d_31.png)

As well as adding new elements to the Dom and modifying their attributes。

 they can also change the style of an element。😊，Kind of like dynamically changing the CSS styling。

 taking an element from red to blue or adding a border or setting a transform。

So how we do this is elements have a style property which we can modify in JavaScript。

And this style property corresponds to the style attribute of the HTML element， so if you do element。

t style followed by the name of any CSS property， you can access or modify that style。😊。

So here we have an example， if I set element。tyle。 left。

 I'm setting the left style property to 50 pixels。😊。

The next two lines we can see that I'm trying to increment the left value by five pixels。

 so I'm retrieving the existing element。 styleyle。 left value using pass int。

 I'm adding five and I'm appending the pixel symbol and then I'm setting that new value to element。

 styleyle。 left。😊，In the final example here， I'm changing the background colour。

 so element dot style dot background color equals red。

 and I put a little note here to note that this is in Camll case。

 so the styles in inline styles and CSS are usually hyp separated but in JavaScriptscript they're all converted to Caml case。

😊，Now note that element。star。 leftft will only be present on an element if that left property was set via inline styles or by scripting。

Taking a quick look at the previous slide。Trying to retrieve alignmentstar。

le won't work if I've just set the left value in the CSS。So to get the actual style of an element。

 if it wasn't already set in line styles or by scripting， we can use window。compd style。😊。

Taking a look at this example， I got window dot computer style and pass in an element and then I can use the compute style object do get property value to retrieve the value of any。

😊，Of the style properties of that element。Here， I'm re the background color。

Another way of modifying the style is to change the class names which exist on the element which can be done using the class list property。

 so here you see we've got an element， I can add a class， remove a class。

 toggle a class which toggles it or check if a class exists on an element。



![](img/809da449ae600ad588d1294a2445252d_33.png)

So now let's have a look at riding to the dome。

![](img/809da449ae600ad588d1294a2445252d_35.png)

Alright so I've got the same HTML page here as before。

 but now we're going to try writing to the do so first thing I want to do is I want to make a new element。

😊，I'm going to make an image element。I've made an image it's not in the Dom yet。

 but it also doesn't have a source yet， so let's add a source to this image。

So we've got that image and now we want to add it to the dom， so I'm going to do document。

Body to get hold body tag and append a new child。And pass in on new node。Awesome。

 so the image is now showing up， obviously it's looking really big so I'm going to change the width attribute。

😊，Okay， cool that looks much better。Now suppose I once you add some styling。

 if I take a look here in my style sheet in my elements tab you can see in my style sheet I've got this class name decoratedative image which applies some styling。

 though I'm going to add this class name to my new element so Im want to add decorated image of new image。

classlist。 add and class some decorated image。😊，OkayA。

 now you can see those styles are applied if I take a look at this element。😊。

It's got decorated image cluster list and it's got these new styles applied。

Suppose I want to change it so that I have a slightly different order。

 I can do that using the style attribute resource。I'll change mut image。 style order。

And there you can see it's got a new border。I can't actually see the pink co this photo。

 there you go。Cool， so that's how you do writing new elements to the dom。



![](img/809da449ae600ad588d1294a2445252d_37.png)

One more cool thing which we're able to change about the view in JavaScript is scrolling the page to a certain position manually。

 so in JavaScript the window object gives us scroll X and scroll Y which tells us the current scroll position of the page and then as well as that it gives us a scroll to method so this accepts a top position a left position and a behavior which is like smooth or no scroll behavior which。

😊，Lets us through the JavaScript scroll to a position on the page。



![](img/809da449ae600ad588d1294a2445252d_39.png)

So let's have a look at an example of how we can use this to scroll to an element。



![](img/809da449ae600ad588d1294a2445252d_41.png)

Alright so what I have here is a H Tl page as you can see it's got this button which has clicked as well it's got a red square and it's got a blue square so I've just added these two divs and I've added some styling to make them colored and to make the second square positioned。

😊，2000 pixels from the top of the page and give us a scbar。

So what we want to do is we want to make it such that if I click this button。

 it'll scroll us down to this blue square。😊，Right now clicking this button doesn't do anything because I haven't added an eventless button。

 so let's switch over to the JavaScriptscript and let's try and write this code to scroll us to the blue square。

😊，First what I'm going to do is I'm going to use query selector to get the。Bice Square。

So this second square has the class name second so I'm just using query selector to get back now I want to get the button so the button has ID VTN so I'm just getting to use that。

Co now I've got both my elements now I want to add an event listener to the button such that when I click it it will do something we're going to have another lecture on events where I go into detail about how to add event listeners but I'm just going to quickly add a little function that will run when I click the button。

So in this event listener， what I want to do is I want to get the position of this blue square and then I want to scroll to it。

😊，So added this call here to a function called Get bound in client rec and to show you what it does。

 let me just quickly console Lo what it's returning。😊。



![](img/809da449ae600ad588d1294a2445252d_43.png)

So get bounding client rec returns a Dom rec object which basically gives you the size and the position of this element。

 so I have the top value which is 2000， which means this blue square is 2000 pixels from the top of my current client window so I'm going to use this and the scroll2 method to scroll to the blue square。

So scroll two except a top position。And I'm going to say record dot top。



![](img/809da449ae600ad588d1294a2445252d_45.png)

Let's try and run that。Cool， you can see when I click the button。

And that scrolls me so that the blue square is that。

One more cool thing about the scroll2 method is that I can specify behavior as a scrolling behavior and it has auto or smooth。

😊，When I set it to smooth。I get a nice animation where it actually animates me scrolling down to the blue square。



![](img/809da449ae600ad588d1294a2445252d_47.png)

All right， so that's it for today's lecture on the Dom， so thanks so much for listening。😊。



![](img/809da449ae600ad588d1294a2445252d_49.png)