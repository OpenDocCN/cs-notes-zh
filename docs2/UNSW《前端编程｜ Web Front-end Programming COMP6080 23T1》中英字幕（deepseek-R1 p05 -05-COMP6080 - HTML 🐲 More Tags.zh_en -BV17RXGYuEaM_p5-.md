# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p05 -05-COMP6080 - HTML 🐲 More Tags.zh_en -BV17RXGYuEaM_p5-

Hi everyone， my name is Hayden and I'm here today to talk to you about just a few more HTML tags that we didn't cover in the core HTML Funds lecture These tags aren't really that commonly used but we thought wed just spend 15 minutes to essentially elaborate on just some more obscure things out there so that you can start to get a sense that actually hey there's a lot more that we can do with HTML here。

So there's a whole list of tags that you can actually find on W3 schools。

 if you just go W3 schools HTML tags， they'll give you essentially like a full list of what HTML tags exist and there are so many here there are some that I've honestly never heard of before。

 they show you ones that used to exist， but are now deprecated， deprecated。

 meaning that they're know no longer supported， So when something is deprecated it might often still work。

 but there's no expectation that it works right So if you imagine a browser is a set of rules。

 So HTML is like a set of rules and a web browser is like a compiler and that web browser's responsibility is to go and implement those rules and if something is deprecated。

 web browsers may still choose to support it， but they aren't required to as part of the rules。

 For instance， center used to be a very popular tag and it probably still works。

 we can try it out if create like a bold hello over here and then we center it with the center tag。



![](img/ec64e713311cb0c68c4bd675da257f05_1.png)

![](img/ec64e713311cb0c68c4bd675da257f05_2.png)

![](img/ec64e713311cb0c68c4bd675da257f05_3.png)

And then I go load up my page。You'll see that it still works。

 So even though it's been deprecated browsers in this case。

 like Microsoft Edge will still support it， which is which is very good。

 But there's a few tags I want to talk about code Pre and bad head and enough foot meta abbreviation and no script。

 So firstly， code is a funny tag。

![](img/ec64e713311cb0c68c4bd675da257f05_5.png)

![](img/ec64e713311cb0c68c4bd675da257f05_6.png)

Which was， I'm not really sure on the background of it。 In fact。

 I'm not sure on the background of many of these， but code's really there。

 if you if you're building typically very simple pages and you want to actually write some codes。

 So you know， you think about some， you know， what some C code hash includes do A O dot H。

 And then you have your in main and stuff like that 0。



![](img/ec64e713311cb0c68c4bd675da257f05_8.png)

And code by itself often doesn't really do a lot。 It's often a semantic tag。

 which we're going kind of talk about more with the header na and footer。

 But what we often do with code is we actually wrap it inside of this pre tag。 Now， pre tag。



![](img/ec64e713311cb0c68c4bd675da257f05_10.png)

![](img/ec64e713311cb0c68c4bd675da257f05_11.png)

Stands for I think it's， iss a pre format？P formatted text And what that essentially means is that if you've worked with Hl a little bit。

 you'll notice that Hl doesn't care about white space。

 right Like we've kind of learned this if you make a page and you go bold hello and then you do another bowl goodbye and you put all this space between it。

 the H par and web browsers just doesn't care frankly It just will do whatever。

 It just shoves at all in the same spot。 What pre does is preessentially treats it like raw text and that also means it doesn't care about tags。

 So， for instance， if I go and put this between some pre formatatting tags。

 And now I load this up does care about tags。 but you'll see it pretty much doesn't。



![](img/ec64e713311cb0c68c4bd675da257f05_13.png)

![](img/ec64e713311cb0c68c4bd675da257f05_14.png)

![](img/ec64e713311cb0c68c4bd675da257f05_15.png)

It doesnn't care about。 So it does care about white space。 It doesn't not care about white space。

 So that's really useful for things like code， because what it means is that if we wrap our code tag inside of a pre。

Like this， our code actually starts to look like real code。 So then you might have the question。

 what happens if I get rid of the code tag。And I just have pre， what does it look like now？

Pretty similar。 So then we ask ourselves， okay， sorry about the。Cause， then if we look at like。

The HTML code tag， What does this say， code tag is used to define a piece of code on a computer。

 The content inside is displayed in the browser's default monospace font。

 So this is why it's really good to look at these references because what this is actually telling you is that the code tag displays it in a monospace font。

 Now what is a monospace font。 Well， most fonts， right。

Don't have every character as a different amount of width。

 And you can kind of see this pretty easily if I do something like a really thin letter like this。

 And then I do a really wide letter like W。 Like how many eyes are here。Like。

 let's go and replace all these eyes with Ws。Like that。 So your text editors。

 when you're doing programming， are often monospace， too， right， it makes it easier。

 really easy to code， but you'll see on web browsers。

 they're actually notice the difference like this one is more narrow， This one is not。

 But if you wrap it in code， what it's saying is that it will actually use monospace because that's how we code like that。

 So you can see the bold and stuff is still respected。 Now， pre by default。

 I'm pretty sure does monospace things anyway。嗯。So it's kind of like pre monospaces， code monospaces。

 but the pre is what actually gives you that like pre formating where it takes into account white space。

 So code just monospaces， pre both monospaces and respects whitespace。 Why do we use them together。

 That's a good question。 and I'll cover that when we talk about semantic tags because arguably you don't need to use both to display code right because you could just display code with one。

 But there are two other tags that exist。 And you kind of see this all the time。 is it tags。

 a lot of tags， particularly formatting tags are just。



![](img/ec64e713311cb0c68c4bd675da257f05_17.png)

Really what you can do with CSS， but they're just pre set。

 right You can set monospace formatting with CSS。 You can you don't need the H1 H2 H3 tag because you can just do that with CSS on a span。

 you know that these these are all presets， if you will。

 I just jump ahead and oven and foot briefly because there are these HM tags。



![](img/ec64e713311cb0c68c4bd675da257f05_19.png)

Callold header and nav and footer。 I have to look up tag because， you know。

 it can get confused with like the head tag。 But this， yeah， this is very different。 So in H Tl。

 if you have say H Tml like this and you have a head tag， We're not talking about the head tag。

 We're actually talking about a body tag called header。Like this。

 And there's a few things you actually see sometimes on sites。

 you'll see header tag and navt and a footer tag and you might like to look at these and think what do they do because if I put something here and there does it does it what pre format does it have and you can actually see that there's not really any pre format。

 you can kind of tell that there are block displays because of the fact that there's like a new line there。

 But if we look at what this is the header element represents a container for introductory content or a set of navigational links。

And you think， okay， well， what does that really mean？

 And this is where we start getting into the idea of semantic tags。

 So a semantic tag like you could this isn't a real separation。

 but you might have tags what you might call formatting tags like pre or H1 or paragraph。

 And then you have semantic tags。 And sometimes they're both which are not really they don't change the format as much as they help the browser and programmers understand the code better。

 So when you as a programmer look at this page now， you go okay， I see that there's a header。Okay。

Do we need a tag for that， Probably not， You could use HTML comments to solve that problem。

 had a start right like you could do this。That would solve your head a problem immediately。However。

 the reason that these semantic tags are useful is because they help things like Google and search engines and web browsers look for certain things。

 and you've actually seen this right if I Google， for instance， Airbnb， it might go to example。

 you see all these like login help sign up stuff here like the way that Google can look at a website。

And in fact， my company at the time of this recording， I think we screwed ours up a little bit。

 And you can actually see here。 like have a look at this。 This is like my。

 my company site is we've got these like sub pagesage here。 Google has found these。

 We haven't told Google to to use these。 Google has simply like found them and recorded them here。

 And because we haven't semantic like we haven't written this page properly。😊。

Google has just like pulled the same information for each of these pages which is kind of funny right it's like oh well。

😊，That's the same。 That's the same。 That's the same。 That's the same。

 And that's why these semantic tags matter because services like Google or something else will look for these to understand your page more。

 So if you put these in your page than scrapers and everyone else is like， I get it。

 you're creating meaning on the page。 code is also somewhat similar。

 I don't know what search engines might do with a code tag personally。

 but it's certainly a signal to programmers at the very least。 And also， it makes things easier too。

 if you， you know， if you have something like a div style here， you know。

 and you do the monospace stuff。

![](img/ec64e713311cb0c68c4bd675da257f05_21.png)

It becomes a lot easier to someone looking at it， even if you're using CSS if you use the code tag instead。

 because divs are great because of how generic they are。

 but they really don't give you much indication of what's going on。😊。

Speaking of this search result here， if you have a look at these search results and you think， oh。

 this's really interesting。 how did Google figure out what this text here is， right。

 More and more people， right， or in invest。

![](img/ec64e713311cb0c68c4bd675da257f05_23.png)

Peller is an investment platform empowering everyday people。How does Google find that， Well。

 Google actually finds that through meta tagags。 So if I look up Html Me tagag。

And I go to the W3 schools page about it。 You can see that meta defines metadata about the HTML document and it lives in the head。

 So it's essentially like it's not rendered information。

 It's information that helps scrapers and indexes learn more about your page and typically the things you'll have up here are keywords you'll have things like your fab icon I think this was covered briefly you'll have things like your description and you can see these on those pages right open this up and you'll see right here。

 meta description well organized and easy to understand I'll read over what my face is web building tutorials This is what it says and what you'll notice is when I go back to Google what is it。

It might say it here somewhere。 Oh， that's the description。Sorry。

 let's look at this again a bit more clearly。Keywords， description。

O G description offers free tutorial， reference and exercises。 So what do we see here back in Google。

'm not sure why this one isn't showing up。 but it's kind of like this is where that information is in keywords as well。

 So when when you get like Google that's like scraping stuff， it looks to that。

 it looks to a lot of the stuff Viewport image。 have you ever pasted a link into Facebook or Instagram and notice that when you paste the link。

 it actually like gives you like a preview image。 Where do you think that preview image comes from why is it always so good。

 And it's it's not good because Facebook or Instagram just says that's the perfect image。

 it's good because they actually tell it like right here on the page in one of the meta tagags。

 It's actually saying if someone goes to like paste this into Instagram or Facebook。

 then I want you to show them this image。 And if you do that to that page。

 you will see something like that too So that's what meta tagags are for。😊。



![](img/ec64e713311cb0c68c4bd675da257f05_25.png)

And then the last last few to talk about are we have an abbreviation tag。

 This one was just a really small 1。 I wanted to。

![](img/ec64e713311cb0c68c4bd675da257f05_27.png)

Show you because it's， it's not that exciting。 And it's an example of how there are many。

 many tags out there。 So if I copy this code here， this abbreviation tag。

 you can see what this abbreviation tag actually does is that it。

Has it it creates a piece of text that gets underlined and then has a pop up。 So， for instance。

 on my page here。You can see this。 if I put my mouse over WHO。

 it actually pops up World Health Organization。 Now， Ken。

 do you need this abbreviation tag to do that， No， you could kind of actually do that with， I think。

 an anchor tag and a name， Is it name or is it title， It's probably title。Yeah。

 it's definitely title。 You know， you still get that。 And then you could use CS S to。

 to underline it。 You know， text， text decoration as like underline。

 And I think there's a way to do like a dotted underline， but I can't remember。

Can't spell decoration。Yeah， you know， so you can like do it with Cs S。 But again。

 what's the point if there are these tags that make things really clear。

 And this is also really useful， too。For instance， screen readersrs。Right， like if you。

 for accessibility， which you'll， you hear about in late elections， if someone is trying to。Actually。

 look at your page。 like if， if there's a computer trying to screen read your page and most web pages have lots of links with titles on them like this one。

 right， It's got a。Let me find one。 It's probably got a title。

 A lot of links on websites have titles。A lot of modern sites probably don't do it。

Let me see what's here。Let me go to Lake， Governoror。A good friends at UNSW。Yeah。

 you got Covid 19 updates。 So you could imagine a screen reader trying to read this isn't gonna go。

Visit our Covid-19 website， Covid-19 updates for the latest on UnsW's response， because it's obvious。

 right， Like that title is not necessary。 but if you wrap it in an abbreviation tag and someone is trying to get the screen reader。

 I'm not saying this is how it works。 I'm giving I don't know。

 I'm giving an example of how it could work and why it's useful。

 that screen reader might say the W HO World health Organ was founded in 1948。

 because it knows that that's an abbreviation。 So it knows if maybe you're trying to read it out to someone who can't who has some impairments that stops them maybe being able to like put their mouse over it that you can help them out。

 So that's why all these tags are really useful。 So's also a noscript tag。

 a no script tag is what comes up if you disable jascript on a site。 So， for instance。

 if we go to the course website。Like this you'll actually see in the way let me line wrap it。

 there's often a no script。 Yeah， you'll actually see this here。 So even on the course website。

 there's actually this no script tag and the way browsers process a no script tag is that if jascript is enabled it doesn't render that。

 And if it isn't enabled it does render that。 So let me pause the video and disable ja and I'll show you。

Cool， so I'm just on on it's different on every browser。

 but I'm just going go disable JavaScript here right and now it's what happens when I try and reload still working。

ok。Clearly done it wrong， Dis job skills。大。Yeah， okay。

 so now it says you need to enable jascript to run this app。

 So this actually exists on many websites because most websites as you learn about jascript later。

 it's really critical to most websites。 Pre much everything you use runs it these days。 So it's。

 it's not that exciting tag。 And then lastly， the other 1 I wanted to show was。😊。

An embed tag because you see these a lot for things like YouTube videos and stuff。

 So if we go to a random YouTube video， quite often。

 you can embed them on your page with the embed tags。 This is not my account。

 I don't log in on on edge。 But let's find this one。

 best adventure cooking 1000 minutes food recipes。 If you go to。Share。Yeah， where is it。

Where is em bed。I might have to do it on one of my videos。

 This has changed since I last looked at it。Let me do it for one of our lectures。 Give me a sec。

Actually， I can show you something different。 So if you actually Google YouTube H L inbed。

You'll often see a code。You can find us on the YouTube page， too， but you're often。

See an embed code like this one。Right， and what you can do is you can actually copy that onto your page and just replace the YouTube code。

 There's bunch of ways you can go about this。 This is just one of them。

 So if I go find that YouTube video we were watching。Where was that？Or is it miniature food。

 else's down the bottom。 sorry， And I go and grab this code up here like that。

 And then I paste it in here。 And now we can go about to our page。 Now。

 the way that most websites work is sometimes they won't let your image。

 They won't let your video be embedded。 Sometimes they will。

 But here I can go and change the width to this to like 200 or something。 You know， refresh the page。

 and you'll see that it's a very different video。 So 120 is like a height， whatever。

 And there's the video actually embedded on the page and I can play it now。😊。

So that's an example of the embed tag。 The embed tag is a bit different from an iframe。

 An iframe kind of literally renders like a page on there。

 whereas the embed tag is more to kind of embed media content and other stuff。

 So you you would use say an eyeframe to load a whole page within a page。

 but you would use an embed to load a piece of media content within a page。



![](img/ec64e713311cb0c68c4bd675da257f05_29.png)

That's pretty much the crux of this。 There's a ton more。 you can go and read about them。

 And most of these you， you won't really come across much。

 but hopefully that gives you a bit more of a canvas of， you know。

 the breadth there is to this whole topic。 So thanks。



![](img/ec64e713311cb0c68c4bd675da257f05_31.png)