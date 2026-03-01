# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P14：-14-Lecture 14_ Information Security - GPT中英字幕课程资源 - BV1D142147he

![](img/303795b8de776c7d95d4db424884c367_0.png)

Alright， let's get started。 So today we're continuing talking about networking E things and we're going to be talking about information security。

 So last last class we talked about if you're trying to build a service。

 how do you make sure that service stays up and stays available。

 even as more people begin to use it Today， we're going to be talking about how do you keep information safe and sound。

 How do you prevent attackers from getting into your system and and stealing sensitive information。😊。



![](img/303795b8de776c7d95d4db424884c367_2.png)

This really could be an entire class by itself。I don't even feel justified saying that today's lecture is a high level overview because that implies that you give a sense of everything in the area and really we're just going to be able to talk about a small slice of the topic from the perspective of network system design。

And just really quickly， sorry for the interruption， I just realized I did not start。

The recording on this thing， so。Just to give you a refresher on network systems from last class。

 usually you in a network service， you have a server and the server listens for connections on the internet from one or more clients。

 so it just waits until somebody connects to the port that it's bound to and then it can start talking to that other computer and usually。

What happens is I mean the way that we've been talking about this so far is you just get a file descriptor on both ends and the two computers can send bytes to each other by writing to and reading from their file descriptors and that's really how it works under the hood。

 but we would rather not think at such a low level at the byte level of communication it would be a lot nicer if we had more formal and consistent ways to talk about things and usually the way this works is the two servers will speak some predefined language with each other and we call this a protocol。

So a very common protocol is HtTP like whenever you go to a website。

 your browser is speaking a well understoodtood language called HTTP。

 it's talking to the server in a format that all HtTP servers understand saying，Hey。

 please load me this page and then the server knows how to interpret that because they're both speaking the same language the same protocol and the server will go and will fetch the contents of the webp page and then it will write a response back to that file descriptor using a predefined response format。

And that way， the two computers on the internet know how to talk to each other。

This make sense to everyone， everyone feeling all right about this so far？So yeah。

 the server gets the request and sends a response。So let's take a moment to think about what might we need to defend against if our server has sensitive information。

 and I think it may actually be more helpful to flip this question and ask。

 say that you are trying to break into a web server， there is some web server， some HTTP server。

 somewhere on the Internet， or maybe not even HTTP it's just some server somewhere in general。

 somewhere on the internet and you're trying to break in and steal information。

What would be your thought process， obviously most people here don't have experience with doing something like this。

 but if you were approaching this from first principles， what would you try to do？Sure。

 you can start sending requests for random resources and see what happens。

 So there's an element of discovery here。 Like you might not know exactly what the server does。

 You might not know what all the paths are。 And so maybe the server。

Response to certain kinds of requests in a way that exposes information。Any other ideas？Yeah， so。

You've mentioned this term called denial of service and denial of service just means that you are denying service to other people。

 usually by taking the server down or by making the server so busy that it can't respond to other people。

And denial of service is a very important topic it's a little bit different from information security because you're not really extracting information out of the server you're just taking it down for other people。

 but that is definitely a concern You also mentioned phony requests and that definitely has something to do with with information security How might sending phony requests be helpful。

That's a really great idea let's try to find some way to mimic to be an imposter for somebody who does have permission on the system there are a number of ways that we could do that。

 it kind of depends on how the system is set up and like how it's designed to communicate maybe it's as simple as like figuring out the username of an admin and then just sending a request and say hey I am this person and if the server is not very intelligent it might not verify that you are that person。

Back to this idea of like sending phony requests or invalid requests。

Another thing you can do is you can try to send an invalid HTP request we mentioned that the client and the server are supposed to talk using this predefined language called HTTP。

 but what if you deviate from HTTP a little bit and you send something that kind of sort of looks like HTTP but has syntactical errors in certain places and it may be possible to send a malform request in such a way that。

Induces a buffer overflow on the server if they haven't done their HTTP parsing correctly。

 that's really just string parsing if they haven't done their string parsing correctly。

It's possible that they might have a buffer overflow。

 then you can exploit that and get remote code execution on the server so you can upload whatever code you want and the server will run it as if it were part of the servers program。

 That's another way that that you might exploit this。

So we came up with a couple of different strategies and these vary significantly in how difficult they are to do。

 like it's probably a lot easier to send random requests to poke around to see like what is on the server than it is to try to engineer a buffer overflow exploit。

 a latter of which is actually very， very hard。So I think about this。

 like if you're trying to secure a server， I think about this in three steps and three different levels。

 first of all， don't give information to attackers that ask nicely if somebody knocks on your front door and says。

Hey， what's your Social security number， you probably shouldn't give it to them and the same applies for network services。

As a baseline that everyone should meet， we should definitely not be giving sensitive information to attackers that ask nicely。

 we also need to make sure that any dependencies of our system also do not give information to attackers that ask nicely and then the final step which is the hardest step is making sure that you don't give information to attackers that don't ask nicely if somebody sends you a malformed HTTP request intended to cause a buffer overflow we want to make sure that we're also not compromised there。



![](img/303795b8de776c7d95d4db424884c367_4.png)

And I'll talk about each of these steps in much more detail。So as a first level。

 don't give information to attackers that ask nicely。



![](img/303795b8de776c7d95d4db424884c367_6.png)

To to recap like this is what HttP requests look like you send a request so you write some bytes in a specified format。

 so for example you want to get some path like whenever you go to HttP colonhoname。

com/ssecret/s What's happening is your browser is sending this request in this format and then the server replies with some response and say that this is some like restaurant server that has recipes and the attacker just asks like hey。

 what is your super secret sauce and then the server responds。

 oh it's MSg and it has just given away whatever secret was stored on that server the attacker didn't even have to do anything it really just ask nicely。

No one would be this silly。Right。Attacks never look like this。Right？We hope。Um， so Panera。

Perra's mobile ordering app actually worked like this。

 you could have an attacker that would send a request to foundation API/lashuser/ URA s some user ID。

 so a user ID is just some number and the server responds back with all of the information that Panerra has about this user ID。

 including their email addresses， their phone numbers， their food preferences。

 and a bunch a bunch of other information， and this is really bad。

 especially because these numbers happen to be sequential。

Every user that signs up on the system gets an ID that is just the next integer and so you could trivially just enumerate every number and download their entire database that'd be a very。

 very easy thing to do just by asking， say，Hey， can can I get this user's information？

And I think this is this particular incident was a very good case study in how not to handle a security breach。

 it went really badly， I've heard of worse but but this one was pretty bad。

 blew off the security researcher for eight months。

 he kept trying to contact them and they actually called him a scammer and said that they didn't want to do business with him。

 not that he was asking for any money or anything， it was just saying， hey。

 I have this vulnerability information and they thought he was lying。

And then so he ended up getting frustrated and so he went to the press and said， look。

 this is ridiculous， there's this clear exploit， and within two hours of him going to the press。

 Panera announced that they fixed the issue and only 10，000 users are affected。If you look at this。

Number in this request。That that's that's what 7382194。 That's a much bigger number than 10，000。

 And so not only did they lie about the number of users affected。

 but they also did not actually fix the vulnerability they closed this one API endpoint so we call this an API endpointlash foundation API slash users URA is called an API endpoint It's just a particular path prefix that you can ask the server for information about so you can pass this endpoint the number7382194 and it will return you information about the specified user so they fixed this one API endpoint。

 but it turns out every other API endpoint in this application was designed the exact same way and in fact there were other applications as well including their enterprise catering app which had a lot of corporate data that had the exact。

Same design。If you want to read more about it， there's a good write up from the researcher that found this issue here。

 And as a side note， I'm not trying to pick on Panera。 This is definitely not a。

 as you'll see throughout this lecture。 this is not a panera issue。 This is an issue that is。

Rampant throughout all of industry and that's part of why we're teaching this class is we want you to know what you're up against and to know the different kinds of issues that are very common out there。

So how do we do this properly， there are two principles in security called authentication and authorization。

And they sound similar， they both start with A， they're both just as long and hard to type。

 but they mean subtly different things， so authentication means who are you。

 like who is talking to this system？And usually authentication is established by supplying credentials。

 for example， like you tell the server， hey， I am some username and here is my password to validate that I am me。

 to prove that I am me， or you give some like two factor authentication token or you provide some secret key that only that person should know and that's authentication。

Authorization is talking about， are you allowed to do what you're trying to do？

So once you know who is talking to your server， you also have to verify that whatever it is that they're trying to do。

 they're allowed to do， maybe in this like customer data example。

 authorization means that if we know that you're a particular user， that's cool。

 we're only going to authorize you to access your own data。

 you shouldn't be allowed to get the information of other customers on the system。

And this is established by some policy， so for example， like you can access your own emails。

 but not emails of other people。And if you want to have a secure service， you must establish both。

 you can't have just authentication and it doesn't even really make sense to have authorization without authentication because you really don't know who you're talking to。

 so you need to have both and I'll give some examples of what happens when you have one but not the other。

So commonly what this looks like in practice， just to contextualize this authentication and authorization thing。

What this often looks like in practice is you have a client and a server。

 the client makes some request and it passes some authentication tokens， so for example。

 a username and a password。And the server might respond and say， hey， great。

 next time you want to talk to me。Use this random token。And the reason that。

I'll come back to this in a few bullet points， but the reason that we use these tokens instead of like every time the client talks to the server。

 the client could pass the username cactus and the password ply。

 but the reason that we prefer passing these tokens instead。

Is because we want to minimize the number of times that that those credentials get set over the network。

 We also want to minimize the。For example， like say that you log into a website and you type your username in your password。

 The browser is going to need to send many more requests in the future。

 but it would be ideal if the browser didn't need to hold onto to your username and password。

 like you only type your username and password when you're logging in and then after you're logged in the browser just forgets your username and password to try to it's not stored in a global variable or anything to try to reduce the possibility of programming error。

Also makes it so that you can expire the token， which is helpful。

 so it might expire after two weeks or something like that。Then the client says， hey。

 show me emails for user cactus， here is my token and when the server gets this request。

 so this is an authenticated request。It has a token the server first has to validate the authentication so it has to validate that ABC 13 is a valid token and has to figure out like who it belongs to so it has to look up in a database of tokens and say oh I gave this token out to cactus so we're talking to cactus and then it has to check authorization so it knows it's talking to cactus it has to make sure that cactus has permissions to see emails for cactus which by a sensible authorization policy would say yep。

 that's fine and so then the server would respond and say here are the emails for user cactus。

And this is very， very often how things will work if you look at web applications and you look at the requests and the responses that happen。

Does this make sense to people？Any questions about this so far？

So just to highlight the authentication and authorization here。

 authentication clients must demonstrate their identities。

 so that's the username and password being supplied here。And authorization。

 the server has to verify that the person that they're talking to actually has permission to do what they're asking to do。

And I mentioned like you don't have tokens， it would be possible to just pass the username and the password for every request。

 but we would like to avoid having to remember the username and password and also we can expire tokens after a week and have the user log in again。

Oh， if you've heard the term cookies， that's a very common term in web programming and like browser land。

 cookies are tokens， same thing。All right。That's authentication and authorization。

 Let's look at what happens when you。Acciddentally or intentionally omit one or the other。

 Panerra was an example， by the way， of a complete lack in authentication。

 None of those requests were authenticated。 You did not have to provide anything that indicated who you were。

 And so there was no authentication in that picture。

Here is a less egregious example that came up three weeks ago。

So last week we talked about clusters of machines and if you have a cluster of 1 thousand00 machines。

 you can imagine it would be very difficult to manage all of those。

 it's not really practical to SSH into each of1 thousand machines individually to perform a system update or to check if it's overloaded do monitoring things like that。

 So saltt is a product that it's a systems administration product that lets you oversee these large clusters of machines and you can have a bunch of nodes in a cluster that will check in with this master server so they'll send a request to the master server and they'll say。

 hey， here's my CPU usage or like here are the processes that are currently running or something like that。

And you can also have a system administrator that contacts the master server and says， hey。

 please update all of the servers to version 10。This master server has an internal queue。

 so it'll add that message to the queue， and then it will broadcast eventually that message to all of the servers saying。

 hey， please install version 10。Does that make sense？

And I should mention that all of these requests that I just showed are authenticated and authorized properly。

 so there's nothing wrong there。What is wrong is it turns out that。

If you happened to send a request indicating this underscore sendend to underscore P function。

 and in this request you said， hey， install a Bitcoin miner and kill SSH on all of the Minon servers。

 on all of the servers running under this master。嗯。

And you didn't provide any authentication or authorization。

Then the saltt master would happily add that message to its job queue and then it would send that message out to all of the servers。

 This is a total accident like this is not supposed to happen。

 SendPub is a function inside of the master server and it's a function that gets called when the system administrator sends something like please update the servers to version 10 so it's supposed to be a private function and that's why it's called or that's why it's prefixed with an underscore but somehow I don't know how I haven't actually looked at any of this code somehow they created a mapping so that that function could be called by a network request。

And I forgot who mentioned this at the very beginning。

 somebody mentioned like just send a bunch of requests and see what you can find this is the kind of stuff that sometimes comes up like nobody intended for this to be callable from a network request。

 turns out it was and turns out that you could ae arbitrary messages that are sent to these servers。

So what happened Well， three weeks ago， entire clusters started becoming unreachable like many companies。

 all of a sudden they could not be reached， you couldn't SSation。

 their servers went down and what happened is many of those servers were targeted with Bitcoin miners and a backdo that allowed the attacker to get in and take data out although I'm pretty sure it was just a Bitcoin mining attack as far as we know。

 well I mean this is only three weeks ago， so actually we we really don't know much yet but。

As far as I know， it seems people were mostly interested in Bitcoin mining and not in harvesting data。

But this happened and and this is huge pain in the butt because first of all。

 you can't even get into the servers right now。 And then once you do get back in。

 how do you verify that the attackers aren't still on the machines If they control the machine and they have root access。

 they can set up a facade that looks like they're not on the machine when， in fact， they still are。

So this was very difficult if you want to read more about the attack， here are some more links。

 but this happened three weeks ago and it was not a purpose。

And it it just so happened that like somebody made a mistake， there was an accident and one of these。

 these network endpoints was exposed when it shouldn't have been。

What happens if you don't have authorization， so you do have authentication。

 but you don't have authorization And to give you an example of this。

 there's a company called Lo Smart。That you probably have never heard of。

 but what location smartmart does is they partner with every US cell carrier and they know the location of every single cell phone on these carriers in the US。

 and they sell this location data to law enforcement to marketing agencies and to companies wanting to track corporate devices。

And you can't opt out。 It's not like your cell phone is providing information to location smart or to your cell phone carrier for that matter。

 The location is computed by cell phone tower triangulation， so you can't really opt out。

 So this is a major issue and it affected pretty much everyone。

This company provided a demo on their website so you could type in your contact information and your phone number and then。

It would send you a text message where you have to like click a link to verify that yes。

 I do want my location to be exposed for this demo and then it will show your location on a map on a Google map so it'll put a little pin and you can see you can verify that yes。

 apparently they do have your location I honestly don't really know why this was considered to be that helpful。

But they just wanted to show like， yeah， we， we do have this data， we're legit， whatever。

 not really sure this seems to me like a bad idea from the start， but。

The way that this worked was your client so your browser when you go to this website and you say。

 hey， like I want to sign up for this demo， it sends a request to the server and this is what the request looks like in particular it says the phone number that you want to get the location of then the server respond and it has a bunch of information two fields that I want to highlight are this privacy consent required true field。

So it's basically saying that in order to get the location for this device。

 we are going to send that device a text message and it has to confirm that it wants to have its location shared。

 and then it also returns this random token。And that token is used for authentication。

So then the client， I just shortened this because I needed the space。

 so then the client sends another request that says， get me the status of this phone number。

Like has it accepted the request yet and the server will say nope actually it hasn't requested or it hasn't accepted the tracking request yet subscription not active。

 and the browser will just keep sending this request over and over again。

It's effectively busy waiting。And so it will try again and it will send that request again。

 and after doing this a couple times after the user actually accepts this thing on the phone。

 the server will respond and say，Yep， they opted it in and you can ask for their location now。

So I'm going to shorten this and then finally the browser now knowing that the device has accepted the request。

We'll send a request saying， here is my token， I want to get the exact address for this particular phone。

And then the server responds saying okay， here's the location data and it response in XML format。

 I couldn't actually get the response This is taken from the blog of the person who discovered this issue and he just omitted the final response body so I don't have the actual data but it just responds with location data in XML format。

This makes sense。So what is the problem here？嗯。This actually is okay。

 so let's say that you omit the middle request， you just skip that step。

 so let's say that you do the request， you like ask， hey。

 I would like to track this device and then immediately you ask for the device's location。

The server will respond with an error if the user hasn't consented。

 so if the person hasn't accepted that text message saying。

 like do you want to share your location with this demo application。

 if they haven't consented then the server will respond with an error as it should。

So this actually works。As designed。 But if you change this very last parameter。

 So before it was L OCRQ location request， if you tack on a dot Json。

Then it responds with location info in JSON format， regardless of whether or not the user consented。

So in response， I honestly don't know why they designed it like this。 first of all。

 it's a little bizarre that they're using both JSON and XML for those who aren't familiar。

 JSON is just a way of like structuring a bunch of information。

 XML is another way of structuring information They do the exact same thing。

 I don't know why they have both。But they do and if you change the format。

 then they just skip the authorization checks， so they're still authentication here like you still need to supply this token to say。

 hey， I am the same person that requested this location to begin with。

 but it doesn't even check that the user has consented via the phone。

Which seems like a big issue and。I mean， this affected everybody that has a phone in the US。

And it was almost certainly a bad case of copy paste。

My guess is that they implemented this JSO thing first。

And then they changed it to XML so they coped and pasted the code for this endpoint。

 and then they were like， oh wait， we forgot to add authorization checks。

 so they added it to the XML endpoint and they forgot to add it to the JSO Endpoint because they weren't actually using it anymore。

嗯。ItBggles my mind why some of this exists。But it does anyways。

 so it's probably a bad case of copy paste and iss trivial to exploit I mean I just showed you exactly how it works there is a really good technical right up here and if you want to read more about the context and the aftermath there is a good link as well。

嗯。Do I have any anything else？嗯。Yeah， so so if you want to read more about it。

 there's there's some information there， how do we prevent this from happening。

 I think this is maybe the more important question。So the standard approach。

 one that you'll see very often is you use a web application framework。

 so when you're implementing these applications， you definitely should not be reading from the file descriptor directly and then doing some processing that's very low level and we would rather have a high levelvel library or framework for dealing with this。

And usually what you'll do is you'll use a framework that manages all the HTTP requests for you and the responses is for you。

 and you just say， hey， when a request comes in for this API in point for this path。

 call my function here when somebody comes in for this path， call this other function。

 when somebody comes in for this path， call some other function。

 and you can figure this framework so that for every single request。

 it checks authentication and authorization before calling your application code。

That way you can't make a mistake， there can't be a copy paste bug where you have checks on some requests and not on others because the framework is programmed to do these checks for every single request no matter what。

 and then it calls into your application code。So this is pretty effective。

 there are still sometimes mistakes with this， but if you many of these mistakes are caused by copy and paste and if you do it this way to minimize the amount of copy and paste。

 then you minimize the potential for error there。There are also some more experimental approaches using type systems。

 sort of like how rust ensures that you never forget to lock a lock or you never forget to free memory。

 There are some approaches with with making sure that at a language level you never expose information to endpoints that aren't verified and。

And you like take take incoming input， you make sure that you validate that input before doing anything with it。

 and hopefully we'll have a talk on this later in the class。Everything makes sense so far。



![](img/303795b8de776c7d95d4db424884c367_8.png)

All right， I never know how far we'll get with these slides and looking at the time right now。

 it looks like I prepped a little too much information so。

I may skip some slides in this next section， but we'll see how we do a time。



![](img/303795b8de776c7d95d4db424884c367_10.png)

All right， so this is a diagram that we showed last class and this is how many distributed systems are architected and a key thing that I want to point out here is these servers have IP addresses too not only do you need to make sure that your compute nodes。

 your application servers you have to make sure your servers don't give out data to people that ask nicely。

 but you also need to make sure that your dependency servers like your database servers also don't give information to attackers that ask nicely if attacker finds your database and goes to it and says hey。

 please give me all of your data and the database says sure， no problem here you go。

 that seems like a really big issue。And we should try to address that。

And to give some concrete examples。This happens with all kinds of database servers。

 but just to name one， there's a database called Elasticse and it's very popular because what it allows you to do is you can just dump in any kind of data。

And it will analyze that data for you， you can run arbitrary queries on that data。

 so it's very commonly used for application search for website search。

 I mean search is in the name that's really what it was engineered for。

 but it's also sometimes used for metrics， analytics， visualization。

 anything involving heavy data processing。Very commonly used。

And the reason is because it it's so easy to do pretty sophisticated things with。

 you can just throw up a cluster and as data comes in。

 you just throw it in the cluster and then whatever searches or analytics or queries you need to run。

 you can just quickly run it on all of the data。So the default settings for Elasticse are that it will only respond to local connections you install Elasticse on a machine and you can only talk to Elasticsearch on that machine really it is like binding to a port。

 but it's only responding to clients that are coming from the same computer。So it's。

It is using networking， but it's not really talking to anything outside of your own machine。

 it's like networking at a very， very， very limited scope if that makes sense。

Which is a problem if you want to use Elastic searcharch and cluster like the diagram that I showed because you need to have other machines talk to the elasticastic search machine。

So what do you do， you just change the configuration so that it accepts external connections。

Does this sound good to people？Because what do you do is you just put the server on the internet and it's accepting connections from anybody and literally anybody can connect to the server and ask whatever they want and。

And this happens all the time， so I Googled Elasticse data breach and I was expecting to find like a handful of articles。

 but actually like every single link on this first page is a unique data breach。😊。

A different data breach，5 billion records，1。2 billion records，1 billion，57 million，15000。As see。

Is there。Everyone in Ecuador。What else is here？m let's keep going， okay。

 250 million Microsoft records， I think these were customer support， yeah， customer support records。

Let's go to the next page， 24 million credit in mortgage records that also sounds pretty bad。

Pretty major breach。 I don't remember what the details were here。

 but like it's not hard to find these breaches happens multiple times a year。

 and one that I just found out about， I think last week， if I remember right。

So this is website called have I beenponned Awe website you should sign up if you haven't heard of it before。

 it just sends you an email whenever your information gets found in an online data dump I it that helpful I don't know。

 you can't really do anything about it I mean it just sends you an email saying like hey you're screwed but but I mean maybe it's nice to know about I don't know so last week I got an email saying that my data was compromised in a company's data breach that had 103 million records it's pretty big breach。

And。The big twist here is we actually have no idea which company it is。

We have absolutely no idea where this data came from It was found on Elasticse instances on the internet。

 nobody who has any idea who it belongs to or like what kind of cluster it's part of it's just there it's a public IP it's totally accessible and we don't know whose it is so it includes a lot of information including random stuff like recommended by Andy arranged for a carpenter apprentice Devon to replace bathroom vanity at some street address on some date。

Kind of bizarre， again， like based on the data inside， nobody's been able to figure out。

Where this is from。If you want to read more about it。

 there's a really good link here that talks about this breach。

It's all kinds of these breaches centering around Elasticse and you might be wondering like。

Why like there's got to be something wrong with Elasticsearch right Well Elasticsearch says hey this is not our fault these breaches are caused by a poor understanding of security and how the software works and if you if you remember the default setting the default settings is actually secure like by default the database will not respond to external connections。

But what do people do， they actively configure their installations wrong so that it just responds to anybody on the internet。

 like people are actively shooting themselves in the foot here。And really。

 I'm picking on Elasticse here just to provide one example。

 but if you Google any other database technology， S3 is probably the next biggest one that comes to mind。

 just Google S3 Data breachach and you'll find horrifying things is pretty interesting。

So is this elastic search fault if we had more time I would love to talk more to have your thoughts about like why do you think this happens。

 but here is my opinion， here's why I think this happens。

The first reason is bad default settings I think we've made a lot of progress here。

 but commonly databases have a default username and password and they don't require you to change it and this is true of Elasticse。

 so if you can find a database exposed you probably know its credentials because people were too lazy to change the username and password。

MongoDB is a really popular database that used to have horrible default settings。

 it used to be configured to accept all connections by default， which is pretty bad。

I think we're slowly getting better at this like MongoDB doesn't do that anymore。

 a lot of MySQL MySQL is another common database， a lot of MySQL installation tools will require you to change the default username and password。

 but we're definitely not all the way that this is still an issue。

There's also the issue that Elasticsearch pointed out so this is the issue that they blame that they put the blame on they say that it's the fault of engineers and system administrators there are people who are running the systems who have no idea what they're doing and they say。

 hey I need to access my database from a different server so let's just open it up to everybody and and I think this is really a systemic problem this is true in many places in industry where。

Where companies will prioritize shipping new features and making new releases rather than making those releases secure。

 right if you develop something and you spend a lot of time trying to make it secure。

Probably most people won't be able to tell it's going to look the exact same to somebody using this application。

And so security is often not rewarded and it's tacked on as an afterthought。

And and I think we've been making some progress here。

 maybe there's certainly more legislation coming out like California recently passed a pretty strong privacy and security law that that was supposed to。

Comp with the EU's legislation。 but we really have a long way to go here。

 and I'm not really sure that。We're becoming better as engineers in general。The last problem。

 I think， and I think this is the most interesting one。

Is we've designed systems where the path of least resistance is bad security。

Like if you want to design a secure system， you need to design it so that it needs to be harder to do things wrong。

than it is to do things right， because people will always choose the easiest option when they're using your system。

 If you're designing a database， you have to design it so that it's harder to screw up than it is to do things right。

 And I think in many ways we're just starting to think about this。

 This is a new area of development and there's a lot more work that needs to be done in terms of figuring out how to design systems that are secure by default。

So what can we do about this， like how do you avoid these issues if you're running a big service。

 Microsoft was in there， there's so many high profile companies with security teams that were breached by silly breaches like this。

If you run a big company and you have resources and you have sensitive information。

 you need to dedicate resources to regularly testing for things like this。

 You can set up automated scans。 I worked at a company last summer that does this as a service so they will contract the companies and they will try to find all of the servers that that company uses on the Internet so that they can find like hey。

 you have this Amazon S3 bucket that looks like it has your company's information this probably shouldn't be on the Internet and you need to find these things before。

Before malicious individuals do you。You also need to pay auditing firms to try to find weaknesses in your system to actually go and try to attack it so that they can find things like this。

Also， if you're not running a big service， I think there's still a lot of work that we can do。

 as I mentioned， to try to figure out how to improve security for systems that we don't operate like you may not have control over Microsoft databasease。

 but if you're working on the database that they use you can try to figure out how to make it more secure by default。

GitHub for example， has started making some really interesting contributions here。

 they don't actually run people's services， they just host their code。

 and so it's easy to throw up your hands and say like hey。

 there's nothing I can do about this but they thought hard about this and they said are there some creative solutions we can come up with to try to help this problem？

And like one thing that they started doing is they started scanning vulnerabilities。

 they started scanning code for vulnerabilities， and if your code uses a dependency that has a known vulnerability。

 then they'll alert you and submit you a pull request to fix it。



![](img/303795b8de776c7d95d4db424884c367_12.png)

嗯。So that's level two in defending against attackers that ask nicely。

 what about the attackers that don't ask nicely？

![](img/303795b8de776c7d95d4db424884c367_14.png)

So I was going to do a little thought experiment， but。We sort of did that at the beginning。

 if you're trying to hack into a system。You should always try the easy things first。

 like find obvious weaknesses， find API requests that are unauthenticated and or try social engineering Social engineering is remarkably effective like you could send a phishing email you could call somebody up pretending to be somebody else。

Those are are big issues if all of those fail， the next best thing。

So so the reason that I designed the slide this way is because if youre thinking about this。

 most people would jump to， well， if we can't find obvious weaknesses， let's find new weaknesses。

But actually。You can just turn to weaknesses that other people have found like known vulnerabilities in code。

 and you can try to exploit those。Most of the time you don't even have to do any。

 you don't have to spend time finding buffer overflows because there are so many buffer overflows that already exist and people are really bad at fixing them。

So to give you some examples of where this has gone wrong。

Some of you may have heard of this ransomware called Wannary what it does is it just encrypts all of the files on your computer and then you have to pay Bitcoin before you can get your files back fortunately this is one of the ransomwares that actually does still have your files there are some ransomware viruses that will encrypt all of your files and demand Bitcoin payment but they actually don't have the decryption key and so you pay the Bitcoin and then you still don't get your files back。

It's estimated that it caused up to $4 billion in economic damage， it was a huge problem in 2017。

And like it crippled to NHS， it killed， they had to turn away patients because their hospital stopped working。

嗯。And how did this happen， this was entirely preventable， absolutely entirely preventable。

 here's a timeline， so at some point pre 17， we don't know when。

 but the NSA discovered a buffer overflow in the file sharing stack in Windows they didn't share it with Windows so they sat on this bug and they used it to develop offensive exploits for espionage。

In March， Microsoft discovered the bug independently and they released the patch in a security advisory basically telling everyone。

 hey， you need to update to this new version of the software because it fixes a critical security vulnerability。

In April， there's a hacking group called The Shadow Brokers that announced that they stole this vulnerability from the NSA and they published it on the internet。

So kind of questionable。Ethics here， I mean， I guess Microsoft had already patched it。

 but that's what they did。And then people started picking it up and they started using this exploit to develop their own malware。

And in May， that's when Wnary started to spread across the internet。So notice the timeline。

arch there's nearly two full months before it started to spread and it still took a while before it inflicted its maximum damage if we had just updated our systems within a week。

 we would have been totally fine， no issue。There's another breach。That you may have heard of。

From a company called Equifax， so Equifax is a credit monitoring company when you get a credit report。

 your credit report comes from one of three companies that are the credit unions in the United States。

Equifax's data was breached。And。I don't know if anybody knows exactly all of the data that was taken but。

There was a lot of sensitive data on basically any adult in the US with a credit history。

 like if you have a credit history， Equifax has data about you。

 even though you've never shared it with them， like you may have never heard of this company。

But they operate your credit history and so that data was stolen。

What the timeline here like could this have been prevented absolutely yes。

 nobody came up with a clever hack to break into Equifax's software like nobody developed a buffer overflow to try to break into Equifax。

 people were just being opportunistic。So what happened on March 7th。

 Apache released a security advisory for vulnerability in a framework called Apache Struts。

 so remember I mentioned that most web software is built on libraries and frameworks that handle HTTP requests for you。

 this is one of those。But it had a bug， and so they told everyone， if you're using Apache struts。

 make sure you update。Guess who didn't update and then in May。

 attackers started using this vulnerability to get remote code execution in Equifaax systems。

 so they were able to run whatever code they wanted using this bug。In July， so many months later。

 Equifax finally discovered that they're being breached， but they didn't say anything about it。

 and they claim when they finally went public， they claim that they didn't think that it was a very big issue and that's why they didn't announce anything。

 but they sat on this July， August， September for two more months until they finally announced that we've been hacked and。

Their response was really catastrophic。Some good commentary from Brian Krebs on。

How badly they handled this and maybe how they could have handled it better。But yeah。

 if you want to read more about it， there are some links here， again， entirely preventable。

 if they had just updated their software within a week or two of this advisor coming out。

 they would have been fine。So updating might be annoying。

 but being compromised is much worse and you really need to make sure that your systems stay up to date。

 a lot of progress that we've been making is in trying to figure out how to get people to update more。

 more regularly。I think it's also important to try to reduce your attack surface。

 so if something doesn't need to be exposed to the internet， then don't expose it to the internet。

Like if you want to avoid your databases being hacked via these like buffer overflow vulnerabilities。

 then just don't expose the database to the internet if you have a piece of your application that can be exposed only to your ceberries on like a private network。

 then you should try doing that。There are zero day vulnerability， so this definitely is an issue。

 like the last resort here if there are no known vulnerabilities。

 the last resort is defined a brand new one， so zero day vulnerability refers to a vulnerability that is zero days old has just been discovered。

And if you want to stop these kinds of attackers you have to find and fix the bugs before they find them and use them to exploit your system this is actually really hard。

 you have to pay people to find these vulnerabilities and and it can't just be your developers when you're developing you're thinking about how should the system be used when you're trying to find vulnerabilities you need to take the mindset of how should the system not be used how can I abuse this code that was intended to do one thing and use it to do something completely different so you really need to pay people to get into that mindset and try to attack your system and find issues。



![](img/303795b8de776c7d95d4db424884c367_16.png)

So there are ways that companies do that。And it's not just good enough if。

If you are sure that your software doesn't have buffer overflows or other zero day vulnerabilities。

 because again， your dependencies can have vulnerabilities。

So Google established this team called Project Ze whose sole purpose is to just find bugs in any commonly used software this link goes to Project Zero's blog。

 I would highly recommend checking it out it is probably the best technical security blog that I know of there's a lot of really interesting stuff that comes out there and some of it it just goes way over my head but some of it is pretty accessible。

So that's all I have for to if you have questions please stick around and I'd be happy to answer them otherwise we'll see you next Tuesday have a great weekend and congrats on making it through week7。

Yeah， absolutely， I don't know。

![](img/303795b8de776c7d95d4db424884c367_18.png)

嗯。I think that was this last slide here。 Yeah， so heart bleed was a vulnerability in。2014。

 if I remember correctly， that allowed an attacker to send a。So first of all。

 I should explain what is SSL SSL or really TLS is a protocol that establishes encryption over those internet pipes。

 so last week I showed that diagram of like you could write to a file descriptor and like it'll go through these internet pipes and come out the other end。

Well， TLS or SSL， as it's referred to sometimes， is just another layer of abstraction on top of that so that when you send to the TLS stack。

 it gets encrypted before it goes through the Internet pipes and then it gets decrypted on the other way out。

 so anytime you use an HPS website， the data is encrypted using TLS。So how is TLS implement it。

 nobody implements it themselves it's a really bad idea to try to implement crypto yourself。

 it's always a better idea to use somebody else's implementation and the most common implementation of TLS is called Open SSL and pretty much everyone uses it like anytime use SSH I'm pretty sure SSH Open SSH uses Open SSL。

 anytime you use an HDPS website you're using Open SSL。

 but it turns out that I mean everyone realized this in 2014 because Open SSL had a absolutely critical security vulnerability that。

Allowed for reading arbitrary server memory so it wasn't a remote code execution exploit。

 fortunately you you couldn't execute arbitrary code。

 but you could read arbitrary memory and by sending a bunch of malform requests to the servers over time you could extract the entire server's memory。

 including any sensitive encryption keys or sensitive information or whatnot and was especially bad because openSL is also used in a lot of embedded devices that don't get software updates such as routers。

 for example。And so it had a massive scope， everyone uses SSL and it was very difficult to patch。

 I'm sure there are still unpatched devices that are vulnerable to heartbleed。

And the reason I bring this up is because when this came out， everyone realized that holy crap。

 everyone uses open SSL and open SSL is one unemployed dude working like on on his free time。

 There's no team Open SSL is not a company。 There's no paid team working on this thing and it's such a high。

It's such a critical piece of infrastructure that is not really maintained by a company。

 it was just really one person at the time。嗯。Who I think was suffering from health conditions as well。

 So there was a lot going on there and that。If I remember correctly， I could be wrong。

 but I believe that's why Google founded Project Ze。

 I think Project Ze started around that time because they realized that there is a whole lot of open source software that everyone depends on that is not really actively maintained and we should be spending more effort。



![](img/303795b8de776c7d95d4db424884c367_20.png)

Maintaining and auditing this software。