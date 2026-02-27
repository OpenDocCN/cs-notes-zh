# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p18 -18-COMP6080 - Dev Tools.zh_en -BV17RXGYuEaM_p18-

Hi everyone。 My name is Hayden and today we're going to be talking about devtool in particular。

 the devtool in Google Chrome， though this applies for many browsers and you can transfer the skills。

 these lecture slides were prepared by Markrovviitch at Canva but today I'll be taking you through some of the content。

 Now devtool are a way that we can debug prototype and analyze pages。

 If you've worked in programming languages like C before you might be familiar with GDP。

 It's a kind of debugger。 It helps you go really deep and understand things in a lot of detail and dev Tool is kind of like that except it's significantly more powerful than probably any debugger you're likely to have come across with the kind of programming background you'd have at this point。

It's really exciting。 It's one of those things that you it reminds me of like you playing piano or something。

 It's like it's really easy to do something basic and get some value from it。

 but you can spend years mastering the benefits of it or you know honing your skills and there's always so much to learn。

 but let's firstly just start playing with it。 I've got some code here from a previous lecture where we did some layouts and you'll see that it looks this is our old。

 don't forget to sign up chaotic CSs layouts page。 One of the first things we're gonna do is open dev toolsol Now opening dev toolsol is different on different machines generally you can open it one of two ways。

 which is either with a keyboard shortcut or by right clicking and clicking inspect or inspect element or something similar。

 And this opens up dev tools I can also press F12 on this Windows computer it's different in different computers。

 Now I'm gonna make our code a little bit smaller in this case today just so we can see the extra space。

 but now I've opened up dev tools。

![](img/8db844303b7ade041ef7d8ad285175cb_1.png)

![](img/8db844303b7ade041ef7d8ad285175cb_2.png)

![](img/8db844303b7ade041ef7d8ad285175cb_3.png)

![](img/8db844303b7ade041ef7d8ad285175cb_4.png)

![](img/8db844303b7ade041ef7d8ad285175cb_5.png)

The first thing you're gonna want to look at in devtools is the elements tab and it's where we're gonna spend most of today。

 The elements tab is where you can essentially see all of the elements on the web page。

 all the raw source code and kind of break it down and you'll see just as I move my mouse over this the browser is smart enough to highlight those particular sections and I can click on it to move through it with you know with my fingers here so I can see okay well there's a big you know there's the outer box and I'm just I can expand and retract there's my inner left。

 my inner my inner right is kind of hidden my inner left is there there's my right hand bar my inner left has all this text inside of it you can see the text overflows you can look through this as much as you want and it helps you analyze the different parts of this you will also see that you don't have to kind of go and find everything through this little box here you can actually click on elements and click inspect and that will take you straight to the element in。



![](img/8db844303b7ade041ef7d8ad285175cb_7.png)

that took me straight to the pop up or if I right click on this and click inspect that takes me straight to that inner left class div so that's what this select element is for it allows you to。



![](img/8db844303b7ade041ef7d8ad285175cb_9.png)

Go deeper on some things。 but let's keep moving。 So in terms of analyzing it。

 you can do lots of analysis， but one of the more fun things you can do is you can actually edit the page straight from the dev tools on the right hand side here So for instance。

 I can go and double click on this text and I can change it to just say how you and press enter and it will go and update the web page。



![](img/8db844303b7ade041ef7d8ad285175cb_11.png)

Like this。 I can also go and add and delete things。 For instance， I can find this element。

 I can right click on it， and I can actually go duplicate element。

 which will create two of them in this case that you can't really tell the difference because they're over each other。

 but I can also delete it by clicking delete element。 And when I delete element， it will。😊，You know。

Bump it round like that。 I can also rearrange things by。呃。

In this case duplicate might work so you can see more clearly there what duplicate does that's pretty easy if you don't want to duplicate you can simply click and drag something so I can click and drag this down here it's hidden now。

😊，It'sVery hidden to get it outside of this div。There we go。There's my blue element there。

 It's way down the bottom there。 I've just dragged it down to a different part of the page。

 I can edit the styles of this。 I can make it longer if I'd like to 300 pixels， 400 pixels。

 I could go and add more HTML inside of it if I wanted to you can make it invisible。

 you can hide the element， which will hide it from the page。

 That's kind of like visibility hidden you can make it visible again so you can really edit that dom there's a fun little hack if you want to where if you actually come up to the HTML tag at the top。

 you can actually double click on that and if you add。😊。



![](img/8db844303b7ade041ef7d8ad285175cb_13.png)

![](img/8db844303b7ade041ef7d8ad285175cb_14.png)

It's not letting me edit it。 edit as H T M L。 If you actually add， I think it's。

Content editable to that。 If you just add that to your page， then browsers are actually quite。

Smart and what they'll be able to do is they will be able to， I' say， just save this。Good。

 you can actually now go and change the text on the page。

Which is crazy so this is like a really easy like you know gooey way to change the page hello there and if you remove it。

 then naturally you can't edit the page anymore。😊。

![](img/8db844303b7ade041ef7d8ad285175cb_16.png)

So lots of little fun ways to edit things。 You can also force the state on certain elements。

 So let's say， for instance， that on this page， we might go and add a a link。



![](img/8db844303b7ade041ef7d8ad285175cb_18.png)

To I have to refresh the page here， it'll go back every time you refresh the page。

 it goes back normal。 But let's say you add a link here to Google again。 So when I click。

 don't forget to sign up， I get taken to Google。Now obviously when I put my mouse over that at the moment。

 nothing interesting happens， so you know maybe I need to add a style there and say hey。

 for the pop up， if you see an A as a child of it， I would like the hover of the A that's a child of it to have no underline。

So now when I move my mouse over there's no underline and what the slides are showing us is that we can actually go and take an element like this。

 we can right click on it and we can force the ho state。

So this is really handy for kind of development reasons if you want to be able to see what that is maybe some things are hard to hover over。

 maybe there's links you don't want to click on， maybe you know active visited focus。

 you can focus particular forms you can kind of manipulate reality as much as you want you know it's really like editing the matrix in a lot of ways So forstate is pretty useful I' mainly use that for I think focus hovers I often just do myself but focus is really handy to play around with most of what we've seen so far has been editing the actual HTML。



![](img/8db844303b7ade041ef7d8ad285175cb_20.png)

![](img/8db844303b7ade041ef7d8ad285175cb_21.png)

Up here， but。A lot of the exciting interesting parts are actually down the bottom here in what we call you know the Sts tab and the Sts tab is for any given element like that link。

 I can actually go and see all of the styles that have been declared on that。😊，嗯。Like this one。

 like the one we just wrote。 So this is saying that this particular anchor tag， the link。

 it has text decoration none， and this is the definition that it came from。

 and it tells me where it was defined。 in this case。

 it says inside a style tag And if I click on that it'll actually take me to where in the source code that was defined So really。

 really versatile I can do things like if I right click on that it'll show me what kind of the underlying styles are because remember how we said before there's like these kind of compound styles where instead of writing background left background right。

 we can just say background。 we can do the exact same thing with text decoration text decorations is actually a series of smaller or like more nuanced or more specific styles so we can actually see how that happened we can turn it on and off。

😊，Like this so you can turn it on and off， you can add more styles to it where you say you know what when someone's hovering actually want it to be white。

So you can add things there， you can click on that and you'll get a color picker where you can go and find the relevant hex value。

😊，Like this so you can go and really play around with it if you'd like to。

 So really really powerful And you can also see here that the original pop up these are all the styles that it inherited so we could turn some of these on or off if we wanted to you can also see it shows you in cases where a style has been overwritten So the popup had a color of white but we've gone added another color in a higher specificity definition for the color green。

 So it's showing you here that it's kind of been overwritten which is which is really helpful and cool so。

😊。

![](img/8db844303b7ade041ef7d8ad285175cb_23.png)

That styles tab is， is crazy powerful。 It's probably the most common reason I'd use dev tools is just to play around with styles there。

 It saves you having to。You know， you can kind of， you can kind of tweak and manipulate a website in dev tools rather than having to update your code and refresh the page。

 which is really great right next to the Sts tab is the computed Sts tab。

 The computed Sts tab is more focused on what is actually rendered。

 So think of styles as kind of what you defined or what's defined and computed is how the。😊。



![](img/8db844303b7ade041ef7d8ad285175cb_25.png)

The web browser takes that and then generates it。 So for instance。

 there's a cursor pointer for this a element here。 Cursor pointer is how that mouse changes from the little arrow to the little hand and that cursor pointer we didn't define it。

 It's just saying that the browser has said it's a link therefore I'm going to apply that style。

 You'll see there sometimes quite a lot of compute styles。

 If I go show all it will literally show you every CSS property that exists because nearly all these CSS properties have defaults like。

The font always has a weight， which is normal， and it's always just default， say 400。

 which is just normal， or it's not bold lighting color， margin left， margin， right， margin top。

 These things have to have value。 So this is really useful when you want to go really deeper。

 Say something doesn't make sense。 And you're like， I didn't apply a margin there。

 But it looks like there's a margin。 So you can go look at the computed styles and see if there's a margin。

 And if there's a margin。 you go， okay， so Css is populating this for me。

 Now I can debug this further。 So that's what the computed styles tab is for。



![](img/8db844303b7ade041ef7d8ad285175cb_27.png)

Name value hints。 we kind of saw this when I was like editing things。 you know。

 if you type in and it'll like show you all the different CSsS properties and then for each CSsS property。

 itll give you all the options you can have So just to like show you that again if I have my pop up a hover here and I say background。

 I can see that there's background color and then it'll give me all the Burleley would how beautiful the burley wood background color So the tool itself will give you lots of property hints and value So you didn't even need to Google stuff because the browser knows all the Css right it knows everything So you can just use the browser to your advantage element state。

 we've really kind of talked about that except previously we kind of right clicked on things but you know in some cases you don't need to right click on it you can。

😊。

![](img/8db844303b7ade041ef7d8ad285175cb_29.png)

![](img/8db844303b7ade041ef7d8ad285175cb_30.png)

![](img/8db844303b7ade041ef7d8ad285175cb_31.png)

Fce it down here so I can either right click on it here or I could kind of turn it on and off here as well if I'd like to There's so many buttons。

 you know， like you just can play around with this thing and get lost forever。 We've seen colors。

 you can set box shadows dynamically。 So remember in the CSS formatting lecture。

 we talked about box shadows and talked about how kind of interesting and complicated they are。 Well。

 let's go and take our pop up。 What happens if we want to add an inline style。

 This is the equivalent of adding it to style equals。 you know， of like box shadow you know。

 one pixelix one pixelix one pixelix gray。

![](img/8db844303b7ade041ef7d8ad285175cb_33.png)

![](img/8db844303b7ade041ef7d8ad285175cb_34.png)

You know but like that doesn't mean a lot so what if I click on this now we can start playing around with the shadow。

 we can move the shadow around， we can increase the spread of the shadow or the blur of the shadow。😊。

Like that。You know there' there's a lot we can tweak， we could you know make the blur really big。

 the spread pretty small， we could then go and change the color to maybe something， you know。

 really gentle， we could make the color pretty transparent too。So it's very， you know。

 like and it's crazy like how easy was that， that was much easier than kind of hand programming some of these things and you'll find more and more and more and I discover more all the time。

😊。

![](img/8db844303b7ade041ef7d8ad285175cb_36.png)

![](img/8db844303b7ade041ef7d8ad285175cb_37.png)

Now you can also see the changes you've made if you come up the top here and you go to more tools and changes now in this case。

 this usually works a little better when you kind of modify a separate file I' probably made a small mistake here。

 but this is kind of if you've lost track of all the changes you've made you can get a little summary list there's other tabs here like rendering So for instance here you know there's all these options like disable local fonts。

 disables local sources in font face。You know， emulate CSS media types so you can emulate like what happens if a printer tries to load the page because in the past you used to be able to set CSS for a printer and just for a user on a screen。

That's how some pages print differently to how they look， particularly pages that are printed a lot。

 you know， like maybe booking confirmation pages look much nicer。

 but they don't get printed that way to save on innc。

 It's just like this endless pit of things you can do now there's more tabs here on in the dev toolsol but most of what you're gonna to be focused on with CSS is the elements。

 but just as a quick point console is going to be where we can debug a lot of jascript sources don't really use a ton this is fairly complicated So I wouldn't worry too much about that network is really useful later in the course。

 you can actually see all the kind of pages that are needed to load it in this case our page on HTML is just one page。

 but if you're importing files this becomes really useful because you can see the page that you've requested you can see how it went。

 you can see the URL you can see the response It gives you the source code that was loaded。

 this is really really useful。Lighthouse is a SEO tool really great for determining if your website's good we're going to chat about that later application is also pretty useful because this is where we can see things like cookies and local storage which you'll learn about soon case storage notification it's just endless right payment。

😊，What is I've never even looked at this one right。

 payment handler push messaging like it just keeps going。

 So don't be overwhelmed go and play around in your own time。

 but mostly get comfortable with this elements tab because that elements tab is where you can see everything。

 not just the compute styles， the the raw styles。oops。We've got， you know， animations。Like。

 it's just never ending， right， which is a good thing。 I'm sure， I'm sure that's fun。 And look。

 even here， before we wrap up， you can see that each element it'll show us。

 that's the size of the element。 That's the padding 10 pixels at the top。 There's no board。

 There's no margin。 And then here is the， what's the outside here。😊。

We can make that slightly bigger for you， the position， you know the position on the page。

 that's the position fixed setting it and you'll notice that as the page re sizes those numbers change because they're computed in real time so。

😊，Yeah， keep exploring， keep having fun， hopefully that's a good starting point for you。😊。

Definitely use the element tab to debug your work because you'll find it so much easier than just changing values。

 hoping that you can figure things out。 Good luck。😊。



![](img/8db844303b7ade041ef7d8ad285175cb_39.png)