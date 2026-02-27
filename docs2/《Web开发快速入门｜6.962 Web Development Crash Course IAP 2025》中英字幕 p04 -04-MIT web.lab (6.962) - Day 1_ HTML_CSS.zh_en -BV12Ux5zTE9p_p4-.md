# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p04 -04-MIT web.lab (6.962) - Day 1_ HTML_CSS.zh_en -BV12Ux5zTE9p_p4-

Okay， since we're a little bit behind schedule already。

 I'm gonna go ahead and jump into the next lecture。 So as an introduction， I'm Sovi。好。Oh。

 and this is Evan。 He doesn't have a mic。 So saying his name for him。Yeah。

 so our lecture is gonna be on H T L and CS S。 You might have already seen this before， but again。

 we're gonna to start off a little bit slow and then speed up gradually。 So。

 and if this is new to you， don't worry because， again。

 we'll have the lectures on our website for you to review。



![](img/fe961236d062f74e5842de4dddd1e56a_1.png)

Before we jump in， let's talk a little bit about why H T L and C S S is important to learn。So。

 arguably。The thing in website design is conveying information to a user in a way that's like nice to see。

😊，And Ht， L and C， S S are going be our core two things for front end development， for that purpose。

So here's a website that you might be familiar with。 And here is the H T L and C， S S。



![](img/fe961236d062f74e5842de4dddd1e56a_3.png)

![](img/fe961236d062f74e5842de4dddd1e56a_4.png)

Kind of extracted from it。So H T L stands for hypertext Markup language。

 You can basically just think of it as the language that your web browser is reading through in order to describe what Web page you're looking at。

A common analogy people will use is that H T L is like。

 or if like a web page was like a fully formed person。

 then H T L is the skeleton that's holding the structure together。 And C。

 S S is like the bells and whistles， like the nice flash that makes it appealing to look at。😊。

Fortunately， the main idea of this lecture is going to be that H TM L is really simple。

 And you can actually just think of it as a bunch of nextxed boxes or containers。😊。

So let's see what that actually means。Using this example from X KCD。

All H T M L is really describing on this web page are these containers。 So here's a big one。

 Here's the container that contains the entire web page。

Here's one that contains a little bit more closely。 all the information on the Web page。

Here are three containers contained within that that have the nav bar。

 the title and the actual content。And so on， and so on。

So let's look into the code to see how this is actually done。



![](img/fe961236d062f74e5842de4dddd1e56a_6.png)

Here's a really， really simple website。The code on the left generates this kind of bare bones looking website on the right。

So let's walk through the code and see how every part of it affects the site that we see。So first。

 in any H T L document， you w to include this header thing called doc type H T M L。

 It basically just tells your web browser to use the latest version of H T M L。

 It's pretty easy to forget， but it's kind of important。 So try to remember。Next。

 we move on to our first H T element。And you'll see that it has this kind of opening and closing structure。



![](img/fe961236d062f74e5842de4dddd1e56a_8.png)

And， of course， that's because the elements are containers， like I mentioned before。

So the key structure of H T L elements is that they have an opening tag。

 which is just the name of it with these bracket things and then a closing tag。

 which is the same thing。 But with a forward slash。

 And anything that's contained within it will go in between。 pretty intuitive。

And you can see that container structure right here where we have the H TM L container is containing both the head and the body。

 And then both of those contain other things as well。

I think the syntax for H T L is pretty simple as long as you keep in mind that it has to respect the fact that it's a container。

 right， So you can't have this kind of thing where you're starting something， starting another thing。

 And then closing the first thing before you close the other one。

 So this is basically the only thing to remember。 Just make sure that it's nested properly。

 And you should be fine。

![](img/fe961236d062f74e5842de4dddd1e56a_10.png)

Allright， I'll pause here for questions。There any。

![](img/fe961236d062f74e5842de4dddd1e56a_12.png)

Okay， cool。So let's go back to the code and look at things a little bit more deeply。

So I mentioned the structure of this thing， but I didn't actually tell you what it does。

 This one is called the root。 And it's just gonna contain all things in the web page。

 And the syntax is pretty simple， as' just H T M L。Within those。

 you're always going to include the head and the body。Within the head。

 you store what's called metadata。 So metadata is things that aren't going to be displayed on the website。

 but they'll help it like do what it needs to do。 So， for example， it will include the title here。

 and you'll see that it's not actually on the document。 It's not in like heading or paragraph。

 but it's in the top here in this tab thing。Other things you'll include in there are links to other files like style sheets。

 which Evan will talk about later in the lecture。Next is the body。

 and this is gonna contain everything that's actually displayed。So。That means the heading。

And the paragraph。Which have the following。

![](img/fe961236d062f74e5842de4dddd1e56a_14.png)

Names for their tax。So as a quick stopping point， the H tags that we've covered so far are H T L head。

 body， the headers and the paragraphs。I also included these other ones div in span。

 They're pretty important。 and I'll talk about it in a little bit。

 but they're kind of like your generic。 If you don't know what else to do， you use those tags。

There's also this notion of attributes for HTML L elements。

So we see this like plane structure here that I showed you before。But what if you wanted to like。

 modify your element in a way that you couldn't just do by adding like text or adding like something inside of it。

What you do is within the opening tag， you add an attribute。So an attribute will be defined by。

Putting the name of the attribute and then setting it equal to something within a string。Attributes。

 And that's the value。So some common places that you might be using attributes。

 One very common one is inserting links。So the syntax for link is just a。 stands for anchor。

 if you're curious。Insert a link。 It will add the attribute for H F。

And the value is just gonna be the link。 So here's an example of that。If you click on this link。

 it'll go to Web up。 MT UD U。Another really common one is going be images。

So for image to insert an image， you'll go to the source attribute， S RRC。

 And then you set that equal to the name of the image， wherever that is。

 like relative to your directory。Now， there's something a little bit weird here with this opening and closing thing for images。

 because。When you have an image， you're not really gonna put anything inside of it。

 You're not gonna put text of your image， or you might put probably not in this way。So instead。

 what H T L lets you do。Is get rid of the closing tag entirely。

And make what's called a self closing tag。So for this。

 it'll display the same thing that it did before。 Just an image。

 But because you don't need anything inside of the opening closing， you just make it one tag。Oh。

 another thing to keep in mind， as I mentioned before。

 you have to navigate to the correct like file name。

So if your HTML TM file was in like the same directory。

 like directly as your image or GF or whatever， you can just put it like this。

 But if it's in within another folder， then you need to update that accordingly。

Another quick thing is in the case that your browser doesn't display an image correctly。

 it's good practice to just add alt text。So that maybe a user who's like confused when they don't see a picture will like understand。

 This is also good for like semantics。 If you're just like reading through your code and not looking at the web page。

 may be good to like label things with alt text and things like that。



![](img/fe961236d062f74e5842de4dddd1e56a_16.png)

有。I'll stop here for questions， again。裤。

![](img/fe961236d062f74e5842de4dddd1e56a_18.png)

Alright， some other common elements are lists。 list is pretty simple。

 You can have ordered or unordered lists， and they contain the list elements。



![](img/fe961236d062f74e5842de4dddd1e56a_20.png)

![](img/fe961236d062f74e5842de4dddd1e56a_21.png)

I think that one's pretty self explanatory。 Okay， back to the ones that I mentioned before。

 div and span。 So div and span are gonna be your like go to generic elements。 And all they really do。

 or they don't do anything like specific。All they do is just group together other elements。

 So they're just like plain containers。The difference between them is that div will group like a block section。

 while span will group something that's like in line。 So if you wanted to select like。

 let's say you had like a paragraph and you wanted to select like one thing to maybe like style it。

 then you could use span around that like word or like a couple words。

 And then it would stay in line。 Where if you use div， then it would like。Try to like。

 do a line break or something like that。So here's an example of two divs and two spans。

 So as you can see， like the divs are stacked on top of each other， whereas the spans are。

 they respect like。They're not。Sact。

![](img/fe961236d062f74e5842de4dddd1e56a_23.png)

So if we wanted to add a div to our old website。We could just。I don't know。

 box our body around with a div。You might be wondering like， oh， like， why did I do that？

 It doesn't really do anything。But now we have this nice box where we can just refer to like the div。

 and then it'll refer to both the heading and the paragraph。

And this becomes helpful when you're doing styling and stuff。 Evan will talk about that more。



![](img/fe961236d062f74e5842de4dddd1e56a_25.png)

啊，呀。So I threw a whole lot of tags at you and maybe not like that much time to remember all of them。



![](img/fe961236d062f74e5842de4dddd1e56a_27.png)

But don't worry， because Google is gonna be your best friend with this。

 It's not that hard to find H M L elements and like what they're best use for。

You can go to this site called MN Web docs。 And it has like pretty good descriptions of all the elements。



![](img/fe961236d062f74e5842de4dddd1e56a_29.png)

Alright， I'll stop here for questions again。

![](img/fe961236d062f74e5842de4dddd1e56a_31.png)

O可付。Okay， so as I mentioned before， div is like a very generic element。

 And you're probably gonna want to use it a lot What you're doing， like styling and like。

Referring to groups of things like that。And at some point， I'm sure you'll wonder， like。

 why not just use divb for everything。And there's a couple reasons。If we look at the MN Web docs。

 actually， they say that div should only be used when there's no other semantic element that's appropriate。

 And a semantic element is just one that's like labeled with what exactly it's supposed to do。 So。

 for example， like nav bar， that's a semantic element。 And it's， it's just nav header。

 footer section。 These are all just better things to use。😊，1 is for like readability。

 because maybe you come back to your project like a week later and you forgot like what all these divbs are supposed to do。

 But then if you have semantic elements， then it's easier to like parse your code。

 It's also helpful for like web crawlers and bots that are just looking through your website。要。

So to sum up， don't just use div。It's useful。 It's helpful。 It's like the first thing you'll go to。

 But try to use MN Web docs to find the element that best suits your needs。Alright。

 this has been our intro to H TM L， and I'll pass it on to Evan to talk about C， S S。



![](img/fe961236d062f74e5842de4dddd1e56a_33.png)

哎嗯。

![](img/fe961236d062f74e5842de4dddd1e56a_35.png)

So。C， S， S stands for cascading style sheets， and it's used for styling your browser。

 and cascading stands for sort of how the rules are applied。

 because they're applied in sort of other rules overide， Other。

 depending on the order they're written。

![](img/fe961236d062f74e5842de4dddd1e56a_37.png)

So back to the Cafe Run E website。 This is what it looks like with C S S and H T M L。

 But if you take away the C S S， then you end up with something like this。

 And you can test this out for yourself in your browser if you just go to the website and then open developer tools and you can go into the head of the H T L and delete all the style sheets。

 which are linked。

![](img/fe961236d062f74e5842de4dddd1e56a_39.png)

So back to our analogy， C， S S sort of adds a look to your skeleton that H T L gives you。



![](img/fe961236d062f74e5842de4dddd1e56a_41.png)

So here's what a basic C， S S rule set looks like。 So at the， at the top， you have your selector。

 So this lets you indicate which which H element you're trying to sell。

 This might be something like Dave or H1。 So an actual H M element。

 but it could also be something like a class or an I D， which we'll talk about in a sec。After that。

 you also have the property， which is， in this case， color。

 And this selects what property you're gonna adjust with your style。

 And then you add the actual value that you're going to adjust。So let's see what this looks like。

 if we have our H1 or if we have our heading and paragraph here and okay， we'll add one more line。

 which we'll ease later。Then if we add the div styling sheet。

 which has the color set to red and the font set to a， we see that it changes from the Serif font to。

Oh， yeah， from the seif font to。

![](img/fe961236d062f74e5842de4dddd1e56a_43.png)

The red aerial， and。

![](img/fe961236d062f74e5842de4dddd1e56a_45.png)

I have to join the zero code。

![](img/fe961236d062f74e5842de4dddd1e56a_47.png)

![](img/fe961236d062f74e5842de4dddd1e56a_48.png)

![](img/fe961236d062f74e5842de4dddd1e56a_49.png)

![](img/fe961236d062f74e5842de4dddd1e56a_50.png)

， so if you add in the style sheet of div， then you change the font and color to red aerial。Okay。

 now， if you now one more thing we can do is instead of doing the selector for div is we can do a selector for class。

 So in this case， if we create a class。 And the syntax for that is you just do a dot and then you follow up with the class name。

 Then instead of selecting all divs within the H TML document， you can select only those。

 which you indicate with the class info。 And so in this case。

 you see that only info is read an aerial， whereas paragraph is still ser and black。😊。

Another one you can use is something called an I D。 And so I D is different。

 You put in the attribute I D。 and on the CS S S side。

 you put in a hashtag to indicate that's an I D。 So in this case。

 it sort of looks like they do the exact same thing。

 But we can talk about a little bit talk a little bit about how they're different。



![](img/fe961236d062f74e5842de4dddd1e56a_52.png)

So the first thing is， if you have a given H T M L element， you can only have one I D。

 So within the I D attribute， you can only put in single I D。 whereas for classes。

 you can list out a bunch of classes spaced out。 And if you put in multiple classes like class 1。

 class 2 class 3， This can imply the style from class 1 to and 3。 whereas with an I D。

 you only get the style from the single I D。Furthermore。

 Is must be only given to a single element on the H document。

 So you can't have one div with a given I D and then another div that has the same I D to apply the same styling。

 If you want to do that， you have to use a class and you can place the class on multiple different elements。



![](img/fe961236d062f74e5842de4dddd1e56a_54.png)

And the syntax is， of course， different。 The hashtag versus the dot。

One more thing to talk about in terms of these Is and classes is sort of the hierarchy。

 So this is sort of the cascading part of the CS。 And so the lowest specificity is when we have elements and we select。

 for example， we selected the div and added styling to it and the highest specificity is when you do inline styling。

 And so that's what something called the style attribute。

 But we don't usually use it because it's bad practice。So on this hierarchy。

 we see that I that are higher than classes。 And what this means is if you have some CS code like this。

 where you have a class like info and you set the color to red。

 And then let's say you have the lower specificity div， which sets the color to blue。



![](img/fe961236d062f74e5842de4dddd1e56a_56.png)

Then the div with the class info。 Okay， wait， ignore the paragraph。 that should actually be blue。

 But the， the the div with info， which has class info takes on the color red because the class takes higher precedence over the HM element。

 And we see that the aerial font family is still applied and not on the paragraph。

 but on the info still so。😊，That's wrong， but I that。



![](img/fe961236d062f74e5842de4dddd1e56a_58.png)

Yeah， so that's the hierarchy。 We go from elements。 Then you apply your class styling。

 And then if you have an I D， the I D styling overrides any of that。



![](img/fe961236d062f74e5842de4dddd1e56a_60.png)

![](img/fe961236d062f74e5842de4dddd1e56a_61.png)

So best practice is to mainly use classes because the most flexible， you can use them。

 you can reuse them so that you don't have to rewrite your CS S S over and over again。

 And it's your highest specificity over your general element selectors。



![](img/fe961236d062f74e5842de4dddd1e56a_63.png)

Are there any questions on C， S S。

![](img/fe961236d062f74e5842de4dddd1e56a_65.png)

If not， we can briefly look at how you actually put this into your website。

 So if we go back to our hello H T M L， we have this head section。

 which is where we want to put our metadata。

![](img/fe961236d062f74e5842de4dddd1e56a_67.png)

And so that's where we link our style sheet。 So we link our style sheet style C S S that we just wrote。

 And then that'll put in the style。 So then if you want to apply any classes that we wrote within the style sheet。

 such as my class， then you can just put it in as an H TM attribute。

 And then you should get you should get everything that you want。

 And this is and you can link multiple style sheets as well。

 if you have a style sheet where you specifically focus on writing on styling fonts and then another for specifically styling how you want things ordered with respect to each other。

 you could have different style sheets to organize that。

 and then apply them all at once within the HL document。



![](img/fe961236d062f74e5842de4dddd1e56a_69.png)

So I guess in conclusion， HL is your nested boxes， and C S is your listed descriptions。

 and you put it all together to get your website。

![](img/fe961236d062f74e5842de4dddd1e56a_71.png)

any questions。嗯。If not， then you can put more feedback for this。Yeah， you put your feedback here。



![](img/fe961236d062f74e5842de4dddd1e56a_73.png)