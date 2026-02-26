# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p38 -39-COMP1531 22T2 - 4.2 - 📚 (Part 1) HTTP Servers.zh_en -BV17RXGYuEaM_p38-

Welcome， everyone。 welcomelcome to the largest topic in CO 1531 in terms of a single kind of lecture。

 this is probably one of the few lectures that we will break up over two videosca we have to because you know the lecture stops today。

 and it is on H T TP servers once again。 Quick preface。

 This has nothing to do with your labs until week 5。

 This has nothing to do with your project until week 5。 So you don't need to worry about in week 4。😊。

呃。Which is great。 This is。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_1.png)

For many of you， going to be a really exciting topic， because。

Whilst we sit here and I talk about teamwork and you know project management and package management and all these other things that are really important。

 most students do this course and they think， oh cool。

 I learn JavaScript and I learn how to do web servers。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_3.png)

They leave the course。For many of you， regardless of what I want the priority to be。

 you're gonna like this topic。Web servers are a fundamental part of web based full stack software。

Without going into the。The deep weeds of this topic。The short story is that。

Most things these days that we build are on the Internet。They run on the internet。

 about think about what you use。YouTube， Gitlab， Web CM M S3。What's in your Web browsers。Disord。

 Microsoft Teams， these are all web applications。Even if they don't seem like they are。

 nearly everything is now it's crazy。 So it's a really。

 really fundamental part of you wouldn't call it a part of computer science as much as it's just a relevant part of the world these days。

 So we need to understand it and the things we're going to be talking about are networks in general。

 a little express servers， which is basically jascript web servers or more specifically node web servers。

A P I's is a topic and then crud and， and possibly， I think some testing at the end as well。

 So we won't get very far into。 So if you're feeling very tired， then。Don't worry， we're nearly over。

 So firstly， topic of networks， it's really important to understand these three tiers when it comes to talking about computers and networks。

 because it'll make you seem smart。 Not really。 It's actually just well， maybe， but。

It's really useful to understand what we're referring to。

 So a network as a concept is a group of interconnected computers that can communicate， right。

When you're at home， even when the NBn goes down。You can actually still send files between computers in your home because you're on your your router。

 your land network， whatever you will， because you are on a network at home right and a network is just a broad concept。

 Computers connected together。 Many things are a network。

The Internet is an idea of having a global infrastructure for networking computers around the entire world to talk to each other。

The Internet are computers chat， like you get the you know what the Internet is， right， It's。

 it's just computers everywhere talking with each other。 What is important， though。

 to distinguish is an idea of the world wide Web。 W W W the web。

 And the web is a system of documents and resources linked together accessible via URLls。

Particularly with H T TP stuff。 and you've probably seen this right， Look at this web page。

 H T T P S teaching dot bitflip here， H TT P S web CM M S 3。

 these are all part of the web and the web runs within the Internet and the Internet is a network。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_5.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_6.png)

嗯。Why， why we talk about this is because。What we're learning about Web servers run on the Web。

 Internet servers can be nothing to do with the Web。 Can I give you a good example。

 Who's used Tigerger V and C before。Right， you have it connected to VLb remotely。Right。

This isn't the Web， but it is the Internet， because what you are doing here is that you are actually。

Communicating over the Internet， but you're not using a web。 Basically。

 if you're not using a web browser， it's not the Web。But， you know， sorry， yeah。

 if you're not using the Web browser， it's not the Web， but it's still the Internet。

 That's kind of how to think about it。If you want to know more about networking。

 go and study comp 3331 where they go into that sense of depth。

Network protocols is also an important thing to understand when it comes to networks。

When you communicate over the Internet， you know， we kind of understand the computers are binary machines。

 They're sending binary to each other all the time。 But when you communicate over a network。

 you need to have a certain structure so that everyone can understand you。

 know think about a phone call When you call someone up on the phone that you haven't met before。

 you know hi， you know my name is Hayden， I'm calling about the socks that I ordered that haven't arrived for three weeks。

 know， when you get to the end of the call， they might say。

 you know is there anything else I can help you with today。

 there are certain structures to how humans converse that helps us all get on the same page。

 even if it's someone you've never met before on a topic you know nothing about structures help people understand each other so。

Think of it like standard interfaces， right。 So communication happens over networks that way。

 Different structures are used for different types of communication。

 And one thing we're learning a lot about in this topic about web servers or H TTP servers is the the。

Communication standards of the Web。What we're looking at here。😡，network。Communication protocols。

This is how computers without the Internet can chat。These。

 these protocols are used all the time on the Internet。 They're really common on the Internet。

 and one of those protocols is specific to the web。 That's over here。 HTTP。

 you've seen this all the time。 your whole life， I'm sure。

HtTP is an example of one of the protocols of the Internet or of networks in general。

 and it is the protocol of the web， and it's the primary protocol that's used when you access when you use websites。

 essentially， there are bunches of other things。 And this topic is a mile deep and you can go and learn about it if you want。

 But the point is that there are many protocols when you connect to Vla。 you are connecting through。

I don't even remember。Is B and C et own。 I'm not a networks person。 sorry。

 but I do a lot of stuff with you know， I get my unSW emails over Iap。

 you've probably seen like pop3 imap SmtP to do with emails。

 there are ways that you can communicate over the Internet but not through web browsers。

 You've got SSH is a whole other thing， right SSH is another way of communicating。

 There's just lots and lots of stuff here。 So this is the idea of network protocols。

 And a lot of what we're gonna focus on in the course is the HttP network protocol。

 and that's what we do through web browsers。 These are all examples of like FTP protocols and you know SmtP imap protocols and S protocols。

 these are just different programs and stuff。 But we're really going be talking about the H TTP protocol。

 HtP stands for hypertext transfer protocol。 and it's the protocol for sending and receiving Hl documents。

That was the original intention for it。 Basically， the original Internet was designed for the original web。

 which is part of the Internet， was designed for basically really simple websites。

 It's like if you ever been to Wikipedia or just like， you know。

 gone and looked up like blue fish or Ino， Sure there's a blue fish out there。 blue fish。 Okay。

 you know， blue fish。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_8.png)

It's a simple page， right？ It doesn't feel very interactive。 It doesn't feel very dynamic。

 It doesn't feel like a game。 It doesn't feel like a program。 It's just very， it's like text。

 It's like you literally getting a book on the Internet。

 That was the original inception of into the Internet。 And the idea was quite simple。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_10.png)

You have a web browser。Like Google Chrome， Safari， Fire Foxox， Edge， whatever。

You send a request out over the Internet to a web server and you say， hello。

 I would like this resource。 I would like this thing。 and the web server goes， hm， okay。

 and it does some processing。 and it gives it back to you。We do these kinds of things all the time。

 right， I， I mean， what what would an example of this be。When do you do that。I du'tno。

 I'm sure every time you order food， it's not too dissimilar， right， You're a client。

You're a real person looking for something。 You go to， you， you go to a centralised place。

 you ask for a thing They give you a thing back。It takes time for you to like sometimes you have to wait to ask。

 sometimes asking takes a moment， sometimes they need a moment to prepare the staff。

 sometimes it takes a moment for them to bring it out to you， you know， the Internet is the web。

 I mean the internet broadly but the web is all the same kind of principles。

 you can carry a lot of common sense across。To there。Cool。

 so that's the background on the Internet kind the webb and everything else。

What we're going to be focusing on in this course。Is the Web server part。

 We are going to be building our own one of these。You know， there's a course that CS SE。

 the CSE offers right called Com 6080。 and Com 6080 is where we focus on this。How to， you know。

 building things on someone's computer， making websites in Chrome。

But what we're really focusing on in this one is web servers。嗯。

And the Web server technology that we're gonna be looking at in 1，5，3，1 is called Express server。

 It's a no JS library。 It's an NP PMM library。And it allows us to run our own HTTP servers with no JS。

It's an NPM module， it's really quite straightforward to use and to download。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_12.png)

If you'd like， right。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_14.png)

And we're gonna use some code examples。 But in the， in the simpler sense of it， we can go and。

 we can go and use this ourselves。 In fact， we can go and use this within a typescript repository。

 You don't this is actually this can be be run with Typescript even though you don't need types。

 But all I would really have to do here。 It's honestly very simple。 is that I can go into， you know。

 I've say got my project here。 This。 pretend this is a new project。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_16.png)

I then come along and I say， NP PM install。 you don't want to save debit'cause it's like a product。

 It's not just for you。 It's， it's the actual Web web server that runs in production。

 I've lost my water bowl。I probably went to fill it up and lift it out there。

So I go and install that。And it will go and install the stuff for me like I want， great。Done。And。

Then all I have to do is make a really simple application。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_18.png)

Like。This。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_20.png)

And this can mostly just be copied from the Internet。 And let's kind of dissect this for a second。

 The first line is us， express。The first line is us importing express。

 That should be relatively straightforward。 You've probably done something like that so far in the course。

 The next two lines are us creating an express server。 If you're not sure what this line' is doing。

 think of this as very similar to the prompt sync library that you've probably used in the labs。

 And then the next line is for us to， to set a port。 What's a port。 Let's come back to ports。

 That's a very weird idea。The next line is a little bit of a quirk of express that you can kind of gloss over at the moment。

 That doesn't really matter。 And we'll talk about later。

 The next chunk here is actually the interesting thing。

 which is where we describe how the web server works。

 This is us actually making the Web server do things。 And what this is saying is this is saying that。

When someone tries to access a URL on my web server。At slash， right， which is the root URL。

I want you to call an anonymous function， right， That's kind of why we talk about this advanced function thing。

 I want you to call a function that takes in a request and a response。

 and it simply sends a response of hello world。 And again， there's a lot of stuff here。 That's okay。

 when we use libraries like this。There's always going to be a lot of things that we don't know how they work immediately。

 And this one is just what gives the server a functionality。

 And then this last line here is what actually starts the server。

 It actually starts a server off on a particular port。And that particular port。

 to forget the port for a second。 But that， that's actually what runs the server so that it works。

 And here's the thing， right。 So firstly， just a quick tip for anyone who's watching at home。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_22.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_23.png)

When you connect to Vlab。And this is just a demonstratestrator point。

 You don't have to just specify V labb。 You can actually specify a particular V lab。 For instance。

 I'm gonna connect on and you can't see this here， but。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_25.png)

This is， I'm actually writing this in my thing， it's Vx1。

 so normally they tell you to connect to V lab like this just with this string。

But you can actually connect to a specific V lab server。

cause I think there's like 16 V lab servers by writing in V X 1 dot V lab dot C， And when you。

 when you can know God and stop doing that on sec， they probably change。

 Everything changes all the time。 and I get confused。One second。OhI no。

 they're not letting me anymore。 this surrounds all my plans。嗯。I don'tno。 Some might know。

 Probably no one knows。 That's okay。 We don't really need that。That was a dead end。Yeah。

So the point is， let me take a step back when you connect to VLb。

 what is actually happening when you connect to VLb is that there are like 16 computers sitting in at UNSW and you kind of get sent to one of them randomly。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_27.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_28.png)

And I can tell which  one I'm on， because when I open up the terminal。

 it actually says it right here and it says right here， I'm on V X 8。 And usually I can't change it。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_30.png)

Yeah， I can't do that， but my point is if any of you right now connect to VLb。And you are on V X 8。

 You are You are kind of using Vlab on the same computer as me。

And the way that web servers work is that web servers run on a computer。

 And let me just actually get this express example up。

 Let's actually run this piece of code together。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_32.png)

Right。What do we got， Sorry， one sec。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_34.png)

Let's actually look at this piece of code together。 So if I go into 1，5，3，1 code for a second。Right。

 and let's actually run it。 What was the， was the code we were running。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_36.png)

leave me alone。This is our basic express app。 so let's run it now。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_38.png)

All we have to do is， you know， run this card。NPM run T， S node。Saw slash 4。2。Express basic。

So I'm running the code and let's pay attention to a couple of things about it。

 First thing is that this code doesn't run and finish。

 And that's because the way web servers work is that they actually run as an infinite loop。

SoThere's actually code here kind of running as an infinite loop。

 And the weird thing about why that's the case is because what a web server is。

 Think about it like you're working at a restaurant or you're working at like a fast food window or something I'm sure there's a handful of people who have worked at McDonald's You don't really like turn up to work Run in a second and go home do You kind of come to work and you sit there in a loop till your shift finishes and then you go home and your loop is like stand at the drive through。

 wait for the order， take the order。 do the order， get the next order。 You know what I mean。

 you're just sitting there in a cycle。 So this program is actually really similar。

 It just kind of runs except the difference with this program is it's shift never ends until you tell it it ends So it might just sit here running for an hour or 10 hours or 10 years if you really let it or unless the computer turned off。

And it's actually kind of running on the， the， the， you know， V lab right now。

 And if I open up a web browser because remember that here on Vlab， I'm running a server。

It's a web server。But what I can do is I can open up a web browser like a client here。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_40.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_41.png)

And I can access a particular URL。Which is local host 3000。

 And you'll see that it printed out Hello World。This is really important to。Dissect together。

 because this is a few new ideas， firstly。What the hell is local host。

 Local host refers to the current your computer。 So a bunch of you would know， just through your own。

Existing in the generation of computers that every computer has an I P address。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_43.png)

If you've ever Googled it before， you know， what is my IP， you'll get things like， oh。

 this is my IP address or something， al right。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_45.png)

You have all these like I addresses。CSC probably， you know， what is my IP。

 there's be some IP address here， right， there you go。All these different things and。嗯。

Local host just refers to my I P， like at home。 So it's just saying this computer。

 it doesn't need the Internet。 It's just like home computer。 Then we have this idea of a port。

A port is a really weird and interesting concept， basically the way computers go。Is。

They have a whole bunch of like， you know， again， not to keep going through the drive through window thing。

 but imagine that a port is like a drive through window in your computer。

Your computers like a McDonald's。 Your computer can have like a whole bunch of drive through windows and do a whole bunch of serving of things to different customers all separately。

 right。And we've just kind of picked window 300。 And there's a whole bunch of windows。

 And there's some complicated rules around what， you know， numbers you can and can't use。

 And there's a， there's kind of a minimum number。 And there's kind of a maximum number。

 But in most senses， between 1000 and 50000， you can kind of just make up a number， right。

 Like what's。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_47.png)

What's the number we love， How about。2022。I think I can use that one。 And if I change that port。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_49.png)

Right。And I run it again。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_51.png)

And I go back， oop， sorry， and I go back to my web browser here。

It won't work anymore because the web server is now running on port 2022 like this。Hello， well there。

Right。So it's kind of like， and I could go and， I could go and open up a new terminal and run another one。

 if you want。 So it's kind of like these little slots that exist。

 And a computer only has so many slots。 Now， what's really interesting is if anyone here。

Is on V lab in particular， V X 8 right now， You can go and sign into V lab。

You can actually access this too。Because this isn't on the Internet right now。

 even though it's like a website， it's not on the Internet because you know VL like most computers at home。

 if you just run a web server at home， it isn't just on the Internet suddenly， Vla is no different。

 but you can still access it right， because you're all on the same computer if you've connected to this VX8 here。

But if you're on another V X thing or even watch this， right， Local hostt 2022。

 I can't take that and put it on my。 This is my home computer here。 right， I'm in edge。

 You can see my Windows computer。 It doesn't work。 It's like。

 I can't reach this page because this computer here is at home。 And this。

 this V labb here is in the CSE building。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_53.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_54.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_55.png)

So I can run a web server on one CSE machine and play with it on the same CSE machine。

 but I couldn't do that otherwise。 And if you're on the if you're on if you are all on the same CSE machine as me on V X 8。

 you can run this stuff as well。 you like again， I mean it， if someone's on V X， like， you know。

 let me see if I can connect to oops。I don't know what I just clicked， but let me see if I。

 if I like， for instance， like， let's try this out， let's see what I connect to。 V X 7。

 you can see it there。So， you know， if I open up another one， V X 4， I'm just doing this over here。

 V X 6， I'm just opening and closing the connection， V X 3。Maybe then you have 8。 I think they。

 maybe I thought they had 16。V X 7。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_57.png)

V X 8， look at that。 I got another one。 So I got randomly allocated to V X 8。

And you'll see that if I log into， you know myself here。

In another session of V lab at the exact same time。Right and I open up say chromium。

And I can access now local host 2022， because these two things here。

 this V lab session and the one underneath， they are the same computer。

 So this this is the point I'm trying to make here is that when you run a web server。In this course。

 in development。It is running on a machine。 It is not running on the Internet。

 So even though we call it a web server for this， for the。不得呃。In the sense of development。

 it's all kind of in one place like it' it's isolated So that's just really。

 really important because a common thing that students do all the time is they run a web server on VLb or importantly。

 they run a web server on like VS code SSH and then they open up their own computer web browser and they try and load local hostst 2022 and're like it's not working and it's not working because when you do SSH VS code。

 you're connecting to CSC and you're running the web server and CSC。

 whereas your web browsers at home。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_59.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_60.png)

Yeah， so you just have to kind of have that in mind。

 And that's just important to understand how these things work。

 Jess says if you were logged into different account， would you still be able to。 Yeah， exactly。

 So Kai in the chat and Jack in the chat have both logged in like they're on their account right now。

 And we could send each other messages if I want， right， Like， for example， if anyone's live here。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_62.png)

I doesn't matter'cause they can just read my screen。 But like， if I wanted to。

 I could go back to my code and say， like， hi hi， how are you。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_64.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_65.png)

Like this。 And I could update that。 And I I close my server with control C。

 and then I can run it again。And you'll see that Kai will be able to now if they're on their。

 if they're on the same V X 8 machine， then they can see it too if they refresh the page。Right。

 and it'll come up and it'll say that there。But again， it won't work locally or it'll work here。

 Right， see， different machine， like different connection。

 different like account in a wave at the same machine。 So it's just really important。

 Your server runs on a computer。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_67.png)

Roms on a computer。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_69.png)

Now。We've shown that we can change the port。We've shown that we can change what this does。

 Let's show a few more things before we kind of wrap up a bit tonight and we'll get deeper into it on Wednesday。

But。The ports。2022， the reason we point this out is because when you run your express server。

 And I don't know if if Ka， Ka， if you're listening to me right now， if you could。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_71.png)

Maybe， maybe it's too hard。 But if， if someone here knows how to do this， if you could run an。

 if you could run your own server on port 2022 or port 300， in fact， maybe I could。

Maybe I could do it myself。 So if I'm running this port here on 2022， right。

If I go and open up a Vlab session on Vx5， right， see that Vx5。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_73.png)

And I log into V。 don't worry， Kyle and stuff。 I， I don't think it's necessary If， if I。

 if I go into V X 5。And then I open up a terminal on my V X5 machine， and I go to， you know， 1，5，3。

1 code M2。 and then I run NPM run T S node4 point now。So slash 4。2。Express basic。

It'll work because they're two different machines。Right， now， if you run this at home。

 it's always gonna work because your computer at home， your MacBook， your Windows， computer。

 whatever， it's probably not doing anything interesting。It's probably just sitting there。

 So you're able to use port 2022 or port 3000 really easily because your computer is just not doing anything weird。

 whereas the problem is， is that if you connect to Vx8。

 So let's imagine for a second that I'm here running my server on Vx 8 and then say Ka comes along or someone else and they connect to Vlab and they're like oh Vx8。

 that's so exciting。 And then they log into Vx 8。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_75.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_76.png)

What will happen here。As I'll show you is that they'll， you know。

 they'll be sitting around coding and they'll be like， yep。

 I'm going open this terminal and I'm going to open 1，5，3，1 code， and I'm gonna go into。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_78.png)

When run here it's 4。2 express basic。 And when they go to run that。

 Express is going to complain and Express is going say， whoa， the address is already in use 2022。

 you can't use that。 It's already in use。 And the reason it's in use， you'd be like。

 what do you mean， I'm not doing anything， I'm not running anything。

 And it's because you are running this on the same machine as Hayden as in Hayden's using 2022。

 So if you are kind of testing the stuff on CSC machines， which many of you should。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_80.png)

What you'll have to be wary of is sometimes you run your code like this And it just won't work。

 And all you have to do is really simple。 You just go in and you just go and say。

 I'm gonna change my port to 3000。22， run it again。Works fine。 So in theory。

 we could have many CSE students sitting around。 Hayden over here is running his on 2022。

 and then Kai could be over here running his on 3022。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_82.png)

And they're just two students running two web servers on different ports。

So a web server is just a program。 like a web server in its。

 in its simplicity is a program that runs。That。Liists on a particular computer， on a particular poet。

For a request for information and it gives information back。 That's， that's it。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_84.png)

What we do with Express here though， is that we specify different URLs because with web servers。

 a lot of what conveys the information in URLs and we can actually make many of these for instance。

 I could make another URL called slash1 and that's going to return one and I could make another URL called slash1 slash2。

 I could call it anything and that returns2 and I could make another one called oh my God。

 why is this URL so long， which returns， I don't know you know and what I'm doing now is I'm actually creating a web server Oh yeah so Kai says he's just quickly quick tangent。

In a sec。 So sorry， where was I。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_86.png)

What was I editing。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_88.png)

Oh， right in front of me。 Oh my god， it's getting late。 So what I've got here。

Was I'm running like I've got my web server now has four URLs that it accepts。

 and it gives different input based on each URL。 So if I come up here and I turn my server off and I run it again。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_90.png)

Oh， no。Oh'scause I changed it to 3022 Jesus。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_92.png)

If I change it to this， right， then I run it again。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_94.png)

What you will see is that this server now running on 2022， it will have。

 it will have a URL here for that。 It'll have a URL for slash 1 for slash 1 slash 2 for slash。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_96.png)

Why is this URL so long， You know， So you was was the URL。 Oh my God。 Why is this URL so long， yep。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_98.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_99.png)

So， yeah， it's like， there you go。 It works like this。 And this is， this is based like basically。

 this is what we'll go through in the next lecture where。Which is the extension of this one。

 where we basically just really show you all the crazy cool things you can do with this and building your own software。

 And it's all based on jascript。 this is a jascript library。 It's all just jascript。

 So but just to really round out the example， Kai's actually running a server right now on port 2023。

 So if I was to close my app and maybe I want to away for lunch and I came back and someone started using my port。

 it won't work anymore because Ka's on Vx8 using it。

 Now I'm pointing this out as if this is like a problem you run into all the time like you're trying to get a car park in Randwick or something。

 But in reality。😊。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_101.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_102.png)

Most of it doesn't create a problem at all。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_104.png)

It only really matters if you're using really common ports like 3000， which is the default port。

 otherwise it's unlikely that you're going to run into many kinds of problems with it。嗯。Yeah。

 so that's， that's really the crux of it。 So again， remember， this is just the import line。

 This is the setting up of the app and the choosing of the port。 This line here。

 it does something important， but you just， it's not gonna make any sense explaining it。

 So you need to include that。 And that's， that's really it。

's express is a really simple server library where most of it's just set up。

 And then you just kind of everything that I've highlighted。 You just expand that out doing many。

 many things if you want to。 So yeah， that's， that's about。😊。



![](img/5235cb1364d5cbf0d954368cf2cfbc52_106.png)

嗯。So that's it on the express server。When it comes to next lecture。

 we're going to talk more about APIs talking to the server and building things with the server， too。

We're gonna do a whole bunch of more code examples。 We'll do that in the next lecture。

 This is just a bit of an intro to。Web， Internet and a server like this。 So thank you， everyone。

 for coming along。 We don't need to leave feedback yet，cause we're only halfway through a lecture。

But that's it。 We'll keep going in the next one。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_108.png)