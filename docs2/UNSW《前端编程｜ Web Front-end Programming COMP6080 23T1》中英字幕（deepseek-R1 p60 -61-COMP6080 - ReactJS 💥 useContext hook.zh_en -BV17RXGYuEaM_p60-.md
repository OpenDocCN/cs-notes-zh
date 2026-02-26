# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p60 -61-COMP6080 - ReactJS 💥 useContext hook.zh_en -BV17RXGYuEaM_p60-

Hi everyone。 My name is Hayden， and today we're going to be learning about the used context hook in react。

 It's one of the less used hooks and it's particularly useful in certain use cases。

 Often it can be avoided。 That's kind of where it differs from the user effect or the use state hook。

 which are kind of the bread and butter of react hooks。

 But I'm going to take some time to explain how it's used and what problem it solves and where this relates to is essentially how to manage your code state。



![](img/5e4c16795529883251f7f857630a695f_1.png)

Beyond a component。 And what I mean by that is that you know how to use the use state hook to manage state within a component。

For what happens if you want properties or state to be available outside of a component across different parts of the application？

 Well， there's basically three ways that you can solve this problem。

The first one is kind of the simplest。Which is using props and passing state down hierarchically。

 hierarchically through components and through components and through components。

 The second way is using a react Js use context tool。

 which is kind of like a way of just having global variables， essentially in your reactor。

 It's like the cleanish way of having global variables。

 The third way is to use a proper scalable state management tool like Mobex or Redux。

 as's a ton more。 But they're kind of the two most popular react based state management tools。

 And those things are essentially like fully fledged， scalable。

 very robust to have a lot of features in them。 really cool stuff。 That's what a lot of like。

 you know， proper corporates would be using。😊，They're quite involved though。

 and there's something that we don't feel is critical to the learning outcomes of this course。

 So Moex Redux， those other state management tools are beyond the scope of the course。

Passing things down by props gets you a lot of the way。

 but sometimes you do want things in a global variable state with this kind of like。You know。

 semi the semi workable methods。 So what we're going do is we're going to have a look at passing props down through components。

 And then we're going to show you how you would do that with the use context hook。

 So when you're passing props down through component。 You're essentially saying， well。

 I've got state in component1， and I'm going to be giving it to both component to end component 3。

 Now I have a small example of this for you。 So I have here a simple。



![](img/5e4c16795529883251f7f857630a695f_3.png)

Let me just enter this down so you can see it。 I have a very simple react up here and most of it is well summarized。

In this particular component。 And what this component does is that it's a main page component。

 It stores a page number state with a set page number。

 It's got a button that essentially on its click all it does is toggle that between 0 and 1。

 If you increase know if I set it to the current value plus 1 mod 2。

 which is just like a way of going0，1，0，1，0，1 because it'll keep overflowing back And that button just says change page。

 And depending on the state of page number， whether it's 0 or not 0。 Ie 0，1。

 It will render the page 1 or page 2 component。 Now this page1 and page 2 component are just two simple components in different files with a div that says page 1 and page 2。

 So really simple。 know， I've clicked that， know page 1 and page 2。

 Now what happens if I want to create another button here， that is essentially it keeps track of a。😊。

Like a counter。Right， so I'll say up， I'll， you know， I'll have like an up button。

And what that up button is gonna do is basically， every time I'm gonna click it。

 it's going to increase a counter by a certain number。 So I'll create a new counter state， right。

 I'll say counter set counter equals react do use state 0。 And instead of 0， it's gonna say counter。

 And every time I click it。 What I'm gonna do is I'm simply gonna call set counter with counter plus one。

 right， fairly standard example， you've seen these before。 let me put a B there。 So， you know。

 we have a bit more。Space on the page like this。 So up up up up， it increases it right。 Now。

 what happens if you want to give that information to page 1 and page 2。 Oops。

 we don't need this down here。 I don't know why that's there。

 What happens if I want to give that to page 1 and page 2。 Well。

 what I would do in this case is I would pass it through as a prop。

 I would say counter equals counter like this。Bam， and then in my page  one and page 2。

 I could access that through props。 I could say， you know， page 1 props do counter like that。

 And I could do the exact same thing for。Page2。Like this prop stock counter， and I'll capture props。

So now you can see whether I change to page one or page two。

 both of those components can access that state， but that's because it's being passed down through props。



![](img/5e4c16795529883251f7f857630a695f_5.png)

The other way to solve this problem is to use the use context hook。 Now。

 I think the use context hook is a very strange hook that isn't super intuitive。

 at least at the time of this recording。 So what I've done is I've gone and prepared a demo that you can essentially copy and paste from the code here。

 You can just go look up the code， which shows you how we would use it。

 So what I'm going to do is I'm gonna unwind the code I've done here。Like this。

And I'm going to go back to main page， and I'm not going to pass that counter in。

 but what I would really like to do is have this counter accessible across the entire application。

So what I've got in my main app dot Js X， right， This is my absolute like most out of file is I've got a whole bunch of code that。

 again， you can go on copy。 Now， you notice before I unmented this code， all app dot Js did。

 which is my highest root component。 was it just return main page。 It was kind of pointless。 Now。

 what I'm gonna have it do is wrap the main page and what we call a context provider。

 essentially anything inside of this context provider can consume these， this context。

 And when you think of context， think of like global variables， right， So every time I say context。

 Think global variables， it's just an easy way of getting your head around it quickly。

 And what you can see here is that。😊，How this is working is that my main component at the very top of my app is actually just creating these two use state variables called var 1 and var 2。

 So this isn't anything to do with use context here。 This is just me making two state variables。

 And if I wanted to use these everywhere， which I do。

I could just pass them down through main page and then main page could pass them down to every other component。

 But you know from programming that requiring like global barriers to be passed through every function layer can really add a lot of bloat and confusion to your code。

 So we're going use this approach instead， which is that what I'm doing is this context provider that I wrap the page in。

 I am giving it a value， which is a simple object that contains my getters and my setters。

What I'm really doing here essentially， is making my use state variables accessible across the entire application。

嗯。How this is working then。Is that I also have a separate context。File here。Which is， again。

 this is just a little bit of boilerplate。 It's a little bit weird。

 But essentially what this context file does is it sets the initial values of my context items。

 and it creates a context like a little set of global variables And it returns that back to my app dot Js。

 Now， again， you can do this a bunch of different ways。

 This is just one particular example that I'm giving you。 Now， again。

 you don't have to understand it fully， because it's not core to the course。

 That's kind of why we're skipping over this because whether you can do this or not。

 we think you understand enough about frontend web development because you could just use local storage for this。

 right， That would just be a bit messier。 And it would live beyond the the lifetime。

 I guess of the page load。But this is just me storing two particular variables。

 So what I do now is if on my sub pages， say my main page here。

 I would like to access those variables like Var 1 and var 2。Right， I'm， I'm gonna。

 I'll keep this counter here for a second。 Let's say I want to print out v 1。

 What I can actually do is I can say cons。Getters， setters note， note the use of braces。

 not the use of the， the side brackets equals。Yall， what is it？Use context， context。Now， again。

 some of you， I'm sure have a different way you go about this。 And that's totally fine。

 Use context context from。Context。

![](img/5e4c16795529883251f7f857630a695f_7.png)

So you can see V 1 there is it's an empty string to start right， so if I just write get' dot。Bowan。

Like this， you can see it's an empty strain。Now， what you'll notice here is that look at the similarities between my use context and my use state lines。

 Notice how they both have a very similar kind of behavior in terms of it's like cons 2 things equals a hook and then something。

 Now this line' is a little bit different。 But essentially。

 what happens is if I include this in any component。 This getters set equals use context context。

 I can then access all of the getters and all of the setters inside of my context。

 And all of that's defined in my app dot JSx。 Again， you can just copy and paste this code。

 So let's say I come along and I say， you know what， I want this counter to be global。

 I want it to just be a global variable。 This is how I would modify the code。 I would grab this。

I would go。Counter set counter like this。 I would add my counter to my getters。

 I would add my set counter to my setters， and I would change its initial value to the initial value dot counter。

 which is defined inside of the context file here。So I would then say， yep。

 my counter's default value is 0。 That's all I need to modify in that file。 And now I'm good to go。

 Now that information should be accessible on all of my pages。

 So here I should be able to say getters dot counter。Which。Should hopefully give me0。

 I can see that it's not。Oh， there it is。 I just have to refresh the page because I added。

 I'd modified。No， I don't know。 I had to refresh the page That's interesting。

 So I've got my counter 0 there。 And now， instead of calling set counter。

 I can actually just call Seters dot set counter。Getters dot count of plus one。

 And now when I click that button， it increases it。 Now。

 the reason this is exciting is because I can now go and copy that and paste this into my。嗯。

My other component files。I have to， sorry I have to include the import。

I can go and paste that into my other component files。 And here I can just say page 1。

Get's dot counter。Like this。And now that works。 So I could go and do this in my page too， as well。

Copy this line。Getters dot counter。And then like bam。 now， but all of my。

 like you can see here how I'm not having to pass anything through props。

 It's all just being like shared through this global variable。 Now。

 the boilerplate that you have to deal with is you have to import some context。

 and then you have to use the context hook。 They're the two lines of boilerplate you have to do to access your global variables。

That's assuming you don't add anymore。But if you'd like to add some more。

 you're gonna have to modify your main like kind of top level component。

 and you're gonna have to add a small value to。Your context file。 again。

 if you have a better way of doing this， please go ahead。 This is not meant to be a teaching thing。

 This is actually just meant to be a helpful tip so that you can kind of go and explore other learning outcomes in the course。

 but please feel free to use this as much as you want。

 wherever the code is wherever the code is hosted in the course right now is where you can find this Itll be under the react react hooks context or whatever whatever is listed on the learning site as well。

 You can also take the time to check out how the course website does it。

 you can go look at the source code online if you want to， it's all sitting here。

 this example is taken from that。 So if you want to go see this used in more detail。

 please feel free to check that out。 And otherwise， thank you。 So hope that helps。😊。



![](img/5e4c16795529883251f7f857630a695f_9.png)