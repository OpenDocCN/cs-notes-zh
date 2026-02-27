# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p11 -11-MIT web.lab (6.962) - Day 3_ Workshop 2 (Feed + Router).zh_en -BV12Ux5zTE9p_p11-

OK嗯。Alright， so today we'll be doing workshop 2。 And so we're building up， we're building on our。



![](img/374f9e896f9309ae77e8daaaad756d9c_1.png)

呃，OK。We're building on workshop 1， where we built this feed page profile page。

 And now we're going to build a feed page where we can sort of have our Facebook like posts and comments and things like that。

 Yeah， so we'll be using all the stuff that Andy talked about in the last hooks lecture。

So we're gonna build the front end where we have posts and also comments。

And we'll add on the back end tomorrow。And this is sort of what we're going for today。

So to get started， it's the normal steps for our workshops， reset hard。 check out W T Ster。

 And then you can always do， use the questions Do at the queue when you need help throughout the workshop。

嗯。哎。哎嗯。Yeah， so。This is what our component hierarchy commentary looks like from workshop 1。

 So we have the app。 We have our profile aar， and then we just had the little clicker item。

 But now we want to make it a little bit more complicated。 have our whole feed。

 where we have posts and then comments on within those posts。 And yeah， again。

 this is what we want to go for。So we wan to create the feed page。

 We'll do some routing so that we can get between the profile page and the feed page。And then。Yeah。

Let's， let's just get started。 And MPM runs up to。To view your。To the your cap book。

 mine is on local host 5，1，74cause I think there's something else on the port。

 but yours should be on 5，1，73 if you have nothing else running。



![](img/374f9e896f9309ae77e8daaaad756d9c_3.png)

Okay， so to start， we'll do a quick warm up。 commence to get caught up are always in the top right。

 And yeah， for throughout this workshop， we're gonna have a bunch of steps。

 And you can always use like the little search bar on the left or command or command just F。

 And then you can search step 0 or step 1 or step 2， etc cea。 to find。😊。



![](img/374f9e896f9309ae77e8daaaad756d9c_5.png)

The steps you're looking for。 So our will be step 0。

 And we want to import feed dot Js instead of profile to get something that looks like this。

And you can have a couple minutes either that。哎。So。I over how to do this one now， so。

First thing we want to look is we kind of want to see where feed is with respect to where we want to import it into。

And if we look in our sidebar here， we're working at App JS X， but feed is within pages。

 So if we want to import it， we can do the same thing as we see profile being imported。

And we just import。可以的。And you can see that the feed， the feed file exports feed here。

 export default feed。And so to render it， we just see the same thing。

We just do the same thing as profile。 We do the fake H M L component with the open with the self closing tag。

 And then we can come to profile for now。嗯。So then if we go over the profile page。

 we see what we want。 It just says this is the feed。

 but it doesn't have anything yet because it haven't filled it in。



![](img/374f9e896f9309ae77e8daaaad756d9c_7.png)

Okay， so now let's get started with step 1， which is just rendering a single story component。

And reset hard and check out step  one to get started。



![](img/374f9e896f9309ae77e8daaaad756d9c_9.png)

哎。So step  two is gonna be another I should say step 1。 Step 1 is gonna be another exercise。

 So in Vt J S， we want to render a single story component。So。Right now， we have nothing in3 do J。 S。

 We just have a div with some filler text。 And if we look inside modules。

 we have a file called single story。嗯。And single story is also not filled in yet。

 It just has some filler text， but we want to fill it in with something to get。这个什么定的？Oh wait。

 this lead is out of order。嗯。Oh wait， no， it's fine。哎。So yeah， we want something。

That looks like this。 ignorere the stuff at the bottom there。 But yeah， we just want a name。

 which is in bold and then some content rendered here。

 And if we look inside our inside our single story。 we have a doc string here。

 which tells us which props are being passed into single story。

 So we have Is your name and content and we want to use these props to render something that looks like the picture on the slide。

And you can also look inside card do CS， S， S for appropriate C。

 S S files to try to create the component。And we're also're on step 1。

 even though the slides say step 2。

![](img/374f9e896f9309ae77e8daaaad756d9c_11.png)

![](img/374f9e896f9309ae77e8daaaad756d9c_12.png)

Okay， so for this one， we can start by just rendering in。Single story after we import it， so。

Single story as your editor should usually fill in the import line。

 And then we do the same thing as before。嗯。And then just put in single story。

So if we do that for now。嗯。O是。If for now， we just get that this is a single story text。嗯。And。Now。

 we want to actually fill it in with props。是。We wantanna display the creator name and content。

 We already have the class。 we already have the C S card story filled in。

 and then to fill in the first。Heading， we could。就。嗯。I mean， it doesn't really matter。

 but we could just do it H1， and then。嗯，Cl name。And。Set it to you bold。So let me open up。Card C， S。

 S。E vote。嗯。And then。Put in。Creter name。A using props。And then we can add the actual content。

And we can use the。Card story content。个人。And now， we want to。Actually， use the props。

 So we fill that in with the attributes from where a single story is called， so。

You can set them in here。嗯。能。I be something。 And then right now。

 we don't actually have a We don't actually do anything with the I yet。

 but we can just pass in some dummy value。嗯 yeah， then we get the。啊。

We get the heading and then the content passed in through the prop。That's step 1。



![](img/374f9e896f9309ae77e8daaaad756d9c_14.png)

You can check out W T step 2 to get the result and to catch up。right， so step 2。

 we're going to create a story state to maintain the stories within our feed and。



![](img/374f9e896f9309ae77e8daaaad756d9c_16.png)

And this will just be a follow along。And。Right now。

 we're just going to be hard coding our list stories。 So tomorrow， in our next workshop。

 we'll be working on having some sort of back that serves our stories。 But for now， we're just。

 we're just working on the front end hard coding some stories in our state。And since we don't。

 since we want to render a bunch of stories within our feed， we want to hold this story state within。

We want to hold this story state within feed， because that holds which stories should be rendered。

 So to start， we can just use the， the normal commands to write down to get create a new state so we can create a state called stories。

 with its setter set stories and then use the used state hook and initially， we want their we want。

 we can just have the default value to be an empty list。

 And then we'll fill in this empty list later。And when we fill in this empty list is in here inside of the use effect。

 inside of the use effect， we want to， we can just hard code some states on render because this is an empty D bracket。

So， we can just create。Some stories。And you can see that what the format has to be here。

 We just have to have three values， which are the I D creator name and content。

So we can just create set random I Ds。K name。Person one。嗯。And then content。啊。刚才完。And then。

I'll just create a list of them， because。In the future。

 we'll want to have we want to be able to list render a list of different stories。

So I'll create more than one。And then to actually set the state， we use the set stories function。

 which is created by the， by the use state hook。 And then we can set stories to be a list of story 1。

 storyory 2 and story 3。And lastly， just to see what this list looks like。Ill render with。

I'll render it with the。With a single story。With Json does stringingify。

 And all this does is it takes a。Takes adjacent object and then returns turns it into something readable。

And that's gonna be Javascript。 So we surround it in the curly brackets。And then。

 just pass in stories。嗯。Yeah， so if we take this and then reload。

 we see we get a list of I Ds and created names and contents rendered here。呃。Yeah。

 so there's just hardtro stories for now。 And then they still change in the future。



![](img/374f9e896f9309ae77e8daaaad756d9c_18.png)

![](img/374f9e896f9309ae77e8daaaad756d9c_19.png)

So now we have multiple stories。 And so far， we've just rendered this one story down here。

 So we want to figure out how to render a list of these stories， which can be variable。



![](img/374f9e896f9309ae77e8daaaad756d9c_21.png)

So。呃， check out。Check out W2， step 3。

![](img/374f9e896f9309ae77e8daaaad756d9c_23.png)

So this will be another follow along。 And we sort of want， we want to render。Are。

 our stories are China list。 and we have a component to render a single story。

 which is called single story。 And we need to somehow go from just a list of information to a list of components。

So yesterday， we talked about the map function。And that function just takes in some list and then some function and then applies the function to everything in the list。

 So in our case， we have a list of， just information， a list of Json objects。

 And then we want to have instead a list of components。

 which is something that can be rendered by the J S X。😊，So we didn use the map function to do this。

And have some function that goes from。That goes from just the list of information to a list of the actual components。

是。是。好，OK。So to do this， we use the map function syntax。

 and then we'll create a variable to hold that list， that new list of single stories， so。And also。

 one other functionality we want to。We want to also work with， is。

create a fallback for when there are no stories in this stories list。So to do to do this most easily。

 well create some variable。To hold our list of stories。 And then first， we'll check。If the。

 if there are stories at all， so we can check the length of the array。And if it's not equal to 0。

 then we can。Then we can render the actual stories。 But if it is equal to 0， we can set stories。

Sttories list。这。So the no stories。So those stories div。 Now you want to render instead。

But if there are stories， then。We can use the map function。And the map function takes in。

You just put a dot after the list you want to apply the map to。

 and then you input the the function that you want to apply。

 So the function let me apply is if we have some story， then。We want to return a single story。

And if we want to implicitly return， we can just use parentheses。

And we can create a single story component。And we want to pass in the props。

 So if we have a story object which has I D creator name and content。

 then we can just directly pass in the props that way。 So I D is gonna be equal to the story I D。

And then the content is gonna be equal to the story's content。And then creator name is the same。对。

So this creates a stories list， which is equal to there aren't any stories。

 If there aren't any stories at all。 And otherwise， it maps it into a list of single stories。So now。

 instead of， instead of just putting us Json dot screen in five of the stories。

 we can now input our stories list。And。If we reload。

 we see that the three stories that we have within our story state is。Is rendered。

And now we can check whether our fallback works by。

Let say we just delete the hard credited stories here and then just make it an empty list。

Then we the render。 There aren't any stories。And if we change it back， we get the stories again。O。



![](img/374f9e896f9309ae77e8daaaad756d9c_25.png)

So。That was step 3。 So I'm going a little fast just because we're a bit behind。

 And our last step before we break will be step 4。 New story。 So Re heart and。Check out stuff4。

So step4 will be another follow along。 And now we're going to create a framework for inputting these stories。

 So this is so we want a framework where we can modify the story state because we have a method to render stories based on a variable state of stories。

 And so now we just need to create something that can modify it。😊，So。This step is a bit long。

And you can。You can check all the places we need to modify for step 4。So， to start。哎。To start。

 we have this starter file called it。Call new post input。Call new post input J S X。And in here。

 we have this start component that we've made。 And it's called new post input。

 And you can kind of take a look。Edit and try to parse what's going on。

 But I think itll be easier to see if we just render it to start。So。So if we look at the rendering。

 it sort of just has a box and then a submit button。 And basically。

 the new post input is a nicely wrapped component where you have has a default or it takes in the number of props。

 which is default text， and then a callback function。And。之前的。Alright， yeah。

 so it takes in a callback function and then some default text to render， so。If you pass those props。

And then。Let me see that we get some default text within the post box。

 So the reason that we have this more general component called new post input instead of separate new story input and new comment inputs。

 is that in the future， when we input in a when we start creating the comment section and then a functionality for adding more comments。

 we might want to have different callback functions for when the comment submitted and different functionality when different default text。

 So having a general component like this， which you can。

Use as a child component for both new story and new components nice because it makes it reasonable。是。

So now we'll create the actual news story component。

 which is more specific to news story rather than just a generic submission box。是。To start。

 I guess we can just。To start， we'll start in the feed file， actually。

 because we want to have this new story input to modify the story state within the feed。

 And the best way to do that is to start by creating a function within。Within the feed。

 because that's where the story state resides。So because otherwise。

 if you wanted to actually modify the story's object。

 then you'd have to pass that down into new story input and passing it's more messy to pass these objects around。

 So this is just best practice。So。We can create a new story。Which takes in。Which takes in some story。

嗯。And then after that， it wants， we want to modify the story state， so。

We can use the set stories function for that。And then we can use the syntax with the dotta dots to have all the current set of stories and then add in the news story。

And then this is something that we're gonna pass down into new post input。嗯，min。

So within our news story function， we have another call that function called add story。 And okay。

 this is a little bit repetitive。 But this will make more sense tomorrow。

 when we do more functionality within the ad story function here besides just calling add news story。

 So we're passing， we're gonna pass the proper add news story into news story。

 And then just actually add the news story。 So this value here that we take in is just gonna be。😊。

Okay， I deleted the submission box， but it's just gonna be the text you put into the submission box。

 And then we want， we're gonna want to do something for that submission box。 And in this case。

 we're gonna want it to add a new story based on that submission box。

So the new story object is gonna be something like the one over here so we can just create。

A random idea。 or just a random。 And then。嗯。The creator name。Since right now。

 we don't have any better info about who's actually creating it。 We'll just call it anonymous。

And then。For the actual content here， we can use the value that's passed in through the submission box。

So this will， so from， so this add story function in news story。

 when triggered is gonna input this new value into add news story。

 which will accordingly update the stories。The stories state within and feed。Now。

 the last thing we need to do is just integrate this callback function that we created with new post input because new post input lets us call。

 lets us submit a prop called on submitm， which is triggered when a value is submitted。So。

We can now return a new post new post input。And then we could set the default text to just like。

Enter your story here。And then here to answer submit。嗯。

And then set on submit function to be equal to this add story function that we just created。So。

 now we have。A set of functions that updates the story state。 And then now we have。

 now we put that into the new story component， which is exported into feed。嗯。

And then we can actually just render it at the top of our list。

And we're gonna want to pass in the prop add news story。Which is just called that news story。So。

 yeah， if we see that， we see the enter story here。 default text is filled in。 and hopefully。

 if we put in a news story。And click submit。The story state is updated。

 and now we can add stories to our website。And you can just keep on adding things。

 and the lists will just grow with the new stories that you add。Alright， yeah， so that was。

 that last step was kind of a lot。 So yeah， are there any questions about creating the。

 the multiple callback functions to update the story state。If not。

 you can always add more questions to the questions doc and put yourself in the queue if you're behind。

 And if you w to get， get the actual result for what we did in step4， just reset hard and check out。

WT is step 5。嗯。And you should get the same functionality。OK。嗯。Yeah， I think we're gonna pause here。嗯。

OK。I think we can get started again。Does anyone want to like。

Sort of say what they think about the first one。 Like。

 why do we have a separate new post input component。

Instead of having like two independently coded news story and new comment components。

I don't want to give a shot at this。Yeah， like， why do we。

 Why do we abstract some of the functionality away into new post input。Instead of just creating。

A new story。 and then creating a new comment and not having the new post input。Okay， I can。

 I kind of answer the question in the question。 but it's like， it's good for abstraction because。

When we have like， common functionalities。Because like the news story and the new comment are gonna to look very similar。

 They both have like an input and a submit button， and they both like send or do some behavior to like an array。

嗯。We want to abstract all that functionality away so that we write as little of repetitive code as possible。

And this is just good coding practice in general。Apped to web development。

So what are some things that are common to all the new blank components。嗯。我。New story， I guess， like。

All the things that are common are going to be inside the new post input component because。

New story calls， new post input， and a new comment also calls。Do you post input eventually。

But I guess already said this， they both have an input area where you type in text。

They both have a submit button。And then they both have some function that you call whenever you press that submit button。

And then finally， the on submit prop for a new story component。You can always trace down。嗯。

You can always trace down the props of these components。 Again， it's a tree。

 So there's one one unique path。If we look at a new story component。嗯。We return。Another component。

 the new post input。And we pass in on submit as a prop or ad story as a prop for。The on submit prop。

嗯。And ad sorry is this callback function that we define in the component。Essentially。

 this callback function is called whenever the submit button inside the new post input is called is pressed。

And because。Like the new story and the new comment will have different callback functions that are called whenever you press the submit button。

 That's why we have the functions defined inside New storyory and you comment respectively instead of finding them both inside new post input。

So we have to pass that callback function into the on submit prop。Which is then used。

And access here props to onsmit。Okay， any questions about the first five steps。OK。Yeah。

 so so far and。I think it's pretty helpful to really take a look at steps 2，3， and 4。

 because you're gonna to see very similar steps steps 6， through 8。So far in sub0。

 we just simply replace Feud with profile。And then in step 1， we created a hard coded state。

For other stories。And step 2， we rendered a single story component using the dummy data from the state。

In step 3， we took our state， which is an array。And then we mapped that array。

It's an array of JSX elements。I guess， sorry， an array of components， specifically single stories。

And then finally， in step 4， we added a text box。嗯。In。

At the top here so that you can add a new story， you can type something and then press submit。

 and it shows up at the end。OK。So step 5 is going to be conceptually a break away from all this。

And it's gonna be a bit。New slash confusing， probably。

It's honestly a mini lecture within this workshop。问。

Our next task is to add navigation within the website。And all of you have seen navigation before。



![](img/374f9e896f9309ae77e8daaaad756d9c_27.png)

When you visit。Any URL。You see that this URL， the domain is like doc do Google dot com。

 Then afterwards， you see this slash presentation and then slash D， all of this。

All this determines what we showed to the front。 and pretty much all these websites use routing。



![](img/374f9e896f9309ae77e8daaaad756d9c_29.png)

嗯。So what's our end goal， Our end goal is to have something that looks like this。



![](img/374f9e896f9309ae77e8daaaad756d9c_31.png)

嗯。We want to be able to toggle between the different components based on what URL we're at。So。

To specify the exact definition of URL， this is going to be the base URL。

It could be like catbook com。 In our case， it's local host， colon 5173。

And then plus whatever route path you append after。By default。

 the route path is gonna be like a forward slash， which is equivalent to having no route path。

 So these two first these two urs are gonna do the same thing。

Except in like very specific nuanced cases， I think。

And then you can do something like catbook dot com slash profile。

 And this should show you a different page from catbook dot com with just forward slash。

And then at least in our example， if we have some URL that has some random route path。

 we want to show a not found component because this。Path doesn't actually make any sense to us。

 We only have two valid paths for the user， either。The base path。

 the base URL or the base URL plus the profile path。OK。So visually， it's gonna look like this。

 And I realize it's really small， but。This says local host 5173， and this shows our feed。

So this is the base URL。And then this one is local host 51，73 slash profile。And at this route。

 at the slash profile route， we want to show the profile component。And then finally。

 if we have some random thing like ASDF。Or anything else that's not a forward slash or a profile。

We've already created this component for you inside the code。 It's called。Not found JSX。

And we can just import it。But we want to render that whenever we reach some like random path that we don't recognize。

So any questions about what our goal is with these routes。O。While I'm talking。

 you can also just check out step  five if you haven't already。不。For routing， the。

 I guess standard way to do it is using a library called react router。

There are many route router packages。 In fact， in the past we used to teach one called Re router。

 all of them behave sort of differently。 but the main like core ideas are all the same。

It sort of tells react how to like handle when you're at different URLs， which components to render。

React writer is going to be discussed in a future lecture。

 We're going to go a lot more into like what's actually happening underneath the hood。

And for this lecture， because we have such a simple like router setup， we only have two pages。

 the feed and the profile。 you don't actually need to know exactly what's going on to be able to code this up。

对，3。This isn't something that you have to do because we've already set this up for you。

 but in general， whenever you need an external package。

 you have to go to your package do JsonN file inside your code。So I'm going open that up real quick。

 just to show you。In package do Json， you can go under dependencies and see all the packages that you're dependent on。

This is pretty similar to like when you're in a Python environment。

 If you've worked with that before and you have like， like Pip， like。

 there's a lot of package managers for you， like Pip Conda。Yeah， there's a lot of different things。

 but。We use NPM， node package manager。And then。Once we specify a package in here。

Specifically like reactor writer Dom， and then give it a version。

This meaning that the version has to be at least 6。00。And then we run NPpM install。

This is what actually lets us use all the code inside of this package， so。Just to show you that。

 if I delete my node modules。嗯。And then try going back to the website。



![](img/374f9e896f9309ae77e8daaaad756d9c_33.png)

Maybe。Shouldn't work of maybe a ss work。But I wouldn't be able to do。Anything with a router。

So I need to NPM install so that I have access to this package。OK。呃，I love about的。



![](img/374f9e896f9309ae77e8daaaad756d9c_35.png)

![](img/374f9e896f9309ae77e8daaaad756d9c_36.png)

So part  one for creating a router。 And this is gonna be a follow along。 So if you could。

 please pull up。Index do JSX。And notice that index index JS X is the root react component。

And you know this， because。Or this is like where you're defining the root react component。

 because you see this code that says。ReactOm。 create root， document get element by ID root。

And this is rendering app。We saw this in like the lecture from this morning。

But in the root component is where you should do all of your router logic。Part1。

 I'm just going to unment all these imports。We import from reactor do the same way that we do for anything else。

 We just specify the things we want from it， and then from the package name and strings。OK。

And then also at the top， I didn't add this as a slide， but go ahead and import feed。Not founds。

This should be under pages。As well。And then profile。So you might be wondering。

 this is pretty strange， because。Before we had all of that imported inside of app。

We would just surrender either profile or feed inside of app。

Now we're taking all those components and bringing it into our index do JSX。So。

This doesn't seem to make sense， because。It's not actually needed this high up the tree。Normally。

 but with the router， we actually do need it all the way up here inside index。OK。

So now that we have this imported。The next step is a lot of code at once。

But this code is gonna be very standard。 And in fact。

 I think all the code moving forward for the router isn't going change much or diverge much from this。

Especially these first two lines。Where we define a constant called router。

And then set this equal to create browser router， which we just imported。

Called on create routes from elements。And then inside is where we actually handle all of the logic for creating these routes。

So I'm just going to type this in real quick。Create browser route。可以。Rooututes from elements。

And then inside here， I'm gonna be putting my route components。2月。

So how do we do these route components？嗯。Sorry， once so。

I guess let me explain this this code more in depth。

 So what we're doing is we are creating an opening route tag。And this route takes in two props。

 one being the error element， as well as the element。

The error element is just an optional element that we can pass if we reach some sort of error。

The most important thing is all of these routes need some element。

And we sent this equal to whatever element we want to render。So。On the very outside。

 we want a render app。And that's what we're doing like down in the code， orre rendering app。

But we've seen that like， there's some behavior with the routes that determines which inner components we want to render based on the route we either want to render feed or profile。

And that's why we nest。Both of these routes， one for feed and one for profile inside of this outer route。

So the route for path， the route for feed again， was just the forwardd slash or the base URL。

And then the route for profile was forward slash then profile。

So these inner routes are taking in both path and element as props。

The outer one really only needs element equals app。

But because we want to show a page when we reach some path that's not either forward slash or forward slash profile。

 then we have an error element that displays。嗯。The not found component。Okay。

 so having here any questions about this？I'm going to type this in real quick， too。

Notice that the insider routes are self closing while the outside route。Its not。OK。Should look good。

Moving on。We're not completely done yet， even though we've like created the routing logic or most of it。

 we've created the router， we actually have to like put it somewhere so that it's actually rendered。

 yes。嗯。Yeah， so I think the error element probably could go in here。 I'm not exactly too sure， but。

Like。The reason why we have。Like app is either displayed。

 which displays feeder profile or nothing is displayed at all。 So like。

 if we had an error element here， we sort of wan to catch any bad paths like outside and not like inside。

At least in this case， because like。If it was inside， we would still like be rendering app。对。嗯。Yeah。

 I think they're probably better expertss that reactor out than me。You can probably ask them。

So the next step is pretty simple。 We just go down where we're creating the roots and rendering。

And instead of rendering the app。I'm going to comment that out。

 and then we're going to render router provider instead， which we imported from react router dom。

And route provider takes in。A prop called a router。And we pass in the router that we just created。

Okay， so first a good。Allright， we're almost done。Or at least we're done with the changes we need in index JSX。

嗯。The next thing is， we。Like taking a step back and looking at the component diagram。

 we have the nav bar on the top and then the feed。For the base URL。

 And then we have the network on the top of the profile for a slash profile then not found just takes the whole page if we reach some path that's not recognizable。

So this means that we probably want our NfR to lie inside of app， right。嗯。

Because when we're rendering not found， we don't want to render the naFir。

So this is a reactor writer tree， which you'll see in the reactor writer lecture more。

But this left component is like the element that's rendered normally。 That's the error element。

 And then these are the elements that are rendered based on what path you're at。And so like。

 how do you actually。Render one of these components inside of app。And to do that。

 it's a really simple change。We just go into app JSX。At the top， import something called outlet。

From react righttterdo。And then instead of having the feed。

 we just let the router handle it based on the logic inside index JSX。And then， we just。

Create this outlet。不可认。We won't even need a feed at anything。 It just knows by itself。嗯，嗯。Now。

 let me take a look at the website， hopefully。嗯。We haven't changed the na bar yet。 but hopefully。

 if I go to something like。Profile， awesome。 Okay， now we see the profile component。嗯。

The feed is still working if I go to the base URL。And then if I visit something。Random。

 it's going to show the not found component。O， so。That's pretty much all we needed。

At least for the router。嗯。The last part being， we want to be able to navigate to these different pages without having to like。

 go to the search bar and then like change the URL。So to do that。

 react router also has like links that you can click to change the URL automatically。嗯。

And we're going to add this to our nav bar。So at the top in navbar。

Go ahead and import link from react Rotter Dom。And then。



![](img/374f9e896f9309ae77e8daaaad756d9c_38.png)

嗯。We want these links to be like to the right here and here for a home and profile。

 So I'll just create two links。One link。Has its two or like the URL that you want to send it to to be the base URL。

And it's going to have the text home。And then the other one is going to send you to profile。

I'll wrap all this around in a div。And then。For S CS， I believe inside the NF bar at CSS。

 you can see NFbar link container。And then for each of these links。

 I'm going to give it some CSS as well。NF bar a link。OK。嗯。Now， if I refresh。Press home。

 it goes to home， go to profile。 Okay， awesome。 So these， these buttons work。And then， finally。

I'm just going to get reset hard and show you the final code。

 you can add a bit more CSS to make it in line。Using the UN line block class。



![](img/374f9e896f9309ae77e8daaaad756d9c_40.png)

O。That' was a lot in router。

![](img/374f9e896f9309ae77e8daaaad756d9c_42.png)

Anyone have any questions about router， how we implemented anything here。O。Cool， so step 6 through 8。

 I don't know if we'll have time for all this， but。Step 6 through 8 are analogous to steps。

This is atypo 2 to4。 And where you worked in feeded do Js to create these stories that display on the website。

So inside the feed， which is this outer component， you render lots of individual single stories。

And in Se 6 through 8， we're going to create a card component that contains。A story。

 as well as all the comments related to that story。

And then we're gonna render the comments very similarly to how we render the stories inside feed。



![](img/374f9e896f9309ae77e8daaaad756d9c_44.png)

Okay， so if you haven't already， check out step6。O。



![](img/374f9e896f9309ae77e8daaaad756d9c_46.png)

对。So， yeah， our current component structure， at least at the root of feed。Is feed has single stories。

And now we want to change it so that feed renders a card。

 which then renders a single story and then comments。This is so that inside our feed。

 instead of rendering single story， then comment， single story comment， which is。

 which doesn't really make any sense。Now we abstract away this entire story and come together into one single card。

And that way， we can still map all the stories inside our feed to card elements。But then。

 card elements。那。Or I guess take that story object， render the story， of course。

 but also obtain the comments for the story and then render those as well。嗯。

I guess it's a bit confusing， without an example。Anyone unclear about what this is doing？So。Yeah。

 before。These green boxes were the single stories。Now we're creating this card。

And then the same single story component is being rendered in signed card。

 and then we're gonna render comments down here。So for step 6。

 I'll let you guys work on this yourself。嗯。I highly recommend going to， oh， one quick thing。

Make sure to get pulled because there have been some changes to the branches since。

You probably last checked them out。So at the bottom。Make sure you get pull。

And to make sure that you're up to date， you can do gi status。

And it should say that your branch is up to date with origin slash W2， step 6。

If you have issues with this， also hop on the queue。 If you want help with this as well。

 please hop on the queue。 The staff are not doing anything right now。

 so they they can help as much as you want。But yeah， once you've done that， search up to do six。Oh。

 sorry， Step 6。And then follow all the steps in here。I'll give you around five minutes。

 Feel free to work with the neighbors around you。Okay， I'm just gonna go go ahead and start。

 Feel free to tune me out if you're really close and are about to finish。

But the way I'm gonna to work through this is I'm just gonna go through。

And implement this component tree。So starting at the top， instead of having the。

Feed render these single stories。 I want to render card instead。So， to do that。I can just import。

Card。Which is in the modules folder。And now now that I have access to the card component。

And just taking a look at Car。It seems like I can just replace single story with card because the props that single story take are actually the same as the props that card takes。

 It's just ID D， creator name and content。So if I do this now。And take a look at my website。

 I should see nothing。Which makes sense because I haven't implemented the card component yet。嗯。

As a placeholder。I'm just gonna to return。Hi， and then now I see three highs。

So the card component is indeed rendering。 I just now have to render the single story and comments inside of the card component。

So， let me see。嗯。Looking at Tus or step six， everything that's left is in cart。So。Big picture。

 What are we doing in Card， We're creating a common state。

Or a state that stores all the comments related to a post。

And then we're gonna render that alongside the story that were passed down。So。To start。

 I'm actually going to do this part that we already have， which is rendering the story。

singleing story takes in the same props as card， So single story is ID prop。

Is going to be our props dot I D， which is passed down from feed。Over here。And then the creator name。

Is equal to prop stock creator name。And the content equals prop stock content。And don't forget to。

Import your components。Okay， so it seems like it's working now。All I've done is， essentially。

Ignore the comments。 I've essentially added a new stage between the feed and single story。

 Now it's surrendering card with render single story。And。

The remaining step is adding the comments into the card。So for the comments。

 I'm going to have to use a state store it。So， imports。You state from react。

And then up here at the top of the component， I will define the common state。 So con。Comments。

 set comments。Equals use state。And just like the feed。I'm going to initialize this to an empty array。

So I'm really copying over or doing everything analogous to like what I did in the feed。

And then in the use effect， when the component is first mounted。

 So whenever one of these cards first mounts。I'm going populate it with some comments or some doing comments。

And。For now， let me just do like。Seets comments to。H。

Which means that every single card that's surrendered is gonna have its common state be equal to high after the。

 after the mounting。And then。Down here， just to see what it looks like。

I'm going to JO that stingify this list。The common state。嗯。I'll open the console。

Identifier single story has already been declared。Okay， thanks。O。Yeah。

 so now I see high underneath every single story。Okay。

 and then I'm just going to reset this and check out to see what I would be doing inside these use effects。

So if you could also do this， checkout step7。Essentially， what we're doing here is I've created like。

A master list of all the comments under any single post that ever existed。

So there's three comments that ever existed。The first comment has a parent。Whose story has I D1。

 I D1。And this corresponds to this first story。Because as you see here。

 we created the first story to have ID D1。And then the second comment has parentent ID2。

 third comment has parent ID3。And the reason not all of these comments are being rendered or set to the common state is because。

I'm filtering all of these hard coded comments。To find the comments that have the same。Parents。

And here。As。The I D of the story that it belongs to， that it's nested under。So， for example。

 if I'm here in this component。The prop I D underscore I D that's past sin is I D 1。

This is passed from the story。From the feed component。And then inside the use effect。

 I'm filtering for all comments that have the parent I D I D 1， which is just this first comment。

So that's why when I set comments to this filter， it only returns an array that's length 1 that contains this first comment。

Which is why for all of them， you only see one comment。 But in reality。

 if I added another comment like this。With the same ID。Id 3， then comment 4。Now。

 if I look under story  3， I should see two comments。Any questions about how this worked。O。



![](img/374f9e896f9309ae77e8daaaad756d9c_48.png)

Let's move on to step 7。

![](img/374f9e896f9309ae77e8daaaad756d9c_50.png)

This is just styling comments。 Oh， yes。Yeah， that's a good point。

 great pointcause it reminds me to point out that the code here inside。

These two use effects where we first like load the stories and load the comments。

 This is really bad code。 And we're just using this code to demonstrate what it would look like on the website。

In reality。Yeah， it would start off as no comments。 and then inside this use effects。

 we actually like request the comments for a given story。

 So it's not like hard coded or anything like this。 In workshop 3。

 you'll actually see us like making a request for the real comments that we'll use。嗯。Yeah。

 so this code's pretty bad。 It's just to like demonstrate this point that we can render stuff like this。

还会。Yeah， like， I guess， I don't if this， this is what you're saying， but we could like take out the。

Take out this like master list of comments， put it in feed and then filter there so that we only pass through。

The correct comments。Yeah， there's a lot of ways to do this。

 I think this is how like workshop 3 starts off with the code because it's like less work to transition from this to what we actually want。

 So that's just how we did it。嗯。Yeah， so。Moving on to step 7。嗯。

I will probably walk through this code because it's a shorter step。嗯。What we're doing in the step is。

We're rendering each of the comments inside of the comments state。To a single comment。

So it's really similar to what we did with the feed where we were render each of the stories to。

A card which eventually got rendered into some a single story。嗯。So I'm first going to go to card。

And I'll import single comment。And feel free to， feel free to follow along。

So I've imported single comments。Which resides here， which I'll pull up。To the side。Okay， actually。

 okay， I've done one step for you。 do the other two steps。 I'll give you guys。😊。



![](img/374f9e896f9309ae77e8daaaad756d9c_52.png)

Like，5 minutes。

![](img/374f9e896f9309ae77e8daaaad756d9c_54.png)

Okay， if you're still working， that's fine。 just hit me out。Continuing off where we left。Yeah。

 so we imported single comment and。Like we did in feed where we take the story state。

 which is an array。 and then。Call the map function。So create like a list of components。

We're gonna do the same thing for the comments。 And essentially， I'm just like。

 I'm just gonna copy and paste the code。And then change all the occurrences of stories with comments。

Sorry。Okay， I don't know what happened。One cool trick is instead of resetting hard。

 you can get stash。And then。I'm gonna that like essentially resets the status of your branch。

 I'm gonna check out the next step， just to cheat a bit。Okay， I to copy that。

And then I'll go back to the old branch， and then。It stash pop。

 So it like restores the changes that I just had。And then now I'll just copy paste。OK。So yeah。

 I'm doing the same thing as I was in feed。 The only difference is now I'm rendering single comment。

The I D is。The I D prop is going be whatever I get。Or like the ID attribute inside the objects。

The creatorer name is also going to be found inside the objects。As well as the content and。嗯。

I guess the parent isn't inside there。 You don't actually need to know the parent for the single comment。

So yeah， like if we look at the single comment component now， we see that it takes in ID。

 creator name and content as props。Notice that this is just a dock string。

 It doesn't actually like enforce any of the props you passed in。

 but it's always good practice to like specify what props you want each component to receive。嗯。

So now that we've rendered a single comment with these。With these props。

 let me take a look at what it looks like here。Oh， and of course。Instead of。

 instead of rendering the JSson string a five version of comments， I'm gonna to render comments list。

O。This bar actually shows up inside of single comments， so we're on the right track。

The last part is just using the props that we received from the parent。And then displaying the text。

So on the left， I want to have the creator name。And then。Let me save that。Okay， cool。

 So the creator name now shows up on the left。And then here on the right side。I want to render。

The content of the comments。Okay， yeah， it looks like it worked。

We have the creator name and then the content of the comment。Let's say I create a new post。

This also is looking good to us because if we don't see any comments underneath a story。Essentially。

 if the common state is。emptympty。等。It should see that the length of the comments list is 0 and then return a div that says no comments。

So that's what's rendered inside of this story because there's no comments underneath or there's no comments inside the card component。

That's being rendered here。Okay， that concludes it for step7， any questions about that？Okay。

 get reset hard and then check out step8， please。And step 8 is now gonna be analogous to step 4。

Which was adding a new story。 Now， we're gonna be adding a new comment。

And this is gonna appear instead of at the top of the feed。

 This is gonna appear at the bottom of the card component。 So when you're actually rendering it。

I would just put like the single or sorry， the new comment component down here。

And then pass in whatever props you need to pass in。So I'll give you guys。

If Id like seven minutes to do this， is going to be a bit more tricky。Also。Just in case。

 run get status in your terminal。 And then if you don't see that， your branch is up to date。

Please get reset hard and then get pull。O。Let's get moving。I think by now。

 you've probably realize it like this， all the codes actually， you know， getting pretty messy， so。嗯。

It's actually kind of hard to like figure out where everything should go。

 how all these props and states are passed down。嗯。Yeah。

 so it's definitely very understandable if like all the code is really confusing。

I think it helps a lot to get caught up as much as you can later today， so that tomorrow。

 when we start workshop 3， you'll come in at least knowing all of the react stuff。嗯。Yeah。

 so for step 8。Starting in card。 JsX， I'm going to import new comment。

This is a component inside of the new post input do JSX file。Okay， and then。Over here。

It's actually better practice to put the callback functions and everything else like after the use effects。

 you want to use use state and then use effect and then everything else。I'll just have it up here。嗯。

I'll refer to feeded， which is where we did our callback for adding a new story。And again。

 the reason we need a callback function is because。

The actual state state set is defined inside the card component。And then once。

 when we're passing down。喂。All the comments are in here。 We have our set state function also in here。

 But then underneath it in a child component， we're gonna be rendering the new post input or the new comments component。

 So this new comments component doesn't actually know what to edit when you press submit。

And that's why you need to somehow pass down either the set state function for the comments。

 down to the new post input， or you pass the callback function down that actually runs the set state function。

So。I'm just going to copy what it looks like over here。

I'll create a callback function called add new comments。And it takes in a value。

 which is supposedly a common value。And then sets the comments。To。Whatever the old value was。

With the new value， you cancatenate it to the end。Notice that this actually returns a you array。

And JavaScript doc and cat will return a new array， but dot push will modify the old array。

So dot conca is safe。And another way you could you could write this， which is actually preferred。Is。

list decomprehension， I think。Decompressing that comments into。

A flat end array and then a pending value to the end。But yeah， this doesn't matter too much。

Once we our once we've created this callback function。Now we want to render the。

A new post or the new comment component。And。I'm going to look at the documentation for a new comment to see what we want to call the prop。

Luckily for us。Under new comments。We know that we want to pass down a problem called story ID。

Which is equal to the prop ID。Essentially， the idea that we got from the feed。For the story。

As well as the add new comment function。Which should just be the callback function that we just created。

 also called add new comments。OK。So if I render this now。这说问。Oh， because it's not running anything。

Yeah， so what I want to do is。Render something just to see that it's working。just like。Do that。Cool。

 so it's rendering。 I know that this render is working。

And now what I actually want to render is a new post input。

And then inside the props for a new post input。If I go up here to see what it takes in。

I see that the prop's name is story ID D and then on submit。And we can also give a default text。

Value。So the default text is。ItDoesn't really matter too much。 I'm just gonna say。Oh。new comments。嗯呢。

For story Id。Notice that this was passed in from the new comment from the CarDJSX file。

When we render the new comment， we pass in sorry ID。So this is reference using。Props do story， I D。

Which is the name that we're passing here。And then the。On submit function or the on submit prop。

Is going be this function that we're gonna create here。 orre fully implement here。

 which is add comments。And add comment for now， again， Sam as with the stories is gonna do。Not much。

 besides。Adding or calling the， the callback function that we passed from card。

And then adding this new dummy comments。So the content is whatever value was inside the input。

And then the creator name， anonymous I D。 I'm just gonna say random commentss， I D。And also。

For comments。Remember that the comments all need a parent field。

 which refers to like what their parents' ideas。So when I create a new comments， I also want to have。

This parent fields。And how do I know what parent it has？ Well。

 it was passed all the way down as a prop called story I D。So with this。

This looks like a pretty good new comment， I have the value of the text box。

 the story that it falls under。My name， anonymous user， as well as some random I D for the comment。

And if I。Now， try to type something。I forgot to say propt story id。

But if I now try to type something and then press submit。Changing this to add new comments。嗯。

It should work now。 and I can add you comments using this input。Okay。Yeah。Any questions about this。

As homework or practice or whatever， step 9 is。Not too difficult， It's。

Taking like an old component tree where we have the single story。

 the single comment and the new comment inside the card component。

 and then combining the like these last two parts into one single component。So that way。

 it's like more organized。 We have the single， or we have the story with its own component。

 and then we have the comments with its own component。 instead of having a story component。

 comments component， comments component。 This is just messier。 So step 9 is just doing that。

Combining it into a single commons block component。And then you can check out the completed code。嗯。

W2 completes。OK。This is probably one of the most intense workshops slash lectures so far。

 I definitely recommend going through it again at home。 If you can。 We have office hours。

 which are super， super， super helpful。 All of us are like， really， really。😊，Like。

 we really want to help you understand this content because moving forward。

 we're gonna be going quite fast， especially with like servers coming up in the next lecture。

So if you can nail down a solid understanding of react as quick as possible。

 that's going to make your life a lot easier。In the next few lecturexs。 So yeah。

 please come to office hours。 if even if you're like not even like 100 percent sure if you're like 90% sure about something。

 still pull up， will'll help you get reach that 100%。 and hopefully。

That'll improve your experience in the class。嗯。

![](img/374f9e896f9309ae77e8daaaad756d9c_56.png)

Yes， also， please fill out the feedback form。At Webblb dot is slash feedback。

 If you didn't fill that out for the first lecture， if you could do that， too， that'd be great。



![](img/374f9e896f9309ae77e8daaaad756d9c_58.png)