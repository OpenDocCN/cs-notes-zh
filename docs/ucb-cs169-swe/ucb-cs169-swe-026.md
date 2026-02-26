# 026：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p26 26 CS169 26.zh_en -BV1UsB7YPEMj_p26-

。没有这事。I this any known been on a We association。Hello what time。哦，拜。I this a black out your。 Can any。

Thinking that。P Valley received。That。Take the address。我系贵你。そすげえみたいた。Wait， yeah。

 that's just standing here， right？Yeah， that's。个。The turn on。Here， I can just look at it。嗯。Yeah。

 you good。 You're good。 yeah。But robots we actually。 So oh， yeah。Yeah， alright。

 our 15 minutes are up。 again， we thank you for your time。 And please。

 if you haven't filled this out， please do fill it out by tomorrow。😊，Yeah， thank you。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_1.png)

Yeah。Alright。Yeah。Get inか。なり？Okay， all right， let's go。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_3.png)

もし。そ明大。けい。对。系。な。有。嗯。M。Okay。いが出る。With people sitting to that， there's a few open keys。

in the middle here。And also。发律。Allright， so。While I am getting things reconnected to the internet。

 the way this is going to work。Six minutes， you're going to switch off。

 there is one master Google slides deck that we're going to be using。

I will warn everyone ahead of time that a lot of you have very beautiful presentations that are going to be too long for six minutes。

 so if you need to go fast， that's all right， if you decide on the fly that you want to skip a few slides。

 feel free to do that but we will be strict with timekeeping other than that the first announcement I have not had a chance to post on Piazza yet。

 but the homework 8 extra credit deadline， I'm extending to Monday night so you have a chance to work on that if you'd like。

And。Aside from that， we can have team3 come up here so that we can get started。Yes。

 the form that you'll be Yes。 Oh yeah。 the， the reviews form is posted in general in Slack。

 It is an annoying URL。 So just open that up and the。

Before each presentation is the list of groups who should be reviewing that is also on Piazza。

 so if you look at the Piazza post， it will tell you which groups to review。

 if you are here to do extra credit reviews， pick any four teams during this session to get your extra credit for doing reviews。

A going using the microphone yeah， so the easiest thing will actually be to have people， yeah。

It make。 testing one piece。I。Testing， testing， all right，是。Part。切がないです。我想学的戏是。Yeah。家嚟我佢放声下。Okay。Yeah。

 yeah。It'll be， yeah， it'll be helpful for people in the back potentially。

 but just like you can just pass it along。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_5.png)

So this is also going be recorded， but not publicly available。 so it will be helpful for that。

 and then you can so。if someone else， you can also pass this mic around too you。

We have two to pass around。optional1，2，3， you can also pass this along if you want to talk that as well。

Yeah。本くないです。Hello。啊。No。Yeah。Hello。呃。I this working。Pre。you can just start just like pressing space。

 so whenever you start talking oh it's already on。Oh， it's on。 If you just talking into it， Oh yeah。

ち。Why there isn't an house。Is there a question？So are the team that are reviewing this。

 the one that's like next to the number， or is it， are we reviewing the one next to？So teams。Five，9。

 13 and 16 are reviewing this presentation， so after they're done， you should fill it before。

So like on Piazza， the post is at the bottom， it says like team free。

 and then it will say like those are the ones that you're reviewing。Wait， so question Yeah。

 if it says group number and to review right Yeah， I assume it was the numbers that I to review are the ones assigned。

 number3 would have to review by13 I put， I may have put this wrong on here Yeah。TheYeah。

 it's the other way around， ignore that from now。All right， now I get fine。

This is why happens when you do things at 1 AM。We will fix the slides， followed piazza。

And where're getting get started？Good， everyone。我来。Okay。Hey， everyone。 Good morning。

 We're really excited that it's our very last lecture。 We are group 3。

 and today we will be talking about our project， The BJC teacher tracker。

 For those of you who may be a little unfamiliar with BJ C。

 The BJC stands for the beautyy and Jo of Comping， which is an online computer source curriculum that is designed for high school juniors all the way up till college freshman。

 The introductory version is actually maintained and run here at UC Berkeley by Professor Dan Garcia。

 which is package in the form of the very popular course C S 10。

 So our project was essentially designing a web app to actually track teachers in terms of applicants and manage the system completely online。

 So my name is Veroon。😊，I'm Kimberly。I'm Dalton。Okay so on what the BJC teacher tracker is so BJC is an introductory CS curriculum just like Verone said before that's developed at UC Berkeley so there's a teacher guide and solution that they provide that requires teacher access and so that's the main part we were working on the BJC teacher tracker is a new project for fall 2019 So we started the project from scratch and for the customer features for the purpose of the app there were three main things so first was the form submission for teachers to request access to the curriculum then we had admin ability to easily approve these teacher requests and third we had admin view on statistics of the kinds of teachers teaching the course and the schools implementing it and who was using which type of course。

So onto a small demo of the app now， so first this is the homeage of our app。

 so the first thing you see is the form submission for teachers to request access to the curriculum so you can see all the different fields for us to gather data on the teachers and then the school information。

This is the form filled out。 And then you see a confirmation that the form was submitted。Yeah。

 and then the second half of our app is meant for admin so here an admin is able to log in using the Google account and once they log in there'll see this information which allows admins to validate forms that have been submitted by teachers and then also below that we have course statistics and school statistics counting what types of teachers we have in the database and which how many teachers are in each school that are in the database and then below that we have a map with pins at every school where there are teachers in the BGC program。

And then if you try to delete a form， then you get a confirmation message so you don't accidentally delete an important form that a teacher has submitted。

Yeah， so one of the core functionalities that we had to add in this application was actually automatically sending an email to teachers who were approved in the system。

 So as you saw in the previous slide， every applicant actually had a validate that is approved or deny button next to their application。

 And if the administrators decide to actually validate these teachers。

 then our application would automatically send an email to set teachers inviting them onto our platform with a respective username and password。

 So this is sort of what one email looks like。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_7.png)

And this is a template that we're using currently。Next slide。

So in terms of technical challenges and the design process that we had to follow。

 some like the two biggest problems that we had were actually integrating Google O2 with our platform。

 because we had some security issues。 And also deploying our service to Heroku was a little challenging because we were using SQL light 3 in development。

 But as you all know might be familiar by now Heroku doesn't support SQL light4 production。

 we had to shift to Postgres。 And that was a little messy at times。 in terms of our design process。

 one of the core challenges we faced was actually modeling the information correctly。

 That is choosing the appropriate models in building the appropriate relationships between them。

 at times， we were trying to actually access foreign keys of tables that we didn't actually have to。

 And that meant that we actually had to cut down on what we were doing and keep it extremely simple。

 So we added functionality to our application first。

 And then in sort of like a bare bones fashion and then build style on top of that。

 And that's how we sort of got。😊，To our entire depth process。Okay， so interacting with the customer。

 Michael was a great customer to work with， we always had a clear understanding of customer goals。

 He always told us what the priorities were in terms of which features we shouldn' have went first and we always got great feedback on what we implemented so we always gave us a little tips to make our website better cons。

 we slightly over promise at times were every week there was like one feature that we didn't quite get to that was unfortunate and Michael always says that you're supposed to under promise and over deliver so we didn't really do that。

 and then it was trouble finding time that works for everyone。

 there was literally not a single hour in the week that everybody was free so we'd only get like four or five people for a customer meeting。

And then in terms of the team technical approach， there were some things that worked well for us as a team and some things that we could have definitely done better in terms of what went well。

 we definitely did a good job of following agile practices from week to week and from iteration to iteration we had customer planning customer meetings iteration planning meetings retro meetings every two weeks and then made sure to have standups at least twice a week to make sure we were all in the same page at any given time。

 we also did a good job of having smart user stories and using pivotal tracker to assign points based on how hard each story was and how much time they would take and we also tried to practice pair programming as much as possible assigning two people per major story to offer like advice to each other to help each other out and make sure that no one was like separated everything alone we also had some things that definitely could have gone better we wanted to try to deploy once a week but it ended up actually being once every iteration so that's something we could have done a little better。

 and then we also would have tried to meet in person。😊，And a couple times more。

 but like Dawalson had said， it was kind of hard to find a time where all of us were free。

 so it ended up being a lot of remote meetings which often led to like miscommunications and stuff。

 but overall，😊，Thats where pitfalls for。Future developers in next semester。ok  sorry继你啦， yeah系。

Thank you。😊，Next team。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_9.png)

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_10.png)

ややや。It me。我。I agree。Yeah you。All right， just to keep things moving along when they are finishing up their presentation。

 if you are the next team， if you could start sort of quietly getting up。 Yeah。

 so whoever wants to start， you have six minutes from。Talking just space。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_12.png)

到。Hi I'm Nicholas Ruin， our client was the stageage Mentorship Project。

 this is an organization that sends UC Berkeley students out to local elementary schools to provide mentorship to at risk youth through both academic and extracurricular activities。

Some of the issues that they wanted us to fix were partly related to their paper check in and checkout system that they used。

 mentors would show up for mentorship assignments and they'd check in on a piece of paper and sign out this required manual re-entry into Excel and also sometimes people would forget to check out and also their friends would check in for them if they didn't show up to their assignment。

So the ways they wanted to fix us were to create a new web check and app that requires Calnet authentication and also shows and tracks the geoloc to verify that the students are actually signing in at the school they're assigned to and also allow Excel data to be exported。

And pass over to garage。Hello， everyone。 My name is Rod。

So the biggest technical challenge that we had during the project was integrating geoloc in the app。

 The problem was that we were using different services provided by rails。

 And then it was not giving us correct geoloc of the user。 And also。

 it was very in inconsistent when the user was logloging in mobile using mobile versus laptop。

 And then they were also is issue while masking the geoloc while sending it to the server。

And the way we solved it was we frequently visited office hours。 We talked to T A and asked for sub。

 We talked to team members and asked for feedback and Su on what to work on and how to improve it。

 And we ended up using the factory pattern from Google API。

 and we to integrate the Gelogin in the app using Javavascript。 Yeah。

 So that's how we solved the problem。 And I would like to pass it to2 now。😊。

So I'm gonna talk about our customer collaboration， and。Okay， so our customer was Jasmine。

 She's actually a data student。 And we corresponded mostly through remote and inper meetings。

 So the good things about her was that she always gave us definite goals during each iteration。

 So we always knew what we were working on。 And when we came back for meetings。

 we always had clear feedback from her。 So we knew what we had done wrong and we had done right。

 And also， she was also very impro in making meetings with us。

 she always came on time and we always found good times to meet。 And， you know。

 she was generally a really nice person。 But some of the cons was that sometimes she didn't respond to our emails on time。

 So we would be lacking on some of the assignments we had to provide on courses because she didn't respond。

 But this was not a very big issue。 So I'm gonna pass on to China。

My name is Raymond so some of the things that really worked for us was really good communication。

 we had a Facebook messenger， we sometimes didn't use a flag， but we really communicated very well。

 we would meet in person， we would have remote meetings and also I think most people had very good experience with G so we had to quite minimum reasonable amount of conflicts and we're also able to sometimes like have very effective retro meetings we able to plan and look at what worked and what they didn't work for us and some of the accounts where that sometimes we wouldn't fully finish some of the iterations and we would run into because sometimes we would just overestimate the iteration reading carefully in terms of agile development really carefully sometimes assigned the points to give to each feature and that's something that we could have done better on and yeah I'll pass it on to。

true。So for the previous step I want feature developer。

 the first thing is our test allowed compete because we didn't wait our test before coding and we didn't have enough time to finish it。

 And the second thing is some of the code may need more reffactortering。 So because some of the yes。

Okay， and because some of the code just like a lot easy to understand。

 And they are not much comp documentation。 And the last thing is the access control。

 We are doing it with a different before action methods。

 And as the authorization levels of different users get more complicated， it would be very messy。

 So I would recommend using some sort of S control driving instead。 And then I will pass it to k。

If we had two more iterations， this is what our plan would look like。 robust testing。

 This is what we had a pitfall。 We started testing late。

 and we realized that we couldn't discover more Sapath as we could have if we had more it if we had more iterations。

 and the next part was if we had more iteration， we would also try to encrypt the data that we are feeding in like the geolocation to prevent any kind of data leaks and and the other thing we realized after doing the extra credit homework is the accessibility part that our website wasn't performing really good to the screen reader。

 So we would also like to work on that。 since we are collecting so much data as from the user we also want to integrate some kind of data and tool to actually visualize the data rather than just showing it in a blank database。

 And also the last thing we wanted to include was a notification system。 So if a user did not。

NotCheck out on time。 We would notify both the admin and the user that you were not able to check out。

 So this is what we wanted to add as well。Thank you。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_14.png)

Just是。For anyone using the mic， if you're using it， just hold it closely。

 And then all three of these mics work as long as you hold them closely to your mouth。

 So you can just pick them up to if you want to switch off start。Thank you。😊，And ready。

ITry to give you three two in Monday。Okay so our project was for Calners。

 which is an organization on campus， they required a student director scheduling tool in previous months they've been using Google Sheets to track student director's hours which is a problem because student directors can have both variable and fixed hours syndicate when they're definitely in the office versus when they might be in the office which is a problem in both organizing the student directors and in calculating the hour totals that the directors of Calalner's need in order to manage their budget so our app is meant to one make it easier to track student hours when they're in the office using both variable and fixed times and also to calculate our totals and one of the most important things that they wanted was for it to be a mobile friendly app because usually the directors are out of the office so there's a high amount of times when you're going to be using the app from mobile device so responsiveness was definitely important thing and they also wanted us to be able to send room。

Minder emails to student directors to submit their schedules because it had been a problem in the past so and they weren't doing it on time。

Okay， so for our schedule submission form， we modeled it after went to meetet where we had a table and each time slot was in each cell。

 and the table interacts with JQury using onclick events and this allows for intuitive use for the directors so that they can easily submit their forms。

To send the omitted email message email reminders， we use the jams action mailer and Ruer Schr。

For testing our features， polulttergeist and selenium were used to test the browser and jascript interaction and timeco and email spec were for the reminders。

Some challenges we had were。Using the different databases in dev and production。

 because SQL light and Postgres work differently， so we had different configs for each of them。

And we had trouble testing the session hash。Regarding our customer interactions。

 what went really well was our bire meeting with our customer。

 we held the meetings at the end of each duration during the meeting。

 we show our customer the features we just deployed and was requested from our last meeting。

 And then we discussed the expectations for the coming iteration。 And there are few things we。

 we could have done better First， our customer was a little bit hard to reach in between meetings。

 Therefore， it causes some confusion during development。

 Second thing was that we were unable to show the customer the states of our app before the meeting。

 So they have very few preparation time。 And what we have learned from this whole software development experience was that our app affects more people than our customers because like we have our administrator and we have our student directors。

 So they kind of want different things from our app。

So these are the four agile development that we tried to follow during our project。

 The first one is team interactions。 I think this went pretty well using Slack。

 It was a set of problem with some people's。And it would take a couple days before they was swap。

 but in general， I think that one went pretty well and it was good that we could communicate remotely because not everyone one was available at the same time。

 working software part went very well， I think probably the best of these four because。

Because the agile development practices is very easy to have the software evolve evolve quickly every time you push a feature it。

Show up an app immediately。 The customer collaboration probably needed some improvement as mentioned before。

 there was the problem with interacting with a customer outside of the scheduled meetings。

 So during the meetings it was good outside of the meetings。

 it was a bit harder just to contact informally and ask this is a good feature is something you want or do you prefer A or B and the final one is finding to change。

 I think this is how we managed iterations because。Okay， so final change。

 I think is how we manage generations because not everyone had the same schedules。

 so it was as long as we were able to be flexible and adapt everyone's different schedules because like maybe someone will be more busy over because of mid or something so that's how we manage generations and make things kept moving。

All some of the future pitfalls we for saw over the course of the project was that student directors are going to change over time and some of the information that was in our application was statically coded so we are going to need to make that dynamic for future student directors who join the organization and also currently our app is only designed for scheduling purposes and so if the organization needs it for a different purpose that's going to be a problem to adapt to other needs the organization so it's only going to be useful for scheduling purposes。

So regarding future iterations， as Austin already mentioned。

 we wanted to add the ability to change student directors photos as the semester goes on。

 and also we want to work out we want to work on their layouts and C S S for that because it's not very visually appealing right now。

 So， for example， the one thing we're working on right now is the more intuitive calendar interface and also Diane specifically mentioned that she wanted to be mobile friendly。

 So that's we're working on right now。 And also we want to add more structure organization to the scheduling model class such as you know group by month by semester and or maybe add like working total hours for student directors and last but not the least。

 you know， just write more aspect spec test because always good。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_16.png)

。So。じら他。Okay， that's wonderful。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_18.png)

水。Just hope I post your mouth。All right。Hi， we're team 9。 and our。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_20.png)

Customer with Hispanics and computing。 So first off。

 we'll go over some customer needs and basic features and a short demo。😊，So who is a customer。

 The customer is Hispanic in computing， which is a community of Latinx and Chicanx， students。

 professors and other industry professionals that all share the common interests of computer science。

 and the sole purpose of the group is to serve as mentorship and sponsorship。😊。

So our app is a brand new app， which is an interactive map。

 So we migrated the existing website to a rails app。

 and we also added new functionality for a member's profile page， as well as interactive map。

 And I'll go over the features with the demo。 So as you can see the old website was a little clustered。

 and it was a little difficult to read。 So we delineated the sections better with some like more padding text hierarchy。

 And we also had anchors since it was more of a vertical scroll page。😊，And that was the redesign。

And this is supposed to be a gift。 but oh yeah， it works so that you， you can log in through Gmail。

 And this is cross checkck with the Slack Work membership for the existing app or the existing group。

 And you can view your profile。 You can also edit it。

 and you can also choose whether or not you want to be visible on the map for privacy reasons。

 and you have some basic information that will all appear in the map pop up。😊。

And after editing your information， you should be able to go to the members map and see everyone else to allow their information to be public。

 and then you have some basic contact information there。

 And since were like dealing with people's location and contact information it's really important to be secure about this。

 So without the authentication， you'll just get a flash notice and won't be able to access the map。😊。

So the main technical challenge we had was being able to check if someone was a member of the Hispanics and engineering group in order for them to have access。

We first wanted to implement a LinkedIn login where we would check if someone was a part of the Hispanics and engineering LinkedIn group。

 but LinkedIn's API was too restrictive and didn't allow us to do that。

 and we ran into a similar problem with Google's API。

 checking if someone was a part of a Google group。So what we ended up doing was。

Using the Slack Hispanics and engineering group。So people would log in through Google and then we would check against all the emails in the Slack if that person's email shows up。

 if it does， then their data is added to the database and we use the information from Google to populate the information in the database with that user's information。

So the way that we combine these two things was in our user model。

 We have a validate and create method that takes in that authentication hash that's given by Google。

 So that contains someone's information like their first name and last name and email。

And then we call the Slack member emails function， which gives us all the emails in the Slack group。

Yeah， for the customer interaction， we did put the group in that we always put clients needs and requirement at first。

 and we always ask for the next meeting time at the end of the current meeting。 However。

 we should have sending a follow up email if the client not responding within a few days because that eventually causes the delay of our first iteration。

 And also， we should have updating progress with our client more frequently。

 not only just updating during the customer meeting。So some development practices。

 this is our basic workflow， we would have a customer meeting。

 and then we would have our IPM where we would assign point values to stories that we'd created。

 then we'd go into development and at the end of the iteration， we'd have a retrospective。

So our very first iter0， we met our client， and we started up setting up our foundation on Git。

 pivotal and Slack， other tech， too。So this is iteration one where we would take our this is basically every iteration。

 but we would take our customer meeting， turn them into stories and then into features eventually。

 so these are just some examples of that。And what worked well on this iteration was we had really clear communication。

 We were talking all the time， used when to meet， and we found a couple times that worked for everyone or everyone。

 but one person， I guess， and we also had best practices when coding to the best of our abilities。

 tests， clean code， proper gate usage。So as we settled in in iteration2。

 we were better with our test coverage because we implemented the new tools and we had much more communication between members over what our skills were。

 however， we had some problems with our customer response and this iteration and it slow us down a little bit。

 but we were able to fix that in iteration3。So iteration three。

 we really came together and split up into two teams to kind of get both sides of this working and then bring it together。

 but we sometimes lacked our communication in those commits and changes。In iteration four。

 this is now， so we have all our need to haves and we're working on our nice to Hs and we're doing really well with that。

 but the pressure is causing some stress。And then's just warnings for the future。

 the user authentication for being in the Slack group， the Macbox。

 and the leaflet only has functionality for small models of traffic and the geocoder might cause some problems。

And for the future， we really want to implement admin blog posts because every year they have a topia conference and they have a new page for the conference and to go into the code and change it is pretty cumbersome so we want to make them be able to add a new page without changing the code。

 we also want additional login options with Slack which makes sense because it is a workspace that we're cross checking and also LinkedIn。

😊，And then finally， we also want more fields in our pop up so that they have more information about the people that they want to contact。

And finally， we have we want to filter。Yeah。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_22.png)

It。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_24.png)

嗯嗯。All right， good morning everyone So today we're gonna to talk a little bit about what we worked on this semester。

 we created a web app that helps connect computer science students to tutors at UC Berkeley so we're gonna to talk a little bit about what we created how we made it and a couple of things that we learned in the process which was a learning process。

 of course， so we'll dive right in the first thing basically that we should mention is that we were starting with legacy code which as many of you know could be a double edgeged sword because on the one hand the team that came before us did get halfway there to implementing a lot of the functionality in the app。

 which was really helpful and it got us off to a good start but on the other hand it did cause a lot of growing pains there were kind of extensibility issues maintainability issues all those things that come with it I think Louisis will talk a little bit about that more but overall the project that we were working on was a project。

made for Christopher Hunt， professor here at UC Berkeley， who teaches CS370。

 and he wanted to create a web portal that would help connect UC Berkeley computer Comp science students with his grad students as tutors and so in the app。

 students would be able to request a tutor for a class like 6 to1 B for example。

 and then a 6 to1 B tutor would be able to accept that request， set up some meeting times。

 the student could accept the meeting and then after the meeting they could submit an evaluation and to this point we've been able to deliver all these features and a couple more。

So the challenges that we've， yeah， yeah， okay， the challenges that weve faced。 So definitely。

 as Clark was saying， like I you code is one of the biggest challenges that probably a lot of us faced and。

😊，For us， one of the biggest things was a lot of the tests that were written for the code were like really hardcoded based to what they were doing。

 So for example， when we changed the like test users or like simple things like that。

 like three tests would fail and then nothing would work。

 So it was kind of hardworking around that Another thing that we faced was the design changes and it was because at the beginning of how the platform was made。

For a student and a tutors to meet up， they would have to like change email is like three or three the back and forth right And that's kind of annoying。

 So as we were going through， we realized， hey， we need to add a functionality for setting up meetings and that was kind of like a big thing that we kind of just like end up realizing like halfway through。

 So it required a lot of like design changes。 and then last but not least like we definitely had to do a lot of learning。

 We definitely had to do a lot of research in our own Google was definitely the biggest tool that we used and you know simple things could be like for example。

 one of the ones that I can remember very clearly was when we were doing the meeting setting up the meeting part。

 we would do like an email， I mean a date type in the HTMLml and then a time type and that works very well in Chrome。

 but it doesn't in safari and it was just kind of annoying seeing that So yeah。

 there was definitely a lot of challenges but definitely a lot of those learned。😊。

So our customer was Christopher who worked under the Es department。

 So the interactions were pretty straightforward。 initially。

 it was kind of hard to get him to get him to actually get type a meeting with us for iteration  zero。

 But eventually once we started to get that， it was fine and we did have regular meetings right after our discussion on Tuesday。

 And the first 30 minutes of the meeting would mainly be discussing what we did in the previous iteration and showing him all the features。

 And then the next 30 minutes we just be talking about what features we want to implement for the next iteration。

😊，And we did have great interactions。 In fact， there's another group working on the same application as us。

 So it was kind of hard to he made it pretty straightforward on what features we needed to create and what features the other group was creating。

 So there was no clashing in between。 and we did have good meeting notes which also helped for us to be clear on what we needed to do for the next iteration。

😊，Yeah， so throughout the agile life cycle， we found that what worked best for us was just communicating consistently and holding each other accountable。

 It sounds simple， but we found that it was easy in between IPms and customer meetings you know take our stories go on an island and work by ourselves。

 so we made a point to be diligent about checking in with each other pair programming often and if someone if we found that someone was falling behind or missed a meeting。

 we made sure to send them the notes， hop on a call with them and make sure that everyone's on the same page all the time the biggest thing that didn't work for us was the inconsistency of the forms of communication。

 we did try to stay on Slack， but you know I would shoot an eye messagesage to a friend for something quick or Facebook Mesenger。

 we would also use sometimes。The problems that would lead to are if I would try and go back and see a screenshot or a link to something。

 I would often lose it。 So that was pretty difficult。

So some pitfalls for future developers like we've reoccurring theendum in this presentation。

 like See code is hard， a lot of the code was undocumented and kind of had multiple files that seemed to do the same thing。

 but in reality was hard coded someplace else with tests。

And also we had to understand the code before making modifications。

 This sounds like something inane or something that seems reasonable。

 but especially when we were starting out and we were really eager to work on the project。

 we would often delve into the code and try to make changes without fully understanding the interactions it had with other codes。

 This led to problems because eventually these changes would be unusable or they would fail certain tests and so forth。

All right， so looking forward， we ideally would have wanted to set up CS colors priority and a more seamless time meeting location with Bal。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_26.png)

こ才这个。嗯，H。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_28.png)

や。どします。It should， but it's not guaranteed I just read the restaurant， so I think it should。啊等呢到时。你说し。

St。All right， hello everybody， weird team 13。All right。

 so team 13 today we're going to talk about our project。 We worked with a CBV X stem。

 This was a project introduced to us by an X CS S 169 student。

 It was her mother who ran the oh is the。Something wrong。Oh yeah。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_30.png)

Refresh。Sorry， we just bear with us for a minute。I just heard a question before。就像看的时。

told the order from the you right now。video。Think the presentation is not video。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_32.png)

大しな。会也前下。bit in the。How他边他。Oh， you cannot use。My shit name。可十。 we cannot use our own presence。

 we already have， if you should。Right。Just。Okay， okay。

 so basically we're group 13 and we worked with this company called CBVX STEM。

 it's a stem cell treatment clinic， it was introduced to us by an X169 student's mother and basically the aim of this project was to connect doctors to patients and Ily we could have showed you the pointers。

 but basically the idea of this portal was to allow patients to upload forms to the doctors。

 allow the doctors to track the patient's treatment history。

 the medical history and to assign different treatments to the patients。

Next we talk about our customer。 So this is the picture of our customer。

 So overall its a very nice customer。 always respond to our email on time。 And he also is a C 61。

69 student in previous semester， our fully。 And there's several problem we are having。

 So first we have a lot of feature it。 So that's why like our customer sometimes I really con。

 And to deal with it， they actually have a internal Hi code for our customer。

 And every time when we create a new feature， we actually send an introduction and a small video clip。

 And we also like prepare a lot of prototype before the call meeting。

 So those is the demo for the protocol that we hear。Okay， so technical challenges。

s like this slide didn't load either。 So basically。

 our biggest challenge was that doctors and patients had different levels of like。

Accessibility and management ability for every single resource。

 So there's information that doctors are privy to that like patients should' be able to view。

 So we have some trouble with this because originally we had like in our first iteration。

 we tried to kind of card coding these like limits into the different controllers。

 but eventually move to using a gem called cancan in order to sort of centralize having all of like these access limitations in one place。

 The other thing was that there were like resources that were related， such as like medications。

 documents and treatments， but they didn't belong to each other。

 So we needed to have a way to like have them be able to like have routes in such that pointed to each other more easily。

 But it was a little bit difficult to do that。 So eventually we had an interface called like user holder that would help to like have all of like these related resources point to each other。

😊，Okay， for the team practices we agree on the goal of performing two points of work every iteration。

 So the workload for everyone should be almost the same and。And for frequent communication。

 we hold stand ups on slackla every two days。 Also to make our peer review more objective。

 the Sc master will write the individual evaluation for everyone after the retrospective meeting。

 And that's the， that's what I think we are done pretty well。 However。

 we didn't do much pair programming due to scheduled conflicts。And。

so pitfalls for future developers is that we'd recommend using testwork frameworks more intensely because one thing that we saw that was an issue was that when we would try when we finish our own feature。

 when we tried merging it with the rest of the code。

 sometimes we would cause pitfalls and other people's code features。

 so that's one thing we'd recommend is to test the features for everyone's code collectively before merging it to the repo the master。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_34.png)

We had more time， some things that we would have liked to implement。

 first is that we would like to have a better U I。 So like a more responsive web design layout。

 right now， it's a little bit ugly because this is a new project and。😊。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_36.png)

Yeah， so it doesn't look that great。 And it would be nice to have like a message like messaging within the platform。

 instead of having to rely on external communications such as emails and Whatsapp。Okay。

 and we'll show the demo of our application。 And I' will introduce Peter as a patient。

 which who has a head headache。 And even as a doctor and Peter want to make an appointment with her。

 And he can receive。 She can receive some feedback。 And here's a demo。As a patient。

 I'll log in using the patient portal， and then I'll go to my profile。

 update everything as I see fit， I can submit these changes via the submit change button at the bottom。

 and then I can go to my notification settings and look at both in my email and whatsApp notifications I want to be notified for everything。

连续。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_38.png)

嗯。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_40.png)

When you're ready， just grab a mic。う。sure。Itsmic all three of the mics work。纯街。家听后。哦我。Hello， okay。

Okay， so hi， our， our team is Lyme， and we worked on the Ctrus Legacy project with Jill Finnin Lason。

 and he's our team。So our team worked together pretty well and often used pair programming whenever we could and met up often for our retros and IPMs and try to keep up with most of the agile practices Now working with Jill was great as she responded quickly to her emails and was very responsive to our ideas。

 but something that we experienced that was a little bit frustrating was that we'd constantly have new needs and requirements for our project and often change our backlog and that like just change up like what we needed to do and what we understood from the project initially we think in the future。

 we should under promise more and for what we could deliver and be more upfront about the things that we didn't think we could achieve given our time。

So our project was to build upon an existing website that holds innovation resources here in the Berkeley community hosted by the Char Di Center and automate a lot of the tasks that admin would need to do to keep the website up to date。

 We worked on creating an interface for resource owners to edit their resources that they own。

 rather than submitting their updates for an admin to manually update。

We focused on scheduled emails for various scenarios to build tools to automatically check our database for valid links and send reminders when entries were broken。

We also worked on improving the user interface。So here's a site of， or like。

 here's an image of how the site looked when we started and。

We've got to include like a the follow up， but this is how it started。

So the first challenge we got was to understand the legacy jam cause device。

 which is used to generate a user system to allow the resource owner to log in。

It helps a lot to read documentation。 and when we run into issues。

 we also go on stack overflow to look for solutions。That you phase。

So one of the big requirements that the customer wanted was to schedule emails automatically and we had a lot of trouble doing this initially so we were looking through a bunch of gems to use and we weren't sure what to use and we eventually settled on using action mailer that was built into rails。

And there was a lot of trouble testing as well， but we eventually got that fixed。

We didn't know why emails weren't sending at first。

 but it turns out after like three hours that Gmail had this flag or it doesn't allow less secure apps to access Gmail and then once we turned that on。

 we were able to actually send emails。And for scheduling。

 there was a difference between scheduling on the local machine where we use this gem called When and actually scheduling on Heroku。

 So we found this add on for Heroku called scheduler or Heroku scheduler。

 But it required a credit card。But we eventually got that as well， so。

The third technical challenge we had was working with legacy code in particular。

 finding out where in the front end are changes being produced because legacy code used a mix of react and then H TML embedded Ruby。

 And then what helped us was the global search function in the Ruby My I D E。

 and also working with the Chrome developer tools in mode and also collaboratively talked through the code base。

So things that went well， I think that our team did a really good job at using pivotal tracker and breaking down really large complex problems into one or two point stories and then keeping pivotal tracker updated and then we also worked really well as a team so we had a lot of meetings and if we couldn't all make it we were sure to call and text and message afterwards to make sure everyone was on the same page after those meetings and then we also did a lot of pair programming which was really useful because legacy code is really challenging to code and so I thought that it was very helpful to work with another person and understanding the code base and then implementing those features。

So some of the things that could be improved， some of us worked on like the same features or like front end or back end throughout all the iterations。

 So I think it would have been a better idea to probably like switch roles and like features a bit more instead of just doing like what we were stronger in also more program pair programming like a lot of us did pair programming。

 but some of us worked on stories alone so。There was like less pair programming for some people。

 And then also just like spending more time writing the tests before rather than discovering the bugs later on and then trying to fix them。

And then for future developers， some things we thought needed to be addressed。

 the security aspect should probably be improved because some features that only admins should see are currently also available to normal users。

 Also the overall efficiency， like the pages kind of load pretty slowly。

 So by restructuring the database that could probably be sped up。 And lastly。

 the email functionality since we're since it can like actually send reminder emails to real clients。

 it's important to be cautious of that while testing。If we had one， one or two more iterations。

 we'd implement data analytics， forget your password feature。

 and then also adding an H M L email template to make the automated emails look professional。

 Thank you。😊。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_42.png)

So' never ready。Yes。this one right here。So this like close or that one。Thank you。

 and then just space techniques。All right， ready。All right hi， everyone。 we're group 16。

 and in the past couple weeks， we have been working closely with Professor Fox and added new features to the existing app audience first。

😊。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_44.png)

And in short， audience first is an online ticketing system made for small to medium local nonprofit theaters and their customers and through our development timeline。

 we have definitely persisted in an agile development environment and something that really worked for us was that we conducted para programming as often as possible and we did weekly customer meetings instead biweekly and furthermore。

 we rotated to be the PM of the team and evenly distribute the work among group members。

 but something that didn't really work for us was the ability to keep on track and remembering submitting the B courses checkpoints on time。

嗯。So for our client relation， we had our weekly meeting with Professor Fox on Thursday。

 He's very prompt to our meeting。 at our meeting。 he usually。

 he's really specific about the features that need to be achieved in the next iterations。

He even creates pivotal tracker stories for us to further divide into smaller stories。 So。

 so we can learn about how to use pivotal trackers and assign points to ourselves。There are a couple。

 and we also have this question。 Google Doc。 We posted our questions on because Professor Fox is really knowledgeable in this field since he's been developing this app for more than 10 years。

 We posted our technical questions on this dogc and his。

He usually responds in one or two days so we can be more productive in addressing the problems。

After reading his answer， yeah。So there are also a couple comes in our customer relation because he's really knowledgeable in this field。

 Sometimes we tend to rely on him too much。 what we should have done instead is to。

Explore the code bases and the database ourselves so we can learn about certain tools like Travis C I and some Ruby jams ourselves instead of。

 of relying on him too much。And I like to briefly talk about some tasks we work on as our warm map tasks。

 So essentially， we have two types of users。 The first is the theater admin in the second is the customers。

 So the first warm map task we work on was to modify an existing feature。

 which allows the theater admin to give out free come tickets to customers。

 And the issue with this feature was that the admin has to specify the show when giving out the free come tickets。

 And what the new feature we implemented allows the customer to choose the。

To choose the show upon receiving the freecom tickets and by choosing the shows in the dropdown menu。

 And the second warm up task was to allow filtering by subscription types instead of by like the old feature。

 which is only filtering by subscription year to generate a customer report that allows admin to download as Excel files。

Okay， so now we' talk about some technical difficulties and some technical details。 Our final it。

 our final feature， which is six stories， took us about two iterations or about four weeks to complete。

Specifically， when a customer wants to make an order。

 he or she has the ability to enter comments regarding who will be picking up tickets at the show。

So originally， the enter comments is in the overarching order model。

 which means that we have one comment for the entire order。

 and our client wants us to distribute the comment into every single item， for example。

 like a ticket or a donation so that each ticket has its own information。

 The motivation behind this is， for example， say a person purchases tickets for his entire family。

 like say 12 tickets or 10。 But then some of the family members has a disability so that they need special care。

 by moving the older comments in the higher level into lower level ticket comments。

 the theory has the ability to show who needs special care and which ticket owner needs special care。

 and then this could be done specifically for that order。During the process。

 we had to modify lots of sections that involves Lexxi code because this is essentially a huge Lexi code base and we had to break up functions to involve these new features so that we can have more code coverage and test coverage。

And then we also have to delete some Lexi test codes because their intentions to the。

 the code they testing on is outdated already as we change the functionalities。Essentially。

 what we did is duplicate each order comment into that order。

 And then we modify this for future comments so that we did a sQl migration for future code。Okay。

 so instead of removing the other do comments from the controls and models。

 what we did what we also need to do is to make changes to the existing database。

 So because we are working on an application that is already in production and would we change to the existing database could have an impact on the application that is already running so that could mess up the whole app and a lot of users are currently using our app。

 So what we did is we made a lot of sqL command and use that command on our fake database。

 So apply those changes on our staging data。 So， and then we create the and make changes to the existing database。

 And of course， since we are working on existing app， we have to learn a lot about the le code yeah。

Yeah。Yeah。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_46.png)

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_47.png)

Okay， yeah。We're going to end just right after 11， but if we could just get started， so out there。Oh。

 this one。No all threemic but just remember to like hold it close。Anybody want to use this。ああ。

And we use the mic to yeah they we do one us on。Okay，Yeah。All right all right。

 everyone we're group 17。 we work with night out night off and so the main idea of night out night off is to provide cultural experiences for graduate students and especially graduate students of color and our goal was to create a repository of venues of places where these cultural events could be and there are three main features that we had on this first was creating the actual website and creating the database of the venues the second was to create like a login and user system so that people could come in and view it and add things into the database and the third thing was creating a review system so that graduate students of color could say that certain venues were more had more affinity to certain minority groups so that future minority students could go and check to see which venues they should visit。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_49.png)

It's not。it is it frozen。Yeah， I can't。 It's not。I just right click。

Yeah so for the login functionality， we use the Rails Dev gemm。

 this would give users the ability to add reviews or permission to add reviews and also access user generated information about the venue。

😊，For filtering， first， we would load the data through the Brailles Ro jamm。

 It was given to us in the format of an Xwell spreadsheet。

 And then we were able to filter by venue name， by rating， and also the affinity groups。

 which were provided by the client。😊，Yeah and continuing on with some of our core features。

 so you just could leave reviews for a venue， so we created a。

Reviews relation and with a foreign key so in one too many relationships so users have many reviews and venues have many reviews and then so yeah users can leave like a rating out of five stars and like text for review。

And then so when you click on a venue you get taken to a details page and you can see like a list of reviews by users and so yeah。

 you can see stuff like that average rating by users and then there's also upvoing and downing kind of less similar to Reddit so users can up good reviews and like reviews that might be like inappropriate。

All right， so now that we're going talk about some of the agile complications that we kind of ran into。

 So right off the bat like some of the positive stuff that we did was definitely being able to help each other out as much as possible have good stand-up notes and able to look over and merge each other's PRs relatively quickly and be adaptable to some of the difficulties that came up in terms of development but some of the difficulties that we had were merge issues because we were all trying to work on features that often relied on the similar parts of the codebase So when we were emergingrg PRs and stuff they were oftentimes like issues that came up with this。

 we also initially in the beginning had difficulty planning and setting time for our stand-up meetings and retrospective meetings but to combat this。

 we kind of all made sacrifices and became team players and move around different extracurricular activities that we had so that we were able to make time Lastly。

 the client kind of insisted upon using communication through Google Docs。

 which was a form of communication that none of us were really accustomed to using so we kind had to in order to overcome that had to adapt and kind of take on like their form of communication and really kind of bring ourselves up to speed。

I'm sure that we're communicating well。Yeah， so now we'll move on to technical difficulties that we faced。

 So one of the technical difficulties that we faced was that on our computers we're all using different versions of bundles and gems and rubs。

 And so this kind of caused some issues when we try to run our application。

 our individual computers and kind of。Gavees like separate issues and separate。

And separate debugging problems and another issue that we face was that so in our initial database we had dummy data and so some of this data would have licensing features or missing seeing attributes to that kind of cause bugs later on when we tried to actually run our algorithm our rating algorithms that Puja and Grant mentioned before and so so in our future iterations our handoff concerns would be。

woWould be figuring out how our application would react to different gems for updates and also later in our project we want to expand our database to in other counties so we don't know how our database will react to different attributes for the different so in terms of working with our client we started from scratch for're not working with legacy codes so they expected a lot just because it is a pretty big platform but we had to discuss with them and find a happy medium for sort of an attainable set of expectations and the other two sort of revolve around finding good mediums of communication so first you know we had some miscommunication through email in terms of updates and then also scheduling issues。

For future iterations what we want to do is increase beyond the Bay Area for venues so maybe scope beyond California as well as we increase in size there's going to be also be problems with scalability so we have admin users right now。

 we will probably want to have admins allow super users who can help maintain the website as well as increase and downvote certain reviews to improve accuracy of these venues。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_51.png)

Thank you。😊。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_53.png)

Yeah。Yeah。Have have to use like。The form， Yeah， no， yeah， the form， I get， But like yeah。

 oh here it says yeah。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_55.png)

I' swap they should match with piazza。Wait oh wait， these are the people who are reviewing you。

 All right，So one thank you everyone these were awesome presentations they are real issues that happen in real life if you are going for the next session it will be 105 Stanley we couldn't get this room so we'll start over there at 11 Tech but 105 Stanley。



![](img/ebacf8c8c75dba62751e1fad0ff9daf9_57.png)

其实嗰。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_59.png)

对啊。可以我。Okay。さそ。

![](img/ebacf8c8c75dba62751e1fad0ff9daf9_61.png)