# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p08 -08-MIT web.lab (6.962) - Day 2_ Intro to React.zh_en -BV12Ux5zTE9p_p8-

Alright， so today we're gonna be doing Intro react。So react is another front end framework。

 and it's not entirely distinct from H M L CS， S S。 You'll be using the same concepts。

 but it's the framework we'll be working with for our final projects。

 and the framework that he's sort of everywhere in Web do。



![](img/cf68d6d3909cad706202c4068eec885a_1.png)

But just to recap， let's talk about HTML L C S S and jascript again。 So if you remember the analogy。

 we have HTMLl the skeleton。 C S S is the styling， and then ja makes everything work。



![](img/cf68d6d3909cad706202c4068eec885a_3.png)

So， for example， we can talk about like the Facebook website again and。



![](img/cf68d6d3909cad706202c4068eec885a_5.png)

We have the Facebook website， the first section might look like this where we have a friend section。

 which has a bunch of divs with a couple different classes where styling also includes images and things like that。

And maybe just as a warm up。 turn and talk to someone next to you about what the main feed might look like in terms of the H L。

 so it might look something like this。And so we kind of have a lot of different nested boxes here。

 We have to have a couple different， a couple different classes for all the different headings that's going on and all the different styling and。

嗯。In essence， it's kind of really messy。 And if you ever open up just developer tools on any random website on the Web。

 you'll notice that it looks， there's a ton of divs。

 And if you want to like get to what you're looking for， it's just a whole big mess。



![](img/cf68d6d3909cad706202c4068eec885a_7.png)

嗯。So it would be really nice if instead of having to write all of this up。

 we could just write like one line and say build Facebook。 But， of course。

 that doesn't make any sense because we actually have to tell we have to write down what we want Facebook to look like。

 And so。😊，The idea here is we sort of want to have some sort of modular framework where we can build Facebook by just writing down the tag Facebook。

 but to write down the tag Facebook， we can define it in terms of other tags like the nav bar the friends feed。

 the friends and the posts in your feed。 And if we have some sort of framework where we can do this sort of abstraction where we're able to sort of call some new custom Hl tag and then use that to render part of the feed。

 then we can make our codebook a lot nicer because we can build it build it in modules and it can also help us with reability if we have different modules that are repeated。

 for example， in the feed， therell be posts that are repeated over and over。😊。



![](img/cf68d6d3909cad706202c4068eec885a_9.png)

And it would sort of like continue down the tree。 and you would define each of these new fake H T L tags like Nav bar friends and feet in terms of other fake H T L tags or just raw H TM L。



![](img/cf68d6d3909cad706202c4068eec885a_11.png)

So this is sort of the whole idea behind react， which is a library that's used everywhere for building your front end。

 And these fake HM O tags that I just mentioned are what's called components。

 And these are the building blocks， building blocks for react。



![](img/cf68d6d3909cad706202c4068eec885a_13.png)

So components might look， components are something that you name yourself。

 And so they can look anything like Facebook now or post or feed， but it can be any name you want。

 But generally you you'll want to name it something that actually makes sense。And。Yeah。

 so but what exactly is a component。 Well， it's some abstraction that tells you how to render a certain part of the website。

 And it's very general。 You can do sort of anything you want with any frontend you want with it。

 because within a component， you're rendering all the H L C， S S and jascript at once。

 You can define the actions that happen when buttons are clicked You can define how it looks and you can define the actual structure to the HM L。

 And it's all neatly packaged into one component that you can reuse and call to build a part of your website。

And it's sort of， it's sort of like a function that function in jascript。

 As as Abby was talking about in the last two lectures， you call on this component。

 and then it returns part of your website for you。

![](img/cf68d6d3909cad706202c4068eec885a_15.png)

So sort of going through Facebook， we can sort of talk about what the components might look like。

 So the root level component is called app。 And this is just everything in， in your website and。

I'm gonna be using a bunch of dash boxes here sort of to show how the modules appear on the website。

So within this total act component， there is gonna be a number of different components like the nav bar。

 the info bar， which has all your friends and things like that。 and then your feet。

 which has all your posts。And these components can also be further broken down。 For example。

 the feed component can be broken down into further smaller components that you build。

 like the post components。And these post components can be broken down into even smaller components。

 such as the actual content of the post and the post body and comments that appear below it。

And you can sort of see that there's like this dependency。

 Each component depends on other components that make it up。 And the structure is a bit like a tree。

 And we call this the component tree。 And so it kind of makes sense why the app component is called the root because it's the root of the tree。

 and the arrows indicate dependencies。 So app depends on the three components now bar feed and info bar because that's what's see to build it。

 And the feed depends on posts and posts depends on the content and the comments。



![](img/cf68d6d3909cad706202c4068eec885a_17.png)

![](img/cf68d6d3909cad706202c4068eec885a_18.png)

So。Basically， in summary， the main idea of react is having these components that depend on other components。

 and that can be reused。 So these are all like function calls。

 And you call on the function to build a part of your website。

 And that makes it really nice because now you can see what your website looks like when when you're writing up this website instead of having a bunch of divs。

 instead have postbody， which is composed of posts and comments。

 And then a feed which is composed of post bodies which is composed of posts and things like that。😊。



![](img/cf68d6d3909cad706202c4068eec885a_20.png)

![](img/cf68d6d3909cad706202c4068eec885a_21.png)

And within each component， you can put whatever HTML C S S jascript you want to have have any sort of front end functionality that you need。

So that's the summary of how components work in react。 But to actually make them work。

 there's a couple key features that we need to know about。So， for example， if we have a comment。

 even if we want to reuse even if there are a bunch of different comments which are approximately the same。

're not， they're not entirely the same。 So they don't have the exact same H T M L。

 So we need to be able to generalize it。And。The way we're going to be doing this is or sorry。

 to start like the things that can differ between comments are things like the actual content of the comment author of the comment when it's posted and even the profile picture。

 But the general structure of it's the same in terms of how the H elements are ordered with respect to each other。

 So to be able to reuse this。嗯。We use the skeleton where we have the same structure and like the likening reply button is the same。

 We want to have some sort of。Inputs to our common。 And these are what are called props。

 So just like your functions have inputs， your components also can take in inputs and then render。

 render part of your website based on those inputs， so。这 for our。So for the case of our comment。

 since we want to have the author name， the actual content of the comment。

 the picture profile picture and the date posted to vary along the comments。

 we can pass in these props， these inputs to the comment component and then get out a comment that we want。

So this sort of structure where we have post， which depends on comments is we call the one where the arrow starts the parent and the one where the arrow ends the child and props are passed from the。

 from the parent to the child， indicating what they want the child to remember。

So when you add in the， when you add in the props of Kenny Choy and the comment and then posted a minute ago。

 then you can render the comment that you want。One thing of note is when you pass in the prop。

 you can't mutate the prop on the side of the child， because。Where you can do， you can edit the。

 you can do things with the props。 So just like if you in a function and you say you take in a number。

 you can do calculations of that number， but you can't change the number itself。

 So these props are determined within the parent。 and it's passed down to the child。

 and they can't be changed。By the child。And also， another thing is you also can't pass the props from child parent。

So the main thing with props is it lets us generalize these react components。

 And if we have a component which has parts of it， which are variable。

 then we can pass in these variables。 It tends to get how we want it to render。

But that's how we actually render something that changes over time。

 But how do we actually keep track of what's changing on the website。

 Because these problems are not mutable。 And so if our website is updating over time。

 let's say more comments are flooding in， then we need a way to keep track of what we want to render on our website。

To this， to do this， we're gonna use something called the state。

 So this is the second important part of react components。

 And these are sort of actually just the main two props in the states。

So state is some sort of information maintained by a component。

 It's not something that's taken in by a component。 and it's something that's mutable unlike props。

 And it's something that you can update with， with whatever logic you want within your jascript。走。

For example， in the case of our posting comments。Within the post。

 we can maintain the state which has a list of comments， so。We can have an array。

 which contains like the first comment。 and then another comment adds just maintain a state of comments which can change over time。

And we use this state to pass down props to the child components of the comments。

 And once we pass those down， the comments can render。

 the comment components can render the comments that we have within the state。So。

W do we keep the comment data in。The post state and not the common state。嗯，我。

The post state is sort of the larger component， and it contains all the comments。

 And we want to know which comments to render whens the post state。 So if we， if we maintain。

 we can't maintain these within the common states because we don't know。How many comments to have。

 So， for example， if we add another comment， then we don't have another another comment component where we can store that state。

So we need to have in the post state so that we can actually render like the X number of comments that we need。

So in this example， like if we add another comment。

 we need to be able to render that additional comment。

 But if we didn't have the state within the post， we wouldn't be able to do that。

We can go through another example of using states and props， so。

There's a feature on Facebook where you can hit view replies。

 So comment and you interact with it by clicking on the button。

 and the website needs to adjust by rendering these comment replies。是。

T to talk to a neighbor about which of these options is best for showing comment replies。Alright。

 so in this case， the best thing to do is to store the state show replies within the comment within the common component。

 So this is the same structure as the previous one， except now。

 our common component is the parent component， and it needs to maintain whether or not to render the replies。

 which are its children components。So if we， we maintain this show reply state within the common component。

 and we can toggle it to be true or false。 And then if it's true。

 then we'll render its children components， which are the replies。So as another recap。

 the state is some information that you store within a component， and it is just what it is。

 It stores the state of the component， which determines how it renders things and how it renders its children。

And it's mutable。 And you can use the states and pass it down into children components as props to determine what to render。

And。Here's an overall review of what's going on here。 And we have states and props。 Again。

 the states are passed down into the children's components， and it renders。



![](img/cf68d6d3909cad706202c4068eec885a_23.png)

Okay， so that's the basic structure of react and react components。 Are there any questions so far。O。

If not， then。I'll pass it off to some of it。

![](img/cf68d6d3909cad706202c4068eec885a_25.png)

是。The national practical application。Okay， cool。 So we've seen a little bit about how react can help you with abstraction。

 as well as usability with components。Making your websites like a lot cleaner to code up。



![](img/cf68d6d3909cad706202c4068eec885a_27.png)

So let's see how that actually looks like in code。And my workflow for this is gonna be kind of starting with like the hard coded version where we're like directly writing in like all the information。

 you'd need to render something。 and then like slowly like rolling it back and abstracting it away。

So let's start with this pretty simple component here。It's just a common reply。

 not too much information。Critically， it's just like the name and the content。嗯。Yeah。

 so let's look at the code for a general react component。

 Three things that you're gonna to need in every file that you write。 First。

 you need to import react。 again， react is a library。 It's not built into jascript。

 So you'll need to first import react。 We're also gonna import this U state thing。

 that's going to help us with maintaining state more on that later。Next。

 we have to actually define our component。So I want you to start thinking of these components as functions。

And a function is just like a fancy name for something with inputs and outputs。 right。

 Our inputs in this case are gonna be whatever props are passed down to us from a parent component。

And our output is just gonna be what we render on the actual page。Finally。

 we have to export the component， and this will let us reuse it in like top level。啊， componentson。

So again， I want you to start thinking of components as functions that take in props and then output something to be rendered。

As Evan mentioned before。A reacting component kind of bundles together a bunch of jascript logic。

 as well as Htl rendering and as well as C， S。So。Going back to the function analogy。

 you can think of like the logic of the function as all the jascript。

 And then what you want to render is something called JS X。 It's kind of similar to Ht L。

 I'll explain it a little bit。And a bit。But that's the general idea。

So let's try to render this comment reply。As you can see。

 it looks very similar to what we've done before。We'll just create a div。And then， again。

 we're hard coding right now。 So we'll just add in the header and then some text。But， of course。

 this isn't what we want our end goal to be。 We want to be able to reuse this component for like any arbitrary name or a common text。

And this is where we use props。Okay， if youll recalled。

 props are just like an object that's passed down into your function。

And the way that we extract information from objects in jascript is raising this dot thing。

So we'll just do props name， props content。And now that we've done that。

 we've removed all the hard code away。 We can easily reuse this component to render at least the name and the content。

Okay， so right， what is JSX。I mentioned that it's very slimmer to H Tl， and it is。

But there are a couple of differences。So one difference is that。In J S X。

 you can actually escape into jascript as well。 if you want to do some logic within your component。

 So， for example， you can see here。Within the curly braces。

What's going on inside of there isn't actually Htl， right。

 It's jascript because we're unpacking something from an object。So。

Anytime we want to like extract something from props， we'll have to use these curly verses。

Also notice that instead of class， which we would normally use if we wanted to like style something with C。

 S S， were using class name。 And that's because class is like already a thing in jascript。

 So we can't just。Is the same thing again。嗯，第二。But yeah， for most purposes。

 you can kind of think of them as the same thing。Just remember those two things about escaping so that you can use ja。



![](img/cf68d6d3909cad706202c4068eec885a_29.png)

And class name。Okay， right。 So we've talked about props a little bit。

Let's move on to talking about state。So in our component。

 we had two things that could easily be passed down from the parent into this component。

But something like a like button， it doesn't really make sense to store that in the parent， right。

 because we can just do that in each modular comment reply。

So how about we let this component maintain the state by itself。The syntax for maintaining state is。

 as follows up here。 and you'll get some more practice with this。

 So don't worry if you don't understand it at first。But the idea is to initialize a state。

You'll read con， and then you'll have to put the state variable。As well as the state center。

The state variable is just like the state itself， and the setter is a function that can like mutate the state。

And then you set that equal to U state and just like initializing it。 And then within those。

Apprenheses over there is the initial value。So this is like initializing is liked to false。

 and it's also giving us a function that can change it。

So let's use our state to render like function。There's some styling missing here。

 But the general idea is that we just want。If is liked is true， then we display liked。

 And then if it's not， then we put like so that you can like it。

The syntax that I have here might be new to some of you。But again。

 we have it in curly braces because it's in jascript。 It's ja logic。But。

 so the statement is called a ternary。 And it's just like an F L statement。

 but like written a little bit more clean or not clean， depending on what you like。

But you'll put the condition here， then a question mark。And then if the condition is true。

 then it'll return this。 And if it's not， then it'll return that。So if， is liked is true。

 then we're gonna display liked as we want。 And if it's not， then we're gonna put。And now。

 skipping little things， we have a nice component that we can reuse。



![](img/cf68d6d3909cad706202c4068eec885a_31.png)

And yeah， it doesn't matter。What the name or the message is， we can use this for basically anything。

Okay， I'll stop for questions。A quick。

![](img/cf68d6d3909cad706202c4068eec885a_33.png)

O。Cool， now that we've written our first component， let's try to work through an entire web page。



![](img/cf68d6d3909cad706202c4068eec885a_35.png)

So the first thing what we need to do is understand like the structure of this thing。

 So let's try to work through and generate the component tree that Evan was talking about earlier。

In any web page， the root is gonna to be just this app component， which willll contain everything。

And let's try to look for some other components in here。

Though some things that we can think of are first the nab bar。 That seems like it's pretty modular。

 and we might want to abstract things away in that。The intro seems like it can also be。

Combinine into like one specific component。Os would be nice to keep。Otracts it away。

 And then post is definitely something that we want to reuse like many， many times， right。

That's a great candidate for a component。Here's what a tree looks like。We have app at the top level。

 and it depends on all of these different components here。



![](img/cf68d6d3909cad706202c4068eec885a_37.png)

To reiterate， react components are powerful because they can help us with abstraction and reusability。

And again， abstraction means。Like。Putting a bunch of things into like a black box that you won't have to look at like fine details and stuff。

 But you can reuse it by just like。Importing it and then like writing down like the， the name of it。



![](img/cf68d6d3909cad706202c4068eec885a_39.png)

And reusability， I think， is pretty clear。So yeah， Navbar， intro and photos。

 They're all great to keep his components because you'll abstract away like messy code that you don't want to like look at every time you look at your web page。

😊，And post is helpful for both abstraction， as well as usability。

 because we're gonna have many posts on a single page。



![](img/cf68d6d3909cad706202c4068eec885a_41.png)

O。And again， my workflow for this is going be starting with like the hard coded version and then like rolling it back to a more abstracted and reasonable。

 like module。So let's start with the app。嗯。Okay， this one， I'll just start off with like。

Fully modular。 But you can see that this app is very simple。

 All it does is like instantiate all of these different components。

And there's really not that much more to it。One thing that we are missing。Is props。

So if you recall from the tree。All these different components were like direct children of the app component。

 which means the app is responsible for passing down props into those ones。



![](img/cf68d6d3909cad706202c4068eec885a_43.png)

The syntax have passed down props。And react is very similar to like attributes in Hm L。嗯。

You can set like a variable inside of your props object by doing this kind of thing。

 So write the variable then equals the value。

![](img/cf68d6d3909cad706202c4068eec885a_45.png)

So if we wanted to add props into our components， this is what it would look like。So， for example。

 in intro， we'd want to know like the education and like the city of whatever person this profile is of。

So we pass that down。Photos we want to pass down， maybe like the paths to all the photos that we have our our database somewhere。

嗯。And then the post， obviously， we want the name。

![](img/cf68d6d3909cad706202c4068eec885a_47.png)

And the content。Alright， let's look at some of these children components。And。Again。

 we're starting hard coded and then rolling it back。So the intro here， pretty simple。

 It just has two pieces of information wherever you study at and wherever you're from。

Let's try to roll it back， using the props。Again， remember that every reacting component is just a function that takes props and turns it into something to render。

So assuming that we give the props， all we need to do is just access those attributes of the props。

 So use curly braces， then props dot education。And then for the city， Pro Scott City。

Let's look at photos。 So if photos is a little bit more complicated。To render this component。

 we want to。Have access to all the images that will be used here。 So we have like 7 pictures。

In Kenny's Facebook page。嗯。Oh， okay， let me explain this。So this thing here is mapping。

Each of the photos into an image like elements and JSX。

And the syntax for this is using this map function。 So dot map。Takes in a function。

 and it'll apply that function to like each element of an array。So， for example。

 like we have this array of photos。And then because we're using dot map。

 it'll like turn each of those different images into JSX element。And。Yeah。

 that's why we can have all the images laid out together。

And I think you'll get some more practice with this later。But yeah， good to know。

If we wanted to like reactify this， then we can replace all those image links with just props。

Which will pass down from app。So comparing to what we had before。

We just replace the My links thing with prop do links。And it looks a whole lot cleaner。



![](img/cf68d6d3909cad706202c4068eec885a_49.png)

Alright， next， let's look at the post。 Post is again pretty simple。

 We have the name and then the content。 We also have the like button。

Which maybe uses something other than props。But let's first look at。There props things。

So very similar to the intro。We're just gonna access those things， using。Javascript。Okay。

 let's talk about the like button。So， for the like button。

We probably aren't going to be passing down a prop to denote whether it's liked or not。

 because it's something like very intrinsictri to the component。 And it's not like。

 it's not like one of those cases that Evan mentioned before。

 where you'd like to have it like up in a high level thing。

So let's just use state to implement the like button once again。



![](img/cf68d6d3909cad706202c4068eec885a_51.png)

We also want to implement the functionality of when the button is clicked。

 the like button will change state。

![](img/cf68d6d3909cad706202c4068eec885a_53.png)

And that makes it a really good candidate for state。So we're going to use the same syntax as before。

And this is we're going use that use state thing that we imported。So again， we'll have cont。

 and then we have an array that's defined as is like or we have is liked and then set is lick。

The first one is the state， The next one is the state Ster。

 and then we initialize that default seeing you state。And over here。

Over here is actually an attribute called on click。So。Whenever you're rendering a button。

 there's an attribute for whenever the button is clicked and that's on click。 So on click。

 you'll set equal to a function that you want to be called every time the button gets clicked。So。

 like。As an example here。On click is set equal to this callback function that just like or not callback。

 but a function that sets is liked to whatever it wasn't before。

 you can see they use an exclamation mark。And this will basically just toggle is liked every time you click the button。

And then within that， we're rendering the same thing that we had before with a comment reply。So。

It's the conditional statement。 again， if is liked is true， then we're going say liked。

And if it's not， and we're gonna say， like。Don't worry if this is a little bit confusing to you right now。

 We're rushing through things a lot。There's a lot to cover。

 but you'll get some practice with this in the workshop。And later today， with more onre。Yeah。

 so reiterating。This set is like function within the parentheses。

 It'll set it to whatever values in there。So。Every time on click is true， then。

We're gonna set is like to be the opposite of whatever it was before。



![](img/cf68d6d3909cad706202c4068eec885a_55.png)

Okay， yeah。 So that was a whole lot about react。Definitely， don't worry。

You don't get all the things that I talked about。 We have a guide for you to review。 Very helpful。

 Always come back to it。 So， bla， dot is slash rack guide。And just to recap。

 react is useful because we can do abstraction and reason。

 We want to divide our app into just a bunch of components。One component goes in each file。

 and then each component will bundle together like some JS X or some jascript logic and then output some JS X。

And the syntax for doing that is below。Props in state are like the name of the game with react。

 We'll pass in props using like the attributes， syntax。

And then we read those props by accessing as a jascript object。For state。

 we're going to declare states。The syntax as the syntax that I showed you。

And we can always set our state by calling the set function。嗯。

With the value that we weren't decided to。Ohright。 And make sure to use class name instead of class whenever you're doing styling。



![](img/cf68d6d3909cad706202c4068eec885a_57.png)