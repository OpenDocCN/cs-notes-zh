# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p43 -44-COMP6080 - A11y 🥕 Perceivability.zh_en -BV17RXGYuEaM_p43-

Hi Com 6080 class， I'm Mike and ROP presenting a four part lecture series on accessibility。😊。

It's become an increasingly prevalent thing that the industry has cared about and it's something that we expect all front end engineers to consider as a first class priority alongside legibility。

 performance， testability。😊，And just generally， just we should consider as a first class citizen。

So the question I want to start off with is what is accessibility and why should we care about it？

Essentially， everyone has different preferences for how they live their life and accessibility is about accommodating everyone。

 not everyone is going to navigate the web in the same way as what you might be used to。😊，With。

With desktops or laptops， not everyone's going to be using a mouse。

 Some people may only prefer to use a keyboard， and not everyone's going to see a screen。

 Some people may want to。Use a Braille pad to experience what's happening。

 or they may want to use a what's called a stream reader technology what that does is it reads the content of the screen。

And presents that to the user and they can interact as well with those elements。

It's not specifically around disabilities， it's just about different preferences and if you want a web that's universal for everyone。

 we have to accommodate all these different needs。😊。

So you might be asking how this is quite a big statement， there's a lot here that people。

 there's a lot of different ways that people can experience the web。😊。

The main standard is called the Web content Accessibility guidelines。

 so the web content Accessibility guidelines are a universal standard that codifies a series of testable。

 measurable statements called success criteria。😊，These guidelines apply play to all web technologies including mobile apps。

 and they are the basis for global legal standards。😊，This course will only cover WCG 2。0。

 but it has been updated and expanded upon to a more advanced set in 2。

1 go ahead and check the link out it's quite detailed and this course will be unpacking that。😊。

So there are three levels。😊，Level A is the lowest standard。

 it's specifically designed around certain crerion that's likely to be a blockup for certain user groupss。

😊，Level AA is the standard that most companies aim to achieve。

 and levell AAA is specifically used for sites that are that are targeting people with disabilities。

😊，So we'll mainly be covering AA， but we'll touch on AAA where it's relevant。😊。

So there are four principles of WCAG and these will be the four lectures that we cover。

 one on each topic， so we have perceivable， operable， understandable and robust。

So we'll go ahead and unpack that one at a time， starting off with perceivability so for all content to be perceivable components must be presentable to users in ways they can perceive so that's quite a big statement。

😊，There are a few different componentss， one of the most important parts is non text content。

So all non text content that is presented to the user should have a text alternative that serves the equivalent purpose。

Text alternatives are a primary way for making information accessible because they can be rendered through any sensory modality。

 for example， visual， auditory or tactile to match the needs of the user。😊。

Providing text alternatives allows information to be rendered in a variety of ways by a variety of user agents。

 so if you're finding it really hard to read content， you might prefer to have a voice assistant。

 read that out to you or if you can't see but but you prefer feeling content。

 then you might want to have that translated to a Braille context。😊。

And we can only do that if there's text there。😊，All next or non text content that would be including but not limited to images。

 icons， video， audio， and charts。So we'll jump into an example with images and we'll go from there。😊。

So take this image， for example， this image is not perceivable seeing without seeing it。😊。

This creates an adverse user experience for screen reader users or even just low bandwidth users。

 an alternative text should be provided to improve this。😊。

Even if the source of the image was it included what it is。

 it's still not good enough to describe that experience。So there are three steps to opt。

The three steps are describe the image， adapt it to the context， and marked decorative images。

So what we're looking for is a sentence or a phrase that's best kind to describe what it is。

 so we're not looking for a word or two that's really important to understand。😊。

So here we have a beach landscape on a sunny day looking back over a city。

 this is a really good al text because it captures what we're looking at here。😊，And it's good。

 but it's not always going to be the most useful art text。 So you don't want to always just。😊。

Capture the alt text when you upload the image or when you have the image。

 you need a match to context。It used in an article about Sydney tourism。😊。

Maybe a better outtt would be。Would be Sydney's world famous Bonai beach on a sunny afternoon。

U and what that does is it captures where it is， which is particularly useful in in an article about Sydney tourism。

 but may not be for other contexts where it's not going to be immediately obvious。

 you want to match the experience of seeing the image as much as possible。😊。

If it's just used as a decorative non meaningful banner， say for example。

 it's repeated a bunch of times an empty string is preferred。

 this is not the same as no al text as this will explicitly tell any any any。😊。

Any software that's trying to capture this experience， it'll explicitly tell them。

 don't worry about this image， this is a decorative non meaningful banner。😊。

Let's take another example， so here we have this floppy disk， we have this icon of a floppy disk。😊。

And。We don't really know what it's used for。

![](img/ca2641210af8aafbe0963883a4f65517_1.png)

So go ahead and think about what it be a more appropriate alt test。And essentially。

It depends on context， if it's a list of icons， sloppy this is probably the right one。😡。

If it's a save icon， what you want to do there is rather than saying it's a floppy desk， floppy disk。

 say it's a save icon。Or just say it saves and if you're trying to describe an action。

 it's probably better that to put that label on the button and just say this is a。

This is a decorative image， and we will elaborate a little bit more on the labeling requirements for buttons in a future lecture。

😊。

![](img/ca2641210af8aafbe0963883a4f65517_3.png)

As an exercise， have a think about a simple line chart。😊。

Think about what meaningful foot information would be relevant to the user you'd want to communicate so a hint I want to give you here is it would be very hard to understand a list of coordinates。

Instead， think about the direction of the line chart。

 think about what information or what message you're trying to convey to the user。

So another part of perceivability is distinguishability。😊。

So we've covered non text content for the text that is there。

 that has another requirement that it must be legible。😊，嗯。

So text should be used instead of images of text。😡，This is fairly straightforward。

 if it's mid of text， there's going to be a lot of software that's not going to really be able to understand what's going on。

😊，The page must also not resist being zoomed in up to 200% and must not result in a loss of content or functionality。

😊，A large part， a common theme of a lot of accessibility go loans is really just not resisting what browsers do because browsers。

 for the most part， handle accessibility pretty well as long as you don't resist a lot of things。😊。

So the most important problem that the most common problem that happens in distinguishuability is the color contrast of text and the background。

 including images。😊，That contrast must be sufficiently high。So in practice， this means a 4。

5 to one contrast ratio for text smaller than 18 points or three to one contrast ratio for text 18 points or larger。

So what this link does is it takes you to a contrast check out and you can test various different colors。

😊。

![](img/ca2641210af8aafbe0963883a4f65517_5.png)

So let's take this example， here we have text on an image and to a certain extent。

 it's really hard to read。😊，The text is on a part of the image。 that is。

That is quite visually intense。And the color contrast isn't really getting you there， by the way。

 a when you're comparing text to images， you typically want to pick the worst part of the image and test that according to。

😊，According to the contrast guidelines。So here on the right side。

 we have text with an image that's darkened。So here it's a lot easier to read the text。😊。

Not everyone's going to want to duck in their images say so this requires a bit of design slash creativity you can change the contrast of the image。

 you can darken the image， you can change the text， you can add a。And a box around the text。

 as you might have seen in movie subtitles， the text will often come with an outline and that works just as effectively as well the guidelines are fairly flexible as long as there's some way to see the text on the background。

😊。

![](img/ca2641210af8aafbe0963883a4f65517_7.png)

是的。So that covers the first。Part of accessibility so just to wrap up we have perability and that means the ability to distinguish and it would this gives you the ability to distinguish content this applies to both text and non textex content。

😊。

![](img/ca2641210af8aafbe0963883a4f65517_9.png)

See you next time。