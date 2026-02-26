# 023：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p23 23 CS169 23.zh_en -BV1UsB7YPEMj_p23-

All right， all right， so both。the microquiz should have closed now， and I'm going to before we start。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_1.png)

Let me reopen the eyecl wrap。 So today's topic is going to be。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_3.png)

Mostly about JavaScript， the dom， hopefully things that you've had a little bit of a chance to play around with in some of your applications。

 but if not we're going to talk about。没没有没有。We're going to talk more about JavaScript。

What the language is like， how you can use it， and then we're going to continue on with some of that on Tuesday。

Tuesday will be。Well， at the end of Tuesday， I start to wrap up the class a little bit。

 but also talk continue to talk about JavaScript， some web accessibility stuff Tuesday's lecture will be useful for the optional homework assignment that will be out on the weekend。

But yeah， so before we get started with that， there were a few things that I wanted to point out came from office hour question。

 Piazza questions， things that Ts have seen that will be useful。 hopefully。

 for working on projects as a team， the first particularly useful thing a couple people have asked about。

Well stuff on Heroku having all team members access and shared applications。

 So you should all be on the same Github repository。 Unfortunately。

 this doesn't sync automatically to。Let's see， what can I use。I can use any of these applications。

 So Heroku access doesn't sync automatically with Github， but。

When you're on Heroku you have the ability to add collaborators to an application。

 so anyone who is on that Heroku list is able to push， deploy。

 access the application on Heroku as well， most of the stuff that is on。

 I guess pretty much all the stuff that is on the Heroku webpage can also be done through Heroku's command line tools。

 so whichever you're more comfortable with。You can choose to use。Personally， once you get used to it。

 the command line tools are really easy， there's a couple commands that you need。

 which most of that is Git pushush Heroku master， but if you want to or if you have a need。

 you can use the website to deploy from GitHub。Hopefully you have no need to。

 but I have deployed apps from my phone this way when things go wrong。And so that's always there。

 And then anything else that you might need to。Work on environment variables， email settings。

 those kinds of things are also on the Heroku website。

The main thing there is make sure all your team members have the ability to push。

You can choose to create multiple Heroku apps if you'd like。

 you get a decent amount of just free dino hours per month。

 so you can each have your own copy if you want to test out a different pull request or something like that。

 feel free to make as many Heroku apps as you want。

 but ideally your main app everyone in your group should have access to So that is the Heroku website。

The other things that I added here， let's see the Heroku command line tool。 So let's go over here。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_5.png)

So。And let's get。I click out of the way。Like all good command line tools， when you type Peroku。

 it has some help and some command output。This is especially useful just in terms of learning what's available and the things that Heroku can do。

嗯。The important thing is， if you were not the one to set up Heroku。

 the first thing you would do is probably Heroku log in to make sure that your credentials are stored locally。

 But what you can do with the Heroku app or the Heroku command line client is。呃。

There's a couple things that are useful。 So if you do Heroku apps。

 it just lists all the apps that you have access to。 So you can see that like。

 I have access to some of the course ones and a bunch of stuff from testing and whatnot。

 But the really useful thing is。

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_7.png)

When you're working with multiple apps， if you do get remote dash V， you can see the names。

 Heroku has the ability to。Let's see。 I this gonna have log。 You this lot of logs。

 So Heroku logs is a useful command to view Web logs。 You can tail to watch them live。

 and then you can specify either dash a for the name of the application。So。

That is actually not the name。It's this name。And dash a is one way to get web logs or to specify the application。

 The other way that you can do， which is really useful is dash R is your git remote。

 So this could be dash R Heroku dash R staging。 if it's a staging remote。

 So if you have multiple heroroku apps， the command line tool gives you the ability to switch between them and those kinds of things。

😊，You also have the ability to do something。Like this。Heroku run。Oh， it is now P。 okay。

 they read it Oh， no，What。Oh， fine。 You want me to。Well， this is a problem with Li demos。no。

Where did。What。There we go。So assuming this connects one of the useful things you can do on Heroku is run arbitrary commands。

 if you run bash or if you prefer another shell， you get access to just a standard console that you can mess around with your application。

 ideally with Heroku， you shouldn't need to log into your server too much and mess with things。

 But if you are debugging something if you're。Try to understand how something's worked。

 what's on there， you have the ability to do that。As well， so that is。That is an option。

 Heroku run any command。A couple people have been。I mean， oh。But。

A couple of people in doing things with the database。

 Heroku PsQL gives you a Postgres console that you can use to run SQL queries against if you're trying to debug something。

 understand what's there。That can be a helpful tool， although in general。

 you should not have a direct need。2。Access the database directly。

 But Heroku gives you all these tools so that if you want to， you can choose to do that。

 The other two things that are useful。So Heroku has a command called Heroku local， which let's see。

Let me switch。 Let me kill this first so that I can actually start up an application。

 So Heroku local will use the setup and the command in your pro to run the application locally。

 So if you have。A setup where there's a particularly long command。 you can use that。

 It's also useful because if you're testing something like a different web server or a production like environment。

 then you could run that locally as well and so。Kroku local is a good way to do that there is also。

A convention where。All right， there's a file in most Git reos or a lot of local projects called dot end and let's see if there's anything。

Horrendous on here。 That's probably not great to show whatever。 There's not too much on here。

 That's particularly crazy。 Well， yeah， I'll just delete that canvas token。

 so no one can access grades。I'm pretty sure it's bad anyway because it's like from five years ago。

 but I'll just make sure to delete the ones for my account。

 So the thing about dot end is useful is it's a place to put secrets in your application that。😊。

Are not in your git repo。 So if you have some stuff that's local， you can。You can store there。

 The important thing， though， if you do this is to make sure that in your gett ignore file。

 you have dot end listed so that it's not committed to the repository。

 but dot end is great because like the rest of rails convention over configuration。

 dot end says these are the key value pairs that are environment variables that should be in my application。

 you can use them to override behavior easily。 And so Heroku local will。

Automatically load those environment variables， if you do。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_9.png)

Heroku config。There is。Let's。Do this again。So Heroku config will give you all the environment variables and there's actually a format。

Called dash S， which outputs an environment file that you could just load into your application。

 So this makes it pretty easy to。Share some stuff from Heroku loaded in and most of these keys in here are not even particularly useful since this application is not currently working。

So。Those are just a couple things that while you're working on heroroku。It can be useful to debug。

 explore the command line tools。 They are particularly useful。 They do a lot of good things。 Oh yeah。

 There's another gem called Foreman。And forman does a very similar thing to Heroku local。

 It runs an environment file。 It has a couple more complicated options。

 just in case you want to control things a little bit。More precisely。

But that is a useful gem that will also automatically set up your environment。 runs your application。

 It shows you the nice thing is， if you have multiple processes running。

 So if you need to start up a separate database locally。

 So there's a few groups that are using Postgres locally in development。

 this application that I have here does as well。😊，Forman and Heroku local can run。

 can make sure to start that up in the background automatically。 And so that is an option as well。

 But just want to make sure that people。Have a chance to play around with those things because as more and more of you work on your applications together。

 keeping things in sync can be a challenge。But there are a bunch of tools to help。

A bunch of just additional resources， one of the things that。

I think it was really helpful for just keeping up with things sort of。Mostly passive reading。

 And then with a little bit of active reading， there are a bunch of weekly email lists。

That are all run by the same group and they're organized by topics of particular interest to people in this class probably are Ruby Week and frontend focus or Ruby Week is pretty much all things Ruy related frontend focus is mostly frontend dev。

 there's Postgres， JavaScriptscript ones but one thing that was listed on the email list yesterday。

 which I thought was a pretty good guide， is。A complete setup starting from scratch on Ra 6 with modern jascript tooling the things that you might want to have that are not necessarily required。

 but can be useful tools。 So that's those well。 if you hopefully everyone has set up their apps。

 But I encourage you to take a look and say if there's things that you might want to add or experiment with as you go along developing things。

 So that's there。 I put links to the most recent issues。 if you have a commute。

 these are nice things to ski on your commute。 But otherwise。

 it's something that I usually spend like。10 to 15 minutes a week。

 just poking around and seeing what's new。 And oftentimes there's really helpful things。

 If you like databases， If you like SQL stuff， Postgres Week is really good。

 Sta code is generally things about web development developer operations。

 So you'll see things like new H TP features， SSL stuff， security related things。😊。

And so those are good useful resources。At the meat of today's topic。Javascript。

 so some big picture stuff a little bit about the language。

And then some stuff about the Dom and web browsers。 So this is Brennan Ike。

 the creator of Javascript。 It was created in 1991，1992， and。

A lot of people have to hate on JavaScript， but the thing that's here is plus if I it had to be done in 10 days or something worse than JavaScript would have happened。

 which understanding the fact that JavaScript was implemented in 10 days in the 1990s as a first specification。

诶。Is a pretty good explanation for why some things are the way they are。

And so what we're going to talk about today is。B。When we're creating interactive experiences in rails。

 what stuff should we be doing in JavaScript， so this is not serverside JavaScript。

 this is also not totally discussion on Tuesday we'll have react as a topic because it is relevant to some projects。

 it's an interesting thing react is I think a fun framework。But it is its own thing to learn as well。

 So you'll see some of that in discussion on Tuesday。 And then the other goal is， you know。

 what are sort of the minimum things that we need to provide modern web experiences for a rails app using jascript。

 And this is really key because。😊，Creating a whole new react app for every single page is quite a lot of work。

 It's a lot of overhead。 There's a ton of stuff that you can do， just natively rails。

 some really simple views， rendering a table。 All that stuff is what rails is great at。

 writing ja on your own to make highly complicated interfaces。😊。

things like react is useful when you need it， but if you don't need it， stay away from it。

 so gradecope as an application has a mix， it's probably by the total number of pages， 50。

50 things that are all react and things that are just standard rails pages。That are tables。

 grade views that are not super interactive， so they only have sprinkles of JavaScript。

Use the right tool for the job essentially。嗯。Javascript has an unnecessarily bad reputation。

 It has earned some of this reputation to be fair， but like all languages。

 it's nowhere near as bad as the haters want you to believe。 I particularly am fond of Java and Ruby。

 So this course uses two of my three favorite languages。😊。

And so I think there's a lot of good stuff here a good point to remember is that to the extent possible use JavaScript as an enhancement to your application。

 so when you have something like a button， you should be able to click that button without needing JavaScript as much as possible。

 there are of course certain experiences where the application。

 the needs are so interactive that they don't make sense without JavaScript。

 but in general try to use it as an enhancement and not a requirement。For client side jascript。

 JQury is still the de facto library that you pull in for doing things like manipulating the Dom。

 which we'll talk about。 JQury itself is a library the code that you write it from manipulating user interfaces is super imperative。

 it is when I click this thing this thing should happen， update some classes， it's not a framework。

 it doesn't give structure to your code， but it is a useful tool。

 So at the point where you write tons of jascript， you want a tool like react。

 maybe angular maybe something else to help you manage tons and tons of ja。

 but reach first for something simple and then add as you need。

 and just like we have our spec in rails。 Jasmmin is one of the better testing frameworks in jascript So we'll look at a little bit of that。

And node JS is serverside JavaScript。 It is a separate beast。 The language mechanics are the same。

 Unfortunately， the problem with JavaScript is there is no rails of JavaScript。

 There is actually a node library called sales because it's rails with an S for some reason。

 I don't really know why but it's not。It doesn't have the same sort of force that Rails does。

In like jascript doesn't in the same way。 It is a lot more of configuration than convention。

 So kind of the opposite approach， pros and cons to each。 But there's not quite the same。

The same structure that you have。 So where we're going to be focusing is enhancing client side parts of our applications。

 So things like adding UI。嗯。And we're not going to talk about today。

 but Tuesday's discussion will veer into the idea of single page applications using something like react。

 where the majority of the UI happens in one single view。And when you navigate。

 you're just replacing a bunch of jascript rather than making a full page load。

 So pivotal tracker is a mostly single page app。 Gitthub is not a single page app。

 Facebook has various bits that are single page apps。 Twitter is mostly a single page app。

 There is a simple rail Sadoku game。There are also completely standalone client site app。

 So Google Docs is one where it's not really a single page app， but it is。Well。

 a gigantic message JavaScript really， with a complicated server component for syncing and then serverside apps and node are the equivalent of what we'd be doing in rails。

 so this is where we'll be talking about today， mostly on the enhancement part。

Part of the use in understanding JavaScript is。Thinking about where it came from and there's just a bunch of interesting history here that。

 again， from time to time， pulling in computer history things。So small talk。

 crazy language in the early 80s that。Came out of Xerox park if you've heard of alan k。

Who was a fairly famous computer scientist。 He was a big proponent。

 Small talk heavily influenced both Ruby and jascript。

 So there's kind of going to be some similarities there。 Javascript inherits a lot from Lisp。

 which Ruby has as well。 So this is where we get。The functional stuff。

 so small talkg gives us objects， this idea of like everything is an object from Chaub and Ruby。

Javascript， highly functional as well when you write it correctly， at least。

 or when you take advantage of the features that are there。And then there's this other。

More esoteric language called self， which gives JavaScript its interesting use case for inheritance。

 which is not typical classes， but called prototype inheritance。

 It is just as powerful as classes but works in a way that most people don't expect it to。

 so there is。Some getting used to that。 But these are the things that kind of。

That Javascript inherits from。 So a small talk originally used in the Xerox Alto in the 80s。

 the first thing that had a graphical user interface。

 And then this language self inspired things like Newton script。

 which if you've ever seen the Apple Newton is a crazy story。 it is a device way ahead of its time。

 But the ideas of。😊，Now， we're there。 live on。 It is sort of the， the ultimate precursor to the iPad。

 So jascript came around really in the 90s when Nescape。Was just coming into its own as a browser。

 It was originally called live script to make your pages lively。

 That word lively actually comes from the small talk community。

 But there was this idea that they wanted people to write Javascript。 And in the 90s。

 Java was the thing。 So like， well， let's make a scripting language that looks like Java。

 And then we'll call it jascript。 And it will look sort of like Java， but be nothing like Java。

 So the name Javascript， a total misnomer。 But it's what we have。😊，A few years later。

 it gets standardized as ECMscript。 So this is something that if you read。

 start looking into posts about JavaScript， you'll see a lot。嗯。

The biggest deal probably in the history of JavaScript adapting web pages is。

For all the crap that Internet Explorer deserves， this one is one of the longer lasting impacts is the function XML HP request。

 This is the one thing in Java that makes it easy for ja to call out to a web server and get a response。

 and that is what basically changes the Internet forever， because。Five years later， especially。

 Google Maps is the first giant application after there's multiple browser support for this to repeatedly make AJX requests。

 which we'll talk about in a second。To build a really dynamic web application。 And then 2015。

 we get what is now known as ECmascript 6 or Es 2015。

 And now basically JavaScriptscript is in a pretty good state where every year there are new jascript versions and releases and modern browsers are pretty good at。

 So if you want some sad， sad comedy， the history of jascript versioning is， well。

 it's basically just pretty ridiculous because。You really quickly have things like E S1 and E S2 somewhere along the way。

 everyone adds all the stuff into what is going to be JavaScript version 4。 So Emascript 4。

And then people decide that it's like too much work to implement。

 And so version 4 of javascript just like doesn't exist。 It is one of those things that。

Lives in the history of just the internet。But around that same time in 2008。

 people start calling this thing harmmony， so if you ever see this word harmony。

 they are well now not so modern but at the time it was a code name for all the new modern stuff in JavaScript so if you ever look into the stuff that Chrome gives you so there's a page in Chrome called Chrome flags that control the internal behavior of Chrome。

 if you call Chrome from the command line， there is a dash dash harmony flag which controls additional features so these things that like standards try and add to kind of live on for years but throughout this debate people in the early 200s try and create ES4 and then it takes them all the way until 2015 to eventually add most of the features that they wanted back in 2005。

 2006。To ja。 And so today， jascript is much better in a much better place。

 It is changing super rapidly。 So this is the part of jascript where。😊，There is a lot of cool stuff。

 but it can be hard to keep up with。 So don't feel like you have to learn all the new stuff。

 I have a couple examples in the slides of new jascript functions styles， but。😊。

It is a really interesting language。 if you like studying programming languages。

 because it has such a crazy history， JavaScript is worth exploring。 There is。

Just so much interesting stuff there。 a few things worth mentioning in jascript now。

 And because there's a rant， which I will spare you。 But oftentimes in development。

 the jascript that you write gets what is known as transpired or compiled back down into regular jascript。

 so。😊，Microsoft has this really awesome extension to JavaScriptscript called Typescript。

 which basically adds some amount of static typing to JavaScriptscript So giving what is almost more Javalike in a way。

 but adding type safety to a very dynamic language JSX is the style of mixing HTML and JavaScript that react uses。

 it looks like writing HTML in your ja files， but all that stuff gets compiled back down into function calls。

 and。Most projects or modern web apps use a tool called Babel。

 which allows you to write all the new modern jascript features that are not yet supported in browsers and compile them back down into jascript that you can send to a web browser。

 So one of the challenges of ja is that it runs in a user's browser as the programmer。

 you have no control over what version of internet Explorr or safari or Chrome your users are using So with jascript。

 you kind of have to target the lowest common denominator in Ruby， if you want to use a new feature。

 you just upgrade the version of Ruby on your application server and you have complete control for that。

 but because you don't have control over the user' computer there is often this additional step in ja plan。

 people call it transpiing which is just a new made word for compilers it's a compiler that compiles to the same language。

I don't know why we couldn't just use the word compiler， but there you have it。

What are we going to do today， Why is this slide repeated。More about the Dom。 And then Tuesday。

 we're going to talk about accessibility。 So jascript is particularly important for our applications because it is the only language that we get to run in our web browser。

Web browserrowers on every device use JavaScript。And that is the place that you。

If we want to control the web page， that's what we have to go through JavaScript has。

A whole bunch of built in native functions that access the Dom， which well explain in a bit。

 but these are the bits and pieces of your Web application。

 That is what gives you the ability to say， can I add an onclick handler to this button。

 Can I pop up an alert when I want to and so。Javascript is the place that happens。

 so common things triggering key presses， HP requests。A。And。

Pretty much everything else within JavaScript， you can prevent pages from reloading。

 you can control the entire client side experience。 So if you develop web apps。

 there's pretty much no escaping JavaScript。And so。

You have the ability to access pretty much everything that is in the web browser and so with that the first clicker question。

 so JavaScript has this ability to access everything within its own web page when we are using JavaScript from the client side。

 which of the following things is most likely not true。And if this opens。

So we have a few options inspecting the dom and then talking about seric validation。

 So one of these is not true。All right， it's gettingd。Let's see。これな。Cool。

So a pretty good distribution of responses， take about 30 seconds and talk with a peer and see if you can come to an agreement on which of these is not true。

So far， most of the people are correct， A is definitely true， so focus on B C and D。All right。

 take another 20 or 30 seconds and put in a vote。See if we can get another 10 votes in。

Another 10 seconds。All right。Cool， so。Someone want to make the case for D。

No one want to make the case for Y D is correct。Let's go from bottom up。

 And I want to make the case for sorry， why D is not true。 Not why D is。

 so not true being the correct answer。 make the case for why we might need to do D。Allright， fine。

 so。Going from the bottom up， D is the correct answer to this one。The end。

The server doesn't need to repeat the validations performed by Javascript。 So why is this not true。

Javascript runs on the user's computer。Anything that comes from the user's computer to the server cannot be trusted。

Users on their own have the ability to modify the JavaScript that runs on your website。

 so if you perform a form validation in JavaScript。

 the only thing that's being validated is the actual stuff that's being typed in the form。

 the HTEP request that is sent to your server with the form data could have those validations in that form could have been skipped。

 they could be coming from an API request that doesn't have JavaScript form validations。

 so any security type stuff that happens on the client side。呃。

Will also need to be repeated by the server。 It is useful to have validations in both places because they give a more responsive user experience。

 but if you're going to only have validations in one place， lean for having them on the server。

 So C some validations， maybe impractical to perform on the client and must be done on the server。

 C is definitely true， the commonplace where you have serverside validations that need to be done on the server or when you have relationships between multiple models。

 So let's say I create some data。And I'm trying to。Add items to a cart by some tickets。

 There might be validations that the client side is only doing one step of that process。

 so the server validates that I maybe still have access to something or that a particular thing is still available for sale。

 the other place where validations on a server are especially useful is whenever you have a uniqueness constraint。

 It is way more important to check that on the server than the client because if you ever have multiple concurrent requests。

 So if you have a big application。And for whatever reason you might have something that's unique。

 You always want to check that on the server because when the client checks it。

 even if you made an end point to check for some value being unique。

 another user in the meantime could have created that resource as well。 So if you have unique names。

Those need to happen as serverside checks as well。 Javascript can prevent the submit button from submiting a form。

 This is true。 This is true， along with a， Java can inspect the Dom element attributes to see what the user typed。

 So jascript has access to literally everything on the user's webp page。

With like one or two exceptions。And this means that because that is access to everything。

 it can do whatever it wants， it can just delete the submit button， it can create new submit buttons。

 whatever you want your JavaScript to do， it has the ability to do so。

Javascript is a place where we add this dynamic stuff。 So the question is。How do we。

 how do we learn jascript and how do we get people to write a nice。

 clean jascript that isn't just the stuff that you see on stack overflow When people say that jascript has a bad reputation。

 it has a bad reputation because a stack overflow answers that。Sort of answer the question。

 but not in a great way。 So we'll go through the common eight step plan for learning languages。

 But as a reminder。The stuff that we've talked about before。

 so code guidelines for nice method refactoring， class structure， so all the design patterns。

All those apply。To JavaScript。One of the useful tricks is to keep。Your declarative jascript code。

 separate from your HTML T react kind of turn this turns this on its head。 So if you're using react。

The DOm markup and the JavaScript get intermingled a bit， but within Re， it kind of works。

 You have the ability to do same test driven development using Jasmine or other tools。

And if you're interested， there is a book JavaScript The Good Parts， it's now a bit out of dated。

 but it's sort of the short guide on writing clean JavaScript if you want to Google it。

 there's a picture of JavaScript the Good parts， which is like 100 pages and JavaScript。

 the definitive guide， which is like 1000 pages next to each other。

Because people like to point out that 10% of JavaScript is good。

 I think there's a lot more than that， but it is a useful resource。U。

We have not or if you have used houndciI for your ruby code。

 that's the only place where we've talked about codelins。

 but codelins are particularly useful in ja because they prevent you from making some of the really common mistakes that JavaScript has with weird。

 ambiguous types and ESS L is one prett' is one that is a nice auto formatter。

 if you've set up houndciI。 it runs jascript and code climate as well。

 will do all the same checks on your ja code as well。

 So there's a whole bunch of tools there as well。 they roughly mirror the same stuff that you've be doing in rails and Ruby so。

Again， we'll focus on types and typing first， what are the primitives。

 and then we'll get into the other bits in a second。The goal with JavaScript。

One of the really nice things is it is in every browser， so if you open a development console。

 you will have the ability to type whatever JavaScript is on that web page。  importantlyly。

 you can do this for your own application， but you can also do this for every single website you visit。

 I will frequently open up the inspector for websites to understand how they are built。

 and that is a good use of examples for how you might want to do things。So like Ruby。

 JavaScript is interpreted， it is dynamic。It means that we can just type it into a console and get a response。

 We can change types when we want and so on。 And so everything in JavaScript is an object which looks a lot like a hash。

Javascript hashes。Or objects are。Very simple key value pairs in JavaScript， the quotes are optional。

It's sort of like a ruby symbol， but not quite。 But if you have things that don't fit within the structure of a key。

 So keys can be like variable names， but you can put spaces in there。 You can put emoji in there。

 Actually， emoji or valid variable names in ja on a modern browser。

 So you don't even need to quote them if you don't want to。

 Don't actually use emoji' as variable names in your jascript code。

Mostly because it breaks Internet Explorer， but other browsers are fine。Like hashes。

 these things can be nested as deeply as possible。 What goes on the right side is anything that is valid in JavaScript so a key can map to any kind of value and we'll see how that's used as well useful and important JavaScript is singlethed it does not have any native concurrency abstractions there aren't the idea of threads There are things in node JS now that kind of give you this but it's been a long work in progress within a browser。

Browsers do a bunch of work to fake multithreaded JavaScript。

 so there are places where multiple things on a web page can be happening at once。

 but technically speaking， JavaScript as a language is single threaded。嗯。

Important that what we're talking about here is all this stuff is going to be browser jascript。

 No JS is pretty similar， but there will be some differences。

 So just be aware of that if you're used to writing node or if you later go on and write some server side ja So one of the biggest gotchas in ja is the meaning of this it is roughly equivalent to self and Ruby。

 but not quite which is that when you're in when you're not dealing with an object。

 when you're not dealing with a function， this refers to the global object。

 So in a browser that is the window property， if you've ever done something like window dot location。

 will give you stuff about the URL this without any context refers to that window object。

 inside a function is where it's similar to self where we have our classlike structures。

And in railils， we have this thing called the asset pipeline。

 so app slashasse slash jascript is a good place to put your JavaScript code。

 you can write it in multiple files and then Ruby or rails rather will bundle it all for you stick it in your views the nice thing here is it handles a bunch of stuff so that you don't have to worry about browser caching you can write small modular JavaScript files and have them be compiled into one single thing that gets downloaded by the browser。

So the helper is super valuable。And again。Like all other code， nice。

 clean modules are going to be important。In JavaScript。No， okay， there we go。So in jascript。

 if we manually open two separate browser windows of our application。

 which of the following things or which is true， can we。

What kind of effects can we have on the two separate windows？Let's see if we can get up to。About 40。

We're 50。 We've got 40。Give it another 10 seconds。Alright， that's pretty good。Cool， yeah。

 most people pick C。And C is the correct one here。Each window in Javascript is an independent version of the interpreter。

 This is particularly important for security reasons。 If page A could talk to pages B， that would be。

Pretty disastrous， because that means any website could affect any other website。 Of course。

 if you need two environments to communicate with each other， there are APIs。

 but all of them involve some additional setup work to enable pages to communicate with each other。

But by default， each one has their own interpreter。 If you want two things to communicate。

 you have to explicitly create an API that both pages know about。 And this is all the browsers doing。

 So that is a good thing。 So ja。 We have the ability to write in the browser。 It's single threaded。

And so。Now the most probably useful thing functions， methods， encapsulation in JavaScript。

Everything in JavaScript has this thing that is internally called a prototype。

 for the most part you don't need to worry about this。

 but it is useful because this is a way of over time building out more complicated class structures in JavaScript。

嗯。When you access a method on an object， it will see if that object is directly defined on that object itself。

 and then if not it will look for this special prototype property and look if a method is there。

 and if a method is not on that prototype， it can go sort of up the chain。 So ja。

 even though it doesn't have typical classes like we normally think of it does have a method of inheritance。

 it is useful， you can build as complicated of applications in ja as you can in any other environment。

And。In JavaScript， when you do this with the prototype。

 things inherit both the values and the functions that are defined。On。On that prototype。

And this is a little bit different than classical inheritance， but。It still gives us what we need。

 for the most part， it's something to be aware of when you build large JavaScript applications。

But you can get by with sort of just knowing where to poke around and look。 So here's some Java code。

We have this thing Var is an optional variable declaration， you should definitely use it。

 which we'll talk about in a second。😊，So we say var function， this is a constructor。

For a movie class， this refers to the instance of the movie。Hi。

These functions are the equivalent of instance methods。On an item。And when we use this movie。

 we use the new keyword before。They construct your methods。The Patriot is new movie。

 and then we pass in the properties that our constructor function takes。

And if we ever want to define functions on a movie， we can do that。 We can define additional ones。

 We can call whatever functions or properties we have。And。If we just say this。

 this it will refer to the constructor function itself。 So jascript， what we'll say in a second。

 if you leave off the parentheses of functions， they are not called。

 that is a little bit Python like where you have the distinction between。

A function that is being called and just the function itself in Ruby。

 because parentheses are optional， we don't have that ability。

 so that's one of the differences between just referencing a function itself， but in JavaScript。

 leave off the parentheses you get the function object as well。And again。

 this is the constructor function down here。So this is Conor functions have been described as jascript's worst design flaw。

 The reason is that。It's not apparent from reading a function necessarily。

 whether you immediately have to say new of movie or just call movie to get a movie object。

 the way that you can tell is if this is used in a function to refer to that object。

 you need to use new before it。 If there is no this used It's just a standard object。

 So it's a little bit like an initialized method in rubby， except it's built in to a single object。

And its or it's built into a single function。 it happens in one step。

 you don't have until very recently a class keyword like you would and so。

The the important thing is that if you were to call in this example， if we leave off the word new。

 when we call this movie function， this now refers to the global object because。Javascript， really。

 that was the design decision that if we say new and we pass it and we call a function with new。

 this now refers to the instance of an object。 If we forget to leave off new。

 then Javascript just continues along。 and this refers to whatever the global object is， so。嗯。

This is said to be calling it without a receiver， which is what new is and also if we。

Try and get the return value of that function。 it is undefined。 So when you use new。

 it explicitly returns the instance of that object。 you don't have to do something like return this。

 JavaScriptscript handles that for you when you use the new method so。Which of these？

Values or which of these statements is correct and we'll evaluate to9 this syntax here。

Is new jascript syntax that is a shorthand for a function declaration。

 So this is a function with no parameters that will square a method。 So this is a power operator。

 And when you use inline methods in jascript， they now have implicit returns like Ruby。

 although they only have implicit returns when they are one statement long。

 which is a crazy restriction， but this works like calling a normal function。

 So this is the one piece of a particularly modern jascript in these slides。 but this is a syntax。

 which you will see， as you write more jascript。 So which of these will evaluate to 9。😊。

And let's see if we can get a few more votes in。Oi。Cool， so a pretty good distribution。

Let's take 30 seconds and see if。You can come to an agreement on which of these is right。

Remember that when we leave the parentheses off。We are not calling a function。

 we're just referring to that function value。And that may help as a hint for narrowing some of these down。

Yeah。What。No， this' I didn't。Where are we timer，まいす。All right， let's take about 10。Or 15 seconds。

See if we can get back up into the 40s。Feel free to vote randomly if you're not sure。

Voting randomly still counts for participation points。

You should make like a question with like one answer。Let' see how many people vote for other options。

 That does happen。then you find people may using phone。不是这意个。Well you can't vote for IC from home。

 I don't think。Oh， well， it'll still open。 I guess so。 I should try that。 It's a good idea。 Allright。

 so we're up to about 40。Cool， so still a pretty good distribution。

 The way to answer all coding questions is to try them in the interpreter。

The nice thing about JavaScript is that you don't have to care about tabs and spaces so we can just put this in the interpreter。

 I have this open， so I'm going to use node， but this would work just as well in the browser。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_11.png)

So let's paste this in。

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_13.png)

So again， if I just refer to square， I see that it's a function with the name of square。

 So what is the option here， square。

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_15.png)

Of three dot area。So。Because we didn't use new square3 of area reports undefined and why is this the function square itself doesn't actually have a return statement。

 so in JavaScript， we haven't mentioned this yet， but the return type of a function without an explicit return statement is undefined the other terrible design decision in JavaScript is that it has both undefined and null as values。

 you can also redefine undefined to be something else， which you should never do。

 but JavaScript will happily let you do it。 There's a lot of fun things that you can do there。So。

This one， again， because area is undefined， we can't actually call it。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_17.png)

This one is not going to work as well。 So this suggests that we do need the new keyword。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_19.png)

So C is getting closer to what we want， but。What happens here， area is itself a function。诶。

Why can't I see my， That's weird， am might， okay， whatever。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_21.png)

So。This code right here， we called new， so new square is the right instance。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_23.png)

But because we left off the parentheses， area did not work。

 we could if we wanted to call it like this。

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_25.png)

And why did that actually。Not work。Oh， I know why。 because I'm so the implicit return thing is actually even stupider than I remember in jascript。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_27.png)

Wish。Is why you should be careful about writing slides at 1 AM。There we go。

 impmplicit returns work if you leave off the braces and if you put the braces in there。

 then you have to type return。Yeah， so。Anyway， aside from minor JavaScript weirdness。

So if we were to call this with parentheses， it would work。

This one then as well works because what we do is we initialize a new copy of square。

 and then instead of。

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_29.png)

Instead of calling it square， we've now called it P， but we call P with new。Pass it with a value。

 we square things and all that works as well。 The other thing that if we wanted to test this。

 that we could do。So， whoops。So console。t log is the same thing as puts in JavaScript。

 so if I just console that log of this。Where we go and。If we do something like this。

 we have a square function。 So if I were to just call square of three and I console that log of this。

 what I get back is a giant， massive object， which in node Js is named global in the browser。

 it would be window。 But so if I call it without new Con log of this。

Is that global object an effort to say new square of three。 When I console out log of this。

 the thing that gets logged is an instance of a square。

 and then the thing that is the return value of new of square3 is the instance of the square that we just created。

 So if you're ever not sure what this is referring to it can always be helpful to log it。

 the other thing which is a useful resource for learning ja， especially because。

Some the stuff can be a little bit confusing if you remember Python Tutor from CS621A。

 Python Tutor has a JavaScript evaluation option， which means that they should probably rename it。

 but computer scientists are bad at naming things， so it's still called Python Tutor even though it evaluates JavaScript。

So。Last couple things for today functions are first class objects in JavaScript。

 they can have their own properties because basically a constructor function that creates an object。

 it can have its own properties， it has a function prototype，It is。Also super common to treat them。

As anonymous functions， so if you're used to writing functional programming。

 you will hopefully feel right at home in JavaScript。ES6， also known as ES2015。

 adds classes to JavaScript where you have a class syntax， you have a constructor method。

 they work much more like you would expect classes to work in something like Ruby or Java。

 they are still based on the prototype inheritance。

 so you write them in a way that looks normal but under the hood。

 they have all the same stuff that classes in JavaScript do today。

Var restricts the scope of a variable to the local scope Every time you write a variable in JavaScript。

 you should use the word var if you want to write modern JavaScript。

 which I highly encourage you to do， you have the keywords let and cont。

 so let creates a variable that exists in the local scope that can be redefined Con creates a variable which is a constant and cannot be redefined so that's useful if you import something if you just have a static property that you don't want to change and so on。

And the best practice for ja is to wrap things in a scope that doesn't pollute the global namespace。

 So what does that look like。Oh， well that will be on the next slide。

 the very last thing that we'll get to。So oftentimes in JavaScript。

 you wrap things in an object to kind of group them together， kind of like a module。

 these can have as many functions or properties as they want。

 you can nest them in one direct assignment statement， these two setups are equivalent。

 properties can be functions， so all those work the same。

And we're just going to continue on with idioms。 So one of the idioms for wrapping functions together。

Is something that you'll see a lot in front end code。

 which is wrapping a function in a closure and immediately calling it。

 This limits the scope of that function to something that has。Once you invoke that function。

 it it executes the scope of that function no longer exists because it's been wrapped in its own expression。

 this is something that if you're using a compiler like Babel or something with react。

 you really don't need to worry about， but you will see this fairly often in typical frontend JavaScript。

And。The other thing that we'll see is a bunch of jQury stuff so JQury is also the canonical name for that is the dollar sign variable so if you ever see dollar sign it probably refers to jQury but it doesn't have to and again a common thing here with functions is because they can be arguments to other functions these are often referred to as callbacks and so。

Like any good language with harder functions， you can pass them around， assign them to variables。

 You can do things like curry them。 You can use Lambda， whatever you want with functions。

 So we will continue on with ja on Tuesday， and then we'll get into some front end accessibility step with the dom。

 but。😊，That's what we have for JavaScript and so we'll see you then and again microquiz on Tuesday as well will based on the stuff that we talked about today and the last couple of Michael quizzes will just have a couple additional questions from previous stuff in the semester too。



![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_31.png)

![](img/dbabc14e86ad2eaae2c47ab7d7cf2ce3_32.png)