# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P21：-20- Web.2020 - GPT中英字幕课程资源 - BV1VcrrYUEL5

嗯。Now there's no audio。We can hear you now， Le you know。Okay。All right， yes。

 welcome back clearly we have no idea what we're doing first try。All right。

 Edwin Kael's 75th birthday， Edwin Katmel is a computer scientist。😊。

He's an absolute giant of 3D computer graphics。He。Was a student at University of Utah which was really influential for computer graphics you may have seen the famous Utah teapot。

 he was a student there of Ivan Sutherland who was the father of computer graphics basically。

 so he's very very high up the computer graphics family tree。

He's been involved in graphics in film since the very beginning。

 if you're familiar with the TV show Westworld that's on right now。

 that's kind of based on a movie from 1973， which was the first movie to have computer graphics and one of the graphic sequences in it was a 3D animation of his hand。

 which he and a partner had done。Since then he led Lucas F's computer graphics group that turned into being a cofounder of Pixar。

 which turned into being the president of Walt Disney Animation Studios。

 so he's been sort of a central figure in graphics and in movies。



![](img/91a6a99e14072f17cc85ed9804f242d7_1.png)

He originated the concept of texture mapping， which is key to like every modern video game。

 he's had a bunch of other technical contributions if you're taking CS 184 this semester or pretty much probably any semester and any graphics class ever anywhere you've probably read or had secondary reading for his his paper on subdivision surfaces。

😊，So really， if you are a fan of movies or graphics， celebrate his birthday today。

Today in networking 22 years ago was the official launch of Mozilla。

And a little history here is that like。The first web browser that was really successful was called Mosaic and it was in part funded by the Gore Bill。

 it's part of the reason why there's the joke about Al Gore saying he invented the internet。

 which he didn't actually say。嗯。But anyway， one of its developers， Mark Andreesen。

 who's now a famous venture capitalist， went on to found a company called Netscape。

 and Netscape made a web browser called Netscape Navigator。

 but internally it was called Mozilla and many of you have probably never heard of Netscape Navigator。

 but like this web browser was completely dominant for a crucial period in the 90s。嗯。So anyway。

 in 1998， an organization called an organization called Mozilla appeared。

They released the source code to the browser under an open source license and this is what eventually became Firefox and this was。

Sort of the beginning of the Mozilla Foundation and it didn't really work out how the organizers of Mozilla originally thought it would。

 but I think that's probably for the best Mozilla is a pretty cool organization it's not for profit。

 it works on behalf of the people really and you know it just tries to make sure that the internet stays open and accessible and preserves privacy and other good things and along the way they develop some pretty cool technology which we all use。

And all this is super relevant。Because today's topic is the web。So before the break。

 I said we were going to start looking at some user facing things， you know。

 rather than stuff like routing and TCP， which if everything is going well you may never see or think about and we started with DNS which at least originally provided a user facing system for interacting with the network based on names instead of addresses。

😊，And today we're going to talk about the web， which is truly the face of the internet and truly a game changing killer app and really not just a game changing killer app。

 but like a world changing killer app。All right， so what are we going to talk about here I'm going to start with a little bit of background that I'm going to talk about the basics spending the most time looking at HtTP。

 which is the key protocol behind the web。😊，Then like we did with DNS， we'll talk about。😊。

Three often interrelated topics of availability， scalability and performance。

And I'll finish by revisiting something from earlier on if I have time。

 which I'm not sure is going to happen。嗯。All right。

 so starting with a really abbreviated history of the web。嗯。In 1989。

 Tim Bs Lee was a software engineer at Cern， he's now a professor at MIT， but back in 1989。

 he saw a problem at CEern。And CernN you've probably heard of。

 you're probably at least vaguely aware of the large Hadron collider and so Cern is a giant particle physics lab。

😊，And all that work。All that giant work doing very tiny work creates a lot of information。

 you've got experimental results and methodologies and infrastructure and people and so on and so on。

😊，And secondly， scientists often come and visit from all over the world and do experiments and then go home。

 a lot of them only stay a couple years。And so this led to this problem where a lot of information would get lost。

 there was so much and the people who might know about it may not be there anymore。

 so even though a lot of information was recorded somewhere and possibly even recorded on a computer somewhere you might have a really hard time finding it like you know maybe you'd need to know which computer to log into with like a remote terminal and then youd need to know where it was stored and how it was stored on that computer。

and he also found that CEernN's existing documentation system， which is called CNdoc was lacking。

 it was strictly hierarchical， but he didn't think that really fit with their information or their organization。

😊，And so he pitched a solution in the form of a document called Information Management a proposalpo in 1989 in which he said。

 the actual observed working structure of the organization is a multiply connected web whose interconnections evolve with time and by the end of 1990。

 this proposal had turned into the start of the web。

So I thought it was worth pulling some points out of his proposal in this slide。

 all the text on it is straight out of his proposal。And。So。

He talks about getting away from hierarchy， kind of like I just mentioned。

He mentions that this system should be accessible over networks。He talks about heterogeneity and how。

 you know you should be able to access it from any type of system。

He talks about noncentralization and says that information systems start small and grow。

 they also start isolated and then merge， a new system must allow existing systems to be linked together without requiring any central control or coordination。

 which I think was an interesting observation。U。And so here's a diagram from the proposal。

 which represents some of what he've been talking about here。

And he really already has sketched out exactly the structure of the web today in a minute I'm going to present my own version。

 which I realized after I made it， it's pretty much the exact same diagram based on you know understanding of the web today。

As an added bonus， you can see a cautionary tale about relying on spell check here。U。

So this last one I think is particularly interesting。

 he says if we provide access to existing databases as though they were in hypertext form。

 the system will get off the ground quicker and here he was talking about using this system to access things like CRNDock。

 their existing documentation system and UniX Man pages and their phone book and so on。😊。

And so here's a diagram he did of that which shows how you know。

 you can use the web to access this this database that already existed。

And so I think we can think about his proposal as basically a list of reasons why the web was so successful and so first it wasn't really trying to force anything。

 it didn't need you to structure data in a particular way。😊。

It didn't need you to store data in a particular way。It didn't need to use a particular computer。

 a database system and it didn't need you to abandon existing systems that worked you know we talked about making them accessible through the web。

And had networks in mind from the beginning and you know this may be sort of surprising today。

 but there were a lot of computer systems which weren't designed with networks in mind。

It also provides an integrated interface to scattered information。

 which I'm going to come back to in a little bit that same phrase。

And it was designed to be a practical solution to a specific problem。

 you know this wasn't just a thought exercise and this can be huge in making projects successful if if this is not something that。

😊，That you have yet experienced， this is something good to know about this notion was captured in a really influential book about open source software called the Cathedral and the Bazaar and has this quote in it。

😊，Every good work of software starts by scratching a developer's personal itch。

 and that's exactly what the web was for Tim Bers Lee。嗯。

Finally CEN and Tim Burnerns Lee didn't try to charge for this technology。

 they made it available for free， they I think they eventually announced this license that it was free in perpetuity。

 free license in perpetuity and we take that sort of thing for granted a lot these days。

 but this was you know around 1990 this was still really early days for open source software and open development in general。

 the new public license which of course is used by so much software today was only like a year old at the time Linux wouldn't appear until a year later。

 so this was you know relatively revolutionary。And so anyway， like not all of this was new。

 but this was when the time was right for it to all really come together for the first time。

And I think that list of what made it successful then is pretty much what makes it successful now the web gives a lot of leeway for how websites work。

 it didn't overspecify things， it had this really abstract model of like nodes with links right around at the same time that the web was starting like I think it actually started slightly later but immediately became far more popular than the web was this system called Gopher and Gopher had a way more rigid structure。

😊，The developers said that they modeled it off of how we organized information in the real world at the time。

 which was like a library to them。Um， but you know。

 I think you can ask a question like something they probably didn't have in mind like online banking or online shopping。

 how would you map that onto a library？You know the the web started with something way more abstract which you can use to build a library or a bank or a store and I think that that starting from that really abstract powerful notion of you know just content linked together is a huge portion of the success。

 you can imagine if you start an information system thinking oh this is a system for doing banking。

 you would never be able to have taken that banking system and used it to create Gmail or Facebook or something like that。

 so a big a big part of this success I think。U。And。It's not tied to any one underlying system。

 any particular hardware， any particular technology at all， except for its own。

U and it's decentralized， which means that anyone can buy or rent a server and an internet connection and add their own content or service to the web。

U and it gives us the ability to quickly navigate all of that content and all those services。

 even when they're from different sources and it lets us organize and reorganize them on the fly。😊。

So to sort of finish this introduction out。You know， it turns out。

The early web was almost mind numbingly simple from a technical standpoint。

 and it turns out that from an intellectual standpoint。

 a lot of the ideas behind the web had been being worked on for years and from the perspective of some of the people who did a bunch of that work。

 the web didn't even do it very well or well at all。Um， but the execution was amazing。

 it was and still is a hugely successful and practical system that absolutely changed the world。嗯。

Scott Shankker， who's my advisor and who's taught this course many times。

 has pointed out that no professor could design something so simple。

 it's got enough functionality to be effective， but not enough to prove her cleverness。

 which I think is an interesting thing the web is practical and has like just the right amount of insight behind it。

So。Um， you know， ultimately， I think。You know， we we couldn't possibly have a class about the internet and and not look at it and the fact that it's been used for a while now and it's been so successful and that people care about it means that it's only gotten more interesting。



![](img/91a6a99e14072f17cc85ed9804f242d7_3.png)

All right， so。Let's start off by looking at the basics。A lot of this will be pretty quick。

 I'm sure many of you know a bunch of it already， but I want to kind of establish sort of common context and terminology。

So what are the requirements of the system？As Timber and and Lee said in his proposal。

 we want this web of information and so we need a way to represent content that links to other content and that's HTML。

We need a client program to access， navigate and display content like HTML。

 and that's the web browser。We need a way to reference content and that's URLs you know it's how you link or embed content in other content and URLs really like the first general handler name for arbitrary internet content you know before that we had DNS but that didn't name content at all that only named hosts and you could add a port and that basically just named a process on some host right so being able to name the content in this kind of universal way was actually a pretty huge innovation。

嗯。We also need something to host that content and that's web servers。😡，And。Finally。

 we need a protocol to get that content from the server to the client and practically speaking that means we need a way to turn web URLs into TCB connections。

 so that's HtTP。😊，So really quickly， we've got HTML， the hypertext Markup language。

 or a way to represent content with links。

![](img/91a6a99e14072f17cc85ed9804f242d7_5.png)

So here's a tiny HTML document， you probably all know HTML。Um。

 and we have a browser which lets you access display and navigate content。



![](img/91a6a99e14072f17cc85ed9804f242d7_7.png)

Um and。Using HTML your content can let you link to other content。

 this is what hypertext means or more generally hypermedia。

 this ability to link from one piece of media to another。



![](img/91a6a99e14072f17cc85ed9804f242d7_9.png)

You can also embed content in other content and like note in this case。

 you know that the embedded resource isn't local at somewhere else and this is the magic of the URL like in general systems just didn't work like this before。

嗯。So this is what I meant when I talked about providing an integrated interface to scattered information。

So how does this magic URL work it's made up of several parts。

 the first part is technically called the scheme， but for practicable purposes it's the name of a protocol。

 there are URL schemes for a lot of protocols to let you access and refer to them in a common way。😊。

Then you've got the host name or an IP address， optionally you can include a port。

 usually the protocol infers a well known port， but you can override it。

Then theres a path which traditionally in many cases reflects a path in a file system on the server。

Then there's the resource， this is the thing that you're accessing in many cases。

 especially traditionally it was a file with the content you wanted， but it could also be a program。

😊，Um， like here is a crazy URL， which is for accessing a particular email in an old version of Yahoo's webmail service。

😊，And you may notice this question mark in here， and then that's actually another optional part of the URL。

😊，Which is a query。In the previous example， the query was for some specific email to show for web searches。

 it's the search terms and so on。😊，And then finally。

 there's an optional fragment and this is like a subpart of a resource。

 like a way to name a specific paragraph on a web page。

So not sure exactly how we're going to do this on Zoom， but are there any questions so far， you know。

 you can ask them in the chat or maybe by audio。Or raise your hand， you could try that also。

All right。I'm going to take this as meaning， no questions。

So at this point I've been speaking pretty highly of Us and really they are great。

 they're such an important idea and they seem so obvious in retrospect。

 but the internet was around for a pretty long time before someone thought of them so you know credit where credit is due。

😊，But I do want to remind you of this subject that I brought up during the DNS lectures。

 and this is actually sort of a mashup of two slides from the DNS lectures。😊。

From a thousand0 feet URLs are basically a host name plus a file name and so you know there's this question of like is this ideal like what if you move a file to a different machine？

😊，And what if you want to replicate the file on many machines？😊，Like just in general。

 like who cares about the machine， we care about the content and so that that kind of notion has led to research like name data networking。

 which has specifically been working on ways to address and name and store content directly instead of having to associate it with a machine。

And in some cases we're not even interested in content， we're interested in a service。

 so maybe services would be the right way to go， though just naming a service isn't even necessarily that interesting。

 you know maybe we need a generic way to specify the usage of a service somehow anyway。

 my point here is that URLs are great， but I want to encourage you not to let what we have now constrain your imagination for what we could have。

And the way things could work。Um， you know， if Tim Bernner's Lee's imagination had been constrained by what existed at the time。

 we wouldn't have gotten the URL for me to complain about in the first place。So， you know。

 there is that。嗯。All right。So。Let's put it all together。We've got HTML。

Which represents content with links and embeddings。嗯。We've got web servers which host the content。

We've got URLs which specify the location of content。And we've got HttP to get content。

From the servers based on a URL。And then we've got a browser that displays and navigates that content。

And this is the diagram I was talking about， I didn't do this on purpose。

 but it's so similar to the one from Tim Bernner's Lee's proposal 30 years ago。😊，So again。

Any questions on this？😊，Try to let me know in the chat。All right。

So at this point we've covered all this stuff pretty well。

 I think in as much depth as we're going to we've got a question。

 did you think of support for a query at the time as well like the query part in URLs I'm assuming is what that means and yes I'm quite certain he did you know he I mentioned you know he had this notion of making other things like like Cerndoc available through HTTP and the way that that would be done would be probably through some script with a query and so a query URL so yes。

 I believe the answer to that is yes。😊，U。All right。So。Slides are stuck， there we go Okay。

 so we're going to spend some more time talking about this part now HttP。😊，So basic HtTP。

I'm going to focus our discussion on sort of the most common versions of HtTP at the present。

 which are HtTP1 and HttP 1。1 these are a pretty direct。Outgrowth of the original version of HttP。

 which was retroactively named HttP 0。9。There is an HTTP2， it was published in 2015。

 it's basically based off of work done by Google who obviously has a really big interest in pushing things forward as of now less than half like 44% of websites use HTTP2。

 it's a pretty big departure from earlier versions， but not really like in a change of semantics。

 more like just the way it works for performance reasons。😊。

HttP3 is kind of on the horizon again a lot of the work was done by Google。😊，And again。

 a lot of the changes are really about performance and not about changing the semantics。

It's not finalized yet and all browsers don't support it yet and as of today something like 5% of websites use it and it's like all the ones owned by Google and Facebook you know it's Google and YouTube and I don't know blog sptter or whatever。

And so HP2 and three we're going to mostly put aside。

But a lot of what I say will apply to them as well。So。HTP uses a client server architecture。

 the clients connect to the server using TCP on a well known port， which is port 80。

The client issues a request， the server issues a reply。😊，And the protocol is stateless。

So all this stuff， you should basically understand what I'm saying here。

 we're going to go through the details but hopefully you get the gist。

This maybe is a little bit less obvious， hopefully we'll have time to come back to it later。

But let's start by taking a look inside sort of the most basic kind of HtTP exchange in a time sequence diagram。

😊，So first， the client initiates a TCP connection on port 80。嗯。

Then the client sends a request and this often fits in a single packet。

Then the server sends a response。And the client acts it。 And， you know。

 the response may spread multiple packets。 And so they all get act。And then。

The server closes a connection。Simple， I think。You know。

 let me know if you have any questions on that， I think it pretty much makes sense。嗯。

And so now let's take a look inside the requests themselves。嗯。So it's plain text。

 it's human readable， and the lines are separated by CRLF。嗯。And all right， side note。

 my experience tells me that not everyone in this class probably knows what CRLlf means。

So in common text encodings， like ASI and Latin One and UTF8。

 these are things your computer uses to represent text。😊。

In using encoding's common English letters and punctuation are encoded by like a single byte。

 so like a byte with a value of 65 is a capital A， 97 is a lowercase A。

 35 is the pound sign and so on and so on。😊，And。The lower characters are control characters like eight is backspace。

 four is end of transmission。😊，10 is line feed or LF and 13 is carriage return or CR and so what do these mean they come from when these control characters controlled printers before video displays and so the line feed made it feed one more line worth of paper through the printer。

And the carriage return made the carriage， which is the thing that actually prints a character return to the left side。

😊，So you're probably familiar with backslash n in a lot of programming language and stuff for new line and on UniX like systems that just means linefe but it basically is both on UniX like systems on Windows it means CRLF if you open a file and text mode and lots of programming languages it does the translation for you automatically if you've ever opened up a file and a text editor and every line ends with some weird character or like carrot M those are carriage returns and that file was probably created on Windows and you're probably on a UniX machine。

The carrot M is a way of representing control M and if it's not clear why it's M。😊。

M is the 13th letter of the alphabet and carriage return is control code 13。All right。

 so back to the HP request。The lines are separated by CRLF。

And so we're going to be requesting this URL shown here on the right and so the first line of the request once you get the TCP connection open is the request line and I've color coded it for you you're welcome and it's got three parts and so the first is the method and that's basically the action that you're going to perform i'll talk about these more in a second but the most common one is gett which does just what it says it's how a client gets a file。

😊，And then there's the resource， which is the page to fetch or you know the thing to fetch in this case it's the web page about dohtl。

And lastly， it's the protocol version， which for our purposes， is 1。0 or 1。1。嗯。嗯。So。

That's followed by request headers， these provide more information or modify the request。嗯。

And them some of them are optional， some of them are required。

 it kind of depends on the circumstances。😊，Then there's a blank line。And then there may be some data。

 there may be a body and this is used when the client is actually submitting information like if you're sending an email and Gmail。

 the text of the email will be in this body portion。😊。

and I just want to call out how the URL fits in here， you know， we took this URL and the domain name。

 you know， told us where to connect。😊，And the rest of it ended up on the request line pretty much to tell the server which page we wanted。

So now let's look at the response for this request。And so it starts out with a status line。

 and this tells us the protocol version that the server used。It also gives us a status code。

 which is this three number code， which tells the client if the request was successful or whatever。

And it is a human readable reason for the status code in this case。

 we see a 200 which means everything was fine and the reason was okay。😊。

Then we've got response headers that provide additional information， like you can see。

 it shows the date here， it shows what server was used to serve this and so on。

Then there's a blank line。And then you've got the body of the response， which is again， optional。

 but it's really common， like in this case， it's going to be the HTML of about dot HTML。

 the file that we requested。So let me know if there are any questions on that so far。All right， so。

Quick rundown of the important hTP methods there are more but I think they're all like exceedingly rare these are the big ones and so the first one is get which we looked at and its just like most requests are gets and it's like how a client fetches a resource。

😊，Then there's post， which is sort of the opposite。

 it's usually how a client sends data to a server submitting a form or adding an item to a shopping cart or things like that。

And then there's head， which I think is actually pretty rare。

 but it's basically exactly a get except that the server doesn't send the body。

 it just sends the headers。😊，The status codes， we saw 200 already， which means everything's fine。

 There are more。 The first number tells you what kind it is。

 So like 200 ones are all some kind of success。😊，300s are supposed to be redirections， though 304。

 which is a super important one， which we'll talk about later， is not really a redirection。

Unless you're really stretching the definition， but we'll come back to that。

400 are when the server thinks the client made an error the famous one here is 404 which means the resource couldn't be found I'm actually super curious。

😊，If people in the Zoom are like familiar with 404 did you know what 404 meant before I just mentioned it like I don't know say something in chat or do a hand raise or something' I'm curious or maybe also say no if you didn't know what it is。

Got some， got some yeses。Got some。Got some kindas。It's you know someone mentions and this is so true like you know。

 they were they're not super the reason I wondered whether people knew about them now is that they're not nearly as common as they were because of shifts in the way website content is managed but in you know the 90 the early 2000s they were super common they were one of the annoyances of internet everybody hated them and because of that as someone pointed out in chat a lot of websites switched to having like funny or interesting 404 messages so that when you found a missing page instead of just getting error 404 you'd get something sort of amusing I guess to sort of you know take this sting out of it。

嗯。Okay， anyway， 500s are when the server has had some kind of an error。

 it's definitely like the catch all basically like whenever the server has been misconfigured。

 you're likely to find 500 errors。😊，And so with that， we've covered all this stuff。

And we still need to talk about this stuff。😊，But you know。

 we're going to talk about some other stuff first so before I move on。😊。

Let me know if you've got any questions on stuff we've just covered。All right。

 so at this point we've we've kind of talked about the basics， so you know。

 like what else do you need？嗯。From a user's perspective we need to be fast and we need to be highly available。

 right， nobody likes a slower broken sight。From a content provider's perspective。

 you also needed to be fast and highly available because you need to make your users happy。

 you also want it to be super scalable right you want to stay fast and available even with lots of users and lots of content。

😊，So。Do these goals sound familiar？嗯。I hope so because they're really similar to the ones from DNS if they didn't sound familiar I think maybe you haven't watched the DNS lectures yet and I think there are some of you I don't know if you're watching the zoom。

 but some of you you should go watch them they're great I give myself four stars。😊。

Possibly out of 10 stars， you can decide， but you have to watch them first。so。Anyway。

 we're going to solve them with really similar ideas as we discussed for DNS replication and caching。

We're also going to address some issues with TCP。And so， you know， that brings us to availability。

 scalability and performance in HTTP。😊，嗯。So like with DNS， these are somewhat intertwined。

 I'm going to talk about basically three things which are caching。😊。

Content delivery networks or CDNs。And the interplay of HtTP and TCP。So starting with caching。First。

 a quick refresher。See time management， I think going to make this super quick。

Why is caching work caching works because of the principle of locality theres there's basically two kinds。

 there's spatial locality which means if you know you access a thing。

 you'll probably access another thing nearby temporal locality says you know if you access a thing you'll probably access it again soon if you're taken 61C you're familiar with both of these in the context of CPU caches。

 one of them is a lot more relevant to web caching than the other。

 anybody have a guess which just someone throw it out in chat。😊，You got a guess。Everybody's got。

 It's temporal。 temporal is way more relevant to web caching。U。

So how well does caching work it works really well up to a point file popularity has this high peak but a long tail that is there's a large overlap in highly popular content。

 but there are also many unique requests set another way。

 you know everyone downloads the same viral memes， but everyone also has their own weird interests。😊。

Anyway， this is pretty common to many types of caches。

In the real world caching is also complicated by the fact that content is increasingly dynamic。

 YouTube， social networks， Netflix， et cetera， they all offer you these you customized views tailored to you and they update them often。

 but there's still a lot of static content worth caching， you know， there's images。

 there's CSS style sheets， there's JavaScript libraries and so on。All right。

 so how does caching work in HtTP， the key is all in those headers that we saw in the request and the response。

 starting with the two response headers， cash control and expires。😊。

And so the cache control header is actually used for a lot of cash related things。

 there are a bunch of variants of it for both requests and responses we'll talk about a couple。

 but the most important is for the server to specify what it calls a max age and that's just a TTL in seconds it's how long the response can be cached for it looks like this in a response。

😊，Cash control is an HtP 1。1 thing in HtTP 1。0 there was just the expires header and the expires header is like a TTL in absolute time。

 so it's really more like a time of death。😊，Um，Svers often just send both。So back to this。

 these two headers are basically different ways of specifying a TTL。

But that isn't always sufficient you know in many cases the server doesn't really know when in the future content's going to be updated so clients need a way to force skipping caches and get to this server and this is done with the cache control noC or the pragma noc request header depending on whether it's HtP 1。

1 or 1。0。I'm walkingalking through an example here。Um at。T0。

A client is requesting a document which has a one minute TTL。

 so the client makes the request and it's intercepted by the cache and the cache doesn't have the document so it sends it to what we'll call the origin server。

😊，The origin server sends the document back to the cache。

 giving it the TTL using the cache control max age header。And then the cash returns it to the client。

And there you go。At T1， the document is updated on the server。😡，There， so now it's 2。0。

But if the client does a request now。The cache is going to give it the stale one until t equals 60。

So。Question for you all， do you have any idea what you would do about it if you were in this situation。

 if you wanted the latest version， like I just told you that the browser needs to send cash control no cash。

 but do any of you have an idea of what you would actually do if you were sitting in front of your browser in this situation？

😡，Yeah， I got a suggestion to clear cache in the browser。

 anybody have another suggestion that's that's definitely true that。😊，That would absolutely work。

 It's sort of a what's that， what's that expression。It's a way bigger hammer than you need。

Nobody else any ideas on this？So you could refresh the page。😊，If you just hit refresh。

It's actually just going to reload it， it's going to go to the cache and get you the cache version。

You're on the right track。AhConl shift R or hold shift and click the refresh button。So yes。

 Richard in chat got this one and so。Yes， you can get your browser to do what's sometimes called a hard refresh。

By shift clicking or doing control shiftr in your browser。And so basically， if you did this。

 let's say t equals 10 when the catch is still stale。

 it's going to send the request with the no cache header。😊。

U it's going to get to the cache and the cache is going to skip it。

 even though it's got it cache and send it straight to the server。

 the server is going to send it back and it's going to end up getting the new version at the cache and at the client。

😊，Okay， so what if the TTL expires and you hit refresh and the document hasn't been updated。😊。

What happens then？Is that you transfer the file for nothing right you just transferred it。

 but you already had the version in the cache if you did it you know earlier it would have been version one if you did it now you get version two again。

And that's sort of wasteful， right that's a waste of your bandwidth。And it's a waste of your time。

 especially if it's a big file。And so we have this request header if modified since。

 and the value for it is just the date of the version that you currently have in your cache。😊。

When the server gets it， if the file has been updated since that date。😊，It sends the latest version。

嗯。If it has not been updated。Then it responds with status code 304 not modified， like I said。

 not really a redirection， but you know this includes all the headers is just not the body so it lets you know that you're up to date but doesn't waste bandwidth actually transferring it if you already have it。

嗯。Right， so。In the previous example， I kind of drew the cache as this separate thing and that happens。

 but it's also the case， as was mentioned in chat， you know， every browser has its own cache。😊，嗯。

And so let's look at how a typical caching interaction works from the browser's perspective and actually。

 you know what I'm going to go back and earlier when we had this suggestion to clear the cache to get the updated version of the document。

😊，That would be true if it was the version in your local cache your browser cache that was out of date。

 but in that example it was actually is cache somewhere else and so just clearing your local cache wouldn't necessarily fix that you do need to send that request with that no cache header to resolve it so sorry I was wrong when I said that。

😊，All right， so。Going back here what am I talking about right so let's do an example and see how it works from the browser's perspective with the browser cache so it starts by requesting a resource。

😊，If the resources in the browser cache， it checks to see if it's expired and if it's not。

 it uses the version in the cache。If it is expired。

 it sends the request using the if modified S and the date of the cached version。

And if the server's version is newer， it sends the new version。

 if the server's version has the same date， it responds with a not modified message。😊。

And if the resource wasn't in the browser cache， the client sends the request without the if modified sense because it doesn't have a date to compare with。

So okay， pop quiz， I gave the conditions for if the server's version' is newer or the same。

 what if the server's version's older？😊，What do you do then？Got a suggestion for a 304。

Not a not a bad guess， I mean， really if this happens。

 something really weird has happened right like how would the client have gotten a newer version than the version that's on the server right。

 where would it have gotten it from？😊，So something must have gone wrong somewhere in practice I think the usual is actually that the server just sends its current version in this case too。

 so really it's just comparing like if the server's version is the same as the client's version otherwise it sends its current version。

😊，All right， again， you know， this example was just looking at the browser cache in the cases where the browser actually sends a request。

 it may have then pass through other caches that have a similar algorithm。😊。

So any questions on this stuff so far？Because the next thing we're going to do is dig into a more complex example。

😊，I'm going to do it kind of quick， all right。So。We've got two clients downloading a document。

and the clients both have browser caches and there's also this other cache in the middle of the network here and the document has a TTL of five let's say minutes and so I'll put that up in the corner too。

😊，All right。At t equals zero。A requests the document and it's not in the cache。

 so it forwards it to the server， which sends it back to the cache。

 which caches it and sends it back to the client。At T equals one。Be requested。So what happens。

 so on throughout， what happens here？Where does it get fetched from？No takers， it's going to。

It's going to get fetched。From the cash， yes， the cash returns its version。嗯。Thank you to Samuel。嗯。

So then at T2， the document is modified on the server。😡，And at T4。B request the document again。

 so what happens here？😡，Is it going to get it from the origin server？Get the new version。

From the cache， from the cache， I assume you're talking about the shared cache。But。No。

 it's going to fetch it from the browser cache right the TTL and the browser cache is still just fine。

 so good guesses， but it's going to load it again locally。😊，So at T6， A requested again。

And so now it's going to send this request with the if modified S header。

 and it's going to send that to the cache。😊，And it's doing that because the document TTL was five and so it's now out of date。

And the shared cache is going to do the same thing it's going to send to the origin server。😊。

Which is going to send it back and it's going to get cache at the shared cache and at the client and so version two gets fetched from the origin server。

😊，At T7， be requested again。Goes to the cache with the if modified since it has indeed been modified。

 so it gets returned from the cache。Any questions on that？All right。

 so to some of the important cash related headers。We've got the cache control max Age and expires。

 which are basically TTLs。嗯。So we've got a question of is the TTL the time it expires or how long it lives right and that's that's basically like you know you can see how the two are kind of equivalent or can be equivalent and so。

😊，Cash control max age is the number of seconds until till it expires and expires tells you a specific time that it expires。

😊，Do the shared cash and the client cash have the same TTL？😊，It's， I think， going depend。

It might depend in general， they should be very close。There might be depending on the implementation。

 they might be off like a little bit like the time it takes to do the request。

 but it should be pretty much the same。Now we've got this great question of where the shared cache is located usually and just hang on。

 we're going to talk exactly about that。嗯。All right， so we've also got these this request header。

 you know， we've got the no cache one to tell you want to skip the cache and then we've got this way of the if modified S header in order to skip downloading the body if our cache version is up to date。

嗯。And。So a quick kind of final word on the cash control header like I mentioned it does a lot of things and some of the things it does just as a side note here。

 cash control No store is a way to let a server tell everybody definitely not to cash it and it's used for things like banking data which you don't want people to store a web page that has your bank account number on it or something especially because they may store it insecurely and then there's cash control private which is basically a way of you know saying that the data is only meant for one user so you can store it in a browser cache but you shouldn't store it in a shared cash。

😊，And so we've talked how caching works， but where are the caches。

 we know we've got one in a client but as was asked in chat we've got a question of where do the other ones live and so they live in proxy servers and so you know what's a proxy server it's a server that makes requests on behalf of the client the caches that we saw in previous examples fit that definition and caching is a major feature of a lot of web proxy servers proxies are also often used to enforce policy they're used to do load balancing and they're used for protocols besides just the web but our focus is going to be on the web。



![](img/91a6a99e14072f17cc85ed9804f242d7_11.png)

And so here's sort of a baseline diagram with no caches。

 you've got you know many clients transferring data from the same server here in SearchCp。

 it generates kind of unnecessarily load on the server and on the network and the clients may experience unnecessary delay。

And。So。😊，A content provider may set up a proxy server， a cache called a reverse proxy。

 and so this is a cache that's near this server。😊，Um， this reduces server load since， you know。

 the easy stuff gets， you know， served out of cache。嗯。So。Oh I just said。

 then there are forward proxies which cash documents close to the clients and so this reduces network traffic and latency and server load。

😊，And so。You know this is typically done by an ISP or an enterprise or in this example， a university。

 and I just I want to point out that， you know， it's true that it does reduce the server load。

 but like the people who actually set these up that's not usually their concern right it just kind of happens but that's not why they set up the cache。

 they set up the cache for the other reason。

![](img/91a6a99e14072f17cc85ed9804f242d7_13.png)

So back to this， where the cache is， they're also in proxy servers。

 either forward or reverse proxy servers。😊，嗯。And they're also in content delivery networks or CDNs。

 but this is zone whole topic， so if there are any questions on this caching stuff。

 let's talk about it。😊，Now。All right， so content delivery networks。嗯。

We know from our talk about DNS that replication is a huge benefit。To availability。

 scalability and performance， you know it spreads the load。

 it puts content nearer to clients and you know caching is basically sort of an opportunistic form of replication。

 but like what if an organization doesn't have a forward proxy or what if a content provider wants to make sure that its content is always replicated and close to its clients？

And so this led to this idea of like caching and replication as a service and that's what the original CDNs were about and so I call that CDN 1。

0 that's my term。😊，嗯。And so a CDN is basically a large distributed storage infrastructure。

 the absolute king of CDNs says Akaai who has over 275，000 servers in 136 different countries。😊。

And so you know you've got this question of how does a content provider get their data onto aized servers and there's basically two ways pull and push and we'll come back to that in a moment。

 but both techniques are often used with a DNS trick mentioned in the DNS lectures。😊。



![](img/91a6a99e14072f17cc85ed9804f242d7_15.png)

嗯。And so how it works is a content provider buys service from a CDN like Akamai。😊，The CDN。

Creates new domain names for the customer like e12596。dscj。 akaaied。

net is akaai's name for CNN's content。And so the CDN's DNS servers are authoritative for the new domains。

And so then the content provider like CNN in this case rewrites their content to include URLs for the newde domains instead of their own domains and they call is aizing their content。

😊，mFor example， CNN might have had some nice URL like www。cnn。com/spho。

 which now becomes this total mess of a URL on the right side here。😊。

So when a client accesses something from the CNN， it first you know goes to CNN and downloads the page。

 but then all the embedded links for JavaScripts and images and stuff all go to AkaMmai and you do this DNS look up for AkaMmai and their servers。

We'll pick one of their 275，000 servers to serve it usually based on the location of the client and the server load and so on to try to get the best server for the client。

So DNS P quiz here， if CNN doesn't want to embed a weird akamite domain name in its pages。

 is there anything it can do about it？😊，Yeah。Way to go， way to go， people， you seename it， right？



![](img/91a6a99e14072f17cc85ed9804f242d7_17.png)

YouAnd so CNN， in fact， does have a C name for cdn。cnn。com is， in fact， this akamai record。Good job。

All right， so。It'sGoing back to how the content provider how it gets their content on the CDN servers。

 the first way is pull and so here AAMI servers just act like a cache。

 the content provider as give an AAMI an origin URL and when a client requests from AAMai if AAMI has a cache。

 a server from the cache， otherwise they'll pull it from the origin。

 request it from the origin and cache a and serve it。😊，So。

The other way is push and so basically in this case， AkaI servers just act like any web server。

 the content provider has explicitly uploaded content to the CDN and the CDN distributes it to all their servers。

😊，So there are trade offs between the two different approaches。

 the super super short version is that pull is less work for the content provider but push provides more control。

😊。

![](img/91a6a99e14072f17cc85ed9804f242d7_19.png)

So just to see what it looks like， pull CDNs look a lot like other caches that we've looked at。

 except now the caches are probably in some ISP network somewhere。

 the CDNs like this because it lets them provide a service and get caches you know somewhere close to clients and ISPs like it because it saves them on transit traffic so they're willing to let AkaMai you know put these caches in their network somewhere。

A difference from other caches we've looked at is that it's only caching content from the CDN's customers。

 right？Push CDNs look a little bit different again the CDN puts servers in other networks。

 but now the content provider pushes to the CDN companies pushes their data to them。

 and then the CDN pushes that content to their actual servers and now the content gets retrieved from there。



![](img/91a6a99e14072f17cc85ed9804f242d7_21.png)

So it's pretty clear to see how this works for static content like I was calling CDN 1。

0 you can cash on demand pull style， you can replicate manually push style and you can pick which cache or replica using kind of clever DNS but you know what about dynamic content or dynamic features and so CDNs want to provide this type of service and there's actually a lot of evolution in this area right now。

And so that finishes up CDNs， any questions？All right， so。TCP and HTTP。

 we saw that caching can be this big performance boost， but TCP can also have a really big impact。

 so let's start with some observations here and。😊，First many web pages are composed of multiple objects like an HTML file and a bunch of embedded images and stuff many of the responses are pretty small like only a few packets。

😊，For example， small images or three04 responses if you've got it cached。😊，I did a test and so CNN。

com resulted in 40 year responses that fit in a single packet and that was with a clean cache so there are a lot of these really small requests that was just loading the front page of CNN。

😊，嗯。And so the TCP overhead， fetching in small objects can be really large。😊。

So let's think about my 40 small objects from CNN， how do you retrieve them and naively you do it one at a time。

 you open a TCP connection， you do the HTT request and response and you close that connection like in this time sequence diagram here。

Not that when I've got two arrows going the same direction。

 those could be basically on top of each other， I'd put them on top of each other or I'd put them spaced just so that you can read the labels。

嗯。But okay， so in snares like this， the transmission delay isn't the issue。

 a packet of five megabits takes less than three milliseconds to transfer rather a packet at five megabits takes three milliseconds to transfer so the time really is dominated by RTTs like my RTT to Google is 30。

😊，Milliseconds。So like 10 times more。So how long does it take to download 40 small objects？40。

Times 2 R TTs， right。You need two RTTs， one for the TCP connection， you've got the SIN and SinAC。

And then one for the HTP， you've got the get and they've got the response。😊，So why not three。

 you know， it's because by the the third one is just for the close of the connection and who cares。

 you've already got the content， so two times 40。Anyway that's about 2。4 seconds that it takes。

 even though the actual transfer time you know the transmission delay if youve just sent the data straight out would be less than a quarter of a second and I'm being really conservative here like5 megabits is not that fast I pay for cheap internet and I get 25 mebits and I used Google for the run trip time and Google's Google they're distributed and highly optimized lots of sites will be slower CNN was actually more like 45 milliseconds for me it's like using those numbers it's actually more like it takes 3。

6 secondsd and the transfer time should actually be like half a millisecond I think。So anyway。

 it's obvious that this approach is not so good。So one thing we can do about it。

Is to make the requests concurrently that is we can make several in parallel so how many RtTs does it take to download 40 small objects if you do it for at a time？

😊，It sayss straight four times improvement， right？So obviously this is a big simplification like I'm assuming that you can safely ignore the transmission delay。

 but it's a big win and so browsers actually do this like over time the number of concurrent connections they've supported has changed and I'm not sure if it still is but for a really long time it was really common for browsers to use six connections at once or up to six anyway。

😊，Another thing we can do is what are called persistent connections and the idea here is just to maintain the TCP connection across multiple requests and the client and server could just tear it down whenever it's been idle for a while。

So this has a number of benefits， the first is obviously that you don't pay for an extra TCP connection setup for every connection。

😊，This also has benefits for Tpeeak congestion control。

 which you'll learn about in the coming lectures。😊，嗯。So how many RTTs？

To download 40 small objects with a persistent connection。U，It takes。

40 for each object plus one for the TCP S and SAC。With a 30 millisecond round trip， that's 1。

23 seconds， so that's a pretty substantial improvement。

But you can combine it with persistent connections， so with four persistent。Connections。

For concurrent persistent connections， it would only take 330 milliseconds， so that's a big win。

And so browsers do this too， it was optional in HttP 1。0， it's optional in 1。1 also。

 but it's the default。😊，So you could also do what are called pipeline connections and so these are like persistent connections taken to the next level instead of waiting for a response before sending requests。

 you just send a bunch of requests all at the same time and this is taking advantage of the fact that you usually know a bunch of things that you want to download all at the same time like when you load the main CNN page it pretty much immediately knows a bunch of those things it wants to download。

So there are two big performance advantages here， the first is it reduces the number of RTTs。😊。

The second is that， you know。If you know multiple requests or responses are really small。

 then they can be smashed into like a smaller number of larger packets。

 like if your responses are only 100 bytes， you could fit a bunch of those in a single packet and larger packets are generally more efficient。

So how many RTTs to download 40 small objects？2。😡，Only two。

 so this is probably dominated by the transmission delay now。

 so this is like getting towards optimal here。嗯。So these were introduced in HTP 1。

1 and then everybody turned them off and they've been turned off ever since。

That may seem sort of surprising， given that they seemed like they were going to be this absolutely huge win。

It was primarily for two reasons and the first one was bugs like a common manifestation was that images on a page would load swapped like in the wrong places because the responses came back in the wrong order。

 my guess is that this was basically because it was tricky to adapt existing multi-threaded proxy servers to do pipelineing and people just got it wrong but that's just a guess。

😊，And the second reason was what's called。Head of line blocking。What's head of line blocking？



![](img/91a6a99e14072f17cc85ed9804f242d7_23.png)

I'm glad you asked。So imagine you're downloading six objects using two persistent connections over here on the left。

So you request one on one connection， you request another on the other connection。

And the one on the first connection finishes quickly。😊。

But the one on the second connection turns out to take a really long time。

 like maybe it ends up actually being a big object， not a small object， many packets。

 not just one packet。Um， and so while it's taking forever， all four of the Roman ones finish。😊。

Now with pipeing what do you do so you'd send three at once over here on the right in the first connection and then on the second connection you'd also send three at once。

But。The first three finish really quickly on the first connection。

 but that pink one still takes a really long time and that means that the other two also take a really long time so with persistent connections you know five of them finished fairly quickly and one finishes slow with pipeline connections three finish very quickly but three finish slow and so because that's you know because the slow one at the head of the line blocks the other two and it turns out that this issue can like make user experience worse。



![](img/91a6a99e14072f17cc85ed9804f242d7_25.png)

And so。The other reason。Is head of line blocking basically saying small requests get stuck behind big ones？

HTTP2 replaced this with a technique called multiplexine which is sort of like connections inside connections。

 they had much better results with this， they've improved even further in HTTE3。😊。

So kind of summing this up。A single connection per small object will absolutely destroy the performance as Rtts dominate and those Rtts really do add up just looking at this here。

 you know I said it was 30 milliseconds to Google Berkeley from where I am www。

 bekeley is 50 milliseconds。😊，And you know， we know from the DNS lecture that that's through Amazon web services。

 if I access Berkeley directly by going to like the Es machine， I get 30 milliseconds。😊。

University of Massachusetts across the country that's 100 milliseconds that's if I go to a CS machine at UMass。

 if I go to www。ummass， I get 25 milliseconds， anybody got an idea of why that is all the way across the country 25 milliseconds。

 how is that possible I'll give you a hint and it's something I've talked about already today。😊，Yeah。

 CDNs， it's Akamai Akamai serve their main site。U。University of Sao Paulo， Brazil， 300 milliseconds。

 so you know，  80 round trips at 300 milliseconds that to be 24 seconds to load CNN if that's how things worked。

 luckily they don't。Um。So things you can do about it。Our concurrent and persistent connections。

 pipeline connections and combinations of those， though pipelines aren't actually used today and。

You knowAgain， I'm ignoring multiplexed connections。

 though those are also used today for some traffic。A final question here。

 why doesn't this apply to large downloads， it's because if the transmission time dominates。

 the only solution is to get more bandwidth essentially。😊。

And so the next thing I was going to talk about was that thing I said I would hope to come back to but didn't think I'd have the time so I don't have the time so we got like a minute if anybody's got any any remaining questions here。

😊。

![](img/91a6a99e14072f17cc85ed9804f242d7_27.png)