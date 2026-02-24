# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p02 -P02-Lec 02 - Reflection Activity; Ocaml Custom Types.zh_en -BV1zQ27BeEfF_p2-

![](img/8988002a35f2508a39599753650b3add_0.png)

Testing。Is wild。 Hello， folks。 Ho friends。 very quickly， If you need access to the B courses。

 please come up to where。😊，U lovely GSIs R， and we will get you your name and email written down so we can enroll you in the B courses if you're having Github classroom and other infrastructure related things。

 we will go over that。 Do not worry。 Thank you。Very much。So yeah， go ahead。

 We're gonna have about three minutes of sort of flex time here where you can go ahead and come down and chat with the Gsis Other than that。

 we have a very fun and full schedule for us today。 So first quick logistics updates。

 We have heard back from the department that they're willing to raise the enrollment cap。

 So we are gonna have more seats， which is really exciting。 So yeah， it's looking good for that。

 But if you are currently in the situation where you're either waiting for a concurrent enrollment thing to go through or you're still on the waitlist because they haven't actually raised that cap yet。

 please do come chat with the GsI just to make sure that you have access to everything that you need to have access to we want to make sure you have the B courses。

 you have the grades go。😊，Yes， one more thing about waitlisted folks if you have emailed me I have seen your email and I will give you access to the things If not yeah feel free to come to talk to us or come up during office hours and we can get you your access thank you。

😊，So okay， for those first three minutes， we'll have that flex time for you to come chat with the GSIs。

 we'll try to get you sorted out other than that， our plan today is we are gonna go ahead and meet our Gsis they're going to do a quick introduction We will then take some time to reflect on Why are we here Why are we doing here Why are we learning about programming languages。

 Why are we learning about compilers and specifically why are you the individuals in this classroom with lots of different goals and values and needs。

 Why are you specifically here And so that will be our first reflection activity After that。

 we will go ahead and switch back to making friends with O Camel。

 we will finish up the activity that we started last week and then we will go ahead and carry on with one new one I'm going go ahead and fix this battery before I pass things along to the GSs to introduce them and after that we'll be right back do please come up here if you're trying to sort out your course and stuff。

😊，就查到。My direction was start。Ac learning excitement。Alright。

 huge welcome everybody to our second session of programming languages and compilers。

 We are so excited to welcome you all here。 and I'm also super excited today to welcome our amazing core staff。

 These are the folks who actually make this class work for everybody。 actually make everything run。

 We are so excited to have them on board。 and we are so grateful for all the work they do。

 These are absolutely the people who make the class amazing。

 So I'm gonna go ahead and pass it off to them to introduce themselves。

 And then we'll get about our business today。😊，Hello， how is everyone doing。

 Can we get like a thumbs up thumbs mid， a thumbs down is okay， too。Beautiful， yeah。

 welcome to week one， hope y'all are having a good time My name I don't have it。

Can I just speak to any。I'll just speak。 I think it's easier than using the mic。 My name is David。

 use A he pronounce。 Im the head GSI for the course。 I'll get into some introductions later。

 But first， I want to do a fun active learning exercise where we all debug the homework infrastructure together。

 I have been seeing youred posts。 And I know there's been some homework shenanigans。

 So I'm going to ask everyone。 We're gonna try different a few things first， First。

 if you've not already。 Could you go on the course website and click on the homework zero link。😊。

To accept the homework assignment。I suppose if discussing with a partner near you is helpful。

 you can do that as well。You are free to commiserate。嗯。啊，安排。啊。Yeah。

 so I'll just give you all a couple minutes to go through that。Yeah， I do want to say。

 I know it can be frustrating to try and debug like course infrastructure links and all that sort of stuff。

 especially wild semesters getting started and you're trying to like get sorted with your classes and things so I do apologize I was mainly responsible for setting up the website and I am learning。

goes wrong is my fault， everything that goes well is there but yeah。

 it is my first time to assign here at Berkeley， so I'm learning along with y'all and that includes how to set them。

GitHub classroom links。 Yeah， okay， is there anyone who is having issues If you're having an issue。

 if you're getting some kind of error message， please raise your hand。

So if you're still not able to access it， please come down during the five minute break that we'll have at the middle of class and David will still be here and they can talk to you about what we're up。

Yes， is this a question？It was just like a。The course。Yeah， it was working yesterday， you said CS70。

That is extremely funny。 That's very silly。 We'll get in contact with the Es folks。

 But thank you very much for bringing it to our attention。 Yeah。

 any other questions before we keep going。😊，A。Okay， yeah， I think the other thing I wan to。

 I have a few announcements on the infrastructure front。 So first。

 if you are enrolled in the B courses， you now have access to the grade scope。

 We took care of this this morning。 So for all folks who are enrolled in the B courses。

 you now have access if you're not yet enrolled in B courses， we will enroll you and then。😊。

You'll get access to the gradeco after that。 If you have emailed me about waitlist stuff and getting access to the things。

 I will give you access。 If you've not yet emailed me。 You can come up to me during the break。

 You can also talk to me during office hours。 You can also talk to any of our lovely staff。

 we are happy to help you。Yeah， our discussion sections are going to be tomorrow。

 we will have three discussion sections， one at 10 AM，1 at 5 PM and1 at 6 PM。

 The room is available online。 It'll be put up on the website。 Yeah。

 and then also for my office hours， I was just notified of this tomorrows tomorrow's office hours will happen at Cory 531。

 not 5，27。 this will also be on the website。 I'll make an announcement。😊，But， yeah。

 those are my like infrastructure related things。 Any questions about infrastructure things before he moving。

Okay actual course things like I said， I'm David， I'm a third year PhD student in Sarah's lab Like I said this is my first time Ting here at Berkeley and my first time teeing this course。

 so I am very very excited to。😊，Be here with y'all and get to learn together with everyone and get to talk about programming languages。

I guess if we're talking about values today， I'm here for a couple reasons，1， I think。

Like programming is just very sick。 I took basically the same course as an undergrad at UCSD and I had a really really good time with it I think it is very cool that we have like this magic box that you can just kind of like tell the computer what to do and the computer will just do it。

 I think that's very cool and also like you know as compiler developers as programming language developers。

 we get to design and dictate the languages that people use to interact with these things I think that's really sick。

The other part of why I'm here is when I was an undergrad， I was also an ethnic studies major。

 and I ended up interacting with a lot of community organizers as part of that work。

I want to be able to give them the agency to be able to fu with the computer， you know。

 to be able to。Use computing towards ThorNe。Yeah， that's why I'm here， I very excited to meet， y'all。

 very excited for all semester。Hello。Hey。Okay，m sorry。 hi everybody。 I'm Iha。

 I am a fifth year master's student。 so I just finished my undergrad last year。

 I was in USA Statess and I， my research is mostly in theoreticalical cryptography。

 So that's like the mathematics of like securing computer systems。 And I。

 so I'm also GSI office hours will be like on the website。😊。

And I'm happy to chat about anything you want in office hours。 The reason。

 so the reason I took this course。 I took this like last fall is because my best friend was really into programming languages。

 And I was like， fine。 I guess I don't have anything else to be doing。 I thought it was very fun。

 And I'm really excited to teach all of you about like the cool things we'll do with this course today get together。

😊，Hello everyone， my name is Kabiir， I'm a reader for this course this semester。

 I'm a fourth year undergrad studying Es。And I guess the reason I'm here is that I've kind of been into programming languages since high school。

 so I took this class last semester， it was pretty fun and I'm excited to be on the other side of it。

Huge thank you to all of our amazing core staff and again。

 if you are continuing to have any infrastructure problems。

 do come and chat with David right at that midpoint when we have our little five minute break A thank you so much one more round of applause for our amazing course staff。

😊，And with that， apologies for microphone news。 we are now going to get into a little bit of a reflection activity。

AndThis is basically thinking about what are we doing here， why this class。

 and it's totally fine if the answer to that is commion time or a friend was taking it。

 That's an awesome answer， perfectly good reason。But I basically want us to take a time to think about if this class connects to our longer termm vision for the work we want to do in the world or to our goals or to our values。

 I know we talked about some general reasons we might be interested in programming languages and compilers last week。

 But this time it like youd really reflect on what it will be for you。

 and just to sort of jumpstart that conversation。 I'm going talk a little bit about why I ended up taking this class when I was an undergrad。

 and then a little bit about how I've been able to use the techniques from a class like this in much longer term and exciting work in the world。

 So way back when I took this because number one， I had heard that the projects were gonna be fun at the time that was a good enough reasons。

 that was one big one and that was a really important one。

 but I had also started to think about the fact that people I really respected and who I could see needed computation that they were really struggling to use the programming languages and programming tools that they had access to。

 And that seemed pretty weird to me。To wonder about whether maybe we needed new programming tools。

 new programming languages， whether we needed a more diverse range of programming tools available。

 And that got me pretty excited about the ideas of building new programming languages and what it would take to actually implement a programming language。

 And so I signed up for my own compilers class back in the day and had a blast。😊。

And so the reason I bring this up is it's not necessarily obvious， especially with a class like this。

 where much of the time we're thinking about， you know， assembly。

 we're thinking about these extremely lowlevel instructions。

 It can be hard for us to figure out how this might relate to other goals that we have out in the world。

 And so I want to just tell a little bit of a story about how this sort of ended up shaping my own trajectory in computer science land for a long time。

So I mentioned that I was already starting an undergrad to be interested in this idea of making programming more usable or making a diverse range of programming tools。

 That is something that I have， in fact， followed up on long after that class。 And so for example。

 years and years later， I made a programming tool that basically makes it really easy for people to automate web pagess。

 Now， on the first glance that doesn't necessarily seem like something that might connect to values to longer termm goals。

 But it turns out there are a bunch of social scientists and other folks who don't have formal education training。

 who end up really wanting access to large volumes of web data they don't have enough time enough people to just collect that all manually。

 And so naturally enough they want it scraped， they don't have the programming skills to use traditional programming languages to do it。

 But once they had access to my tool they were able to do it。

 And so I'll give an example of one team that I think about a lot that was basically figuring out how to set the thresholds for housing voucher。

And their goal was to help make it easier for low- incomee families to move to high opportunity neighborhoods。

 and they figured out that the census data that's coming in once every 10 years is not actually fine granularity enough to set those thresholds in a way that worked。

 It was really easy to end up with a threshold that was too high。

 and then they couldn't help as many families or a threshold that was too low。

 and then you were actually forcing people into worse housing。

 So there are all kinds of ways that this could go wrong if you didn't have access to fine granularity data。

 And then they figured out that Craigslist apartmentparts com all had the kind of data that would help them actually do this work at a much finer granularity。

And so this is the kind of thing that my lab works on in general is making programming tools that are intended to help folks doing their work out in the world。

 so we're collaborating now with biologists， with journalists， with lawyers。

 there are all kinds of different folks who turn out to need programming tasks done。

 but not necessarily have the formal education in computing topics。

 to use the programming languages that everyone in this room is com use。

AndSo that's one of the reasons that I personally think about compilers and programming languages as something that's really connected to my goals in life writ large。

 So what I'm going to ask you to do is now take about two minutes to just think silent to yourself。

 We are going to get to the stage of like chatting with folks around us。 But for now。

 I just want you to think silent to yourself for about two minutes， jot down if。

Programing languages and compilers is connected to your goals， whether that's your two year goals。

 your five year goals， your 10 year goals， your whole life goals。

 go ahead and take about two minutes to brainstorm that。 jot down any notes to yourself。

 I'm not gonna ask you to share this with the class。 No one's gonna have to shout this out。

 but I am gonna ask you in about two minutes to turn to the folks nearby and chat through it with folks。

 So have something ready to say。 So go ahead and sit in silence for about two minutes。



![](img/8988002a35f2508a39599753650b3add_2.png)

All right， go ahead and turn to the person next to you。

How does this class advancer connect to your goals？いさ。はい弱い。来来。そうです。太明。何兄いや、いつ。要みな。一し。All right。

 thank you everybody for taking a moment to reflect on that I know it's a little bit weird and not necessarily always part of our flow for what we do at the start of a class。

 but I appreciate it。Okay， we are now going to dive back in on our activity that we didn't quite complete last week。

 Are there any questions now that folks have had a weekend to think on it about where we left。

Our activity last week。So if you recall， we had learned about what's going on with ifs and else's。

We had figured out some things about pattern matching。 We had this interesting new match keyword。

 We were figuring out， okay， we can do some things with it that look a lot like ifs and else's and other languages。

 but maybe there's some other stuff going on with it， and that's about where we left things。Okay。

 great， in that case， let's go ahead and dive in on our next sub activity。

 which is we are going to the last left off with this program right we had figured out what was going to happen if we put each of these lines at the end of this program snippet。

😊，And if you recall， what we were doing was first， we read the program carefully。

 We predict what's going to happen。 We commit ourselves to our prediction by writing it down。

 whether that's in the notes app or on a piece of paper or whatever。

 And then if we're ready to actually check it， we can go ahead and open something like O Caml playground and actually find out what's going on。

😊，But our first thing is to make prediction because we are trying to refine our model of what this language is going to do。

 So let's go ahead and take let's take a couple minutes first。

 we'll reflect to ourselves about what will happen with A B and C。

 and then I'll give you the go ahead to turn to someone nearby。 but first reflect to yourself。

All right， go ahead and turn to someone nearby， what do you think？What a good question。

 that is a great question， is indentation going to matter？大十一。For example， is like the education。

Did it make sense or almost like see what。Make your hypothesis and we'll double check， yeah， yeah。会い。

あ那り。All right， let's start coming together。Does anyone want to yell out what you think A is going to be？

I'm hearing ready。 hum， if you think ready。Hm， if you think something other than ready。Same page。

 All right， I like it。 I like it。 That sounds good。 What have we got for B。😊，Okay。

 I'm hearing not sure， hum， if you think not sure。H， if you think something else？well well done。

 team。 that's great。 We're doing great。 We're doing so good。 What do we think for seat。Okay。

 I'm hearing not sure about that either， Huford， hm not sure about that either。

Home for anything other than that。 very interesting。 Well， fortunately。

 we have our answer key in the form of the O Camel implementation。

 So let's go ahead and find out what's going to happen。 So here we go。 We've got this right here。

 That's what we're looking at。 We've got 1，60，1，64。 That was C。😊。



![](img/8988002a35f2508a39599753650b3add_4.png)

呜哇哦。What is going on？ Have we had a mistaken hypothesis about what Ocala is going to do。

I want you to go ahead and turn to the folks next to you and brainstorm what is happening here？

I'm just going to give you a hint about what the compiler is seeing。お。

So this is what this looks like to your compiler。Weird， weird， weird。Alright。

 so this is going to be relevant to our next activity。 So let's try our next little segment here。

 and you'll notice there's something that has changed。😊。



![](img/8988002a35f2508a39599753650b3add_6.png)

I noticed that there's this parent。That there wasn't there before。

 And there's this paren that wasn't there before。 So let's go ahead and do those exact same inputs for this new Read to。

But let's go ahead and notice those interesting new parents that we see there。

Discuss with folks nearby， A， B， and C。Where you said compiler these。在这边。

The indentation does not matter， the compiler is not paying attention to the indentation。

The parenten is basically just like the parenten in math。 right， We're doing grouping。

 We're saying treat this together。Yeah， you can only use Pres for actually two things in Oaml。

 unlike a lot of the other languages that we work on right， so like in OcaMl。

 you are using Pers to make a Tple or you're using it like a mathematical print where you're trying to group things that should go together。

お。そなせご。

![](img/8988002a35f2508a39599753650b3add_8.png)

よししやし。太是我累死。So just to give you a sense of how this one comes out so we can see that the only changes I made。

 I just added those pers。Now it's doing what we like。 So that was a little bit mean。

 I did trick you by having the indentation look a particular way。

 which suggests to our human brains that， oh， this is gonna to be grouped together and then these other things are gonna be grouped together So that was a little bit tricky。

 But the reason I'm doing this。 The reason I'm trying to make you remember this is real soon you're gonna be in front of your editor with an okaym problem an okaym program that is having this exact problem and I'm trying to get you to remember okay what was it we had to change that time So one of the things that you should be doing as you are writing your programs is's over communicating with the compiler saying okay compiler。

 I really want to treat these things together and you can use your parents to group these things right so that's exactly what we've done here。

 we' said okay I really want this case where we're matching a wild card to belong to this broader match that's what I want to be happening here whereas then I want to be done after this parent I want to be done with this match which means that this wild card。

I'ming to go ahead and be associated with that。Match。Yes。I think this question is。

 could we nested even further， and yes， absolutely， is that the question， Yeah， absolutely， Yeah。

 keep it going。Other questions， yes。The question is whether new lines have a semantic meaning。

 this is something that we are going to mess around with a little bit in the next time that were building the course compiler。

 but sort of no， So you will see that if we want to sequence things we are going to be having to use semicoons whereas in many other languages you would use new line to mean sequencing So I think that's the question you're asking is that okay yeah。

Other questions on this， I know it was a little mean of me to trick us and to suggest indentation was going to matter。

Okay， cool， let's get into our next sub activity。

![](img/8988002a35f2508a39599753650b3add_10.png)

And again， I'm going to ask you this time to reflect silently， what are we going to have for Ready3。

 reflect on A， B and C， and then you'll discuss with folks nearby。

If you'all like to see the last one too， I never know if you want to see the last one as well。

All right， go ahead and discuss with folks nearby。是。All right。

 does anyone want to shout anything out for A？I'm hearing ready， hum if you think ready。Oh。

 and uncertain ready， anything other than ready？I've burned you once， but it's okay。

 We're all on the same page。 Yes， I agree。 That should be ready。 That should be ready。

 What do we think about for B。😊，I'm hearing not sure， hum， if you think not sure。H。

 if you think anything else。Yeah， I agree。 That one's going be not short。 What have we got for C。

 What do we think。I'm hearing Not sure。 hum， if you think not sure。H， if you think anything else？

I agree， great job team， you did so good。So now is an awesome time for us to address any questions about what we have learned about matches and pattern matching。

 what are we thinking about here？

![](img/8988002a35f2508a39599753650b3add_12.png)

We feel good， we love pattern matching， we're already all on board。Yeah。Great question。 Oh， wait。

 I think I've understood the question。 Let me see if I've actually understood the question。

 So I think the question is， why was it even okay to have this program at all。

 Maybe that wasn't the question。Okay so。It kind of wasn't okay for us， right。

 So we were in this situation where it wasn't actually going to give us okay。

 let me actually clear out。 So here we can see， like it didn't actually give us what we wanted。

 right， we didn't actually get out what we were expecting to get out by calling it on 160 and 164。

 So in some ways， it really was saying no， we're not doing this。 But in other ways。

 So if we had gone ahead and given what was it 61 c。Oh， sorry， I keep forgetting to clear it。

That would have been fine right so it still would have given us this warning。

 which is talking about what we did wrong here， but it would have still been happy to play ball。

 And that's basically because at the end of the day。

 the programmer is in charge right So basically what okayme is set up to do is to go ahead and look for things that it's not sure you handled right。

 but if the programmer has persuaded themselves right Like they believe that for some reason the only thing we should ever be getting here is 61 C。

 and we're never going to see anything else and the programmer knows this。

 the compiler is going trust you。 the compiler say okay you know what's up if you're positive that this is never going to come up。

 you should go for it I'm gonna to give you the warning but you should feel free to go for it。

 but the warning is saying a couple of things to us right So it is saying one of these match cases is unused right。

Basically， we are going go through the match cases in order and we'll go down the first one that matches。

 And so having a wild card followed by another wild card， we are in fact。

 always going to go down that first wild card。 And so that's what it's saying when it says redundant case。

 this match case is unused。 I it' saying you've got to here。 That doesn't make sense。

 The other thing that it's warning us about。 is， hey。

 you haven't handled something for this outer match。

 You have this outer match where you've only handled the input 61 C。

 and you haven't handled anything else。 And in fact， it even gives us a concrete example。

 It says here's this empty string。 you haven't told me what to do if I get that。

RightAnd so it's not saying necessarily that you have to have a wild card case at the end。

 We'll see some examples soon where we're not going to be using wild cases， wild card cases。

 and that's totally fine。But yeah， you have to be pretty sure you've covered everything for some reason。

Yes。

![](img/8988002a35f2508a39599753650b3add_14.png)

Oh， I think I understand this question。 This is actually about something more like this of do we need two wildcard down here in order to make this play nice。

 No， so the wild card is happy to match whatever you've thrown in there right。

 So one wild card is gonna be totally fine。 Now say you did something we're soon gonna see some examples where we actually instead of using a wild card we'll introduce new names on the left hand side right on the left hand side of the arrow。

 And so we'll say something like a。 And then we might use a over on the other side。

 but we were okay with matching whatever。😊，And in that situation。

 if we wanted to talk about the second， the first item， the second item。

 then we would need to actually go ahead and continue to do a structure like this where we've got the comma between。

And then we would need to match。Does that answer？Yes。What would happen if you。In this example。



![](img/8988002a35f2508a39599753650b3add_16.png)

No。In the very。

![](img/8988002a35f2508a39599753650b3add_18.png)

Or yeah any， oh， this is in this example， what if we put the wild card first， Great question。 Yeah。

 if we put the wild card first， we're going to go down the wild card every single time right because wildcard is happy to take anything。

 And so we are just going through in order。 And then the first one that we match with。

 we're going down that path。I saw another question back there somewhere。Yeah。I love this question。

 So this question is basically， okay， say we went ahead and we added something after here that wasn't a wild card。

 Would we ever go down that， No， because again， wildcard is happy to consume anything。

 So as soon as it hits a wild card， it's going down that path。 It's not continuing down the matches。

😊。

![](img/8988002a35f2508a39599753650b3add_20.png)

downown。Okay， I think I've understood that question。 So I think that question is， if we do this。

 then do we get to go back to the prior match once we're outside of the parent。 Yes， absolutely。

 So this is communicating to Ocal that we want all of this to be treated as a single match。

And then everything that's outside。Will be outside， right。

 So this should not be matchshed with something that's inside。 It should be matchshed for this most。

O。Okay， totally feel free to come up during the five minute break。

 which is going to be our next thing。Other clarifying questions， yes。Go back to the last example。

 absolutely。

![](img/8988002a35f2508a39599753650b3add_22.png)

This is great。 I think I understand the question I'm struggling to copy。

 so let me copy it out of a place where I have it already written down better。

So let's go ahead and try this。 So we have our answer key for us right here。



![](img/8988002a35f2508a39599753650b3add_24.png)

Yeah。Let's go past that。So I think this is about this situation where we have both prior course and current course and what if we want a wild card in one of them。

 what will have。 Okay， great， yeah， excellent question。 Let's find out。 So let's go ahead。

 Do you want the first one to be a wild card。Okay， so let's go ahead and have this be B。

And let's go ahead and put。I'll clear that out。Is that the question Oh， sorry， let me get rid of。

This。Oh， ready through， yeah， good。Yeah， thumbs up， amazing。Yeah。Ohoops。Hang on。 I did have a oh。

What did I do wrong Oh I didn't put in my syntax has been wrong this whole time， I'm so sorry。

 there we go。There， now we got what we should have gotten。

Other questions about how this is all playing together。

 I know match pattern matching in general is not familiar to people who are coming into this class。

 So it's totally fine if you're not with pattern matching quite yet。

 but now is a great time for questions about it。😊，If you added an extra argument， okay， so。

The question might be， what if now I do。This。Okay， great。Oh， okay。

 so I think this is maybe about the， the match。 So let's make a new new。 let's call it just n。

 And then let's have N here。And then let's update all of our matches。 Is that what the question is。

 Okay， great， Yeah， So we are going ahead and just going through and changing it to basically match up everywhere。

 Right， Okay， Mel wants you to be talking about the same thing in all the places that you're talking about。

 the same thing。😊，All right， let's go ahead and take our five minute break。

 David is going to be up here at the front， so if you are continuing to have B courses problems。

 please come talk to them。 Thank you very much。Very sufficient。



![](img/8988002a35f2508a39599753650b3add_26.png)

![](img/8988002a35f2508a39599753650b3add_27.png)

Quick heads up， even though the activities we've been doing on the website are linking to some old tutorials point。

 whatever that thing has been broken， I highly recommend Ocaml。org/ play。

 the Ocal playground instead if you are looking for an in browserser way to run your Ocal snippets I mean okay the ideal is you already have it installed you're good to go。

 you're ready to run it on your machine， but if not this is what Id drag about。



![](img/8988002a35f2508a39599753650b3add_29.png)

Alright， let's go ahead and come back together。 So if we have lingering questions about our pattern matching。

 about this interesting new match keyword， now's a good time for us to wrap them up。

 Otherwise we'll go on to our next Ocal activity。😊。



![](img/8988002a35f2508a39599753650b3add_31.png)

Okay fantastic in that case， quick reminder that if for whatever reason you are having a hard time reading it up on here。

 totally fine， we can also follow this link on here。

 okayL activity too and that will be the activity that we're about to do。

 please feel free to just go to the course schedule and grab it from there if you would rather do that rather than be looking on the projector。



![](img/8988002a35f2508a39599753650b3add_33.png)

But otherwise， we're going go ahead and we're going to start。

 So this time we're doing it without sort of the ABC thing。 But basically。

 we're trying to predict what's going to get printed out for lines 10，11 and 12。

And I would like you to go ahead and first consider it silently to yourself for about 30 seconds。

Please discuss with folks nearby。😀嗯。😊，All right， what do we think for line 10？

Please feel free to shout it out。All right， I'm hearing lid cost per yard 15 hum if you think that。H。

 if you think anything else。I totally agree。 What do we think for line 11？

I'm hearing cotton cost per yard six， hum， if you think that's it。Home， if you think it's not。

I totally agree。 so nice when we're on the same page。 What do we think about that last one。

 What do we think do we think it might be wool cost per yard 18， hum， if you think yes。

H if you think no。Okay， cool。 It looks like we're on the same page。

 So I'm just gonna real quick talk us through what we've actually done here。

 right so we can actually we can see this run。 We can see that that's how it's actually gonna turn out。

 So let's go ahead。 and here's the exact same thing that we've got。

 Let's go ahead and clear this and run it and okay， it came up with exactly the things we predicted。

 So hopefully nothing too shocking here。 But I do want to talk through。

 What has happened here is previously。 We were talking only about types that were built in。 right。

 We had strings。 We had ins。 We have now made a new type of our very own。

 We have made this fabric type。😊。

![](img/8988002a35f2508a39599753650b3add_35.png)

Alright and so you're gonna to expect that you're， you're having to write types with lowercase letters。

 And then we have made these constructors， right， So it's all well and good to have a type fabric。

 But perhaps we might like to actually construct one of those。 And so we've made three constructors。

 We've made linen。 We've made cotton。 We've made wool。😊，And those are the constructors。

 I know these look a little bit different from the constructors as you've seen them written in other languages。

 but this is what our constructors are going to look like So we'll also see constructors that can take inputs。

 but for now these are very simple constructors that just make something of type fabric。

So how are we feeling about this so far， so far， so good yeah？I love this question。

 So this question was how does our our function that we've made。

 How does it actually write cost per yard of fabric？

 How does this know that what we're getting is something of type fabric right we talked about the fact that we have our colon and our colon means has type but we haven't actually written that here。

 We didn't at any point say we are taking something of type fabric So it actually knew because of those constructors that we were matching on So we chose to match with linen cotton wool those were the constructors we used in this match And so okay Caml being very smart for us it was looking at F and it was like okay。

 well， this F thing we're gonna to see if it's linen we're gonna see if's cotton we're to see if it's wool。

 do we have anything that has constructors of that type Oh， yes。

 we do it's this fabric type looks like what we're gonna be getting in is something of type fabric。

Yeah。so。Absolutely， so you can absolutely always use that colon to mean has type。

 You can go ahead and write and。 I want this to only be fabric。

 We're not doing it in this activity because we're doing a bunch of activities where I'm trying to get you to guest types and stuff。

 But yes， absolutely。 And in general， when you are writing your own programs。 I highly highly。

 highly recommend writing those type annotations as often as possible both to communicate to your future self about what you intended to have happening there。

 But also， it's a really good debugging strategies。 So one of the things we talked earlier about。

 include more parents than you think you need include more type annotations than you think you need。

 It is gonna be helping keep you less confused and the compile less confused。

 So it's good for everybody。😊，也需要。I love this question， so I think this is this question。Oh。This is。

Sorry， I'm such a dreadful typer。 That's my main problemm here。 Okay， so let's call this metal。

And we'll have linen cotton wool and silver。Something like that I that the question， Okay。

 so let's clear this and let's run。This pattern matching is not exhaustive。 So in answer， sort of。

 right， like everything is still working。But it says it's possible that this is actually going to be a metal in which case we're not actually going to be getting everything that we are expecting to get。

 So what will happen if instead we do silver。And then let's clear it again。And let's run it again。

 Now it's not going give us that warning。 So that's kind of weird， right。

 because it was happy to run it。 That was fine。 But it was saying， you know what。

 you haven't covered silver because this might be a metal。

Does that answer the original question about overlapping constructor names？I think this question。

 Okay， so right now， I haven't written it with the。Sorry。

 I haven't written it so that we're actually giving names to these。

 in which case we would be able to。Is that the question， yeah。But we could have done it up here。

 right like there are lots of places that we could do it。So definitely， absolutely。Okay， amazing。

 let's go on to our next sub activity。 Again， I'm going to ask you to start by silently contemplating this beautiful program that we have before us。

 and then we'll discuss。😊。

![](img/8988002a35f2508a39599753650b3add_37.png)

Oh， and to be clear， this is all getting sort of appended into the same thing。

 So we're still in the same program where we have access to fabric。

Please go ahead and discuss with someone nearby。大が。也上。



![](img/8988002a35f2508a39599753650b3add_39.png)

![](img/8988002a35f2508a39599753650b3add_40.png)

All right， what do we think？For line 16。Yards for sample。I am hearing one。 hum。

 if you think yards for sample 1。H， if you think something else。Amazing， same page。

 what do we got for that next line， yards for mini dress？

I'm hearing yards from mini Dr four hum if you think that？If you think anything else？

Amazing yards for maxi dress。I'm hearing aid home， if you think yards for max Dr 8？

H don't if you think anything else？Amazing， what about for our final line there， yardss for suit。

 colon。😊，I'm hearing nine， hum if you think nine。I't if you think anything else？Amazing， yeah。

 no tricks here。 this is pretty much doing what you probably expected to be doing。Great question。

 Yeah， so this is actually really helpful for us to work through right because we can see that we have jacket yards plus pant yards here。

 but then we have int times in up here。 but the star actually is not serving as times up here。

 So this is actually the same way that we build up tuples in O Camel。

 if we're talking about sort of the type of the tuple。

 Well talk about the type of the item in slot 0， the type of the item in slot1。

 but we'll connect them all with stars。 This is just using that exact same syntax to indicate that okay。

 we are gonna be taking two inputs into suit。 So that star definitely does not mean multiplication。

 It just means we're putting this all together in something like a tuple。😊，Yes。

 so basically that fabric sample that we're making here where we have no inputs coming in looks exactly like these constructors that we had up here。

 right before we had these constructors where we weren't actually giving any additional information。

 we just had the bare constructor， no data stored with it。

 That's the exact same thing we're doing with fabric sample。Can you make these types of recursive。

 Yes， absolutely。 And I think we're going to see an example by the end of the section sheet。

 although I don't fully remember。 But yes， you can make them recursive， absolutely。Other questions。

 we feel good。Other yeah， no good。 Okay。 All right， let's move on to the next segment。Of the same。

And I want you to contemplate silently for let's take maybe a minute。Sorry about the arithmetic。

Go ahead and discuss with folks near by。If you are struggling to remember numbers from earlier in the program。

 that makes sense， go ahead and pull it up on the activity sheet on your computer。No dumb questions。

Oh。HSa more what you mean about the second half of that question。Yeah， we're doing exactly that。

 right， So we had our cotton， our linen and our wool。 and in order to make something of type fabric。

 all we had to do。就说的。Fabric。I know right， we get to just define our own types it's so cool。Yeah。

Yeah。多アか。太。Utualize with。I mean， it's like some type of thing。No， it's not a subtype。

 It really is about the constructor that was used to create。 Yeah， so subtypes also exist。

 we'll get into that as well。 But no， that is just about the constructor。Yeah。

 definitely if you if you have follow up questions on。Did you have follow up questions？

Starting to feel。Totally fair。Yeah， you can think about how like。Right， like true and false。

Everyone's like， okay， yeah， those are booleans， and there's no data stored with them。

 Those still have tight Boolean。So if that helps for thinking about it。



![](img/8988002a35f2508a39599753650b3add_42.png)

念。All right， what do we think？What about for this line about the summer suit？

Anyone want to yell it out？I'm hearing 135， hum， if you think it's going to print out summer suit$ dollars $135。

If you think it'll be something else。Nice， we're doing such a good job of generating these hypotheses about how it's working。

 Good mental model of what's going on。 Okay， what about for winter su。😊，I'm hearing  dollars 162。

 hum if you think it's that？H't know if you think it's something else？Awesome， okay。

 so you all have developed exactly the mental model that I was hoping you were gonna develop。

 But if you didn't develop that mental model， that's also totally fine。

 So we have this language implementation that can actually answer our questions about what the language does。

 It's all about writing the program that is gonna help us learn the thing we need to learn about the programming language that we're playing around with。

 So this is one of the big things that I'm trying to get us to extract from this activity is that the documentation absolutely like turn to documentation to learn about languages 10%。

 But over the course of this semester， you are gonna to be playing around with a bunch of half implemented languages。

 language implementations that have bugs， languages that you know you have written and therefore are not documented And sometimes you are gonna have questions about what are the meanings of programs in this half implemented language。

 this language that you haven't actually completed yet。

 And you're gonna have questions about what do these programs mean。

 what do these programs do and you're gonna。F out how to do exactly this activity of I think what's happening inside is this。

 let me write the program and then run it and then see what comes out the other aside in order to figure out what's actually happening。

So I'm just going to show us that this program does indeed run and does indeed produce what we're hoping it will produce。

 I also want to draw our attention to one more thing before we wrap for the day。

 which is you can notice up here。Remember from the last activity。

 when we didn't have that underscore that wild card as our last match case。

 we were getting warnings from the compiler。 The compiler was saying，Hang on， hang on， hang on。

So why？Aren't we seeing that here right and we're not seeing any warnings here？Perfect， right。

 so we know there are exactly three ways to construct something of type fabric。

 We can use the linen constructor。 We use the cotton constructor， we can use the wool constructor。

 And those are the only three ways of making something that is going to have type fabric。

 So as long as we've done the matches for all of those。 We get to go。 We don't need any well causes。

 there's no other way to land on something that has type。😊。

What other questions might be coming up for folks。I think I understand the question。

 So I think this question is， what if we add in silk， right。

 We now have an additional constructor that we could use to make something of type fabric。

 And now is it going to give us the warning。 Do you want to make a prediction。Great prediction。 Yes。

 it absolutely warns us， right， So it's only if we have actually covered all of the cases that like if if we have covered all the cases and O Camel can also recognize that we've covered all the cases。

 that's when we're going to go。😊，Other questions， yeah。Great question。 So this question is。

 we could obviously fix this by adding the match with silk。

 but could we also fix it by adding the wild card that we were playing with before。😊。

So let's clear this and find out。要办。被当时。Great question。 Okay。

 so we know that there's only these three ways， and we've already covered it here。

 What's going to happen。 So again， let's clear。Morning， redundant match case。 right。

 So it's the exact same situation as when we had a wild card followed by a wild card。 Okay， saying。

 you've already covered all this。 Why you have that wild card in there。Okay。

 I think I might understand the question。 So this is saying。

 what if we made a thing with the silk constructor， We do， in fact， have a silk constructor。

 and it is for type fabric。Do you still want this wild card in here？ No。

 you want to remove the wild card。So let's clear that and let's run。呜啊哦。All good。Nice。Co。

What else are we wondering about？Having questions about。Yeah。Oh， I'm so glad you asked that。

 So that comment was， hey， why did the rest of the program still run。

 even though we ran into that era， So like we can see that the line that talks about line cost per yard。

 I didn't update the string。 we can see that that's not here。 But all these other things ran。

 So what we're actually in inside this silly little Oaml playground website is actually a rep。

 So a read print loop。 So this is not running a program in the classical sense right So when we were back in the situation of building that compiler compiled M that was just here's a program we're gonna run from the command line although we actually did also interact with it via the rep。

 when we opened up。 So you can also interact with your programs in the Reple But yeah。

 when we're doing the read print loop， basically if you take a look at every place where I've used the double semicolon here。

 That's just communicating to the read print loop， give me some output from this give me some output from this give some output from this。

 So this is as if I tried something that didn't work and then tried a bunch of other things that did work。

 That's what's going on there。So glad you asked that， yeah， great question。

I think this is this question。 Can we go ahead and have。Like everything's good， we're only using。

 but do we have to？You can get start to get a hint from this red squiggly line。

 but let's run it just to see。It doesn't like that。

 it doesn want the constructors to have a unique name for that type。

 so it's totally fine if we have some other type that also has a constructor with that name。

 but within the type。All right， we are at the end of class if you have questions please come down and hang out。

 but thank you all for a lovely second session of class。Amazing， what we got。

 So it's kind of still I'm still kind of。

![](img/8988002a35f2508a39599753650b3add_44.png)

I up on the constructive thing， yeah。