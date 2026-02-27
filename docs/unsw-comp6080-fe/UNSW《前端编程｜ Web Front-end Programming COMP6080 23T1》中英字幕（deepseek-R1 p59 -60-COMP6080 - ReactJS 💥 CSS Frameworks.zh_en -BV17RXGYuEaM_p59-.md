# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p59 -60-COMP6080 - ReactJS 💥 CSS Frameworks.zh_en -BV17RXGYuEaM_p59-

Hi everyone， my name is Hayden and today we're going be talking about CSS frameworks in the context of React JS。

 So in react JS there's a whole bunch of different ways that you can make CSS come to life on the page and that you can structure your CSS Today we're really interested in learning about probably the easiest way to build large scale applications as quickly as possible So let's first take you through just a couple of the key ways that you can use CSS and react JS right So for this particular lecture I've gone and gotten a simple react app set up for us and that react app is hiding inside the CSS frameworks and it's just a typical one that we're used to seeing many。

 many， many times。😊。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_1.png)

![](img/eb4c03788c6ee2e1b310299e9c4e8648_2.png)

What you'll notice in all of the default react apps is that they all have this import slash app dot CSss that you've seen from other lectures。

 and this is the method one you see up here， which we've already covered。

 which is importing style sheets directly。We're gonna jump today to the second and kind of on the other end of the spectrum。

 very， very abstracted， very easy approach， which is to use a component library like material material Ui。

 which is an example library we're using today。 We're using a component library so that we don't have to go and write all this Cs for things like buttons and tables and headers and everything else。

 And we can just get it coded quickly。 So a library like material UI。

 It's a simple website M Ui material Ui。 And it's designed for applications like react to be easily installed。

 And you can see here that in this one， it is a react library。 If I want to get started using it。

 I can just literally go and copy and paste that install command。

 and it will go and install some of the key component。

 It's the key modules from NPM that we need to make this happen。 In the meantime。

 whilst that's installing。😊。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_4.png)

Going to go and clear this out so that I can start off with a really simple page。

 We're just gonna keep this whole thing very， very simple。 And once this is done。

 we'll start up our react app。 And whilst that's happening。

 if we go to the material UI website and we start looking through their docs and we go to the side by here。

 you'll actually see here that there's a whole bunch of components。 and this is all material UI is。

 it's a handful of pre。Pre style components for us。 So you can see here we've got。

 we've got everything from buttons to check boxes to radio buttons， Sw， text fields， cards， dividers。

 tables， dialogues。 And if you click on some of these， such as say。What to be a fun one like menu。

 for instance， You can see menu here is a kind of menu like this。

 Now this is a very simple what you might call a primitive library。

 maybe not quite some of it primitive not primitive is in terms of basic but primitives like fundamental components right So like on a website a primitive is a thing like a button and a text input and you might think of components therefore as something like this that uses those things together and pages as a series of components。

 but these are all very arbitrary lines that don't really have you know super strong definitions。

 but if we come here and now that that's done and we we start this react up up。😊。

What we'll see is we have our little hello app here。

 Now I would like to use one of these components here， such as let's find a simple one。

 What's a dialogue。 What does that look like Okay open simple dialogue。 Oh that's a nice little one。

 So let's try that。 So if we want to use something like this。 we can actually see an example we want。

 typically there's a whole bunch of examples such as this one。 And if you like an example。

 you can just click on this show source code underneath and copy and paste it right I'm going go and find a simple one to start just so you can get a feel for it。

 And I'm just gonna pick button。😊，So buttons are really easy。 If I open the source code here。

 you can see that there's a few different button types and what I'm going to do is I'm going to just quite literally copy and paste this button here。

 you can see that those three buttons are all the same button component。

 but they have slightly different properties I'm just going to move my face for this particular moment It's got three different properties right which is contained and outlined and text。

😊，So now when I come to my page， you'll see the buttons not defined because I have not imported it from the Ma UI library。

Whereas now it's here。 Now， this looks a lot like what was on the web page。

And I can change what's inside of that。 I can say hello， and there's my button。

 and you can see that it's got a nice color。 When I click on it。

 it does this like nice little wavy motion。 That's just probably CSS properties built into it。😊。

And we can take this further if we want， right if we want to make it a disabled button。

 we can just add disabled to it and again the Ma UI component library has all of the CSS built into this。

😊，Sorry， I had to sneeze。 It has all of these styles built into it。 And if you go further down。

 you'll see even more types of buttons。 you can change the color of the button。

 So you see how how we have a contained variant。 We can actually give it a success colour。

And all of these buttons will tend to follow a fairly similar colour format。

 And these libraries have these universal， like for instance， if I go material UI colours。

You'll see that there's often depends on the library。

 but there's often a very simple predetermined set of colours， right， or in， you know， in this case。

 here's just a handful of ones you see。And。These are like primary colours and set like I'm not elaborating on this particularly well。

 but the point is that a lot of these libraries have themes and those themes tend to have colours and those colours are often defined by fairly simple names such as success right。

 Let me undiable this。😊，Such as success and info and warning and primary。

 which is usually blue and secondary， right， all these different colours。 I mean。

 what's really useful about libraries like this is if you define your page not thinking about， oh。

 this is the blue color， But this is the primary color。

 what it means is that if you want to go and change a theme。😊。

Materialally U Y because it's a nice little abstraction。

 we'll be able to go and update all of those things accordingly for you as well。

 So if we want to do something more interesting than say a button。

 maybe we'll go back to what we had before， which was a dialogue。😊。

I can see a open alert dialogue I like here and there's a lot of code。

 but I'm just gonna go and copy。 I usually copy these in two parts。

 I've got my the like the HTML part and then I'll go and import the library。

 So you see there I've got my button variant and open dialogue。😊。

I can also see that if I look at the sample code here that they've actually also got some dynamic code for us。

 So you know these libraries aren't just a bunch of HTML components。

 They are often also a few like use states and other things。

 And then there's a whole bunch of stuff I need to import here。

 I don't need to import button again because I really got that。 So I can go and copy and paste this。

 Now I've got some compilation problems react is not defined。

 it once react imported because I'm using the use state hook and now we've got this open alert dialogue。

 And when I click on it， I get this nice little dialogue。 great。

 I could go and clean up this code a little bit right。

 I might look at this and think this looks a little bit ugly you know like these these functions are so simple。

 could reduce it down to that。 And when you really look at the code here。

 you can see that we've got our button for open alert dial。

 And then we've got our hand or click which just sets it to be open。

 And then our dial component itself is only open if open as true and on close we call hand or close。

 So you can see that it's really just a boiler plateway。😊。

trying to just get some basic react functionality here。

 And then you can go and change everything you want inside of this。 And in fact。

 you could customize it further， Like what happens if you want to have another button that doesn't just agree or disagree。

 but like come back later。 you can just go and modify these kinds of basic components and give yourself lots of different things。

 And what happens if someone hits come back later。 or what happens if someone disagrees and you want to give them an alert。

 and you say no， I don't want you to disagree。 Now it's like I click disagree and I get that。 know。

 So that would be mean。 be at the point， It's like you're just kind of using this。

 And it's a lot of copying and pasting。 and there's a lot of modifying what you'll find with these component libraries is sometimes I draw this little chart out for people。

 which is that if you look at。If you draw a chart of， say。

You know how much you want something to look， how you look。How you intend for it to look。Or it。

To look。Right， if you were to chart this where the X axis is like how much you want it for something to look。

 And over here is like the effort involved。Well， you know， if the effort involved here is like。

 you know， infinity and the effort here is like 0 and how much you want it to look like what you intended for here is 0。

 And this is like 100 per。 Well， here's what you're going to notice with component libraries。

 They're going to follow a fairly straightforward curve that's going to look like。但。

Where to get something that kind of 80% looks how you want it to。

 it's gonna be like no effort at all。 right， Like you look at this。 And you think， yeah。

 that looks nice。 It'll pop up and stuff。 But the second you want to say。

 do something slightly more interesting。 Like I want to put an icon here。

 And then you start trying to like navigate through the code and be like， allright。

 there's a dialogue title。 Or what happens if I put like a little。

 I'll make just like a little div here， right？ It's like a 50 pixel width and a 50 pixel height and say background red。

 just a little placeholder for us。Sometimes it's easy。 Sometimes it's hard。

 Put a little red box here。 Dam it， it's not going in the right spot。

 I just want it to sit to the left of that here， It's probably gonna be okay。

 Now like dam it's still not going in the right spot。 It's like， well， that's because， you know。

 it's a development。 But let's make it float left。 This one willll probably be fine。 And you're like。

 cool， okay， well that one kind of work。 But now how do I change the padding of that text， right。

 Because normally if I was just coding this manually。

 I will go and change the padding of the text here and you think， well。😊，Maybe I can try this。

 And I just kind of pull this example out。 The point is， though。

 that you're essentially taking something that's pre prepared， right。

 And it's just like everything in life。 If something's pre prepared。

 it's going to be harder to kind of wind it back to how you want it sometimes。 But in this case。

 for instance， it's probably okay to rip this apart a bit，20 pixel padding。 Okay。

 maybe I can't margin top。Okay， so and again， I'm， I， I could figure this out。 but it's like。

 you can see here how suddenly you're like， oh， okay， well。Maybe this can be a div。

 And then suddenly your code。 Okay， so if it's a div， that makes sense。

 starting to look a little bit cleaner。Give it a margin left。 And， you know。

 and then your code starts to， to turn into spaghetti。 This thing this one has to be a paddingler。

Maybe not， you can play around with it， right？The point is that。Just a little bit of manipulation。

 Often you can solve the things pretty quickly。 This is probably like getting into this area here。

 But sometimes you would just bash your head against the wall。

 And you just have to go into these component libraries knowing that they're probably often going to only be 90% how you want them。

 right。 So like if you look at the course website echos。 Most of this turned out pretty well。

 you know， the things turned out relatively similar to how they were wanted and often the things that didn't。



![](img/eb4c03788c6ee2e1b310299e9c4e8648_6.png)

Like， for instance， I， I really wanted to get rid of some of these card backgrounds。

 And I figured that out in the end。 But there was a little bit of a struggle there。

 Probably the main thing that was difficult was getting some of these like sidebar things working because I couldn't quite find a component that did what I wanted it to。

 So I had to kind of rip a couple of things apart。 You know， that took a lot of time。

 That's where like。You know， the whole， you know， the 80-20 rule right。

 like 80% of your efforts spend on 20% of the output or whatever it is。

 whatever incarnation of that sentence exists。But you get the idea。

 So you can take this further and further and start adding more and more buttons。

 And I don't really need to go through a whole example because like， you get the idea。

 It's just this layering on top。 And you'll find so much stuff here。 you will find。



![](img/eb4c03788c6ee2e1b310299e9c4e8648_8.png)

Progress right progress bar。 So if you want to have this little loading screen whilst you're talking to the server。

 that's a great thing to do。 You can again just go and copy that in。 I'd be like， oh。

 I'm gonna take this circle progress and I'll just put them on my page and then I'll just import import this line and all of these items here are part of what UPm installed and it's like great now we have that。

 So now what I could do is I could maybe only show that。😊，If the。

Dialogue is open right now this makes no sense at all。

 but you get the point like you can start conditionally rendering with this stuff。 So it's not there。

 and then I click open alert dialogueg and it appears。

 and then I click agree and it goes back very powerful ways to build things quickly， right。

 Like once you understand react and now that you understand a component library。

 you can do things very quickly。 And I said in a previous lecture that the initial incarnation of this course website。

 Maybe it looks different when you're watching this video probably It took about， you know。

 it was a day。 It was pretty much a day。 in terms of just the Ui because it was just this is a sidebar from material Ui。

 This was built in material Ui。 I'm pretty sure this was based on。😊。



![](img/eb4c03788c6ee2e1b310299e9c4e8648_10.png)

Was it Nava？Often， I just Google these things like I often don't look through this。

 I'll often just be like， na bar material U I， and then it'll app bar react。

 And you'll see very similar things like there's the app bar。

 And you'll see if we go further down that。What do they call the slidey thing， I think it's a draw。

Is it a drawer？Yeah， it's this right it's it's a draw component。

 it appears it's like a draw that you slide out。 So that's where that kind of comes from， you know。

 and it was modified and I went and found an example that had like a multilevel draw Some of these won't be on the actual material UI website though Some of these things you will have to go and look up online。

 You'll have to just Google things for particular examples。

 I don't think there was a multilevel example here。😊，But again。

 if you feel like exploring more and seeing what more was done。

 go check out the source code for the course site because all of that sitting inside the frontend source folder and you can go and see a whole bunch of stuff like you know the course outline page for instance。

 is made up of a whole if I go to the actual course outline if you go and have a look the whole course outline page is made up of a series of topography and dividers and these are all material Ui components。

 you can intermingle them with like your standard your standard like HTML components too right here's an ordered list and a list item we got more topography unaudered list list items dividers you know tables and this table comes from material Ui and you'll see that in things like the course outline too This table comes from material Ui it's a material Ui table with a material Ui button very。

 very straightforward stuff so。That's the crux of it。

 That's what I probably recommend you spend time with The third type of styling that exists is the use of styled components。

 St components are something that aren't unique to react。 They you know， they exist。

 it's kind of a library that is just。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_12.png)

A JavaScriptscript wrapper of CSS， and I'll just find one for you it's actually an example of it used in the course site。

 Let me just find that。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_14.png)

So there's actually a file inside of the echos repo that you'll see at least again at the time of 22 T1 called upload and upload is a really really simple component and it's something if you watch the left page you'll see it really quick when I load it you see a little flash it。

 It was very brief。 It was like a little circle thing。

 It's the same circle thing that we saw before right circle progress here and the way this component works is there's pretty much a loading wrapper which is just a diviv and then inside of that I have either if there is no error。

😊，Right， then I show the circle progress and if there is an error I say please try again later。

Basically what happens is I've also got a timeout here where if 10 seconds passes and you don't get sent off the page。

 then it forces an error because it assumes that the server timess out and the way this particular component is actually used if we look it up is it's actually used here inside of like a wrapper for all the pages where essentially what happens on every page is that a request is made to the server to get information。

And whilst that information is not populated， the page has not loaded and therefore it shows this component。

 So the second the server returns the data， the component that's using it no longer renders it and therefore it disappears So it's kind of either loading or an error stage because once it's no longer loading。

 it's just not rendered anymore。 but the point is that we're using a material wide component here circular progress。

 but I also used to have a div here。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_16.png)

And this div used to have a whole bunch of styles on it。 And you might be thinking， oh， well。Okay。

 Hay and well， I， I've been told that。Using this kind of global CSS is bad and it is bad。

 the reason it's bad is because in react。When you import CSS this way， like the old school way。

 like an index do Js， it's actually imported globally so those styles are available throughout the entire application。

 whereas when you're making kind of styles with a component in a true component composition design pattern approach。

 you want to make sure that everything in this component is completely selfcontained because that component should be separable and isolated and reusable but I don't want to have a div here with all these styles and I don't really know how to break it up into its own file with a class。

 So what you can actually do is use these styled component。😊，Pace from material UI。 And in fact。

 there's there's actually a style components library that doesn't rely on material UI。

 You can go and check it out online。 It's a little bit different， but the same gist。

It's basically a library where。You can go and define a component。

As essentially a styled version of the A tag as in， you know。

 the A Htl tag that has the CsS properties。 So what's happening here with material UI styled。

Function is a very similar thing。 It's basically the same just in a slightly different code format。

 where it's saying that the loading wrapper is actually going to be a styled HTML div with these CS properties right So now load loading wrapper is kind of like a custom property sorry like a custom component with these like custom styles。

 Now what's exciting is if you would like to reuse this loading wrapper component。

 you can simply take it and go and export it to another file。😊，So if you wanted to have。

 say a whole bunch of your own primitives or your own things that you want to modify。

 then you can go ahead and do that。 And what's even more exciting about how material Ui works is that if this doesn't have to be a div you can actually reuse and continue on this composition approach where you say like loading wrapper big and you can say it's a styled version of loading wrapper where it has more properties such as you know with the 400 pixels and it will inherit the previous properties and expand on that。

 So this is kind of beautiful inheritance approach that you can apply here to actually defining your own custom styles。

 And this is definitely something I would recommend that you go and do if you are trying to take these like。

😊，Define your own primitive so to speak， which you kind of do sometimes right because there's lots of things where material UI just doesn't or any component library it just doesn't have the component or the primitive you're looking for so you're going have to go and make your own。



![](img/eb4c03788c6ee2e1b310299e9c4e8648_18.png)

![](img/eb4c03788c6ee2e1b310299e9c4e8648_19.png)

Now， this is great if you're going go and make your own。

 which is a third party using style components， a custom middle ground to fine tune components while still making them reusable right。

 So more reusable than this old style CsS， more fine tune than material Ui， however。

 let's say that you have a material Ui component like a button on our page here and you want to just make a little bit of a change to it right Well to make just a little bit of a change to something。

 most material wire components are able to just have a style dumped on them like this where I could say you know styles like with 200 pixels。

😊。

![](img/eb4c03788c6ee2e1b310299e9c4e8648_21.png)

That usually changes it。Though you'll notice that for materially Y。

 you'll often see this SX prop used around the internet。And essentially。

 it's a little bit more versatile with some of the stuff it can do。 So when you use style。

 it's essentially just applying that to like the raw element itself。 whereas Sx， as you can see here。

 custom style that has access to the theme。 So themes are something we're not really talking about in this lecture because we can only talk about so much that we could talk for millions of hours。

 But if you want to a materially why theme is essentially where you can go and。

Kind of change all your colors and all of your formats in like a universal way。 though， honestly。

 you know for the sake of this course， we really think that just something simple is fine。

 Like this course website is using all the standard material Y themes and it looks fine。

 But if you want to go spend some time looking into different kinds of themes and explore things you can do with the Sx property。

 that's fine。 just be you know use this kind of thing sparingly with custom styles。 In fact。

 I would generally recommend that if you're putting more than a style on this that what you probably do is you probably go and start using the styled library and you start saying well。

 just so that my code is particularly clean， I'm gonna I'm gonna come up here and I'm gonna say。

 well， styled like that。 And then I'll say you know big button equals styled button。😊，Like this。

 And then you can say width 200 pixels like that。And then you should be able to take big button and。

Put it here， like this。It's probably probably not going to work， probably forgotten something。

200 pixels like this。 JS X closing tag is missing because I forgot to copy the closing tag。

 And now we have that big button there， right， And then this is just really handy because this shows that you can componentize things because it will keep reiterating in the lectures。

 it's like。Custom， like this is not bad。 What's bad as putting style on a particular tag。

 Because once you put style on a particular tag， that tag is often not very reusable。

 It's not very separable。 What's nice about this is I can come along and I can copy and paste it into another file。

 and I can import it if I want to。 I can't do that the other way around。

 So lots of little lessons here。 But again， this lecture is or just to help you get a feel for things。

 And hopefully， we've done that a little bit。 So good luck making some U very very quickly。



![](img/eb4c03788c6ee2e1b310299e9c4e8648_23.png)