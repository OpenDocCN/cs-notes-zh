# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p50 -51-COMP6080 - ReactJS 💥 Lifecycle.zh_en -BV17RXGYuEaM_p50-

Hi， my name is Nick Barker， and this lecture is how React Work for Comp 6080。



![](img/ab3ffe593057ee7af9f625e23200a81a_1.png)

So before we start digging into the internals of how react works。

 first we're going to have a look at what react actually is。

 what problems it's trying to solve and the solutions that it uses to get there。So React， in essence。

 is just a JavaScript library for building user interfaces。

It was released in its recognizable form about seven years ago。

 which is a very long time in JavaScript framework terms。

And it came out of an internal project of Facebook。

 and it's been open source and maintained by Facebook since then。

The main ideas that react brought to the table in 2013 are the same as the ideas it still uses now。

 which are declarative rendering and components。We're going to mainly focus on declarative rendering in this lecture as components will be later on in the semester。

So what actually is declarative rendering， well it contrasts directly with imperative rendering in the same way that declarative programming contrasts with imperative programming。

So in imperative programming， we tell the computer exactly the steps that it needs to execute in order in order for us to get to a specific outcome。

 so we specify the process， but we don't actually assert on what happens as a result of running all of those steps。

Declarative programming is the opposite。 we give the computer the desired end state and we say I don't care about how you get there。

 I want you to figure out how to get to that end state。

An interesting way to think about this can be in the context of trying to bake a cake。

Imperative programming is like you're using a recipe book that doesn't have any photos。

 it just has a series of instructions， you know use this many eggs， use this much flour。

 and you're going to assume that as a result of executing those instructions correctly。

 you'll get a cake at the end。Declarative programming is a lot more like finding a photo of a cake that you like and then giving that photo to a chef and saying。

I don't care about how you cook this cake， what steps you use。

 I just want to end up with a cake that looks like this at the end。

So in order to contrast between imperative and declarative programming。

 let's look at a very simple web scenario。

![](img/ab3ffe593057ee7af9f625e23200a81a_3.png)

We have a blank page with a green background that we're going to call page one。



![](img/ab3ffe593057ee7af9f625e23200a81a_5.png)

So how do we create this page from scratch using only JavaScript？Well， first。

 let's have a look at the imperative way to do this。

 the imperative way we have to execute the exact steps in order to get us from point A to point B。

 So in this case， it's very simple。 All we have to do is reach into the document body style object and mutate the background color property and set it to grim。

So as a reminder， in imperative， we're specifying the process and not the outcome。

 we're not saying to the browser。The result must be that the background color is green after this。

 we're simply saying change this variable and we'll assume that we'll get there。

So the declarative way to do this same thing is that we declare the expected UI and we let react actually figure out how to get there。

So in this case， we've got our a functional component and we're just returning a self closing body tag with a style prop with the background color set to green。

So as a reminder in declarative， we specify the outcome that we want。

 but we don't actually care about the process to get there。

So this seems like a lot more code for the same outcome。

 especially seeing as that we need to include the actual react libraries and the browser compatibility libraries themselves which are like 109 kilobys of JavaScript right so if it seems like we're going to get the same outcome。

 why should we bother using this type of declarative approach？Well。

 let's take a look at a scenario that's getting a little bit more complicated。

Let's say we now have two pages， we've got page one， the green one， and page two。

 which is a white background that has three buttons。



![](img/ab3ffe593057ee7af9f625e23200a81a_7.png)

And we want to actually transition from page one to page two。

 so we'll assume that we start in the state of page1 and then we want to move to the state of page two。



![](img/ab3ffe593057ee7af9f625e23200a81a_9.png)

So the imperative way to do this is just execute the exact steps to get us from page1 to page2。

In this case， we're going to mutate the document body style。

 we're going to set background color to white。Then we're going to call document create element three times to create three buttons。

 and then we're going to use the append child function on the body to append the three buttons to the body。

 and that will get us to the state of page2。So the declarative way to do this same thing is that we just declare our expected states and we let react figure out how to make the changes by using an if statement in our functional component。

So in this case， you can see that if our page type is one。

 we're simply going to return the body tag with a background color to green as we saw before。

 but otherwise we're assuming that our page type is two and we're going to return a white body with three buttons inside it。

So this still seems like more code for the same outcome， why bother， you know。

 you might not be seeing the benefits right now， but we've actually forgotten a really major part。

Of this UI system that we've just built with these two pages。

Our UI that we have at the moment is actually now a state machine。

So if we think about our pages as states， we have to remember that in a state machine there are a combinatorial number of possible state transitions right and if we just look at our possible state transitions here。

 we've actually got six of them we have empty going to page one empty going to page two page one going to page two。

 page two going back to page1 and then we have these two states that we don't really have to worry about here which is page one and page two both going back to empty because we're unlikely to want to wipe our website back to a white screen so we can ignore those but we still have to deal with those for first state transitions。

So let's look at the reverse example of what I just demonstrated before here we're actually going to transition from page two back to page one。

 so from a white page with three buttons to a blank page with a green background。

So the imperative way to do this， we're executing the exact steps to get us from where we are to our desired state。

 and we can see that it's starting to get a lot more complicated。

So we actually need to keep some mutable references to the buttons that we create。

 so we're doing the same thing transitioning to page2。

 and then when we go from page two back to page one。

 we have to check that our buttons are actually instantiated and then if they are we're going to remove them from the dom one by one and set our mutable variablesials back to null。

So it's a bit more complicated now， let's have a look at the declarative way do this。

And if you look closely， you'll notice that this code is actually exactly the same as it was before。

 and this is the major benefit that you get out of declarative rendering。

Because we're just declaring the states and letting react figure out how to make the changes。

Our declarative code， by definition， handles all the state transitions for us。

 and this is a huge benefit as our application gets more and more complicated。So in general。

 in the Webas applications become more complex， we end up with more possible states and as a result the number of possible transitions between those states expands really。

 really rapidly。So even just on the high level idea of pages。

If we have 50 pages and we're only transitioning from one page to another， that's a minimum of 2。

450 possible transitions that we would need to handle edge cases for。

So when we're using a declarative framework like React。

 all we need to do is describe the complete output UI from those 50 states and react will actually manage all the transitions for us and as a result it sets a ceiling on the amount of complexity that we have to deal with with all of our possible edge cases。

The second problem that declarative UI aims to solve is the problem of untracked UI mutations and they become much more likely as our team size grows and I'll give you an example of what I mean by that。

Say we have another team in our organization and they say， oh。

 wouldn't it be wonderful if we could just have an extra div， you know。

 with like a message saying I don't know， please accept cookies or something like that on the bottom right corner of page too。

😊，And they think， oh， it's just a message， it's not interactive or anything。

 it's simple enough that we don't need to tell the team that built Pdge2 about this。😊。

But then you can see that if we reuse the same imperative transition code from page two to page1 that executed the exact set of instructions to just change the background color and remove the three buttons。

 we'll miss removing that new div and now we've got what's called an untracked UI mutation in that there's a div on page one that nobody knows about except the user who can see it obviously in their browser and when you have very complex state transitions and you're not using a framework that will ensure that your UI is consistent eventually you'll end up with something like this。



![](img/ab3ffe593057ee7af9f625e23200a81a_11.png)

Here's another fun example。Say we have two script tags that we're both loading asynchronously。

And the first one sets the background color to red。

 and the second one attempts to set the background color to blue。 So the question here is。

 what is the color of the body。And the answer is， I don't know it depends if this is actually a race condition because there's no synchronization between these two scripts they could both load at any time one before or after the other。

 depending on network conditions， server load。The CPU on your machine。And so in this case。

 we can end up with multiple imperative scripts trying to modify the dom at the same time with no knowledge about what the end state。

 the desired end state should be。

![](img/ab3ffe593057ee7af9f625e23200a81a_13.png)

So it's not all bad we had imperative rendering for a very long time， you know。

 the web was active from the early 90s all the way up until you know the early 2010s when declarative frameworks started coming out。

And it's very convenient and ergonomic for doing simple things。 You don't need any extra libraries。

 you don't need to transpile your code to build your JSX。

 you don't need to worry about package management。And the general rule that I think you can use when you're deciding whether you need to use a declarative framework or not to do your UI is just whether you have any data that's external to the Dom or not and what I mean I'll explain what I mean by that。



![](img/ab3ffe593057ee7af9f625e23200a81a_15.png)

So let's say we have a form that has a checkbox indicating whether the form should be submitted or not。

 let's say it's a terms and conditions form right and we have a checkbox that says I accept the terms and conditions and then a button that allows us to submit the form。

So in this case， we've got a checkbox in the Dom which has an ID and we've got a button that can submit the form。

 right？So what we're going to do in this case is when we click our button。

 we're actually going to look directly at the checkbox element in the HTML we're going to look at the checkbox element in the UI and we're actually going to determine whether it's checked or not based on its checked property。

And so this means that because we're checking right as we're clicking the other button and we're using the UI as the source of truth。

 we've got a pretty good guarantee that our UI is going to be consistent with our data that we're not going to accidentally allow the user to click the submit button without the checkbox being checked。



![](img/ab3ffe593057ee7af9f625e23200a81a_17.png)

But as soon as you have data that's stored in JavaScript only。

 so say you make a request to the server。You get an array of items back。

 say a to do list and you want to render the to do list of items。

You've now got two different state machines which are your jascript code。

 the array of items in your ja code and the elements in the dom。

 say divs or buttons in your to do list and you're trying to keep those two state machines in sync with each other right so if you remove an item from your to do list array in JavaScriptscript。

 you've got to make sure you remember to also remove the corresponding item from the Dom Sam with reordering with adding new elements with changing the contents of elements and。

You end up in the situation where you just。Chase exponentially more edge cases as your data becomes more complicated。

 so we need a solution to help us with that and declarative rendering actually solves our problems very nicely because it means that we can use our data in JavaScript as our source of truth and our UI will always look consistent。

So you're probably thinking at this point like， oh， this is great。

 UI React provides this UI magic for us， but it sounds complicated， it sounds like a black box。

That's actually not true。 And we can use very basic logic to build our own very simple version of react。

 You can actually do it yourself in the spare time if you want to experiment with it。

So the first step， and by far， the most important thing。

Is that we need a way to ensure the contract provided by declarative rendering。

 So declarative rendering guarantees that if you say the UI should look like this。

 that's what it will look like。 You know， if we if our functional component returns three buttons and react only puts two buttons on the screen。

It's all over， right， we can't trust react at that point。

 so we need to guarantee that what we ask to be on the screen ends up on the screen。

So how do we fulfill this contract？Let's try and think of a really dumb， naive way of doing it。

 the simplest way that we can think of doing it。Well。

Here's an idea How about we just erase the entire dom， we just wipe out the whole page。

 reduce it back to just a white screen， and then we rere the entire interface every time anything changes right So the example with checking a checkbox when the checkbox goes from unchecked to checked we actually delete the entire interface and then we rerender the entire interface with a checkbox being in the correct state。

So the way that you can think about this from an abstract sense is we don't need to think about any state transitions if we always start from scratch。

 right？If we erase the entire page， you can see in this case that erroneous div in the bottom right corner now gets wiped out as a result of the page being deleted and then we can cleanly transition back to page one using the same code。

So if this actually works， what's the point of react， right。

 why can't we just write one function that deletes the whole dom and then be on our way？Well。

 the problem is that it's actually too computationally expensive to delete and rerender the entire UI every time a small thing changes。

 you if you've got 10，000 elements and just checking a checkbox causes you to rerender those delete the whole UI and have to rerender those 10。

000 elements， it's just too expensive。It's actually interesting as a side note to understand why it's actually so computationally expensive to delete the whole do and render it。

😊，So one of the things I really believe this too， one of the things that makes HTML and CSS awesome is the layout engines like Flexbox and CSS grid are just such a joy to work with once you get the hang of them。

And we can use them to really easily make apps that can flexibly expand and contract to different device sizes。

 different orientations， layouts。But the price that we have to pay for that kind of power and flexibility。

Is that often when we delete an element， because our layouts are programmatic， they're not absolute。

 it means that they need to be recalculated。So we have three buttons sitting next to each other and they're all supposed to be equal width。

 right， they'll start out as 33% width。Then if we delete the one in the middle。

 it's expected that the first and the third button will expand to 50% of the width right。

 and when we have to do those types of calculations over tens of thousands of nodes， it becomes very。

 very expensive。So we're at the point now where we know how to fulfill our contract。

Of declarative rendering， but we just need to make our delete the Hol dome approach more efficient。

So here's an idea how about we figure out how to only delete and recreate the parts that we actually need to delete and recreate。

Here's the trick。Right。We don't actually care about the layout when we're making changes to the dom。

 right？In the process of making changes， we don't care about layout recalculation， right？

So we' going we want to let the browser figure out how to do the layout updates after we've already made all of our changes。

So。Since the layout recalculations are the expensive part。

 what we end up doing is we keep a virtual copy of the entireon the entire HTML tree in JavaScript right and we just make changes to our virtual tree。

 we delete elements， we move elements around。And then we look at the previous tree and the new one and we figure out precisely what has changed between those two trees。

 and then we can use those precise changes to make a very minimal set of changes to the actual dom and minimize the amount of cost that we need to pay to relay out things。

So this technique in a general sense。Is known as the virtual dom。

And it's not just used by reactact part， a number of other declarative frameworks as well。

So the key to the virtual Dom working well。iss that we're able to cheaply diff as in find what the differences are。

 di the previous state and the new state， and the reason that we can do this cheaply is because we don't have to pay to relay out all the elements when we recreate a new tree。

So if we look in this case， this is a contrived kind of example of that untracked UI mutation of the div that hung around so we can see。

We're going from a state where we have three buttons and a div and we're going to a state where we just only have the three buttons。

And on the right hand side， we're indicating in gray that we don't have to change those elements at all and in red that we have to delete that one。

So in this particular case， react won't need to pay the cost of deleting the outer container or any of the three buttons。

 right， because it can see that between state 1 and state 2。

 everything is the same apart from that one de in the bottom right corner。

So under the hood Re basically takes a snapshot of the way that the UI looked before and the way that it looked now in the cheap virtual Dom。

And it looks at those and says， this div is the only thing being removed and nothing else has been changed。

Then internally， it just calls remove element to delete a single div from the dom in the same way that we would do it in the imperative way and it avoids having to pay the cost of deleting and rebuilding the whole dom。



![](img/ab3ffe593057ee7af9f625e23200a81a_19.png)