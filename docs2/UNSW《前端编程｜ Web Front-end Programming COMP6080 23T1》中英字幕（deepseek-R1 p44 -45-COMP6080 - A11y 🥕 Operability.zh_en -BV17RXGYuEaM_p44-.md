# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p44 -45-COMP6080 - A11y 🥕 Operability.zh_en -BV17RXGYuEaM_p44-

Hi class， welcome to Part two of the Accessibility series。

This one will specifically tackle operaerability。Soopability means that components and navigation must be operable。

😊，The interface cannot require interaction that a user cannot perform。

Not everyone who interacts with a web page will prefer to use a mouse or a touch device。

It's important that all page interactions support keyboard。

 all page actions support keyboard interactions。So a lot of things are going to come for free as long as you don't override them in soarrow keys in space and page up and page down to jump down the page and up the page。

😊，Tab and shift tab to jump between interactive elements。

Enter andarrow keys to interact with the element。So specific examples mean that buttons need to support click and tapap as well as Enspace key。

 links will need to support click and tap as you know， it'll also need to support EnT。😊。

Select dropdowns we need to supportarrow keys to change the selected item and support enterter and E。

So a lot of these are going to come for free， as I said before。

 it's really just making sure that you don't override the bras default and any custom components that you want to implement。

😊，That they're not being everriden or they're not being implemented。

So that's kind of what you the main section that you want to be thinking about there。

So one of the most important takeaways is to not set keyboard traps。

If you start at the top of the page。Tabing should hit every interactive element。

 and after the last interactive element， it should cycle to the top。

This means showing the focus outline on every element at least for keyboard users。😊。

So this is an example where you might be trying to implement something that you're trying to do。

 but what that accidentally does is it makes things unusable for keyboard users。

So here we have a prevent default， what that's going to do is when you press tab on that element when that element is focused。

 it's not going to go to the next one。So yeah， this is going to be something where you need to be careful of what's happening here。

😊，Often if you're trying to do a particular particular UX for visual users。

 you just need to be careful for for keyboard under users， that's going to be a big part of。😊。

Of your assessments at this stage that they don't have this。



![](img/fba8e31008d96070cd2452447abb914d_1.png)

So let's look at some interactive elements。Forms and form elements should be marked up correctly。

Often using standard HTML elements such as buttons。

 inputs and text areas over messing around with divs。😊，嗯 will。Work better for you。

 So rather using devs to achieve a particular style， use standard HTML markco。

 It makes it a lot easier for browsers to support operability and for people to understand there will be times where you do need to do it and it's just going to take a lot more time and a lot of the styling say yeah。

 like the button styling is not particularly nice， but it's going to be easy to override than to try to support everything that the current button is doing。

😊，It's also important to add appropriate attributes This will be expanded upon in the next lecture or skip ahead and read the spec on NDN。

😊，EG， I've added the one for the inputs， and they all link out that one。

 it's going to be fairly easy to find。😊，So here is an example of a form element here。

 we have a label， We have an input and a button。 The button is going to be what I want to call attention to here because we will spend more time on labels and inputs to the next lecture。

But here we have a button and the sub type submit， so notice that the button doesn't have an onclick function。

Instead， the form has an odd submit function。That does。Pretty much the same thing。

 but what it does on top of that is if you have an input， if you're selected on an input。

 if you have， if you're focused on an input， if you're on a phone device or a screen reader。

 it'll allow you to submit the form immediately， So that's gonna to be really nice for a lot of users。

😊，Who aren't as comfortable using the mouse or using the using touch。

The one commonly accepted exception in the industry is select elements。

So the CSS customization of the HTML element is very， very limited。😊。

Unlike buttons and inputs and text areas and forms。

 you're going to know what to override most almost over everything you want to do and it's just going to be a lot easier than trying to fiddle around with divs and then adding all the keyboard handlers and adding all the markup。

😊，嗯。So if you add select elements， you don't need to worry about that。

 that's going to come more or less for free。

![](img/fba8e31008d96070cd2452447abb914d_3.png)

So use。Use headers， sections， sidess and photos。 This is going to be really important。

 This is going to be something that's quite going to be。Quite heavily assessed in your page， so。

If you're looking at a visual page， the sections and categories of everything is going to be a lot clearer。

 So it's may it's really important to add。That markup to your page to improve offerability if you can't see the screen so we're aiming just to create parody between the or as much parody as possible between visual users who can see a screen and those who can't see a screen and are just relying on markup and some visual some audio or tactile feedback instead。

So headers will tell you what's at the top， that's note that this is different to head。

 which is specifically for metadata， header will say this is the top of the page and for screen reader users。

 they might just want to skip over this because they've seen this a thousand times。

So you want to include a nav as well if you have a nav list or a nav menu。😊，嗯。

So if you have multiple nas， you need to label them。

And there there is markup available to say what the label is， what the nav does。

 So if you if you have a nav in the header and often people have k nerves in their side or foot。

 if you have more than one you need to you need to。😊，Say what it is。Also in the header。

 I want to call out that here I'm introducing the concept of roles。

 which is going to be really important as we progress through。😊。

Here it tells you that it tells the user that this is a search bar。

 that this may be apparent from the UI， but it's not going to be apparent to keyboard users or screen reader users。

 so it's really important that you mentioned that this is a roll vehicle search。😊。

Also you want to have a main section and sections within that it's really important that again the order is correct that you don't have mains within sections。

😊，Um you can actually sections outside of mains and you can have sections in the sides and foot and headers。

😊，嗯。But that's kind of kind of be the hierarchy that you want to be comfortable with。 aside。

 the side can be before the main。 You just， it's just important to have the markup。

And just have a photo yeah。If there's repeated content， use a skip link to bypass it。

 So skipling is a weird kind of industry hack。But it's really。

 it's really useful for screen reader users so essentially。😊。

YouYou need a piece of text that's invisible until it's focused。

But it needs to be invisible in a particular way。 So using display none will hide it from the tab order and using visibility hidden will also hide it from the tab order。

 So what this does is it。We clip it with a bunch of things to just make sure that it's not visible unless unless it's immediately focused so when you when it's on focus。

 you can see everything is just un and。Yeah， that's just going to really support keyboard users a lot of websites they where they have this to support。

😊，Spific key。Specific users who aren't looking at a screen。

Um skip over carousel is itum there are a few different reasons why you might want to use a skip link。

 one of them is you want to skip over the carousel。😊。

Here we have a carousel and if you keep scrolling it it's just going to keep loading loading more content。

 So actually what you effectively created is a keyboard trap without the skipling。😊。

What the skip leg would do is it allows you to skip over the carousel。😊，So here。

 because we have a Hf with hash， that's going to jump to them to this element。

And create a seamless tab order。 you might offer you is also commonly expected that you add one to go back up。

Because they might want to tab all the way down and then shift tab all the way up。This was。

 this is just gonna support that。It's also really useful to have skip links if you want to skip at the top of the page。

 you want to skip directly to the main content， that's going to be really useful if you want to say send them directly to the first big call out but you don't want。

😊，you still want everything else in the between to be clickable if that's something that you want to provide。

So HTML is quite limited。It was just never designed with web applications in mind and so was never built for more complex Us I'm sure this is something you're very aware of at this stage。

😡，嗯。😊，So what work has been supplement on top of H team model is IR， that A R IA。

It is a series of additional attributes to supplement HTML， It is not intended to replace HTML。

It should be used sparingly and thoughtfully on top of HTML tags and roles。

So AR stands for accessible， rich Internet applications， So it's yeah。

 its it's designed to try to accommodate more of modern web applications。

So we'll go through all your attributes here， I think that's going to be really useful it's going to show you a glimpse of it unfortunately there's quite a lot of attributes and it's going to be something that ING is probably the ones likely you're going to be most likely to use。

😊，Um， but yeah， not everyone is going to want to use the attributes。

That I supply here or may want to use attributes that I don't mention。

 so that's going to be where you want to look to to the markup。

 but these are the ones that are going to be specifically referenced in your assessment。



![](img/fba8e31008d96070cd2452447abb914d_5.png)

So with Aria， you can add labels for icon only buttons。

Here we have a button that that reveals a menu。But the image is just a hamburger or icon the three horizontal stripes。

And obviously， because it's doing something， we just want to have out text equal empty string。

But here you can add a label so even though it's apparent from the UI we need to we need to say what it does so here you can add I label it's not going to show up in the in the visuals this is really just attributes that tell the tell the screen reader or the voice assistant hey this is a button that shows a menu so if you use voiceover on OSX it's going to say something along the lines of button comm show menu so that's going be really useful。

😊，You can add state for custom components that have no native HTML equivalent。

 Many attributes are only valid on particular roles， so here we have a button with roll equal switch。

So here the example I give is you want to accept cookies yes or no。😊。

So this is something that's quite stateful so this will only work if you're using JavaScript whether that's react which is probably what you're using in this course you could also be using GQury just anything that's going to support changing changing the the。

😊，They attribute。So here you can accept cookies and for as long as you're on the page。

 you can turn it on and off。😊，Here we have our chat。So this can be true or false。

 This can be something you can toggle。 This should reflect the current state and they should be reflected in both the UI。

 as well as。As well as in the attribute。You can define modal takeovers。This only adds markup。

 So in many cases， you need to add jascript to actually implement it。

 This is just to tell the screen reader user that this is intentional。

 This is what the alert is trying to tell you to do。But it won't actually the moment for you。

 It is just so that if it does happen， if you need to implement it by JS， it tells the screaming。

 hey， don't worry， like relax。😊，You could still use the page。

 you just need to perform this action first。So here is a really good example。

 we use this we something along the lines of this at Canva。😊。

We you need to sign in to perform this action。This is， for example。

 if you you're in a browser and for some reason your cookies have been peer cleared or your local storage has been cleared。

 just something that's going to make it so that the authentication token is broken。😊。

So you need to sign in to perform this action even just something as simple as you've an idle and the token is invalidated so here you need to add role equals alert dialogue in other cases role equals dialogue makes more sense or role equals alert in this particular case we want to prevent any other actions and we want to ban everything else so how this gets visualized in the UI is often a big box with some text and everything else is black or everything else is gared。

😊，So while you can't click anything directly， often a lot of those items are still tabable。

 so you need infinitenet JS to band taping to anything else around it。😊，Yeah。

 so saying role equals a dialogue as well as Iotal equals true， that's going to serve you well here。

😊，You elements can define control relationships between elements。

So here I controls accepts an HTML ID。So you have an ID on the button。

So you have an ID on the element type that the button controls and you have are your controls on the button。

So to cast back to the old example， the previous example of show menu。

You need to include what the menu controls。This is going to be really useful to indicate what the button controls。

😊，It's not actually， as I said before， it's not going to control。

It it's not going to control you need infinite JS to control it。

 so you need to mark this up yourself， something that's really common to do is when you've shown the menu。

 when you want to say once you've actioned this button， jump to that aside。😊。

That's going to be a really common pattern。That's just going to really ages as。

And say when you've closed the menu， you go back to the button。Yeah。

 so you can control the through Js。 That's going to be what you want to do there。

You also want to define whether the element that is currently expanded or not。

So our expanded is intended to be used for pop out or pop up elements。

 So if you have a button that pops out a menu or a button that creates a sidebar pull out。

You need to use Io expanded and it's quite stateful much it's pretty similar to Iya checked。😊。

So if I expanded is false， you still need the element。

 or you just don' you just don't need to have anything inside the element。

 so this can be blank when it's the inside of the outside can be blank。😊，嗯。But when it's true。

 it's expanded and that just that just makes it a lot easier。

And the last part of what I want to mention here for this particular example is AR has pop up。

 so this is a bit of a weird evolved attribute。 so just to kind of elaborate a little bit more on that IR itself has expanded due to the needs of what it used to be so AR has pop up used to be true or false。

😊，But now we want to accommodate the different control patterns that might happen when you have something that pops up。

So here we have RR has pop up equals menu， so has pop up can be false， usually don't need false。

 that's kind of the assumed default。😊，But what you can do is add a string here that can be menu。

 list box or dialg， there's going to be your three that you most likely want to use。

There are a few others， but they're super specific and they're probably not what you're going to be doing in this front end fundamentals course。

 So menu list box and dial menu is yeah， it's going to be a list of menu items。😊。

This box is really just the other word for select。 So if you have a select menu。

UmYou want to show each list， you want to show when it's expanded， show a list box。

Of all the elements and you have list items within that。Or options。

 as they prefer to to to be called。 we also have dialogue。

 So that's an example that's related to the other one。 You can。

You can do a sign in that this button has signed in and when you click it。

 it has a Moal takeover and it will say fill in your username and password。

That's going to be the example of what you'd want to do there。So combining this all together。

 together gives us the ability make to mark up our own select component。

 youll still need to create your own you still need to do this the JSX。

 but this will tell you exactly what you're looking at。😊，So if you want to build our own select。

 we need a list element with Ro equals list box。 So here we have the same I controls our expanded I has pop up。

And the area has popped up its list box。We have the button that tells you the label of the element。

We have a an unordered list that parts really important as well， we override it with list box。

 we override the role with list box and we have the ID that's referenced by the controls tag on the button。

And yeah， we have much list items with Ro option。And I selected should be false。 This is a list box。

 This is trying to emulate a select so usually one of them will be true。

 but what this does is it allows you to multi selectlect and so you can have I selected it can be true for a few examples if you're doing that I believe there's this attribute on the list box to say multiple can be selected So that's going to be really useful if it's something that the UI supports。

 but you want to support here。😊，嗯。Just something I wanted to call out is as per the beginning of the lecture。

 you would need to add keyboard handling。Well while stuff like enter will open because if the button enter will open the list box。

 you'll still need arrow keys as well when you're selected in the list box to select between the options。

And。The most commonly accepted pattern is when youre have the last time scroll to the top or go to the top。

 Taing will exit the list box and closeboard through something quite similar to that where it just closes the list box and it returns focus to the button。

😊。

![](img/fba8e31008d96070cd2452447abb914d_7.png)

Extra considerations。This's going to be really hard to do。

 but it's something I wanted to call out because I think this is really important。

 this is going to affect not too big of a population but it's going to just cause a really terrible experience for them。

😊，I don't think a lot of us。Think a lot too much about this。

 but it's just one of those things where if you're not careful。

 you might accidentally cause seizures and just you might put someone in the hospital。

 we don't usually think about front end engineers doing this sort of stuff， but it's possible so。😊。

Do not design content in a way that is known to cause seizures。

 This includes flashing content very quickly and you need to be extra careful with flashing red content even even moderately quickly' there's an exact specification that you can find online。

 but really just，😊，Use common sense。 don't flash things too much。

 This is gonna be really hard to fail。In your assessment and just just going forward。

But that's are something I wanted to call out。It's also important to give sufficient time for users to complete tasks unless let's say it's impossible to do so。

 say with an online auction site， you don't really have the luxury of being able to give that sufficient time。

😊，But otherwise， yeah， you should try to accommodate how people experience the web and not pressure。

 not create too much pressure there， some people might have learning disabilities or cognitive disabilities or just they just take their time and it's important to give sufficient time for that。

😊，So for example， error messages should stay visible for as long as it's relevant and any tool tips you may want to use should stay visible if you hover over the tool tip。

😊，Yeah so that's fairly straightforward the tool tip one is something you may not have hit if you're building your own tool tip if you hover over if you hover over the element it should usually stay up but if you hover over the tool tip it should definitely stay up。

😊。

![](img/fba8e31008d96070cd2452447abb914d_9.png)

Cool， so that wraps up operability。Really just， yeah， don't overwrideite the browser defaults。

 if you're implementing your own custom， you need to add a bunch of attributes。

 IO is well supported to。Give you more answers to that。



![](img/fba8e31008d96070cd2452447abb914d_11.png)

See you next time。