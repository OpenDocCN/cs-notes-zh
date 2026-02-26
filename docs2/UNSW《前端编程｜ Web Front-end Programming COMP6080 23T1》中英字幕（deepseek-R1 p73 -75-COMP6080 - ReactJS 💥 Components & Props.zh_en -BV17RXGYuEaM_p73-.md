# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p73 -75-COMP6080 - ReactJS 💥 Components & Props.zh_en -BV17RXGYuEaM_p73-

Yeah。Hi， everyone。 My name is Hayden， And today I'm going to be presenting a lecture on components and reusability or what you might see referred to sometimes as components and props。

 This lecture was originally written by forhar Raman， but today I'll be presenting it。

 and hopefully we will get you excited about some of the powerful things you can do with react and languages like react。

 So first thing， though， is why reusability。 So reusability is a concept。

 It tackles a fairly fundamental thing most computer scientists already understand。

 which is that we don't want to reinvent the wheel when we're programming。😊。



![](img/3e6116d87aade573294f65d0255cabd6_1.png)

bunchunch of reasons for this。 Firstly， it's much more efficient when you can reuse something that's already written。

 you don't have to write it again。 So you save time programming。

 there's a lot more consistency with what you can do because you have one source of truth and that one source of truth means that if you change it。

 it changes everywhere and things are also easier to test and debug because back to the point you have one source of truth。

 So what we're really searching for today is how do we apply these principles of reusability to reduce repetition within our front end code in particular with react。

 Now， a term you might hear or see about is the idea of component driven development。



![](img/3e6116d87aade573294f65d0255cabd6_3.png)

![](img/3e6116d87aade573294f65d0255cabd6_4.png)

Some people might see this as you know the component pattern or composition pattern or composite pattern or a whole bunch of other ways to describe it。

 but basically you know in the broad world of web and other things components are a way where you can encapsulate something in the case of front end is typically HTML tags。

 put them in a box and then reuse those boxes， you're kind of used to this idea because you already know that you can extract or like you grab common values and put them in a variable you know that you can grab common code or like processes and put them in functions。

 we're going to be doing the exact same thing here with UI components。



![](img/3e6116d87aade573294f65d0255cabd6_6.png)

In particular， Re is really well built for this because it was kind of designed as a language around the idea of componentization。

 so straight up we're going to get all of that power in react with like minimal learning minimal setup and it's all kind of done with the same JavaScript and JSX that you've probably already started to get used to。

It allows us to reuse not only the visual elements， but also the logic。



![](img/3e6116d87aade573294f65d0255cabd6_8.png)

So if we take ourselves towards a basic react component。Like this one here。

 you're probably used to really simple react components。 In fact， for the starting code here。

 we've got our little react up。

![](img/3e6116d87aade573294f65d0255cabd6_10.png)

I've got myself our app component， remember that in react quite often you'll see that you have your main app dot Js and that app dot Js。

Is itself a component， it just so happens that the entire page there。

 which is the main page of your app， that page is just a component Now this idea of components and page is getting conflated is something you get used to pretty quickly。

 but what you've probably seen when you develop things is that you might come across and maybe make a button and that button might say you know click me。



![](img/3e6116d87aade573294f65d0255cabd6_12.png)

What you would have seen or we might have explored in the live lecture is when you have a button like that what you can actually do is instead of just thinking about this file as one page in one component。

 we can actually create multiple component in that file if we'd like to so I can come along here and say I'm going create a function called my button I know functions a bit of a weird way to describe a component。

 but it's basically just using the syntax that already exists in jascript。

 if you could create a new word in the syntax call component that that would be fine。

 but that's not how it works。 and every component in react is just a function that returns some HTML or more specifically JSx in the end。

 So for instance， here I have a my button and what I can do is I can actually go and take this HTML JSx code here。

 and I can go and have my button return that。 Now the brackets here aren't required。

 you can kind of avoid them。 I like them， I think it makes the code a little bit cleaner and then inside my app component。

I can now do this。 I can now write my button。And what's cool about this is I've now taken some code。

 turned it into its own component， and now I can reuse that。

 I can simply copy and paste it and then back to the reusability common source of truth when I update that component。

All of the usages I it update。 So this is very， this is very useful because I can avoid repetition everywhere in my code now。

 and it also means when I want to do more interesting things like say， you know。

 have all my buttons disabled， I can just do it in one place。😊。



![](img/3e6116d87aade573294f65d0255cabd6_14.png)

So that's the basic idea of extracting you know JSX into a component and as you've seen there we reuse that a couple of times。



![](img/3e6116d87aade573294f65d0255cabd6_16.png)

![](img/3e6116d87aade573294f65d0255cabd6_17.png)

Now， while that's all well and good。There's a question that comes up。Which is。

Won't my components not always have the same text in U I。 What happens if say， you know。

 the text or certain stylistic elements of this my button will change， you know。

 in different use cases， for example， you know， you might have a button that is disabled。

 for instance， or a button that's not disabled or it might have different text。

 And the answer is that。When this kind of componentization was designed。

 there was an awareness the different UIs have different needs。And to get around that。

 react has a mechanism which we call props。And props are an ability to customize react components when they're created with different parameters。

 And it's really the same concept as a function。 We're kind of going back to the basics of programming here。

 When you first learn functions， you know that you can pass in different different properties。

 different parameters， different arguments， however you want to refer to it into them。

 and we can do the exact same thing here。 Now， what's interesting and different about react， though。

 is the way that we pass things in， takes a minute to get your head around。 Now。

 whenever you create your own component and react。 the way to approach it is to say my button。

 my component takes in one parameter， and that is the object props。

 this object will have a ton of stuff in it。 Now， if I console log this object。😊。



![](img/3e6116d87aade573294f65d0255cabd6_19.png)

![](img/3e6116d87aade573294f65d0255cabd6_20.png)

Which is a good starting point。In fact， I'll just reduce my button to one button for now。

Let's open up the console。What do I see in the console。I can see here that it's empty。

 That makes sense because my， whilst I'm trying to capture these props or properties。

 that's what props stands for。 I'm not actually passing anything into it。 Now。

 what the props object is populated by。Is is quite a simple set of rules。

 It's kind of the equivalent of HTML attributes。 So if I come here and I say my button name equals Hayden。

Age equals three and I save that perhaps actually are now kinds those kind of HTML attribute and value pairs packaged up into a JavaScript object like you can see up here in the console。

And why that's handy is that I can do something now， for instance。

 to say my button text equals Hayden。 And then when I want to replace the click me now with that text。

 I can just say props dot text。 So all of those things that I'm passing in a kind of bunched into that props property。

 You know， I could also do something like， say width equals you know，50。 And then here I could say。

 well， my button style is going to be with。Props dot width。

 sometimes you need to put text in here to like add the pixels。 It depends on the scenario。

 reacts pretty fine with that。 So now I can control the width of it， for instance， pretty handy。

 this kind of ability to then reuse things and， you know。

 say I use my last name and I make that one slightly smaller。

 This is great because now we have that exact same component that we reuse。

 And if you want to kind of increase the height of all those components at 50 pixels here。

 We can do that in one spot。😊，This is also an important lesson in how to use jascript you'll see in later lectures that well learn more about CSS frameworks。

 which are the right way to do things。 So if you kind of think oh。

 I have this style that I want to apply to many components quite often you'll find that those many components that you have can just be abstracted into kind of parent component like this like oh my buttons have all the same height Well you know you can even forgo style sheet sometimes and simply apply the style here to the button directly because now you've gotten you know a similar benefit to what you get with style sheets in general I'm going go and clean up the alignment of this a little bit。

 I'll show you kind of how you generally write this obviously you have auto formats are pretty easy but this is how I would generally see a lot of react stuff written something like that that's kind of just a bit more readable given how things are broken up。

🤧嗯。So that's one interesting thing about props。 The second way that sometimes people approach things is if you pass in a couple of parameters like text and width。

You can actually kind of clean up your code by pulling them out directly。

 say this is what we call destructuring where I say okay。

 there's my props width and text like this and now I don't need that prop dot part because I kind of already pulled them out。

 and then you'll see some people will take it even further which I generally recommend if your component only has one。

2，3 or four props where you go and you take that destructure and instead having to write this explicit line here where you say you know width and text is equal to props I grab that and I come here and I paste it there and now for someone using my component。

 they don't just see this props variable， they kind of see immediately that yes。

 there is still only one parameter for this component or function but that is an object that contains a width and a text key and I'm going to use that and I like this approach because it helps you easily see what that component takes in right off the bat So that's quite nice。

 the other thing you can do is that。😊，What you'll see is if I might just unwind that for a second if I console log props again。

呃。If you're thinking and a couple of you will be thinking， what happens if I。

 instead of using this void tag approach here， I instead just put something in here like， you know。

P emoji and my button， I treat it like kind of a， you know， an open close HTML element。

 And I save that。 And what you'll see now is that。That particular element actually has a third props added called children。

 And this is how reacts design。 So every everything you put in between the square brackets。

 So everything you encapsulate within the tag is immediately passed into your component as a dot children object。

 This is really handy because sometimes you want to reuse kind of classic HTML semantics such as with a button。

 you know that the text of a button exists between the two tags， So instead of saying text now。

 I can grab this and go and put it。 Well should't have done that。 go and put it here。

 So we now just say， you know， Hayden Smith like this。

And this reads a little bit more familiar to some people。 So now instead of using text。

 I can just use children， it's always children， children is what the name is to the things between the bracket。

 So again， suddenly we're expanding what our function can do。

 Now what if I want that button to also be disabled。 Well， if I just put disabled here。

 nothing's going to happen Because whilst that disabled is passed in as a props element。

We're not doing anything with it。 So one other hack you can do when you're creating components is that if you know that。

They're a particular attribute。 Like， this is really helpful if you're wrapping a basic component。

 is what I can do is my button has this particular style here， right？ But if I do dot， dot。

 dot props。If you're not show what the spread operator is you might need to Google it。

 I won't go into it in this lecture because we probably covered it somewhere else， but in JavaScript。

 there's a spread operator that's basically a way to kind of inject a list of things into something。

 So what I'm really saying here is that I've got all of these props in an array。

 I now need to take them and expand them out basically you know it's kind of like a way of saying if I have you know ABC you know ABC equals D here take all of these。

And pop them here。 So it's like now it's， it's populated like that。 So it's。

 it's just a way of just passing something along。 But the benefit of this is anything that I add here will come through as props。

Which what it will try and do is add anything I pass in immediately as an attribute to the underlying button。

 it's basically a way of just creating like a generic pass through。



![](img/3e6116d87aade573294f65d0255cabd6_22.png)

嗯。出屎。Got the problem there。 So oh， no， unexpected token。



![](img/3e6116d87aade573294f65d0255cabd6_24.png)

There we go For the brackets If you don't have that the JSX is like what the hell is three dots So you need to put it like that and why this is useful is that now any normal attribute that you pass in such as disabled will just kind of like funnel through to it。

Or， you know， what are other button properties Well type equals submit， for instance， you know。

 that one where you click on it， I don't sorry that's not it。 But equals button。

All these other kinds of things you can pass in。Now， when would you not want to do that， Well。

 you would not want to do that in cases where you actually don't want people to be able to pass things through。

 I rarely will see this used unless you're kind of doing like a benign wrappper。

 A really simple example might be like， let's imagine that you want to create a。Also， a link。

 but you want to call this like， you know， a UnSW A tag or something。 So， you know， UnSW A tag。

We want to go to Google and we have Google here， but you know what you actually want to do with this new component you're creating。

 which I call you know UNSWA， is that every time someone clicks on that link。You will return。

 you know， a graph equals。You know， prop do H F， you know， where it's like prop stop children。

 You get the point。And a， but you want to be sneaky。

 you want to say every time someone clicks on the link。

 I actually want to reroute them through like a third party service， right， like so I'll go and say。

 well， the where I'm sending them is actually to， you know， redirect dot com via URL equals。

The you know， props af or something like that， you know， So in this particular case now。

 I've kind of created this。 So now all of my tags， and I'm sorry for missing this one down here。

 all of my tags will have that exact same behavior。 But in this case。

 I want my my anchor tag to have all the same attributes。

 I don't want someone to have to go and remember what it is。

 So this is a good example where I'd probably just go and put dot dot dot props here。

 because that dot dot props means anyone who uses this can pass an whole bunch of other stuff like。

 you know， title equals Google without having for me as the component per。

 other the titles coming up now， me as the component person to have to go and define each of those attributes。

 But in cases where you're creating something quite custom， it's not that common。

 I would encourage you not to use the dot dot dot props unless you're actually like， yeah。

 this is a really common component that I expect everyone to use all the time and pass through lots and lots of stuff。

So yeahep， there's just some fun examples of props that we've seen so far。



![](img/3e6116d87aade573294f65d0255cabd6_26.png)

Most of what you'll see in the slides here is just demonstrating different ways to use it。

 There's there's a note here that's kind of important。

 which is that you should treat your components right and react kind of demands this as what you call pure functions and a pure function is something that basically doesn't have a side effect。

 So if you create a function that takes into parameters it should return something new。

 It shouldn't modify those original parameters。 it shouldn't have a weird side effect。

 It should be completely in a vacuum that's in general just good programming practice in terms of how to write functions always。



![](img/3e6116d87aade573294f65d0255cabd6_28.png)

![](img/3e6116d87aade573294f65d0255cabd6_29.png)

And then we'll finish before we we do another couple of examples to tide it off with other types of components。

 Now， there are three here that have been categorized in the slides which are we've kind of seen them in their own way。

 The first one is a dummy or dumb or stateless component。

 These are basically components that don't have props。

 They're things like what we saw at the start where we just had a button that just said click here these are often super useful I think for thing you know。

 you'll see there's used a lot for things like icons you know。

 because like you might have a particular component that's just， you know， say。Your smiley face。

For instance， but just like returnstans。That。I mean， that's not really。I don't really do that much。

 But like， you know， now you can just put in smiley face here。

 So you have like one common source of truth as to what a smiley face is。

 That's a dumb or stateless component。 Then you've got presentational components。

 which are a lot of what we've been looking at here。 It's basically components with props。

 And then you have container components， which。

![](img/3e6116d87aade573294f65d0255cabd6_31.png)

![](img/3e6116d87aade573294f65d0255cabd6_32.png)

啊 you know。These ones， I don't really love the definition of this。

 but what I'd probably more so say is to think about some of what we're seeing with like you know the UNSW anchor as you know containers or wrapper components you might also see used in other scenarios。

 but these aren't really formal definitions that'll will kind of impact your day。

 It's more like a way of understanding。 well， sometimes we've got these like totally new components we create that are super presentation or with props and very variable。

 sometimes we'll have other components that are dumb or stateless。

 sometimes we'll have raper components。 remember， props doesn't just have to be values anyway。

 a really common way to use components that you've probably seen and we kind of glossed over here as well。

 with the button， what happens if you want someone to be able when they click it something to happen。

 Well， you know that the button will have some kind of onclick。

 So I'm going write this out more explicitly。 Let's say that we have an onclick props。

 and you generally want to reuse the same semantic like onclick。

 So now I've got my say this bottom button that says Smith。



![](img/3e6116d87aade573294f65d0255cabd6_34.png)

I go and， you know， clean up the code very slightly。 Well。

 I want to add an on click to that where I'm going to call a function that I wrote and that function is just going to say alert。

 hey。So now I want to refresh that page。That should work。

Hey like that right and you can see here when you look at the console log we have the props of width value children value and then oncl oncl F where F is a function you can't see a lot of how that function works here because that's not what the console is about but you can still pass a function through。

 which is what matters。Now the final thing about components is about layout and structure。

 so a general rule of programming and Re is that we don't have more than one component per file。Okay。

 what we often try and do is come along here and make ourselves a folder which we might call components。

 for instance， and then we actually go and put our components inside that folder with like the name of the component as the file。

So now I've got my components folder and you can see I've got three components here。

 which is smilemiyface My button and UnSW anchor。 So when I go and grab Smiy face here。

 I might say go into I shouldn't have saved that so soon。

 I'll go and create a new file here called Smiy face， right？



![](img/3e6116d87aade573294f65d0255cabd6_36.png)

And usually you give it the exact same name as the actual component。

 and you'll include it there like this。 You'll also need to export this particular。Function。

 you can do a default export or a normal export。 I think it's pretty normal to have a default export when when you're dealing with components because in theory。

 one file， one component， it should just certainly export one thing。 And then we go and include that。

 We say well， import smiley face from you know， components slash smiley face like this。

 Okay that still works。 And then we go do the exact same thing for these two things as well。

 So I go and make another file inside the components。



![](img/3e6116d87aade573294f65d0255cabd6_38.png)

![](img/3e6116d87aade573294f65d0255cabd6_39.png)

![](img/3e6116d87aade573294f65d0255cabd6_40.png)

This one is called UNSWA dot Js， pretty simple， cool， easy。 I need to export。

 default that one as well。get rid of that now。And you can kind of see where this goes right。 is like。

 you know， I've got my U W A， And then I'll do while I'm here my my button。



![](img/3e6116d87aade573294f65d0255cabd6_42.png)

I'm going I take that。

![](img/3e6116d87aade573294f65d0255cabd6_44.png)

And then， export that one to。My button gott J S inside here。



![](img/3e6116d87aade573294f65d0255cabd6_46.png)

Done go and export， default that。

![](img/3e6116d87aade573294f65d0255cabd6_48.png)

Easy done。 So this is， that's components and props。 I break up my code into components。

 Those components can be variable based on properties that I enter。 and then from there， I go and。😊。

I go and super easily just like。Component folder 1，2，3， include， include， include。

 And then I can go and include those in other files。

 And I can go and create components from components。 You know。

 something we probably didn't touch on much was that this is a multileve thing。

 You can come into your my button thing and say import smiley face from smiley face， for instance。

 and you can just go and include a smiley face at the end of every single button you have。 So。

 you know， components can live within components， right。

 You can have components or components or components or components。 There's no limit to it。

 But hopefully that gets your started。😊，Good luck。 Have fun。 It's a great way to code。

 It makes your everything much， much easier， particularly compared to older school styles of Javascript。

😊。

![](img/3e6116d87aade573294f65d0255cabd6_50.png)