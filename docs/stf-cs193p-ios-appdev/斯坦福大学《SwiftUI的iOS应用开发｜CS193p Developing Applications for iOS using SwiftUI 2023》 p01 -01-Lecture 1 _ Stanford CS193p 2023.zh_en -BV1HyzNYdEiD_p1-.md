# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p01 -01-Lecture 1 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p1-

。Hello internet and welcome to Stanford CS193P developing applications for iOS using Swift UI。

 I'm Paul Haggerty， who've been teaching this class for 13 or 14 years and occasionally I will record it and put it up on the internet for all to see so that you can see what we're doing here at Stanford。

Fortunately this quarter I did not do that， we are back on campus here after the pandemic。

 I didn't set up all the cameras and all the stuff that's necessary to do that so I really apologize for that。

 however I did record the screen of my laptop I had to do that because my students for their assignments one and two need to follow along with what I'm doing and that requires them to be able to look back and see the demos。

It's good for you too because you can do the same thing it's also very good for my keynote slides where I go over some of the concepts of Swt UI。

 etc ceter， and I also put this airpod in my ear all quarter so hopefully the audio and all this will be pretty good。

Unfortunately， there are some things that。E in real life here that weren't on the screen。

 for example， this card game that we are developing。

 I made some actual cards for it and I use Lego as an analogy quite a bit you see my Lego helicopter。

Infamous bag of Lego there you will definitely hear about those when you are listening to the demos and we also have this very beautiful large projection screen right here and I tended to walk in front of it and gesture at the code and you will obviously not see my gestures there and also maybe the fonts hopefully they're going to be big enough for you to see on a small device but might have to go to iPad size or whatever but I think it's generally going to be pretty good。

Now this is a university course my students are taking other classes。

 I'm trying to pour this information into their head one week at a time over 10 weeks and we have a little bit of a systems bent the way we approach this we're trying to understand not just how to develop an app for iOS but how does the SwtUI system work as a whole so that may be something you are or are not interested in but whatever interest you about developing for iOS here。

're going to definitely want to go to cs193p Stanford。

edu you'll find links to these videos here of course also you're going to find the homework assignments which I highly recommend you do to learn this stuff and also demo code I only make the students type it in the first few weeks and after that I post all the demo code for all the demos that I do in the course。

One other thing to be careful of this is being taught in spring quarter of 2023 and right down the road as we speak。

 Apple is giving their WWDC their worldwide developer conference and they're probably inventing all kinds of great news with UI and iOS things and some of those changes might shift a little bit as out from under what we're teaching in this quarter so if you're watching this。

Even late in 2023 but certainly 2024 and beyond， and you might have to take a little bit of care to see if some stuff has changed that makes this a little different than what's in the course。

 now this is an intro course so I don't expect a lot of stuff to change out from under it but it's something to pay attention to。

that's all I can think of to say， I hope you enjoy watching these videos and best of luck to you in your life as an iOS developer。

Okay well welcome there to CS193P this is like when the pilot says we're going to Cleveland make sure in the right place。

 this is what we're doing developing applications for iOS using Swift UI and I'm only going to spend just like five minutes here on slides and we're going to just dive right in and that's the way this course is going to be most of the time I think you learn the best if I just show it to you as opposed to slides but there are some things where I'm going to have to put some slides to talk about concepts and all that。

So what's this course about SwiftUI in particular is what this course is about。

 mostly we're going to develop application for iOS the first seven or eight weeks for towards the end of the quarter。

 I'm actually going to show you how to use what you've learned in SwiftUI to build a Mac OS app or even a watchApp or Apple TV that are all the same SwiftUIs use for all of them。

So what are you going to learn， you know some things are going to be kind of familiar to you。

 like object orientator programming， the programming language is kind of C like。

 but really we're hardly going to use object orientator programming in this class so that's mostly just kind of experience for you that will help you learn the new stuff and the new stuff includes a new language。

 completely new language functional programming instead of object oriented programming how many people here have written some code in a functional programming language。

Actually that's a lot I mean over the years and first time I asked that zero next year May one or two and I'm seeing a few of you so you know languages like HaSkell and all that stuff those are functional programming languages most of you I can see have not add that I'll be walking through it I'm not going to assume you know anything about functional programming you're also going to learn about a different way of user interface programming how many people have done some user interface programming in a reactive user interface system about the same number again less than a third of you so I'm going not assume you know anything about that as well and then at the end of the quarter I'm going to talk to you a little bit about object orient databases too。

And probably the best thing you're going get out of this class is you're going to see real life application of all those things you're learning in all your other classes。

 okay， just a little bit of all of it， I've listed a bunch of them here。

 but that's one of the best things about this class just integration of all those things is we're going to do all up everything there we will be doing。

Prerequisites someone asked about this before the number one prerequisite in this class is some experience writing code because it's all coding okay all your homework assignments。

 you got a final project is all coding I'm not gonna ask have quizzes on concepts you're going to show me that you know how to do it as the quarter goes on so if you have not written a lot of code in your life this is gonna seem like a lot even though each assignment is actually not that much code some of them like assignment 1 maybe it's a dozen lines of code and it kind of ramps up but even the biggest one you write which is probably assignment3 maybe it's100 lines of code but it seems like a lot if you have written a lot of code so that's the number one experience so I put CS16 A and B and 107 and then 108 for example。

 I put those as prerequisite just to make sure that you've at least had some experience because some people show up to this class maybe they've only taken CS16 a and it's like that's all the code they've ever written okay maybe in high school they did Ap computer science or something this is really to get you along there。

I do also want you to have learned some structured programming methodology like objectoriential programming。

 even though we're not gonna to be doing objector your programming here。

 at least when I teach you functional programming， you'll have the idea oh yeah there's like a structure there's classes and inheritance and instances that you have an object or a programming functional programming has a lot of things too that are like that conceptual things you see what I mean and so I want you to have had that experience that's why 107108 is a great prerequisite for this class because object or programming like CS43 which I believe is functional programming that's a fantastic prerequisite for this class but not random people have it Another kind of pretty hard prerequisite is that I hope you have already learned more than one language like Python and Java or C+ plus and some other language just so that you're not learning a new language in here it's the first time you've ever seen a second language you know every time you learn a new language you start to see what's common to everyone。

Language and what's different in every language and that there's a learning curve there right it gets steeper and the more language you learn the more it flattens out where it's just less work to learn a new language if this is your second language ever you're learning you're on the steep part of the curve right if it's the third or fourth now you're starting to flatten out a little bit that's another one I put up on prerequisites and all of these things are things that the more of this you have the easier this class is going to be and the less of this you have the more of a challenge it's all going to be。

How does the course work mechanically how does it work Well number one thing I'm listing here is Ed discussion on canvas do not be shy if you have a question or're doing your homework。

 whatever about hitting this in lecture it's mostly going to be demos I'm going to be walking you through code and it says here lots and lots within an ever growing narrative context okay what do I mean by an ever growingrow narrative context so I'm going talk about the narrative way of learning to do a system like Swift UI versus what I call the vignette way the narrative way is you learn all the characters and settings of Swift UI and some plot along the way but mostly you're learning the world right your world building and we do that by telling the story of developing a Swift Ui application we're going to spend the first five weeks in this class building one big application as animation and all kinds of stuff in it。

 but it's going to provide this context that you're very comfortable in as I add new。

Pieces to it right you'll know the code you'll know what I'm doing and it also at the end of it。

 you'll see what it's like to build a big application It has a lot of stuff in it versus the vignette way of learning。

 which is way a lot of people learn to do Swt UI program which is you just kind of hacking away and you're like I need to do drag and drop How do I do it and you go on Google and you say search drag and drop and you go to some website and there are some fantastic ones out there and they'll say here's a little vignette how you do drag and droprop right here's the functions you call here's the thing you got to implement and you just learn that little thing that's why it's a vignette right it doesn't even try to tell you the big story It's just telling you this one little story about drag droprop about animating in a certain way。

Now which of these ways is a better way to learn clear winner， the answer is。

The combination of the two All right， you get the narrative thing from me in the next 9。

10 weeks and then you're gonna be totally set up when you go to use vignettes to learn that you'll know the story。

 you'll know the settings you'll know the characters So all the little plots in the vignette you'll be ready to go That's the answer both and the vignette stuff on the Internet is fantastic I'm not gonna name any one of the people in particular because I don't want to slight the others。

 but there are some really really great people online doing fantastic vignette stuff So that's what you're gonna to get is that narrative approach and that's why we're gonna to do one big app in the first five weeks。

 then we're going to do another big app pretty much the same size app in only the three weeks after that because you'll know so much more from the five weeks you'll be able to quickly do a similar size app and then you're going to do a third one your final project you're gonna get three weeks to do that as well。

Then I sometimes do slides like this， but not much again， concepts mostly only。

And there are reading assignments， there's basically one document。

 the Sw programming reference guide， you are going to read that entire thing Okay now that's a lot to consume and I'm going give you four weeks to do it and I'm actually going to guide you through it read these chapters first and skip over that and come back to it later so that you can consume such a huge amount I do not expect I'm not going give you quizzes on it I don't expect you to know every single thing the most important thing I want you to know from reading that is what's in there because when you go to do the vignettes or even later in this course and you're trying to do something you'll just know oh yeah。

 there was something in there about optionals what was that again and then you can go back and find it and read it if you don't do these reading assignments assiduously and go through every read every line of it you won't really know what's in there that's what the reading assignments about very important to kind of background noise only for the first four weeks of the quarter then you're done for the rest。

And then of course there are programming assignments， six of them in the first seven weeks。

 one week each， most of them are due on Wednesdays。

 so you'll have one the day after tomorrow this due next Wednesday。

 assignment two is the exception it's going to be due on a Monday， a week and a half later。

 and then assignment three will go another week and a half and be back on Wednesdays for the rest of the time assignment three in this class is like a midterm。

Make sure you schedule yourself to have time to work on assignment three it is the first app I'm going to ask you to write on your own the first or two assignments you're going to build on what I'm doing in lecture assignment three it's like okay now show me that you can do an app all by yourself basically it's similar to what we do in the first two weeks but it's still you're on your own so assignment three like a midterm。

And then finally there's this final project you get three weeks to do it。

 you can pick whatever you want to do it， there'll be a rubric。

 a very strong rubric that tells you what I'm expecting from you。

 therell be a process where you submit a proposal for what you want to do and I'll just kind of take a look at it and we'll see does that gonna fit the scope of what the rubric is saying some ideas are more easily you can satisfy the rubric more easily with some approaches some final project ideas than others。

 but that's you can start thinking now what you might want to do with the final project。

 you only get three weeks to work on it， I guess only I mean three weeks in some ways a long time but in some ways a short time one thing I'll say about the grading know this class only pass no credit and pass means you've prove to me you can write an iOS app that means you pass this class and you do that in two ways one you pass all the programming assignments at least show me that you minimally understand what I'm asking you to do in all of those and you pass the final project and that's an and don't think that you can just ace the。

The weekly assignments and then to blow off the final okay in fact。

 or the other way around actually don't think you can blow off the program assignments and then just nail your final and you're going do it I need to see both things happening okay and the course details document there's on canvas read that thing every line it describes all the course logistics I'm just emphasizing a couple of them here prerequisites and this I'm not going go over the rest Does anyone have any questions about course logistics before I dive into the actual course content here。

Okay， great， let's do it。I saw that almost half of you have done assignment zero。

 assignment zero is to install this application Xcode and to hook it up if we go to Xcode settings up here。

Can see that there's a couple of things to set up here。

 an Apple ID you have to set up and then a Github connection so you have to do these two things。

 Gitthub is how we're gonna submit all your assignments and I'll be showing you how that works in my demos here and the Apple ID thing it's just required by Apple it doesn't cost anything neither of these cost anything Github。

 you can create your own free account and the Apple ID you don't need to pay you can have a paid developer account with Apple and you only need it if you're gonna to use Apple's server technologies like game center or you're gonna put an Apple on the app store These things use server space right in Apples servers and they charge you $99 a year that is the developer fee you won't have to do this in this classroom I'm not going to ask you to do any of that stuff so you're good to go。

When you run Xcode， this splash screen comes up and along the right there you're going to see all the projects we work on this quarter。

We're going to start here by creating a new project。

 I can click here to do it or I could go up here file new project same thing and it goes here and you saw this I'm not going go over this because it's all covered in assignment0 but we are going to be building an i app we will be doing a document app later in the quarter and these other ones games and all this I just don't have time to cover all these other kinds of app but it gives you an idea of how much there is in SwiftUi there's just so many different kind of things you can do again。

 I'm just telling you the basic story right the characters in the settings of the basic story we're going to go I app here it's going to ask us a few questions again。

 I covered this in the tutorial。Here we are， we're ready to build our app。

 I'm going to show you what app we're going to build over here in a physical version of it here。



![](img/fd5caeec976b16b76b3bd6af3aa91f7e_1.png)

It'ss a game， probably you've heard it called concentration， okay or memory。

 the idea is there's these cards， I get these 12 cards up here and I get to kind of guess so I'm just going to flip one over。

If I can do it here， yeah。And then， oh， I have a pumpkin there。 Okay， and then I pick another one。

 like maybe this one。It's a ghost。So I don't have a match here， so now I'm going to pick another one。

 and when I pick another one， these two will go back face down。All right。

 but I have to try and remember what was there， right， I had a pumpkin there a ghost there。

 so let's see what we have here， I'm just going to flip them up。 There's a witch。

And what do we got here？We have a cat so now we have four different things you're going to have to help me here because i'm old and so my memory is not very good。

 but what do we got here oh no a spider it's not going well here that。

You all remembering all this what I got down here Oh bats。

 luckily that was the last one so now that I know that the bats are right here。

I'm going to pick this batch right here。W I got a match and now the next card that I choose。

It's going to take these cards away because I've matched them and presumably i'll get some points or something for these right i'm going to score this in some ways and part of your homework assignment is you get to decide how to score this and this scoring can be very sophisticated not just points for a match or maybe penalty for mismatch but timing like the faster you pick them the more point you get or something so anyways when I pick this。

Next card up here， let's say。The cat leave the cat face up here。 And then I said， keep going， right。

 What do we go here， Cat， I think we had。 Here's the pumpkin。 I think that was here， et cetera。

 So I'm going to use these cards。Hear us props as the quarter goes on to talk about features and stuff we're doing all right so everyone understand the game we're building。

Now it's a simple game， but we're going to be building a game with all kinds of animation。

 the cards moving around and the animating and flipping over and all these kinds of things and we're going to call this app memorize。



![](img/fd5caeec976b16b76b3bd6af3aa91f7e_3.png)

And this team thing， you're gonna pick your own team it'll probably say add team if you haven't done the tutorial yet。

 and then the organization identifier in the video I suggest doing this reverse DNS notation here and just put your SUNet ID right here that's almost certain to uniquely identify you and we're doing everything in Swift UI here so it's Swift UI and Swift and we're not going to be doing these things down here at least not at the start of the quarter。

Next， and now it's going to say where you want to put it I did the assignment zero tutorial。

 so there is my repository that I cloned from GitHub so if you haven't done assignment0。

 which is watching this video tutorial you'll know exactly what I mean by that and I'm going to put it inside of this cloned repository which currently has nothing in it and this is the place I'm going to submit my assignment because your first assignment which I'm going sign on Wednesday its actually I'll make it available today you can go look at it is to replicate what I'm doing today in Wednesday and then add some stuff that shows me you understand what I'm doing。

You're going to do this and I'm going to say create。

Creates our first project here's our first project I'm going to make this much larger so we can see what's going on here I'm also going to hide some of this stuff and bring it back as we talk about it and I'm going arrange it and Xcode is huge it's got so many features I mean if you look up here at the menus look how many menus a menu I mean there's so much stuff if I went over Xcode today I wouldn't even finish we'd be still be going Wednesday so you're gonna to learn most of what you' learn from Xcode by discovery as you start doing things you'll start learning you'll see me doing things as time goes on in here。

But I am going to cover a few things kind of the main things， let's start right along the top。

 you see the top here， it has this little like play button and then it has the name of the app right here。

But this is important this iPhone 14 Pro here， this is a simulator。

And you can choose all kinds of different devices。 there's more of them that are listed here。

 I'm going to choose， let's say iPhone 14。 and what this is asking you is what simulator do you want to run this on when you press play。

 So let's press play。 see what happens here。 This is going to launch another app Its the iPhone simulator app。

See that status line up there attaching to memorize on iPhone 14。

 So that status bar will be telling you everything Xcode is doing。 here it is。 it's launched it。

 There it is the whole hello world。 The same thing you were seeing back in Xcode and what's cool about the simulator。

 This is actually simulating the whole device。 if I swipe up from the bottom here。

 I can go to do things like settings and stuff like that。

 which is nice because you might want to run your app with certain settings on dark mode or whatever just to see how your app works or maybe your app uses mail。

 there's mail on here on the simulator， you can test that。 So I'm saying simulator is great。 however。

 if you all notice here， there's also seems to be fun right here。

 this looks like a phone saying hello world here。 And this is called the preview pane。

 this is previewing whatever is on this side。 this view right here。

 this little hello world thing and we're gonna look at all that code in a second here。

 And this not only is previewing it， it'll do it。In real time it sometimes will pause like when you go out of the app and come back So it's running down in real time So you see it says hello world。

 if I go over here to the code and change this to be hello CS 193p you can see it's actually every as I type the characters it's updating it this is really fantastic okay this is really nice and even if you make big changes over here。

 it will mostly keep up with you sometimes it'll put up a little X that says I can't understand what you're saying because you're not finished typing or whatever but it's really really an awesome system。

So we'll get to that in a second。Over here， this little button in the upper left this is the navigator and the navigator can show you your project in lots of different ways in this way right here's the leftmost tab this is the files navigator it's showing you all the files in your project now when you create a new project you get these three files over there for free this one called content view which is this code you're seeing here that we're gonna be looking at in detail today there's also this other one memorize app see that one this is your main program see where it says at time main we'll look at this code a little bit later's pretty simple code as you can see and then there's this assets thing This is where you can put assets like video files sound files icons images your app icon goes here you see the thing says app icon there you can drag it in here so that's what your assets are media assets and that's it that's all that there is in this project nothing else。

This navigator can also show you things like your source repository。

Here's the repository that's overr in GitHub and I can see the remotes in there。Because my main。

 it can also search。One thing about search you see it says find you can also do find and replace up here it's kind of hidden but if you click on find you can change it to be replaced show me all the errors。

 if I do bugging it'll show me my break pointss I can also see all my past builds that I've made all the errors that came out whatever this is the navigator it's how you navigate now what's interesting is you think well' it's pretty important to have this open as I'm navigating you almost never have that open right and the reason for that is that along the top there's a couple of cool things this is tabs。

Anything you open you can get back to really quickly with tab and these tabs will grow as I open more and more files and even more kind of access is this line。

 this is the path bar this is showing you a path to where your cursor is see the blue line right here that's actually showing me the full path to it。

I'm in my memorized project， I'm in a memorized folder that's where all these files are stored I'm in this content view。

 this little icon means it's a swift file and I'm in the body bar right here。

 which in fact is where I am and not only does this show you it you can use it to jump around I want to go over to the memorize app going to go back to the content view etc so this is what you're going to use to navigate around for your files not that navigator thing but you know the navigator will also pop out when you have an error for example you're running your program array index out of bounds it's going to pop up there and show you oh you've got a problem。

Then on the right， you saw those one appear over here， this is the inspector。

And this actually inspects or kind of gives you a UI to edit whatever is selected over here Now you see this thing when I type CS190 P。

 it just immediately update， that's because it's in run mode see this little live thing down here you can also put it into select mode and when you're in select mode when you click on something in your code。

 it'll select it see how to put a little blue box around it there and it also at the same time will over here if you look in the right inspectors。

 this one it'll show you all the things you can edit about it like its color this is like an editor for or inspector now why do we have this well a couple of reasons one。

 I'm going to teach you how to do it all over here okay here're gonna be programmers you can be working over here so you might say why would I ever want to set the color here when I can learn a line of code which is what this is to do it。

Well the answer is you might not be a programmer， maybe you've handed this off to your UI designers and they want to play around a little bit with the alignment of things or whatever or the colors or you've sent it to your localizers people who are localizing it to other languages and they want to reset this thing right here and they're not really programmers so maybe they would and mu this around and send it back to you because watch what happens when I change over here。

 see color accent color， let's pick orange， it changed the code。

 these things are linked this is always showing what's happening here and this is Els editing what's selected there。

Now again， you guys are programmers probably not going to have that open very much。

 this is how you're going to be looking at Xcode the vast majority of the time here。

There's another thing at the bottom pull it up so down here we actually have two things one is your debugger that's on the left over here and you're not going to need to do much debugging in this class in the first few weeks maybe you do print statements to the console though and that's right here you got debugger and your console one thing is cool is in your code if you put a print statement to print out to the console this will automatically fly up when when it sees output coming up there。

So that's it that's the grand tour of the basic parts I'll show you one other thing which is hiding this you see this preview on the right if you don't want it。

 if you click here， you can say show editor only and it will just only show the editor or to get it back you pick canvas that's what they call this thing I don't know why they don't say preview window but canvas。

All right， I don't think I have anything else to show you about Xcode。

 so time to start looking this code。The first code I'm gonna look at is actually down here See it says content view previews。

 This thing that we're building here is called a content view。

 That's just a generic name content view。 It just made that up because it didn't know we were building a card game so it didn't know what to call this freestruct that it gave us the hello world thing it could have just as easily been called hello world view or something like that。

 but this content view under our previews is the thing that glues that to this。

 What is this preview showing look it's showing the content view。 This thing up here。

 This usually don't have to mess around with， I'm going show you when you would need to but I'm actually going to move it down out of the way So it's not bothering us we don't need to look at it has nothing to do with what were actually working on and you can do that too if you want that preview thing is almost always just going to say make one of these and put it up here。

All right， let's start going through this line by line of code， let's start at the top there。

 import Swift UI that's like an include or an import that you would see in other languages we don't always import SwiftUI believe it or not because we're going to separate out basically our UI from our backend from the logic like our game the thing that decides whether two cards are a match and how many points to give is not going to be a UI thing it's going to be separate out into this old world。

 those files will not import Swift UI。They'll import something probably called foundation。

 which is like arrays and dictionaries and stuff like that， but it's not going to import Swift UI。

But on flip side， everything that's doing UI has to import swiftift UI There are other things that we might import like when we do the object or database。

 we're going to import core data core data is the module that has all of the object orientation database you'll see that later in the quarter。

Now let's look at the guts of what makes our little low world thing happen over here。

 You can see the first word isstruct。Struck is just a key word in Swif that means this is a structure Now all languages pretty much havestructs Now in C。

structs are just are little things that hold variables in Swift UIstructs are super important they are the heart of everything we do in Swift UI okay。

 pretty much everything is astruct。Andstructs can have variables。

 of course in there but they can also have functions and when I say that they have variables and functions。

 some of you are immediately thinking oh， it's like a class right a class and object or program that's got variables and functions but it is most certainly not object or programming it is not a class it is just astruct that has variables and functions in it so there's no inheritance going on here right there's not it's not object or programming now there is a keyword called class that is a class that is an object or thing。

 we're barely going to use that keyword in this whole quarter。Second thing there。

 content view that is just the name of this type okay we're declaring a type here astruct type and it's called content view and again it just gets got picked for us because it doesn't know what we're doing so it's like this is the content of your app so I'll call it content view we're going to rename that pretty soon like next week or the week after to be called something like memorized game view because that's really what it's going to be eventually。

This right here， Co view might be the most important thing you're going to see today。

 and this is your entree into understanding this functional programming thing I'm talking about。

 by the way， sometimes you'll hear this called protocol oriented programming as well。

So what does this mean now， I'm going to introduce a little thing I'm going to do。

To help you know what's really important， which is when I am going to talk about something that's really important。

 I'm going to write it on the board here and you can take a photo of this later or whatever or just helps you understand this is important and so I'm going to write this one now this is the first one and I'm going to quotes here and say behaves like a something okay this is fundamental to the functional programming and that's what this colon space view means it means this struct called content view behaves like a view。

Now I'm emphasizing this so much because behaviors means behavior functionality。

 this is functional programming all right we're really going to focus on the functionality。

 the behavior not on the data people ask me what's the difference between functional programming and object orient programming objects。

😡，Oriented program really it roots and it's evolved some but its roots are data encapsulation you've probably heard that phrase right functional program would never use the word data in its description of what it does it's more like behavior encapsulation if anything but it's much more than that but it's all about behavior how do things behave how dostructs behave so thisstruct behaves like a view well what is a view a view is just a rectangular area on screen that draws something and can get events just exactly what you would think a view is and so this content view behaves like a view。

If I behave like a view， what do I have to do or why why is that a good thing or whatever Well。

 any time you behave like something you have two sides of a coin right a double edged sword if you want to think about it one side of the sword is you have a responsibility if you're going to behave like a view youve got to do the things a view does and so there's going to be some thing you have to do or multiple things you have to do to satisfy this claim that you want to behave like your view for view incredibly there's only one thing you have to do which is to have this variable in yourstruct。

It's called body， our body and its type is some view and we're going to talk exactly what that means in a second and the other side of the double edge sword is if you satisfy this requirement and do this thing。

 you get all the things un view knows how to do and in Swift UI it's massive， hundreds of functions。

 all kinds of functionality built into view， you just instantly get it all。

It's a very leveraged kind of way of programming because you only have to do this one little variable and then all of a sudden you get this massive amount of functionality like setting your color and all these other things that you're going to see us do in the next few weeks in fact we're going to spend the whole quarter most of what we're going be doing is exploring what a view can do and we won't even get halfway through it that's how much stuff of you can do swift you eyes all about views as you can imagine rectangular areas on screen that are drawing and taking events。

Let's take a look at that var body and try to understand what's happening with this var body Now it's kind of weird you're probably okay with what I've selected here Var is just a keyword means it's a variable body is its name right to the name of the variable some view is its type let me show you what what another variable might look like and you'll probably be a little more comfortable how about var I is an int。

😡，Far S is a string。This is the syntax for variables keyword the name of the thing colon the type now don't get confused this is a different thing。

 this is behaves like a this is is of this type those did happen to use the same kind of colon thing which you know the reason they chose that is。

If this S is of type string， it behaves like a string。 Okay， so it's but don't。

 but it's not the same thing。 This is not。This string is a struct。So S is a struct it's a string。

 int is a struct you see what I'm saying view is not a struct。

 view is a thing you can behave like okay called a protocol。So I can confused there。

 but that's what and I can have as many of those bars as I want。But this far down here。

 a little different for one day， it's got this。This is little curly brace thing and so I'm gonna to write on the board again here's something important so this is computed property a computed property。

 the reason it's called that is because this var body these things we call them properties you call them variables you'll sometimes here we call them bars because of that keyword bar but they're properties in Sw because it's a property of thisstruct that it has that variable attached to it。

 so that's what property means computed means this blue part which is that the value of this variable it's not stored somewhere it's computed every time someone asks or the value of body it runs this code。

And that's the value。This code is getting run over and over。

 Every single time someone asks for this body。 It's computed。

 It's read only because it's calculated here， but it's still a var because there might be variables in here that are making it return a different thing every time you call it。

 This is code。 It's gonna run。 And so it might change。 So that's why this is variable。

 but it's like a read only variable because you can only compute the value。 Comp properties。

 you're gonna see them all over the place and Sw you are These up here are not compute properties I guess youd call them normal properties。

 Okay stored properties。 There'll be storage in that struct for those things。

How about this some view okay， that is an awfully weird type that's not like string or int or something it's got some and then this weird thing view which is a behaves like thing。

Well， can anyone guess what that means， some view？That type。No guess there is okay。

 so good's good thing I'm explaining it， it means that the type of this variable has to be any struct in the world as long as it behaves like a be。

In other words， some few。Now which view okay， because there's thousands of views in the world。

 which one is it， well， very simple， this sum， tell Swift， execute this code， see what it returns。

 use that。So that's what some view means， it means run this code， this is a computed property。

 only works with computed properties like this， it means look in there， see what it returns and。

That's it that's the you to use so it's doing two things at once once it's figuring this out for you and two it's making sure that the thing there returns is some you it will give you a big compiler error if it doesn't。

I want to try and understand why it is that if you want to behave like a view。

 your only job is to implement something like that， this bar body some view。

 how does that make sense because basically what it's saying is if you want to behave like a view。

 you have to variable that returns some other view。What？😮。



![](img/fd5caeec976b16b76b3bd6af3aa91f7e_5.png)

Let's use this beautiful Lego that my son built for us today to understand what is going on here。

 So I have a Lego thing here it's this set right here。It's called emergency vehicles， headquarters。

 Okay， it's part of the city， Lego City things， it's just be your city and it's got some parts here。

 it's got the headquarters building here。 It's got a nice fire fighting helicopter and an ambulance and a police car right here and it even comes。

 this is funny comes with granny here and granny's been doing some barbecuing at the barbecue but it's under a tree and she's caught a tree on fire see that fire't coming out the top and this helicopter firefighting Come along in。

Shoots water cannon at it， so I don't know who designs these things a Lego anyway that's what we got so we got this Lego thing right here。

We're going to draw an analogy between Lego and the views。 Now， the first thing is easy。

 and I'm going to pull a wall off of this building right here。And this you'll understand easily。

 right， everyone's played with Lego， I assume they're these little bricks right。

 little white bricks and of course， if you stack the bricks on top of each other to build things and some might even say that it's a。

Vertical stack of things okay so you do that and now you can definitely see that part of the Lego analogy right is that if you think of Legos as views then I'm going to be combining together maybe vertically like a V stack there Okay so that's the kind of the simple part of it。

 but there's a little more of a complex way of looking at it which I want you to see the Lego analogy this way and then it'll all make sense why we have this bar body let's consider our helicopter right here。

What we're going to do， we're going to take the rotor off right here。

 so here's my helicopter's rotor。I'm going to say that this is a Lego。

We know that those little bricks are Legos， but now I'm going to say this is a Lego。

 I put it together out of smaller pieces。 Okay but once I put it together。

 now I have a rotor Lego complex Lego。 same thing here made with the landing gear。 Take that off。

 Here's the landing gear of my helicopter。 This is a landing gear Lego now that I've put all these pieces together。

 and the same thing here， This is the airframe Lego helicopter airframe。

 maybe it's made up of other things。 tail cockpit Lego。

 whatever So I'm going basically build my Legos here out of these more complex Legos that I built。

 And in fact， maybe I'll even vs stacked them。 look at this。 I'm to put that there。

 I'm gonna put this on top of here。 I just stacked three Legos。

 a rotor Lego an airframe Lego and a landing gear Lego to make another Lego。

What if this were my content view you see so do you see why defining myself as a view having a variable that returns some other view makes sense because if I'm building a helicopter view。

 I'm going to vSt three other ones that I probably built with other ones so it's infinite recursion here。

 I can build arbitrarily complex things， not just my helicopter but my whole headquarters。

 I can build my whole Lego city out of things by just always having my view be built out of other views。

😡。

![](img/fd5caeec976b16b76b3bd6af3aa91f7e_7.png)

And so inside here we're obviously mostly going have B stacks and H stacks and grids and things that combine other views to make more complex things so that's our Lego analogy there let's dive in and look at this ones this free one we got that does this and how it does what it does it's pretty obvious I'm going to write a couple of more things up here creating instances ofstructs named parameter and also parameter default so I'm going to do all three of these here at once First thing creating instances ofstructs how do we create a struct not just a view but any struct super simple here's an example of creating a struct an image struct here's an example of creating a struct a text struct both of thosestructs behave like a view。

They're also kind of like Lego bricks， they're in the Swift UI library， they're like building blocks。

 the base of the most simple kind of views that you can have。

And the way you create a struct is you just put its name so like arts is called content view so if we were creating a content view we would say content view open parentheses。

 any arguments you need to pass to create that struct and close parentheses really。

 really straightforward what's tricky though， what's probably new to almost all of you is this little beauty right here okay。

 system name。So here's image， image is just astruct， behaves like a view。And here's its argument。

 G system name。 It's naming that parameter。 It's named。 Now， not all parameters have name。

 This one has no name。But you don't need a name here because the text view。

 obviously just give me the text， I'll show it， but here this could be system name。

 maybe it could be the word named。If you say image named and then a string。

 then it goes over here and looks in that assets place I was showing you before。

 and it tries to find an image that you brought into your assets named that string you see。😡。

I can have the same construction here and just have a different name for this parameter。

callled named instead of system name and now it interprets it differently and it also means that you can have lots of different combinations of arguments to createstructs right and we're going to show you later in the quarter how you you know do that basically how you make it so that onestruct can be created with all different kinds of initializing arguments。

Very common， almost allstructs have more than one way to implement them if they have any complexity at all。

 even text has some other ways to initialize it where you can give it a number， for example。

 until it to use a format or to format it。That's how you create astruct， okay。

 so that's the creating instances ofstructs。The third thing is parameter defaults and what parameter default is saying is there are other arguments that you could specify here。

 but you'll take the default value so you don't have to put it So you're often going to see that sos let me show you that by talking a little bit。

About beeft。Because Eagle eyed students are saying， well， what about this？

That's a struct right its a struct that behaves like a view in fact。

 so VSt is no different than any other view the only thing about VStack is that it takes other Legos and stacks them on top of each other that's how we're getting this so if you look at this UI there are three views here。

 there's the text view there's the image view and there's the VStack that contains both of them。

But why does VSack not have open parenthees something well actually it could， it could be。

 for example， VSAC has alignment as an argument dot leading look what happened。

 it made the things line up on the leading edge there or I could do。Spaccing。

20 something like that put more space between the things so it does have arguments see open parentheses。

 closed parentheses arguments in there now you might be thinking， oh， okay。

 so what you're saying is if I don't have any arguments， then I don't have to do anything not true。

If you have no arguments， you normally have to do this and this is legal too not the compiler is running here。

 it's not complaining， this is all everything I've typed perfectly legal。

But what the heck does this mean？What is going on with that right there Well。

 I'm going to go back to my Lego here。I'm actually going to open the box。

How many people here have not built a legacy thing like this on pretty much everyone， right？

We do look how it comes。Comes in bag and see on that， can you see on there it says one。

 And if I dig in hear more， there's some instructions。And then the instructions also have a number。

 so this is number two， find bag number two here it is。this is the helicopter。 I get a bag here two。

 here's my instructions for two how to do it VStack is kind of like these two things put together right it wants a bag of Lego。

 which is what I've got selected right here and then it provides the instructions how to stack them in vStack's case on top of each other So we're going talk about this bag of Lego that is the thing in curly braces。

This thing in curly braces is actually a function。Embbedded functions like this are everywhere in Swift UI。

 It might seem weird now get used to it because all code you right is going to have embedded functions everywhere。

 Guess why。Functional programming functions are passed as arguments to other things all the time it's just the fundamental part of functional programming and that's what's going on here。

 This function returns a view it returns something that behaves like a view in particular。

 a bag of Lego。So the bag of Lego is a view now unfortunately we can't just。

Put it on our thing okay we have to open it up and arrange it so bag of Lego views need to be passed to something like a v stackack or a grid or something that can open the bag up and put it in there。

 but it's still bag of Lego is still a view It still gets passed around like a view。

It's also kind of got weird syntax for a function because it's like this is just two views。

 image and text kind of listed， it's kind of list right and so there's a postpro step going on here that is taking this list of views packaging it up into something called a tuple view to U PL viewple is not the word two tuupple view just means a list of views could be any number not just two and so it's making a twople view so this is actually a function that returns a twople view with these two things in it the image and the text that's what's going on here that's reality tuupple view is a bagelleggo view never makes sense on its own it always wants to be passed as an argument but it doesn't look like this is being passed as an argument to the Vtax but it is because really this looks like this content。

Colon。And that。That's really what's happening here the whole thing where we didn't say content and we didn't have the open brands series closed parenthees that's all just to make the code look simpler and nicer and cleaner。

 but this is really what's happening VStack is a view that's taking this one argument which is a function that returns a bag a Lego view that it can arrange。

Let that sink in， everybody got that what's going on there。Now people。

 other people who would teach you so if you why would probably not tell you any of this。

 they would just say， oh， when you have VStAC just put curly brace and a list of views。

 that to it and they wouldn't tell you that that's a function and that there's a twople view going on and all that and so it's probably fine if you're like I don't really get that。

You can look at it as just my VStack get to curly brace list of views and it'll work fine for probably the whole quarter or most of the quarter。

Inside this backloglu of view， we can't do much， we can only really list views。

 we can have conditionals if thens and we can declare local variables that's it we can't do any math。

 we can't do any other stuff we just do those three things and the thing that turns this list into a tuupple view is called I'm going to write this up here a view builder。

So when you hear viewBuilder， they're talking about the thing that turns that list of views into a twoal view。

All right， we've kind of mostly understood what's going on with building。

 I'm going to leave that content there by the way you would never do that in your actual code。

 which is gross right， you would go the nice cleaner word。

 but I'm going to leave it up there for a while， we'll switch it back in a minute。

 but I just because I really want to sink in what's going on there。

So let's keep talking about things here， let's talk about these， see these two lines of code。

 image scale and foreground color， what are those and padding too， what are these things。

 we know this is creating astruct， this is creating astruct， what are these things doing？

Those are just functions。 This is what it looks like to call a function in Swt。

 very similar like Java， right， call a function。Unfortunately。

 none of them have an argument like system name， but I'm stuck with what they created for me here。

 but you're gonna to see a lot of functions do have these parameter names they can it's optional if they want them or not now these functions aren't really special in any kind of fundamental way but it's important to know what they do we call this kind of function of view modifier because what it does is you call it on a view right image is a struct that behaves like a view so it can be called these functions can be called on it and these functions can be called on any struct behaves like a view it's part of what you get when you say yeah。

 I behave like a view you do what you're required to do the bar body now all of a sudden people can call these functions on you and there's hundreds of them。

These things right here， they return of you。😡，You send them to a view。

 it modifies the view in some way and then it returns you a new modified view When we look at this v stack。

 we thought there was an image in there and a text， but not quite。There's a text。

 but there's an image that has had its scale modified to be large and its color changed to orange that's really this view so there's two views in here。

 this one and this one。Because this one modified it and returned to view。

 and then we modified that view。And what's great about all views doing all these functions is that we can chain these view modifiers。

 modify view， then modify it again， then keep modifying it over and over。Okay。

 so that's what's going on。These things， image scale and foreground color， I can change them。

 of course， like let's change that image scale to be small。

Look how small that got right there see that and we already saw that we could change our color in the editor。

 but we can also change it in code notice X code helps you a lot if I type dot and start to type look it shows me right here oh I want my green。

And it goes to green。Another thing that's important to understand and remember is that VSt。Is a view。

So you can send these things to it and that's what that padding is at the bottom now you're not really noticing it。

 but there's padding around this since it's centered you can't see it what happens if I took this padding and put it around the text okay so I'm going to cut over there paste。

See， that thing kind of moved out of the way because this text got a padding around it。

 all views do that。But here's the real power of it， what if I sent to vStack。 font。

 which is a view modifier and I we'll go， these are all the different fonts we can do。

 let's say a large title。This got large and this got large。

Everything in the VStack got that modifier so V stacks and H stacks and grids and other things that take bags of Lego when you do things on them that really don't make sense to do to the whole thing。

 they pass it off to the things inside not only things like font， but also watch this。

 let's take our foreground color。Put it out here。And change it， see， they change both green。

Both orange I modifying everything inside so the scoping of these view modifiers matters now what about image scale that seems like it's an image only thing right doesn't make sense to do a you know on a text but if I take this out here put it down here。

Still works， they still got small。Now， that's just because image scale was applied to the text and the text ignored it because it's not an image。

So that provides a lot of flexibility to be able to put these things on the outside and have them only apply to the things on the inside that really care。

Hopefully this helps you understand really all there is to know about building views。

 we can create the views right here and here we can modify them with these modifiers。

 we can use the VStacks and list views to combine things and we return it all from our var body and that's what makes us into a helicopter view or whatever。

And we're just going to do this more and more building bigger and bigger things as we build our app。

So let's start building our app there what do we need to build that app well we need cards okay we got to have those cards here's a card right here obviously to build a card I'm gonna to need a rectangle so let's get a rectangle on screen I'm just going go in here get rid of some of this stuff we don't need a globe we really we do on some text actually but we just want the text to like have an emoji on it or something one thing you're going to find out in this class。

We love emoji in this class okay we are gonna to use so much emoji in this class In fact。

 the second app we're going to build is called emoji art all right so emoji is our favorite thing and we're gonna just but you can see why look at all these cute emoji let's go with a ghost put a ghost in there by the way I just went up here to this edit menu all Mac apps usually in the edit menu the last one is this emoji and symbols you can go pick things so I put that there I don't really need this padding around here I am going put the padding back on the outside of my body usually the top level thing in your app the content view or whatever you want padding around the outside in case it starts getting big you want to not smash into the edges right the edges of your device so we usually need the padding。

Around the outside I'm going to do this font large title I'm going to put this just on the text。

 no reason to apply that to everything and now I'm going to put my rectangle in here let's just type it in we're going to use rectangle there you go I got a rectangle so rectangle is of course astruct that behaves like a view It is also something that behaves like a shape。

So shape is another thing in switch UI and rectangle is one， another shape is circle。

 there's also rounded rectangle， which is kind of nice for a card rounded rectangle now rounded rectangle needs an argument。

For example， it's corner radius 12 points or so， and this has created this little bit rounded rectangle so we definitely need that for our card。

 but our card， the emoji is on the front， it's not down below like this so we need to put it on the front and that's really easy to do we're just going to change our V stack into a Z stack。

Z is this direction。Right towards the user is Z。 V was up and down H， by the way， is side to side。

 So like V。 So look， right little guy， you appeared on the front。

 but that doesn't actually look like a card either。 The card is white。 The back of it。

 It might be orange， but the front is white with it on there。 So we actually want that to be white。

 but I can't really just say something like foreground color。That white。

That's not really doing it either because now I can't see the card right It just blends in the background。

 So what I'm going to do here is I'm going to use a shape thing called stroke border。

Dbe border takes an argument here line width， I'll do 10 to start so you can see that's making a thick border so now this looks a little more like our card ours don't really have a border but we kind of need it because our background might be white so they to be careful there。

And so this is looking good notice I also typed this right here okay as opposed to right here and both of those are okay。

 I tend to like to put them here on the next line as opposed to on the same line like this unless this is the only modifier and it's very tightly coupled to what I'm doing so I might be okay with the font on the text one like that。

 it's a style programming style thing。By the way the stroke border can have lots of other arguments。

 for example， it could have style， so I'm just showing this to show the amount of things that we could have。

 we could make that thing be dashed， dashed line， maybe that's 10， then 10 on and then two off。

Something like that。I only did this to show that complicated things are possible now i'm not going to ask you to do these kind of complicated things。

 it takes a while to learn all these things so we'll be doing mostly simple straightforward things like just line width here and we don't need line with 10 maybe line with two is enough yeah that's thick enough to kind of give us an idea of the card。

Now we might think， okay， good， our card looks good。

 but actually this card does not look good and I'm going to show you why right here in our preview。

 you see this little button down here， variance。Click on that。

And you can see that there's color scheme variant， orientation variance， and dynamic type variance。

 so these are the three major ways that devices differ。This one is dark mode and light mode。

 How many people have done dark mode on their phones。

So everybody knows that so you want to be able to look at your UI both in dark mode and light mode make sure it looks good in both Or is landscape and portraits side by side so you can see what they look like so let's look at the dark mode light mode here it is there they are side by side our cards look terrible in dark mode okay they really want to have a white background in dark mode too so how can we do that unfortunately there's no way to both stroke and fill a shape。

You can only either stroke it or fill it， by the way， get this。

ThereSo how are we going to do this then， we need a kind of a white background。 Well。

 we're just going to create another rectangle behind it。 Okay。

 so I'm going to go here and copy and paste this。Creating a rectangle and this one's going to be foreground color white。

 I could also say dot fill white， that's another way of saying this and now we have it behind。

And we got a color， let's get rid of our image scale in there。We can go back to live mode。

 for example。And we could also do with landscape， now let's do it with landscape just why we're here。

 let's go over here to our orientation variant。You can see in landscape it's kind of hard to see。

 We could zoom in there a little， but it looks okay。

 looks okay there So mostly those variant views are just to kind of get an idea if it looks right When you actually come to build your app。

 you're going to switch this whole thing into dark mode and you do that with this switch。

Color scheme， dark mode and now my live view is in dark mode so I'm gonna to make sure this looks how I want I'm basically really debugging it。

 So the variant view is just to get you an idea and then this view is to really pick what you want Okay whether it's orientation and dynamic type by the way is you want your app to look good if the user is like me getting old and needs the font to be really big to be able to see there's a slider in settings on your phone that lets you set that and you want your app to look good so the size variance will show your app looking like 10 different font size。

So we got a card。 This looks like a card。 It's not very good。 It's got a tiny little。

Thing and it's really gigantic， but before we fix any of that。

 let's make multiple cards So how are we're going to do that Well。

 of course we could copy and paste maybe we'll just make an H stack。And inside this H stack。

 we'll put four cards， so I'm just going to cut and then go paste， paste， paste， paste。

Put these in here。 Look at that the four cards right This is extremely bad code right here。

 you would never copy。 In fact， anytime you find yourself copying and pasting。

 you're almost really doing it wrong， right any time I do that copy with code。

 I always stop now now what am I really gonna to do when it's time to really do this right Okay because copying and paste is just so error prone obviously not good So how do we get out of it the other thing too is look how long this v body is。

 how many lines of code is in I want you to have a goal。Certainly in this class。

 but also in your life as a Swift drive programmer。

 never have a function or a computed variable like this longer than 20 lines of code。

12 preferably I'm going to endeavor when we go through this to never have one with more than 12 lines of code just to show you it can be done and there are tools in terms of the syntax of the language to be able to do that and I'm going show you one of them right now and what this one is is I'm going to create a new view just like I told you I had the rotor view It's like I'm going to create my rotor view。

 which is a card view so how do we create a new view。 really easy， I'm gonna scroll down here。

 This is my content view right here。 So I'm just right below my content view I'm going to saystruct card view。

 It behaves like a view。 what happens when I behave like view， I got to do var body。

 which is some view and it's a computed property So inside here I have to put anything Well I'm going put one of these things。

 of course D stack cut that out of here paste it in here。Well， I've just made a new view。

 a card view that represents one of these cards。 and now no I can go back and get rid of all this yucky code。

 just delete it all。 and instead I can say。Card view。

Right because we know that how we create astruct， the name of the type。

 and then the arguments our card needs no arguments to be created and if I want multiple of them here I could copy and paste。

And of course I'm going to show you how to do multiple of those without copying and paste basically a four loop right the for loop。

 by the way， in Swift is essentially a bag of Lego right because it's going to create something multiple times we're not going to do that right now though。

So that's good that look this code looks really good both of these bar bodies are really small and really clear what's going on and I just did that H stack on the fly I hope everyone was comfortable with that right it's just horizontally stacking the cards across this way now we eventually want it to be a grid and we'll get to that on Wednesday make this into a grid but for now we're just going make this be horizontal。

And this is essentially our Lego analogy fulfilled。

 we created a rotor and then we made four of them actually。

 but we fulfilled our kind of analogy of building another view out of other things and then building something out of that right so we're kind of going down the road of our analogy。

Now let's see what time we got， Yeah I think we have time to do one last thing。

 which is our card view has no arguments， but I can give it an argument like what about this card view being face up or face down That'd be cool if I could have the card view have an argument。

 whether it's face up or face down wouldn't that be cool No problem just going on here I'm gonna say。

And my struct var is face up is a type bull。 Okay， bull is a struct。 that's built into swift。

 It's true or false are its only values。 I've created that。 And as soon as I do that。

 I get an error up there。 missing argument for parameter is space up。 Well。

 if you have a var like this in your struct。 it has to have a value。 Okay。

 this is something to understand right off the bat。 allstructs， every var has to have a value。 Now。

 this var has a value。 It's computed。This var has no value。Okay。

 so that's why the creation of it up there is saying， I need to give that thing a value yeah。Oh。

 you're like a shill in the audience because I'm going to show you exactly how to do that。

 I could say barar face up equals false。Now， this is not required。 you see。

 because I gave it a default value。 This is just a default， though。

 because I can still go up here to my car view and say。Is face up is true。

And change that changes it so this is how we do these arguments to the creation ofstructs and also where that keyword comes from member like system name to image。

 this is is face up。It's really really simple now now that we have is face up how could we use it inside of our card view to draw our card face down well I told you that the bag of Lego okay this thing right here is allowed to have conditionals like if then well let's just do it if it is face up then we want what we got right here that looks like a face up card else。

What does the back of the card look like， That's this thing， It's just a big rectangle。

 Let's put that in there。 that's this same rounded rectangle right here。But instead of being white。

 it's whatever color this thing wants to be so I'm actually I'm going to specify the color and when I don't specify the color on the card view。

 that orange up there actually percoates all the way down into the card views。You see。

 when I made this H stack before and color orange， it made it the default for everything inside the H stackac。

 including all the way down into the card view， that's why the card views。

 their backs are orange and also why they're lying around the outside because the card view doesn't specify what the background。

Is and so it's getting the color from above。That makes sense。

We got to stop because it time's up what we're going to do next time is we're going keep going on all this we're going to add some more bars in here we're going to do some more stuff with this face up this or not and then we'll eventually move this to being a grid instead of just being this way across okay that's what we're going to do on Wednesday and then next week really importantly I'm not here next Monday。

 no lecture next Monday okay so' on Wednesday we're gonna to pick up with that thing I was telling you about the back end and the front end are separated so we'll start preparing ourselves to have game logic over there for playing our game and that'll be in a separate space and then on the Monday after that we'll hook the two up we'll have our game playing。



![](img/fd5caeec976b16b76b3bd6af3aa91f7e_9.png)