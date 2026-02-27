# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p35 -35-COMP6080 - Javascript AJAX 🦊 Intro.zh_en -BV17RXGYuEaM_p35-

![](img/ca584a89399ae79024658bce5991fbc2_0.png)

Hello everybody my name's Simon and I'll be taking you through how to do asynchronous networking in JavaScript I've prepared five lectures the first of which goes through sort of some history。

 lays the groundwork for what we're going to be doing and then the second one。

 second lecture is all about sort of the underpinning mechanics of JavaScripts asynchronous model and then the final three lectures will be all about the actual technical details of how we go into asynchronous networking in JavaScript。

😊，So without any further ado， let's just dive straight into it， shall we？Yes。Okay。Start presentation。

So asynchronous networking in Java， the first thing that we're going to be talking about is。😊。

The client server model and what this phrase called Ajax is。

 maybe you've heard of this phrase before， but if you haven't。

 then we will define it by the end of this lecture。😊，Okay。

Let me just make sure that my little window isn't uncovering things。Alright。

 so a little bit of recap from 1，5，3，1。 Or if you haven't done 1，5，31 before， then this will be。

 I suppose the first time you've heard of this although I doubt it。

 So when we talk about client servers， this is an architectural pattern for how to do。😊。

Networking is one of the main examples， it also happens even when you do APIs you have like client APIs or people who use your APIs and then people who provide the services of the API are called servers。

 So client and server and for our purposes a client is a smartphone it's a laptop it's a computer it's a web browser is something like this and our servers generally when we talk about servers。

 we're talking about racks of machines and data centers and these data centers collectively are what we call the cloud So these servers that are owned by Google that are owned by Facebook。

 Amazon all of their server run on these servers which are locked away in data centers Frigid environments to keep electricity going and the way it works is that our client us we make a request So this user is on go and they're trying to search for cats they make a request to the server the server is going to do some processing。

😊，This processing includes validation of arguments。

 executing some API depending on what we're actually requesting in this case we're just going to be requesting the order complete options and then the server returns some data back。

😊，And so you can see here in this。go window， the user has started to type in cats and then the things that we get back are the order complete results from the server and the server has determined that cats obviously is something that you might want to search for if you search for cats and CAsis is another potential order complete。

😊，Solution。And it's the job of the client to take this data generally。

 the data at least will contain raw data like what you see here。

 but the survey also can send back some HTML， it can send back CSS and it can send back JavaScript Sc scripts with your browser。

😊，Goes in executes。And this is what we call the server response。

 so the request rate is what we send to the server and then the response is what we get back from the server。

And I mean， this is how client servers work clients they send things。

 I guess I'm mean reverse on that clients， they send things to the server for their whatever they need for like a request and then the server sends back the response and so it's this interplay that we call the client server architectural pattern but。

😊，It's not as simple as having one client and one server no no no no no。

What's more likely to be is that your app has multiple clients that are being deployed like you could have your mobile client or you could have your desktop client。

 You could have your headless headless client， which is。😊。

Relatively useless for a web app since it's all about the visual but hypothetically you could have such a thing and then your server is actually taking all of the requests from these different clients here and then sending back responses to them。

😊，But this is also a bit of a lie because what's more likely to be the case。😊。

Is that we actually have multiple clients and they're sending multiple requests to multiple different servers for all different APIs。

 so I've called this reality square because if you think about it。

 the left side or I guess the right side this reversing view I'm going to say what's left and right from me。

 I'm sorry and then you can like flip eventually in your mind but this side are all of the different possible clients that can exist right。

😊，And then the right side are all of the different servers that can exist and if you think about it。

 this is kind of like a bipartite graph because for you can imagine in your mind that every web client could connect to every other server and that would be an n squared situation here。

😊，So web app one is sending request over to the latest news API and so as a web app two。

 they're both sending requests to the latest news API and they're fetching back， I don't know。

 the latest news， whatever's trending， whatevers cool。

 but web app two is also fetching from the super cool Cats API because maybe for every。😊。

Maybe for every news tidbit they're also putting in a fact about a cat or an image about a cat。😊。

And so。😊，When we talk about client services in the modern age， this is the reality。

Where servers are under intense load are clients that kind of they're not isolated because they are also serving sending multiple requests to different servers。

 but the clients don't make as many as the servers do。😊。

But you can see we potentially have a problem， right。

 because it's not as simple as having a one to one connection。😊。

We have some design considerations that we have to take into account。

So what are these design considerations？😊，Well， for our client。Interactivityivity and responsiveness。

 which is low latency right， that is the most important thing for a web client。😊。

We need to make sure that user input is serviced basically as soon as it happens and that for any long running。

Operations the user needs to know the progress of what's happening Obviously you can do that in terms of like a what's how a spinner or a progress bar or some sort of loading screen' like the idea of responsiveness。

 even if your app is extremely slow just if being responsive gives the perception that this app is very。

 very usable right？😊，The client side， ideally， the first time you load it should be really really quick and you only ever do an initial hard page load once。

😊，UmIt's it's kind of interesting that as the Internet bandwidth speed has gotten quicker。

 people that people have actually become less patient when it comes to looting pages and if you think about it that kind of makes sense right。

 because if everything loads fast， but then yours just happens to load really slowly。

 then that is out of the ordinary， but if everyone's used to things loading slowly。

 then it doesn't like stand out as much。😊，And obviously。

 it only ideally wants to load once because if we load the page multiple times。

 then you have the potential for like losing where you are on an anchor point。😊。

Or if you don't have an anchor point you'll lose your place because you're just jump straight back to the top of the page if you're like in the process of filling out a form。

 you'll lose any unsaved data， it's just really really bad user experience that a page reload can make the person your user lose their flow or lose their place in where they are in the document and if you're writing client side code naturally everything that you do is client focusedcus so we need to make sure that all of these things these three points are actually that。

😊，And this isn't of course about server side architecture or how to write fast servers。

 but I think it's informative to at least know kind of the concerns of the server because you really want to know。

😊，So how to like work in tandem since the server does support you and server side。

 what happens is that servers need just handle thousands of requests every second。

 thousands of requests come in。😊，And you want each of these requests ideally to be handled within single digit millisecond response times。

Um， so there's what's my math point I going to con there。

Servers also deal quite heavily with resources。 So resources， not just time， but hard resources like。

Power usage， the number of servers that's obviously the amount of time it actually takes to do something but。

You know these data centers that host the servers incredibly expensive to run every microsecond。

 every millisecond costs real money that we need to minimize not only that it's also an environmental thing the better your service operate and the more perform that they are the less power that they use which obviously is good for the planet so I think trying to write good code fastcode minimal code is all around a good a good thing to understand maximizing throughput right that is the I've lost my mouse monitor and keeps this here maximizing throughput is the most important actually let me see I think and you can actually turn on a laser pointer is that。

😊，What is that is this？Yes， haha no you can see the laser pointer awesome right so maximizing throughput that is the most important thing for a web server minimizing latency that's the most important thing for your client so。

😊，These are the problems we do have solutions， but to see how we got to those solutions。

 let's just take a brief little walk。😊，Through history。Sir years ago。

 back in the era that I was born， the 1990s， what was the world like？And the early 200s as well。Well。

 for one there were no smartphones that's for sure clients were majority desktop web browsers I kind of lumped laptops in with desktops because most of the laptops of the time just ran a very。

Similar version of Windows 95， 98， 2000， so they're kind of count as desktops。😊，嗯。

Most of the servers did not exist in the cloud Google I think had just started by that point in Amazon as well so there was no GCP Google Cloud platform。

 there was no Amazon web services， none of this， if you ran a web based business you had your own servers on your preancies somewhere。

😊，This is by far the era of the static web page right static webage is that is that you know you download you send a request or web server。

 it downloads the HTML， the CSS very minimal jobscript because see is a very slow bathroom and then it renders once and then that's it anytime you want something to change you would have to send another request。

😊，Get back the new HTMLtMl page。From the server and that's called well that technique is called server side rendering。

 but you can think about it as a static website so every web page is literally a separate HTML page。

😊，Which is not by far not the case nowadays and the way you would scale your web app is that you would upgrade your server because a server does everything。

 it handles rendering of the webpage， it handles the actual business logic it handles database access it handles everything so if you need a better web app like one that's faster one that can handle more requests then you have to get better hardware。

😊，And that was basically the case throughout the 90s。

 early 200s the internet remember you have to remember that the internet was only born just I think 93 was when the World consortium World Web consortium was founded so people were just starting to figure out everything right and then we'd come to the mid like early 200s of mid 2000s basically the what do we call the ns right the majority of clients they're still basically web browsers。

😊，But JavaScript is getting more， it'， it's going to use more and more in no small part because of JQuery。

 which is one I think the most widely used JavaScript library around。And CFPers are getting fast up。

Still like we're getting into one， two， three gigahertz range。

 I think two gigahertz by like 2007 was was quite common more RAM obviously。

But we're still kind of just。Trying to take whatever is happening in this side in the 90s。

Just kind to its logical conclusion， there's not really any big architectural changes we're still scaling the servers vertically。

😊，But we are starting to see a lot more horizontal scaling， but the biggest thing。

The biggest thing that happened for web by far is the iPhone and smartphones in general。

 because for the first time in technological history， computer science history。

 your web clients were no longer your like how would you say classical computer for the first time we have a handheld computer that is almost as powerful at least in terms of rendering web pages as the computers of the 90s in fact I'm sure the iPhone was stronger than the gateway PCs or you know feel the packet bell machines of the 90s these are all computers maybe you guys don know the brands but。

😊，Basically iPhone the smartphone changed changed everything right because now especially going through the 2010s。

 2011 2012 definitely when AW West launched GCP launched like most clients of web things now aren't computers they're internet of things and mobile clients so internet of things is things like well anything that has internet connectivity smartphones obviously computers still did the classic examples。

 but。😊，Pluss the word fridges， washing machines because apparently that needs to be a thing。

Rspberry Pis， web cameras， all of these can connect to the internet and if they have a display。

 it's almost incredibly likely that the display that they're using is probably a web browser based display and that is a thing that you can do。

😊，You can take like the rendering API of say Chrome or Firefox。

 I think it's called gego pin Firefox or whatever， but you can embed it into applications and that's actually how the S code runs its your way。

but the point the main point is right is that almost all rendering is client side now and cloud server hostsing is dominant。

 so if you want to make your web app all you need to do go sign up for say AWS right your front end in JavaScript or Trascript。

😊，Wwhich is type Java and then you basically write a very simple backend that connects to your relational databaseb like MySQL or something like this。

 you put your backend on the say EC2 instances on AWS and then you just add like five of those andWS handles all of that you know hard stuff for you and then you just have it serve out the front end for you and just like that you have almost as much power I say optus in the 90s when they were trying to create all their onsite servers so。

Things really did change。When we came to the right side。 So as you can see， some of the solutions of。

Like minimizing latency。Pushing server， what would you say， increasing server computational capacity。

Through horizontal scaling， these already are some of the solutions。

 but let's take a look see at what the sort of canonical things that we should say are。😊。

So on the client side right now， because most of the rendering is done on the client side。

 we have this nice separation of modularity。 The client side for all intents and purposes。

 really is the。😊，Presentation layer， presentation layer and then your server is just a backend logic and data layer。

 so we can leave the presentation strictly to the front end。

 which is good because it means that the front end can do things that we can optimize the front end for presentation for responsivity。

 things like this。😊，The next thing that we have been able to accomplish is that on the client side。

 the first page load can happen really quick because now with CPUUs being so much faster and web browsers being very much more complex。

 what it means is is that we can just grab the minimal amount of HTML CSS and JavaScript stick it inside of the initial page load and then for any other data that we need thereafter。

 we can grab it asynchronously。😊，And this is a technique called lazy loading if you're interested。

 but the idea is is that we grab the minimal necessary amount of stuff first and then after that when the web app is running as users go to whatever page that they need to。

 we grab the data there and then only we don't grab everything upfront and this greatly reduces latency。

 which is great to see。😊，Again， we're not talking we're not looking at server side architecture。

 but it's interesting nonetheless to see how servers do it。

 but serverside right they scale horizontally so just in case you guys can get the terminology vertically is when you just add more hardware to a single server。

 but scale horizontally is when you add more servers。😊。

So now service where I think they've scale they've scaled to millions of requests per second because they also do asynchronous event for assess which is pure and what this means in essence is that whilst we're waiting for IO because service。

😊，Backend servers also do a lot of I like reading from theirs， grabbing information from networks。

 things like this， Then they can go and serve other requests， So we're always moving， always moving。

😊，And of course， there is low balancing because we have many more servers。

 we have to figure out which request goes where， and thats that's called load balancing。😊。

So just as a reup， if we go back to the history slide， we started off everything being。😊。

Altogether or， or rather。Altogether on the server server does everything client side basically is a dumb renderer。

 It just grabs the stuff from the server and then sticks it on your web page and the server handles all the complexity。

😊，In mid 2000s， early 2010s， mainly in mid 200s， I would say。Kind of the same。

 but we're starting to see some of these technologies evolve and then in our present era。

We have very much as nice separation and responsibility and we're grabbing things lazily and lazy loading is king when we're talking about responivity because what it means is that we can put all that computational power。

😊，On the responsiveness for the client， which is what we want and the server handles。

It's data fetch business logic asynchronously as well。 So this idea。

Of using asynchronous methodology。To increase responsiveness， to reduce latency。

 to maximize throughput this。Is what we call ajax and Ajax the acronym is asynchronous JavaScriptscript and Xml the Xml was because before JO became a really big thing Xml was sort of the。

😊，What would you call language dire of passing information across different services but？

I think most people agree that Xls not use very much nowadays。

 but I don't think Ajadge kind of roles。Of the tongue as well as agex does。Take it for what you will。

 maybe use if we stop using JSson and we use Ymma， maybe this will be AJ and we'll get back to having nice acronym。

😊，But we have to understand that AjaX is not a single technology。

 it is instead a set of techniques to create asynchronous web apps。😊，Yeah。

 and the nice thing about Ax like I said before is that it allows for well the smooth UiUX。

 it allows for a modular front end and back end， which is great。

 but even more what it means is that we can also use offline apps right because as the front end is changing。

😊，We're able to save the state locally and asynchronously push it to the server once we regain connectivity again。

 and that's actually how things like the whole Google Office suiteite works and Office 365。

 you know like Microsoft offering， they all work if you like turn off your internet connection。😊。

Pall or cable or whatever turn off your wfi， then you'll notice that you can still use it and then when you get connectivity again then you'll realize that it will sync to the server so that's pretty cool。

And this diagram kind of represents sort of the old way where the web browser is kind of just the interface。

 we send requests to the web server it does its thing and then the web server sends back everything。

 but now the web browser still has a user interface， but we're pushing。

Through to this hypothetical ageax engine， which doesn't really exist right is this is like the specific technology that we use to do to all this asynchronous stuff。

 But you can think of it like we send calls off to this asynchronous engine。

 It does stuff This asynchronous engine will eventually return。

 right It's not synchronous doesn't happen in a nice flow。

 It's like we're waiting for the results to come back， which we'll see coming up。😊。

But it's very much this closed loop and then the web browser does its closed loop。

 which is pretty cool。😊，Right， so this is AjaX and the client server model like the reason why I wanted to introduce this first is because we have to understand that we're talking about what we're going to be talking about。

 which will be。😊，嗯。XMl H TtP request and then fetch and asy weight these like three different things。

 right， they are all just a means to an end。 They're just a means to go ahead and。😊。

Enable having a smooth UIu mod front and back end offline app capabilities。

 all this stuff right so we had to like layer the groundwork。😊，In summary today。

 we talked about the client Ser model and we gave a definition for Ajax and next we'll be looking at。

Javascript and how does JavaScript handle concurrency， what is concurrency？

We don't assume that you guys have ever looked at anything to do with concurrency for， you know。

 again， all intents and purposes， maybe you've just early done synchronous programming up till now。

 but。The world is much more exotic than just calling a function。

 waiting for the function to return and then continuing。

 so that's what we're going to be talking about next。😊，All right， I'll see you guys then。



![](img/ca584a89399ae79024658bce5991fbc2_2.png)

Yeah。