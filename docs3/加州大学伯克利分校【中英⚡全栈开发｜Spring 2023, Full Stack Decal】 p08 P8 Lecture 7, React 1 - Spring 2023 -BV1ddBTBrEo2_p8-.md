# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p08 P8 Lecture 7, React 1 - Spring 2023 -BV1ddBTBrEo2_p8-

いです。

![](img/43e3105670cd18649e19f2250b3b82e0_1.png)

这可以的。Twice。Good evening， everyone。😊，Today is the。Intro to React lectureture。

 it's a very important one。Hi， everyone， you're going to get started。两对。

All right today we're going to be teaching you probably like the most important lecture of the semester intro to React and I'm Vhan and I'm Ikey。

Yeah。Oh。Okay， so you've learned HTML， you know CSS you know a bit of JavaScript。

 raise your hands if you do know these please yes okay good we know this so now we're going to shift to like frontend we're going to combine three of these together and use react which is kind of a framework how many of you have already heard of react before。

😊，Okay okay it was created by Facebook so Facebook does use it so what is react it's a JavaScriptscript library which helps us make interactive UI so you don't want plain design you want more more like good frontend good UI for your users so the main aspect of react would be components so kind of like smaller pieces of code so you've used HTMLM attacks before so something similar to that you can create your own components which are kind of like for example if you're like building a house you can create a door and then your house can have a windows so the door the windows can have separate properties and it also is very useful when you want to reuse code so you'll be reusing your components。

😊，So why use frameworks and libraries at all， any answers， anyone？这面有。Yeah，各位。Wow， also good wow。

 look at that， yes， makes a life easier。😊，Yeah， so react again will make your life easier。

 you're going to fall in love with front end。😊，Out of curiosity。

 how many of you are leaning towards front end？I expected more， okay。😊。

So react is again very popular it's very easy to work with one of my favorite frameworks these are a few。

😊，Benefits， it's good too it's when you're testing speed and of course， combines HTML。

 CSS and JavaScript together。Okay， if we want to bring out our laptops。

 just check if you already have node or NPpM installed， you can use the P flag to check that。

 otherwise if you can if you don't just go on to node JSstarort and then you can download it straight away we'll give you a few minutes。

这第一个是。是。Yeah， I see the setting will go so。大丈夫。嗯。有不必的。嗯。The then。Yeah。诶，还明后他。Okay。くさい。我完。This系啲咩。不清楚。

没。嗯。对。嗯。그러ね。か基さして。大一问。Okay， I'm going to go ahead。So to create a react app。

 that's the command you can run in your terminalins， you don't have to。

 but whoever wants to can just try it out is just going to create a react app。嗯。Make should to be。

这问题。哎哦嗯。系。我听年。就你身来。你不没回。Thanks。就是个欠。嗯。Okay。对以。Okay。So coming to components。

 we're going to reuse pieces of code， we're going to again like I mentioned if you're building a house。

 I have a door component， I have a window， I have a roof which has its own properties and I'm going to combine all of my components to build a house also all of my components can have different data。

 different logics or different functions， yeah and it improves readability。

So here we have an example。Just a question， do you think the spider is cute？😊，Yes，や。Yeah。

 we want that to be our WDb mascot， but yeah， no one's。😊，Okay， so that's an example of a component。😊。

Welcome is the name of our component so you're kind of thinking there's like HTML tag and then there's like JavaScript what is happening here so we can actually combine HTML and JavaScript together it's called GSX that's what we use in Re so yeah so these individual HTML tags are also components but right now we are creating our own welcome component and that's what it's going to look like。

Any questions till now？Yeah。这微信边论几你个行现在唔可。Yes， yes。Okay。

 so how do you use it so you can use components inside other components so as you can see here we have a component called app and then we're using our previous welcome component and we're returning that kind of we're like creating our own HTML tag。

So once you create your react app also you'll see like an index or GSX and inside that you'll see a line which says react dom dot render which renders the root of your。

Website and then your components come under your route so you can think of it as like your route is like your main page and then your page has different components so all get rendered like react on or render renders your route。

And once you create components， you want to export them if they're in different files and import them into the file you're using。

 that's when you can use it like inside of app。Okay， any questions？Okay， I'm going to move to props。

So props stands for properties， you can pass data into components。

 your components can have different data， different logic。

 so to kind of reuse components props is a good way so again。

Your house or your door can have different properties， and each component can have。

Different properties as well， and they behave differently。So coming back to our welcome component。

 for example， I don't want to welcome a spider， I want to pass in my name， some I passing in name。

 kind of you can think of it as like an argument and it'll display welcome whatever I pass in the name as。

Okay。

![](img/43e3105670cd18649e19f2250b3b82e0_3.png)

啊。So we are kind of creating a Ti ta to game。That's our board， so we have three main components here。

 we have board game and square game range。So we're going only look at board and square actually so that's what our game looks like we have a board we have a bunch of squares now I want different properties for my square I want different properties for my board I want my squares inside my board so i'm going to create different components so a square component has a button because we want the user to be able to click on the square and display the X。

So if I just boss in。Yeah。Thank you。Okay， so our square has a button。So if I specify something here。

 I don't want。My button to be a constant X， I want it to change into an X or an O depending on the user。

 so I'm going send in some properties。So I'm sending in kind of like an argument and。Yeah。

 so in my board this is my board component， so you can see it's a function and then I'm rendering or returning the square over here。

Now， since my square， yes， square did you。Oh， yes， no。You can use either， yeah， yeah。

 it doesn't matter。嗯。So in the board component I'm returning the square over here。

 but now this is kind of not going to work because our square component says okay we want some properties so I'm going to send in a value here。

Let's make it just in X right now。So now what this is doing is's from props。

 it's taking value and it's going to display that as the button。

There you go so right now all my squares have x's so of course we don't want that we want it to change as other user clicks it。

So I have something defined here， which is the board so I'm going to use that right now Wihan is going to explain more of this later on。

Oh。Okay， so there you go。 So it's picking up from our。Constant board here。

 And then we're passing the value as。The boards， I。

The Ih value and then squared here takes the props and accesses the value。

 which is what we are passing in。So similarly， we also want to have an on click function because these are buttons。

So we're also going to specify on clickrop here。对。Yeah， what's it。

And then so this is how props works and wehan is going to get deeper into how we're going to implement the rest of the board so this is basically how you like how you define props for a function or a component and then you can pass it from other components when you are returning that specific component。

 so any questions regarding props。Yeah，Yes。嗯，嗯。我都是抠分的。Oh。

 that's inside of my board component when I'm returning the board。

 so it's rendering each square yeah。

![](img/43e3105670cd18649e19f2250b3b82e0_5.png)

Okay cool， now let's talk about state。So you use state and react to be able to store data inside of a component so so far you've seen props which are what we're using to pass data from a different component down to a child's component but state is slightly different and that it allows us to kind of have some like local data that's changing so for example in ourtict toe game what you'd store in the state would be things like which current player is being active and then also the board state like what are the Xs and Os on the board right now。

And so you may say to store local data I could just use like a traditional variable the problem with a traditional variable is react doesn't actually know when to change what's displayed inside the browser。

 when to actually like rerender what you see on your screen and so when you use a state variable that's slightly different it'll tell the browser that okay now we actually have to rerender what's on the screen。

So let's take a look what state looks like this has quite a few parts。

 but the first thing you'll see right here is there's a U state function call。

This USA say function call you're going to pass the initial value so right here I have a really simple counter example and what it does is it will print out a button and every time you click it the counter will go up so by passing in zero the initial value of this count variable is going to be0。

Now the way I update the state is you can't use regular kind of assignment equals with stay variables you have to use the set function that it gives you so right here every time I click on the button using this on clickick I do count plus one and then that's how my counter works it's going up by up by one every time also you're going to see this on click right here in case you're not already familiar with this this is an event handler it's similar to like the on clickick you'll see an HTML and it's also a good example of a prop because but instead of passing like a string you're passing a function。

All right。And so just a quick overview of question。

Yeah okay that's a good question so if you haven't seen the syntax before on the technical term it is destructuring but you state returns two things it returns the value of the state variable and it also returns a function that lets you set the state variable so the way you kind of receive those two arguments is using the syntax。

😊，And yeah， you can you can name count like how whenever you want， just kind of match this pattern。

Okay， so what's the difference between props in state props are something you get from a parent component and then state is going to be internal to the component the main difference you're going to find is that you can't change crops but you cant set a state。

And also both for your component renders。Let's get to know。

Now a common issue you'll find is sharing data for example you may be creating like a large web application and tons of components need to access to kind of let's say like what users logged in or maybe like what's in the user's car and so the question is how can components B and C share data and the answer is that you're going to want to put the state as high as possible and so you would put all their shared state in A and pass it down as props to B and C。

anyone have any questions on that？Yeah， yeah， so a child can't directly access state。

 but you can pass a component state as a prop to its child。All right， and yeah。

 that's basically summarizing the last slide in words。All right。

 now let's take a look at a demo of adding state to our application。



![](img/43e3105670cd18649e19f2250b3b82e0_7.png)

So right now the app isn't very interactive， but I'm going to start by converting our regular variable to a state and this will let us。

Have it be interactive。Yes。So now what I'm going to want to do is when the user clicks on a certain square。

 I'm going to want to update update that square and I'm going to want to put an X where they clicked。

So what's going on here is when the user clicks on a square it's going to call this on square clicked routine and then what I'm doing in this on square clicked routine is I'm setting at the at the square that they click I'm going to set it to an X and then I'm calling set board with a new board you're also going to see this dot dot dot syntax which you may have not seen before this is pretty much copying the array when you call setboard you need to pass it with a completely new array and so that's what this does it copies it say have a brand new array。

Al right， let's go test this out。So now when I click we have X's coming up So now I almost have a working game ofticktk toe。

The one last thing I need to add is so it actually changes players and so the way I'm going to do that is very similar I'm going to turn player into a state variable by using use state。

And then when they click on the square， I'm just going to use some if and I'm going to change the player so if the player is an X。

I lovebe呃。Now yeah， you can switch between。嗯嗯。Yeah。

 now you can switch with new players and you have a whole game ofticactile does anyone have any questions？

Yeah。yeah， no。So you can think of it as it'll just render like render a specific component and react has a whole algorithm you can learn about about how it determines what there re。

So you don't have have to implement like set player and set order。诶。Yeah。

 those are given to you when you call you state like right up here。

Yeah one of the things where react is so useful is that it does not so when you're changing something it does not render the entire page so if you have like a cart and you want to plus one it won't like reload the entire page it will just reload and relender that component yeah。

Okay， any other questions？Yeah嗯我我。Yeah， this part right here。Yeah， or this。

So player is the current value。 So when I first run this function。

 player is going to start out at the initial value of x and then if I call set player with I can pass any parameter to it then。

When the component renders， then player will be the kind of new value so it'll change from an x to an o so player is a current value of the variable set player you can use for like any any parameter。

Yeah。诶十我 think I can everything for。Yeah， yeah if you said to the that's like a very easy mistake I made that mistake in an interview once I just did player equals and that won't do anything you'll notice your component doesn't change so be careful about that。

😊，Yeah。Yeah pretty much you can put anything in in state again the only thing to be careful of is make sure you're always passing a copy to this to set state like make sure you copy the array。

Yeah。All right，Any last questions？Perfect， then we'll move on I I'll get back to the slide。😔，Yeah。



![](img/43e3105670cd18649e19f2250b3b82e0_9.png)

Itね哦 okay。It。Now well briefly talk about useful tools these are extensions you can install in VS code to make coding and react a little easier the first one is prettier a lot of like people the right react code that looks like total garbage they don't indent and so the easy way to installablyttier it'll do everything for you you save your file it'll format it help your code look clean。

😊，And the second one is ESLin， as I talked about there are a lot of like easy mistakes you can make。

 for example， if you forgot to use set player and you use player equals the ESLin is a tool it'll kind of validate your code and catch those errors really really great way to prevent mistakes。

😊，And yeah， yeah announcements homework three is due tonight and yeah homework4 is Ri。

 which is due next week。Yeah， that creative。I don't think so I think they were talking about that。

 I don't think there was a red will and I think probably announced something。Yes， I mean。

 now we might extend it what we'll say。诶。That is oh we don't have any all right that's the end of the lecture Yeah any questions you can Yeah so the the more technical explanation would be react to be efficient if the two objects have object identity and ja meaning JavaScript like they're the same array and they point to the same memory location it won't it'll think they're the same and it'll try to optimize it so it will doesn't update and so when you copy an array JavaScript knows that it's actually a new value and that it's not the same value。

呃嗯嗯意。Oh yeah， it'll be recorded in Boston。

![](img/43e3105670cd18649e19f2250b3b82e0_11.png)