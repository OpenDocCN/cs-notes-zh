# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p06 P6 Lecture 5, JS 2 - Spring 2023 -BV1ddBTBrEo2_p6-

嗯。

![](img/6479d6852f01fc5d759e842fca9899b9_1.png)

有个那什会。一9。你该听气睇开十上交。或者里边。我呢。不好意思。Ohあ。I。告。没。我。Okay， not just。I。好的呢。とい。嗯。嗯。Yeah。嗯。不可以不知道。我同灯调。Okay。

 so it's Bley time so i'm going to start the lecture now this is lecture five JavaScript dom top five me。

So first。What is the do like what is the document object model it is a data structure that the browser will create when loading a page so if you've taken 6 to1B or anything it's literally just a data structure and it kind of has the structure of a tree so it has elements and nodes and it's made like each HTML tag is its own node and the content is like the child node of each element。

So for example， this is kind of like the structure of an HTML page and the dawn so you see the HTML like first tab thing is the root node and then the head and the body or like child node of that and then like each node there is like child nodes of each other。

And there's not like one set way to like。Define or like show this。

 but it's just the general structure is like a tree kind of data structure。

And we can traverse this just like a tree data structure。

 we go down the dom and kind of like in a parent child relationship。

And the main reason why we want to learn about the dog is。

To use jascript to modify it so basically we can use the dom to change elements in their cs and we do this by selecting an element via jascript and then we can change the style through that and。

Through this， we can add interactions like。Setting what happens when we check a checkbox or hover over something。

 we could also resize and transitions and a bunch of other stuff that we'll talk about later。

And before we get into methods involving how to change the doM and stuff。

 we need to know what the document actually is so the document is a globally available variable so it's like just built in the browser and it is used to modify the DOM and interact with the HTML and CSS。

There's a lot of methods that you can use for the DoM and if you just like Google like document like jobscript Dom documentation。

 there's a bunch of methods that you can see to how to modify and like select things。

And it's actually， we won't get into this too much in the course。

 but it's actually a property if the window object which represents a tab in the browser and that window object has like a bunch of information about like the size of the browser and stuff like that。

 but what we're concerned about is the dom because that's what we're actually going to be editing。

So now we can get into the methods that we use to actually select things and modify things。

So the first one we're going to talk about is query selector so this returns the first element that matches the CSS specified so inside of those parentheses in the query selector you put a valid CSS specifier so that would be like a class name or an ID or even like a tag like div or P and it allows us to modify the elements is CSS the element that we select and its properties so for example。

In this red square example this we have this zoo that has a class name red square and you see with CSS we're changing the background color to crimson but then using JavaScript we can actually change the background color using JavaScript and we do this by using document on query select so you see we're selecting the first element that has the class name red square and just like a little note about query selector because you can select like a class name or an ID or like a tag or like from like any CSS like property we need to tell the code like which one we're selecting so if we're selecting a class name we have to put the period in front of the class name if we're selecting an ID it'll be like the hashtag or like number symbol and if it's just like like Dave or like P or something like a tag you don't fit anything。

So。Basically this variable is now just pointing to this div right here and so we can change the background color by using like dot sell that background color and change it to lime green so if we actually like compile this code and like put it in the browser the divIF would be mine green。

And another way we can select elements is by document docket element by ID and this is basically the same thing asqueer selector。

 but instead of being able to select like class names or ID to like anything you can only use ID for this and the reason you would do this over queer selector is because it's faster and also you don't have to worry about like putting the hashtag or like period in front of the ID name because all you' ever can select using this as IDs so you just put the string of the ID inside of parentheses and。

Yeah， for example。It's just talking about it element ID and then we're assuming there's like some HO like if or something with the ID demo and。

So that's selecting that element and then we can change the inter HTML which is basically like if you have like a divb or something and you like put text inside of it and like if you load in the browser it'll like say that text right inter HTML basically changes what that text says so。

Whatever like this dude would be or like whatever this element would be。

 now like the text of that would be hellello world。对。Something makes sense so far？All right。

So what can we do with this， we've already talk about in HTMLMl and style style would just be like any CSS style so that it would be like dot style dot background color or like dot style that color or like dot font or something and then we can also change the elements class name using JavaScript so if we do likequeer select or whatever dot class name。

 we would like dot class name equals and then like some class name we would actually change the class name of that element。

And there's also just more elements， if you like Google it， there's like a ton of work you can do。

And some other methods。Two of them are elements by class and get elements by tag name these two return arrays and basically it selects like all of the elements in your HTMLMl that have that specific class or that specific tag and it returns an array of all those elements and this is useful if you want to like loop through all those elements and like change parts of like each one of them。

And you can also create an element using this by using the create element method and tag。

 so basically that tag would just be like div or P or something that would just create a new div or P。



![](img/6479d6852f01fc5d759e842fca9899b9_3.png)

嗯。Okay， so here's a demo。If that career out just like a say。Oh， yeah， yeah。And also sometimes if you。

Like if you click on like a button or something and you want a new div to show up。

 you can do that because you can't really do that with like just HTML button。嗯。

Hopefully we can see that。But so basically just to demo query selector and get element by ID。

 say that we want to like change the text of like that blue body one tag or that blue body like element。

We could select that by using query selector because that blue body one thing that is the H1 with a class blue text。

哦。So what we could do is we could do like Po body one equals document。 query select。And then。

被文我发工资卡文。We notOh the lights。哦。呢个是。No。嗯。I don't know how to turn off the lights here。There is like。

听我唔讲咩嗰佢先。'Not very good with stuff I have no idea what's going on here。嗯。

Can you guys like still kind of see it？嗯。It it like visible at all。Okay。Yeah。

I guess if you if you don't know what's going on just like ask。

 I guess and there's also going to be recordings， sorry about that。

So since it's a class name per query selector， we need to put a period in front of the class name。

 so the class name is bluet。So basically， body one is now responding to that H1。嗯真。

And so could you body one do inner？H you can just like decide what we want。

The text of that to be so we could do like。I like that。And then。Oh， body want to inter H well。

And now we change the text。Of that H one that used to say body one to JavaScript Do is the v using JavaScript。

And so we could also use get element by ID if you see the introduction thing right there。

 it has the ID introduction so we can actually select that element using get element by ID so we can say cons。

Intro equals document。嘅就你。Bye I D。And since we're just getting about the ID and like it's just。

 it's always going to be the idea， we don't need anything in front of it so we can do introduction because that's the idea of it。

And then if we want to。没必会。Make the text of introduction like more legible because it's really ugly right now we could do like intro。

tyle。color equals like white or something。And if we save that now。

 you see that the introduction text is now white。And we just did that by selecting that element and then changing the color of it。

Do that。

![](img/6479d6852f01fc5d759e842fca9899b9_5.png)

So as I kind of mentioned before， we can modify multiple elements at once so we can multi modify them using a loop。

And taking advantage of the methods that return ors so in this example iss just on order list that has a bunch of list items that all have the class JS target and inside the JavaScript it。

We're selecting we're like creating a array basically of all of the elements that have the class name JS target。

And so because it's an array now we can loop through it all and then。For each。

Like element inside of there we're just changing the inner text to modified by JavaScriptscript so basically what's happening in this is that all the elements instead of saying unchanged now are just going to say modified by JavaScriptscript because we selected them all and then changed the inner textex of them all。

All right so events and listeners so basically events are like when certain things happen on a page。

 so for example， if you click on a button or you like type in in like some input or even if you like hover on an image or something that's an event and listeners are what we use to like。

Basically tell like when an event happens so respond to these events by having event listeners and these event listeners run when whenever like the event specified happens so for example a demo。



![](img/6479d6852f01fc5d759e842fca9899b9_7.png)

嗯。So。If we have like。In input or something。And we've put the class name of like， I don't know input。

And then。Do you put like placeholder text。To take here。And then。

We have like a P tag that says nothing has。U。我 the classね。不会。People裤。And so a nurse group tag。

We can select this input element and then actually like add an event listener to it。We document the。

There is laughter。点出。And then if we want to if we want something to happen when we type in this into this input。

 I should probably show what it iss doing。

![](img/6479d6852f01fc5d759e842fca9899b9_9.png)

So yeah， you can see。We basically have an input。And then the P tag， nothing has happened yet。

Because nothing has happened yet。And so we could do input。i event listener。And then。

We can listen to if like when there's a key up。So， that basically means。

Just whenever you type into the text box of the input。

 this function that we're going to make is going to fire。So。In this function。If we could like。

Change the text of that piece。 So first， we would have to。

Select the P so we can like select it and then change the inner HTML of it。So。

 so now we have key copy as a variable in our JavaScript。

And so now we can change the in your HTML of it so we can say could you a copy。有。

coffeeoffee doin HTML is equal to。Input that value。So this will basically set P copies。

Like text inside of it to be。Whatever text is inside of this text box and it'll update P whenever you change something in that text box or like whenever you like have a key press in that text box because that's what we added the event lister for。

So if we like type here like that。You see that it changes the text of that。That's。He right it there。

 does that make sense？Yeah， oh yeah， yeah yeah。That should also work。Yeah。All right。

 so that was kind of a demo on how to use event listeners。



![](img/6479d6852f01fc5d759e842fca9899b9_11.png)

And another way you could do this is using inline event handlers that do the same thing as adding an event listener just like the way that we just did it。

 but you can only assign one event at a time so basically just see what I'm talking about this is the way that we just did it so that we have a button and then we like select it by get element by ID from the ID button and then we add an event listener that listens for when the button is clicked and then whenever it's clicked that function will fire and it'll alert you that you click on the event well you clicked on the button。

And an inline event listener would look like this。And so basically it gives the button an attribute on click and then sets that to whatever function you have like inside your script tag or like your JavaScript so in this case you name the function My function and so you have a my function in the JavaScript and then that function like one called alerts the same thing you click on the button。

 but in this case you're not like adding you're not like typing out like add event listener you're just putting on click。

My function， but the only draw the drawback is that if you want to also have like an on hover like a function that happens like when you hover on the button or something。

 you can't do that with an in line of a handler because you can only have one and if you try and put another one it'll just like override the one before it。

All right， so event alllegation。Basically， since it's a tree kind of data structure， the dom。

When you like when an event handler？Like when when the event like it listens and it like sees that you like click something or whatever。

It moves like down the tree and then like back up so basically whatever。

Like your parent notice if like something happens there， it'll。

Like show up on the other elements if that makes sense so basically。As you see。

 it just like it goes down and then it goes back up just like like a tree。



![](img/6479d6852f01fc5d759e842fca9899b9_13.png)

And to just demo this。What if we have like。A button。That's a。Work me。With a class or could do IG。

 I guess or。What' it us。If we wanted to oh wait， yeah and。If we have like。A bunch of these buttons。

If we wanted to like have an event listener for each one of these。

 we would have to like manually go and like loop through all of them and then like add an event listener to all of them。

Which is kind of tedious and also like not very necessary if we want the same like thing to happen when we click on each of those buttons。

 so instead we can put them all inside of a do。And we can just have a class for this。That's like。

Container。And so basically， if we put an event listener on the do for like on click or something。

Then for each of these buttons， it will also like do the same。

 it'll like have the function fire for like each of these buttons。

Because of event bubbling basically because it's。The buttons are like children of this div。

The event really。It'll like bubble up so。If we did that， it would be。

We would have to let this do so on container equals document。Very chill laughter。Where。And then。

We could do container do。And event listener。And this time， we're going to be watching for a quick。

So whatever someones on it， this function will find and。

Maybe we could do like each time you click on it， it'll make an alert。That says。要。Clicked on。呃。Like。



![](img/6479d6852f01fc5d759e842fca9899b9_15.png)

And so。If you then click on any of these。Then it'll。

Say that and if you don't understand what happened just there。

Basically we have added an event listener to listen to on click for that div container that contains all of the button elements and so for the add event listener like the function。

 we can actually pass in like the event you don't have to。

 but if you want to use like the actual event that happens。呃。

Then you could pass that in and basically what we're doing there is event target intertex。

Basically like the event would be the click and so the clicks target which would be whatever button you just clicked and the inner text of that button so well for all these buttons right now it's click me if we like changed it。

Play one，2。3。开。诶。We can see that like each time we click on it。

you can't see but it says you clicked on five when you click on the button that says five on it and you click on three when you click on the one that says three so basically。



![](img/6479d6852f01fc5d759e842fca9899b9_17.png)

That event that part the enter text， the inner textex would just be whatever text is in your button。

And the target is like the button itself。So then it just alerts。

 you've clicked on whatever button you've pressed and we don't have to add an event listener to each button because of event bubbling。

That the container like encapsulates all of those buttons and so it like kind of like bubbles down and then you can like bubble back up and they'll like still have that same event。

Like it'll have that data of the event they can use。



![](img/6479d6852f01fc5d759e842fca9899b9_19.png)

![](img/6479d6852f01fc5d759e842fca9899b9_20.png)

。All right， so what's basically like the lecture is pretty short， but。Just a side note for。

Like the future I guess， or if you guys if any of you guys have learned react or any other framework。

 what we just did was vanilla JS， but if you ever use reactactor like any of those industry tools you won't actually be like manipulating the Dom like the way we did right then but we thought it would be important to like know what' was going on and like how to actually manipulate the dom like manually because it makes it a lot easier to understand like what frameworks are actually doing and。

Like to like actually know what's going on in those frameworks。And also。

I think a lot of companies like interview in vanilla Js as well。

 so you might have to still use vanilla Js even if they don't like you used reactor and like next or something。

So yeah and just some announcements homework two is due today if you have questions you immediately post on and you can also ask me right now and。

For the project， one personal website is due on February 24th。

So yeah that's that's the lecture thank you for coming。😊，诶Yeah。Okay。Oh yeah， the attendance word is。

Unicorn， it's unicorn。Yeah， the the attendance's word is unicorn， yeah， all lower case。Yeah。啊 yeah。

So。你细。Oh。Yeah。这个。我啲。Yeah。那て。好はい。好现。我帮你。No。可以啊。这个是。Yeah。系。那。Hello。Thank。感。こ。原告。系在还个。你好系。两点半。嗯。Okay。呢行。

Yeah。那完。Can I ask technicalBook'。没好。まし。あはい。到几。です。嗯，好的行，好的。我咩话。Okay。は。那所以他们边。系冇下。后然后对。对非常像。我诶啱。

So those。And then hi those to classic。啊，一米。嗯。P。I was wondering S like book copy the stuff during one。

 so if I save it this I the top works like this works， but this doesnt this。

Like all of your JavaScript into one script tag。SoI them I feel like。🎼Uing。好。Can you doing。嗯。对。是。

After just a try and thought was a source， it very hard though。是这。诶你。嗯，我就。は。嗯的啊，了嗯。It是。So yes。

 there was panel。嗯，すでこ大丈。嗯上个我先。你。Thank you人。I don't know that。it may not exactly okay alim' hM。

I change the。佢我我以咗。私都管。而得这个。And didnt know should slide。Thanks what。我就做。哦，但今日我哋唔系嘅事。

Yes don't chocolate says like just from the。前一个。I。你那么点。Yeah， it is such。Start the。The。

I looks so imagine this is what I've done。も。那我这里。没有。I just emotional fine。

Because we're adding margin， we want to sit on。okay fine。度诶三个。So took a little distance。あめな。

how I a lot of how would you recommend I feel like that complicated。他主要来嘅。诶本先你件时先车。Does don justs。

exciting。Yes。AndI。And it looks like is this a big message。Yes。

realized couldn't sleep and I approached and then I like wanted to my learning URL and it wasn't like changing so then I unpolishged my taste you know I' come to building。

I'm sorryrry。Yes。考。All right。I want to recently submit the URL on grade skill for get updated right like we don't have to generate a URL URL Yeah it think like the URL in the read。

一瞓照。So other acusement makes， it's just only this part。打开不书。よしたおいます、ね。我这。That过。Buts a secret。

So during。Yeah个是个质本的关系。没有。正嘢。咁实咩千零。对。Yes。In the building yes， but bringss。我。

the one that I know yes doubt。what books。like。Something like initially this week was my global on my computer then。

I participateす。咱村块就是给你个给点准确的是吧。嗯嗯。你这唱一下。It's to everythings going to my directorcur。

So like it goes to local so like local files， my user downloads and then own my computer it send out your computer。

This happens is so see know。嗯反正不起码打一嘛要想去。か。Yeah。🎼Okay is it correct is it。Yeah。嗯。at each perspective。

Let's see you sound like H which like any part。this is a single message Okay， let's try try not' see。

I don't know why the private go short runs for。And any number I can see has English。另外个前况呢啲嘅。这是。你问你。

没什。Yes。有人。嗯。Yes是那个。没问题。我 think我哋佢之前都做做啊。嗯嗯嗯就是。ick haven't。全分钟。Well，真。我 do。some都不。嗯。因我觉得我就是。同意。So。好这个。

嗯。对。对。你改。再见。对。Okay。嗯，那。Yeah。闹钟听到。诶，有啥原件啊。是我真的有。啊呢。这什么意。没有。Yeahs。Yeah，该。でで最て。系好先。唔使觉咗啲大。No。没。嗯。这关是。嗯。

It。对。t。嗯，这个。do方 yes。Yeah so think。I should I did it。 I did and you and then。你唉关这另一个事。不，是这个是。

get I was going I think is there a more origin was the difference。不是。So given I on lecture。

 if get clone automatically test。呃，因为一般的。现在我看。啊，谢谢。それでなおしゃりまし人あて聞て。just。嗯，你真系。なちゃ。So for。

It should be the same attendance link as。

![](img/6479d6852f01fc5d759e842fca9899b9_22.png)