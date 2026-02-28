# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p25 -25-MIT web.lab (6.962) - Day 6_ Advanced React (Context).zh_en -BV12Ux5zTE9p_p25-

够。Hi， everybody。I'm Daniel。Again， and I'm gonna be talking in this lecture about react more about react state management and about react router。

 So basically， react has like a bunch of helpful packages for you。😊，嗯。

And helpful like functions for you。We haven't talked about yet in this class that will help you make。

Potentially make your projects a lot easier to code on the front end。 So today。

 we're gonna be talking about some of just a few of those functionalities。



![](img/636a6d73a301372002f1cf1a24cb856c_1.png)

Specifically， we'll talk about use context in react。

 and we'll learn more about react router and the react route tree。And our goal is to kind of。

Expo like a few of these concepts to you。 And maybe then you can like try to look towards like react documentation or whatever that may be to like。

 help aid you even further in your projects， essentially。Yeah， so first。

 we'll do a quick recap of what we've learned so far about react state management。😊。



![](img/636a6d73a301372002f1cf1a24cb856c_3.png)

So the main tool that we have for react state management so far is U state。

And the way that this is generally set up is that first， we like at the top of our document。

 we need to import use state。Inside every single document。

 we create a state and a set state function using the U state hook。If we want to。

 we can call the set state function in order to change our state at any point。And then in general。

 if we want to pass this state into a child component。

 then what we need to do is pass it in as a prop to our child component。

 and then our child component will be able to access it using the props that is passed into it。

Here we pass in the name as a prop to child component。 And then it's able to use name as a prop。



![](img/636a6d73a301372002f1cf1a24cb856c_5.png)

过。O so。Let's imagine that we have this following react component tree， where。We have our。

We have a state called name in our top level component called app。

 But then we use the same state all the way over here。In Aric。In the component G。Then what happens。

Is we have to pass this name crop all the way down from app to。F here。

 potentially another component all the way down to G。 So then。

We're kind of every single like step of the way。 We're passing this names state as a prop through。

This can get a little messy。 And just to go through how it can get messy。

 we'll go through a little bit of an example of what we like don't like， what maybe we wouldn't like。

So this is my Google homepage。 So we'll just look a little bit at like the Google website since it's like a pretty simple example of a website。

嗯。O， yeah， so。Yeah， so the top layer of any website usually is generally the web page。

But if we were to like code this and react， then we want to like look at what the next level layers are beneath the web page。

 So maybe the next level layers， maybe a few of the things in the next level layer。

 This is probably not all of them。 I， I wasn't even really looking at the search bar。

 but just a few of the examples are maybe the nav bar at the top or the modal that pops up when you click on your profile icon。

 That might be another thing that is managed by the top level thing。Okay， yeah。

 so a few of the third layer things beneath that， all of the all of the icons on the top。

 But just an example， we might need thev， the Navbar icon with our profile picture。

We might need our main icon area that says hi Daniel here。And we also might need like。

 the other accounts section。That might be its own component within the modal。

 where we show all of our other accounts and。嗯。And like allow ourselves to like click on the other accounts and log into them。

 basically。Yeah， but the problem here is that all of these components might need to like access our current user or change our current user。

So， if we're passing in。Are if we have a user state and like a set user set function。

 then we kind of need to pass in this user and the set user function as props into like a bunch of different components。

 So like， we're passing in like props dot user equals this user name and then props dot set user。

As another function。 And then it just becomes really messy really quickly。

 because you can imagine if every single one of our components had like 7 props passed down into it。

 then your code would just look like this like for every single time。

 every single time you wanted to write like。😊，Every single time you wanted to write。

Like any component within your N JS X， basically。 And generally。

 we try to keep our code shorter when possible， so。Yeah。

 we don't want our coach to just get messy like that。And basically。

 react has kind of a solution for this， which is called context。

 So context basically provide a way for the higher level components in our tree to communicate。

One state or potentially multiple states that it keeps track of to all of its sub components。

So you can think of it as basically the sub components getting some context as to like what the higher level states are without the higher level states having to or without the higher level components。

 having to pass down everything all the way through props。



![](img/636a6d73a301372002f1cf1a24cb856c_7.png)

Yeah。So， of course， we would probably have to see it in code to understand what was actually going on。



![](img/636a6d73a301372002f1cf1a24cb856c_9.png)

So here's an example of code without use context。So as you can see in this code。

We are making a user state。And we're initializing it as my name。

 And then we're passing the user stay all the way down。And through a component。

Starting from component 1， all the way into component 2。

And then into component 3 and then all the way into component 4。

 And we're passing it down through every single every single layer。And then finally， in component 4。

 we use the state。So。

![](img/636a6d73a301372002f1cf1a24cb856c_11.png)

If we wanted to save some。Save ourselves the hassle of having to pass it all the way down。

 What we could instead do is outside of our component， we create a context。Called user context。

 But we can， Well， we can call whatever we want。 This is a helpful name to tell us that this is keeping track of the user。



![](img/636a6d73a301372002f1cf1a24cb856c_13.png)

Then inside component1， we wrap the content of component1 in what we call a provider。

 and every single context that we use using create context has this provider element。

 And this allows us to wrap everything。 it's essentially just an element。That does nothing on the。

 like visually， but。嗯。Like， it allows everything inside of it to see whatever it's providing。

 And here， we're providing the value of user。So providers have a special keyword called value。

 And here we。Like， basically， we give it a Json object where like the user is our user state。Yeah。

So yeah， one thing that you'll notice here immediately is that component， too。

 we don't need to pass a user prop down into it。 So in the previous code。

We saw that we needed to pass a user prop into component 2。Here。

 we don't need to pass anything down into component 2。

 It'll already be able to know what user is as long as we use the context that is wrapped around。

And in order to use the context， what we'll do。Is we call the use context hook。using。User context。

 And then this will give us whatevers in the value thing。

 So this value thing is a Json object with one parameter。 We pull out that parameter using dot user。

 And then now we can use it。

![](img/636a6d73a301372002f1cf1a24cb856c_15.png)

Yeah， so an analogy。That you can think of is that like you state might be like a piece of information。

Which is our like user and our set user。 We can change that piece of information， if we want to。

But our use context is kind of like an empty book that you can write in that a lot of people have access to。

 In particular， everybody like below you in your subt can can access。That。

 that piece of information that you write into that book。 then the。

 the provider is kind of just like the library that you can check out the book from。

 And so if you wrap everything around like this provider， then like。

Everything like that can access your library can now check out this book and read what's inside of it。



![](img/636a6d73a301372002f1cf1a24cb856c_17.png)

过嗯。I think。Yeah， I'll stop。 I'll stop for like 30 seconds， maybe。

 And you can take a look at this code， make sure like everything makes sense。

 If you have any questions， feel free to ask them right now or in the question stock。



![](img/636a6d73a301372002f1cf1a24cb856c_19.png)

哦， yeah。Yeah， they can be in completely different files。

 So the only thing that matters here is that component 4 is within the tree of component 1。

So everything that's like a sub componentonent of component one or sub componentonent of that or so on and so forth should be able to access anything that component one wraps in a provider。

Yeah。Yeah。嗯。This is kind of like a dummy example we'll see in the workshop that like you can even define the user context in a separate file from your like component as well。



![](img/636a6d73a301372002f1cf1a24cb856c_21.png)

Okay， cool。Moving on， we'll do like a little bit of a review kind of of like how the component works and how you use context specifically there。



![](img/636a6d73a301372002f1cf1a24cb856c_23.png)

Yeah， so here's an example component tree with app as our top level。😊。

Let's say we define a context around a where we set our happiness to 6。Okay。

 so how many components will we know will know like what。Our happiness is maybe like。

 give a give like a number of fingers on your hand， like  one to 5。 Like， what do we think。😊。

For how many how many components in this， this component tree。O。Cool， yeah。

 I see like mostly fours and fives。 Yeah。 So if we include a， then the answer is 5。

 if we don't include a， then the answer is 4， but it's gonna just be everything but like A and below。

 the other side of the tree won't know what like our context is or what's inside of our context。

 But it'll be A， D G and H。😊，Yeah。Cool， and then maybe you have the question。

 if we can have multiple contexts， maybe something like this where we have one use context that's wrapping everything or underneath A。

 And then another one that's wrapping under everything underneath C。😊，Yeah。

 so we can definitely do something like this。 There's something that like really prevents us from doing this。

 We just have to define two separate contexts and two separate providers， basically。



![](img/636a6d73a301372002f1cf1a24cb856c_25.png)

过。Okay， any questions before moving on， we're gonna move on to like a different topic entirely。

 basically。

![](img/636a6d73a301372002f1cf1a24cb856c_27.png)

O。So we're going to talk about react router now。You've already seen react route。

 We kind of talked about a little bit in workshop， too。

 but we're gonna dive a little bit deeper into how react route works。 basically。 and what like。

Maybe you saw like a router or a router provider or something like that。 And you were like。

 I don't know exactly what that is。 But we'll kind of talk about what all of those are right now a little bit。



![](img/636a6d73a301372002f1cf1a24cb856c_29.png)

So this is our code from Workshop 2。And we created this like router kind of thing。 And then we like。

 rendered it into like， the element。Anytime you want to use like any package， basically， but。Here。

 we're using the react router Dom package。 You need to import what you want to use from it。

Here were just importing these packages or importing these functions that you don't really have to worry too much about。

呃。The router setup is in line 17 through 24。 And the first two lines generally won't ever change。

 So you don't have to really worry about them。 And then we kind of create the route。

 We create the router based on what's like inside of this。Component like3 almost。 And then。Finally。

 we render the route into， into the document by using this getting the getting element by I D of the route and then rendering the router provider into it。

 Yeah， so the funny thing here is this router provider is actually a context provider。

 And it like basically。😊，Allows everything inside of our router provider to see anything about the URL that we want to。

 So like the URL is kind of like what is being provided in the context right now。

 So everything inside of our router provider can see the URL。

 So that's like a like funny fun link to like what we just talked about with use context。

 So router providers like using some kind of use context in the background to like kind of provide this information to all the subcomp。

😊。

![](img/636a6d73a301372002f1cf1a24cb856c_31.png)

Yeah， so let's zoom in a little closer on the router declaration。

 So this is the react route tree and all our pages that kind of exist here。嗯。

And if we take this route tree， we can kind of transform it into like this tree as follows where we kind of represent green elements using like green and then air elements using red。

 So here we have the app and not found at the top。 And then below it。

 we have two components feed and profile that exist at the paths。Just slash into slash profile。

So if we continue with this example tree， router elements are always gonna be rendered starting from the root。

 So even at local host 5，1，7，3 slash profile， we try to render profile。 But in order to do that。

 we have to render app first。So what does that mean exactly， If we go into the app code。

We see like this outlet thing in Appdot J S X when we return and。

You might wonder like what the outlet is doing。 You can essentially think of the outlet as like a placeholder。

 like component。So when we render at slash profile。

 this outlet will be replaced with like the profile component。 So here， if we navigate to localhos 5。

1，7，3 slash profile， we'll see that the outlet that was previously here is just gonna basically just。

😊，In essentially be replaced with the profile component。

 And then if we instead navigate to localho 5，1，7，3， then we'll be rendering at the slash thing。

 So we'll be rendering feed。 So this outlet component is gonna be replaced by feed instead。

 And so like you'll just see two different component trees at these two different routes。

 essentially。😊，Because thatlet is。Acing as a voice holder。Cool。

 and the nice thing about this is that no matter where we navigate to。

 we always see the nav bar at the top。 So that's like the important part here。

 which is like what makes like the like outlifting kind of nice is that no matter。

 like whether you're a profile or fade， you always see like the same nav bar at the top of your page。

😊。

![](img/636a6d73a301372002f1cf1a24cb856c_33.png)

Okay， cool。 If you wan to pass props into outlets。It kind of works。

 as you might expect from the parent side。 So you pass in this my test prop， maybe。

 and then you feed it some parameter。 and then from your feed。Before you would maybe like if。

 if you weren't like in some router sort of tree， you would just access this prop using prop my test prop。

But it'll look a little bit different in react router when you're passing through this like。

Route component instead。 So here， if you try to console log， this， it won't work。 Instead。

 what we do is this， we use the use outlet context hook。 We haven't seen this yet。

 but it might be useful in your project if you ever want to pass in like the same prop into all of like the sub components of your route tree。

Essentially， we just replace props with the use outlet context hook。

 and we're able to access the My test prop parameter。😊，Any questions here。

 I'll go back to the slide and pause for like。30 seconds， yeah。Yeah。

 so whenever you want to use react hook， you generally want to import it in the file that you're using it。

 And so here this is in feeddot JSX。 So we'd probably have to import use ala context at the top of feed dot ASSX in order to use the hook。

Any other questions。

![](img/636a6d73a301372002f1cf1a24cb856c_35.png)

Cool， okay， moving on。

![](img/636a6d73a301372002f1cf1a24cb856c_37.png)

Yeah， so now we'll talk about how the route tree kind of gets transformed into routes。

A path to the route is essentially like the concatenation of all the relative routes along the route。

So。Just as an example here， we have this like slightly more complex tree。嗯。

If we navigate to a local host，5，1，7，3 slash profile slash Alice。

We'll be rendering profile A because we'll travel down from the root to slash profile and then to slash Alice。

 so。Well be rendering whatever happens。 And we try to like， we'll be rendering whatever the tree。I。

With like just starting from profile A， essentially， yeah。

And then we didn't talk about error elements yet， but error elements essentially catch when the paths don't match route valid router paths。

So here， as an example， local host 5，1，7，3 slash game。We'll be building a game in a later workshop。

 But so far， we don't have one out yet。 So right now， if we try to navigate here。

 it'll just render the not found element。Because starting from a route， it doesn't see anything。

That's slash game。O。嗯。So， yeah， I have another question for all of you guys。

 So what would be rendered， Which one of the components would be the one that is rendered at local host。

5，1，7，3， slash profile slash Charlie。 Would we see feed not found profile or user not found。

 Maybe like again， finger， like 1，1 for feed，2 for not found，3 for profile and4 for user not found。

 What do we think。Cool， yeah， I saw like basically all fours。 Yeah， that's correct。

 We'll just go for it。 We'll go start from the root。 We'll go to slash profile， and then。😊。

In slash profile will。Try to go to slash Charlie， but it won't exist。 so we'll see a user not found。



![](img/636a6d73a301372002f1cf1a24cb856c_39.png)

Co， if we were to write this tree out in code， it would look something like this where we have this inner profile。

 like tree， where there's a slash profile here and has an error element of user not found。

And then beneath that， there's kind of two。2 sub sub browses， essentially。Yeah。

 this is the first example that we've seen of like a route router tree of depth more than one。

But I'll kind of skip past this。 And if you want to look more at it， you can come back to it later。

 But yeah， kind of this。This code is just going to map out into like this tree， basically。



![](img/636a6d73a301372002f1cf1a24cb856c_41.png)

Okay， if we wanted。Let's say I wanted like a lot of profiles。

 And I didn't want to hard code every single one as a react component。

 Like if a user creates a profile on my website， I'm not trying to like go into my source code and then add another file with another like component saying like profile C or something。

 So the dream scenario is that like s profile slash Abbbby reads Abby from the URL and then passes in it passes it in as a parameter to like the profile component。

 And I only have one profile component that can kind of manage like。😊。

Manage whatevers inside of it using the props that's passed into it。Yeah。

 so the nice thing is that reactor router has a functionality for this too。 Of course， it would。😊，嗯。

Here we have。Slightly different react。Rooututer tree， where。We were the second。

Route that we define has a colon name。Tag at the end of it。

 So this colon name part is a dynamic part of the path。



![](img/636a6d73a301372002f1cf1a24cb856c_43.png)

And so what that means is。This will be passed down as a parameter for the profile element to be able to access。



![](img/636a6d73a301372002f1cf1a24cb856c_45.png)

So how do we get the name in profile dot J S X。嗯。We just kind of add it at the top。Here。

 let's say this is， this was our code before in profile dot J S X， where we didn't feed a name down。

Now， if we were。We use this use parameters hook in order to kind of retrieve whatever in the URL。

So we just do， we just write constant name equals use parameterss dot name。 And this。

 in this dot name part， will'll just look for any colon name。Part of our URL。

And then it'll replace that with。Like whatever is passed in。 And then here。

 maybe we just like set the document title to like names profile page instead。

 So what happened here is basically if we went to slash profile， slash Abbey。

Then when we access use parameterss， it'll have the name parameter as Aby because we've replaced our colon name area with Aey and it act as a dynamic part of our route。

 Now， when we navigate to slash profile， slash Aey。

 we'll see Abby's profile page as the title of our document instead。过。Yeah， that's。

 that's kind of the last part of it of my lecture。 So are there any questions about this。

I'll leave it up forick。a bit as well。哦， yeah。Yeah， so let's say you。

Wanted to pass it more than one parameter。 you could literally just do something like slash。

Call the name。 and then。Slash colon， like。I D or something。

 And then you can like just access it using use parameterss dot name and usepre do I D。

 like you can just retrieve the two parameters from there。 essentially。

 any like anything in your URL with a colon in front of it， you can retrieve like just using。

Using use PRs and then retrieving the name， the same thing that you put into the URL。

 Basically here we put colon name。 So we retrieve it using dot name。Any other questions。



![](img/636a6d73a301372002f1cf1a24cb856c_47.png)

And so the last kind of comment that I wanted to make。I'm gonna skip the wrap up。

 Is that like there's a bunch of resources out there for you to be able to learn these things yourself and react has a bunch of other useful hooks for you to use in your project。

And you will probably find reading documentation pretty helpful for you to be able to incorporate like interesting functionalities into your front end。

 So just here are just a few links for you to like maybe learn a little bit more about these things if you want。

 But yeah， if you ever like are wondering anything。 you can always look towards documentation。

 ask stack ask people on stack overflow， like things like that。 Yeah。

 there's a bunch of resources out there。 So yeah。

![](img/636a6d73a301372002f1cf1a24cb856c_49.png)

嗯。Willll be moving on。 But before that， if you want to go to Weblab do slash feedback and。

Give me some feedback on the like。On a lecture， yeah。



![](img/636a6d73a301372002f1cf1a24cb856c_51.png)

But yeah， thank you guys。