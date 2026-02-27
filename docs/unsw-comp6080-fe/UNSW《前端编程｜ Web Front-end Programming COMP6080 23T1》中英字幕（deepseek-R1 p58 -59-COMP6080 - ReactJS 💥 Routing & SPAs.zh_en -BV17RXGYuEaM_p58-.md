# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p58 -59-COMP6080 - ReactJS 💥 Routing & SPAs.zh_en -BV17RXGYuEaM_p58-

Hi everyone， My name is Hayden and today we're going to be learning about react JS routing and single page apps。

 The essence of this lecture is trying to solve a problem that you might have come across so far。

 which is how exactly do I have a like a multi page website because when you think of a website you probably think of something where when you navigate there and let me just use you know UNSW as an example。

 you've got a URL and then you've got another page and all these different things they change what's in the URL。



![](img/675820c374322e95a93a1a38bccfbf32_1.png)

You know， in this case iss a little bit different， but you see here slash researcher。

 and then when you click on someone's name， you get slash something else。

 So how do we solve for that where we can create a react app that essentially has kind of like a different page for those different sections。

 And the answer to that is we're going to look at a particular react Js library。

 which is called react router Dom It's a very popular library and is pretty much the standard one used with react Js and the purpose of it is to allow us to associate particular components as in react Js components with particular URL routes。



![](img/675820c374322e95a93a1a38bccfbf32_3.png)

It's able to let us link between routes without requiring a full refresh This is something that kind of classical websites even like the UNSW site don't do you'll notice that every time I click on a new link the page does a full refresh you can tell because of this little loading bar up here up the top so that whole page is being refreshed every single time。



![](img/675820c374322e95a93a1a38bccfbf32_5.png)

![](img/675820c374322e95a93a1a38bccfbf32_6.png)

![](img/675820c374322e95a93a1a38bccfbf32_7.png)

You can see it doing that。 So that's the second thing because sure。

 we can build things to just be on different pages。

 but how do we link to them without causing that refresh And the third thing is how do we capture wildcard in the URL and load things dynamically and a really good example of this right would be pages like this one where we have say all these different events and all these different events have different URLs but these pages would be generated dynamically Someone out there doesn't have a single react js component for every single event right。

 they don't have like a whole separate file， They have one file that takes in the same ish URL but with different string。

 So how do we capture that information and dynamically render the page they're the three questions we want to answer and we're going to answer them by using the react route or dom library So what I've done just to prepare this lecture is I've gone to run create reactor to generate a new react up here I've got it right here and what I'm。



![](img/675820c374322e95a93a1a38bccfbf32_9.png)

![](img/675820c374322e95a93a1a38bccfbf32_10.png)

![](img/675820c374322e95a93a1a38bccfbf32_11.png)

Going to be doing is。嗯。Loading these files up， installing reactor routeuterdom and showing you what we can do with it。

So here I've got a folder called reactact routing Ss and inside that folder you can actually see that I've got my basic reactor here。

 So what I'm gonna to do is well let me change the syntax just so that you know it looks okay what I'm going to be doing here react is I'm going start up this reactor so that we can start fiddling with it that's going to open up a new app in the browser here and now we want to try and create a couple of pages So how would we create a couple of those pages Well let's start simple let's try and create。

 for instance， for us just a home page and an about page and maybe a profile page and we'll try and expand this idea where profile pages can be multiple different people's profiles So the first thing we're going do when we work with react router dom is I would usually recommend you go to their website Now this library maybe superseded in a year or two or three by another。



![](img/675820c374322e95a93a1a38bccfbf32_13.png)

![](img/675820c374322e95a93a1a38bccfbf32_14.png)

Type of dependency， but at the moment it's pretty strong， right。

 it's doing 7 million downloads a week。 So there's a getting started guide which you can find here and they'll usually tell you。

 you know you have to well create your react app。 this is for a tutorial but。

Then they'll also tell you kind of what to install。

 So here I can see the NPm module that I would like to install， which is react router dom。 Now。

 one thing that's tricky at the time of this recording in early 2022 is that react router dom is currently at version 6。

 and that version was a massive upgrade from the previous version version 5。

 So you have to be very careful about this because coding in version 6。

Is very different for what you were doing in previous version。 So I'm going go and stop my react app。

 Im gonna installr do react router Dom。 I don't think you need the out 6。

 I think it will install version 6。嗯。Then I'll start up my react app again。



![](img/675820c374322e95a93a1a38bccfbf32_16.png)

Great。And then I'll load it up。 And now we can actually， you know， start using it。

 So let's have a look。 Let's scroll through here and let's look for something that's interesting。

 This is what you're looking for。 So here is kind of your like main page。

 So what I'm going to do is I'm going go and get rid of all this stuff here， All the default things。

 and I'm going to copy and paste from here， this browser router。

 So if you remember back to what I wrote on the。

![](img/675820c374322e95a93a1a38bccfbf32_18.png)

The very short lecture notes， you remember that I said the first thing we're trying to do is associate particular components with particular routes。



![](img/675820c374322e95a93a1a38bccfbf32_20.png)

![](img/675820c374322e95a93a1a38bccfbf32_21.png)

So what I mean by that is that what I want to be able to say here and let me just make this a bit bigger so you can see it under my head is that I want to be able to say well the default route here should take me to a particular component and then I want another route which I might say is like slash about to take me to another component。

And then I can create another route called slash profile。

 which I want to take me to another component。 So now what I can do here is like go and define those three components at the top。

 Now， normally you might go define these in separate files。

 But just to keep things really simple to start， I'll define them all at the top。

 I might call this component here home。This component here， profile， obviously。

 if you haven't seen the components and props lecture， that's kind of a prerequisite here。

 And now we'll go and start creating those components。 So I say， well， my home component。

 it can just return D of home。 So let's keep these components really simple just to demonstrate the principles。

 I'll have my second component here， which can be about， which can just return about。

 and then I'll have my third component， which can be profile， which can show profile there。 Now。

 when I go back here， you'll see that its go call。😊。

It's going to complain about something not being implemented once I fix up a couple of my syntax errors。

 it says all these things aren't defined and that makes sense because these three types。

 browser router routes and route are all defined in the react router dom library。

 so I have to import those three things。Now， this will make my page work now。

So you can see here I've got home so what's actually happening here is that this main component in react is loading。

 but this browser router component is able to figure out what to render and it will look through all of the routes here and decide what to render and because this is forward slash is in the default URL it rendering home but if I navigate to slash about you can see the page still is about and if I navigate to slash profile I now get this on profile。

😊，Now， where this stuff gets a little bit more interesting is how to link between those pages。

 So what happens if you want to have some kind of common header bar， for instance。

 right I want to have some header bar up the top。 Well， let's try and make one。

 What you don't want to do is put any components inside this browser router tag。

 Everything inside of here is essentially react route or dom structure。

 If you want to create a component that goes above all of these things。 Well。

 you can do that a few ways。 One ways is you could go and create a component inside all of these so that each of these home about and profile components all have like a nav bar like using a proper compositional approach。

 But that sounds like we have to write the same thing out a few times。

 So maybe let's try another approach。 let's try and actually just put a nabar element here。

 right I'll just call this nav and let's see if it renders on the page。

 So before I actually figure out what I want to render on my page， I can have an approach like that。

 So now what you can see in terms of how this works。 is。

React is just simply loading this component and all the browser router is doing is choosing which of these to render and which of these to not。

So it's， it's essentially like a conditional rendering mechanism。

 So this is always rendering because it's in all of them。

Now I mentioned that you could actually take this like， in fact。

 I'll break this out into another component for you called Nav。I'll just go and break this out here。

 I mentioned before too that instead of putting nabs， say in your main app like this。

 that you could actually go and put it inside of these three components right。

 so I could actually do something like thisv。And I could remove it here。

 And now it's gonna be inside all three components。 You might be thinking， oh。

 this seems like a worse solution because I am repeating myself now that is partially true。

 but the advantage of this approach is that now each component is able to decide whether it wants to render the nav or not。

 And this is particularly useful when dealing with things like or or pages that simply just don't always display things。

 A really good example of this is on the course website we have certain pages that display this subnav component at the top here。

 like lecture content and tutorials and assignments and resources in or not installation。

 but some pages don't have it。 So rather than put that subnaav bar inside of all of these。呃。

All all of the page components or putting it up the top of the browser router。 we put browser router。

 we just put it in some of the components， which is just like a nicer way to program And in some ways。

 this is kind of clearer to people this is kind of like your ideal way where each component is just composed of other component so that a programmer can really see what makes up that page but obviously repeating yourself if you're gonna do it always is kind of bad So we would take that out here and leave this nav component in here。

Now， that was part one。 We'll kind of touch back on that at the end。

 Part2 here was how do we link between routes without requiring a full refresh。 Well。

 let's say this is actually a nav component and that nav component is going to consist of the different parts of the site。

 So maybe what I'll do is I'll separate the nav from the rest of the page with a horizontal line and then I'm going to replace these divs with spans。

 And then what I'm going to do is I am going to put in the three links here。

 So I'll say home and about and profile。 And I want these to be links。

 and I'll go and put some line between here。 so。😊。

![](img/675820c374322e95a93a1a38bccfbf32_23.png)

![](img/675820c374322e95a93a1a38bccfbf32_24.png)

Oh， I need to put that in a。 that's funny。 They' interpret it like an or statement。Yes。There go。

 So I got home and about and profile。 Now， maybe I want a little bit of extra space between all these。

 So I'll add a H entity。 You can go and look those up if you want to。

 That gives things a little bit of breathing room。 M BSP means。I don't even remember what it means。

 but it means space。 And now what I want to do is link these things。 And then you might be thinking。

 oh， okay， well， to link it， I'll just use， you know， a， A Tf equals slash。Like that。

And then this one here is for about， so it'll be like slash about and then this one here。

Is for profile。Slash profile like this。Okay。The problem with this is that whilst you are redirecting。

 if you pay attention to this little icon up up in the top left here。

 you'll notice that it's kind of flashing quickly。 And that flashing is indicating that that page is actually doing a full reload。

 And that's not ideal。 That's not what we want。 We want it to be more seamless than that。 Now。

 if this page was bigger you would notice the full reload just like the unSW page。

 But in this instance， you're not noticing it。 So how we get around this is there's actually a component as part of the react router dom library called the link link is a react Js component。

 And what it does is that it replaces the a component。So it's， you know， open A N A。

And instead of a tri。The attribute is called2， which makes sense。 It's like link to this route。

 And what this does is this doesn't tell the browser to go and reload a full resource。 A web page。

 It simply works within the react framework to。Rerender parts of the page。

 So if I now go and run this。What have I done wrong， Hopefully， it'll give me an error。Not too sure。

Very strange。 Let me just pause and。So a small detail I forgot。

 And I found it by looking up the console What is going on here is that the way react router Dom works is that it only likes doing reactor router dom stuff within the browser router。

 So this is problematic because what it's saying is that the links here。

 the link tags exist within the nav component， but the nav component does not exist within the browser router component。

 Basically react router dom doesn't want to do anything outside of the browserr browser router component。

 So therefore you think oh， it's fine。 I'll just come and drag this in here。

 That should solve the problem right？ This becomes pretty effective in the sense that。

Now we can actually do the linking inside of it。 So before what we had was we had this up here。

 which is bad。 It's weird that it doesn't display a page error， but it is in the console。

 whereas this one is better because it's within browser router。

 what you can't do is you can't put it within routes。

 If you put it within routes Re router dom gets angry again because it only expects a route tag to be inside of routes。

 So now we've got our nav here。 and you notice when I click through this， the page isn't refreshing。

 It's very seamless。 In fact， the virtual dom is not even re renderndering this line here。

It's leaving this line alone because reacts very smart and only re renderndering what it needs to。

 right。This is good news for us。 we've now made a simple page where you can link between components like that。

😊，You'll also see that if I refresh the whole page。

 it stays on this because when you refresh a browser page， it just stays on the URL you're on。

 So that's number two， linking between routes without requiring a full refresh。

 The third thing we said we'd look at is how do we capture wild cards in the URL to utilize state。😊。



![](img/675820c374322e95a93a1a38bccfbf32_26.png)

![](img/675820c374322e95a93a1a38bccfbf32_27.png)

Now， what I mean by that is what happens if I want to have a URL that's like profile slash Hayden。

Or profile slash Emily or something like this。 Now， the reason this isn't working right now。

 The reason literally nothing is rendering is because react router doms， browser router routes。

 this stuff here。Looks for an exact match。So because this is slash profile slash Emilyily。

 it's like that doesn't exist。 it doesn't care that it slash profile。

 what it's looking for is something like slash profile slash Emily。That works。 Now。

 this is also an important lesson that a lot of these routing libraries are able to reuse components。

 So here I can say that both slash profile and slash profile slash Emily both take you to the profile component。

 So that's good knowing that we can reuse those things like that。😊，Now。

 we don't w to have to write out one of these for every single thing， right， But let's start there。

 I've got my slash profile slash Hayden slash profile slash Emily。

 they all load the profile component。How we would then make this more dynamic because we would have our profile component。

 and it would like a look at the URL and try and par out the name。

 And that gets really messy really quickly。 Thankly。

 react router dom is smart enough to give us a wild card in the URL where I can use colon name。

 So the colon indicates a wild card。 And the name is just the name of that wild card。

 So what this really means to react router dom is slash profile slash something like that。😊，Right。So。

That's super handy， because now， even though when I。When I refresh this page。

 no matter what name I put here， Hayden hello， it's always loading that component because it's like whoop slash profile slash something well that's what we have here。

 it' slash profile slash something but the next question is how do we actually capture that information？

This is where a really useful react router Dom hook comes in， which is the use Paras hook。

And what use I'll show you how use prams is used。 So let's this profile thing here is a page and what I can do in this react component。

 and I'll just make this， I'll just expand this out a little bit。

 so we have a bit more breathing room。How we can use this one is that inside that component。

 I can say con parametersms equals use parameters who like this。

 And then I will say console dot logg parameters Rams。 And let's have a look at what the output is。

 So if I load up F 12 here。I can see that prams is an object that has a key name and is hello。

 if I change this to Hayden， it's key as Hayden and you think， oh。

 this is quite interesting because now what I can do is I can actually just say profile prams do name。

And now， this page will render。Whatever is here。Profile， Emily profile Hayden profile。 hello。

 And you might be thinking what's the point of this。 It's like， well。

 typically how this would actually work on a computer is you would use this to make a fetch and that you would give that fetch to a back end and that back end would return you the information you want。

 That's what's happening on a site here like UnS Ws when you load all of these events， right。

Is this just passing this grace tame information to the back end and loading that information forward。

So that's super handy， That's super nice。 What happens if someone doesn't enter a name？

Does that component still load？ Yes， you can see that because it comes up there， however。

There's no name。 So what might we do。 We might want to say something like please enter a name。

 So let's do that quickly。 I've got my profile component。

 And what I'll do here is I'll do some conditional rendering。

 and I'll say if prams dot name is blank。I don't know， let's try it out。No name。 Maybe it's blank。

 Maybe it's null。 Don no try it out。Okay。It doesn't seem to be blank。

 Maybe we'll try the undefined case。 I， if it doesn't exist。No name， great。

 So if there is no parameter name。😊，Maybe let's like render a little short sub component。

 And that sub componentent might do something as simple as。Store an input。And that input， you know。

 I can do an input like this。And when someone types it in， and then we can put a button。

 say button go。 and that will take you to a particular page。 Now， I'm just。

 I'm just expanding on this very briefly so that you can kind of see how this goes。

 So what I can do here is I can make a little version of the component that's simply going to。啊。

You know， its value is gonna be name and it's on change will be E， E dot E dot set name。

 E dot target dot value like this。嗯。Which is probably a bug there。 Let me just word wrap this page。嗯。

And now I go use my， my use state hooker rights。 I'll just say， you know， con name， set name。

Equals react dot use state null or empty string or something like this， right？

 And now I've got this little component that should be able to update。

 Now it's complaining here because reacts not definedca I didn't import react。

 So I need to import react from react here like that。 And now I should be able to type into it。

 And when I click go， nothing's gonna happen because my button's not doing anything。

 but react's really easy。 I could say， well， on click， I want you to do something。



![](img/675820c374322e95a93a1a38bccfbf32_29.png)

![](img/675820c374322e95a93a1a38bccfbf32_30.png)

I want you to go to a particular route。Now， the old school way of doing this is you could say that。

 well， I'm gonna call a function and that function is just gonna set the window location H F to say slash profile slash。

Name like this。 And that'll send you to the right page。 if I， if I do that。

 I type hello and I click go， it'll send me to the hello profile。 And if I click back to profile。

 I can go to the Hayden profile。The problem with this is that I'm using window dot dot location dot H F。

 which is actually reloading the whole page。 And again。

 you can see this if you watch the little green icon at the top with hello refreshes that whole page。

So whilst this， as I said， whilst this does work， it's just not perfect。

 how we actually do it within the right react framework is that there's another react router Do hook called use navigategate and what use navigatevigate does is you can collect it in a variable like this。

 use navigate。And instead of letting window dot location dot Htro equal something。

 you can actually just call and navigate and give it that URL。

 And it will do all of the smart rerouting for you。 So now when I type in Hayden。

It sends me to that page， but it did， it did not refresh everything。

Now that's that's really exciting and cool because now we have a way to like do this and this this will pay dividends for you on much more complex pages where you don't want to rerender lots of stuff。

😊，Now， that kind of summarizes the third item here about capturing wildcard in the URL to utilize state。



![](img/675820c374322e95a93a1a38bccfbf32_32.png)

But I just want to quickly come back to this。 associate particular components with particular routes。

 because。

![](img/675820c374322e95a93a1a38bccfbf32_34.png)

The new versions， the new version of react router， what it allows you to do is it actually allows you to nest routes if you'd like to。

 What I mean by that is， let's say we， for instance， have another page called about slash team。

 Then we'll create another page called about slash I don't know， history or something like this。

 right。And what we want to do in each of these cases is like we want to link to a particular page。

 I'll just kind of quickly copy and paste these components。I'll call one about。

 I'll call another one about team。I'll call another one about history like this。

I'll go and change the components that these things are linking to。Wops。Yeah。

 so I needed to add them to the nava anyway。 So I'll go and create like an about team and about history。

 and I'll go and update this to be about team and about history like this。

 And now you can say I've got all these different URLs and it is sending it to different places right。

 However， you can actually clean up your react router dom in the V6 by saying， actually。

 you know what， all of these different abouts are're actually all kind of subsets of each other。

 So instead of this being a void component， I'm actually going to treat this like an openclo component。

 And then inside of that， I'm going to go and put these two routes。

 And because it's inside of slash about I can actually get rid of that。😊。

So it's a little bit interesting， but oops， I've done something wrong there， let me just fix that up。

See if this works no。You just get rid of that。So you see this isn't actually matching here。

 And that's because I've definitely done something wrong without realizing。

 But you can see that about is matching right Now， what has gone wrong here。

 And I've made this mistake in the past is that while this is a really cool feature of react router do。

 it doesn't always behave exactly how you might expect。 So， for instance。

 what this is saying here is not that if it's slash about， go and load about。

 And then if it's slash about slash team go and load about team。

 this is actually saying if it's slash about slash anything， we're gonna load about。

 And then inside of that， we're gonna to load one of these other components。

 So it's actually built hierarchical。 And why this is really tricky is there's actually a。😊。

I think it's called outlet。I should double check that。

 but there's another component of reactor routedon called outlet。

 And what happens is if you have a component like about that has sub pages。

 you actually need to include that as a component。Inside of your code。

 And this might be a little bit confusing for what's actually happening here is outlet is kind of like this placeholder used by reactor Outer dome that simply says。

 you know what， if there's any sub pages， put them here。

 So that when I go and load history and team and normal about if there is a sub page。

 it goes and loads it there。 So that's why you see that both about and about team are being loaded in this particular case。

 So this is actually something that's really powerful。

 if you don't want that behavior and you one all these pages to share the same， same base URLs。 But。

not have any common code。 There's a few different things you can do。 Obviously。

 you can just go and write out all the URL separately。

 You could go and create an about component that simply has nothing in it except an outlet like this。

 It's just like an empty component。 That's another way you can do it。

 But you know you can play around with that as you'd like。

 But that's the basics of using reactor router dom and just to recap Now we're able to associate components with particular routes。

 typically you will put these in separate pages like separate files。

 usually I'll create a page folder for these。 I'll go and say new folder called page。

 and then I'll go and move some of those across。 I just have to close my editor and reopen it。

 doesn't do file history。 Well。 I'll go and create a new page and I'll go and grab this。

 and I'll put this in a new file。 and I'll call this the about page。

 and then I'll import it here inside of dots。 You know how to do components by this point。😊。

So you get the idea right， but this has just been keeping it simple in one file for the example。

 but yeah， normally you would break it up， so。And I hope that helps you gain some confidence in building multi route pages。

 not only linking them to components， being able to move between them and then also capture those wildcard。

 So thank you very much。

![](img/675820c374322e95a93a1a38bccfbf32_36.png)

![](img/675820c374322e95a93a1a38bccfbf32_37.png)