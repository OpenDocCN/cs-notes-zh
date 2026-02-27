# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p64 -65-COMP6080 - Product 🍪 Figma & Component Libraries.zh_en -BV17RXGYuEaM_p64-

![](img/2bbba374d55131a0dfc4ae620dac0bb2_0.png)

Hey Sam here， so today we're gonna to be following on from our last UX lecture where we looked at design systems and we're going to be looking at the practical day to day side of the design system。

 which is its component library just like a builder make sure to tend to their tools as frontends we often have to create our tools for doing our jobs and that means creating a shared UI components that we reuse throughout application creating a component library So as a frontender it's really important to understand have an understanding component libraries today we'll be looking at three things about component libraries first we're going to be looking at how designers understand and seek component libraries because that filters through to how we see them as engineers Secondly we're gonna have a bit of a look at different ways we implement a component library。

 looking the source ones and then third we're gonna look at a tool that can help us impact our component library and I'll be doing a bit of a library。

😊，Coding demo so exciting first onto what is a component library So components。

 I suppose components are little bits of user interface that we can use to put together to make an application examples of components would be like an alert so like a little you know that's got some text and like is in a bubble and likeable warning or error or something a button is a component。

 a slider a badge a card。😊。

![](img/2bbba374d55131a0dfc4ae620dac0bb2_2.png)

'There's endless numbers of components that you interact with on your daily life。

 so often we don't want to re a button from scratch every single time we're building a new page application so we use a component library that lets us define what a button looks like in one place and then reuse that throughout the application。

啊。Component libraries is really important to note isn't something that just developers think about。

 The idea of reusing and creating consistency is really important to user interface design。

 A great user interface isn't one that makes the user think。

 You don't want the user guessing at every screen is this a button or is this not you want to have a sense of consistently throughout the user interface。

 So we see that designers often have component libraries as well for a designer component library is a collection of graphical elements that they can reuse。

 So we're making a mockup of a new application at Canva。

 instead of having to redesign what a button looks like I can just grab a button from my library。

 know punk it in the app and start using it。 and diso for frontenders。

 So obviously front enders they know graphical elements they are pieces of code But if I want a button I can import from Ui based button。

 I have a react component and I can use that So I don't have to think about styling。

 So that's a very high level of water component libraries。

 But I think the first question is how do designers。😊。

understand component libraries so I think in order to really understand so we talked about the sizes of last week why they want a component library to create the sense of consistency。

 but we need to take a step back to understand how user interface designers are creating their designs and see how components figure into that process so。

So if we have a look at popular user interface design applications。

 we find out about things like Sket Figma or Adobe's XD application and it's really interesting to think about these applications might we're familiar to So and lot lot of people are familiar with Photoshop which is for editing Ra images and illllustrator which is for editing vector images so often designed user experience user interface design vector images they're made up of paths rather thanre being made up of pixels that allows designs to resize them what people might not know is that the applications the user interface design users usually isn't the same as the standard vector I apps like Adobe Illustrator or Iscape so these standard apps are often really good for drawing know you've got lots of tools to make beautiful swirlly paths and create illustrations for magazines with banner。

 all types of things。😊，However， as a user interface designer。

 you usually don't want swirlly cards to write like how many times have you used an application and seeing lots of swirlly lines in often user interface designers it's straight lines。

 its text and maybe some example images that that's about it so there's a different class of application。

 which is it's vector just like the illus landscapescape but it's。😊。

It's it's got features that are tailored for creating user interfaces those features usually come in the form of styles and components so we're gonna take a quick look at both of them today I'm going be using the Figma language for these tools like different tools will call them different things so components in Figma are called symbols and sketch but I think it's the same conceptual ideas FigMma is a very popular tool that you can get FMA iss also a browser based tool's this's great free plan if you want to try to self but conceptually this is the same across most tools that user interface designer will use。

So嗯。What is so in Figma you have the concept of a style I think a style is quite self explanatory It's a bit like a variable。

 so you can have a color style， which is where you define in a shared library。

 know this is the Canva blue， this is Google blue， this is thelassian blue or whatever you're designing for and you can reuse those colors throughout and then instead of having to remember the hex codes to use everywhere So that's kind of like a variable in programming sense know you could check a variable in in your SAas or in your ja if you were implementing a component library。

But then they also have this idea of components so components in react terms are like they're a collection of HTML elements and give some code condition to create them components in a Figma term are quite similar error。

 they're a collection of graphical elements， but obviously there's no code to create them but what they do have just like you know buttons are kind of linked together because they're generated from the same code in Figma if you create a component all instances every time you copy paste or duplicate that component。

 they all remain linked together unlike a simple group or a static illustration what that means is that if you edit the original version of the component。

 the math star， it will。All of the instances of the component will update with the changes that you've made。

And that allows you to create that sense of consistency but it also allows a designers for flexibility you know if I'm designing a complex application I might not want to have to design the button first or maybe you know design a complex application and then my client's gonna be like I love it and I just hate I don't like how thick the shadows are I don't want have to go back and change it individually I want to be able to you know switch between designing base components designing applications and have everything kind of fluid update。

😊，To give you an example of what I mean， I'm going to jump into a quick demo using Figma so images。😊。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_4.png)

Jump over。 All right， here's the scenario for the demo。 I'm working on job site。 It's like LinkedIn。

 but it's not LinkedIn。 maybe I don't know pull it sand in few minutes and I'm making a mobile app my job site So important component of his mobile app is gonna be the kind of list item that I can click on So first I'll just draft this inigma So I'll draw a rectangle this is using the R key graphic design software I'll use some styles on the site So rather than you know getting risky and getting the wrong shade of white I just choose the mono whitehite style that's from a library that I set up for as a designer so I can jump in there add a shadow and the border radius suite now I'm gonna go and add I'm just gonna add some text again using the style So checkuck in a large title。

😊，嗯。我怎啊。I'llCheck in the last side of the job。这个。Y， Im talking medium title sweet。

 so I chuck in my title， I ch in my sub title。Job location whatever you're getting the idea that this is a component that I'd like to use。

Throughout my application， sweet， I'm vague going to just regrade the component that I've already drafted and I'm jumpping a circle not comment a circle。

😊，So I'm not a designer， so I'm not teaching you guys to how to design something press command G grouped it all together so we'll call this job。

在。Sweet， so I've got a group。😊，If I duplicate the group， I've got another group， you know。

 I can drag one group around， I can edit the group blank。😊。

Nothing is the here right that's exactly the same This is not a component at this point。

 but if I' can do all that delete the copy， if I first click the component button here。

Create component we'll see it goes purple to note that it is a component and why do you depend that？

I can move the you ahead to copy around， you know I'll set up in my in my mock up here we go。

 I'm going to have you know a mock up of the jobs page with lots of jobs。

I set up set up my jobs page put the components in there Now if I go and then realize I'll ship the the logo circle here。

 it' it squash it the wrong size， if I add it in the original component。

We see that it's now updating every instance that the component so that's what I was talking about when I was saying they' linked right I can move it around in the original component on the left and in all of the instances on the right update that's really useful。

Another really cool thing about components is they do allow some level flexibility because in this job list I might want to demonstrate in the mock up。

 but not all the jobs are the same so I might want to have， you know this could be a job at Canva。

 this could be a job at you know another company company doing。

And you say it' let me edit let me edit the bits of the component。

 but still then if I go and I change something also the component。

 so maybe I decide actually we need to make this stand out a bit more。

 it's updated the attributes that haven't overwrittenden so the job title is now rare or whatever color I want to make it even though I can edit little bits of that another kind of technique they use as a designer is showing hiding so you seeing this title in the original in my kind of。

The components that I've prepared earlier， got we've got a new version here too。

 so provide creating instances of that。I can actually show and hide。

 I can go into the instances and I can show and hide the new batch。

So I don't want the new badge on those and that's really useful because it lets me I can go and edit the new bad later have they unfortunately bigger on whatever。

 but it will update all the ones that have the new badge and it won't change the minds where of hitting the new badge。

So that is components。They let me what has that let me do as a user interface designer It's let me let me change things afterwards after after I've started using something。

 which gives me more freedom in my design process， more freedom go backwards and forwards between it's the design small bits of the design and that lets me my app more quickly because I't I don't have to get everything right signed up in those components then we can never change them again it's way more flexible and that also lets makes me more effective to a designer lets me get more consistent user interfaces great This also means and I think this is where it's most useful is that your user interface。

 anyone who'sing if you're working with someone who's designing user interface for you they're probably thinking in terms of components too So as designer here you have to make a decision about like should the new button be its own component like what's too big to be a component the individual text of the job title that's probably too small to be a component because it's not very useful to reuse that but what is the correct level of。

Draction， for instance， which in many senses is actually very similar to decisions that you as a developer need to make when you're making a component library。

 you need to decide what is a component versus what's just some user interface that doesn't go into the library that's not special enough to be reused in multiple places that you're just going to copy paste if you need to。

Yeah， so I suppose the moral of this story is your designers are going through similar things so you towards you can look towards what they've done to get inspiration about how to use it and then just to give an example I want to share an example of one of the component libraries that's built into Figma so here we go we've got this beautiful component library here as examples of what components might to include you see we've got you know we've got different inputs。

 different buttons， different check marks， different loops content and this is really helpful because that means then if I want to go and make a。

If I make a new design for something， it's very simple that you know just。Boom。

 drag and dropping the search， drag and dropping this thing you know very simple makes my life as a designer easier and thinking in the same way that I just want to drag up components allows us create con phone libraries and make our lives as front enders easier。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_6.png)

Sweet， so I think that' that's enough of viewing it from the designer perspective what do we do now that we know we have some components。

 we know we want to reuse them， how do we do that as a front ender。Well。

 I think there's two there's two。Theig ways we can implement a component library as broadly two strategies The first one is a CSS space strategy and the second one is a react or using the framework that you're currently't using strategy so in a CSS strategy example that might be bootstap or materialized AO that would be a like shared CSS file or a library CSS files that provide class names that we can use to create a component so that we know it'll implement a dot button class dot alert class a dot slide or whatever a react or framework one it's going to give us react components that we can import for eachUI component。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_8.png)

Let's look some pros and cons of each approach。 so vanilla component library super it's super easy to use very。

 very simple。 So here's an example of bootst that's really popular vanilla component library we see but a dear I've had to add some。

I had to add classes so it's an alert， it's primary alert， add the text， it's just normal HTML。

 I'm adding something components I have to make sure to add the appropriate classes there。Also。

 if I need to want to do non CSsS related things。Being more accessible by using a role property。

 I have to remember to do that because it's obviously it's a CSS file it can't add R properties it can't add roll properties it can't help you with accessibility so you can only help so much。

So that is one of the disadvantages so just going through quickly with a CSS we're using class names。

 it's often using a pre assesssor such as SAS S CSS S ASS or less to generate the CSS dolls。

And the pro is is that is' really easy to use and you can use it across nonre pages so if you have a marketing page re application that's just like static HTML easy。

 you can just import the same CSS file， you can be consistent。😊，Big con this。One。

 not everything can be implemented in pure CSsS for instance。

 if you want like a menu that pops up when you click down there are some crazy radio un hacks。

 but like generally you're not gonna be implemented that in CSS you're can to need some jascript Often these libraries do provide some jascript that you can use so it's like a bootstraps file and you add like and it reads looks scours the dom to elements with certain class and add the functionality to them that can be really there are there's the pendulum that conflict with the mutation to the dom that react is making because it's not all going through react but also it adds extra complexity because now you have your react editing the dom and you also have bootstrap editing the dom So that is a real downside the added complexity Second is the like of know any form kind of type safety or even throwing errors when when you made mistake I can maybe type I and alert and it I'm not going。

I the only way I would be able to notice that is visually it wouldn't throw an error or something wouldnt and if I was using Typecr they wouldn't be able to get tight errors from that which you know we don't want errors in our program that's for sure the third one。

Is that bad accessibility as we're talking about， if you want to add extra attributes elements such as for accessibility or for functionality。

 as we talked about initially， you have to open manually。

 But fourth and I think this is really important is that there' poor encapsulation I can't define the API that lets people edit the styles very easily you know they can just add more CSS you know kind of hook in that makes it really hard for me is to update my component library because every CSS is inherently global as Tom talked about any CSS in JS talk and since you can just add more CSS to override things。

 it can become a mess quite quickly。Obviously I wouldn't present two types of things and one there only cons but didn't have a solution so another way you can implement a complaint library and this is definitely the way we'll be looking at today is in react so that is every component such as a button and alert whatever it's just a react class and you just import it from you know you have a shared react file。

😊，And using ports pretty pretty standard stuff this is great because you can you can define the API to so going through the problems that we have with the last one you can define exactly the API for customizing things you know you don't have to let people add extra class names to your component you can just say you know the only way you can customize this component is for instance passing a severity prop to the component of an alert here from this example is from。

Material Ui so yeah that would be you can define exactly the API you want to overwride things and that can make it easier to use。

 but it can also make it easier for you to upgrade things later each component defines their API which makes it more type safe each component always has a do node because each is like a react element an almost always returns do node so that makes it more encapsulated。

Yeah， and you can use any method that you want for styling the components。

 you can use style components， you can use CSS JS or you can just use plan CSS files。Pretty。

 it's pretty cool， so that is。I suppose that is one of the reasons that people often opts to create component libraries and react by exporting files rather than exporting rather than having a shared success file。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_10.png)

One thing that you will know。When when looking at component open source component libraries and I employ you to do that。

 go and have a look at up material UI for react or bootst that's a CS one。

 when you're looking at component libraries， they have great demonstration pages。

 So often have examples of like， Here's what an alert looks like that's read。

 Heres what want an alert。 Here's what every example of a component basically is rendered then。

 This is really good。😊，And again you really the component because you can see hey。

 this is what components people built， but it's also really good as a developer of a component library because you can quickly see here is every version of this component when you make a change。

 you see how it updates every state that gives you a little of confidence when you're making changes and having confidence preventing errors I mean that's what you want you don't to you don't want to be introducing bugs and when you can see everything all the different states of a button。

 one with the icon on the left the icon on the right， you can make changes with confidence。😊。

And often。So as a third part of today's talk， we're going to have a look at at ways。

 a way that we can create amazing kind of demo pages like this that can let us make changes with confidence and also develop things faster so if I'm developing a button in that application I might have to wait until I've finished you know developing enough of the other busy application and until I have the spot where I look for。

😊，On the other hand， if I have a cool demo page like this I don't need to wait I can just start developing all the buttons and now and then I can go and use them later as the app gets more fleshed out this is really important in larger applications you know think of you're developing a date pick but your date if your only time you pick a date is like three menus deep in setup screen。

😊，Every time you reload the page to you know oh I need to make a change to the data picker you reload the page to do the new version if the only way you can access that is through of the app that means you have to navigate three menus every time and that's a terrible developer experience you're not going to be productive if you can't see the changes quickly so that's the third reason why having a great demo on page for all your components is really helpful it lets you develop things in isolation rather than having to develop things inside the main app。

So what's the way that we all get up doing this well it's a storybook page。

 it has all of the advantages that we talked about we can build the components before the out they belong in we can see all the states of components next to each other and we can reload and preview them without having to navigate to the rest of the app。

So the way the storybook works is that is there separate entry point to your application。

 the storybook or the harms page， but storybook's a common name harms pages or another name so you have your code single code base all your files。

 all the components to them then then we go at the top we have abnormal entry points so that might be we run young run start youngn run build whatever and that builds your app like for instance Canva gray app then we have a different entry points so it's using the same code but instead we use young run storybook and it builds a different set of files So instead it won't use it won't build all the normal files it build different files So it's building it basically different。

😊，And it builds your component library then you can see the demo page and you can see all the components in one spot and development quickly Obviously you ship the normal entry point to users that's what you know if you go to Canvacom you see you see the camera application and you don't ship your storybook harness page to users you just keep that any code base and it's just the development and internal usages so you know you don't go to Canva parliament and see a page that has all of our different buttons on its that's a company secret So so。

😊，I'm going to jump into a quick demo I prepared that earlier that uses CR reactor and it has a simple alert component I'm going to demonstrate how we can set up a storybook inside C reactor and I'm going to demonstrate。

😊，Creating a story up for that alert and I'll show you what that would look like and how it would help me developing in the future so Sw let's jump into that。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_12.png)

This wait， as we see here， I have a prayer right that if I yarn run start。

 it's going to start my normal app and。

![](img/2bbba374d55131a0dfc4ae620dac0bb2_14.png)

![](img/2bbba374d55131a0dfc4ae620dac0bb2_15.png)

And as you see， this is my normal location， silent location， whatever I was in in， you know。

I can't see the component I'm developing because we'll pretend that it's like three menus deep inside my application。

 but in reality， I just haven't written the application。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_17.png)

So which is two valid reasons to want to have a strokebook so here I have an alert component hopefully this following course now this is new we have you know it takes a children parameter。

 a children prop sorry for the content and it takes a mode prop which will define both the styling through the class name here and it'll also we've got a little switch on the mode to add an icon which is pretty cool yeah。

😊，So that's great what we're going to do is we're going to use storybook。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_19.png)

There is a page of documentation on storybook I've included a link in the presentation which I'll share around afterwards but so so we're just following the documentation and using NPX storybook in it so NPX is just like it's a special NPM command that downloads a package and runs it so this is downloading storybook running it and it's running in it so that's it's going to scan my current configuration。

Of my build， I'm just using Ceract very standard and it will install storybook。Sweet。

 so now we've got storybook set up， we're just going to yarn run storybook。

Although yeah we're going to ask the storybook。And just like yarn runs start and C react up runs A ya。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_21.png)

run a dev server business just's going to start a quick dev server we'll also notice that we have a new terminal you just go to our Pro directory。

系。If we list SLC its storybook as added a folderable stories with some auto generated documentation content。

 we don't need that for today， but if you're using yourself how quick we' check out the documentation。

 I'll just get you remove that sweet。So in here we're going to create a new file for our story。

 we're going to create alerttortories。 jSx。That is。

So we've got a alert of Js and we've got a alert of stories。

 Js and that's quite I think that's quiteplan we'll just import we'll import alert here because that's what we wonder by the story of。

So again， we're reusing code， the code from the main application。

 even though this is not going to be the story itself is going to be included the main application。😊。

We have to export the bulk of the title of the story。

 so this is alert is that's the title for all the stories and it's just read the documentation very simple。

😊，Storybook stuff。And then we're going to export cons。

And this will be the name of the individual story， so I want to do first with a story about the error like so our export constant error。

I'm just going to exploit the component that we want to use so that in this case that's a word。

Then we're going to set error， do it。Aeroal as equals aal as， I'm going to set that to the arguments。

Of。Any arguments that we want to use？For our story。 So in this case， that's going to be our mode。

 You know， we remember back to what error took it took for children and mode。

 So we're just going set mode to error because that's what our error look is going look like。

 we're going to set the children to。That's what the story was like。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_23.png)

So so we we ci that。Right。So this is load up storybook and we see right here boom。

 we have the alert component。 I'm not a designer。 doesn't look great， but is narrow alert。

 We obviously have controls here where we can change the properties we send it。 So we will say， yay。

😊，Now， this is a struggle。So this is great， This means that as someone developing a component。

 obviously an alert component， very simple component， but it a more complex component。

 a date picker an alert with like 3 billion variants。

 very easy to test it because we can just we can just control it here without having to go navigate through the main application So I've talking a few more examples right we can check in a。

😊。

![](img/2bbba374d55131a0dfc4ae620dac0bb2_25.png)

Morning。Another warning in here。And so the morning prop and obviously some warning。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_27.png)

Yeah， and then the。

![](img/2bbba374d55131a0dfc4ae620dac0bb2_29.png)

冇。Yes are we we said。

![](img/2bbba374d55131a0dfc4ae620dac0bb2_31.png)

啊，你。What we have to do here is we want to obviously because we're assigning we're assigning something or that's just remanming so create a copy so we set the R it's standing on both it with the same variable so storyorybook has this pattern where you go to bind and then an empty empty right and empty audit story and what that does is that creates a copy of the function。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_33.png)

![](img/2bbba374d55131a0dfc4ae620dac0bb2_34.png)

So same code that is a different copy， and that means that when we assign to it。啊。

Our warning and error stories will now be different at。 So this is great。

 This means when I want to make a change， you know， for instance， I'm going to change。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_36.png)

Maybe I decided we don't want the icons anymore， boom I removed the icons。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_38.png)

I can very quickly go back to Storybook and in content。

 see examples of this with all the different versions of my component。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_40.png)

我想。So that without I demo using storybook I just want to highlight one cool extension of storyboard is that storybooks can be used for visual regression so if I wanted to go and check and obviously the alert is a very simple example。

 but for more complex things such as you know the landing page here which we here's an example of a visual regression test in the real world we have a landing page here。

And we can see a visual regression test basically will take a screenshot of each storybook item whenever I make a change。

 so know just like running tests it might happen it on a committee if it might have it on poor request or you might be when you run it locally so a visual regression test suite it'll go through itll take a screenshot of like all of your storybooks and it'll diff them to the last version of the screenshot and that's really good for detecting unintended changes or you can run it across multiple browsers and you can see when something looks different when it really shouldn't so that's that's another great reason that you would want to create a storybook or harness page。

In summaryum day we looked at UI component libraries， we looked at FGma。

 how FEma has great and other user interfaces software it's got great tooling to support you creating user interface and five libraries second we looked at ways you would implement it we looked at a CSS based approach or react based approach both of them have their pros and cons but you'll often want to create react components instead and then thirdly we looked at storybook as a way to create great demo page so you can develop a component library without having to develop the whole app around it and ultimately thats fluidity lets you be more effective get more stuff done quickly。



![](img/2bbba374d55131a0dfc4ae620dac0bb2_42.png)

放生成 next time。