# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p09 -09-MIT web.lab (6.962) - Day 2_ Workshop 1 (React).zh_en -BV12Ux5zTE9p_p9-

Okay， we're gonna a ho ahead and start with the， the second workshop。

I'll let everyone find their seats。M should beating。Allright， I'll go ahead and start。

So earlier today， we told you a lot about react and how it'll help a lot with your projects once you get into like really complex design。

Specifically， it helps with abstraction and re。Let's do a quick recap。

The idea of react is that you can break down your U I into modular components that you'll be able to reuse and call with ease with having to write out the entire thing。

 Each component takes in a prop。😊，And it manages its own state。And they have their own。

 like various uses and times where they're helpful。

And all the components will interact with each other through parent childil relations。

 props will pass from parent to children， never the other way around。

And you can think of the structure， like a tree。So ultimately， the idea is that。

Once we have our components， all we need to do at the end is just link them together。

 passing down the appropriate props。And then at the very end。

 all we'll need to do is just instantiate our app element， and that'll contain our entire web page。

So we did this before with Facebook。 but let's try to break down another website into its components。

Following the component。As always， we're going to start with the root。And that's the app element。

 as always。Within that， we'll have direct children of the app。

And these are things like navbar or bigger components like an entire feed or a trending pad or trending tab and more suggestions。

Within all these components。You might have smaller smaller child components， such as tweets。

Or specific。Profils to be put in like the who to follow tab or maybe articles in like the trending tab as well。

And furthermore， there is components like search bars and little like gadgets on each of the posts as well。

To refresh you on props， props or information that will be passed from parent to child。

And they're passed in the following manner。Pos。Element will take in the prop's name and text。

 And you do that by adding the attributes for name and text and then setting those to the appropriate value。

And then what react and interpret that as is giving javascript object to the component that looks like。

What I have up there。The other important concept is state。

 And these are pieces of information that are uptable。 So if you'll remember。

 props can't be changed by the component themselves。

 They can only be changed by like a parenting component。But with state。

 you can maintain that within the component。 So this is very helpful for things like like it is liked。

 as we showed you like a couple times before， or like status or like if there's a user。

 then maybe you want to say if it's online or not。Things like that。

So let's directly construct the component tree。As I showed you before， we start with our app。

And then we have some direct children。And then。Within those， we have further sub childrenildren。

For example， tweets， profiles。If we started our top level。嗯。We have。

All the children directly instantiated。Let's follow down the path of one of these components。

So if you look at the feed component。嗯。Since we're not getting any props passed in。From app。

We'll directly get the information that we need。And store it as a state。So in this case。

 our state is going to be tweet data。And it's gonna be loaded from some API。

 And we'll touch on that later， in the course。But all you need to know is that it's maintained by this component。

And not one above it below。And we'll use that state set。

So that we can load up the data into this variable here。Then within our return。

We have to render this。And for that， we're gonna be instanting tweet components。

 And these are sub childrenildren of the feed components。And in those tweet components。

 we have props passed down。So in this case， it's username。And maybe some more stuff。

 like the content of actual tweet。So let's see what that looks like。And the child component。

Because we passed down props， we need to。Let react know that。 So props are passed in。

 and then we can easily unpack those props。By usings dot。

pause for a moment because that was pretty quick review。And you guys just learned it today。Okay。

 so final recap。A reacting component is basically a bundle of like jascript logic and HTMLl rendering that lets you reuse a piece of code that you don't want to keep writing over and over again。

A component can be represented as。A piece of HTML L code or a bunch of other react components stick together。

It can receive information through props and maintain its own information through state。

And these components all interact with each other， using a tree structure。

I've linked the react guide， again。And I encourage you to check it out， because。

Some of this stuff is a little hard to grasp at first。

 but it's important that you get it because you're gonna be constructing your entire project。

 using reacts。 I'll pause for any questions before we jump into the workshop。Okay。

 then we'll go ahead and start。So as we did with the first workshop。

 we're gonna be using V S code or maybe your terminal as well。

 So I'll give everyone a moment to get that。要 quick。Our end goal for this workshop is going to be to。

Convert what we had from the last workshop into a react。嗯。Webage， and then add a few more。

Components on here that'll use are concepts of props and soup。Right。

 once everyone has got V S code up。We have a few more setup steps。Shall I get into right now。

So yesterday， we mentioned。A little bit about node。

 So node is gonna be how we can develop using jascripts in our browser。

And I think this was in the setup instructions， But everyone should have downloaded node。

As well as NPM。So before we move on， we're just going to。

Make sure that we all have the right version of node。And you can do this easily by typing in node。

 dash V into your terminal。And anything that's version like 18 plus should be good。

 I think the latest is like version 20。 So if you have that。这跟说。All right， good to move on。

If you have anything in trouble， then always remember to just join the queue and someone can help you。

O。Once we verify that， we have node。We're going to open up the Capa react folder from last time。

Open up the terminal window in V S code or elsewhere。And then run the following commands。

So I already have it up here。But once you get there， you should get something that looks like this。

And also， make sure that you navigate to the folder correctly。

 So you should see like catbook react and the can。Alright， I'll give everyone like one more minute。

To get this done。And once again， if you're having any trouble， then just run the queue。

 and someone can help you。OK。Let's first talk about the component tree for a catbook。As always。

 we're going to start with app as the root。And within that。

 we're only gonna have two components today。 We'll have the nav bar at the top and then the profile page。

 as you can see。Within the profile， we're also gonna have this funny component called cat happiness。

 And we'll let you know what that does in a bit。 It's basically just gonna be like this dumb counter that counts how many times you've clicked。

😊，The profile picture。Yeah， here are the components highlighted。Is the happiness about it。

So you'll notice that the starter code for today is a little bit more complex than it was last time。

To get everything like。Situated。Let's open up the client folder。So if you're in V S code。clientient。

And you're going look at source。S RRC。And then within that， there's also components。

And this is gonna have all of our。Opponents laid out。So within this components folder。

You'll see that first， we have just the plain app component。

And this is just as simple as I described before。It's basically just the k naob bar。

 and then the profile。We also have a folder for the rest of our modules。And pages。

So pages is gonna include things like profile。 So theyre fully formed pages that are a little bit more complicated。

And then the components that will instantiate into these pages， such as Nvbo。Or。Happiness。

And the only ones that we're gonna modify today are。Profile， navbar and cat happiness。

 So you won't need to worry about the app， J S X。Okay， I mentioned this before。

 but make sure that when you're doing styling。On reaction components。

 use class name instead of class。 And this is because class is already like a special word in jascript。

So。We have to use class name， instead。Also， good practice is every time you're creating a class for CS。

 S， you should put the component name before like a more specific descriptor。And。Like， of course。

 this is just helpful for like reading through your code。But it's also important because C。

 S S applies to the entire web page。 So you don't want to like。Mixed together。

Sttyling for components that like have similar functions， but are like， actually。

Like related to different components。So today， instead of。

Dragging out the file and just like pasting it in your browser。

We have a different command for running your page。And I'll let you guys all try it out。

It's gonna be NPM run dev。And it'll spit out this thing here。And all you need to do is。比 this。

And then you can go to your browser。

![](img/74a0a92e8ed9c269dfb61ecd07d67249_1.png)

And then and。Its the in， And then it should have your website。

I'll let everyone try that for a moment， before we move on。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_3.png)

。By the way。啊。Oh， and if you're using V S code and you'd like to open up another terminal while this is running。

 you can press this button here。And it'll create another one。You can use。Okay。

 it sounds like there's still some trouble with the setup。 So I'll stop for like two minutes。

Before I move on。啊。어， oops。Okay， I， there's a typo on the slides。 It should be 5，1，7，3 and not 5，1，3。

7， sorry。Okay， sounds like。We're kind of on track now。 So I'll go ahead and move on。

We have three steps for today's workshop。And the first one is gonna be just implement the nav bar。

Before we do that， make sure you run these commands。 I think I already had you run them。

 but just in case。We're starting on the same。P。This na bar is gonna be pretty similar to the one that we did in the workshop yesterday。

But today， we're gonna have to do it using the syntax of react。So， remember that。

When you have a react component， whatever your render is going to be within these return parentheses。

If you remember our old code。Our nav bar was like pretty simple。

 We just had this like nav container here。 And then within that。

 we had a title with some more styling on it。And it's gonna be a very similar thing here。And then。

 of course， we also need to style our a bar。Which we also did in the last workshop。

So I'll let you get the hang of doing that here as well。Also。

 something that we didn't mention in the lecture was how to link like C S style sheets into react components。

You do that by using this import line here。And then。He'll import this path。

If you're ever unsure like which path to import， you can。Right click onto the C， S S file。

 copy like the relative path。嗯。A we now， not the road。You copy the path。

And then just do that as well。But。If you know that your component is like auditing the same directory。

 then you can just do something like this。Remember， dot means it's in the same directory。And then。

 with him there。The file right there。I'll give everyone like two minutes to reimplement the nav bar。

 and react。You can use whatever class names that you'd like。

 Just make sure to keep it like somewhat reasonable。And you can add whatever style you'd like in C。

 S S as well。Okay， I'm gonna go ahead and start solving it with you guys。

So the first part of this is just putting in the H T L code into our。Return。So， instead of no。

We're going to have this now bar。And then， we're gonna have。More stuff inside here for the title。

We're also gonna add styling。 So we want to add class name。Not class。And then name it something。

describes what it does well。Again， see that I'm using。The component name。Before I put the descriptor。

And then for this one， as well。什啥玩意的。Right， I'll let everyone。Get up to this。还。For a minute。Okay。

 the next part is to apply the styling。So for that。

 we're going to open up our CS style sheet for Navbar。

And then depending on the class names that you used。Well select。And then， apply。Oh， okay。

 I think I forgot something。嗯。Yeah， we'd like to keep using the same variables that we defined earlier。

So if we open up our old style C， S， we can just copy paste that。反呢。

And that'll allow us to use the variables。That we have before。

And feel free to change the colors if you don't like our blue。I will also plus styling to this one。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_5.png)

You still have your。Local host support up。It should auto update。 And you can see the nava bar。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_7.png)

Do everyone like one more minute to get to this part。N move on to the next。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_9.png)

And again， your website should look something like this。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_11.png)

OK。Okay， so that was the first step。 I'll pass it on to Abby from here。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_13.png)

But。In case you fell behind a little bit。Can always just get reset hard and then check out two step 1。

Alright， this is about the halfway point of the workshop。 Everyone， stand up。

We're not doing another Wall challenge。 Don't worry。 this is quick。Maybe got a little jog in place。

 going。Gotta get that blood flowing。 Otherwise， we're gonna fall asleep。Oh。

 that should not be plug display way。Okay， okay， get it。有个。O。

What if your screen sharing has paused me。哦，我去。嗯，I don't know。Okay， let's just try presenting again。

 see what happens。Yeah， can you。我也 can。Okay， sure。 that works。Cool。All right， everyone。

 we are going to keep plowing ahead， just like two more steps in this workshop。

 and then we'll take like a more legit bio break。😊。

So the next step is to add the cat happiness component。So basically。

 what we had before was our profile page that did not have this cat happiness component in the middle。

 It just had about me， my favorite type of cat。 But now we want our component tree to look like this where we have profile and then the cat happiness component within the profile。

😊，And then we also want to state that stores our cat happiness， because if you notice， if I go to。😊。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_15.png)

I'll go to Weblab do slash example。In order to see what this should look like。

And then if I go to my profile page， what we want is this functionality where I can click the profile picture。

 this little  corgi boy， and then my cat happiness increments。 and I can just spm it all I want。

 And it's like cookie clicker， except without the weird functionality to like hire grandmas to make cookies for you。

😊，So this is what we want and。We want this cat happiness to be stored as a number。

 and that will be stored somewhere on this web page because obviously。

 it has to keep track of how many clicks I've made so far。😊。

So that's a good candidate for react State。But the question that we're asking now is。

 which component should we store the cat happiness state in。

 Because remember that react state is something that a component maintains。

 We store it inside one of our components。 So the question is。

 which one of these components should we store the state in。😊，Think about a for sec。

 turn and talk to someone nearby you。Which component you think it should be。Alright。

 I'm going to pull us back together。Raise your hand if you think it should be stored in an app。😡。

Okay， raise your hand if you think you should be stored a NAF bar。Now。

 raise a hand of you think it should be stored in profile。Okay， some hands。

 raiseise your hand if you think she should be stored in cat happiness。Also， some hands， okay。

So it's probably either profile or cat happiness。 The correct answer to this is profile。😊。

So we don't want to store it inside that little box for the cat happiness。 And why is that？Well。

 if we want to update the cat happiness， when we click this button。

This cat happiness component is just this little box here。

 This has no way of knowing when I've clicked the profile picture。

 So the only component that we will be able to know when I've clicked this profile picture is the component that the profile picture is in。

 That's profile。😊，And so only profile will be able to respond to when I click this image。

And then what we can do is we can take that state that's stored in profile and pass it down into our cat happiness component as a prop。

 That way， cat happiness can display the number of the state that we stored in profile。😊。

Any questions on this。Yeah，我知道。In that case， we would probably just pull the state up into whatever highest level component we need it to be in。

So we might pull the state into app and then pass the the set function into an app bar。OK。

So like I mentioned earlier， profile， this component is going to have no props and a state of cat happiness。

 and then that cat happiness state is going to be passed down into the cat happiness component。

 That's this little box here that just displays that number as a prop。 that way， cat happiness。

 the box component can display that number。😊，So how do we add state to a component。

 We looked at the syntax earlier， but we'll review it。 We use the syntax cons。

 and then whatever the state we want to be in this case cat happiness。

 and then a set function for it is equal to U state。 and then inside the U state the parentheses。

 we put the default value。😊，Later on， we'll talk about a little bit more about what you say it is and why we want to do this as opposed to just using a regular variable。

 But for now， just remember that this is a syntax that we use。Alright。

 so let's get on the same page for step 1。 Just a quick note。

 make sure that whenever you're doing these workshop steps。

 you save or close out of any unsaavfe files。 If your tabs in V S code look like this with a little white dot in it。

 that means you have changes that are unsaaved。 And if you try and get reset and get check out when you have those unsafe changes。

 get will be confused and not know what to do and you'll get errors。

 So just make sure that you save or close out of your unsafe files。 So that。😊。

You can totally flush out your changes when you do gi reset dash hard。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_17.png)

Alright， so I'll give you a minute to run those commands。And I will get into my cap of react。O。

So I'm in my VS code， I'm on W1， step1， and then in another terminal， I just use。

 we just use this button to open up a split screen terminal or this one to just create a new window of our terminals in VS code。

And then here in another time， I'm going to be running MPM Runevev。

Raise your hand if you need more time to execute these commands and get caught up。Cool。

 we'll move along then。So your next task is to add the cat happinessiness component。

And so what we need to do is we need to add a state for cat happiness to our profile。 Actually。

 wait before before I get into that。😊，Don't worry about this slide for now。 Just take one second。

 Let's open up the files that we're going to be working in。 So if we go into the client folder。

 that just means our front end and we go into source because it's our source code and then components because these are react components。

 Then if we open up the modules and pages folders in the modules。

 we'll see ca happinessiness do J S X， which we'll be working in。 And then in。😊。

The pages' folder will see profile J SX。 And that's just because profile is an entire page whereas cat happiness is just a small subcomponent of a page。

So take a second， open up both of those files。And take a minute to read over both of the files and figure out like what。

 what we have right now before we're， don't worry about what we're gonna add。

 Just look and figure out what， what is being stored in these files。And why don't you。

Turn and talk to someone next to you。 show them either profile or cat happiness。

 and just tell them what we have in the file so far before we're adding anything。😊，Allright。

 hearing some good conversations， but I'm going to pull us back。

 so just to quickly recap what we have right now in our profile page is this is a react component and inside here we have the container for our avatar。

 that's our little Corgi boy。😊，And then here's our name and then the horizontal line。

And then here we have our flex box that contains all of the things that happen under the horizontal line。

 namely the about me section。And then what will be our cat happiness component， but isn't yet。

And then the section that says my favorite type of cat。

And then inside the cat happiness component right now， we have basically nothing。

 It's just a bunch of containers。Any questions on the code。Okay， so next up。

 we're going to add cat happiness。 so we want to add the cat happiness state to profile dot Js。

 and then we want to import the cat happinessiness component into profile dot Js so that we can use it。

 And we're going to add the cat happinessappiness component right here in our profile dot Js。😊。

And then finally， inside the cat happiness， if you have extra time inside the cat happiness file。

 then we'll take in a cat happiness prop。😊，Yes。So， the。Actually， I'll give。

 I'll give you a minute just to like， parse what we're doing。So basically。

 what we're doing in this step is if we have our whole profile page。And then within it， we have。

 you know， our profile， etc。And then within it， we have this component。

 That's just the cat happiness button。And this is cat happiness。That's our component。

Then remember that we said earlier that we want profile to store the state of cat happiness。

 Cat happiness being the number that we want to display here。😊。

So that means that profile is going to need to store。Some kind of。Cat H state。But then， in order for。

The cat happiness component to render it。 We need to pass that state down。

Into the cat happiness component as a prop。And so that's what we're going to do in this step。

 And additionally， we also need to add the cat happiness component to the profile。😊。

Raise your hand if you're confused on what we're doing in this step。O。In that case， let's get coding。

 I will give you guys a few minutes to attempt this， and。

Feel free to flag down one of the staff if you have any questions。

Hold up a finger or two or three or four for how many more minutes you think you need on this。

Alright， cool。 I will give another。2 to three minutes。Maybe three minutes， yeah。Alright。

 let's do another time check。 Give me a finger or two or three for how many more minutes you think you need。

😊，OK。I will give like one more minute， and then we'll pull back together。Alright。

 for the sake of time， I'm gonna have to pull us back together。 but I hear some really great chatter。

😊，Really great digestesting it。 Don't worry if you don't get it right away。

 youll have plenty of opportunities to practice this。 And by the end of Web lab， you will be a pro。

 so。😊，All right。So first thing that I'm going to do is add the cat happiness component here。

 This is a little bit out of order from the slide。 But generally， if I'm。

 if I have a component inside of another component， I'm just gonna add it and see what happens。

 So right now， I'm gonna add。😊，Inside of this div， the。A wait。嗯。I think I need to put。Another。

Subcon div in here。So that I can make sure that this cat happiness component。Fills in its own。

Little section of the profile page。 I'm gonna stick another。

Dive in here and then put the cat happiness component inside of it。

So this is what I would do if I just passed in a component normally。 And then let's see what I。

 and this is what I changed。So let's see what happens when I run this。I'm just gonna。Make this small。

On the side。Oh， wait， this is the example， my bad。I was like， why is it working。

 It's not supposed to be working。Okay， notice I get this white screen。 If I get this white screen。

 that means there's an error。 What you should do when you get this is open up the console。

 which you can do by right clicking， going to inspect。

And then opening up the JavaScriptscript console。 And then here。

 you'll typically see more detailed error messages on what exactly went wrong。So here， notice。

 I get this F error here。 uncutaught referencer。 Cat happiness is not defined at profile。😊。

Which means that it doesn't know what cat happiness is。 That means I forgot to import it。

So I'm going to import the cat happiness state， so my profile knows what to do with it。

So here at the top， I'm going to。Import cat happiness from。

 And then here I need to put the file path of the of the file that I'm getting this component from。😊。

And in this case。The current location that I'm at that profile do J S X is in is inside pages。

 This is， but the cat happiness component is inside modules， which is a different folder。😊。

So I need to， in order to get the file path。Of cat happiness relative to profile。

 I need to use dot dot to step back one directory into the components directory。😊。

And then from there， I can go into modules。 So slash modules。And from there。

 I can get the cat happiness component。And so now， after importing cat happiness from one step back into modules folder。

 Cat happiness at toX。Then， hopefully。If I reload this page。It is still sad at me。

 Why is it still sad at me。Cat happiness。嗯。Did I import this wrong。Your happiness is not defined。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_19.png)

But I actually have no idea what I did wrong here。Give me a second。Let me check the solution。Wait。

 that's literally right。 What am I doing。Oh， really。No。😔，Wait， I'm pretty sure you can put it。Okay。

 you know what。 I'm going to。Just keep coding for the sake of。Education。

 and then figure out what the heck I did wrong there in a bit。Okay， so next up。

 after we added the cat happiness component， we are going to。😊。

At our state to holds the number of the cat happiness。

 So cat happiness with the capital C we're using as the component。

 And then we're going to define a state for the similar thing。😊。

So we're going to do cont and then cat happiness， and then set cat happiness。😊，Is equal to u U state。

And then we'll set our default value to be 0 because we have0 K happiness to start。

And then we'll get the same kind of error if we just have this as is。

So we need to also import U state from react。 And so the syntax for this is we need to add。Brackets。

And then， import use state。So I added the U state import here。And then created a state here。

Any questions on this syntax for react state。Alright。

 then we' we're gonna actually use that state to pass down into cat happiness。

 So cat happiness component can display it。😊，And so I'm going pass it into the cat happiness component as a prop。

 So here I have my cat happiness component。 I'm going pass in。

 The cat happiness prop is equal to the value。😊，And then， here。

We're going to put our cat happiness date。Now， I'm。

 I'm apologized for the kind of bad naming where everything is named cat happiness。 But basically。

 this， cat happiness is our component。😊，And then we have a prop whose the。

 the prop name is cat happiness。And then we're setting that equal to。

And then notice here that we have to include the curly braces because we're entering a jascript environment。

 So we're inserting jascript into our H TM L， using these curly braces。And then。Here。

 we can put the jascript variable， also known as our react state， cat happiness。

So we'll take the cat happiness number from our react state， feed it into the H TM L。

 And then that's the prop value for the cat happiness prop for our cat happiness component。

 All the number of times I'm saying cat happiness today。😊，Any questions on this code。Okay。

 so just to summarize all of the changes I made to that I made to this code。

 I added the happiness component and passed in our state as a prop。😊，I added this state。

And then I imported all the necessary things up above。I'll give you a sec just to copy it down。

 if you need。I you know， I'm just going to keep going。

And then all we need to do now is we need to actually display the prop， like。

 receive the prop in the cat happiness component itself。

 because we're passing it in here from profile to cat happiness。

 or're not doing anything with it right now。 So I'll open up our cat happiness component here。😊。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_21.png)

![](img/74a0a92e8ed9c269dfb61ecd07d67249_22.png)

And here， in order to receive props， we just put the props。Here as an input to our function。

And then we'll display the count。 We'll display the prop。 So here again。

 we're using curly braces because we're putting in a jascript thing。

 That is our prop dot cat happiness。😊，And this is a jascript expression。

 So we need to put it inside curly braces in order for it to be inserted into the H T M L。

So this is how we pass a prop down。On the left side and then on the right side。

 you see as a child component， we're receiving that prop。Notice here that earlier。

 we talked about react components being literally just a function。 So we have this react component。

 that's a function called cat happiness that takes imp props input and spits out the corresponding H T M L for those props。

😊，Or like for the component， I guess。All right， next we are going to move on to the next step。And。

ぶぶルぶぶぶぶ。So right now， if we display this， which let me see if I don't have a bug。

And can show you guys。

![](img/74a0a92e8ed9c269dfb61ecd07d67249_24.png)

No， I have the same bug。 That's tragic。Maybe I misspelled something。Oh。

 I just forgot to save my files。 I'm trolling， guys， sorry。It works。 Don't worry， my code works。

So here right now， it's 0。 But obviously， if we click this， nothing happens。

 So that's what we're going to do next。 We're gonna implement the functionality。

 So when we click our profile page， the cat happiness increments。😊。

That's pretty straightforward to do。Okay。Now we're gonna get caught up。

 so get reset hard and get check out to the next step。I'll give you a second to do that。Alright。

 let's move on。y Daniel， we have a question。Oh， never mind。 Maybe were good。O。So。Next up for this。St。

 why don't you。Turn and talk to someone。 Actually， Wait don know。 I take that back。

 We're gonna change the cat happiness when I click on our profile picture。

 And so what we're going to do for this is we're gonna define a function inside of our profile component called increment cat happiness。

😊，And that function increment cat happiness is just going to take our cat happiness and add one。

 prettyty simple。😊，So we're going to write that。 And then we're also going to implement。

The code to call that function any time we click the profile picture。

And so the way we're going to do this is that in H M L， any div has an onclick attribute。

And that attribute takes in a function such that when you click on that div in the H T M L。

 that function will be called。And so， we want to run that。

Like input the increment cat happiness function to the on clickick of our div。

But before we get into that。We're going to think about how we might implement this。

 So these are all partial implementations of this step。

 And I'll give you a minute to read the code and think about which ones are valid ways of implementing this。

 Which ones will work and which ones won't。Alright， now talk to someone next to you。

 What do you think。And we're assuming here that increment cat happiness is just what I described earlier。

 a function that。😊，Increases the cat happiness by one。Alright， I'll pull everyone back together。

 Let's take a poll。Open hands if you think A works， close hands if you think it doesn't。

Open hands close。 Okay， O， we're getting a mix。 How old for B， Open hands， if you think it works。

 close hands if it doesn't。Okay， mostly open hands。 Now， see， open hands for yes。

 close hands for no doesn't work。Alright， also mostly open hands。D。Open hands are close。 Open hands。

 if it works， Close hands if it doesn't。Okay， a lot of。Cllosed hands。 That's good。

So the correct answer is that A， V and C all work。 D does not。

D does not work because we are calling the increment cat happiness function and passing whatever that function returns into the oncl。

 which is not good because increment cat happiness probably returns like undefined or something。

 And so what we're passing to the on clickick is useless。😊，But all of these A B and C all work。 now。

 if you notice。A here is a function that takes in nothing。

 And what it does inside the function is just called increment cat happiness。

 So it's literally exactly the same as C。😊，But just a lot more verbose code。

 So C is a much cleaner way of writing what you might want to do in a。And then， B is just。

Rather than going through the increment cat happiness method。

 we're just directly using the react stay set to set the cat happiness。Okay， so without further ado。

 I'm gonna have you guys implement this。 So implement the increment cat happiness method and then call that method。

😊，Whenever the profile picture is clicked。I'll give you like two minutes to attempt this。

 We'll be walking around if you have any questions。Alright， show fingers。 How many what people need。

All right。Cool， I am going to。Get started， though。Alright。

 it seems like people are nearing on being done， if not done already。

 So I'm going to pull us back together and。Implement this。

 So we're not gonna need cat happiness right now。 We're just gonna be in profile do J S X。

And so here we have our function， increment cat happiness。

 All we want to do is call the set cat happiness。😊，Method。And then what do we want to set it to。

 Well we want to set it to the old cat happiness plus one。 So that's what we're gonna do。😊。

So this is how we increment our cat happiness function。And then。

In order to make this function called any time we click on our profile picture。

 we're going to go to this div here， profile avatar container。

 And we're going to give it an on clickick attribute。 And remember。😊。

We're using these curly braces to enter a JavaScript。

 little mini to evaluate a JavaScript expression。And so here we're going to put in the function。

 increment cat happiness。😊，So here is what I changed these two lines。And then。If we run this。

And we click on our profile picture。And our cat happiness increments。Yay， it works。

Any questions on this code。All right， we're all set then。

So if you want to check out the finished app and you weren't able to get there。

 feel free to get check out W1 complete。But otherwise。I'm going skip this recap。For the sake of time。

 And after this， after a quick break， we're going to talk a little bit more about the react life cycle and hooks。

Okay， real quick。Just open up the feedback form。 And you can give Sova and I feedback on the workshop。



![](img/74a0a92e8ed9c269dfb61ecd07d67249_26.png)